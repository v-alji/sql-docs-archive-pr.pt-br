---
title: Executar operações de índice online | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index online operations [SQL Server]
- online index operations
- ONLINE option
ms.assetid: 1e43537c-bf67-4db3-9908-3cb45c6fdaa1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d09bd99a0eaec5fdb433bd8c33351d7622957a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583036"
---
# <a name="perform-index-operations-online"></a><span data-ttu-id="93e93-102">Executar operações de índice online</span><span class="sxs-lookup"><span data-stu-id="93e93-102">Perform Index Operations Online</span></span>
  <span data-ttu-id="93e93-103">Este tópico descreve como criar, recriar ou descartar índices online no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93e93-103">This topic describes how to create, rebuild, or drop indexes online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="93e93-104">A opção ONLINE permite acesso simultâneo de usuários aos dados da tabela subjacente ou de índice cluster e qualquer índice não cluster associado durante essas operações de índice.</span><span class="sxs-lookup"><span data-stu-id="93e93-104">The ONLINE option allows concurrent user access to the underlying table or clustered index data and any associated nonclustered indexes during these index operations.</span></span> <span data-ttu-id="93e93-105">Por exemplo, enquanto um índice cluster estiver sendo recriado por um usuário, esse usuário e os outros poderão continuar atualizando e consultando os dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="93e93-105">For example, while a clustered index is being rebuilt by one user, that user and others can continue to update and query the underlying data.</span></span> <span data-ttu-id="93e93-106">Quando você executa operações de DDL (linguagem de definição de dados) offline, como a compilação ou recompilação de um índice clusterizado, essas operações mantêm bloqueios exclusivos nos dados subjacentes e índices associados.</span><span class="sxs-lookup"><span data-stu-id="93e93-106">When you perform data definition language (DDL) operations offline, such as building or rebuilding a clustered index; these operations hold exclusive locks on the underlying data and associated indexes.</span></span> <span data-ttu-id="93e93-107">Isso evita modificações e consultas aos dados subjacentes até que a operação de índice esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="93e93-107">This prevents modifications and queries to the underlying data until the index operation is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93e93-108">As operações de índice online não estão disponíveis em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93e93-108">Online index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="93e93-109">Para obter mais informações, consulte [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="93e93-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="93e93-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="93e93-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="93e93-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="93e93-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="93e93-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="93e93-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="93e93-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="93e93-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="93e93-114">**Para recriar um índice online, usando:**</span><span class="sxs-lookup"><span data-stu-id="93e93-114">**To rebuild an index online, using:**</span></span>  
  
     [<span data-ttu-id="93e93-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93e93-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="93e93-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93e93-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="93e93-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="93e93-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="93e93-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="93e93-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="93e93-119">Nós recomendamos a execução de operações de índice online em ambientes empresariais que funcionam 24 horas por dia, sete dias por semana, nos quais a necessidade para atividade de usuário simultânea durante as operações de índice é vital.</span><span class="sxs-lookup"><span data-stu-id="93e93-119">We recommend performing online index operations for business environments that operate 24 hours a day, seven days a week, in which the need for concurrent user activity during index operations is vital.</span></span>  
  
-   <span data-ttu-id="93e93-120">A opção ONLINE está disponível nas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir.</span><span class="sxs-lookup"><span data-stu-id="93e93-120">The ONLINE option is available in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
    -   [<span data-ttu-id="93e93-121">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="93e93-121">CREATE INDEX</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
    -   [<span data-ttu-id="93e93-122">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="93e93-122">ALTER INDEX</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    -   [<span data-ttu-id="93e93-123">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="93e93-123">DROP INDEX</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
    -   <span data-ttu-id="93e93-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (para adicionar ou remover restrições UNIQUE ou PRIMARY KEY com a opção de índice CLUSTERED)</span><span class="sxs-lookup"><span data-stu-id="93e93-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (To add or drop UNIQUE or PRIMARY KEY constraints with CLUSTERED index option)</span></span>  
  
-   <span data-ttu-id="93e93-125">Por obter mais informações sobre limitação e restrições sobre como criar, recriar ou descartar índices online, consulte [Diretrizes para operações de índice online](guidelines-for-online-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="93e93-125">For more limitations and restrictions concerning creating, rebuilding, or dropping indexes online, see [Guidelines for Online Index Operations](guidelines-for-online-index-operations.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="93e93-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="93e93-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="93e93-127">Permissões</span><span class="sxs-lookup"><span data-stu-id="93e93-127">Permissions</span></span>  
 <span data-ttu-id="93e93-128">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="93e93-128">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93e93-129">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93e93-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rebuild-an-index-online"></a><span data-ttu-id="93e93-130">Para recriar um índice online</span><span class="sxs-lookup"><span data-stu-id="93e93-130">To rebuild an index online</span></span>  
  
1.  <span data-ttu-id="93e93-131">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja recriar um índice online.</span><span class="sxs-lookup"><span data-stu-id="93e93-131">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rebuild an index online.</span></span>  
  
2.  <span data-ttu-id="93e93-132">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="93e93-132">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="93e93-133">Clique no sinal de adição para expandir a tabela na qual você deseja recriar um índice online.</span><span class="sxs-lookup"><span data-stu-id="93e93-133">Click the plus sign to expand the table on which you want to rebuild an index online.</span></span>  
  
4.  <span data-ttu-id="93e93-134">Expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="93e93-134">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="93e93-135">Clique com o botão direito do mouse no índice que você quer recriar online e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="93e93-135">Right-click the index that you want to rebuild online and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="93e93-136">Em **Selecione uma página**, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="93e93-136">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="93e93-137">Selecione **Permitir processamento DML online**e selecione **Verdadeiro** na lista.</span><span class="sxs-lookup"><span data-stu-id="93e93-137">Select **Allow online DML processing**, and then select **True** from the list.</span></span>  
  
8.  <span data-ttu-id="93e93-138">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="93e93-138">Click **OK**.</span></span>  
  
9. <span data-ttu-id="93e93-139">Clique com o botão direito do mouse no índice que você quer recriar online e selecione **Recompilar**.</span><span class="sxs-lookup"><span data-stu-id="93e93-139">Right-click the index that you want to rebuild online and select **Rebuild**.</span></span>  
  
10. <span data-ttu-id="93e93-140">Na caixa de diálogo **Recriar Índices** , verifique se o índice correto está na grade **Índices a serem recriados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="93e93-140">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="93e93-141">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93e93-141">Using Transact-SQL</span></span>  
  
#### <a name="to-create-rebuild-or-drop-an-index-online"></a><span data-ttu-id="93e93-142">Para criar, recriar ou descartar um índice online</span><span class="sxs-lookup"><span data-stu-id="93e93-142">To create, rebuild, or drop an index online</span></span>  
  
1.  <span data-ttu-id="93e93-143">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93e93-143">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="93e93-144">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="93e93-144">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="93e93-145">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="93e93-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="93e93-146">O exemplo reconstrói um online existente</span><span class="sxs-lookup"><span data-stu-id="93e93-146">The example rebuilds an existing online</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee  
    REBUILD WITH (ONLINE = ON);  
    GO  
    ```  
  
     <span data-ttu-id="93e93-147">O exemplo a seguir exclui um índice clusterizado online e move a tabela resultante (heap) para o grupo de arquivos `NewGroup` usando a cláusula `MOVE TO` .</span><span class="sxs-lookup"><span data-stu-id="93e93-147">The following example deletes a clustered index online and moves the resulting table (heap) to the filegroup `NewGroup` by using the `MOVE TO` clause.</span></span> <span data-ttu-id="93e93-148">As exibições do catálogo `sys.indexes`, `sys.tables`e `sys.filegroups` são consultadas para verificar o posicionamento do índice e da tabela nos grupos de arquivos antes e depois da movimentação.</span><span class="sxs-lookup"><span data-stu-id="93e93-148">The `sys.indexes`, `sys.tables`, and `sys.filegroups` catalog views are queried to verify the index and table placement in the filegroups before and after the move.</span></span>  
  
     [!code-sql[IndexDDL#DropIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/dropindex.sql#dropindex4)]  
  
 <span data-ttu-id="93e93-149">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="93e93-149">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
