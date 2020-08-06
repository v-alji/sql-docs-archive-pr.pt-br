---
title: Usar o SQL Server Profiler para criar e testar guias de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- checking plan guides
- plan guides [SQL Server], testing
- plan guides [SQL Server], SQL Server Profiler
- matching queries to plan guides [SQL Server]
- testing plan guides
- SQL Server Profiler, plan guides
- plan guides [SQL Server], creating
- capturing query text [SQL Server]
- verifying plan guides
- Profiler [SQL Server Profiler], plan guides
- query-to-plan guide matching [SQL Server]
ms.assetid: 7018dbf0-1a1a-411a-88af-327bedf9cfbd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 543905343d74c9fbabe5f671d9021657ea5f76b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680912"
---
# <a name="use-sql-server-profiler-to-create-and-test-plan-guides"></a><span data-ttu-id="58b7a-102">Usar o SQL Server Profiler para criar e testar guias de plano</span><span class="sxs-lookup"><span data-stu-id="58b7a-102">Use SQL Server Profiler to Create and Test Plan Guides</span></span>
  <span data-ttu-id="58b7a-103">Ao criar um guia de plano, você poderá usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para capturar o texto de consulta exato para usar no argumento *statement_text* do procedimento armazenado **sp_create_plan_guide** .</span><span class="sxs-lookup"><span data-stu-id="58b7a-103">When you are creating a plan guide, you can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to capture the exact query text for use in the *statement_text* argument of the **sp_create_plan_guide** stored procedure.</span></span> <span data-ttu-id="58b7a-104">Isto ajuda a certificar que o guia de plano será correspondido à consulta no tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="58b7a-104">This helps make sure that the plan guide will be matched to the query at compile time.</span></span> <span data-ttu-id="58b7a-105">Depois que o guia de plano é criado, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] também pode ser usado para testar se o guia de plano está, de fato, sendo correspondido à consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-105">After the plan guide is created, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can also be used to test that the plan guide is, in fact, being matched to the query.</span></span> <span data-ttu-id="58b7a-106">De maneira geral, você deve testar guias de plano usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para verificar se a sua consulta está sendo correspondida ao guia de plano.</span><span class="sxs-lookup"><span data-stu-id="58b7a-106">Generally, you should test plan guides by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to verify that your query is being matched to your plan guide.</span></span>  
  
## <a name="capturing-query-text-by-using-sql-server-profiler"></a><span data-ttu-id="58b7a-107">Capturando texto de consulta usando o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="58b7a-107">Capturing Query Text by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="58b7a-108">Se você executar uma consulta e capturar o texto exatamente como foi submetido ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], será possível criar um guia de plano do tipo SQL ou TEMPLATE que corresponderá exatamente ao texto de consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-108">If you run a query and capture the text exactly as it was submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a plan guide of type SQL or TEMPLATE that will match the query text exactly.</span></span> <span data-ttu-id="58b7a-109">Isto certifica que o guia de plano seja usado pelo otimizador de consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-109">This makes sure that the plan guide is used by the query optimizer.</span></span>  
  
 <span data-ttu-id="58b7a-110">Considere a seguinte consulta, que é submetida por um aplicativo como um lote autônomo:</span><span class="sxs-lookup"><span data-stu-id="58b7a-110">Consider the following query that is submitted by an application as a stand-alone batch:</span></span>  
  
```  
SELECT COUNT(*) AS c  
FROM Sales.SalesOrderHeader AS h  
INNER JOIN Sales.SalesOrderDetail AS d  
  ON h.SalesOrderID = d.SalesOrderID  
WHERE h.OrderDate BETWEEN '20000101' and '20050101';  
```  
  
 <span data-ttu-id="58b7a-111">Suponha que você queira que essa consulta execute uma operação de mescla de junção, mas SHOWPLAN indica que a consulta não está usando uma mescla de junção.</span><span class="sxs-lookup"><span data-stu-id="58b7a-111">Suppose you want this query to execute using a merge join operation, but SHOWPLAN indicates that the query is not using a merge join.</span></span> <span data-ttu-id="58b7a-112">Você não pode alterar a consulta diretamente no aplicativo, então, em vez disso, cria um guia de plano para especificar que a dica de consulta MERGE JOIN seja acrescentada à consulta no tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="58b7a-112">You cannot change the query directly in the application, so instead you create a plan guide to specify that the MERGE JOIN query hint be appended to the query at compile time.</span></span>  
  
 <span data-ttu-id="58b7a-113">Para capturar o texto da consulta exatamente como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o recebe, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="58b7a-113">To capture the text of the query exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it, follow these steps:</span></span>  
  
1.  <span data-ttu-id="58b7a-114">Inicie um rastreamento de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , certificando-se de que o tipo de evento **do SQL:BatchStarting** esteja selecionado.</span><span class="sxs-lookup"><span data-stu-id="58b7a-114">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making sure that the **SQL:BatchStarting** event type is selected.</span></span>  
  
2.  <span data-ttu-id="58b7a-115">Faça com que o aplicativo execute a consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-115">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="58b7a-116">Pause o rastreamento do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58b7a-116">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="58b7a-117">Clique no evento **SQL:BatchStarting** que corresponde à consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-117">Click the **SQL:BatchStarting** event that corresponds to the query.</span></span>  
  
5.  <span data-ttu-id="58b7a-118">Clique com o botão direito do mouse e selecione **Extrair Dados de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="58b7a-118">Right-click and select **Extract Event Data**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="58b7a-119">Não tente copiar o texto em lote selecionando-o no painel inferior da janela de rastreamento do Profiler.</span><span class="sxs-lookup"><span data-stu-id="58b7a-119">Do not try to copy the batch text by selecting it from the lower pane of the Profiler trace window.</span></span> <span data-ttu-id="58b7a-120">Isto pode fazer com que o guia de plano que você criou não corresponda ao lote original.</span><span class="sxs-lookup"><span data-stu-id="58b7a-120">This might cause the plan guide that you create to not match the original batch.</span></span>  
  
