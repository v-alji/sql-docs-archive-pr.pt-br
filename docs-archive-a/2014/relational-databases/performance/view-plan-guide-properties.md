---
title: Exibir propriedades de guia de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.planguideprop.general.f1
helpviewer_keywords:
- plan guides [SQL Server], view plan guide properties
- viewing plan guide properties
ms.assetid: 8c0d2f39-59c1-4168-a649-65473f6a771b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af29c66690a43f89106c1f77aca8c3a02eff2ba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680391"
---
# <a name="view-plan-guide-properties"></a><span data-ttu-id="c18e4-102">Exibir propriedades de guia de plano</span><span class="sxs-lookup"><span data-stu-id="c18e4-102">View Plan Guide Properties</span></span>
  <span data-ttu-id="c18e4-103">Você pode exibir as propriedades dos guias de plano no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c18e4-103">You can view the properties of plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="c18e4-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c18e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c18e4-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c18e4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c18e4-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="c18e4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c18e4-107">**Para exibir as propriedades dos guias de plano usando:**</span><span class="sxs-lookup"><span data-stu-id="c18e4-107">**To view the properties of plan guides, using:**</span></span>  
  
     [<span data-ttu-id="c18e4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c18e4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c18e4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c18e4-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c18e4-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c18e4-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c18e4-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="c18e4-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c18e4-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="c18e4-112">Permissions</span></span>  
 <span data-ttu-id="c18e4-113">A visibilidade dos metadados em exibições do catálogo está limitada aos protegíveis que pertencem a um usuário ou para os quais o usuário recebeu permissão.</span><span class="sxs-lookup"><span data-stu-id="c18e4-113">The visibility of the metadata in catalog views is limited to securables that either a user owns or on which the user has been granted some permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c18e4-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c18e4-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="c18e4-115">Para visualizar as propriedades de um guia de plano</span><span class="sxs-lookup"><span data-stu-id="c18e4-115">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="c18e4-116">Clique no sinal de adição para expandir o banco de dados no qual você deseja exibir as propriedades de um guia de plano e clique no sinal de adição para expandir a pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="c18e4-116">Click the plus sign to expand the database in which you want to view the properties of a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="c18e4-117">Clique no sinal de adição para expandir a pasta **Guias de Plano** .</span><span class="sxs-lookup"><span data-stu-id="c18e4-117">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="c18e4-118">Clique com o botão direito do mouse no guia de plano do qual você deseja exibir as propriedades e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c18e4-118">Right-click the plan guide of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="c18e4-119">As propriedades a seguir aparecem na caixa de diálogo **Propriedades do Guia de Plano** .</span><span class="sxs-lookup"><span data-stu-id="c18e4-119">The following properties show in the **Plan Guide Properties** dialog box.</span></span>  
  
     <span data-ttu-id="c18e4-120">**Dicas**</span><span class="sxs-lookup"><span data-stu-id="c18e4-120">**Hints**</span></span>  
     <span data-ttu-id="c18e4-121">Exibe as dicas de consulta ou plano de consulta a ser aplicado à instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c18e4-121">Displays the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="c18e4-122">Quando um plano de consulta é especificado como uma dica, a saída Plano de Execução XML para o plano é exibida.</span><span class="sxs-lookup"><span data-stu-id="c18e4-122">When a query plan is specified as a hint, the XML Showplan output for the plan is displayed.</span></span>  
  
     <span data-ttu-id="c18e4-123">**Está desabilitado**</span><span class="sxs-lookup"><span data-stu-id="c18e4-123">**Is disabled**</span></span>  
     <span data-ttu-id="c18e4-124">Exibe o status da guia de plano.</span><span class="sxs-lookup"><span data-stu-id="c18e4-124">Displays the status of the plan guide.</span></span> <span data-ttu-id="c18e4-125">Os valores possíveis são **True** e **False**.</span><span class="sxs-lookup"><span data-stu-id="c18e4-125">Possible values are **True** and **False**.</span></span>  
  
     <span data-ttu-id="c18e4-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c18e4-126">**Name**</span></span>  
     <span data-ttu-id="c18e4-127">Exibe o nome do guia de plano.</span><span class="sxs-lookup"><span data-stu-id="c18e4-127">Displays the name of the plan guide.</span></span>  
  
     <span data-ttu-id="c18e4-128">**Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="c18e4-128">**Parameters**</span></span>  
     <span data-ttu-id="c18e4-129">Quando o tipo de escopo é SQL ou TEMPLATE, são exibidos o nome e os tipos de dados de todos os parâmetros inseridos na instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c18e4-129">When the scope type is SQL or TEMPLATE, displays the name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="c18e4-130">**Lote de escopo**</span><span class="sxs-lookup"><span data-stu-id="c18e4-130">**Scope batch**</span></span>  
     <span data-ttu-id="c18e4-131">Exibe o texto de lote no qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é exibida.</span><span class="sxs-lookup"><span data-stu-id="c18e4-131">Displays the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="c18e4-132">**Nome do objeto de escopo**</span><span class="sxs-lookup"><span data-stu-id="c18e4-132">**Scope object name**</span></span>  
     <span data-ttu-id="c18e4-133">Quando o tipo de escopo é OBJECT, exibi-se o nome do procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)] , da função escalar definida pelo usuário, da função de valor de tabela de várias instruções ou do gatilho DML no qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é exibida.</span><span class="sxs-lookup"><span data-stu-id="c18e4-133">When the scope type is OBJECT, displays the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="c18e4-134">**Nome do esquema de escopo**</span><span class="sxs-lookup"><span data-stu-id="c18e4-134">**Scope schema name**</span></span>  
     <span data-ttu-id="c18e4-135">Quando o tipo de escopo é OBJECT, exibe-se o nome do esquema no qual o objeto está contido.</span><span class="sxs-lookup"><span data-stu-id="c18e4-135">When the scope type is OBJECT, displays the name of the schema in which the object is contained.</span></span>  
  
     <span data-ttu-id="c18e4-136">**Tipo de escopo**</span><span class="sxs-lookup"><span data-stu-id="c18e4-136">**Scope type**</span></span>  
     <span data-ttu-id="c18e4-137">Exibe o tipo de entidade na qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é exibida.</span><span class="sxs-lookup"><span data-stu-id="c18e4-137">Displays the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="c18e4-138">Isso especifica o contexto para se fazer a correspondência da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] ao guia de plano.</span><span class="sxs-lookup"><span data-stu-id="c18e4-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="c18e4-139">Os valores possíveis são **OBJECT**, **SQL**e **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="c18e4-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
     <span data-ttu-id="c18e4-140">**Instrução**</span><span class="sxs-lookup"><span data-stu-id="c18e4-140">**Statement**</span></span>  
     <span data-ttu-id="c18e4-141">Exibe a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] na qual a guia de plano é aplicada.</span><span class="sxs-lookup"><span data-stu-id="c18e4-141">Displays the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is applied.</span></span>  
  
4.  <span data-ttu-id="c18e4-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c18e4-142">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c18e4-143">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c18e4-143">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="c18e4-144">Para visualizar as propriedades de um guia de plano</span><span class="sxs-lookup"><span data-stu-id="c18e4-144">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="c18e4-145">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c18e4-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c18e4-146">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c18e4-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c18e4-147">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c18e4-147">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- If a plan guide named "Guide1" already exists in the AdventureWorks2012 database, delete it.  
    USE AdventureWorks2012;  
    GO  
    IF OBJECT_ID(N'Guide1') IS NOT NULL  
       EXEC sp_control_plan_guide N'DROP', N'Guide1';  
    GO  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
    GO  
    -- Gets the name, created date, and all other relevant property information on the plan guide created above.   
    SELECT name AS plan_guide_name,  
       create_date,  
       query_text,  
       scope_type_desc,  
       OBJECT_NAME(scope_object_id) AS scope_object_name,  
       scope_batch,  
       parameters,  
       hints,  
       is_disabled  
    FROM sys.plan_guides  
    WHERE name = N'Guide1';  
    GO  
    ```  
  
 <span data-ttu-id="c18e4-148">Para obter mais informações, veja [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c18e4-148">For more information, see [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span></span>  
  
  
