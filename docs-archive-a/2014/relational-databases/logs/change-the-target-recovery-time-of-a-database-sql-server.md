---
title: Alterar o tempo de recuperação de destino de um banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/13/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c4331d2ade2819d172189a0de9daddecf3d9f6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572550"
---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a><span data-ttu-id="daf19-102">Alterar o tempo de recuperação de destino de um banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="daf19-102">Change the Target Recovery Time of a Database (SQL Server)</span></span>
  <span data-ttu-id="daf19-103">Este tópico descreve como definir o tempo de recuperação de destino de um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daf19-103">This topic describes how to set the change the target recovery time of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="daf19-104">Por padrão, o tempo de recuperação de destino é 0, e o banco de dados usa *pontos de verificação automáticos* (que são controlados pela opção de servidor **intervalo de recuperação** ).</span><span class="sxs-lookup"><span data-stu-id="daf19-104">By default, the target recovery time is 0, and the database uses *automatic checkpoints* (which are controlled by the **recovery interval** server option).</span></span> <span data-ttu-id="daf19-105">Definir o tempo de recuperação de destino como maior que 0 faz com que o banco de dados use os *pontos de verificação indiretos* e estabelece um limite superior no tempo de recuperação para este banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daf19-105">Setting the target recovery time to greater than 0 causes the database to use the *indirect-checkpoints* and establishes an upper-bound on recovery time for this database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="daf19-106">O limite superior especificado para um determinado banco de dados pela sua configuração de tempo de recuperação de destino poderá ser excedido se uma transação de longa execução provocar tempos excessivos de UNDO.</span><span class="sxs-lookup"><span data-stu-id="daf19-106">The upper-bound that is specified for a given database by its target recovery time setting could be exceeded if a long-running transaction causes excessive UNDO times.</span></span>  
  
-   <span data-ttu-id="daf19-107">**Antes de começar:**  [Limitações e Restrições](#Restrictions), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="daf19-107">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="daf19-108">**Para alterar o tempo de recuperação de destino usando:**  [SQL Server Management Studio](#SSMSProcedure) ou [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="daf19-108">**To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="daf19-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="daf19-109">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>  
  
> [!CAUTION]  
>  <span data-ttu-id="daf19-110">Uma carga de trabalho transacional online em um banco de dados configurado para pontos de verificação indiretos pode apresentar degradação no desempenho.</span><span class="sxs-lookup"><span data-stu-id="daf19-110">An online transactional workload on a database that is configured for indirect checkpoints could experience performance degradation.</span></span> <span data-ttu-id="daf19-111">Pontos de verificação indiretos garantem que o número de páginas sujas esteja abaixo de certo limite, para que a recuperação do banco de dados seja concluída dentro da meta do tempo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="daf19-111">Indirect checkpoints make sure that the number of dirty pages are below a certain threshold so that the database recovery completes within the target recovery time.</span></span> <span data-ttu-id="daf19-112">A opção de configuração do intervalo de recuperação usa o número de transações para determinar o tempo de recuperação em relação aos pontos de verificação indiretos, que usam o número de páginas sujas.</span><span class="sxs-lookup"><span data-stu-id="daf19-112">The recovery interval configuration option uses the number of transactions to determine the recovery time as opposed to indirect checkpoints which makes use of number of dirty pages.</span></span> <span data-ttu-id="daf19-113">Quando pontos de verificação indiretos são habilitados em um banco de dados que recebe um grande número de operações DML, o gravador em segundo plano pode iniciar eliminação agressiva de buffers sujos no disco para garantir que o tempo necessário para executar a recuperação esteja dentro da meta do tempo de recuperação definido para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daf19-113">When indirect checkpoints are enabled on a database receiving a large number of DML operations, the background writer can start aggressively flushing dirty buffers to disk to ensure that the time required to perform recovery is within the target recovery time set of the database.</span></span> <span data-ttu-id="daf19-114">Isso pode causar atividade adicional de E/S em determinados sistemas, o que pode contribuir para um gargalo de desempenho, se o subsistema do disco estiver operando acima ou próximo do limite de E/S.</span><span class="sxs-lookup"><span data-stu-id="daf19-114">This can cause additional I/O activity on certain systems which can contribute to a performance bottleneck if the disk subsystem is operating above or nearing the I/O threshold.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="daf19-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="daf19-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="daf19-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="daf19-116">Permissions</span></span>  
 <span data-ttu-id="daf19-117">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daf19-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="daf19-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daf19-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="daf19-119">**Para alterar o tempo de recuperação de destino**</span><span class="sxs-lookup"><span data-stu-id="daf19-119">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="daf19-120">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="daf19-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand that instance.</span></span>  
  
2.  <span data-ttu-id="daf19-121">Clique com o botão direito do mouse no banco de dados a ser alterado e clique no comando **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="daf19-121">Right-click the database you want to change, and click the **Properties** command.</span></span>  
  
3.  <span data-ttu-id="daf19-122">Na caixa de diálogo **Propriedades do Banco de Dados** , clique na página **Opções** .</span><span class="sxs-lookup"><span data-stu-id="daf19-122">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="daf19-123">No painel **Recuperação** , no campo **Tempo de Recuperação de Destino (Segundos)** , especifique o número de segundos desejado como o limite superior do tempo de recuperação deste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daf19-123">In the **Recovery** panel, in the **Target Recovery Time (Seconds)** field, specify the number of seconds that you want as the upper-bound on the recovery time for this database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="daf19-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daf19-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="daf19-125">**Para alterar o tempo de recuperação de destino**</span><span class="sxs-lookup"><span data-stu-id="daf19-125">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="daf19-126">Conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] onde o banco de dados reside.</span><span class="sxs-lookup"><span data-stu-id="daf19-126">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the database resides.</span></span>  
  
