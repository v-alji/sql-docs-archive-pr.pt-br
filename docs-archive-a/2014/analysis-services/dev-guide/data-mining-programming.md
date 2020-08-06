---
title: Programação de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd4bd48b5914d5fda89f94c0a959e670ffec3321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679081"
---
# <a name="data-mining-programming"></a><span data-ttu-id="6b02c-102">Programação de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="6b02c-102">Data Mining Programming</span></span>
  <span data-ttu-id="6b02c-103">Se você considerar que ferramentas e visualizadores internos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não atendem às suas necessidades, poderá ampliar a capacidade do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] codificando suas próprias extensões.</span><span class="sxs-lookup"><span data-stu-id="6b02c-103">If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="6b02c-104">Nessa abordagem, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="6b02c-104">In this approach, you have two options:</span></span>  
  
-   <span data-ttu-id="6b02c-105">**XMLA**</span><span class="sxs-lookup"><span data-stu-id="6b02c-105">**XMLA**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="6b02c-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]dá suporte a XML for Analysis (XMLA) como um protocolo para comunicação com aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="6b02c-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications.</span></span> <span data-ttu-id="6b02c-107">Comandos adicionais têm suporte do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que estende a especificação do XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="6b02c-107">Additional commands are supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.</span></span>  
  
     <span data-ttu-id="6b02c-108">Como o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa XMLA para definição de dados, manipulação de dados e suporte a controle de dados, você pode criar estruturas de mineração e modelos de mineração usando as ferramentas visuais fornecidas pelo [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e, em seguida, estender os objetos de data mining criados usando os scripts de extensão DMX e de linguagem ASSL.</span><span class="sxs-lookup"><span data-stu-id="6b02c-108">Because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.</span></span>  
  
     <span data-ttu-id="6b02c-109">Você pode criar e pode modificar objetos de data mining completamente em scripts de XMLA e executar consultas de previsão em modelos programaticamente de seus próprios aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6b02c-109">You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.</span></span>  
  
-   <span data-ttu-id="6b02c-110">**Objetos de Gerenciamento de Análise (AMO)**</span><span class="sxs-lookup"><span data-stu-id="6b02c-110">**Analysis Management Objects (AMO)**</span></span>  
  
     <span data-ttu-id="6b02c-111">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] também fornece uma estrutura completa que permite aos provedores de mineração de dados de terceiros integrar os seguintes objetos de mineração de dados no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b02c-111">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="6b02c-112">Você pode criar estruturas de mineração e modelos de mineração usando AMO.</span><span class="sxs-lookup"><span data-stu-id="6b02c-112">You can create mining structures and mining models by using AMO.</span></span> <span data-ttu-id="6b02c-113">Consulte os seguintes exemplos em CodePlex:</span><span class="sxs-lookup"><span data-stu-id="6b02c-113">See the following samples in CodePlex:</span></span>  
  
    -   <span data-ttu-id="6b02c-114">Navegador AMO</span><span class="sxs-lookup"><span data-stu-id="6b02c-114">AMO Browser</span></span>  
  
         <span data-ttu-id="6b02c-115">Conecta-se à instância do SSAS especificada e lista todos os objetos de servidor e suas propriedades, incluindo estrutura de mineração e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="6b02c-115">Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.</span></span>  
  
    -   <span data-ttu-id="6b02c-116">Exemplo Simples de AMO</span><span class="sxs-lookup"><span data-stu-id="6b02c-116">AMO Simple Sample</span></span>  
  
         <span data-ttu-id="6b02c-117">O Exemplo Simples do AS aborda o acesso programático à maioria dos objetos principais, e demonstra a navegação de metadados e o acesso aos valores em objetos.</span><span class="sxs-lookup"><span data-stu-id="6b02c-117">The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.</span></span>  
  
         <span data-ttu-id="6b02c-118">O exemplo também demonstra como criar e processar uma estrutura e um modelo de mineração de dados, bem como navegar em um modelo de mineração de dados existente.</span><span class="sxs-lookup"><span data-stu-id="6b02c-118">The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.</span></span>  
  
-   <span data-ttu-id="6b02c-119">**Symmetrix**</span><span class="sxs-lookup"><span data-stu-id="6b02c-119">**DMX**</span></span>  
  
     <span data-ttu-id="6b02c-120">Você pode usar DMX para encapsular instruções de comando, consultas de previsão e resultados da consulta e metadados de retorno em um formato de tabela, supondo que você tenha criado uma conexão com um servidor do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b02c-120">You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b02c-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6b02c-121">In This Section</span></span>  
 [<span data-ttu-id="6b02c-122">OLE DB for Data Mining</span><span class="sxs-lookup"><span data-stu-id="6b02c-122">OLE DB for Data Mining</span></span>](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 <span data-ttu-id="6b02c-123">Descreve adições à especificação para dar suporte à mineração de dados e a dados multidimensionais: novos conjuntos de linhas e colunas de esquemas, linguagem DMX para criação e gerenciamento de estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="6b02c-123">Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.</span></span>  
  
## <a name="related-reference"></a><span data-ttu-id="6b02c-124">Referência relacionada</span><span class="sxs-lookup"><span data-stu-id="6b02c-124">Related Reference</span></span>  
 [<span data-ttu-id="6b02c-125">Desenvolvendo com ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="6b02c-125">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
 <span data-ttu-id="6b02c-126">Apresenta objetos de programação do servidor e do cliente ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="6b02c-126">Introduces ADOMD.NET client and server programming objects.</span></span>  
  
 [<span data-ttu-id="6b02c-127">Desenvolvendo com AMO &#40;Objetos de Gerenciamento de Análise&#41;</span><span class="sxs-lookup"><span data-stu-id="6b02c-127">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
 <span data-ttu-id="6b02c-128">Apresenta a biblioteca de programação AMO.</span><span class="sxs-lookup"><span data-stu-id="6b02c-128">Introduces the AMO programming library.</span></span>  
  
 [<span data-ttu-id="6b02c-129">Desenvolvendo com ASSL &#40;linguagem de script do Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6b02c-129">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 <span data-ttu-id="6b02c-130">Apresenta o XML for Analysis (XMLA) e suas extensões.</span><span class="sxs-lookup"><span data-stu-id="6b02c-130">Introduces XML for Analysis (XMLA) and its extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b02c-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b02c-131">See Also</span></span>  
 <span data-ttu-id="6b02c-132">[Guia do desenvolvedor &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="6b02c-132">[Developer's Guide &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span></span>  
 [<span data-ttu-id="6b02c-133">Referência de DMX &#40;extensões DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b02c-133">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
