---
title: Editor de XML
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.editorxml.f1
- sql12.swb.xmleditor.f1
- vs.xmleditor
- sql12.swb.editor.xml.f1
helpviewer_keywords:
- XML Designer [SQL Server Management Studio]
ms.assetid: 0824a5ce-e67b-4b53-98d9-d371faf2d23c
author: rothja
ms.author: jroth
ms.openlocfilehash: b7c3bbbda4f5a31c4d83b559c1aa623ca2aff89f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582397"
---
# <a name="xml-editor-sql-server-management-studio"></a><span data-ttu-id="05ebb-102">Editor XML (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="05ebb-102">XML Editor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="05ebb-103">Fornece um conjunto de ferramentas visuais para trabalhar com Esquemas XML, conjuntos de dados ADO.NET e documentos XML.</span><span class="sxs-lookup"><span data-stu-id="05ebb-103">Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents.</span></span> <span data-ttu-id="05ebb-104">O XML Designer oferece suporte para a linguagem de definição de esquema XML (XSD) definida pelo World Wide Web Consortium (WC3).</span><span class="sxs-lookup"><span data-stu-id="05ebb-104">The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3).</span></span> <span data-ttu-id="05ebb-105">O designer não oferece suporte para DTDs (definições de tipo de documento) ou outras linguagens de esquema XML, como XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="05ebb-105">The designer does not support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).</span></span>  
  
 <span data-ttu-id="05ebb-106">Para exibir o designer, adicione um conjunto de dados, esquema XML ou arquivo XML a seu projeto ou abra qualquer um dos tipos de arquivo listados na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="05ebb-106">To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the table below.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="05ebb-107">Não há nenhum comando **Desfazer** ao trabalhar em exibição de Esquema.</span><span class="sxs-lookup"><span data-stu-id="05ebb-107">There is no **Undo** command when working in Schema view.</span></span> <span data-ttu-id="05ebb-108">Planeje seu trabalho cuidadosamente e salve frequentemente seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="05ebb-108">Plan your work carefully and save your files often.</span></span>  
  
 <span data-ttu-id="05ebb-109">O designer fornece as três exibições (ou modos) a seguir, para se trabalhar em arquivos XML, esquemas XML e conjuntos de dados:</span><span class="sxs-lookup"><span data-stu-id="05ebb-109">The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:</span></span>  
  
|<span data-ttu-id="05ebb-110">Visualizar</span><span class="sxs-lookup"><span data-stu-id="05ebb-110">View</span></span>|<span data-ttu-id="05ebb-111">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="05ebb-111">Description</span></span>|<span data-ttu-id="05ebb-112">Tipos de arquivos com suporte</span><span class="sxs-lookup"><span data-stu-id="05ebb-112">File types supported</span></span>|  
|----------|-----------------|--------------------------|  
|<span data-ttu-id="05ebb-113">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="05ebb-113">**Schema**</span></span>|<span data-ttu-id="05ebb-114">Para criar visualmente e modificar esquemas XML e conjuntos de dados ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="05ebb-114">For visually creating and modifying XML Schemas and ADO.NET datasets.</span></span>|<span data-ttu-id="05ebb-115">.xsd</span><span class="sxs-lookup"><span data-stu-id="05ebb-115">.xsd</span></span>|  
|<span data-ttu-id="05ebb-116">**Dados**</span><span class="sxs-lookup"><span data-stu-id="05ebb-116">**Data**</span></span>|<span data-ttu-id="05ebb-117">Para modificar visualmente arquivos de dados XML em uma grade de dados estruturada.</span><span class="sxs-lookup"><span data-stu-id="05ebb-117">For visually modifying XML data files in a structured data grid.</span></span>|<span data-ttu-id="05ebb-118">.xml</span><span class="sxs-lookup"><span data-stu-id="05ebb-118">.xml</span></span>|  
|<span data-ttu-id="05ebb-119">**XML**</span><span class="sxs-lookup"><span data-stu-id="05ebb-119">**XML**</span></span>|<span data-ttu-id="05ebb-120">Para editar XML; o editor de fonte fornece codificação de cor e IntelliSense, incluindo Complete Word e List Members.</span><span class="sxs-lookup"><span data-stu-id="05ebb-120">For editing XML; the source editor provides color-coding and IntelliSense, including Complete Word and List Members.</span></span>|<span data-ttu-id="05ebb-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span><span class="sxs-lookup"><span data-stu-id="05ebb-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span></span>|  
|<span data-ttu-id="05ebb-122">**Plano de Execução**</span><span class="sxs-lookup"><span data-stu-id="05ebb-122">**ShowPlan**</span></span>|<span data-ttu-id="05ebb-123">Exibe planos de consulta xml criados, usando-se a opção SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="05ebb-123">Displays xml query plans created using the SET SHOWPLAN_XML ON option.</span></span>|<span data-ttu-id="05ebb-124">.showplan</span><span class="sxs-lookup"><span data-stu-id="05ebb-124">.showplan</span></span>|  
  
