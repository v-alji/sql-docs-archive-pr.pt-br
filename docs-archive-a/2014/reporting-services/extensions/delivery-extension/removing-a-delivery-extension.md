---
title: Removendo uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- removing delivery extensions
- deleting delivery extensions
- delivery extensions [Reporting Services], removing
ms.assetid: dcb7caf2-d19a-4bc5-afb3-2b61ad11cac5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c4320f46b5013b0fa2accbc81792748c2d9f384
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584028"
---
# <a name="removing-a-delivery-extension"></a><span data-ttu-id="a9870-102">Removendo uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="a9870-102">Removing a Delivery Extension</span></span>
  <span data-ttu-id="a9870-103">Para remover uma extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], basta remover o elemento **Extension** da extensão de entrega do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="a9870-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, simply remove the **Extension** element for your delivery extension from the configuration file.</span></span> <span data-ttu-id="a9870-104">Depois que as informações de configuração forem removidas, a extensão de entrega não estará mais disponível para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a9870-104">After the configuration information is removed, the delivery extension is no longer available to the report server.</span></span>  
  
 <span data-ttu-id="a9870-105">Depois que o elemento **Extension** correspondente de uma extensão de entrega é removido do arquivo de configuração, ele não fica mais registrado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a9870-105">Once a delivery extension's corresponding **Extension** element is removed from the configuration file, it is no longer registered with the report server.</span></span> <span data-ttu-id="a9870-106">O servidor de relatório remove a entrada da lista de extensões de entrega e desativa quaisquer assinaturas que usem aquela extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="a9870-106">The report server removes the entry from the list of delivery extensions and deactivates any subscriptions which use that delivery extension.</span></span> <span data-ttu-id="a9870-107">Quando uma extensão de entrega é removida, os usuários não podem mais selecioná-la como um método de notificação.</span><span class="sxs-lookup"><span data-stu-id="a9870-107">When a delivery extension is removed, users are no longer able to select it as a method of notification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9870-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9870-108">See Also</span></span>  
 <span data-ttu-id="a9870-109">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a9870-109">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="a9870-110">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a9870-110">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
