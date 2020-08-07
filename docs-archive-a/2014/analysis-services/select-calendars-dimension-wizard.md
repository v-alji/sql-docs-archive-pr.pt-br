---
title: Selecionar calendários (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.serverSpecialCalendars.f1
ms.assetid: 6e28a020-2586-4b13-9333-b499fb1b33af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2048ee20dd91c942f01982d02f3265a6bad670dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574926"
---
# <a name="select-calendars-dimension-wizard"></a><span data-ttu-id="2bff3-102">Selecionar Calendários (Assistente para Dimensões)</span><span class="sxs-lookup"><span data-stu-id="2bff3-102">Select Calendars (Dimension Wizard)</span></span>
  <span data-ttu-id="2bff3-103">Use a página **Selecionar Calendários** para criar hierarquias adicionais representando calendários fiscais, de relatório, de fabricação ou ISO 8601 para a dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="2bff3-103">Use the **Select Calendars** page to create additional hierarchies representing fiscal, reporting, manufacturing, or International Standards Organization (ISO) 8601 calendars for the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-104"> Essa página será exibida apenas se você tiver selecionado **Dimensão de tempo de servidor** na página **Selecionar o Tipo de Dimensão** ou se você tiver selecionado **Criar a dimensão sem usar uma fonte de dados** na página **Definição de Dimensão** e **Dimensão de tempo** na página **Selecionar o tipo de dimensão** .</span><span class="sxs-lookup"><span data-stu-id="2bff3-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Dimension Definition** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2bff3-105">Opções</span><span class="sxs-lookup"><span data-stu-id="2bff3-105">Options</span></span>  
 <span data-ttu-id="2bff3-106">**Calendário fiscal**</span><span class="sxs-lookup"><span data-stu-id="2bff3-106">**Fiscal calendar**</span></span>  
 <span data-ttu-id="2bff3-107">Selecione para criar uma hierarquia de tempo baseada em um calendário fiscal.</span><span class="sxs-lookup"><span data-stu-id="2bff3-107">Select to create a time hierarchy based on a fiscal calendar.</span></span>  
  
 <span data-ttu-id="2bff3-108">**Dia e mês de início**</span><span class="sxs-lookup"><span data-stu-id="2bff3-108">**Start day and month**</span></span>  
 <span data-ttu-id="2bff3-109">Selecione o dia e o mês em que o calendário fiscal é iniciado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-109">Select the day and month on which the fiscal calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-110"> Essa opção está disponível apenas quando **Calendário fiscal** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-110">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="2bff3-111">**Convenção de nomenclatura do calendário fiscal**</span><span class="sxs-lookup"><span data-stu-id="2bff3-111">**Fiscal calendar naming convention**</span></span>  
 <span data-ttu-id="2bff3-112">Selecione a convenção de nomenclatura usada pelo calendário fiscal.</span><span class="sxs-lookup"><span data-stu-id="2bff3-112">Select the naming convention used by the fiscal calendar.</span></span> <span data-ttu-id="2bff3-113">Selecione **Nome do ano civil** ou **Nome do ano civil +1**.</span><span class="sxs-lookup"><span data-stu-id="2bff3-113">Select either **Calendar year name** or **Calendar year name +1**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-114"> Essa opção está disponível apenas quando **Calendário fiscal** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-114">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="2bff3-115">**Calendário de relatório (ou marketing)**</span><span class="sxs-lookup"><span data-stu-id="2bff3-115">**Reporting (or marketing) calendar**</span></span>  
 <span data-ttu-id="2bff3-116">Selecione para criar uma hierarquia de tempo baseada em um calendário de relatório.</span><span class="sxs-lookup"><span data-stu-id="2bff3-116">Select to create a time hierarchy based on a reporting calendar.</span></span>  
  
 <span data-ttu-id="2bff3-117">**Semana e mês de início**</span><span class="sxs-lookup"><span data-stu-id="2bff3-117">**Start week and month**</span></span>  
 <span data-ttu-id="2bff3-118">Selecione a semana e o mês em que o calendário de relatório é iniciado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-118">Select the week and month on which the reporting calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-119">Essa opção está disponível quando **Calendário de relatório (ou marketing)** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-119">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="2bff3-120">**Semana por padrão mensal**</span><span class="sxs-lookup"><span data-stu-id="2bff3-120">**Week by month pattern**</span></span>  
 <span data-ttu-id="2bff3-121">Selecione a semana por padrão mensal usada pelo calendário de relatório.</span><span class="sxs-lookup"><span data-stu-id="2bff3-121">Select the week by month pattern used by the reporting calendar.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-122">Essa opção está disponível quando **Calendário de relatório (ou marketing)** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-122">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="2bff3-123">A tabela a seguir lista as opções disponíveis para a semana por padrão mensal.</span><span class="sxs-lookup"><span data-stu-id="2bff3-123">The following table lists the options available for the week by month pattern.</span></span>  
  
|<span data-ttu-id="2bff3-124">Valor</span><span class="sxs-lookup"><span data-stu-id="2bff3-124">Value</span></span>|<span data-ttu-id="2bff3-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="2bff3-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2bff3-126">**Semana 445**</span><span class="sxs-lookup"><span data-stu-id="2bff3-126">**Week 445**</span></span>|<span data-ttu-id="2bff3-127">O primeiro mês do trimestre tem 4 semanas, o segundo mês do trimestre tem 4 semanas e o terceiro mês do trimestre tem 5 semanas.</span><span class="sxs-lookup"><span data-stu-id="2bff3-127">The first month in the quarter has 4 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 5 weeks.</span></span>|  
|<span data-ttu-id="2bff3-128">**Semana 454**</span><span class="sxs-lookup"><span data-stu-id="2bff3-128">**Week 454**</span></span>|<span data-ttu-id="2bff3-129">O primeiro mês do trimestre tem 4 semanas, o segundo mês do trimestre tem 5 semanas e o terceiro mês do trimestre tem 4 semanas.</span><span class="sxs-lookup"><span data-stu-id="2bff3-129">The first month in the quarter has 4 weeks, the second month in the quarter has 5 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
|<span data-ttu-id="2bff3-130">**Semana 544**</span><span class="sxs-lookup"><span data-stu-id="2bff3-130">**Week 544**</span></span>|<span data-ttu-id="2bff3-131">O primeiro mês do trimestre tem 5 semanas, o segundo mês tem 4 semanas e o terceiro mês tem 4 semanas.</span><span class="sxs-lookup"><span data-stu-id="2bff3-131">The first month in the quarter has 5 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
  
 <span data-ttu-id="2bff3-132">**Calendário de produção**</span><span class="sxs-lookup"><span data-stu-id="2bff3-132">**Manufacturing calendar**</span></span>  
 <span data-ttu-id="2bff3-133">Selecione para criar uma hierarquia de tempo baseada em um calendário de produção.</span><span class="sxs-lookup"><span data-stu-id="2bff3-133">Select to create a time hierarchy based on a manufacturing calendar.</span></span>  
  
 <span data-ttu-id="2bff3-134">**Semana e mês de início**</span><span class="sxs-lookup"><span data-stu-id="2bff3-134">**Start week and month**</span></span>  
 <span data-ttu-id="2bff3-135">Selecione a semana e o mês em que o calendário de produção é iniciado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-135">Select the week and month on which the manufacturing calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-136"> Essa opção está disponível apenas quando **Calendário de produção** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-136">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="2bff3-137">**Trimestre com períodos extras**</span><span class="sxs-lookup"><span data-stu-id="2bff3-137">**Quarter with extra periods**</span></span>  
 <span data-ttu-id="2bff3-138">Selecione ou digite o trimestre que conterá os períodos extras.</span><span class="sxs-lookup"><span data-stu-id="2bff3-138">Select or type the quarter that will contain the extra periods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bff3-139"> Essa opção está disponível apenas quando **Calendário de produção** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bff3-139">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="2bff3-140">**Calendário ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="2bff3-140">**ISO 8601 calendar**</span></span>  
 <span data-ttu-id="2bff3-141">Selecione para criar uma hierarquia de tempo baseada no calendário ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="2bff3-141">Select to create a hierarchy based on the ISO 8601 calendar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bff3-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2bff3-142">See Also</span></span>  
 <span data-ttu-id="2bff3-143">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="2bff3-143">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="2bff3-144">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2bff3-144">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2bff3-145">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="2bff3-145">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
