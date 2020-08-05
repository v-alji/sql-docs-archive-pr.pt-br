---
title: Modificar exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- views [SQL Server], modifying
- modifying views
- renaming views
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10cf9ecc860d8f9b46a06ac679b0f1a8241000bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573862"
---
# <a name="modify-views"></a><span data-ttu-id="8a515-102">Modificar exibições</span><span class="sxs-lookup"><span data-stu-id="8a515-102">Modify Views</span></span>
  <span data-ttu-id="8a515-103">Depois de definir uma exibição, é possível alterar sua definição [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sem descartar e recriar a exibição usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a515-103">After you define a view, you can modify its definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] without dropping and re-creating the view by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8a515-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8a515-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8a515-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8a515-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8a515-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8a515-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8a515-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="8a515-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8a515-108">**Para modificar uma exibição usando:**</span><span class="sxs-lookup"><span data-stu-id="8a515-108">**To modify a view, using:**</span></span>  
  
     [<span data-ttu-id="8a515-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a515-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8a515-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a515-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8a515-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8a515-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8a515-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8a515-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8a515-113">A modificação de uma exibição não afeta qualquer objeto dependente, como os procedimentos armazenados ou gatilhos; a menos que, a definição da exibição mude de tal maneira que o objeto dependente não seja mais válido.</span><span class="sxs-lookup"><span data-stu-id="8a515-113">Modifying a view does not affect any dependent objects, such as stored procedures or triggers, unless the definition of the view changes in such a way that the dependent object is no longer valid.</span></span>  
  
-   <span data-ttu-id="8a515-114">Se uma exibição usada atualmente for modificada com ALTER VIEW, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] obterá um bloqueio de esquema exclusivo na exibição.</span><span class="sxs-lookup"><span data-stu-id="8a515-114">If a view currently used is modified by using ALTER VIEW, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes an exclusive schema lock on the view.</span></span> <span data-ttu-id="8a515-115">Quando o bloqueio for concedido e não houver usuários ativos da exibição, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] excluirá todas as cópias da exibição do cache de procedimento.</span><span class="sxs-lookup"><span data-stu-id="8a515-115">When the lock is granted, and there are no active users of the view, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] deletes all copies of the view from the procedure cache.</span></span> <span data-ttu-id="8a515-116">Os planos existentes que façam referência à exibição permanecerão no cache, mas serão recompilados quando invocados.</span><span class="sxs-lookup"><span data-stu-id="8a515-116">Existing plans referencing the view remain in the cache but are recompiled when invoked.</span></span>  
  
-   <span data-ttu-id="8a515-117">ALTER VIEW pode ser aplicado a exibições indexadas; entretanto, ALTER VIEW descarta incondicionalmente todos os índices da exibição.</span><span class="sxs-lookup"><span data-stu-id="8a515-117">ALTER VIEW can be applied to indexed views; however, ALTER VIEW unconditionally drops all indexes on the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8a515-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="8a515-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8a515-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="8a515-119">Permissions</span></span>  
 <span data-ttu-id="8a515-120">Para executar ALTER VIEW, é necessária, no mínimo, permissão ALTER em OBJECT.</span><span class="sxs-lookup"><span data-stu-id="8a515-120">To execute ALTER VIEW, at a minimum, ALTER permission on OBJECT is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8a515-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a515-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="8a515-122">Para modificar uma exibição</span><span class="sxs-lookup"><span data-stu-id="8a515-122">To modify a view</span></span>  
  
1.  <span data-ttu-id="8a515-123">No **Pesquisador de Objetos**, clique no sinal de adição ao lado do banco de dados onde sua exibição está localizada e clique no sinal de adição ao lado da pasta **Exibições** .</span><span class="sxs-lookup"><span data-stu-id="8a515-123">In **Object Explorer**, click the plus sign next to the database where your view is located and then click the plus sign next to the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="8a515-124">Clique com o botão direito do mouse na exibição a ser modificada e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="8a515-124">Right-click on the view you wish to modify and select **Design**.</span></span>  
  
3.  <span data-ttu-id="8a515-125">No painel de diagrama do designer de consulta, modifique a exibição de uma ou mais das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="8a515-125">In the diagram pane of the query designer, make changes to the view in one or more of the following ways:</span></span>  
  
    1.  <span data-ttu-id="8a515-126">Marque ou desmarque as caixas de seleção de qualquer elemento que você deseja adicionar ou remover.</span><span class="sxs-lookup"><span data-stu-id="8a515-126">Select or clear the check boxes of any elements you wish to add or remove.</span></span>  
  
    2.  <span data-ttu-id="8a515-127">Clique com o botão direito do mouse no painel de diagrama, selecione **Adicionar Tabela...** e selecione as colunas adicionais que deseja adicionar à exibição na caixa de diálogo **Adicionar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="8a515-127">Right-click within the diagram pane, select **Add Table...**, and then select the additional columns you want to add to the view from the **Add Table** dialog box.</span></span>  
  
    3.  <span data-ttu-id="8a515-128">Clique com o botão direito do mouse na barra de título da tabela que deseja remover e selecione **Remove**.</span><span class="sxs-lookup"><span data-stu-id="8a515-128">Right-click the title bar of the table you wish to remove and select **Remove**.</span></span>  
  
4.  <span data-ttu-id="8a515-129">No menu **Arquivo** , clique em **Salvar**_view name_.</span><span class="sxs-lookup"><span data-stu-id="8a515-129">On the **File** menu, click **Save**_view name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8a515-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a515-130">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="8a515-131">Para modificar uma exibição</span><span class="sxs-lookup"><span data-stu-id="8a515-131">To modify a view</span></span>  
  
1.  <span data-ttu-id="8a515-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a515-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8a515-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8a515-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8a515-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8a515-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8a515-135">O exemplo cria uma exibição primeiro e depois a modifica usando ALTER VIEW.</span><span class="sxs-lookup"><span data-stu-id="8a515-135">The example first creates a view and then modifies the view by using ALTER VIEW.</span></span> <span data-ttu-id="8a515-136">Uma cláusula WHERE é adicionada à definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="8a515-136">A WHERE clause is added to the view definition.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 <span data-ttu-id="8a515-137">Para obter mais informações, consulte [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a515-137">For more information, see [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span></span>  
  
  
