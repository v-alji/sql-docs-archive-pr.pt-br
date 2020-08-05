---
title: Editor de transformação pesquisa (página conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.referencetable.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: e90d6b69-5a26-43c5-8433-5c3c9588e08c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 381378ac1aca85c6bca825033bc439ebc39fb063
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574107"
---
# <a name="lookup-transformation-editor-connection-page"></a><span data-ttu-id="0c405-102">Editor da Transformação Pesquisa (página Conexão)</span><span class="sxs-lookup"><span data-stu-id="0c405-102">Lookup Transformation Editor (Connection Page)</span></span>
  <span data-ttu-id="0c405-103">Use a página **Conexão** da caixa de diálogo **Editor da Transformação Pesquisa** para selecionar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="0c405-103">Use the **Connection** page of the **Lookup Transformation Editor** dialog box to select a connection manager.</span></span> <span data-ttu-id="0c405-104">Se você selecionar um gerenciador de conexões OLE DB, também poderá selecionar uma consulta, tabela ou exibição para gerar o conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="0c405-104">If you select an OLE DB connection manager, you also select a query, table, or view to generate the reference dataset.</span></span>  
  
 <span data-ttu-id="0c405-105">Para saber mais sobre a transformação Pesquisa, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0c405-105">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c405-106">Opções</span><span class="sxs-lookup"><span data-stu-id="0c405-106">Options</span></span>  
 <span data-ttu-id="0c405-107">As opções a seguir estarão disponíveis quando você selecionar **Cache cheio** e **Gerenciador de conexões de cache** na página Geral da caixa de diálogo **Editor da Transformação Pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="0c405-107">The following options are available when you select **Full cache** and **Cache connection manager** on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0c405-108">**Gerenciador de conexões de cache**</span><span class="sxs-lookup"><span data-stu-id="0c405-108">**Cache connection manager**</span></span>  
 <span data-ttu-id="0c405-109">Selecione um gerenciador de conexões de cache existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="0c405-109">Select an existing Cache connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="0c405-110">**Novo**</span><span class="sxs-lookup"><span data-stu-id="0c405-110">**New**</span></span>  
 <span data-ttu-id="0c405-111">Crie uma nova conexão usando a caixa de diálogo **Editor de Gerenciador de Conexões de Cache** .</span><span class="sxs-lookup"><span data-stu-id="0c405-111">Create a new connection by using the **Cache Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0c405-112">As opções a seguir estarão disponíveis quando você selecionar **Cache cheio**, **Cache parcial**ou **Sem cache**e **Gerenciador de conexões OLE DB**na página Geral da caixa de diálogo **Editor da Transformação Pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="0c405-112">The following options are available when you select **Full cache**, **Partial cache**, or **No cache**, and **OLE DB connection manager**, on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0c405-113">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="0c405-113">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="0c405-114">Selecione um gerenciador de conexões OLE DB existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="0c405-114">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="0c405-115">**Novo**</span><span class="sxs-lookup"><span data-stu-id="0c405-115">**New**</span></span>  
 <span data-ttu-id="0c405-116">Crie uma nova conexão usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="0c405-116">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="0c405-117">**Use uma tabela ou exibição**</span><span class="sxs-lookup"><span data-stu-id="0c405-117">**Use a table or view**</span></span>  
 <span data-ttu-id="0c405-118">Selecione uma tabela ou exibição existente na lista ou crie uma nova tabela clicando em **novo**.</span><span class="sxs-lookup"><span data-stu-id="0c405-118">Select an existing table or view from the list, or create a new table by clicking **New**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c405-119">Se você especificar uma instrução SQL na página **Avançado** do **Editor da Transformação Pesquisa**, essa instrução SQL vai sobrescrever e substituir o nome da tabela selecionada aqui.</span><span class="sxs-lookup"><span data-stu-id="0c405-119">If you specify a SQL statement on the **Advanced** page of the **Lookup Transformation Editor**, that SQL statement overrides and replaces the table name selected here.</span></span> <span data-ttu-id="0c405-120">Para obter mais informações, consulte [Editor de Transformação Pesquisa &#40;Página Avançado&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="0c405-120">For more information, see [Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span></span>  
  
 <span data-ttu-id="0c405-121">**Novo**</span><span class="sxs-lookup"><span data-stu-id="0c405-121">**New**</span></span>  
 <span data-ttu-id="0c405-122">Crie uma nova tabela usando a caixa de diálogo **Criar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="0c405-122">Create a new table by using the **Create Table** dialog box.</span></span>  
  
 <span data-ttu-id="0c405-123">**Usar resultados de uma consulta SQL**</span><span class="sxs-lookup"><span data-stu-id="0c405-123">**Use results of an SQL query**</span></span>  
 <span data-ttu-id="0c405-124">Escolha esta opção para navegar até uma consulta preexistente, criar uma nova consulta, verificar a sintaxe da consulta e visualizar os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="0c405-124">Choose this option to browse to a preexisting query, build a new query, check query syntax, and preview query results.</span></span>  
  
 <span data-ttu-id="0c405-125">**Construir consulta**</span><span class="sxs-lookup"><span data-stu-id="0c405-125">**Build query**</span></span>  
 <span data-ttu-id="0c405-126">Crie a instrução Transact-SQL a ser executada usando o **Construtor de Consultas**, uma ferramenta gráfica que é usada para criar consultas navegando pelos dados.</span><span class="sxs-lookup"><span data-stu-id="0c405-126">Create the Transact-SQL statement to run by using **Query Builder**, a graphical tool that is used to create queries by browsing through data.</span></span>  
  
 <span data-ttu-id="0c405-127">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="0c405-127">**Browse**</span></span>  
 <span data-ttu-id="0c405-128">Use esta opção para navegar até uma consulta preexistente salva como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0c405-128">Use this option to browse to a preexisting query saved as a file.</span></span>  
  
 <span data-ttu-id="0c405-129">**Analisar Consulta**</span><span class="sxs-lookup"><span data-stu-id="0c405-129">**Parse Query**</span></span>  
 <span data-ttu-id="0c405-130">Verifique a sintaxe da consulta.</span><span class="sxs-lookup"><span data-stu-id="0c405-130">Check the syntax of the query.</span></span>  
  
 <span data-ttu-id="0c405-131">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="0c405-131">**Preview**</span></span>  
 <span data-ttu-id="0c405-132">Visualize os resultados usando a caixa de diálogo **Visualizar Resultados da Consulta** .</span><span class="sxs-lookup"><span data-stu-id="0c405-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="0c405-133">Esta opção exibe até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="0c405-133">This option displays up to 200 rows.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="0c405-134">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="0c405-134">External Resources</span></span>  
 <span data-ttu-id="0c405-135">Entrada de blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) (em inglês) em blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="0c405-135">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c405-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c405-136">See Also</span></span>  
 <span data-ttu-id="0c405-137">[Editor de transformação pesquisa &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0c405-137">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="0c405-138">[Editor de transformação pesquisa &#40;página colunas&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="0c405-138">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="0c405-139">[Editor de transformação pesquisa &#40;página avançado&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="0c405-139">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="0c405-140">[Editor de transformação pesquisa &#40;página saída de erro&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="0c405-140">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="0c405-141">transformação Pesquisa Difusa</span><span class="sxs-lookup"><span data-stu-id="0c405-141">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
