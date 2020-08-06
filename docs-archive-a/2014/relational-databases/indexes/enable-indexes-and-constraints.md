---
title: Habilitar índices e restrições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], enabling
- nonclustered indexes [SQL Server], enabling a disabled index
- index enabling [SQL Server]
- disabled indexes [SQL Server], how to enable
- constraints [SQL Server], enabling
- clustered indexes, enabling disabled indexes
ms.assetid: c55c8865-322e-4ab0-ba04-ea1f56735353
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4e79689b80a40d00958fa557fe51df2adf9c14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583052"
---
# <a name="enable-indexes-and-constraints"></a><span data-ttu-id="2525d-102">Habilitar índices e restrições</span><span class="sxs-lookup"><span data-stu-id="2525d-102">Enable Indexes and Constraints</span></span>
  <span data-ttu-id="2525d-103">Este tópico descreve como habilitar um índice desabilitado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2525d-103">This topic describes how to enable a disabled index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2525d-104">Depois que um índice for desabilitado, ele permanecerá em estado desabilitado até que seja recriado ou descartado</span><span class="sxs-lookup"><span data-stu-id="2525d-104">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped</span></span>  
  
 <span data-ttu-id="2525d-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2525d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2525d-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2525d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2525d-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="2525d-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2525d-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="2525d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2525d-109">**Para habilitar um índice desabilitado, usando:**</span><span class="sxs-lookup"><span data-stu-id="2525d-109">**To enable a disabled index, using:**</span></span>  
  
     [<span data-ttu-id="2525d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2525d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2525d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2525d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2525d-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2525d-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2525d-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="2525d-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2525d-114">Depois da reconstrução do índice, qualquer restrição que tiver sido desabilitada devido à desabilitação do índice deverá ser habilitada manualmente.</span><span class="sxs-lookup"><span data-stu-id="2525d-114">After rebuilding the index, any constraints that were disabled because of disabling the index must be manually enabled.</span></span> <span data-ttu-id="2525d-115">As restrições PRIMARY KEY e UNIQUE são habilitadas reconstruindo o índice associado.</span><span class="sxs-lookup"><span data-stu-id="2525d-115">PRIMARY KEY and UNIQUE constraints are enabled by rebuilding the associated index.</span></span> <span data-ttu-id="2525d-116">Esse índice deve ser reconstruído (habilitado) antes de você poder habilitar restrições FOREIGN KEY que fazem referência à restrição PRIMARY KEY ou UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="2525d-116">This index must be rebuilt (enabled) before you can enable FOREIGN KEY constraints that reference the PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="2525d-117">Restrições FOREIGN KEY são habilitadas usando a instrução ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="2525d-117">FOREIGN KEY constraints are enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="2525d-118">A recriação de um índice clusterizado desabilitado não pode ser efetuada quando a opção ONLINE está definida como ON.</span><span class="sxs-lookup"><span data-stu-id="2525d-118">Rebuilding a disabled clustered index cannot be performed when the ONLINE option is set to ON.</span></span>  
  
-   <span data-ttu-id="2525d-119">Quando o índice clusterizado é habilitado ou desabilitado e o índice não clusterizado é desabilitado, a ação do índice clusterizado tem os seguintes resultados no índice não clusterizado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2525d-119">When the clustered index is disabled or enabled and the nonclustered index is disabled, the clustered index action has the following results on the disabled nonclustered index.</span></span>  
  
    |<span data-ttu-id="2525d-120">Ação de índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="2525d-120">Clustered Index Action</span></span>|<span data-ttu-id="2525d-121">Índice não clusterizado desabilitado...</span><span class="sxs-lookup"><span data-stu-id="2525d-121">Disabled Nonclustered Index ...</span></span>|  
    |----------------------------|-----------------------------------|  
    |<span data-ttu-id="2525d-122">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="2525d-122">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="2525d-123">Permanece desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2525d-123">Remains disabled.</span></span>|  
    |<span data-ttu-id="2525d-124">ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="2525d-124">ALTER INDEX ALL REBUILD.</span></span>|<span data-ttu-id="2525d-125">É reconstruído e habilitado.</span><span class="sxs-lookup"><span data-stu-id="2525d-125">Is rebuilt and enabled.</span></span>|  
    |<span data-ttu-id="2525d-126">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="2525d-126">DROP INDEX.</span></span>|<span data-ttu-id="2525d-127">Permanece desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2525d-127">Remains disabled.</span></span>|  
    |<span data-ttu-id="2525d-128">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="2525d-128">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="2525d-129">Permanece desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2525d-129">Remains disabled.</span></span>|  
  
     <span data-ttu-id="2525d-130">A criação de um novo índice clusterizado se comporta da mesma forma que ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="2525d-130">Creating a new clustered index, behaves the same as ALTER INDEX ALL REBUILD.</span></span>  
  
-   <span data-ttu-id="2525d-131">Ações permitidas em índices não clusterizados associados a um índice clusterizado dependem do estado, se desabilitado ou habilitado, de ambos os tipos de índice.</span><span class="sxs-lookup"><span data-stu-id="2525d-131">Allowed actions on nonclustered indexes associated with a clustered index depend on the state, whether disabled or enabled, of both index types.</span></span> <span data-ttu-id="2525d-132">A tabela a seguir resume as ações permitidas em índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="2525d-132">The following table summarizes the allowed actions on nonclustered indexes.</span></span>  
  
    |<span data-ttu-id="2525d-133">Ação de índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="2525d-133">Nonclustered Index Action</span></span>|<span data-ttu-id="2525d-134">Quando os índices clusterizados e não clusterizados estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="2525d-134">When both the clustered and nonclustered indexes are disabled.</span></span>|<span data-ttu-id="2525d-135">Quando o índice clusterizado está habilitado e o índice não clusterizado está em um dos estados.</span><span class="sxs-lookup"><span data-stu-id="2525d-135">When the clustered index is enabled and the nonclustered index is in either state.</span></span>|  
    |-------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="2525d-136">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="2525d-136">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="2525d-137">A ação falha.</span><span class="sxs-lookup"><span data-stu-id="2525d-137">The action fails.</span></span>|<span data-ttu-id="2525d-138">A ação tem êxito.</span><span class="sxs-lookup"><span data-stu-id="2525d-138">The action succeeds.</span></span>|  
    |<span data-ttu-id="2525d-139">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="2525d-139">DROP INDEX.</span></span>|<span data-ttu-id="2525d-140">A ação tem êxito.</span><span class="sxs-lookup"><span data-stu-id="2525d-140">The action succeeds.</span></span>|<span data-ttu-id="2525d-141">A ação tem êxito.</span><span class="sxs-lookup"><span data-stu-id="2525d-141">The action succeeds.</span></span>|  
    |<span data-ttu-id="2525d-142">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="2525d-142">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="2525d-143">A ação falha.</span><span class="sxs-lookup"><span data-stu-id="2525d-143">The action fails.</span></span>|<span data-ttu-id="2525d-144">A ação tem êxito.</span><span class="sxs-lookup"><span data-stu-id="2525d-144">The action succeeds.</span></span>|  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2525d-145">Segurança</span><span class="sxs-lookup"><span data-stu-id="2525d-145">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2525d-146">Permissões</span><span class="sxs-lookup"><span data-stu-id="2525d-146">Permissions</span></span>  
 <span data-ttu-id="2525d-147">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="2525d-147">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="2525d-148">Se estiver usando o DBCC DBREINDEX, o usuário deverá ter a tabela ou ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="2525d-148">If using DBCC DBREINDEX, eser must either own the table or be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2525d-149">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2525d-149">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-a-disabled-index"></a><span data-ttu-id="2525d-150">Para habilitar um índice desabilitado</span><span class="sxs-lookup"><span data-stu-id="2525d-150">To enable a disabled index</span></span>  
  
1.  <span data-ttu-id="2525d-151">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja habilitar um índice.</span><span class="sxs-lookup"><span data-stu-id="2525d-151">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable an index.</span></span>  
  
2.  <span data-ttu-id="2525d-152">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="2525d-152">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2525d-153">Clique no sinal de adição para expandir a tabela na qual você deseja habilitar um índice.</span><span class="sxs-lookup"><span data-stu-id="2525d-153">Click the plus sign to expand the table on which you want to enable an index.</span></span>  
  
4.  <span data-ttu-id="2525d-154">Clique no sinal de adição para expandir a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="2525d-154">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="2525d-155">Clique com o botão direito do mouse no índice a ser habilitado e selecione **Recriar**.</span><span class="sxs-lookup"><span data-stu-id="2525d-155">Right-click the index you want to enable and select **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="2525d-156">Na caixa de diálogo **Recriar Índices** , verifique se o índice correto está na grade **Índices a serem recriados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2525d-156">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
#### <a name="to-enable-all-indexes-on-a-table"></a><span data-ttu-id="2525d-157">Para habilitar todos os índices de uma tabela</span><span class="sxs-lookup"><span data-stu-id="2525d-157">To enable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="2525d-158">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja habilitar os índices.</span><span class="sxs-lookup"><span data-stu-id="2525d-158">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable the indexes.</span></span>  
  
2.  <span data-ttu-id="2525d-159">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="2525d-159">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2525d-160">Clique no sinal de adição para expandir a tabela na qual você deseja habilitar os índices.</span><span class="sxs-lookup"><span data-stu-id="2525d-160">Click the plus sign to expand the table on which you want to enable the indexes.</span></span>  
  
4.  <span data-ttu-id="2525d-161">Clique com o botão direito do mouse na pasta **Índices** e selecione **Recriar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="2525d-161">Right-click the **Indexes** folder and select **Rebuild All**.</span></span>  
  
5.  <span data-ttu-id="2525d-162">Na caixa de diálogo **Recriar Índices** , verifique se os índices corretos estão na grade **Índices a serem recriados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2525d-162">In the **Rebuild Indexes** dialog box, verify that the correct indexes are in the **Indexes to rebuild** grid and click **OK**.</span></span> <span data-ttu-id="2525d-163">Para remover um índice da grade **Índices a serem recriados** , selecione o índice e pressione a tecla Delete.</span><span class="sxs-lookup"><span data-stu-id="2525d-163">To remove an index from the **Indexes to rebuild** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="2525d-164">As seguintes informações estão disponíveis na caixa de diálogo **Recriar Índices** :</span><span class="sxs-lookup"><span data-stu-id="2525d-164">The following information is available in the **Rebuild Indexes** dialog box:</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2525d-165">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2525d-165">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-a-disabled-index-using-alter-index"></a><span data-ttu-id="2525d-166">Para habilitar um índice desabilitado usando ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="2525d-166">To enable a disabled index using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="2525d-167">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2525d-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2525d-168">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2525d-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2525d-169">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2525d-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD;   
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-create-index"></a><span data-ttu-id="2525d-170">Para habilitar um índice desabilitado usando CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="2525d-170">To enable a disabled index using CREATE INDEX</span></span>  
  
1.  <span data-ttu-id="2525d-171">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2525d-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2525d-172">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2525d-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2525d-173">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2525d-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- re-creates the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    -- using the OrganizationLevel and OrganizationNode columns  
    -- and then deletes the existing IX_Employee_OrganizationLevel_OrganizationNode index  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)  
    WITH (DROP_EXISTING = ON);  
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-dbcc-dbreindex"></a><span data-ttu-id="2525d-174">Para habilitar um índice desabilitado usando DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="2525d-174">To enable a disabled index using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="2525d-175">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2525d-175">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2525d-176">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2525d-176">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2525d-177">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2525d-177">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", IX_Employee_OrganizationLevel_OrganizationNode);  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-alter-index"></a><span data-ttu-id="2525d-178">Para habilitar todos os índices em uma tabela usando ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="2525d-178">To enable all indexes on a table using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="2525d-179">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2525d-179">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2525d-180">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2525d-180">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2525d-181">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2525d-181">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    ALTER INDEX ALL ON HumanResources.Employee  
    REBUILD;  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-dbcc-dbreindex"></a><span data-ttu-id="2525d-182">Para habilitar todos os índices em uma tabela usando DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="2525d-182">To enable all indexes on a table using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="2525d-183">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2525d-183">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2525d-184">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2525d-184">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2525d-185">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2525d-185">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", " ");  
    GO  
    ```  
  
 <span data-ttu-id="2525d-186">Para obter mais informações, veja [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) e [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2525d-186">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), and [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span></span>  
  
  
