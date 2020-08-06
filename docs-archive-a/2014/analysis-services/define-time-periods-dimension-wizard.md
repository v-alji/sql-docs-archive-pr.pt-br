---
title: Definir períodos de tempo (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.timefrequency.f1
ms.assetid: 6bda6b7e-d306-4e68-9acb-84de8f44d1b4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88b69eaa265b7a98f7d32063b602897d02016fa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582676"
---
# <a name="define-time-periods-dimension-wizard"></a><span data-ttu-id="7da78-102">Definir Períodos de Tempo (Assistente para Dimensões)</span><span class="sxs-lookup"><span data-stu-id="7da78-102">Define Time Periods (Dimension Wizard)</span></span>
  <span data-ttu-id="7da78-103">Use a página **Definir Períodos de Tempo** para definir as informações do ano civil e as frequências de tempo a serem incluídas na dimensão de tempo ou na dimensão de tempo do servidor.</span><span class="sxs-lookup"><span data-stu-id="7da78-103">Use the **Define Time Periods** page to define the calendar year information and time frequencies to include in the time dimension or server time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7da78-104"> Essa página será exibida apenas se você tiver selecionado **Dimensão de tempo de servidor** na página **Selecionar o Tipo de Dimensão** ou se você tiver selecionado **Criar a dimensão sem usar uma fonte de dados** na página **Selecionar Método de Criação** e **Dimensão de tempo** na página **Selecionar o tipo de dimensão** .</span><span class="sxs-lookup"><span data-stu-id="7da78-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Select Build Method** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7da78-105">Nessa página é possível definir o ano civil de uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="7da78-105">This page is for defining the calendar year of a time dimension.</span></span> <span data-ttu-id="7da78-106">Para definir um ano fiscal, de fabricação, de relatório, ou ISO 8601 para a dimensão de tempo, use a página **Selecionar Calendários** .</span><span class="sxs-lookup"><span data-stu-id="7da78-106">To define a fiscal, manufacturing, reporting, or International Standards Organization (ISO) 8601 year for the time dimension, use the **Select Calendars** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7da78-107">Opções</span><span class="sxs-lookup"><span data-stu-id="7da78-107">Options</span></span>  
 <span data-ttu-id="7da78-108">**Primeiro dia do calendário**</span><span class="sxs-lookup"><span data-stu-id="7da78-108">**First calendar day**</span></span>  
 <span data-ttu-id="7da78-109">Digite ou selecione o dia que inicia o ano atual.</span><span class="sxs-lookup"><span data-stu-id="7da78-109">Type or select the day that begins the current year.</span></span>  
  
 <span data-ttu-id="7da78-110">**Último dia do calendário**</span><span class="sxs-lookup"><span data-stu-id="7da78-110">**Last calendar day**</span></span>  
 <span data-ttu-id="7da78-111">Digite ou selecione o dia que encerra o ano atual.</span><span class="sxs-lookup"><span data-stu-id="7da78-111">Type or select the day that ends the current year.</span></span>  
  
 <span data-ttu-id="7da78-112">**Primeiro dia da semana**</span><span class="sxs-lookup"><span data-stu-id="7da78-112">**First day of the week**</span></span>  
 <span data-ttu-id="7da78-113">Selecione o dia que inicia uma semana.</span><span class="sxs-lookup"><span data-stu-id="7da78-113">Select the day that begins a week.</span></span>  
  
 <span data-ttu-id="7da78-114">**Períodos de tempo**</span><span class="sxs-lookup"><span data-stu-id="7da78-114">**Time periods**</span></span>  
 <span data-ttu-id="7da78-115">Selecione os períodos de tempo do ano civil da dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="7da78-115">Select the time periods for the calendar year of the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7da78-116">O período de tempo `Date` é necessário.</span><span class="sxs-lookup"><span data-stu-id="7da78-116">The `Date` time period is required.</span></span>  
  
 <span data-ttu-id="7da78-117">**Idioma dos nomes de membros de tempo**</span><span class="sxs-lookup"><span data-stu-id="7da78-117">**Language for time member names**</span></span>  
 <span data-ttu-id="7da78-118">Selecione o idioma dos membros da dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="7da78-118">Select the language for the members in the time dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da78-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7da78-119">See Also</span></span>  
 <span data-ttu-id="7da78-120">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7da78-120">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="7da78-121">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7da78-121">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7da78-122">[Dimensões em modelos multidimensionais](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="7da78-122">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="7da78-123">Selecionar calendários &#40;assistente de dimensão&#41;</span><span class="sxs-lookup"><span data-stu-id="7da78-123">Select Calendars &#40;Dimension Wizard&#41;</span></span>](select-calendars-dimension-wizard.md)  
  
  
