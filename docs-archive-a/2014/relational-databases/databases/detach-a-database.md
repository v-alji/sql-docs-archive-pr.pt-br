---
title: Desanexar um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.detachdatabase.f1
helpviewer_keywords:
- database detaching [SQL Server]
- detaching databases [SQL Server]
ms.assetid: f63d4107-13e4-4bfe-922d-5e4f712e472d
author: stevestein
ms.author: sstein
ms.openlocfilehash: b8acc809b881012d18f78995bb8e521337fb02ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583615"
---
# <a name="detach-a-database"></a><span data-ttu-id="c2160-102">Desanexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="c2160-102">Detach a Database</span></span>
  <span data-ttu-id="c2160-103">Este tópico descreve como desanexar um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2160-103">This topic describes how to detach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c2160-104">Os arquivos desanexados permanecem e podem ser anexados novamente com o uso de CREATE DATABASE com a opção FOR ATTACH ou FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="c2160-104">The detached files remain and can be reattached by using CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="c2160-105">Os arquivos podem ser movidos para outro servidor, onde podem ser anexados.</span><span class="sxs-lookup"><span data-stu-id="c2160-105">The files can be moved to another server and attached there.</span></span>  
  
 <span data-ttu-id="c2160-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c2160-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c2160-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c2160-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c2160-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c2160-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c2160-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="c2160-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c2160-110">**Para desanexar banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="c2160-110">**To detach a database, using:**</span></span>  
  
     [<span data-ttu-id="c2160-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c2160-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c2160-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c2160-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c2160-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c2160-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c2160-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c2160-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c2160-115">Para obter uma lista de limitações e restrições, veja [Anexar e desanexar bancos de dados &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c2160-115">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c2160-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="c2160-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c2160-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="c2160-117">Permissions</span></span>  
 <span data-ttu-id="c2160-118">Requer associação na função de banco de dados fixa db_owner.</span><span class="sxs-lookup"><span data-stu-id="c2160-118">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c2160-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c2160-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="c2160-120">Para desanexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="c2160-120">To detach a database</span></span>  
  
1.  <span data-ttu-id="c2160-121">No Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conecte-se à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c2160-121">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand the instance.</span></span>  
  
2.  <span data-ttu-id="c2160-122">Expanda **Bancos de Dados**e selecione o nome do banco de dados de usuário que você quer desanexar.</span><span class="sxs-lookup"><span data-stu-id="c2160-122">Expand **Databases**, and select the name of the user database you want to detach.</span></span>  
  
3.  <span data-ttu-id="c2160-123">Clique com o botão direito do mouse no nome do banco de dados, aponte para **Tarefas**e clique em **Desanexar**.</span><span class="sxs-lookup"><span data-stu-id="c2160-123">Right-click the database name, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="c2160-124">A caixa de diálogo **Desanexar Banco de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="c2160-124">The **Detach Database** dialog box appears.</span></span>  
  
     <span data-ttu-id="c2160-125">**Bancos de dados a serem desanexados**</span><span class="sxs-lookup"><span data-stu-id="c2160-125">**Databases to detach**</span></span>  
     <span data-ttu-id="c2160-126">Lista os bancos de dados a serem desanexados</span><span class="sxs-lookup"><span data-stu-id="c2160-126">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="c2160-127">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="c2160-127">**Database Name**</span></span>  
     <span data-ttu-id="c2160-128">Exibe o nome do banco de dados a ser desanexado.</span><span class="sxs-lookup"><span data-stu-id="c2160-128">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="c2160-129">**Cancelar Conexões**</span><span class="sxs-lookup"><span data-stu-id="c2160-129">**Drop Connections**</span></span>  
     <span data-ttu-id="c2160-130">Cancelar conexões com o banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="c2160-130">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c2160-131">Você não pode desanexar um banco de dados com conexões ativas.</span><span class="sxs-lookup"><span data-stu-id="c2160-131">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="c2160-132">**Atualização de Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="c2160-132">**Update Statistics**</span></span>  
     <span data-ttu-id="c2160-133">Por padrão, a operação desanexar retém qualquer estatística de otimização desatualizada ao desanexar o banco de dados; para atualizar as estatísticas de otimização existentes, clique nesta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="c2160-133">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="c2160-134">**Manter Catálogos de Texto Completo**</span><span class="sxs-lookup"><span data-stu-id="c2160-134">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="c2160-135">Por padrão, a operação desanexar mantém qualquer catálogo de texto completo que esteja associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c2160-135">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="c2160-136">Para removê-los, desmarque a caixa de seleção **Manter Catálogos de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="c2160-136">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="c2160-137">Essa opção é exibida apenas quando você está atualizando um banco de dados do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2160-137">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="c2160-138">**Status**</span><span class="sxs-lookup"><span data-stu-id="c2160-138">**Status**</span></span>  
     <span data-ttu-id="c2160-139">Exibe um dos estados a seguir: **Pronto** ou **Não pronto**.</span><span class="sxs-lookup"><span data-stu-id="c2160-139">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="c2160-140">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="c2160-140">**Message**</span></span>  
     <span data-ttu-id="c2160-141">A coluna **Mensagem** pode exibir informações sobre o banco de dados, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c2160-141">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="c2160-142">Quando um banco de dados estiver envolvido com replicação, o **Status** será **Não pronto** e a coluna **Mensagem** exibirá **Banco de Dados replicado**.</span><span class="sxs-lookup"><span data-stu-id="c2160-142">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="c2160-143">Quando um banco de dados tiver uma ou mais conexões ativas, o **Status** será **Não está pronto** e a coluna **Mensagem** exibirá _<número_de_conexões_ativas>_ **Conexão(ões) ativa(s)** – por exemplo: **1 Conexão ativa**.</span><span class="sxs-lookup"><span data-stu-id="c2160-143">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="c2160-144">Antes de desanexar o banco de dados, você deverá cancelar qualquer conexão ativa selecionando **Cancelar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="c2160-144">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="c2160-145">Para obter mais informações sobre a mensagem, clique o texto com hiperlink para abrir o Monitor de atividades.</span><span class="sxs-lookup"><span data-stu-id="c2160-145">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
4.  <span data-ttu-id="c2160-146">Quando você estiver pronto para desanexar o banco de dados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2160-146">When you are ready to detach the database, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2160-147">O banco de dados recém-desanexado permanecerá visível no nó **Bancos de Dados** do Pesquisador de Objetos até que a exibição seja atualizada.</span><span class="sxs-lookup"><span data-stu-id="c2160-147">The newly detached database will remain visible in the **Databases** node of Object Explorer until the view is refreshed.</span></span> <span data-ttu-id="c2160-148">Você pode atualizar a exibição a qualquer momento: clique no painel Pesquisador de Objetos e, na barra de menus, selecione **Exibir** e, depois, **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="c2160-148">You can refresh the view at any time: Click in the Object Explorer pane, and from the menu bar select **View** and then **Refresh**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c2160-149">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c2160-149">Using Transact-SQL</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="c2160-150">Para desanexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="c2160-150">To detach a database</span></span>  
  
1.  <span data-ttu-id="c2160-151">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2160-151">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c2160-152">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c2160-152">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c2160-153">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c2160-153">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c2160-154">Este exemplo desanexa o banco de dados AdventureWorks2012 com skipchecks definido como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="c2160-154">This example detaches the AdventureWorks2012 database with skipchecks set to true.</span></span>  
  
```  
EXEC sp_detach_db 'AdventureWorks2012', 'true';  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2160-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2160-155">See Also</span></span>  
 <span data-ttu-id="c2160-156">[Anexar e desanexar bancos de dados &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c2160-156">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 [<span data-ttu-id="c2160-157">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c2160-157">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
