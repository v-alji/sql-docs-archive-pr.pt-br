---
title: Editor de destino do Excel (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.connection.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: fc13f725-963c-488e-91e2-20627133e842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1556bf713c49aac31f1cc1cd624336f10dbf832f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574815"
---
# <a name="excel-destination-editor-connection-manager-page"></a><span data-ttu-id="8369c-102">Editor de Destinos do Excel (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="8369c-102">Excel Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="8369c-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Destinos do Excel** para especificar informações da fonte de dados e visualizar os resultados.</span><span class="sxs-lookup"><span data-stu-id="8369c-103">Use the **Connection Manager** page of the **Excel Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="8369c-104">O destino do Excel carrega dados em uma planilha ou um intervalo nomeado em uma pasta de trabalho do [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8369c-104">The Excel destination loads data into a worksheet or a named range in a [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8369c-105">A `CommandTimeout` Propriedade do destino do Excel não está disponível no **Editor de destino do Excel**, mas pode ser definida usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="8369c-105">The `CommandTimeout` property of the Excel destination is not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="8369c-106">Além disso, certas opções de carregamento rápido estão disponíveis apenas no **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="8369c-106">In addition, certain Fast Load options are available only in the **Advanced Editor**.</span></span> <span data-ttu-id="8369c-107">Para obter mais informações sobre essas propriedades, consulte a seção Destino do Excel em [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8369c-107">For more information on these properties, see the Excel Destination section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="8369c-108">Para obter mais informações sobre destinos do Excel, consulte [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8369c-108">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="8369c-109">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="8369c-109">Static Options</span></span>  
 <span data-ttu-id="8369c-110">**Gerenciador de conexões do Excel**</span><span class="sxs-lookup"><span data-stu-id="8369c-110">**Excel connection manager**</span></span>  
 <span data-ttu-id="8369c-111">Selecione um gerenciador de conexões do Excel existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="8369c-111">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="8369c-112">**Novo**</span><span class="sxs-lookup"><span data-stu-id="8369c-112">**New**</span></span>  
 <span data-ttu-id="8369c-113">Crie um novo gerenciador de conexões usando a caixa de diálogo **Gerenciador de Conexões do Excel** .</span><span class="sxs-lookup"><span data-stu-id="8369c-113">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="8369c-114">**Modo de acesso aos dados**</span><span class="sxs-lookup"><span data-stu-id="8369c-114">**Data access mode**</span></span>  
 <span data-ttu-id="8369c-115">Especifique o método para selecionar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="8369c-115">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="8369c-116">Opção</span><span class="sxs-lookup"><span data-stu-id="8369c-116">Option</span></span>|<span data-ttu-id="8369c-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="8369c-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8369c-118">Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="8369c-118">Table or view</span></span>|<span data-ttu-id="8369c-119">Carregue dados em uma planilha ou intervalo nomeado na fonte de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="8369c-119">Loads data into a worksheet or named range in the Excel data source.</span></span>|  
|<span data-ttu-id="8369c-120">Nome da tabela ou variável do nome de exibição</span><span class="sxs-lookup"><span data-stu-id="8369c-120">Table name or view name variable</span></span>|<span data-ttu-id="8369c-121">Especifique a planilha ou o nome do intervalo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="8369c-121">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="8369c-122">**Informações relacionadas**: [Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="8369c-122">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="8369c-123">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="8369c-123">SQL command</span></span>|<span data-ttu-id="8369c-124">Carregue dados no destino do Excel usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="8369c-124">Load data into the Excel destination by using an SQL query.</span></span>|  
  
 <span data-ttu-id="8369c-125">**Nome da planilha do Excel**</span><span class="sxs-lookup"><span data-stu-id="8369c-125">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="8369c-126">Selecione o destino do Excel da listagem suspensa.</span><span class="sxs-lookup"><span data-stu-id="8369c-126">Select the excel destination from the drop-down list.</span></span> <span data-ttu-id="8369c-127">Se a lista estiver vazia, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8369c-127">If the list is empty, click **New**.</span></span>  
  
 <span data-ttu-id="8369c-128">**Novo**</span><span class="sxs-lookup"><span data-stu-id="8369c-128">**New**</span></span>  
 <span data-ttu-id="8369c-129">Clique em **Novo** para iniciar a caixa de diálogo **Criar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="8369c-129">Click **New** to launch the **Create Table** dialog box.</span></span> <span data-ttu-id="8369c-130">Quando você clicar em **OK**, a caixa de diálogo cria o arquivo Excel para o qual o **Gerenciador de Conexões do Excel** aponta.</span><span class="sxs-lookup"><span data-stu-id="8369c-130">When you click **OK**, the dialog box creates the excel file that the **Excel Connection Manager** points to.</span></span>  
  
 <span data-ttu-id="8369c-131">**Exibir dados existentes**</span><span class="sxs-lookup"><span data-stu-id="8369c-131">**View Existing Data**</span></span>  
 <span data-ttu-id="8369c-132">Visualize os resultados usando a caixa de diálogo **Visualizar Resultados da Consulta** .</span><span class="sxs-lookup"><span data-stu-id="8369c-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="8369c-133">A visualização pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="8369c-133">Preview can display up to 200 rows.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8369c-134"> Se o **Gerenciador de conexões do Excel** que você selecionou apontar para um arquivo do Excel que não existe, você verá uma mensagem de erro ao clicar neste botão.</span><span class="sxs-lookup"><span data-stu-id="8369c-134">If the **Excel connection manager** you selected points to an excel file that does not exist, you will see an error message when you click this button.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="8369c-135">Opções dinâmicas de modo de acesso aos dados</span><span class="sxs-lookup"><span data-stu-id="8369c-135">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="8369c-136">Modo de acesso aos dados = Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="8369c-136">Data access mode = Table or view</span></span>  
 <span data-ttu-id="8369c-137">**Nome da planilha do Excel**</span><span class="sxs-lookup"><span data-stu-id="8369c-137">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="8369c-138">Selecione o nome da planilha ou o intervalo nomeado na lista disponível na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="8369c-138">Select the name of the worksheet or named range from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="8369c-139">Modo de acesso aos dados = Variável do nome da tabela ou do nome de exibição</span><span class="sxs-lookup"><span data-stu-id="8369c-139">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="8369c-140">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="8369c-140">**Variable name**</span></span>  
 <span data-ttu-id="8369c-141">Selecione a variável que contém o nome da planilha ou do intervalo nomeado.</span><span class="sxs-lookup"><span data-stu-id="8369c-141">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="8369c-142">Modo de acesso aos dados = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="8369c-142">Data access mode = SQL command</span></span>  
 <span data-ttu-id="8369c-143">**Texto do comando SQL**</span><span class="sxs-lookup"><span data-stu-id="8369c-143">**SQL command text**</span></span>  
 <span data-ttu-id="8369c-144">Digite o texto de uma consulta SQL, crie a consulta clicando em **Construir Consulta**ou localize o arquivo que contém o texto da consulta clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="8369c-144">Enter the text of an SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="8369c-145">**Construir Consulta**</span><span class="sxs-lookup"><span data-stu-id="8369c-145">**Build Query**</span></span>  
 <span data-ttu-id="8369c-146">Use a caixa de diálogo **Construtor de Consultas** para construir a consulta SQL visualmente.</span><span class="sxs-lookup"><span data-stu-id="8369c-146">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="8369c-147">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="8369c-147">**Browse**</span></span>  
 <span data-ttu-id="8369c-148">Use a caixa de diálogo **Abrir** para localizar o arquivo com contém o texto da consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="8369c-148">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="8369c-149">**Analisar Consulta**</span><span class="sxs-lookup"><span data-stu-id="8369c-149">**Parse Query**</span></span>  
 <span data-ttu-id="8369c-150">Verifique a sintaxe do texto da consulta.</span><span class="sxs-lookup"><span data-stu-id="8369c-150">Verify the syntax of the query text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8369c-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8369c-151">See Also</span></span>  
 <span data-ttu-id="8369c-152">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8369c-152">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8369c-153">[Página Mapeamentos &#40;editor de destinos do Excel&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="8369c-153">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="8369c-154">[Editor de destinos do Excel &#40;página saída de erro&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="8369c-154">[Excel Destination Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="8369c-155">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="8369c-155">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