## <a name="schema-view"></a><span data-ttu-id="05ebb-125">Exibição de esquema</span><span class="sxs-lookup"><span data-stu-id="05ebb-125">Schema View</span></span>  
 <span data-ttu-id="05ebb-126">A exibição de esquema fornece uma representação visual dos elementos, atributos, tipos e assim por diante, que compõem o conjunto de esquemas XML e ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="05ebb-126">Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.</span></span>  
  
 <span data-ttu-id="05ebb-127">Em exibição de esquema é possível construir esquemas e conjuntos de dados descartando elementos na superfície do design tanto da guia de esquema XML da caixa de ferramentas quanto do Gerenciador de servidores.</span><span class="sxs-lookup"><span data-stu-id="05ebb-127">In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer.</span></span> <span data-ttu-id="05ebb-128">Além disso, é possível adicionar elementos ao designer, clicando-se com o botão direito do mouse na superfície de design e selecionando Adicionar no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="05ebb-128">Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.</span></span>  
  
 <span data-ttu-id="05ebb-129">Em exibição de esquema pode você:</span><span class="sxs-lookup"><span data-stu-id="05ebb-129">In Schema view you can:</span></span>  
  
-   <span data-ttu-id="05ebb-130">Construir e modificar esquemas XML e conjuntos de dados ADO.NET existentes</span><span class="sxs-lookup"><span data-stu-id="05ebb-130">Construct and modify existing XML Schemas and ADO.NET datasets</span></span>  
  
-   <span data-ttu-id="05ebb-131">Criar e editar relações entre tabelas</span><span class="sxs-lookup"><span data-stu-id="05ebb-131">Create and edit relationships between tables</span></span>  
  
-   <span data-ttu-id="05ebb-132">Criar e editar chaves</span><span class="sxs-lookup"><span data-stu-id="05ebb-132">Create and edit keys</span></span>  
  
-   <span data-ttu-id="05ebb-133">Gerar conjuntos de dados ADO.NET a partir de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05ebb-133">Generate ADO.NET datasets from XML Schemas</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05ebb-134">O layout de elementos em exibição de esquema é armazenado no arquivo .xsx, que pode ser visto clicando-se em **Mostrar Todos os Arquivos** na barra de ferramentas Gerenciador de Soluções e, então, expandindo-se o arquivo .xsd.</span><span class="sxs-lookup"><span data-stu-id="05ebb-134">The layout of elements in Schema view is stored in the .xsx file, which can be seen by clicking **Show All Files** in the Solution Explorer toolbar, and then expanding the .xsd file.</span></span> <span data-ttu-id="05ebb-135">Se não houver nenhum arquivo .xsx, isso significa que o arquivo .xsd nunca foi aberto no XML Designer.</span><span class="sxs-lookup"><span data-stu-id="05ebb-135">If there is no .xsx file present, it means the .xsd file has never been opened in the XML Designer.</span></span>  
  
### <a name="customizing-schema-view"></a><span data-ttu-id="05ebb-136">Personalizando a exibição de esquema</span><span class="sxs-lookup"><span data-stu-id="05ebb-136">Customizing Schema View</span></span>  
 <span data-ttu-id="05ebb-137">Os recursos a seguir modificam o layout visual de elementos em exibição de esquema:</span><span class="sxs-lookup"><span data-stu-id="05ebb-137">The following features modify the visual layout of elements in Schema view:</span></span>  
  
