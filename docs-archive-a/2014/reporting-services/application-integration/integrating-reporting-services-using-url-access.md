---
title: Integrando o Reporting Services usando o acesso à URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- URL access [Reporting Services], about URL access
- integrating reports [Reporting Services]
ms.assetid: f1014f7d-fafa-4aa8-8bd2-5bdba835d9b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fedf4ce3011d9caae9d673acf354265537115057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682178"
---
# <a name="integrating-reporting-services-using-url-access"></a><span data-ttu-id="35536-102">Integrando o Reporting Services por meio do acesso à URL</span><span class="sxs-lookup"><span data-stu-id="35536-102">Integrating Reporting Services Using URL Access</span></span>
  <span data-ttu-id="35536-103">Com o acesso de URL, você acessa relatórios por uma URL do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="35536-103">With URL access, you access reports through a report server URL.</span></span> <span data-ttu-id="35536-104">Uma solicitação de URL permite que você acesse um servidor de relatório específico bem como relatórios, recursos e outros itens no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="35536-104">A URL request enables you to access a specific report server as well as the reports, resources, and other items in the report server database.</span></span> <span data-ttu-id="35536-105">Você também pode personalizar a exibição de relatório e a experiência de navegação por seus usuários.</span><span class="sxs-lookup"><span data-stu-id="35536-105">You can also customize the report viewing and navigation experience for your users.</span></span> <span data-ttu-id="35536-106">A cadeia de caracteres da consulta do URL contém configurações de informações de dispositivo, como também parâmetros de relatório destinados a seu relatório e à saída de renderização escolhida.</span><span class="sxs-lookup"><span data-stu-id="35536-106">The query string of the URL contains device information settings, as well as report parameters targeted at your report and the chosen rendering output.</span></span> <span data-ttu-id="35536-107">A forma que o servidor de relatório trata das solicitações de URL dependerá dos parâmetros, prefixos de parâmetro e tipo de item que você está acessando por meio da URL.</span><span class="sxs-lookup"><span data-stu-id="35536-107">The way the report server handles URL requests depends on the parameters, parameter prefixes, and type of item that you are accessing through the URL.</span></span>  
  
 <span data-ttu-id="35536-108">Você pode usar o acesso de URL para inserir hiperlinks em relatórios e outros itens do servidor de relatório nos aplicativos que você desenvolve, se estiver em um ambiente Windows ou Web.</span><span class="sxs-lookup"><span data-stu-id="35536-108">You can use URL access to embed hyperlinks to reports and other report server items in the applications that you develop, whether in a Windows or Web environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35536-109">Os tópicos da seção fornecem algumas ideias básicas para integração.</span><span class="sxs-lookup"><span data-stu-id="35536-109">The topics in the section provide you with some basic ideas for integration.</span></span> <span data-ttu-id="35536-110">É possível usar as informações para começar a criar e desenvolver seus próprios cenários de integração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35536-110">You can use the information to begin to design and develop your own [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integration scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35536-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="35536-111">In This Section</span></span>  
 [<span data-ttu-id="35536-112">Usando o acesso à URL em um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="35536-112">Using URL Access in a Web Application</span></span>](integrating-reporting-services-using-url-access-web-application.md)  
 <span data-ttu-id="35536-113">Descreve como usar o acesso de URL para integrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em um ambiente de Web.</span><span class="sxs-lookup"><span data-stu-id="35536-113">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
 [<span data-ttu-id="35536-114">Usando o acesso à URL em um aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="35536-114">Using URL Access in a Windows Application</span></span>](integrating-reporting-services-using-url-access-windows-application.md)  
 <span data-ttu-id="35536-115">Descreve como usar o acesso de URL para integrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em um ambiente do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="35536-115">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35536-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35536-116">See Also</span></span>  
 <span data-ttu-id="35536-117">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="35536-117">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="35536-118">Acesso à URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="35536-118">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
