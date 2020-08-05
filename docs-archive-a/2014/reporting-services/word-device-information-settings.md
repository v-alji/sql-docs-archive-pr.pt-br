---
title: Configurações de informações de dispositivo do Word | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Word [Reporting Services]
- device information settings [Reporting Services], Word
ms.assetid: 28146498-fae7-4b13-b47f-6ec05aa8e057
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ddd145c5073003a8dc189e3ed9b1bbb25dc11d09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569060"
---
# <a name="word-device-information-settings"></a><span data-ttu-id="986ce-102">Configurações de informações de dispositivo do Word</span><span class="sxs-lookup"><span data-stu-id="986ce-102">Word Device Information Settings</span></span>
  <span data-ttu-id="986ce-103">A tabela a seguir lista as configurações de informações de dispositivo para renderização no formato [!INCLUDE[ofprword](../includes/ofprword-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="986ce-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprword](../includes/ofprword-md.md)] format.</span></span>  
  
|<span data-ttu-id="986ce-104">Configuração</span><span class="sxs-lookup"><span data-stu-id="986ce-104">Setting</span></span>|<span data-ttu-id="986ce-105">Valor</span><span class="sxs-lookup"><span data-stu-id="986ce-105">Value</span></span>|  
|-------------|-----------|  
|`AutoFit`|<span data-ttu-id="986ce-106">`False`.</span><span class="sxs-lookup"><span data-stu-id="986ce-106">`False`.</span></span> <span data-ttu-id="986ce-107">O AutoAjuste é definido como `false` em qualquer tabela do Word.</span><span class="sxs-lookup"><span data-stu-id="986ce-107">AutoFit is set to `false` set on any Word table.</span></span><br /><br /> <span data-ttu-id="986ce-108">`True`.</span><span class="sxs-lookup"><span data-stu-id="986ce-108">`True`.</span></span> <span data-ttu-id="986ce-109">O AutoAjuste é definido como `true` em todas as tabelas do Word.</span><span class="sxs-lookup"><span data-stu-id="986ce-109">AutoFit is set to `true` on every Word table.</span></span><br /><br /> <span data-ttu-id="986ce-110">`Never`.</span><span class="sxs-lookup"><span data-stu-id="986ce-110">`Never`.</span></span> <span data-ttu-id="986ce-111">Os valores do AutoAjuste não são definidos em qualquer tabela do Word e seu comportamento volta para o padrão do Word.</span><span class="sxs-lookup"><span data-stu-id="986ce-111">AutoFit values are not set on any Word table and behavior reverts to the Word default.</span></span><br /><br /> <span data-ttu-id="986ce-112">`Default`.</span><span class="sxs-lookup"><span data-stu-id="986ce-112">`Default`.</span></span> <span data-ttu-id="986ce-113">O AutoAjuste é definido em tabelas mais estreitas do que a área de desenho física (largura de página física excluindo as margens) por página lógica.</span><span class="sxs-lookup"><span data-stu-id="986ce-113">AutoFit is set on tables that are narrower than the physical drawing area (physical page width excluding margins) per logical page.</span></span>|  
|`ExpandToggles`|<span data-ttu-id="986ce-114">Indica se todos os itens que podem ser alternados deve ser renderizados em seu estado totalmente expandido.</span><span class="sxs-lookup"><span data-stu-id="986ce-114">Indicates whether all items that can be toggled should render in their fully-expanded state.</span></span> <span data-ttu-id="986ce-115">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="986ce-115">The default value is `false`.</span></span>|  
|`FixedPageWidth`|<span data-ttu-id="986ce-116">Indica se a Largura de Página escrita para o arquivo DOC crescerá para acomodar a largura da maior página do Corpo do Relatório.</span><span class="sxs-lookup"><span data-stu-id="986ce-116">Indicates whether the Page Width written to the DOC file will grow to accommodate the width of the largest page in the Report Body.</span></span> <span data-ttu-id="986ce-117">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="986ce-117">The default value is `false`.</span></span>|  
|<span data-ttu-id="986ce-118">**OmitHyperlinks**</span><span class="sxs-lookup"><span data-stu-id="986ce-118">**OmitHyperlinks**</span></span>|<span data-ttu-id="986ce-119">Indica se a ação Hiperlink deverá ser omitida em todos os itens onde for definida.</span><span class="sxs-lookup"><span data-stu-id="986ce-119">Indicates whether to omit the Hyperlink action on all items where it is set.</span></span> <span data-ttu-id="986ce-120">O valor padrão é `false`</span><span class="sxs-lookup"><span data-stu-id="986ce-120">The default value is `false`</span></span>|  
|`OmitDrillthroughs`|<span data-ttu-id="986ce-121">Indica se a ação Drillthrough deverá ser omitida em todos os itens onde foi definida.</span><span class="sxs-lookup"><span data-stu-id="986ce-121">Indicates whether to omit the Drillthrough action on all items where it is set.</span></span> <span data-ttu-id="986ce-122">O valor padrão é `false`</span><span class="sxs-lookup"><span data-stu-id="986ce-122">The default value is `false`</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="986ce-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="986ce-123">See Also</span></span>  
 <span data-ttu-id="986ce-124">[Passando configurações de informações de dispositivo para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="986ce-124">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="986ce-125">[Personalizar parâmetros de extensão de renderização no RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="986ce-125">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="986ce-126">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="986ce-126">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
