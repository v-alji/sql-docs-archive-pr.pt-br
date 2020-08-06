---
title: Configurações de informações de dispositivo Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682141"
---
# <a name="excel-device-information-settings"></a><span data-ttu-id="4bc40-102">Configurações das informações do dispositivo do Excel</span><span class="sxs-lookup"><span data-stu-id="4bc40-102">Excel Device Information Settings</span></span>
  <span data-ttu-id="4bc40-103">A tabela a seguir lista as configurações de informações de dispositivo para renderização no formato [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bc40-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] format.</span></span>  
  
|<span data-ttu-id="4bc40-104">Configuração</span><span class="sxs-lookup"><span data-stu-id="4bc40-104">Setting</span></span>|<span data-ttu-id="4bc40-105">Valor</span><span class="sxs-lookup"><span data-stu-id="4bc40-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="4bc40-106">**OmitDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="4bc40-106">**OmitDocumentMap**</span></span>|<span data-ttu-id="4bc40-107">Indica se será preciso omitir o mapa do documento para relatórios que dão suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="4bc40-107">Indicates whether to omit the document map for reports that support it.</span></span> <span data-ttu-id="4bc40-108">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="4bc40-108">The default value is `false`.</span></span>|  
|<span data-ttu-id="4bc40-109">**OmitFormulas**</span><span class="sxs-lookup"><span data-stu-id="4bc40-109">**OmitFormulas**</span></span>|<span data-ttu-id="4bc40-110">Indica se será preciso omitir fórmulas a partir do relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="4bc40-110">Indicates whether to omit formulas from the rendered report.</span></span> <span data-ttu-id="4bc40-111">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="4bc40-111">The default value is `false`.</span></span>|  
|<span data-ttu-id="4bc40-112">`SimplePageHeade`rs</span><span class="sxs-lookup"><span data-stu-id="4bc40-112">`SimplePageHeade`rs</span></span>|<span data-ttu-id="4bc40-113">Indica se o cabeçalho de página do relatório será renderizado para o cabeçalho de página do Excel.</span><span class="sxs-lookup"><span data-stu-id="4bc40-113">Indicates whether the page header of the report is rendered to the Excel page header.</span></span> <span data-ttu-id="4bc40-114">Um valor `false` indica que o cabeçalho de página será renderizado para a primeira linha da planilha.</span><span class="sxs-lookup"><span data-stu-id="4bc40-114">A value of `false` indicates that the page header is rendered to the first row of the worksheet.</span></span> <span data-ttu-id="4bc40-115">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="4bc40-115">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bc40-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bc40-116">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="4bc40-117">[Passando configurações de informações de dispositivo para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="4bc40-117">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="4bc40-118">[Personalizar parâmetros de extensão de renderização no RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="4bc40-118">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="4bc40-119">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc40-119">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
