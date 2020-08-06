---
title: Caixa de diálogo partição de mesclagem (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.mergepartition.f1
ms.assetid: 1c94e250-ee18-4f98-b112-985f6346102a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1978c187bfb5097d286f78650b5bda6645c7a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582187"
---
# <a name="merge-partition-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="44e4d-102">Caixa de diálogo Partição de Mesclagem (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="44e4d-102">Merge Partition Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="44e4d-103">Use a caixa de diálogo **Partição de Mesclagem** no **SQL Server Management Studio** para mesclar partições para um grupo de medidas em um cubo.</span><span class="sxs-lookup"><span data-stu-id="44e4d-103">Use the **Merge Partition** dialog box in **SQL Server Management Studio** to merge partitions for a measure group in a cube.</span></span> <span data-ttu-id="44e4d-104">É possível exibir a caixa de diálogo **Partição de Mesclagem** clicando com o botão direito do mouse na pasta Partições ou em uma partição no **Explorador de Objetos** e selecionando **Partições de Mesclagem** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="44e4d-104">You can display the **Merge Partition** dialog box by right-clicking the Partitions folder or a partition in **Object Explorer** and selecting **Merge Partitions** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="44e4d-105">Opções</span><span class="sxs-lookup"><span data-stu-id="44e4d-105">Options</span></span>  
 <span data-ttu-id="44e4d-106">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="44e4d-106">**Server**</span></span>  
 <span data-ttu-id="44e4d-107">Selecione o nome da instância do Analysis Services que contém a partição de destino.</span><span class="sxs-lookup"><span data-stu-id="44e4d-107">Select the name of the Analysis Services instance that contains the target partition.</span></span>  
  
 <span data-ttu-id="44e4d-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="44e4d-108">**Name**</span></span>  
 <span data-ttu-id="44e4d-109">Selecione o nome de uma partição existente a ser usada como a partição de destino.</span><span class="sxs-lookup"><span data-stu-id="44e4d-109">Select the name of an existing partition to use as the target partition.</span></span>  
  
 <span data-ttu-id="44e4d-110">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="44e4d-110">**Folder**</span></span>  
 <span data-ttu-id="44e4d-111">Exibe o nome da pasta que contém a partição de destino, se a partição selecionada em Nome não usar a pasta padrão da instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="44e4d-111">Displays the name of the folder that contains the target partition, if the partition selected in Name does not use the default folder for the Analysis Services instance.</span></span>  
  
 <span data-ttu-id="44e4d-112">**Partições de Origem**</span><span class="sxs-lookup"><span data-stu-id="44e4d-112">**Source Partitions**</span></span>  
 <span data-ttu-id="44e4d-113">Exibe uma grade contendo as partições de origem que podem ser mescladas na partição de destino.</span><span class="sxs-lookup"><span data-stu-id="44e4d-113">Displays a grind containing the source partitions that can be merged into the target partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44e4d-114">Somente partições no mesmo grupo de medidas que compartilham o mesmo design de agregação podem ser mescladas.</span><span class="sxs-lookup"><span data-stu-id="44e4d-114">Only partitions in the same measure group that share the same aggregation design can be merged.</span></span>  
  
 <span data-ttu-id="44e4d-115">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="44e4d-115">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="44e4d-116">Column</span><span class="sxs-lookup"><span data-stu-id="44e4d-116">Column</span></span>|<span data-ttu-id="44e4d-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="44e4d-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="44e4d-118">**Mesclagem**</span><span class="sxs-lookup"><span data-stu-id="44e4d-118">**Merge**</span></span>|<span data-ttu-id="44e4d-119">Selecione para mesclar a partição de origem na partição de destino.</span><span class="sxs-lookup"><span data-stu-id="44e4d-119">Select to merge the source partition into the target partition.</span></span>|  
|<span data-ttu-id="44e4d-120">**Nome da Partição**</span><span class="sxs-lookup"><span data-stu-id="44e4d-120">**Partition Name**</span></span>|<span data-ttu-id="44e4d-121">Exibe o nome da partição de origem.</span><span class="sxs-lookup"><span data-stu-id="44e4d-121">Displays the name of the source partition.</span></span>|  
|<span data-ttu-id="44e4d-122">**Último Processamento**</span><span class="sxs-lookup"><span data-stu-id="44e4d-122">**Last Processed**</span></span>|<span data-ttu-id="44e4d-123">Exibe a data e a hora nas quais a partição de origem foi processada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="44e4d-123">Displays the date and time at which the source partition was last processed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44e4d-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44e4d-124">See Also</span></span>  
 <span data-ttu-id="44e4d-125">[Partições &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="44e4d-125">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="44e4d-126">Mesclar partições no Analysis Services &#40;SSAS – Multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="44e4d-126">Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  