-   <span data-ttu-id="05ebb-138">Zoom</span><span class="sxs-lookup"><span data-stu-id="05ebb-138">Zooming</span></span>  
  
-   <span data-ttu-id="05ebb-139">Expandindo ou recolhendo elementos aninhados</span><span class="sxs-lookup"><span data-stu-id="05ebb-139">Expanding or collapsing of nested elements</span></span>  
  
-   <span data-ttu-id="05ebb-140">Organizando automaticamente layout de elementos</span><span class="sxs-lookup"><span data-stu-id="05ebb-140">Automatically arranging layout of elements</span></span>  
  
-   <span data-ttu-id="05ebb-141">Reajustando o estado padrão de elementos recolhidos</span><span class="sxs-lookup"><span data-stu-id="05ebb-141">Resetting default state of collapsed elements</span></span>  
  
##### <a name="to-expand-hidden-nested-elements"></a><span data-ttu-id="05ebb-142">Para expandir elementos aninhados ocultos</span><span class="sxs-lookup"><span data-stu-id="05ebb-142">To expand hidden nested elements</span></span>  
  
-   <span data-ttu-id="05ebb-143">Clique no ícone mais na parte inferior do elemento.</span><span class="sxs-lookup"><span data-stu-id="05ebb-143">Click the plus icon on the bottom of the element.</span></span>  
  
##### <a name="to-collapse-nested-elements"></a><span data-ttu-id="05ebb-144">Para recolher elementos aninhados</span><span class="sxs-lookup"><span data-stu-id="05ebb-144">To collapse nested elements</span></span>  
  
-   <span data-ttu-id="05ebb-145">Clique no ícone menos no elemento posicionada na parte mais inferior que você deseja que apareça no designer.</span><span class="sxs-lookup"><span data-stu-id="05ebb-145">Click the minus icon on the bottom-most element that you want to appear on the designer.</span></span>  
  
## <a name="data-view"></a><span data-ttu-id="05ebb-146">Exibição de dados</span><span class="sxs-lookup"><span data-stu-id="05ebb-146">Data View</span></span>  
 <span data-ttu-id="05ebb-147">Exibição de dados fornece uma grade de dados que pode ser usada para modificar arquivos .xml.</span><span class="sxs-lookup"><span data-stu-id="05ebb-147">Data view provides a data grid that can be used to modify .xml files.</span></span> <span data-ttu-id="05ebb-148">Somente o conteúdo (mas não as marcas e estrutura) em um arquivo XML pode ser editado em exibição de dados.</span><span class="sxs-lookup"><span data-stu-id="05ebb-148">Only the content (but not the tags and structure) in an XML file can be edited in Data view.</span></span>  
  
 <span data-ttu-id="05ebb-149">Há duas áreas separadas na Exibição de Dados: **Tabelas de Dados** e **Dados**.</span><span class="sxs-lookup"><span data-stu-id="05ebb-149">There are two separate areas in Data view: **Data Tables** and **Data**.</span></span> <span data-ttu-id="05ebb-150">A área **Tabela de Dados** é uma lista de relações definidas no arquivo XML, na ordem de seu aninhamento (do mais externo para o mais interno).</span><span class="sxs-lookup"><span data-stu-id="05ebb-150">The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost).</span></span> <span data-ttu-id="05ebb-151">A área **Dados** é uma grade de dados que exibe dados com base na seleção na área tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="05ebb-151">The **Data** area is a data grid that displays data based on the selection in the Data Tables area.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05ebb-152">Arquivos XML recentemente criados não contêm nenhum dado e, assim, não podem ser exibidos na exibição de Dados.</span><span class="sxs-lookup"><span data-stu-id="05ebb-152">Newly created XML files contain no data and therefore cannot be displayed in Data view.</span></span> <span data-ttu-id="05ebb-153">Há também algumas instâncias de documentos XML nas quais a exibição de dados não pode ser invocada.</span><span class="sxs-lookup"><span data-stu-id="05ebb-153">There are also some instances of XML documents where data view cannot be invoked at all.</span></span> <span data-ttu-id="05ebb-154">Embora o XML seja considerado bem formado, se não for estruturado dados tentando mudar para exibição de dados irão gerar a seguinte mensagem: "Embora esse documento seja bem formado, ele contém estrutura que a exibição de dados não pode exibir".</span><span class="sxs-lookup"><span data-stu-id="05ebb-154">Although the XML would be considered well formed, if it is not structured data trying to switch to Data view will generate the following message: "Although this document is well formed, it contains structure that Data View cannot display."</span></span>  
  
 <span data-ttu-id="05ebb-155">Na exibição de Dados você pode:</span><span class="sxs-lookup"><span data-stu-id="05ebb-155">In Data view you can:</span></span>  
  
