---
title: Adicionar um medidor a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da4fef-2b02-40e1-977c-f8f80d87155e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7125080d95e9c7b882df8d715cce5c6cf8aa6344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684089"
---
# <a name="add-a-gauge-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="dc78e-102">Adicionar um medidor a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc78e-102">Add a Gauge to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dc78e-103">Para resumir dados em um formato visual, use uma região de dados do medidor.</span><span class="sxs-lookup"><span data-stu-id="dc78e-103">When you want to summarize data in a visual format, you can use a Gauge data region.</span></span> <span data-ttu-id="dc78e-104">Depois de adicionar uma região de dados do medidor à superfície de design, você pode arrastar campos do conjunto de dados do relatório para um painel de dados no medidor.</span><span class="sxs-lookup"><span data-stu-id="dc78e-104">After you add a Gauge data region to the design surface, you can drag report dataset fields to a data pane on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-gauge-to-your-report"></a><span data-ttu-id="dc78e-105">Para adicionar um medidor a um relatório</span><span class="sxs-lookup"><span data-stu-id="dc78e-105">To add a gauge to your report</span></span>  
  
1.  <span data-ttu-id="dc78e-106">Crie um relatório ou abra um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="dc78e-106">Create a report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="dc78e-107">Na guia Inserir, clique duas vezes em Medidor.</span><span class="sxs-lookup"><span data-stu-id="dc78e-107">On the Insert tab, double-click Gauge.</span></span> <span data-ttu-id="dc78e-108">A caixa de diálogo **Selecionar Tipo de Medidor** é aberta.</span><span class="sxs-lookup"><span data-stu-id="dc78e-108">The **Select Gauge Type** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="dc78e-109">Selecione o tipo de medidor que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="dc78e-109">Select the type of gauge you want to add.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc78e-110">Diferentemente do Gráfico, o Medidor tem apenas dois tipos: linear e radial.</span><span class="sxs-lookup"><span data-stu-id="dc78e-110">Unlike Chart, Gauge has only two types: linear and radial.</span></span> <span data-ttu-id="dc78e-111">Os medidores disponíveis na caixa de diálogo **Selecionar um Tipo de Medidor** são modelos para esses dois tipos de medidores.</span><span class="sxs-lookup"><span data-stu-id="dc78e-111">The available gauges in the **Select a Gauge Type** dialog box are templates for these two types of gauges.</span></span> <span data-ttu-id="dc78e-112">Por isso, você não pode alterar o tipo de medidor após adicionar o medidor ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="dc78e-112">For this reason, you cannot change the gauge type after you add the gauge to your report.</span></span> <span data-ttu-id="dc78e-113">Você deverá excluir e adicionar novamente um medidor para alterar seu tipo.</span><span class="sxs-lookup"><span data-stu-id="dc78e-113">You must delete and re-add a gauge to change its type.</span></span>  
  
     <span data-ttu-id="dc78e-114">Se o relatório não tiver nenhuma fonte de dados, nem conjunto de dados, a caixa de diálogo **Propriedades da Fonte de Dados** será aberta e o orientará durante as etapas para criar esses dois itens.</span><span class="sxs-lookup"><span data-stu-id="dc78e-114">If the report has no data source and dataset the **Data Source Properties** dialog box opens and takes you through the steps to create both.</span></span> <span data-ttu-id="dc78e-115">Para obter mais informações, consulte [Adicionar e verificar uma conexão de dados ou uma fonte de dados &#40;Construtor de relatórios e SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc78e-115">For more information see, [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="dc78e-116">Se o relatório tiver uma fonte de dados, e nenhum conjunto de dados, a caixa de diálogo **Propriedades do Conjunto de Dados** será aberta e o orientará durante as etapas para criar um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="dc78e-116">If the report has a data source, but no dataset the **Dataset Properties** dialog box opens and takes you through the steps to create one.</span></span> <span data-ttu-id="dc78e-117">Para obter mais informações, consulte [Criar um conjunto de dados compartilhado ou um conjunto de dados inserido &#40;Construtor de Relatórios e SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc78e-117">For more information, see [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="dc78e-118">Clique no medidor para exibir o painel de dados.</span><span class="sxs-lookup"><span data-stu-id="dc78e-118">Click the gauge to display the data pane.</span></span> <span data-ttu-id="dc78e-119">Por padrão, um medidor tem um ponteiro correspondente a um valor.</span><span class="sxs-lookup"><span data-stu-id="dc78e-119">By default, a gauge has one pointer corresponding to one value.</span></span> <span data-ttu-id="dc78e-120">Você também pode adicionar outros ponteiros.</span><span class="sxs-lookup"><span data-stu-id="dc78e-120">You can add additional pointers.</span></span>  
  
5.  <span data-ttu-id="dc78e-121">Adicione um campo do conjunto de dados à zona para arrastar e soltar do campo de dados.</span><span class="sxs-lookup"><span data-stu-id="dc78e-121">Add one field from the dataset to the data field drop-zone.</span></span> <span data-ttu-id="dc78e-122">Você pode adicionar somente um campo.</span><span class="sxs-lookup"><span data-stu-id="dc78e-122">You can add only one field.</span></span> <span data-ttu-id="dc78e-123">Para exibir vários campos, é necessário adicionar mais ponteiros, um para cada campo.</span><span class="sxs-lookup"><span data-stu-id="dc78e-123">If you want to display multiple fields, you must add additional pointers, one for each field.</span></span>  
  
     <span data-ttu-id="dc78e-124">Clique com o botão direito do mouse na escala do medidor e selecione **Propriedades da Escala**.</span><span class="sxs-lookup"><span data-stu-id="dc78e-124">Right-click the gauge scale, and select **Scale Properties**.</span></span> <span data-ttu-id="dc78e-125">Digite um valor para **Mínimo** e **Máximo** da escala.</span><span class="sxs-lookup"><span data-stu-id="dc78e-125">Type a value for the **Minimum** and **Maximum** of the scale.</span></span> <span data-ttu-id="dc78e-126">Para obter mais informações, consulte [Definir mínimo ou máximo em um medidor &#40;Construtor de Relatórios e SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc78e-126">For more information, see [Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc78e-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc78e-127">See Also</span></span>  
 <span data-ttu-id="dc78e-128">[Regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc78e-128">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dc78e-129">Medidores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc78e-129">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
