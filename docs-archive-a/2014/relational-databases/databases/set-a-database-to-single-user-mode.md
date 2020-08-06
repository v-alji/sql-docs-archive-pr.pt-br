---
title: Definir um banco de dados como modo de usuário único | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- single-user mode [SQL Server], database option
ms.assetid: fb5254eb-b635-4b39-8361-136fd36f2b1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 16281b5fa7d4f6698bb6c498915bfa84779b3e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678783"
---
# <a name="set-a-database-to-single-user-mode"></a><span data-ttu-id="c8831-102">Definir um banco de dados como modo de usuário único</span><span class="sxs-lookup"><span data-stu-id="c8831-102">Set a Database to Single-user Mode</span></span>
  <span data-ttu-id="c8831-103">Este tópico descreve como configurar um banco de dados definido pelo usuário no modo de usuário único no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8831-103">This topic describes how to set a user-defined database to single-user mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c8831-104">O modo de usuário único especifica que apenas um usuário pode acessar o banco de dados por vez e, normalmente é usado para ações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="c8831-104">Single-user mode specifies that only one user at a time can access the database and is generally used for maintenance actions.</span></span>  
  
 <span data-ttu-id="c8831-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c8831-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c8831-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c8831-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c8831-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c8831-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c8831-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c8831-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="c8831-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="c8831-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c8831-110">**Para definir um banco de dados como modo de usuário único, usando:**</span><span class="sxs-lookup"><span data-stu-id="c8831-110">**To set a database to single-user mode, using:**</span></span>  
  
     [<span data-ttu-id="c8831-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8831-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c8831-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8831-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c8831-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c8831-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c8831-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c8831-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c8831-115">Se outros usuários estiverem conectados ao banco de dados no momento em que você configurar o banco de dados como modo de usuário único, as conexões deles ao banco de dados serão fechadas sem aviso.</span><span class="sxs-lookup"><span data-stu-id="c8831-115">If other users are connected to the database at the time that you set the database to single-user mode, their connections to the database will be closed without warning.</span></span>  
  
-   <span data-ttu-id="c8831-116">O banco de dados permanece em modo de usuário único mesmo se o usuário que definiu a opção fizer logoff.</span><span class="sxs-lookup"><span data-stu-id="c8831-116">The database remains in single-user mode even if the user that set the option logs off.</span></span> <span data-ttu-id="c8831-117">Nesse momento, um usuário diferente, mas somente um, poderá se conectar ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8831-117">At that point, a different user, but only one, can connect to the database.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c8831-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c8831-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="c8831-119">Antes de definir o banco de dados como SINGLE_USER, verifique se a opção AUTO_UPDATE_STATISTICS_ASYNC está definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="c8831-119">Before you set the database to SINGLE_USER, verify that the AUTO_UPDATE_STATISTICS_ASYNC option is set to OFF.</span></span> <span data-ttu-id="c8831-120">Quando esta opção está definida como ON, o thread em segundo plano usado para a atualização de estatísticas estabelece uma conexão com o banco de dados e não será possível acessar o banco de dados em modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="c8831-120">When this option is set to ON, the background thread that is used to update statistics takes a connection against the database, and you will be unable to access the database in single-user mode.</span></span> <span data-ttu-id="c8831-121">Para obter mais informações, veja [Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="c8831-121">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c8831-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="c8831-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c8831-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="c8831-123">Permissions</span></span>  
 <span data-ttu-id="c8831-124">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8831-124">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c8831-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8831-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="c8831-126">Para definir um banco de dados como modo de usuário único</span><span class="sxs-lookup"><span data-stu-id="c8831-126">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="c8831-127">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c8831-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c8831-128">Clique com o botão direito do mouse no banco de dados a ser alterado e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c8831-128">Right-click the database to change, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c8831-129">Na caixa de diálogo **Propriedades do Banco de Dados** , clique na página **Opções** .</span><span class="sxs-lookup"><span data-stu-id="c8831-129">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="c8831-130">Da opção **Restringir o Acesso** , selecione **Simples**.</span><span class="sxs-lookup"><span data-stu-id="c8831-130">From the **Restrict Access** option, select **Single**.</span></span>  
  
5.  <span data-ttu-id="c8831-131">Se outros usuários estiverem conectados ao banco de dados, uma mensagem **Conexões Abertas** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c8831-131">If other users are connected to the database, an **Open Connections** message will appear.</span></span> <span data-ttu-id="c8831-132">Para alterar a propriedade e fechar todas as outras conexões, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c8831-132">To change the property and close all other connections, click **Yes**.</span></span>  
  
 <span data-ttu-id="c8831-133">Também é possível definir o banco de dados como acesso múltiplo ou restrito usando esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="c8831-133">You can also set the database to Multiple or Restricted access by using this procedure.</span></span> <span data-ttu-id="c8831-134">Para obter mais informações sobre as opções de Restringir o Acesso, veja [Propriedades de banco de dados &#40;Página Opções&#41;](database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="c8831-134">For more information about the Restrict Access options, see [Database Properties &#40;Options Page&#41;](database-properties-options-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c8831-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8831-135">Using Transact-SQL</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="c8831-136">Para definir um banco de dados como modo de usuário único</span><span class="sxs-lookup"><span data-stu-id="c8831-136">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="c8831-137">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8831-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8831-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c8831-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8831-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c8831-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c8831-140">Este exemplo define o banco de dados como o modo `SINGLE_USER` para obter acesso exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c8831-140">This example sets the database to `SINGLE_USER` mode to obtain exclusive access.</span></span> <span data-ttu-id="c8831-141">Em seguida, o exemplo define o estado do banco de dados [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] como `READ_ONLY` e retorna o acesso ao banco de dados para todos os usuários. A opção de término `WITH ROLLBACK IMMEDIATE` é especificada na primeira instrução `ALTER DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="c8831-141">The example then sets the state of the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to `READ_ONLY` and returns access to the database to all users.The termination option `WITH ROLLBACK IMMEDIATE` is specified in the first `ALTER DATABASE` statement.</span></span> <span data-ttu-id="c8831-142">Isso levará todas as transações incompletas a serem revertidas e qualquer outra conexão com o banco de dados [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] a ser desconectada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c8831-142">This will cause all incomplete transactions to be rolled back and any other connections to the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to be immediately disconnected.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase8](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase8)]  
  
## <a name="see-also"></a><span data-ttu-id="c8831-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8831-143">See Also</span></span>  
 [<span data-ttu-id="c8831-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8831-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
