---
title: Implementando uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af1e804e029dae77fb7836577aa8d4a45ad20109
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584036"
---
# <a name="implementing-a-delivery-extension"></a><span data-ttu-id="82579-102">Implementando uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-102">Implementing a Delivery Extension</span></span>
  <span data-ttu-id="82579-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permite que os usuários criem e publiquem relatórios que, uma vez criados e publicados, podem ser entregues em vários locais.</span><span class="sxs-lookup"><span data-stu-id="82579-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enables users to create and publish reports that, once created and published, can be delivered to various locations.</span></span> <span data-ttu-id="82579-104">Além disso, o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclui várias extensões de entrega e uma API de entrega que permite que os desenvolvedores criem extensões de entrega adicionais para estender ainda mais a funcionalidade de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82579-104">In addition, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes several delivery extensions and a delivery API that enable developers to create additional delivery extensions to further extend the functionality of delivery in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="82579-105">Para obter uma implementação de exemplo de uma extensão de entrega, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="82579-105">For a sample implementation of a delivery extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82579-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="82579-106">In This Section</span></span>  
 <span data-ttu-id="82579-107">[Visão geral das extensões de entrega] entrega-extensões-overview.md)</span><span class="sxs-lookup"><span data-stu-id="82579-107">[Delivery Extensions Overview]delivery-extensions-overview.md)</span></span>  
 <span data-ttu-id="82579-108">Apresenta como escrever uma extensão de entrega para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82579-108">Introduces how to write a custom delivery extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="82579-109">Preparar para implementar uma entrega de extensão</span><span class="sxs-lookup"><span data-stu-id="82579-109">Preparing to Implement a Delivery Extension</span></span>](preparing-to-implement-a-delivery-extension.md)  
 <span data-ttu-id="82579-110">Descreve as interfaces e as classes disponíveis durante a implementação de uma extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], além dos problemas a serem considerados antes da implementação.</span><span class="sxs-lookup"><span data-stu-id="82579-110">Describes the interfaces and classes available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, as well as issues to consider before implementation.</span></span>  
  
 [<span data-ttu-id="82579-111">Criar uma biblioteca de extensões de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-111">Creating a Delivery Extension Library</span></span>](creating-a-delivery-extension-library.md)  
 <span data-ttu-id="82579-112">Descreve a atribuição de um namespace para a extensão de entrega do seu [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e a compilação da sua extensão de entrega em uma DLL de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="82579-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension and compiling your delivery extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="82579-113">Implementar a interface IDeliveryExtension para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-113">Implementing the IDeliveryExtension Interface for a Delivery Extension</span></span>](implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="82579-114">Descreve os atributos de uma extensão de entrega e como implementar a sua própria classe de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-114">Describes the attributes of a delivery extension, and how to implement your own delivery extension class.</span></span>  
  
 [<span data-ttu-id="82579-115">Usar uma classe de notificação para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-115">Using a Notification Class for a Delivery Extension</span></span>](using-a-notification-class-for-a-delivery-extension.md)  
 <span data-ttu-id="82579-116">Descreve os atributos de uma classe **Notification** e como usá-la na implementação de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-116">Describes the attributes of a **Notification** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="82579-117">Usar a classe Setting para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-117">Using the Setting Class for a Delivery Extension</span></span>](using-the-setting-class-for-a-delivery-extension.md)  
 <span data-ttu-id="82579-118">Descreve os atributos de uma classe **Setting** e como usá-la na implementação de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-118">Describes the attributes of a **Setting** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="82579-119">Usando a interface IDeliveryReportServerInformation para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-119">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="82579-120">Descreve os atributos de uma interface **IDeliveryReportServerInformation** e como usá-la na implementação de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-120">Describes the attributes of a **IDeliveryReportServerInformation** interface and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="82579-121">Usando a classe Report para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-121">Using the Report Class for a Delivery Extension</span></span>](using-the-report-class-for-a-delivery-extension.md)  
 <span data-ttu-id="82579-122">Descreve os atributos de uma classe **Report** e como usá-la na implementação de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-122">Describes the attributes of a **Report** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="82579-123">Usando a classe RenderedOutputFile para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-123">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 <span data-ttu-id="82579-124">Descreve os atributos de uma classe **RenderedOutputFile** e como usá-la na implementação de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-124">Describes the attributes of a **RenderedOutputFile** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="82579-125">Implementando a interface ISubscriptionBaseUIUserControl para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-125">Implementing the ISubscriptionBaseUIUserControl Interface for a Delivery Extension</span></span>](implementing-the-isubscriptionbaseuiusercontrol-interface.md)  
 <span data-ttu-id="82579-126">Descreve os atributos de um controle de usuário de extensão de entrega e como implementar a sua própria interface do usuário para uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="82579-126">Describes the attributes of a delivery extension user control and how to implement your own user interface for a subscription.</span></span>  
  
 [<span data-ttu-id="82579-127">Implantando uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-127">Deploying a Delivery Extension</span></span>](deploying-a-delivery-extension.md)  
 <span data-ttu-id="82579-128">Descreve como implantar a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-128">Describes how to deploy your delivery extension.</span></span>  
  
 [<span data-ttu-id="82579-129">Depurando o código de extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-129">Debugging Delivery Extension Code</span></span>](debugging-delivery-extension-code.md)  
 <span data-ttu-id="82579-130">Descreve como depurar código em sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="82579-130">Describes how to debug code in your delivery extension.</span></span>  
  
 [<span data-ttu-id="82579-131">Removendo uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="82579-131">Removing a Delivery Extension</span></span>](removing-a-delivery-extension.md)  
 <span data-ttu-id="82579-132">Descreve como remover uma extensão de entrega de um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="82579-132">Describes how to remove a delivery extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82579-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82579-133">See Also</span></span>  
 <span data-ttu-id="82579-134">[Extensões de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="82579-134">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="82579-135">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="82579-135">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
