---
title: Criar um novo guia de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.designer.newplanguide.f1
helpviewer_keywords:
- creating plan guides
- plan guides [SQL Server]. creating
ms.assetid: e1ad78bb-4857-40ea-a0c6-dcf5c28aef2f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60ba31e2a63575a316db5befb397bea59c0ad1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583562"
---
# <a name="create-a-new-plan-guide"></a><span data-ttu-id="cc4e1-102">Criar um novo guia de plano</span><span class="sxs-lookup"><span data-stu-id="cc4e1-102">Create a New Plan Guide</span></span>
  <span data-ttu-id="cc4e1-103">Você pode criar um guia de plano no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc4e1-103">You can create a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cc4e1-104">Guias de plano influenciam a otimização de consulta, anexando a elas dicas de consulta ou um plano de consulta fixo.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-104">Plan guides influence query optimization by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="cc4e1-105">No guia de plano, especifica-se a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] que se deseja otimizar e uma cláusula OPTION que contenha as dicas de consulta que se deseja usar ou um plano de consulta específico que se queira usar para otimizar a consulta.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-105">In the plan guide, you specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="cc4e1-106">Quando a consulta é executada, o otimizador de consultas faz a correspondência da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] com o guia de plano, anexando a cláusula OPTION à consulta em tempo de execução ou usando o plano de consulta especificado.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-106">When the query executes, the query optimizer matches the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide and either attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="cc4e1-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="cc4e1-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cc4e1-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="cc4e1-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cc4e1-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="cc4e1-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cc4e1-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="cc4e1-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cc4e1-111">**Para criar um guia de plano, usando:**</span><span class="sxs-lookup"><span data-stu-id="cc4e1-111">**To create a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="cc4e1-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc4e1-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cc4e1-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc4e1-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cc4e1-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cc4e1-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cc4e1-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="cc4e1-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cc4e1-116">Os argumentos para sp_create_plan_guide devem ser fornecidos na ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-116">The arguments to sp_create_plan_guide must be provided in the order that is shown.</span></span> <span data-ttu-id="cc4e1-117">Quando você aplica valores para os parâmetros de `sp_create_plan_guide`, todos os nomes de parâmetros devem ser especificados explicitamente ou nenhum deles deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-117">When you supply values for the parameters of `sp_create_plan_guide`, all parameter names must be specified explicitly, or none at all.</span></span> <span data-ttu-id="cc4e1-118">Por exemplo, se `@name =` for especificado, `@stmt =`, `@type =`, entre outros, também deverão ser.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-118">For example, if `@name =` is specified, then `@stmt =` , `@type =`, and so on, must also be specified.</span></span> <span data-ttu-id="cc4e1-119">Da mesma forma, se `@name =` for omitido e apenas o valor de parâmetro for fornecido, os nomes de parâmetro restantes deverão ser omitidos também e apenas os seus valores, fornecidos.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-119">Likewise, if `@name =` is omitted and only the parameter value is provided, the remaining parameter names must also be omitted, and only their values provided.</span></span> <span data-ttu-id="cc4e1-120">Os nomes de argumento são usados apenas para fins descritivos, para ajudar compreender a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-120">Argument names are for descriptive purposes only, to help understand the syntax.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cc4e1-121">não verifica se o nome de parâmetro especificado corresponde ao nome do parâmetro na posição em que o nome é usado.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-121">does not verify that the specified parameter name matches the name for the parameter in the position where the name is used.</span></span>  
  
-   <span data-ttu-id="cc4e1-122">Você pode criar mais de um guia de plano OBJECT ou SQL para a mesma consulta e lote ou módulo.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-122">You can create more than one OBJECT or SQL plan guide for the same query and batch or module.</span></span> <span data-ttu-id="cc4e1-123">Porém, só um guia de plano pode ser ativado em um determinado momento.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-123">However, only one plan guide can be enabled at any given time.</span></span>  
  
-   <span data-ttu-id="cc4e1-124">Os guias de plano OBJECT não podem ser criados para um valor @module_or_batch que referencie um procedimento armazenado, uma função ou um gatilho DML que especifique a cláusula WITH ENCRYPTION ou que seja temporário.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-124">Plan guides of type OBJECT cannot be created for an @module_or_batch value that references a stored procedure, function, or DML trigger that specifies the WITH ENCRYPTION clause or that is temporary.</span></span>  
  
-   <span data-ttu-id="cc4e1-125">A tentativa de cancelar ou modificar uma função, procedimento armazenado ou gatilho DML referenciado por um guia de plano, habilitado ou desabilitado, provoca um erro.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-125">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="cc4e1-126">A tentativa de descartar uma tabela com um gatilho definido nela que é mencionado por um guia de plano também causa um erro.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-126">Trying to drop a table that has a trigger defined on it that is referenced by a plan guide also causes an error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cc4e1-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="cc4e1-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cc4e1-128">Permissões</span><span class="sxs-lookup"><span data-stu-id="cc4e1-128">Permissions</span></span>  
 <span data-ttu-id="cc4e1-129">A criação de um guia de plano do tipo OBJECT requer a permissão ALTER no objeto mencionado.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-129">To create a plan guide of type OBJECT, requires ALTER permission on the referenced object.</span></span> <span data-ttu-id="cc4e1-130">A criação de um guia de plano do tipo SQL ou TEMPLATE requer a permissão ALTER no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-130">To create a plan guide of type SQL or TEMPLATE, requires ALTER permission on the current database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cc4e1-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc4e1-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="cc4e1-132">Para criar um guia de plano</span><span class="sxs-lookup"><span data-stu-id="cc4e1-132">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="cc4e1-133">Clique no sinal de adição para expandir o banco de dados no qual você deseja criar um guia de plano e clique no sinal de adição para expandir a pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="cc4e1-133">Click the plus sign to expand the database in which you want to create a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="cc4e1-134">Clique com o botão direito do mouse na pasta **guias de plano** e selecione **novo guia de plano...**.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-134">Right-click the **Plan Guides** folder and select **New Plan Guide...**.</span></span>  
  
