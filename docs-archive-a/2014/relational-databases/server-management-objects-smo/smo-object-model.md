---
title: Modelo de objeto SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678706"
---
# <a name="smo-object-model"></a><span data-ttu-id="1b213-102">Modelo de objeto SMO</span><span class="sxs-lookup"><span data-stu-id="1b213-102">SMO Object Model</span></span>
  <span data-ttu-id="1b213-103">O modelo de objeto SMO é composto de uma hierarquia de objetos.</span><span class="sxs-lookup"><span data-stu-id="1b213-103">The SMO object model is made up of a hierarchy of objects.</span></span> <span data-ttu-id="1b213-104">O objeto <xref:Microsoft.SqlServer.Management.Smo.Server> é o objeto de nível superior e todos os objetos de classe de instância residem sob o objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="1b213-104">The <xref:Microsoft.SqlServer.Management.Smo.Server> object is the top level object and all instance class objects reside under the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
 <span data-ttu-id="1b213-105">A classe <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> é uma classe de nível superior com uma hierarquia de objetos separada.</span><span class="sxs-lookup"><span data-stu-id="1b213-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> class is a top level class with a separate object hierarchy.</span></span> <span data-ttu-id="1b213-106">O <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objeto representa [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviços e configurações de rede disponíveis por meio do provedor WMI.</span><span class="sxs-lookup"><span data-stu-id="1b213-106">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings available through the WMI Provider.</span></span>  
  
 <span data-ttu-id="1b213-107">Além dos objetos <xref:Microsoft.SqlServer.Management.Smo.Server> e <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, há várias classes de utilitário que representam tarefas ou operações, como <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> ou <xref:Microsoft.SqlServer.Management.Smo.Restore></span><span class="sxs-lookup"><span data-stu-id="1b213-107">Besides the <xref:Microsoft.SqlServer.Management.Smo.Server> and <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objects, there are several utility classes that represent tasks or operations, such as <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup>, or <xref:Microsoft.SqlServer.Management.Smo.Restore></span></span>  
  
 <span data-ttu-id="1b213-108">O modelo de objeto SMO é composto de vários namespaces.</span><span class="sxs-lookup"><span data-stu-id="1b213-108">The SMO object model is made up of several namespaces.</span></span> <span data-ttu-id="1b213-109">Para obter mais informações, consulte o [Namespaces do SMO](smo-object-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="1b213-109">For more information, see [SMO Namespaces](smo-object-model-namespaces.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b213-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b213-110">See Also</span></span>  
 <span data-ttu-id="1b213-111">[Diagrama de modelo de objeto SMO](smo-object-model-diagram.md) </span><span class="sxs-lookup"><span data-stu-id="1b213-111">[SMO Object Model Diagram](smo-object-model-diagram.md) </span></span>  
 <span data-ttu-id="1b213-112">[Namespaces do SMO](smo-object-model-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="1b213-112">[SMO Namespaces](smo-object-model-namespaces.md) </span></span>  
 [<span data-ttu-id="1b213-113">Provedor WMI para conceitos de gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="1b213-113">WMI Provider for Configuration Management Concepts</span></span>](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