6.  <span data-ttu-id="58b7a-121">Salve os dados de evento em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="58b7a-121">Save the event data to a file.</span></span> <span data-ttu-id="58b7a-122">Este é o texto em lote.</span><span class="sxs-lookup"><span data-stu-id="58b7a-122">This is the batch text.</span></span>  
  
7.  <span data-ttu-id="58b7a-123">Abra o arquivo de texto em lote no Bloco de Notas e copie o texto no buffer copiar e colar.</span><span class="sxs-lookup"><span data-stu-id="58b7a-123">Open the batch text file in Notepad and copy the text to the copy and paste buffer.</span></span>  
  
8.  <span data-ttu-id="58b7a-124">Crie o guia de plano e cole o texto copiado dentro das aspas (**''**) especificadas para o argumento **@stmt** .</span><span class="sxs-lookup"><span data-stu-id="58b7a-124">Create the plan guide and paste the copied text inside the quotation marks (**''**) specified for the **@stmt** argument.</span></span> <span data-ttu-id="58b7a-125">Você deve escapar entre aspas simples no **@stmt** argumento, precedendo-as com outra aspa simples.</span><span class="sxs-lookup"><span data-stu-id="58b7a-125">You must escape any single quotation marks in the **@stmt** argument by preceding them with another single quotation mark.</span></span> <span data-ttu-id="58b7a-126">Tenha cuidado para não adicionar ou remover nenhum outro caractere quando você inserir essas aspas individuais.</span><span class="sxs-lookup"><span data-stu-id="58b7a-126">Be careful not to add or remove any other characters when you insert these single quotation marks.</span></span> <span data-ttu-id="58b7a-127">Por exemplo, a literal de data **'** 20000101 **'** deve ser delimitada como **20000101**" **.**</span><span class="sxs-lookup"><span data-stu-id="58b7a-127">For example, the date literal **'** 20000101 **'** must be delimited as **''** 20000101 **''**.</span></span>  
  
 <span data-ttu-id="58b7a-128">Aqui está o guia de plano:</span><span class="sxs-lookup"><span data-stu-id="58b7a-128">Here is the plan guide:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'MyGuide1',  
    @stmt = N'<paste the text copied from the batch text file here>',  
    @type = N'SQL',  
    @module_or_batch = NULL,  
    @params = NULL,  
    @hints = N'OPTION (MERGE JOIN)';  
```  
  
## <a name="testing-plan-guides-by-using-sql-server-profiler"></a><span data-ttu-id="58b7a-129">Testando guias de plano usando o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="58b7a-129">Testing Plan Guides by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="58b7a-130">Para verificar se um guia de plano está sendo correspondido a uma consulta, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="58b7a-130">To verify that a plan guide is being matched to a query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="58b7a-131">Inicie um novo rastreamento [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e verifique se o tipo de evento **Showplan XML** está selecionado (localizado abaixo do nó **Desempenho** ).</span><span class="sxs-lookup"><span data-stu-id="58b7a-131">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making certain that the **Showplan XML** event type is selected (located under the **Performance** node).</span></span>  
  
2.  <span data-ttu-id="58b7a-132">Faça com que o aplicativo execute a consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-132">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="58b7a-133">Pause o rastreamento do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58b7a-133">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="58b7a-134">Localize o evento **Plano de Execução XML** para a consulta afetada.</span><span class="sxs-lookup"><span data-stu-id="58b7a-134">Find the **Showplan XML** event for the affected query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58b7a-135">O evento **Showplan XML for Query Compile** não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="58b7a-135">The **Showplan XML for Query Compile** event cannot be used.</span></span> <span data-ttu-id="58b7a-136">**PlanGuideDB** não existe nesse evento.</span><span class="sxs-lookup"><span data-stu-id="58b7a-136">**PlanGuideDB** does not exist in that event.</span></span>  
  
5.  <span data-ttu-id="58b7a-137">Se o guia de plano for do tipo OBJECT ou SQL, verifique se o evento **Plano de Execução XML** contém os atributos **PlanGuideDB** e **PlanGuideName** para o guia de plano que você espera que corresponda à consulta.</span><span class="sxs-lookup"><span data-stu-id="58b7a-137">If the plan guide is of type OBJECT or SQL, verify that the **Showplan XML** event contains the **PlanGuideDB** and **PlanGuideName** attributes for the plan guide that you expected to match the query.</span></span> <span data-ttu-id="58b7a-138">Ou, no caso de um guia de plano de TEMPLATE, verifique se o evento **Plano de Execução XML** contém os atributos **TemplatePlanGuideDB** e **TemplatePlanGuideName** para o guia de plano esperada.</span><span class="sxs-lookup"><span data-stu-id="58b7a-138">Or, in the case of a TEMPLATE plan guide, verify that the **Showplan XML** event contains the **TemplatePlanGuideDB** and **TemplatePlanGuideName** attributes for the expected plan guide.</span></span> <span data-ttu-id="58b7a-139">Isto verifica se o guia de plano está funcionando.</span><span class="sxs-lookup"><span data-stu-id="58b7a-139">This verifies that the plan guide is working.</span></span> <span data-ttu-id="58b7a-140">Esses atributos estão contidos no elemento **\<StmtSimple>** do plano.</span><span class="sxs-lookup"><span data-stu-id="58b7a-140">These attributes are contained under the **\<StmtSimple>** element of the plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b7a-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58b7a-141">See Also</span></span>  
 [<span data-ttu-id="58b7a-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58b7a-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)  
  
  