3.  <span data-ttu-id="cc4e1-135">Na caixa de diálogo **Novo Guia de Plano** , na caixa **Nome** , digite o nome do guia de plano.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-135">In the **New Plan Guide** dialog box, in the **Name** box, enter the name of the plan guide.</span></span>  
  
4.  <span data-ttu-id="cc4e1-136">Na caixa **Instrução** , insira a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] à qual o guia de plano deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-136">In the **Statement** box, enter the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is to be applied.</span></span>  
  
5.  <span data-ttu-id="cc4e1-137">Na lista **Tipo de escopo** , selecione o tipo de entidade na qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] aparece.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-137">In the **Scope type** list, select the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="cc4e1-138">Isso especifica o contexto para se fazer a correspondência da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] ao guia de plano.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="cc4e1-139">Os valores possíveis são **OBJECT**, **SQL**e **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
6.  <span data-ttu-id="cc4e1-140">Na caixa **Lote de escopo** , digite o texto de lote no qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] aparece.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-140">In the **Scope batch** box, enter the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="cc4e1-141">O texto de lote não pode incluir uma instrução USE\`\`*database* .</span><span class="sxs-lookup"><span data-stu-id="cc4e1-141">The batch text cannot include a USE\`\`*database* statement.</span></span> <span data-ttu-id="cc4e1-142">A caixa **Lote de escopo** está disponível apenas quando **SQL** é selecionado como um tipo de escopo.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-142">The **Scope batch** box is only available when **SQL** is selected as a scope type.</span></span> <span data-ttu-id="cc4e1-143">Se nada for inserido na caixa de lote de escopo quando o SQL for o tipo de escopo, o valor do texto de lote será definido com o mesmo valor que a caixa **Instrução** .</span><span class="sxs-lookup"><span data-stu-id="cc4e1-143">If nothing is entered in the scope batch box when SQL is the scope type, then the value of the batch text is set to the same value as is in the **Statement** box.</span></span>  
  
7.  <span data-ttu-id="cc4e1-144">Na lista **Nome do esquema de escopo** , digite o nome do esquema no qual o objeto está contido.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-144">In the **Scope schema name** list, enter the name of the schema in which the object is contained.</span></span> <span data-ttu-id="cc4e1-145">A caixa **Nome do esquema de escopo** está disponível apenas quando **Objeto** é selecionado como um tipo de escopo.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-145">The **Scope schema name** box is only available when **Object** is selected as a scope type.</span></span>  
  
8.  <span data-ttu-id="cc4e1-146">Na caixa **Nome do objeto de escopo** , digite o nome do [!INCLUDE[tsql](../../includes/tsql-md.md)] procedimento armazenado, função escalar definida pelo usuário, função com valor de tabela de várias instruções ou gatilho DML no qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] aparece.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-146">In the **Scope object name** box, enter the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="cc4e1-147">A caixa **Nome do objeto de escopo** está disponível apenas quando **Objeto** é selecionado como um tipo de escopo.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-147">The **Scope object name** box is only available when **Object** is selected as a scope type.</span></span>  
  
9. <span data-ttu-id="cc4e1-148">Na caixa **Parâmetros** , digite o nome do parâmetro e os tipos de dados de todos os parâmetros inseridos na instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc4e1-148">In the **Parameters** box, enter the parameter name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="cc4e1-149">Parâmetros são aplicados somente quando uma das seguintes condições for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="cc4e1-149">Parameters apply only when either of the following is true:</span></span>  
  
    -   <span data-ttu-id="cc4e1-150">O tipo de escopo é **SQL** ou **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-150">The scope type is **SQL** or **TEMPLATE**.</span></span> <span data-ttu-id="cc4e1-151">No caso de **TEMPLATE**, parâmetros não devem ser NULL.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-151">If **TEMPLATE**, parameters must not be NULL.</span></span>  
  
    -   <span data-ttu-id="cc4e1-152">A instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é enviada usando-se sp_executesql e um valor para o parâmetro é especificado ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] envia internamente uma instrução depois de parametrizá-la.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-152">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is submitted by using sp_executesql and a value for the parameter is specified, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internally submits a statement after parameterizing it.</span></span>  
  
10. <span data-ttu-id="cc4e1-153">Na caixa **Dicas** , digite as dicas de consulta ou o plano de consulta a ser aplicado à instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc4e1-153">In the **Hints** box, enter the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="cc4e1-154">Para especificar uma ou mais dicas de consulta, digite uma cláusula OPTION válida.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-154">To specify one or more query hints, enter a valid OPTION clause.</span></span>  
  
11. <span data-ttu-id="cc4e1-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-155">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cc4e1-156">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc4e1-156">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="cc4e1-157">Para criar um guia de plano</span><span class="sxs-lookup"><span data-stu-id="cc4e1-157">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="cc4e1-158">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc4e1-158">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc4e1-159">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-159">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cc4e1-160">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-160">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
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
  
    ```  
  
 <span data-ttu-id="cc4e1-161">Para obter mais informações, consulte [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cc4e1-161">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span></span>  
  
  
