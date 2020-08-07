---
title: Conjunto de linhas DISCOVER_XEVENT_TRACE_DEFINITION | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: e1ce2d2d-f994-4318-801a-ee0385aecd84
author: minewiskan
ms.author: owend
ms.openlocfilehash: bedd6ec66a188738ac9a522b4802b3b431e82f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681899"
---
# <a name="discover_xevent_trace_definition-rowset"></a><span data-ttu-id="34c46-102">Conjunto de linhas DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="34c46-102">DISCOVER_XEVENT_TRACE_DEFINITION Rowset</span></span>
  <span data-ttu-id="34c46-103">Oferece informações sobre os rastreamentos XEvent atualmente ativos no servidor.</span><span class="sxs-lookup"><span data-stu-id="34c46-103">Provides information about XEvent traces that are currently active on the server.</span></span>  
  
 <span data-ttu-id="34c46-104">**Aplica-se a:** modelos de tabela, modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="34c46-104">**Applies to:** tabular models, multidimensional models</span></span>  
  
## <a name="rowset-columns"></a><span data-ttu-id="34c46-105">Colunas do conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="34c46-105">Rowset Columns</span></span>  
 <span data-ttu-id="34c46-106">O conjunto de linhas `DISCOVER_XEVENT_TRACE_DEFINITION` contém as colunas a seguir.</span><span class="sxs-lookup"><span data-stu-id="34c46-106">The `DISCOVER_XEVENT_TRACE_DEFINITION` rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="34c46-107">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="34c46-107">Column name</span></span>|<span data-ttu-id="34c46-108">Indicador de tipo</span><span class="sxs-lookup"><span data-stu-id="34c46-108">Type indicator</span></span>|<span data-ttu-id="34c46-109">Tamanho</span><span class="sxs-lookup"><span data-stu-id="34c46-109">Length</span></span>|<span data-ttu-id="34c46-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="34c46-110">Description</span></span>|  
|-----------------|--------------------|------------|-----------------|  
|`Data`|`DBTYPE_WSTR`||<span data-ttu-id="34c46-111">A definição XML do rastreamento XEvent.</span><span class="sxs-lookup"><span data-stu-id="34c46-111">The XML definition of the XEvent trace.</span></span>|  
  
 <span data-ttu-id="34c46-112">Este conjunto de linhas do esquema não é classificado.</span><span class="sxs-lookup"><span data-stu-id="34c46-112">This schema rowset is not sorted.</span></span>  
  
## <a name="using-adomdnet-to-return-the-rowset"></a><span data-ttu-id="34c46-113">Usando ADOMD.NET para retornar o conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="34c46-113">Using ADOMD.NET to return the rowset</span></span>  
 <span data-ttu-id="34c46-114">Ao usar ADOMD.NET e o conjunto de linhas de esquema para recuperar metadados, você pode usar o GUID ou a cadeia de caracteres para referenciar um objeto de conjunto de linhas de esquema no método GetSchemaDataSet.</span><span class="sxs-lookup"><span data-stu-id="34c46-114">When using ADOMD.NET and the schema rowset to retrieve metadata, you can use either the GUID or string to reference a schema rowset object in the GetSchemaDataSet method.</span></span> <span data-ttu-id="34c46-115">Para obter mais informações, consulte [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span><span class="sxs-lookup"><span data-stu-id="34c46-115">For more information, see [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span></span>  
  
 <span data-ttu-id="34c46-116">A tabela a seguir fornece os valores de GUID e de cadeia de caracteres que identificam este conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="34c46-116">The following table provides the GUID and string values that identify this rowset.</span></span>  
  
|<span data-ttu-id="34c46-117">Argumento</span><span class="sxs-lookup"><span data-stu-id="34c46-117">Argument</span></span>|<span data-ttu-id="34c46-118">Valor</span><span class="sxs-lookup"><span data-stu-id="34c46-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="34c46-119">GUID</span><span class="sxs-lookup"><span data-stu-id="34c46-119">GUID</span></span>|<span data-ttu-id="34c46-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span><span class="sxs-lookup"><span data-stu-id="34c46-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span></span>|  
|<span data-ttu-id="34c46-121">String</span><span class="sxs-lookup"><span data-stu-id="34c46-121">String</span></span>|<span data-ttu-id="34c46-122">DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="34c46-122">DISCOVER_XEVENT_TRACE_DEFINITION</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34c46-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34c46-123">See Also</span></span>  
 <span data-ttu-id="34c46-124">[Conjuntos de linhas de esquema XML for Analysis](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span><span class="sxs-lookup"><span data-stu-id="34c46-124">[XML for Analysis Schema Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span></span>  
 <span data-ttu-id="34c46-125">[Usar SQL Server eventos estendidos &#40;&#41; de XEvents para monitorar Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="34c46-125">[Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span></span>  
 [<span data-ttu-id="34c46-126">Usar DMVs &#40;Exibições de Gerenciamento Dinâmico&#41; para monitorar o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="34c46-126">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](../instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
  
