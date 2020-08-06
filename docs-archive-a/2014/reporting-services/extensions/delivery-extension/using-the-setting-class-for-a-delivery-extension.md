---
title: Usando a classe Setting para uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], settings
- Setting class
ms.assetid: 50746639-da7c-46a5-ac7b-e87dd6b91880
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 594cf28391ae4523e1a95ad79ee5b1280ff72218
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679179"
---
# <a name="using-the-setting-class-for-a-delivery-extension"></a><span data-ttu-id="6adb4-102">Usando a classe Setting para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="6adb4-102">Using the Setting Class for a Delivery Extension</span></span>
  <span data-ttu-id="6adb4-103">A classe <xref:Microsoft.ReportingServices.Interfaces.Setting> está localizada no namespace <xref:Microsoft.ReportingServices.Interfaces> e representa as informações sobre configurações de extensão para uma extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="6adb4-103">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is located in the <xref:Microsoft.ReportingServices.Interfaces> namespace and represents information about extension settings for a delivery extension.</span></span> <span data-ttu-id="6adb4-104">A classe <xref:Microsoft.ReportingServices.Interfaces.Setting> fornece infraestrutura para o armazenamento de informações sobre as configurações obrigatórias para que uma extensão de entrega funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="6adb4-104">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class provides infrastructure for storing information about the settings that are required in order for a delivery extension to function properly.</span></span> <span data-ttu-id="6adb4-105">Por exemplo, na entrega de E-Mail do Report Server, é necessário que um usuário forneça configurações específicas de entrega de e-mails, como o endereço do destinatário, o endereço do remetente, a linha de assunto do e-mail e mais.</span><span class="sxs-lookup"><span data-stu-id="6adb4-105">For example, in Report Server E-Mail delivery, a user is required to supply settings specific to e-mail delivery, such as the recipient's address, the sender's address, the subject line of the e-mail, and more.</span></span> <span data-ttu-id="6adb4-106">Indubitavelmente, os seus provedores de entrega personalizados exigirão que o usuário forneça configurações específicas para que a extensão de entrega entregue notificações e relatórios.</span><span class="sxs-lookup"><span data-stu-id="6adb4-106">Undoubtedly, your custom delivery providers will require the user to supply specific settings in order for the delivery extension to deliver notifications and reports.</span></span>  
  
 <span data-ttu-id="6adb4-107">A classe de <xref:Microsoft.ReportingServices.Interfaces.Setting> é usada na implementação da propriedade de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> da interface de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="6adb4-107">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is used when implementing the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> property of the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="6adb4-108">A classe de <xref:Microsoft.ReportingServices.Interfaces.Setting> também é usada para o processamento dos dados de configuração da extensão fornecidos por um usuário quando uma assinatura ou notificação é criada.</span><span class="sxs-lookup"><span data-stu-id="6adb4-108">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is also used for processing the extension setting data that is supplied by a user when a subscription or notification is created.</span></span>  
  
 <span data-ttu-id="6adb4-109">Para obter um exemplo de como usar a classe <xref:Microsoft.ReportingServices.Interfaces.Setting>, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="6adb4-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Setting> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adb4-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6adb4-110">See Also</span></span>  
 <span data-ttu-id="6adb4-111">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="6adb4-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="6adb4-112">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6adb4-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
