---
title: Usar o modo PATH com FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
author: rothja
ms.author: jroth
ms.openlocfilehash: ce0cf811f1e610d14a94993b54c51ea079f613e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574562"
---
# <a name="use-path-mode-with-for-xml"></a><span data-ttu-id="ebb45-102">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="ebb45-102">Use PATH Mode with FOR XML</span></span>
  <span data-ttu-id="ebb45-103">Conforme descrito em [Construindo XML usando FOR XML](for-xml-sql-server.md), o modo PATH fornece uma maneira simples de combinar elementos e atributos.</span><span class="sxs-lookup"><span data-stu-id="ebb45-103">As described in [Constructing XML Using FOR XML](for-xml-sql-server.md), the PATH mode provides a simpler way to mix elements and attributes.</span></span> <span data-ttu-id="ebb45-104">O modo PATH também é uma maneira simples de introduzir aninhamento adicional para representar propriedades complexas.</span><span class="sxs-lookup"><span data-stu-id="ebb45-104">PATH mode is also a simpler way to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="ebb45-105">É possível usar consultas em modo FOR XML EXPLICIT para construir esse XML a partir de um conjunto de linhas, mas o modo PATH fornece uma alternativa simples para as consultas em modo EXPLICIT que são potencialmente trabalhosas.</span><span class="sxs-lookup"><span data-stu-id="ebb45-105">You can use FOR XML EXPLICIT mode queries to construct such XML from a rowset, but the PATH mode provides a simpler alternative to the potentially cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="ebb45-106">O modo PATH, juntamente com a capacidade de escrever consultas FOR XML aninhadas e a diretiva TYPE para retornar instâncias do tipo **xml** , permite escrever consultas com menos complexidade.</span><span class="sxs-lookup"><span data-stu-id="ebb45-106">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span>  
  
 <span data-ttu-id="ebb45-107">No modo PATH, os nomes ou alias de colunas são tratados como expressões XPath.</span><span class="sxs-lookup"><span data-stu-id="ebb45-107">In PATH mode, column names or column aliases are treated as XPath expressions.</span></span> <span data-ttu-id="ebb45-108">Essas expressões indicam como os valores estão sendo mapeados para XML.</span><span class="sxs-lookup"><span data-stu-id="ebb45-108">These expressions indicate how the values are being mapped to XML.</span></span> <span data-ttu-id="ebb45-109">Cada expressão XPath é um XPath relativo que fornece o tipo de item (como atributo, elemento e valor escalar) e o nome e a hierarquia do nó que será gerado em relação ao elemento de linha.</span><span class="sxs-lookup"><span data-stu-id="ebb45-109">Each XPath expression is a relative XPath that provides the item type., such as the attribute, element, and scalar value, and the name and hierarchy of the node that will be generated relative to the row element.</span></span>  
  
 <span data-ttu-id="ebb45-110">Esta seção descreve colunas de mapeamento em um conjunto de linhas em várias condições e fornece exemplos.</span><span class="sxs-lookup"><span data-stu-id="ebb45-110">This section describes mapping columns in a rowset under various conditions, and provides examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebb45-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ebb45-111">In This Section</span></span>  
  
-   [<span data-ttu-id="ebb45-112">Colunas sem um nome</span><span class="sxs-lookup"><span data-stu-id="ebb45-112">Columns without a Name</span></span>](columns-without-a-name.md)  
  
-   [<span data-ttu-id="ebb45-113">Colunas com um nome</span><span class="sxs-lookup"><span data-stu-id="ebb45-113">Columns with a Name</span></span>](columns-with-a-name.md)  
  
-   [<span data-ttu-id="ebb45-114">Colunas com um nome especificado como um caractere curinga</span><span class="sxs-lookup"><span data-stu-id="ebb45-114">Columns with a Name Specified as a Wildcard Character</span></span>](columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [<span data-ttu-id="ebb45-115">Colunas com o nome de um teste de nó XPath</span><span class="sxs-lookup"><span data-stu-id="ebb45-115">Columns with the Name of an XPath Node Test</span></span>](columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [<span data-ttu-id="ebb45-116">Nomes de colunas com o caminho especificado como data&#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="ebb45-116">Column Names with the Path Specified as data&#40;&#41;</span></span>](column-names-with-the-path-specified-as-data.md)  
  
-   [<span data-ttu-id="ebb45-117">Colunas que contêm um valor nulo por padrão</span><span class="sxs-lookup"><span data-stu-id="ebb45-117">Columns that Contain a Null Value By Default</span></span>](columns-that-contain-a-null-value-by-default.md)  
  
-   [<span data-ttu-id="ebb45-118">Suporte a namespace em modo PATH</span><span class="sxs-lookup"><span data-stu-id="ebb45-118">Namespace Support in PATH Mode</span></span>](namespace-support-in-path-mode.md)  
  
-   [<span data-ttu-id="ebb45-119">Exemplos: Usando o modo PATH</span><span class="sxs-lookup"><span data-stu-id="ebb45-119">Examples: Using PATH Mode</span></span>](examples-using-path-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="ebb45-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ebb45-120">See Also</span></span>  
 <span data-ttu-id="ebb45-121">[Adicionar namespaces a consultas com WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="ebb45-121">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="ebb45-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ebb45-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="ebb45-123">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ebb45-123">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
