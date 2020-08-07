---
title: Preparando a implementação de uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bbf98286e6ed35542d8117b4b87b5ff3425def69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584030"
---
# <a name="preparing-to-implement-a-delivery-extension"></a><span data-ttu-id="7b0de-102">Preparando para implementar uma entrega de extensão</span><span class="sxs-lookup"><span data-stu-id="7b0de-102">Preparing to Implement a Delivery Extension</span></span>
  <span data-ttu-id="7b0de-103">Antes de implementar a sua extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], você deve definir as interfaces a serem implementadas.</span><span class="sxs-lookup"><span data-stu-id="7b0de-103">Before you implement your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you should define the interfaces to implement.</span></span> <span data-ttu-id="7b0de-104">Primeiro você precisa decidir como a sua extensão de entrega será usada, que configurações a sua extensão de entrega exigirá e a funcionalidade específica de que você precisará implementar para entregar notificações de relatório.</span><span class="sxs-lookup"><span data-stu-id="7b0de-104">You first need to decide how your delivery extension will be used, what settings your delivery extension will require, and the specific functionality you will need to implement in order to deliver report notifications.</span></span>  
  
 <span data-ttu-id="7b0de-105">Cada extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] deve fornecer a seguinte funcionalidade:</span><span class="sxs-lookup"><span data-stu-id="7b0de-105">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension must provide the following functionality:</span></span>  
  
-   <span data-ttu-id="7b0de-106">Uma implementação de interface <xref:Microsoft.ReportingServices.Interfaces.IExtension> que representa a extensão e um nome de extensão localizado.</span><span class="sxs-lookup"><span data-stu-id="7b0de-106">An <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface implementation that represents the extension and a localized extension name.</span></span>  
  
-   <span data-ttu-id="7b0de-107">Uma implementação <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> que cria uma extensão de entrega que pode ser usada para entregar notificações de relatório a usuários finais.</span><span class="sxs-lookup"><span data-stu-id="7b0de-107">An <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> implementation that creates a delivery extension that can be used to deliver report notifications to end users.</span></span>  
  
-   <span data-ttu-id="7b0de-108">A habilidade para processar dados de usuário específicos para uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="7b0de-108">The ability to process specific user data for a subscription.</span></span>  
  
 <span data-ttu-id="7b0de-109">Cada extensão de entrega pode ser aprimorada para incluir a seguinte funcionalidade:</span><span class="sxs-lookup"><span data-stu-id="7b0de-109">Each delivery extension can be enhanced to include the following functionality:</span></span>  
  
-   <span data-ttu-id="7b0de-110">Uma implementação de controle de usuário do [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] que permite que usuários finais usem o Gerenciador de Relatórios para criar assinaturas de relatório que usam a extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="7b0de-110">An [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] user control implementation that enables end users to use Report Manager to create report subscriptions that use the delivery extension.</span></span>  
  
 <span data-ttu-id="7b0de-111">A tabela a seguir descreve as interfaces e as classes disponíveis para extensões de entrega.</span><span class="sxs-lookup"><span data-stu-id="7b0de-111">The following table describes the available interfaces and classes for delivery extensions.</span></span>  
  
|<span data-ttu-id="7b0de-112">Interface ou classe</span><span class="sxs-lookup"><span data-stu-id="7b0de-112">Interface or class</span></span>|<span data-ttu-id="7b0de-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7b0de-113">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="7b0de-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interface</span><span class="sxs-lookup"><span data-stu-id="7b0de-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interface</span></span>|<span data-ttu-id="7b0de-115">Representa uma extensão no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b0de-115">Represents an extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="7b0de-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interface</span><span class="sxs-lookup"><span data-stu-id="7b0de-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interface</span></span>|<span data-ttu-id="7b0de-117">Representa uma extensão de entrega no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b0de-117">Represents a delivery extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="7b0de-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interface</span><span class="sxs-lookup"><span data-stu-id="7b0de-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interface</span></span>|<span data-ttu-id="7b0de-119">Contém informações sobre o servidor de relatório exigido por extensões de entrega (por exemplo, uma lista das extensões de renderização disponíveis).</span><span class="sxs-lookup"><span data-stu-id="7b0de-119">Contains information about the report server that is required by delivery extensions (for example, a list of the available rendering extensions).</span></span>|  
|<span data-ttu-id="7b0de-120">Classe <xref:Microsoft.ReportingServices.Interfaces.Setting></span><span class="sxs-lookup"><span data-stu-id="7b0de-120"><xref:Microsoft.ReportingServices.Interfaces.Setting> Class</span></span>|<span data-ttu-id="7b0de-121">Representa uma configuração para uma extensão.</span><span class="sxs-lookup"><span data-stu-id="7b0de-121">Represents a setting for an extension.</span></span>|  
|<span data-ttu-id="7b0de-122">Classe <xref:Microsoft.ReportingServices.Interfaces.Notification></span><span class="sxs-lookup"><span data-stu-id="7b0de-122"><xref:Microsoft.ReportingServices.Interfaces.Notification> Class</span></span>|<span data-ttu-id="7b0de-123">Contém informações de assinatura que extensões de entrega usam para entregar relatórios.</span><span class="sxs-lookup"><span data-stu-id="7b0de-123">Contains subscription information that delivery extensions use to deliver reports.</span></span>|  
|<span data-ttu-id="7b0de-124">Classe <xref:Microsoft.ReportingServices.Interfaces.Report></span><span class="sxs-lookup"><span data-stu-id="7b0de-124"><xref:Microsoft.ReportingServices.Interfaces.Report> Class</span></span>|<span data-ttu-id="7b0de-125">Representa informações e métodos específicos do relatório métodos que permitem que extensões de entrega enviem relatórios a usuários.</span><span class="sxs-lookup"><span data-stu-id="7b0de-125">Represents report-specific information and methods that enable delivery extensions to deliver reports to users.</span></span>|  
|<span data-ttu-id="7b0de-126">Classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile></span><span class="sxs-lookup"><span data-stu-id="7b0de-126"><xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> Class</span></span>|<span data-ttu-id="7b0de-127">Representa a saída de uma extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="7b0de-127">Represents the output from a rendering extension.</span></span> <span data-ttu-id="7b0de-128">Um objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> contém o nome de arquivo associado e as informações de tipo exigidos pela extensão de entrega para o processamento do fluxo retornado pela extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="7b0de-128">A <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object contains the associated file name and type information that is required by the delivery extension in order to process the stream returned by the rendering extension.</span></span>|  
|<span data-ttu-id="7b0de-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interface</span><span class="sxs-lookup"><span data-stu-id="7b0de-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interface</span></span>|<span data-ttu-id="7b0de-130">Um controle de usuário que representa o meio de recuperação de informações de assinatura específicas da extensão de entrega do usuário no Gerenciador de Relatórios (por exemplo, um endereço de email ou o caminho para um compartilhamento de arquivo).</span><span class="sxs-lookup"><span data-stu-id="7b0de-130">A user control that represents the means to retrieve delivery extension-specific subscription information from the user in Report Manager (for example, an e-mail address or the path to a file share).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b0de-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b0de-131">See Also</span></span>  
 <span data-ttu-id="7b0de-132">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="7b0de-132">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="7b0de-133">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="7b0de-133">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="7b0de-134">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7b0de-134">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
