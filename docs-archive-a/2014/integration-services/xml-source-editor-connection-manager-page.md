---
title: Editor de origem XML (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.connectionmanager.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: e6507403-a3ce-4b6f-91fc-a7de9f7b6283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e40ca6ef2d8fbcd10b756a2ce15f33730c367d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583152"
---
# <a name="xml-source-editor-connection-manager-page"></a><span data-ttu-id="6d81c-102">Editor de Origem XML (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="6d81c-102">XML Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="6d81c-103">Use a página **Gerenciador de Conexões** do **Editor de Origem XML** para especificar um arquivo XML e o XSD que transforma os dados XML.</span><span class="sxs-lookup"><span data-stu-id="6d81c-103">Use the **Connection Manager** page of the **XML Source Editor** to specify an XML file and the XSD that transforms the XML data.</span></span>  
  
 <span data-ttu-id="6d81c-104">Para obter mais informações sobre a origem XML, consulte [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="6d81c-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="6d81c-105">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="6d81c-105">Static Options</span></span>  
 <span data-ttu-id="6d81c-106">**Modo de acesso aos dados**</span><span class="sxs-lookup"><span data-stu-id="6d81c-106">**Data access mode**</span></span>  
 <span data-ttu-id="6d81c-107">Especifique o método para selecionar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="6d81c-107">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="6d81c-108">Valor</span><span class="sxs-lookup"><span data-stu-id="6d81c-108">Value</span></span>|<span data-ttu-id="6d81c-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="6d81c-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d81c-110">Localização do arquivo XML</span><span class="sxs-lookup"><span data-stu-id="6d81c-110">XML file location</span></span>|<span data-ttu-id="6d81c-111">Recupera dados de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="6d81c-111">Retrieve data from an XML file.</span></span>|  
|<span data-ttu-id="6d81c-112">Arquivo XML de variável</span><span class="sxs-lookup"><span data-stu-id="6d81c-112">XML file from variable</span></span>|<span data-ttu-id="6d81c-113">Especifica o nome de arquivo XML em uma variável.</span><span class="sxs-lookup"><span data-stu-id="6d81c-113">Specify the XML file name in a variable.</span></span><br /><br /> <span data-ttu-id="6d81c-114">**Informações relacionadas**: [Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="6d81c-114">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="6d81c-115">Dados XML de variável</span><span class="sxs-lookup"><span data-stu-id="6d81c-115">XML data from variable</span></span>|<span data-ttu-id="6d81c-116">Recupera dados XML de uma variável.</span><span class="sxs-lookup"><span data-stu-id="6d81c-116">Retrieve XML data from a variable.</span></span>|  
  
 <span data-ttu-id="6d81c-117">**Usar esquema embutido**</span><span class="sxs-lookup"><span data-stu-id="6d81c-117">**Use inline schema**</span></span>  
 <span data-ttu-id="6d81c-118">Especifique se os próprios dados de origem XML contêm o esquema XSD que define e valida sua estrutura e dados.</span><span class="sxs-lookup"><span data-stu-id="6d81c-118">Specify whether the XML source data itself contains the XSD schema that defines and validates its structure and data.</span></span>  
  
 <span data-ttu-id="6d81c-119">**Local de XSD**</span><span class="sxs-lookup"><span data-stu-id="6d81c-119">**XSD location**</span></span>  
 <span data-ttu-id="6d81c-120">Digite o caminho e nome de arquivo do esquema de arquivo XSD ou localize o arquivo clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-120">Type the path and file name of the XSD schema file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6d81c-121">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="6d81c-121">**Browse**</span></span>  
 <span data-ttu-id="6d81c-122">Use a caixa de diálogo **Abrir** para localizar o arquivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="6d81c-122">Use the **Open** dialog box to locate the XSD schema file.</span></span>  
  
 <span data-ttu-id="6d81c-123">**Gerar XSD**</span><span class="sxs-lookup"><span data-stu-id="6d81c-123">**Generate XSD**</span></span>  
 <span data-ttu-id="6d81c-124">Use a caixa de diálogo **Salvar Como** para selecionar um local para o arquivo de esquema XSD gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6d81c-124">Use the **Save As** dialog box to select a location for the auto-generated XSD schema file.</span></span> <span data-ttu-id="6d81c-125">O editor infere o esquema da estrutura dos dados XML.</span><span class="sxs-lookup"><span data-stu-id="6d81c-125">The editor infers the schema from the structure of the XML data.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="6d81c-126">Opções dinâmicas de modo de acesso aos dados</span><span class="sxs-lookup"><span data-stu-id="6d81c-126">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--xml-file-location"></a><span data-ttu-id="6d81c-127">Modo de acesso aos dados = local de arquivo XML</span><span class="sxs-lookup"><span data-stu-id="6d81c-127">Data access mode = XML file location</span></span>  
 <span data-ttu-id="6d81c-128">**Local de XML**</span><span class="sxs-lookup"><span data-stu-id="6d81c-128">**XML location**</span></span>  
 <span data-ttu-id="6d81c-129">Digite o caminho e nome de arquivo do arquivo de dados XML ou localize o arquivo clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-129">Type the path and file name of the XML data file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6d81c-130">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="6d81c-130">**Browse**</span></span>  
 <span data-ttu-id="6d81c-131">Use a caixa de diálogo **Abrir** para localizar o arquivo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="6d81c-131">Use the **Open** dialog box to locate the XML data file.</span></span>  
  
### <a name="data-access-mode--xml-file-from-variable"></a><span data-ttu-id="6d81c-132">Modo de acesso aos dados = arquivo XML de variável</span><span class="sxs-lookup"><span data-stu-id="6d81c-132">Data access mode = XML file from variable</span></span>  
 <span data-ttu-id="6d81c-133">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="6d81c-133">**Variable name**</span></span>  
 <span data-ttu-id="6d81c-134">Selecione a variável que contém o caminho e o nome de arquivo do arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="6d81c-134">Select the variable that contains the path and file name of the XML file.</span></span>  
  
### <a name="data-access-mode--xml-data-from-variable"></a><span data-ttu-id="6d81c-135">Modo de acesso aos dados = dados XML de variável</span><span class="sxs-lookup"><span data-stu-id="6d81c-135">Data access mode = XML data from variable</span></span>  
 <span data-ttu-id="6d81c-136">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="6d81c-136">**Variable name**</span></span>  
 <span data-ttu-id="6d81c-137">Selecione uma variável que contenha os dados XML.</span><span class="sxs-lookup"><span data-stu-id="6d81c-137">Select the variable that contains the XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d81c-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6d81c-138">See Also</span></span>  
 <span data-ttu-id="6d81c-139">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6d81c-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6d81c-140">[Editor de origem XML &#40;página colunas&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="6d81c-140">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="6d81c-141">[Editor de origem XML &#40;página saída de erro&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="6d81c-141">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="6d81c-142">Extrair dados por meio da origem XML</span><span class="sxs-lookup"><span data-stu-id="6d81c-142">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
