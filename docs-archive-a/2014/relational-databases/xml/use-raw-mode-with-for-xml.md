---
title: Usar modo RAW com FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML RAW mode
- XMLSCHEMA option
- FOR XML clause, RAW mode
- RAW FOR XML mode
- ELEMENTS directive
- RAW mode
- XMLDATA option
ms.assetid: 02c1bc0b-760c-4589-9ab1-6927c6d9c734
author: rothja
ms.author: jroth
ms.openlocfilehash: b2908a98336ec8a6e12029ad471f22a33d7a4dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684109"
---
# <a name="use-raw-mode-with-for-xml"></a><span data-ttu-id="30a14-102">Usar modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="30a14-102">Use RAW Mode with FOR XML</span></span>
  <span data-ttu-id="30a14-103">O modo RAW transforma cada linha no conjunto de resultados da consulta em um elemento XML que tem o identificador genérico \<row> ou o nome do elemento fornecido opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="30a14-103">RAW mode transforms each row in the query result set into an XML element that has the generic identifier \<row>, or the optionally provided element name.</span></span> <span data-ttu-id="30a14-104">Por padrão, cada valor de coluna no conjunto de linhas que não é NULL é mapeado para um atributo do elemento \<row>.</span><span class="sxs-lookup"><span data-stu-id="30a14-104">By default, each column value in the rowset that is not NULL is mapped to an attribute of the \<row> element.</span></span> <span data-ttu-id="30a14-105">Se a diretiva ELEMENTS for adicionada à cláusula FOR XML, cada valor de coluna será mapeado para um subelemento do elemento \<row>.</span><span class="sxs-lookup"><span data-stu-id="30a14-105">If the ELEMENTS directive is added to the FOR XML clause, each column value is mapped to a subelement of the \<row> element.</span></span> <span data-ttu-id="30a14-106">Em conjunto com a diretiva ELEMENTS, é possível especificar opcionalmente a opção XSINIL para mapear valores de coluna NULL no conjunto de resultados para um elemento que tem o atributo xsi:nil=`"`true`"`.</span><span class="sxs-lookup"><span data-stu-id="30a14-106">Together with the ELEMENTS directive, you can optionally specify the XSINIL option to map NULL column values in the result set to an element that has the attribute, xsi:nil=`"`true`"`.</span></span>  
  
 <span data-ttu-id="30a14-107">É possível solicitar um esquema para o XML resultante.</span><span class="sxs-lookup"><span data-stu-id="30a14-107">You can request a schema for the resulting XML.</span></span> <span data-ttu-id="30a14-108">A especificação da opção XMLDATA retorna um esquema XDR embutido.</span><span class="sxs-lookup"><span data-stu-id="30a14-108">Specifying the XMLDATA option returns an in-line XDR schema.</span></span> <span data-ttu-id="30a14-109">A especificação da opção XMLSCHEMA retorna um esquema XSD embutido.</span><span class="sxs-lookup"><span data-stu-id="30a14-109">Specifying the XMLSCHEMA option returns an in-line XSD schema.</span></span> <span data-ttu-id="30a14-110">O esquema aparece no início dos dados.</span><span class="sxs-lookup"><span data-stu-id="30a14-110">The schema appears at the start of the data.</span></span> <span data-ttu-id="30a14-111">No resultado, a referência ao namespace do esquema é repetida para cada elemento de alto nível.</span><span class="sxs-lookup"><span data-stu-id="30a14-111">In the result, the schema namespace reference is repeated for every top-level element.</span></span>  
  
 <span data-ttu-id="30a14-112">A opção BINARY BASE64 deve ser especificada na cláusula FOR XML para retornar os dados binários em formato codificado na base64.</span><span class="sxs-lookup"><span data-stu-id="30a14-112">The BINARY BASE64 option must be specified in the FOR XML clause to return the binary data in base64-encoded format.</span></span> <span data-ttu-id="30a14-113">Em modo RAW, a recuperação de dados binários sem especificar a opção BINARY BASE64 resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="30a14-113">In RAW mode, retrieving binary data without specifying the BINARY BASE64 option will result in an error.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30a14-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="30a14-114">In This Section</span></span>  
 <span data-ttu-id="30a14-115">Esta seção contém os seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="30a14-115">This section contains the following examples:</span></span>  
  
-   [<span data-ttu-id="30a14-116">Exemplo: Recuperando informações de modelo do produto como XML</span><span class="sxs-lookup"><span data-stu-id="30a14-116">Example: Retrieving Product Model Information as XML</span></span>](example-retrieving-product-model-information-as-xml.md)  
  
-   [<span data-ttu-id="30a14-117">Exemplo: Especificando XSINIL com a diretiva ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="30a14-117">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>](example-specifying-xsinil-with-the-elements-directive.md)  
  
-   [<span data-ttu-id="30a14-118">Exemplo: Solicitando esquemas como resultados com as opções XMLDATA e XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="30a14-118">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>](example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options.md)  
  
-   [<span data-ttu-id="30a14-119">Exemplo: Recuperando dados binários</span><span class="sxs-lookup"><span data-stu-id="30a14-119">Example: Retrieving Binary Data</span></span>](example-retrieving-binary-data.md)  
  
-   [<span data-ttu-id="30a14-120">Exemplo: Renomeando o elemento &#60;row&#62;</span><span class="sxs-lookup"><span data-stu-id="30a14-120">Example: Renaming the &#60;row&#62; Element</span></span>](example-renaming-the-row-element.md)  
  
-   [<span data-ttu-id="30a14-121">Exemplo: Especificando um elemento raiz para o XML gerado por FOR XML</span><span class="sxs-lookup"><span data-stu-id="30a14-121">Example: Specifying a Root Element for the XML Generated by FOR XML</span></span>](example-specifying-a-root-element-for-the-xml-generated-by-for-xml.md)  
  
-   [<span data-ttu-id="30a14-122">Exemplo: Consultando colunas XMLType</span><span class="sxs-lookup"><span data-stu-id="30a14-122">Example: Querying XMLType Columns</span></span>](example-querying-xmltype-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="30a14-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="30a14-123">See Also</span></span>  
 <span data-ttu-id="30a14-124">[Adicionar namespaces a consultas com WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="30a14-124">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="30a14-125">[Usar o modo AUTO com FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="30a14-125">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="30a14-126">[Usar o modo EXPLICIT com FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="30a14-126">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="30a14-127">[Usar o modo PATH com FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="30a14-127">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="30a14-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30a14-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="30a14-129">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30a14-129">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
