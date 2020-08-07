---
title: Configurações de informações de dispositivo MHTML | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], MHTML rendering
- MHTML [Reporting Services]
ms.assetid: 60b85dd8-b4fb-4ad9-be6a-e7c89ac076fe
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 076a0179871775984799fc8ce5366a220f812867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576248"
---
# <a name="mhtml-device-information-settings"></a><span data-ttu-id="e22ce-102">Configurações das informações do dispositivo MHTML</span><span class="sxs-lookup"><span data-stu-id="e22ce-102">MHTML Device Information Settings</span></span>
  <span data-ttu-id="e22ce-103">A tabela a seguir lista as configurações de informações de dispositivo para a renderização de relatórios no arquivo da Web (MHTML).</span><span class="sxs-lookup"><span data-stu-id="e22ce-103">The following table lists the device information settings for rendering reports in Web archive (MHTML) format.</span></span>  
  
|<span data-ttu-id="e22ce-104">Configuração</span><span class="sxs-lookup"><span data-stu-id="e22ce-104">Setting</span></span>|<span data-ttu-id="e22ce-105">Valor</span><span class="sxs-lookup"><span data-stu-id="e22ce-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="e22ce-106">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="e22ce-106">**JavaScript**</span></span>|<span data-ttu-id="e22ce-107">Indica se JavaScript é compatível com o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="e22ce-107">Indicates whether JavaScript is supported in the rendered report.</span></span>|  
|<span data-ttu-id="e22ce-108">**OutlookCompat**</span><span class="sxs-lookup"><span data-stu-id="e22ce-108">**OutlookCompat**</span></span>|<span data-ttu-id="e22ce-109">Indica se ocorrerá renderização com metadados extras que melhoram a aparência do relatório no Outlook.</span><span class="sxs-lookup"><span data-stu-id="e22ce-109">Indicates whether to render with extra metadata that makes the report look better in Outlook.</span></span> <span data-ttu-id="e22ce-110">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="e22ce-110">The default value is `true`.</span></span>|  
|<span data-ttu-id="e22ce-111">**Fragmento de MHTML**</span><span class="sxs-lookup"><span data-stu-id="e22ce-111">**MHTML Fragment**</span></span>|<span data-ttu-id="e22ce-112">Indica se um fragmento de MHTML é criado no lugar de um documento MHTML completo.</span><span class="sxs-lookup"><span data-stu-id="e22ce-112">Indicates whether an MHTML fragment is created in place of a full MHTML document.</span></span> <span data-ttu-id="e22ce-113">Um fragmento de MHTML inclui o conteúdo do relatório em um elemento TABLE e omite os elementos HTML e BODY.</span><span class="sxs-lookup"><span data-stu-id="e22ce-113">An MHTML fragment includes the report content in a TABLE element and omits the HTML and BODY elements.</span></span> <span data-ttu-id="e22ce-114">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="e22ce-114">The default value is `false`.</span></span>|  
|<span data-ttu-id="e22ce-115">**DataVisualizationFitSizing**</span><span class="sxs-lookup"><span data-stu-id="e22ce-115">**DataVisualizationFitSizing**</span></span>|<span data-ttu-id="e22ce-116">Indica comportamento de ajuste de visualização de dados quando dentro de um tablix.</span><span class="sxs-lookup"><span data-stu-id="e22ce-116">Indicates data visualization fit behavior when inside a tablix.</span></span> <span data-ttu-id="e22ce-117">Isso inclui gráfico, medidor e mapa.</span><span class="sxs-lookup"><span data-stu-id="e22ce-117">This includes chart, gauge, and map.</span></span><br /><br /> <span data-ttu-id="e22ce-118">Os valores possíveis são **Aproximado** e **Exato**.</span><span class="sxs-lookup"><span data-stu-id="e22ce-118">The possible values are **Approximate** and **Exact**.</span></span><br /><br /> <span data-ttu-id="e22ce-119">O valor padrão é **Aproximado**.</span><span class="sxs-lookup"><span data-stu-id="e22ce-119">The default value is **Approximate**.</span></span> <span data-ttu-id="e22ce-120">Se a configuração for removida do arquivo **rsreportserver.config** , o comportamento padrão será **Exato**.</span><span class="sxs-lookup"><span data-stu-id="e22ce-120">If the setting is removed from the **rsreportserver.config** file then the default behavior is **Exact**.</span></span><br /><br /> <span data-ttu-id="e22ce-121">Habilitar **Exato** pode ter impacto de desempenho porque o processamento para determinar o tamanho exato pode levar mais tempo.</span><span class="sxs-lookup"><span data-stu-id="e22ce-121">Enabling **Exact** may have performance impact because the processing to determine the exact size may take longer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e22ce-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e22ce-122">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="e22ce-123">[Passando configurações de informações de dispositivos para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="e22ce-123">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="e22ce-124">[Personalizar parâmetros de extensão de renderização em RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="e22ce-124">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="e22ce-125">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e22ce-125">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
