---
title: Configurações de informações de dispositivo ATOM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573821"
---
# <a name="atom-device-information-settings"></a><span data-ttu-id="b1579-102">Configurações de informações do dispositivo ATOM</span><span class="sxs-lookup"><span data-stu-id="b1579-102">ATOM Device Information Settings</span></span>
  <span data-ttu-id="b1579-103">As configurações das informações de dispositivo para a extensão de renderização Atom dão suporte ao envio do nome de um feed Atom e de uma codificação de caracteres a ser usada.</span><span class="sxs-lookup"><span data-stu-id="b1579-103">The device information settings for the Atom rendering extension support submittal of the name of an Atom feed and character encoding to use.</span></span>  
  
 <span data-ttu-id="b1579-104">A tabela a seguir lista as configurações de informações de dispositivo para renderização para um documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="b1579-104">The following table lists the device information settings for rendering to a data service document.</span></span>  
  
|<span data-ttu-id="b1579-105">Configuração</span><span class="sxs-lookup"><span data-stu-id="b1579-105">Setting</span></span>|<span data-ttu-id="b1579-106">Valor</span><span class="sxs-lookup"><span data-stu-id="b1579-106">Value</span></span>|  
|-------------|-----------|  
|`DataFeed`|<span data-ttu-id="b1579-107">Se for especificado, renderiza o feed Atom que corresponde ao nome do feed fornecido nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="b1579-107">If specified, renders the Atom feed corresponding to the feed name provided in this setting.</span></span> <span data-ttu-id="b1579-108">Se não, renderiza o documento do serviço Atom para o relatório.</span><span class="sxs-lookup"><span data-stu-id="b1579-108">If not, renders the Atom service document for the report.</span></span> <span data-ttu-id="b1579-109">O identificador exclusivo gerado automaticamente do feed de dados.</span><span class="sxs-lookup"><span data-stu-id="b1579-109">The unique auto-generated identifier of the data feed.</span></span> <span data-ttu-id="b1579-110">Este valor é usado internamente e você não deve alterar isto.</span><span class="sxs-lookup"><span data-stu-id="b1579-110">This  value is used internally and you should not change it.</span></span>|  
|<span data-ttu-id="b1579-111">**Codificação**</span><span class="sxs-lookup"><span data-stu-id="b1579-111">**Encoding**</span></span>|<span data-ttu-id="b1579-112">O nome da IANA (Internet Assigned Numbers Authority) de uma codificação de caracteres com suporte do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1579-112">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="b1579-113">O valor padrão é `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="b1579-113">The default value is `UTF-8`.</span></span> <span data-ttu-id="b1579-114">Exemplos de outros valores incluem ASCII, UTF-7 e UTF-16.</span><span class="sxs-lookup"><span data-stu-id="b1579-114">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1579-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1579-115">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="b1579-116">[Passando configurações de informações de dispositivo para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b1579-116">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="b1579-117">[Personalizar parâmetros de extensão de renderização no RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="b1579-117">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="b1579-118">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b1579-118">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
