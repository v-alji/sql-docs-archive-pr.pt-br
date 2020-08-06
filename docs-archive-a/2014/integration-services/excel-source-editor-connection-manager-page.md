---
title: Editor de origem do Excel (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3285b5c8b14016b91005af79542e3e2f9b6559b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574799"
---
# <a name="excel-source-editor-connection-manager-page"></a><span data-ttu-id="251eb-102">Editor de Origem do Excel (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="251eb-102">Excel Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="251eb-103">Use o nó **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem do Excel** para selecionar a pasta de trabalho do [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] para a origem que será usada.</span><span class="sxs-lookup"><span data-stu-id="251eb-103">Use the **Connection Manager** node of the **Excel Source Editor** dialog box to select the [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook for the source to use.</span></span> <span data-ttu-id="251eb-104">A origem do Excel lê os dados de uma planilha ou intervalo nomeado em uma pasta de trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="251eb-104">The Excel source reads data from a worksheet or named range in an existing workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="251eb-105">A `CommandTimeout` propriedade da origem do Excel não está disponível no **Editor de origem do Excel**, mas pode ser definida usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="251eb-105">The `CommandTimeout` property of the Excel source is not available in the **Excel Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="251eb-106">Para obter mais informações sobre esta propriedade, consulte a seção Origem do Excel em [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="251eb-106">For more information on this property, see the Excel Source section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="251eb-107">Para obter mais informações sobre origem do Excel, consulte [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="251eb-107">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="251eb-108">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="251eb-108">Static Options</span></span>  
 <span data-ttu-id="251eb-109">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="251eb-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="251eb-110">Selecione um gerenciador de conexões do Excel existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="251eb-110">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="251eb-111">**Novo**</span><span class="sxs-lookup"><span data-stu-id="251eb-111">**New**</span></span>  
 <span data-ttu-id="251eb-112">Crie um novo gerenciador de conexões usando a caixa de diálogo **Gerenciador de Conexões do Excel** .</span><span class="sxs-lookup"><span data-stu-id="251eb-112">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="251eb-113">**Modo de acesso aos dados**</span><span class="sxs-lookup"><span data-stu-id="251eb-113">**Data access mode**</span></span>  
 <span data-ttu-id="251eb-114">Especifique o método para selecionar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="251eb-114">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="251eb-115">Valor</span><span class="sxs-lookup"><span data-stu-id="251eb-115">Value</span></span>|<span data-ttu-id="251eb-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="251eb-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="251eb-117">Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="251eb-117">Table or view</span></span>|<span data-ttu-id="251eb-118">Recupere dados de uma planilha ou intervalo nomeado no arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="251eb-118">Retrieve data from a worksheet or named range in the Excel file.</span></span>|  
|<span data-ttu-id="251eb-119">Nome da tabela ou variável do nome de exibição</span><span class="sxs-lookup"><span data-stu-id="251eb-119">Table name or view name variable</span></span>|<span data-ttu-id="251eb-120">Especifique a planilha ou o nome do intervalo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="251eb-120">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="251eb-121">**Informações relacionadas:** [Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="251eb-121">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="251eb-122">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="251eb-122">SQL command</span></span>|<span data-ttu-id="251eb-123">Recupere os dados do arquivo do Excel usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="251eb-123">Retrieve data from the Excel file by using a SQL query.</span></span> <span data-ttu-id="251eb-124">Para obter mais informações sobre a sintaxe da consulta, consulte [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="251eb-124">For information about query syntax, see [Excel Source](data-flow/excel-source.md).</span></span>|  
|<span data-ttu-id="251eb-125">Comando SQL a partir da variável</span><span class="sxs-lookup"><span data-stu-id="251eb-125">SQL command from variable</span></span>|<span data-ttu-id="251eb-126">Especifique o texto da consulta SQL em uma variável.</span><span class="sxs-lookup"><span data-stu-id="251eb-126">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="251eb-127">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="251eb-127">**Preview**</span></span>  
 <span data-ttu-id="251eb-128">Visualize os resultados usando a caixa de diálogo **Exibição de Dados** .</span><span class="sxs-lookup"><span data-stu-id="251eb-128">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="251eb-129">A visualização pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="251eb-129">Preview can display up to 200 rows.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="251eb-130">Opções dinâmicas de modo de acesso aos dados</span><span class="sxs-lookup"><span data-stu-id="251eb-130">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="251eb-131">Modo de acesso aos dados = Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="251eb-131">Data access mode = Table or view</span></span>  
 <span data-ttu-id="251eb-132">**Nome da planilha do Excel**</span><span class="sxs-lookup"><span data-stu-id="251eb-132">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="251eb-133">Selecione o nome da planilha ou o intervalo nomeado na lista disponível na pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="251eb-133">Select the name of the worksheet or named range from a list of those available in the Excel workbook.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="251eb-134">Modo de acesso aos dados = Variável do nome da tabela ou do nome de exibição</span><span class="sxs-lookup"><span data-stu-id="251eb-134">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="251eb-135">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="251eb-135">**Variable name**</span></span>  
 <span data-ttu-id="251eb-136">Selecione a variável que contém o nome da planilha ou do intervalo nomeado.</span><span class="sxs-lookup"><span data-stu-id="251eb-136">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="251eb-137">Modo de acesso aos dados = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="251eb-137">Data access mode = SQL command</span></span>  
 <span data-ttu-id="251eb-138">**Texto do comando SQL**</span><span class="sxs-lookup"><span data-stu-id="251eb-138">**SQL command text**</span></span>  
 <span data-ttu-id="251eb-139">Insira o texto de uma consulta SQL, crie a consulta clicando em **Construir Consulta**ou procure o arquivo que contém o texto da consulta clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="251eb-139">Enter the text of a SQL query, build the query by clicking **Build Query**, or browse to the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="251eb-140">**Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="251eb-140">**Parameters**</span></span>  
 <span data-ttu-id="251eb-141">Se você inseriu uma consulta parametrizada usando ?</span><span class="sxs-lookup"><span data-stu-id="251eb-141">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="251eb-142">como um espaço reservado para o parâmetro no texto da consulta, use a caixa de diálogo **Definir Parâmetros da Consulta** para mapear os parâmetros de entrada da consulta para as variáveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="251eb-142">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="251eb-143">**Construir consulta**</span><span class="sxs-lookup"><span data-stu-id="251eb-143">**Build query**</span></span>  
 <span data-ttu-id="251eb-144">Use a caixa de diálogo **Construtor de Consultas** para construir a consulta SQL visualmente.</span><span class="sxs-lookup"><span data-stu-id="251eb-144">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="251eb-145">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="251eb-145">**Browse**</span></span>  
 <span data-ttu-id="251eb-146">Use a caixa de diálogo **Abrir** para localizar o arquivo com contém o texto da consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="251eb-146">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="251eb-147">**Analisar consulta**</span><span class="sxs-lookup"><span data-stu-id="251eb-147">**Parse query**</span></span>  
 <span data-ttu-id="251eb-148">Verifique a sintaxe do texto da consulta.</span><span class="sxs-lookup"><span data-stu-id="251eb-148">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="251eb-149">Modo de acesso aos dados = Comando SQL a partir da variável</span><span class="sxs-lookup"><span data-stu-id="251eb-149">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="251eb-150">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="251eb-150">**Variable name**</span></span>  
 <span data-ttu-id="251eb-151">Selecione a variável que contém o texto da consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="251eb-151">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="251eb-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="251eb-152">See Also</span></span>  
 <span data-ttu-id="251eb-153">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="251eb-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="251eb-154">[Editor de origem do Excel &#40;página colunas&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="251eb-154">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="251eb-155">[Editor de origem do Excel &#40;página saída de erro&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="251eb-155">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="251eb-156">[Gerenciador de conexões do Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="251eb-156">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="251eb-157">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="251eb-157">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
