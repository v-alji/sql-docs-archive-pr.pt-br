---
title: Mesclando partições (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572766"
---
# <a name="merging-partitions-xmla"></a><span data-ttu-id="0c72c-102">Mesclando partições (XMLA)</span><span class="sxs-lookup"><span data-stu-id="0c72c-102">Merging Partitions (XMLA)</span></span>
  <span data-ttu-id="0c72c-103">Se as partições tiverem o mesmo design e estrutura de agregação, você poderá mesclar a partição usando o comando [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) no XML for Analysis (XMLA).</span><span class="sxs-lookup"><span data-stu-id="0c72c-103">If partitions have the same aggregation design and structure, you can merge the partition by using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="0c72c-104">A mesclagem de partições é uma ação importante a ser executada quando você gerencia partições, principalmente as partições que contêm dados históricos divididos por data.</span><span class="sxs-lookup"><span data-stu-id="0c72c-104">Merging partitions is an important action to perform when you manage partitions, especially those partitions that contain historical data partitioned by date.</span></span>  
  
 <span data-ttu-id="0c72c-105">Por exemplo, um cubo financeiro pode usar duas partições:</span><span class="sxs-lookup"><span data-stu-id="0c72c-105">For example, a financial cube may use two partitions:</span></span>  
  
-   <span data-ttu-id="0c72c-106">Uma partição representa dados financeiros do ano atual, usando configurações de armazenamento ROLAP (OLAP relacional) em tempo real para desempenho.</span><span class="sxs-lookup"><span data-stu-id="0c72c-106">One partition represents financial data for the current year, using real-time relational OLAP (ROLAP) storage settings for performance.</span></span>  
  
-   <span data-ttu-id="0c72c-107">Outra partição contém dados financeiros dos anos anteriores, usando configurações de armazenamento MOLAP (OLAP multidimensional) para armazenamento.</span><span class="sxs-lookup"><span data-stu-id="0c72c-107">Another partition contains financial data for previous years, using multidimensional OLAP (MOLAP) storage settings for storage.</span></span>  
  
 <span data-ttu-id="0c72c-108">Ambas as partições utilizam configurações de armazenamento diferentes, mas usam o mesmo design de agregação.</span><span class="sxs-lookup"><span data-stu-id="0c72c-108">Both partitions use different storage settings, but use the same aggregation design.</span></span> <span data-ttu-id="0c72c-109">Em vez de processar o cubo nos anos de dados históricos no final do ano, você pode usar o comando `MergePartitions` para mesclar a partição do ano atual com a partição dos anos anteriores.</span><span class="sxs-lookup"><span data-stu-id="0c72c-109">Instead of processing the cube across years of historical data at the end of the year, you can instead use the `MergePartitions` command to merge the partition for the current year into the partition for previous years.</span></span> <span data-ttu-id="0c72c-110">Isso preservará os dados de agregação sem exibir um processamento completo do cubo potencialmente demorado.</span><span class="sxs-lookup"><span data-stu-id="0c72c-110">This preserves the aggregation data without requiring a potentially time-consuming full processing of the cube.</span></span>  
  
## <a name="specifying-partitions-to-merge"></a><span data-ttu-id="0c72c-111">Especificando partições para mesclagem</span><span class="sxs-lookup"><span data-stu-id="0c72c-111">Specifying Partitions to Merge</span></span>  
 <span data-ttu-id="0c72c-112">Quando o `MergePartitions` comando é executado, os dados de agregação armazenados nas partições de origem especificadas na propriedade [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) são adicionados à partição de destino especificada na propriedade [target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="0c72c-112">When the `MergePartitions` command runs, the aggregation data stored in the source partitions specified in the [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property is added to the target partition specified in the [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c72c-113">A propriedade `Source` pode conter mais de uma referência de objeto de partição.</span><span class="sxs-lookup"><span data-stu-id="0c72c-113">The `Source` property can contain more than one partition object reference.</span></span> <span data-ttu-id="0c72c-114">No entanto, a propriedade `Target` não pode.</span><span class="sxs-lookup"><span data-stu-id="0c72c-114">However, the `Target` property cannot.</span></span>  
  
 <span data-ttu-id="0c72c-115">Para que sejam mescladas com êxito, as partições especificadas em `Source` e em `Target` devem estar contidas no mesmo grupo de medidas e usar o mesmo design de agregação.</span><span class="sxs-lookup"><span data-stu-id="0c72c-115">To be successfully merged, the partitions specified in both the `Source` and `Target` must be contained by the same measure group and use the same aggregation design.</span></span> <span data-ttu-id="0c72c-116">Caso contrário, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="0c72c-116">Otherwise, an error occurs.</span></span>  
  
 <span data-ttu-id="0c72c-117">As partições especificadas em `Source` serão excluídas depois que o comando `MergePartitions` for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="0c72c-117">The partitions specified in the `Source` are deleted after the `MergePartitions` command is successfully completed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0c72c-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0c72c-118">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="0c72c-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c72c-119">Description</span></span>  
 <span data-ttu-id="0c72c-120">O exemplo a seguir mescla todas as partições no grupo de medidas **Customer** Counts do cubo **Adventure Works** no banco de dados de exemplo do **Adventure Works DW** na [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partição **Customers_2004** .</span><span class="sxs-lookup"><span data-stu-id="0c72c-120">The following example merges all the partitions in the **Customer Counts** measure group of the **Adventure Works** cube in the **Adventure Works DW** sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database into the **Customers_2004** partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0c72c-121">Código</span><span class="sxs-lookup"><span data-stu-id="0c72c-121">Code</span></span>  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c72c-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c72c-122">See Also</span></span>  
 [<span data-ttu-id="0c72c-123">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0c72c-123">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
