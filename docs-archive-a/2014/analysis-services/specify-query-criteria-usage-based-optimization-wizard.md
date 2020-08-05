---
title: Especificar critérios de consulta (Assistente de otimização com base no uso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.specifyquerycriteria.f1
ms.assetid: 3193adc2-af9f-4234-a4cc-dea0c280a724
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3b93034a089ff3121155e35de4cec96846824a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571622"
---
# <a name="specify-query-criteria-usage-based-optimization-wizard"></a><span data-ttu-id="d4ed6-102">Especificar Critérios de Consulta (Assistente de Otimização com Base no Uso)</span><span class="sxs-lookup"><span data-stu-id="d4ed6-102">Specify Query Criteria (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="d4ed6-103">Use a página **Especificar Critérios de Consulta** para escolher uma ou mais opções de filtro para identificar as consultas a serem otimizadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-103">Use the **Specify Query Criteria** page to choose one or more filter options in order to identify queries to optimize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4ed6-104">Essa página será desabilitada se o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] não puder se conectar com o log de consultas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-104">This page is disabled if [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot connect to the query log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4ed6-105">Opções</span><span class="sxs-lookup"><span data-stu-id="d4ed6-105">Options</span></span>  
 <span data-ttu-id="d4ed6-106">**Estatísticas de log de consultas**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-106">**Query log statistics**</span></span>  
 <span data-ttu-id="d4ed6-107">Exibe informações sobre as consultas armazenadas no log de consultas das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-107">Displays information about the queries stored in the query log for the selected partitions.</span></span> <span data-ttu-id="d4ed6-108">Os seguintes itens são exibidos:</span><span class="sxs-lookup"><span data-stu-id="d4ed6-108">The following items are displayed:</span></span>  
  
|<span data-ttu-id="d4ed6-109">Termo</span><span class="sxs-lookup"><span data-stu-id="d4ed6-109">Term</span></span>|<span data-ttu-id="d4ed6-110">Definição</span><span class="sxs-lookup"><span data-stu-id="d4ed6-110">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d4ed6-111">**Total de consultas**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-111">**Total queries**</span></span>|<span data-ttu-id="d4ed6-112">Exibe o número total de consultas armazenadas no log de consultas das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-112">Displays the total number of queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="d4ed6-113">**Consultas distintas**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-113">**Distinct queries**</span></span>|<span data-ttu-id="d4ed6-114">Exibe o número de consultas distintas armazenadas no log de consultas das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-114">Displays the number of distinct queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="d4ed6-115">**Usuários distintos**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-115">**Distinct users**</span></span>|<span data-ttu-id="d4ed6-116">Exibe o número total de usuários distintos associados às consultas armazenadas no log de consultas das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-116">Displays the total number of distinct users associated with queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="d4ed6-117">**Tempo médio de resposta**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-117">**Average response time**</span></span>|<span data-ttu-id="d4ed6-118">Exibe o tempo médio de resposta das consultas armazenadas no log de consultas das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-118">Displays the average response time for queries stored in the query log for the selected partitions.</span></span>|  
  
 <span data-ttu-id="d4ed6-119">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-119">**Beginning date**</span></span>  
 <span data-ttu-id="d4ed6-120">Filtra consultas no log de consultas com base em uma data e hora de início.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-120">Filters queries in the query log based on a starting date and time.</span></span> <span data-ttu-id="d4ed6-121">Escolha ou digite uma data na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-121">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4ed6-122"> Se a **Data de término** não for selecionada, todas as consultas no log de consultas na data e hora especificadas ou para essa opção ou posteriores serão consideradas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-122">If **Ending date** is not selected, all queries in the query log on or after the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="d4ed6-123">**Data de término date**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-123">**Ending date**</span></span>  
 <span data-ttu-id="d4ed6-124">Filtra consultas no log de consultas com base em uma data e hora de término.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-124">Filters queries in the query log based on an ending date and time.</span></span> <span data-ttu-id="d4ed6-125">Escolha ou digite uma data na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-125">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4ed6-126"> Se a **Data de início** não for selecionada, todas as consultas no log de consultas antes ou na data e hora especificadas para essa opção serão consideradas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-126">If **Beginning date** is not selected, all queries in the query log on or before the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="d4ed6-127">**Usuários**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-127">**Users**</span></span>  
 <span data-ttu-id="d4ed6-128">Filtra consultas no log de consultas com base em um conjunto de usuários especificado.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-128">Filters queries in the query log based on a specified set of users.</span></span> <span data-ttu-id="d4ed6-129">Clique no botão de reticências (**...**) para exibir a caixa de diálogo **Seleção de Usuários** e escolher os usuários nos quais filtrar consultas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-129">Click the ellipsis (**...**) button to display the **User Selection** dialog box and choose users on which to filter queries.</span></span> <span data-ttu-id="d4ed6-130">Para obter mais informações sobre a caixa de diálogo **Seleção de Usuários**, consulte [Caixa de diálogo Seleção de Usuários &#40;Analysis Services – Dados Multidimensionais&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d4ed6-130">For more information about the **User Selection** dialog box, see [User Selection Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="d4ed6-131">**Consultas mais frequentes**</span><span class="sxs-lookup"><span data-stu-id="d4ed6-131">**Most frequent queries**</span></span>  
 <span data-ttu-id="d4ed6-132">Filtra consultas no log de consultas com base na porcentagem mais alta de consultas distintas executadas com maior frequência para as partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-132">Filters queries in the query log based on the topmost percentage of the distinct queries most often run for the selected partitions.</span></span> <span data-ttu-id="d4ed6-133">Escolha ou digite um valor percentual na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="d4ed6-133">Choose or type a percent value in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ed6-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4ed6-134">See Also</span></span>  
 <span data-ttu-id="d4ed6-135">[Ajuda F1 do assistente de otimização com base no uso](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d4ed6-135">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="d4ed6-136">Analysis Services assistentes &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ed6-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
