---
title: Habilitar detalhamento para um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6adfc389776f91132e527130f50f61c9783d9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569721"
---
# <a name="enable-drillthrough-for-a-mining-model"></a><span data-ttu-id="c14f9-102">Habilitar o detalhamento para um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="c14f9-102">Enable Drillthrough for a Mining Model</span></span>
  <span data-ttu-id="c14f9-103">Se você habilitou o detalhamento para um modelo de mineração, quando você procurar o modelo, poderá recuperar informações detalhadas sobre os casos usados para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="c14f9-103">If you have enabled drillthrough for a mining model, when you browse the model you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="c14f9-104">Para exibir essas informações, você deve ter as permissões necessárias e a estrutura já deve ter sido processada.</span><span class="sxs-lookup"><span data-stu-id="c14f9-104">To view this information, you must have the necessary permissions, and the structure must have already been processed.</span></span>  
  
 <span data-ttu-id="c14f9-105">**Permissões** Para que um usuário analise detalhadamente os dados do modelo ou da estrutura, ele deve ser membro de uma função que tenha permissões [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) no modelo ou na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="c14f9-105">**Permissions** For a user to drill through to either model data or structure data, the user must be a member of a role that has [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) permissions on the mining model or mining structure.</span></span> <span data-ttu-id="c14f9-106">As permissões de detalhamento são definidas separadamente na estrutura e no modelo.</span><span class="sxs-lookup"><span data-stu-id="c14f9-106">Drillthrough permissions are set separately on the structure and model.</span></span>  
  
-   <span data-ttu-id="c14f9-107">As permissões de detalhamento no modelo lhe permitem detalhar do modelo, mesmo que você não tenha permissões na estrutura.</span><span class="sxs-lookup"><span data-stu-id="c14f9-107">Drillthrough permissions on the model enable you to drill through from the model, even if you do not have permissions on the structure.</span></span>  
  
-   <span data-ttu-id="c14f9-108">As permissões para detalhamento na estrutura fornecem a capacidade adicional de incluir colunas de estrutura em consultas de detalhamento do modelo, usando a função [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx).</span><span class="sxs-lookup"><span data-stu-id="c14f9-108">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span> <span data-ttu-id="c14f9-109">Você também pode consultar os casos de treinamento e teste na estrutura usando a marca SELECT... DE \<structure> . Sintaxe CASEs.</span><span class="sxs-lookup"><span data-stu-id="c14f9-109">You can also query the training and test cases in the structure by using the SELECT... FROM \<structure>.CASES syntax.</span></span>  
  
 <span data-ttu-id="c14f9-110">**Cache de casos de treinamento** O detalhamento funciona recuperando informações sobre os casos de treinamento na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="c14f9-110">**Caching of training cases** Drillthrough works by retrieving information about the training cases in the mining structure.</span></span> <span data-ttu-id="c14f9-111">Essas informações são armazenadas em cache quando a estrutura é processada.</span><span class="sxs-lookup"><span data-stu-id="c14f9-111">This information is cached when the structure is processed.</span></span> <span data-ttu-id="c14f9-112">Assim, se você optar por limpar todos os dados em cache alterando a propriedade <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> para `ClearAfterProcessing`, o detalhamento não funcionará.</span><span class="sxs-lookup"><span data-stu-id="c14f9-112">Therefore, if you choose to clear all cached data by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c14f9-113">Se os casos de treinamento não tiverem sido armazenados em cache, você deverá alterar a propriedade <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> para **KeepTrainingCases** e processar o modelo novamente, antes de exibir os dados do caso.</span><span class="sxs-lookup"><span data-stu-id="c14f9-113">If the training cases have not been cached, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the model before you can view the case data.</span></span>  
  
 <span data-ttu-id="c14f9-114">Para obter mais informações, consulte [Consultas de detalhamento &#40;Mineração de dados&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="c14f9-114">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="c14f9-115">Como habilitar o detalhamento em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="c14f9-115">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="c14f9-116">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na guia **Modelos de Mineração** do Designer de Mineração de Dados, clique com o botão direito do mouse no nome do modelo de mineração no qual você deseja habilitar o detalhamento e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c14f9-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the name of the mining model on which you want to enable drillthrough, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c14f9-117">Nas janelas **Propriedades** , clique em **AllowDrillThrough**e selecione **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="c14f9-117">In the **Properties** windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="c14f9-118">Na guia **Modelos de Mineração** , clique com o botão direito do mouse no modelo e selecione **Modelo de Processo**.</span><span class="sxs-lookup"><span data-stu-id="c14f9-118">In the **Mining Models** tab, right-click the model, and select **Process Model**.</span></span>  
  
### <a name="to-enable-caching-for-a-mining-structure"></a><span data-ttu-id="c14f9-119">Para habilitar o cache para uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="c14f9-119">To enable caching for a mining structure</span></span>  
  
1.  <span data-ttu-id="c14f9-120">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na guia **Estrutura de Mineração** do Designer de Mineração de Dados, clique com o botão direito do mouse no nome da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="c14f9-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Structure** tab of Data Mining Designer, right-click the name of the mining structure.</span></span>  
  
2.  <span data-ttu-id="c14f9-121">Abra a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="c14f9-121">Open the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="c14f9-122">Na janela **Propriedades** , localize a propriedade **CacheMode** e selecione **KeepTrainingCases** na lista.</span><span class="sxs-lookup"><span data-stu-id="c14f9-122">In the **Properties** window, locate the **CacheMode** property, and select **KeepTrainingCases** from the list.</span></span>  
  
4.  <span data-ttu-id="c14f9-123">No menu **Banco de Dados** , selecione **Processo**.</span><span class="sxs-lookup"><span data-stu-id="c14f9-123">On the **Database** menu, select **Process**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14f9-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c14f9-124">See Also</span></span>  
 [<span data-ttu-id="c14f9-125">Consultas de detalhamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="c14f9-125">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