2.  <span data-ttu-id="daf19-127">Use a instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options), da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="daf19-127">Use the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)statement, as follows:</span></span>  
  
     <span data-ttu-id="daf19-128">TARGET_RECOVERY_TIME **=** _target_recovery_time_ { SECONDS | MINUTES }</span><span class="sxs-lookup"><span data-stu-id="daf19-128">TARGET_RECOVERY_TIME **=**_target_recovery_time_ { SECONDS | MINUTES }</span></span>  
  
     <span data-ttu-id="daf19-129">*target_recovery_time*</span><span class="sxs-lookup"><span data-stu-id="daf19-129">*target_recovery_time*</span></span>  
     <span data-ttu-id="daf19-130">Quando maior que 0 (o padrão), especifica o limite superior do tempo de recuperação para o banco de dados especificado no caso de uma falha.</span><span class="sxs-lookup"><span data-stu-id="daf19-130">When greater than 0 (the default), specifies the upper-bound on the recovery time for the specified database in the event of a crash.</span></span>  
  
     <span data-ttu-id="daf19-131">SECONDS</span><span class="sxs-lookup"><span data-stu-id="daf19-131">SECONDS</span></span>  
     <span data-ttu-id="daf19-132">Indica que *target_recovery_time* é expresso como o número de segundos.</span><span class="sxs-lookup"><span data-stu-id="daf19-132">Indicates that *target_recovery_time* is expressed as the number of seconds.</span></span>  
  
     <span data-ttu-id="daf19-133">MINUTES</span><span class="sxs-lookup"><span data-stu-id="daf19-133">MINUTES</span></span>  
     <span data-ttu-id="daf19-134">Indica que *target_recovery_time* é expresso como o número de minutos.</span><span class="sxs-lookup"><span data-stu-id="daf19-134">Indicates that *target_recovery_time* is expressed as the number of minutes.</span></span>  
  
     <span data-ttu-id="daf19-135">O exemplo a seguir define o tempo de recuperação de destino do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] como `60` segundos.</span><span class="sxs-lookup"><span data-stu-id="daf19-135">The following example sets the target recovery time of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to `60` seconds.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="daf19-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="daf19-136">See Also</span></span>  
 <span data-ttu-id="daf19-137">[Pontos de verificação de banco de dados &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="daf19-137">[Database Checkpoints &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span></span>  
 [<span data-ttu-id="daf19-138">Opções ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="daf19-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
