---
title: Caixa de diálogo Propriedades da dimensão (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.dimensionproperties.f1
helpviewer_keywords:
- Dimension Properties dialog box
ms.assetid: 7235d443-b2ce-4c53-b2eb-abceb28394bb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0523220c76c11280165bc825c5c00c5eb9e23be6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583885"
---
# <a name="dimension-properties-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="c90d0-102">Caixa de diálogo Propriedades da Dimensão (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="c90d0-102">Dimension Properties Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c90d0-103">Use a caixa de diálogo **Propriedades da Dimensão** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para definir as propriedades de uma dimensão em um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c90d0-103">Use the **Dimension Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to set the properties of a dimension in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="c90d0-104">Você pode exibir a caixa de diálogo **Propriedades da Dimensão** clicando com o botão direito do mouse em uma dimensão no Pesquisador de Objetos e selecionando **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c90d0-104">You can display the **Dimension Properties** dialog box by right-clicking a dimension in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c90d0-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c90d0-105">Options</span></span>  
  
|<span data-ttu-id="c90d0-106">Termo</span><span class="sxs-lookup"><span data-stu-id="c90d0-106">Term</span></span>|<span data-ttu-id="c90d0-107">Definição</span><span class="sxs-lookup"><span data-stu-id="c90d0-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="c90d0-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c90d0-108">**Name**</span></span>|<span data-ttu-id="c90d0-109">Exibe o nome da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-109">Displays the name of the dimension.</span></span>|  
|<span data-ttu-id="c90d0-110">**ID**</span><span class="sxs-lookup"><span data-stu-id="c90d0-110">**ID**</span></span>|<span data-ttu-id="c90d0-111">Exibe o identificador da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-111">Displays the identifier of the dimension.</span></span>|  
|<span data-ttu-id="c90d0-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c90d0-112">**Description**</span></span>|<span data-ttu-id="c90d0-113">Exibe a descrição da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-113">Displays the description of the dimension.</span></span>|  
|<span data-ttu-id="c90d0-114">**Criar Carimbo de Data/Hora**</span><span class="sxs-lookup"><span data-stu-id="c90d0-114">**Create Timestamp**</span></span>|<span data-ttu-id="c90d0-115">Exibe a data e a hora de criação da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-115">Displays the date and time the dimension was created.</span></span>|  
|<span data-ttu-id="c90d0-116">**Última Atualização de Esquema**</span><span class="sxs-lookup"><span data-stu-id="c90d0-116">**Last Schema Update**</span></span>|<span data-ttu-id="c90d0-117">Exibe a data e a hora da última atualização dos metadados da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-117">Displays the date and time the metadata for the dimension was last updated.</span></span>|  
|<span data-ttu-id="c90d0-118">**Modo de Processamento**</span><span class="sxs-lookup"><span data-stu-id="c90d0-118">**Processing Mode**</span></span>|<span data-ttu-id="c90d0-119">Selecione o modo de processamento a ser usado para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-119">Select the processing mode to use for the dimension.</span></span> <span data-ttu-id="c90d0-120">Para obter mais informações sobre os valores dessa propriedade, consulte <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90d0-120">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span></span>|  
|<span data-ttu-id="c90d0-121">**State**</span><span class="sxs-lookup"><span data-stu-id="c90d0-121">**State**</span></span>|<span data-ttu-id="c90d0-122">Exibe o estado do processamento da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-122">Displays the processing state of the dimension.</span></span> <span data-ttu-id="c90d0-123">Para obter mais informações sobre os valores dessa propriedade, consulte <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90d0-123">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span></span>|  
|<span data-ttu-id="c90d0-124">**Último Processamento**</span><span class="sxs-lookup"><span data-stu-id="c90d0-124">**Last Processed**</span></span>|<span data-ttu-id="c90d0-125">Exibe a data e a hora do último processamento da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-125">Displays the date and time the dimension was last processed.</span></span>|  
|<span data-ttu-id="c90d0-126">**Modo de Armazenamento Atual**</span><span class="sxs-lookup"><span data-stu-id="c90d0-126">**Current Storage Mode**</span></span>|<span data-ttu-id="c90d0-127">Exibe o modo de armazenamento atual para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="c90d0-127">Displays the current storage mode for the dimension.</span></span> <span data-ttu-id="c90d0-128">Para obter mais informações sobre os valores dessa propriedade, consulte <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90d0-128">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c90d0-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c90d0-129">See Also</span></span>  
 <span data-ttu-id="c90d0-130">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c90d0-130">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="c90d0-131">Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="c90d0-131">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
