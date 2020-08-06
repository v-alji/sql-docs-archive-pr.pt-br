---
title: Definir opções de conversão de moeda (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.calculationsettings.f1
ms.assetid: a49d4e1f-bdda-4a83-ab4f-ce8c500e1d6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61877deb0bc422d65f977e3fc9de3e678f7d8477
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683723"
---
# <a name="set-currency-conversion-options-business-intelligence-wizard"></a><span data-ttu-id="f9f06-102">Definir Opções de Conversão de Moeda (Assistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="f9f06-102">Set Currency Conversion Options (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="f9f06-103">Use a página **Definir Opções de Conversão de Moeda** para definir cálculos de conversão de moeda para um grupo de medidas que contém taxas de câmbio.</span><span class="sxs-lookup"><span data-stu-id="f9f06-103">Use the **Set Currency Conversion** page to define currency conversion calculations for a measure group that contains exchange rates.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9f06-104">Essa página não será exibida se o Assistente de Business Intelligence tiver sido iniciado no Designer de Dimensão ou clicando com o botão direito do mouse em uma dimensão no Gerenciador de Soluções no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9f06-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="f9f06-105">Opções</span><span class="sxs-lookup"><span data-stu-id="f9f06-105">Options</span></span>  
 <span data-ttu-id="f9f06-106">**Selecione o grupo de medidas que contém taxas de câmbio**</span><span class="sxs-lookup"><span data-stu-id="f9f06-106">**Select the measure group that contains exchange rates**</span></span>  
 <span data-ttu-id="f9f06-107">Selecione o grupo de medidas que contém as taxas de câmbio que os cálculos de conversão de moeda devem consultar.</span><span class="sxs-lookup"><span data-stu-id="f9f06-107">Select the measure group that contains the exchange rates that the currency conversion calculations should reference.</span></span>  
  
 <span data-ttu-id="f9f06-108">**Especifique a moeda corrente**</span><span class="sxs-lookup"><span data-stu-id="f9f06-108">**Specify the pivot currency**</span></span>  
 <span data-ttu-id="f9f06-109">Selecione o membro que funciona como a moeda corrente para o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="f9f06-109">Select the member that serves as the pivot currency for the measure group.</span></span>  
  
 <span data-ttu-id="f9f06-110">**Selecione como você inseriu suas taxas de câmbio (selecione uma moeda de exemplo)**</span><span class="sxs-lookup"><span data-stu-id="f9f06-110">**Select how you entered your exchange rates (select a sample currency)**</span></span>  
 <span data-ttu-id="f9f06-111">Selecione um membro que represente uma moeda de exemplo da dimensão de moedas para alterar o texto das opções X moeda corrente por 1 moeda de exemplo e X moeda de exemplo por 1 moeda corrente para exibir a direção da taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="f9f06-111">Select a member representing a sample currency from the currency dimension to change the text for the X pivot currency per 1 sample currency and X sample currency per 1 pivot currency options to better display the exchange rate direction.</span></span>  
  
 <span data-ttu-id="f9f06-112">**X moeda corrente por 1 moeda de exemplo**</span><span class="sxs-lookup"><span data-stu-id="f9f06-112">**X pivot currency per 1 sample currency**</span></span>  
 <span data-ttu-id="f9f06-113">Selecione para indicar que as taxas de câmbio no grupo de medidas de taxa representam um multiplicador para a moeda corrente especificada.</span><span class="sxs-lookup"><span data-stu-id="f9f06-113">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified pivot currency.</span></span>  
  
 <span data-ttu-id="f9f06-114">**X moeda de exemplo por 1 moeda corrente**</span><span class="sxs-lookup"><span data-stu-id="f9f06-114">**X sample currency per 1 pivot currency**</span></span>  
 <span data-ttu-id="f9f06-115">Selecione para indicar que as taxas de câmbio no grupo de medidas de taxa representam um multiplicador para a moeda de exemplo especificada.</span><span class="sxs-lookup"><span data-stu-id="f9f06-115">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified sample currency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f06-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9f06-116">See Also</span></span>  
 <span data-ttu-id="f9f06-117">[Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f9f06-117">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="f9f06-118">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f9f06-118">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f9f06-119">O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="f9f06-119">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
