---
title: Remover o Espelhamento de Banco de Dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- removing database mirroring [SQL Server]
ms.assetid: bbc4d7f7-3bc7-40d6-a822-af195fe7f8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19c1d0449fa1c7434aeaf9c51e3b2dc7bc6b68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681153"
---
# <a name="remove-database-mirroring-sql-server"></a><span data-ttu-id="32da5-102">Remover o espelhamento de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32da5-102">Remove Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="32da5-103">Este tópico descreve como remover o espelhamento de um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32da5-103">This topic describes how to remove database mirroring from a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="32da5-104">A qualquer momento, o proprietário do banco de dados poderá interromper manualmente uma sessão de espelhamento de banco de dados ao remover o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="32da5-104">At any time, the database owner can manually stop a database mirroring session by removing mirroring from the database.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="32da5-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="32da5-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="32da5-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="32da5-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="32da5-107">Permissões</span><span class="sxs-lookup"><span data-stu-id="32da5-107">Permissions</span></span>  
 <span data-ttu-id="32da5-108">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="32da5-108">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="32da5-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="32da5-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="32da5-110">Para remover o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="32da5-110">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="32da5-111">Durante uma sessão de espelhamento de banco de dados, faça a conexão com a instância do servidor principal e, no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="32da5-111">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="32da5-112">Expanda **Bancos de Dados**e selecione o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="32da5-112">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="32da5-113">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="32da5-113">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="32da5-114">Isso abre a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="32da5-114">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="32da5-115">No painel **Selecionar uma Página** , clique em **Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="32da5-115">In the **Select a Page** pane, click **Mirroring**.</span></span>  
  
5.  <span data-ttu-id="32da5-116">Para remover o espelhamento, clique em **Remover Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="32da5-116">To remove mirroring, click **Remove Mirroring**.</span></span> <span data-ttu-id="32da5-117">Um prompt solicita confirmação.</span><span class="sxs-lookup"><span data-stu-id="32da5-117">A prompt asks for confirmation.</span></span> <span data-ttu-id="32da5-118">Se você clicar em **Sim**, a sessão será interrompida e o espelhamento, removido do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="32da5-118">If you click **Yes**, the session is stopped and mirroring is removed from the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="32da5-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="32da5-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="32da5-120">Para remover o espelhamento de banco de dados, use **Propriedades do Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="32da5-120">To remove database mirroring, use the **Database Properties**.</span></span> <span data-ttu-id="32da5-121">Use a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="32da5-121">use the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="32da5-122">Para remover o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="32da5-122">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="32da5-123">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] de qualquer um dos parceiros de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="32da5-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] of either mirroring partner.</span></span>  
  
2.  <span data-ttu-id="32da5-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="32da5-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="32da5-125">Emita a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="32da5-125">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    ALTER DATABASE database_name SET PARTNER OFF  
    ```  
  
     <span data-ttu-id="32da5-126">em que *database_name* é o banco de dados espelhado cuja sessão você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="32da5-126">where *database_name* is the mirrored database whose session you want to remove.</span></span>  
  
     <span data-ttu-id="32da5-127">O exemplo a seguir remove o espelhamento de banco de dados do banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32da5-127">The following example removes database mirroring from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER OFF;  
    ```  
  
##  <a name="follow-up-removing-database-mirroring"></a><a name="FollowUp"></a> <span data-ttu-id="32da5-128">Acompanhamento: Removendo o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="32da5-128">Follow Up: Removing Database Mirroring</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32da5-129">Para obter informações sobre o impacto da remoção de espelhamentos, veja [Removendo o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="32da5-129">For information about the impact of removing mirroring, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="32da5-130">**Se você pretender reiniciar o espelhamento no banco de dados**</span><span class="sxs-lookup"><span data-stu-id="32da5-130">**If you intend to restart mirroring on the database**</span></span>  
  
     <span data-ttu-id="32da5-131">Todos os backups de logs efetuados no banco de dados principal depois que o espelhamento for removido deverão ser aplicados ao banco de dados espelho antes que o espelhamento de banco de dados possa ser reinicializado.</span><span class="sxs-lookup"><span data-stu-id="32da5-131">Any log backups taken on the principal database after mirroring was removed must all be applied to the mirror database before you can restart mirroring.</span></span>  
  
-   <span data-ttu-id="32da5-132">**Se você não pretender reiniciar o espelhamento**</span><span class="sxs-lookup"><span data-stu-id="32da5-132">**If you do not intent to restart mirroring**</span></span>  
  
     <span data-ttu-id="32da5-133">Opcionalmente, você pode recuperar o banco de dados espelho anterior.</span><span class="sxs-lookup"><span data-stu-id="32da5-133">Optionally, you can recover the former mirror database.</span></span> <span data-ttu-id="32da5-134">Na instância de servidor que era o servidor espelho, use a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="32da5-134">On the server instance that was the mirror server, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    RESTORE DATABASE database_name WITH RECOVERY;  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="32da5-135">Se você recuperar este banco de dados, dois bancos de dados divergentes com o mesmo nome estarão online.</span><span class="sxs-lookup"><span data-stu-id="32da5-135">If you recover this database, two divergent databases with the same name are online.</span></span> <span data-ttu-id="32da5-136">Portanto, você precisa garantir que os clientes possam acessar somente um deles – geralmente o banco de dados principal mais recente.</span><span class="sxs-lookup"><span data-stu-id="32da5-136">Therefore, you need to ensure that clients can access only one of them-typically the most recent principal database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="32da5-137">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="32da5-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="32da5-138">Pausar ou retomar uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="32da5-138">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="32da5-139">Remover a testemunha de uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="32da5-139">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="32da5-140">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="32da5-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="32da5-141">Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32da5-141">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="32da5-142">Exemplo: Configurar o espelhamento de banco de dados usando certificados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32da5-142">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="32da5-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32da5-143">See Also</span></span>  
 <span data-ttu-id="32da5-144">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="32da5-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="32da5-145">[Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="32da5-145">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="32da5-146">Grupos de Disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32da5-146">AlwaysOn Availability Groups (SQL Server)</span></span>](../availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
