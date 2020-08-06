---
title: Caixa de diálogo processar (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processdialog.f1
ms.assetid: c065248c-9001-4f0c-928f-9c59eccb618b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 369c121713894bba9b2ce6c40aa2869de49eaa72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685326"
---
# <a name="process-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="06ff8-102">Caixa de diálogo Processar (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="06ff8-102">Process Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="06ff8-103">Use a caixa de diálogo **Processar** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para processar objetos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="06ff8-103">Use the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to process [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="06ff8-104">É possível exibir a caixa de diálogo **Processar** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="06ff8-104">You can display the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="06ff8-105">Clicando com o botão direito do mouse em um projeto, cubo, dimensão ou estrutura de mineração do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no **Gerenciador de Soluções** e selecionando **Processar**.</span><span class="sxs-lookup"><span data-stu-id="06ff8-105">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, cube, dimension, or mining structure in **Solution Explorer** and selecting **Process**.</span></span>  
  
-   <span data-ttu-id="06ff8-106">Selecionando **Processar** na barra de ferramentas em cada página do **Designer de Cubo**, em cada página do **Designer de Dimensão**ou nas páginas **Estrutura de Mineração** e **Modelos de Mineração** do **Designer de Modelo de Mineração de Dados**.</span><span class="sxs-lookup"><span data-stu-id="06ff8-106">Selecting **Process** from the toolbar on every page of **Cube Designer**, every page of **Dimension Designer**, or the **Mining Structure** and **Mining Models** pages of **Data Mining Model Designer**.</span></span>  
  
-   <span data-ttu-id="06ff8-107">Clicando com o botão direito do mouse na página **Modelos de Mineração** do **Designer de Modelo de Data Mining** e selecionando **Estrutura de Mineração do Processo e Todos os Modelos** ou **Modelo de Processo**.</span><span class="sxs-lookup"><span data-stu-id="06ff8-107">Right-clicking a mining model in the **Mining Models** page of **Data Mining Model Designer** and selecting **Process Mining Structure and All Models** or **Process Model**.</span></span>  
  
 <span data-ttu-id="06ff8-108">É possível exibir a caixa de diálogo **Processar** no **SQL Server Management Studio** das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="06ff8-108">You can display the **Process** dialog box in **SQL Server Management Studio** by:</span></span>  
  
-   <span data-ttu-id="06ff8-109">Clicando com o botão direito do mouse em um banco de dados, cubo, grupo de medidas, partição, dimensões, estrutura de mineração ou modelo de mineração do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no **Explorador de Objetos** e selecionando **Processar**.</span><span class="sxs-lookup"><span data-stu-id="06ff8-109">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, cube, measure group, partition, dimension, mining structure, or mining model in **Object Explorer** and selecting **Process**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06ff8-110">Opções</span><span class="sxs-lookup"><span data-stu-id="06ff8-110">Options</span></span>  
 <span data-ttu-id="06ff8-111">**Lista de objetos**</span><span class="sxs-lookup"><span data-stu-id="06ff8-111">**Object list**</span></span>  
 <span data-ttu-id="06ff8-112">Selecione os objetos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a serem processados e as opções e configurações de processamento a serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="06ff8-112">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects to be processed and the processing options and settings to be applied.</span></span> <span data-ttu-id="06ff8-113">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="06ff8-113">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="06ff8-114">**Object Name**</span><span class="sxs-lookup"><span data-stu-id="06ff8-114">**Object Name**</span></span>  
 <span data-ttu-id="06ff8-115">Exibe o nome do objeto a ser processado.</span><span class="sxs-lookup"><span data-stu-id="06ff8-115">Displays the name of the object to be processed.</span></span> <span data-ttu-id="06ff8-116">O ícone à esquerda do nome indica o tipo do objeto.</span><span class="sxs-lookup"><span data-stu-id="06ff8-116">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="06ff8-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="06ff8-117">**Type**</span></span>  
 <span data-ttu-id="06ff8-118">Exibe o tipo do objeto a ser processado.</span><span class="sxs-lookup"><span data-stu-id="06ff8-118">Displays the type of the object to be processed.</span></span>  
  
 <span data-ttu-id="06ff8-119">**Opções de Processo**</span><span class="sxs-lookup"><span data-stu-id="06ff8-119">**Process Options**</span></span>  
 <span data-ttu-id="06ff8-120">Selecione o tipo de processamento a ser executado no objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="06ff8-120">Select the type of processing to perform on the selected object.</span></span> <span data-ttu-id="06ff8-121">Para obter mais informações sobre as opções de processamento disponíveis, consulte [processamento de objeto de modelo multidimensional](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="06ff8-121">For more information about available processing options, see [Multidimensional Model Object Processing](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
 <span data-ttu-id="06ff8-122">**Configurações**</span><span class="sxs-lookup"><span data-stu-id="06ff8-122">**Settings**</span></span>  
 <span data-ttu-id="06ff8-123">Exibe o hiperlink **Configurar** quando você escolhe **Processar Incremental** em **Opções de Processo** para cubos, grupos de medidas ou partições.</span><span class="sxs-lookup"><span data-stu-id="06ff8-123">Displays the **Configure** hyperlink when you choose **Process Incremental** in **Process Options** for cubes, measure groups, or partitions.</span></span> <span data-ttu-id="06ff8-124">Clique em **Configurar** para iniciar a caixa de diálogo **Atualização Incremental** .</span><span class="sxs-lookup"><span data-stu-id="06ff8-124">Click **Configure** to launch the **Incremental Update** dialog box.</span></span> <span data-ttu-id="06ff8-125">Para obter mais informações sobre a caixa de diálogo **Atualização Incremental**, consulte [Caixa de diálogo Atualização Incremental &#40;Analysis Services – Dados Multidimensionais&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="06ff8-125">For more information about the **Incremental Update** dialog box, see [Incremental Update Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="06ff8-126">**Remover**</span><span class="sxs-lookup"><span data-stu-id="06ff8-126">**Remove**</span></span>  
 <span data-ttu-id="06ff8-127">Clique para remover os itens selecionados da **Lista de objetos**.</span><span class="sxs-lookup"><span data-stu-id="06ff8-127">Click to remove the selected items from **Object list**.</span></span>  
  
 <span data-ttu-id="06ff8-128">**Análise de Impacto**</span><span class="sxs-lookup"><span data-stu-id="06ff8-128">**Impact Analysis**</span></span>  
 <span data-ttu-id="06ff8-129">Clique para abrir a caixa de diálogo **Análise de Impacto** e exibir os objetos que serão afetados pela tarefa de processamento.</span><span class="sxs-lookup"><span data-stu-id="06ff8-129">Click to open the **Impact Analysis** dialog box and display the objects that will be affected by the processing task.</span></span> <span data-ttu-id="06ff8-130">Para obter mais informações sobre a caixa de diálogo **Análise de Impacto**, consulte [Caixa de diálogo Análise de Impacto &#40;Analysis Services – Dados Multidimensionais&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="06ff8-130">For more information about the **Impact Analysis** dialog box, see [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06ff8-131">Esta opção é desabilitada quando a opção **Objetos afetados pelo processo** está selecionada na caixa de diálogo **Alterar Configurações** .</span><span class="sxs-lookup"><span data-stu-id="06ff8-131">This option is disabled when the **Process affected objects** option is selected in the **Change Settings** dialog box.</span></span>  
  
 <span data-ttu-id="06ff8-132">**Alterar configurações**</span><span class="sxs-lookup"><span data-stu-id="06ff8-132">**Change Settings**</span></span>  
 <span data-ttu-id="06ff8-133">Clique para abrir a caixa de diálogo **Alterar Configurações** e alterar as configurações que controlam o processamento dos objetos selecionados, incluindo configurações de processamento em lote, configurações de write-back e configurações de erro de chave de dimensão.</span><span class="sxs-lookup"><span data-stu-id="06ff8-133">Click to open the **Change Settings** dialog box and change the settings that govern processing of the selected objects, including batch processing settings, writeback settings, and dimension key error settings.</span></span> <span data-ttu-id="06ff8-134">Para obter mais informações sobre a caixa de diálogo **Alterar Configurações**, consulte [Caixa de diálogo Alterar Configurações &#40;Analysis Services – Dados Multidimensionais&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="06ff8-134">For more information about the **Change Settings** dialog box, see [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="06ff8-135">**Executar**</span><span class="sxs-lookup"><span data-stu-id="06ff8-135">**Run**</span></span>  
 <span data-ttu-id="06ff8-136">Clique para processar os objetos.</span><span class="sxs-lookup"><span data-stu-id="06ff8-136">Click to process the objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ff8-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06ff8-137">See Also</span></span>  
 <span data-ttu-id="06ff8-138">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="06ff8-138">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="06ff8-139">Caixa de diálogo progresso do processo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="06ff8-139">Process Progress Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-progress-dialog-box-analysis-services-multidimensional-data.md)  
  
  