-   <span data-ttu-id="05ebb-156">Popular manualmente tabelas de dados</span><span class="sxs-lookup"><span data-stu-id="05ebb-156">Manually populate data tables</span></span>  
  
-   <span data-ttu-id="05ebb-157">Editar tabelas de dados existentes</span><span class="sxs-lookup"><span data-stu-id="05ebb-157">Edit existing data tables</span></span>  
  
-   <span data-ttu-id="05ebb-158">Gerar um esquema XML a partir de um documento XML</span><span class="sxs-lookup"><span data-stu-id="05ebb-158">Generate an XML Schema from an XML document</span></span>  
  
## <a name="xml-view"></a><span data-ttu-id="05ebb-159">Exibição XML</span><span class="sxs-lookup"><span data-stu-id="05ebb-159">XML View</span></span>  
 <span data-ttu-id="05ebb-160">A exibição XML fornece um editor para edição de XML bruto e, ainda, codificação IntelliSense e de cores.</span><span class="sxs-lookup"><span data-stu-id="05ebb-160">XML view provides an editor for editing raw XML and provides IntelliSense and color coding.</span></span> <span data-ttu-id="05ebb-161">A conclusão de instrução está disponível ao se trabalhar em arquivos .xsd e arquivos .xml que tenham um esquema associado.</span><span class="sxs-lookup"><span data-stu-id="05ebb-161">Statement completion is available when working on .xsd files and .xml files that have an associated schema.</span></span> <span data-ttu-id="05ebb-162">Digite \< para iniciar uma marca e será apresentada uma lista de elementos que são válidos nesse local.</span><span class="sxs-lookup"><span data-stu-id="05ebb-162">Type \< to initiate a tag and you will be presented with a list of elements that are valid at that location.</span></span> <span data-ttu-id="05ebb-163">Depois de digitar o nome do elemento e pressionar SPACEBAR, você terá uma lista de atributos para os quais os elementos oferecem suporte.</span><span class="sxs-lookup"><span data-stu-id="05ebb-163">After you type the element name and press the SPACEBAR, you will be presented with a list of attributes that the element supports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="05ebb-164">IntelliSense não estão disponíveis na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="05ebb-164">IntelliSense options are not available on the toolbar.</span></span> <span data-ttu-id="05ebb-165">Quando estiver no Editor de XML, clique em **IntelliSense** no menu **Editar**para acessar as opções.</span><span class="sxs-lookup"><span data-stu-id="05ebb-165">When in the XML Editor, to access the options, on the **Edit** menu, click **IntelliSense**.</span></span>  
  
## <a name="showplan-view"></a><span data-ttu-id="05ebb-166">Exibição de SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="05ebb-166">SHOWPLAN view</span></span>  
 <span data-ttu-id="05ebb-167">Planos de consulta podem ser salvos em formato XML quando forem criados usando-se a opção SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="05ebb-167">Query plans can be saved in XML format when created using SET SHOWPLAN_XML ON option.</span></span> <span data-ttu-id="05ebb-168">Clique duas vezes em um arquivo com a extensão .showplan para abrir o plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="05ebb-168">Double-click a file with the .showplan extension to open the query plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ebb-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05ebb-169">See Also</span></span>  
 [<span data-ttu-id="05ebb-170">Salvar um plano de execução em formato XML</span><span class="sxs-lookup"><span data-stu-id="05ebb-170">Save an Execution Plan in XML Format</span></span>](../performance/save-an-execution-plan-in-xml-format.md)  
  
  
