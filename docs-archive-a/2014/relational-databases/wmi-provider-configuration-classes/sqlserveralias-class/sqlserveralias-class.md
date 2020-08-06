---
title: Classe SqlServerAlias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583416"
---
# <a name="sqlserveralias-class"></a><span data-ttu-id="e459c-102">Classe SqlServerAlias</span><span class="sxs-lookup"><span data-stu-id="e459c-102">SqlServerAlias Class</span></span>
  <span data-ttu-id="e459c-103">A classe [da classe SqlServerAlias](sqlserveralias-class.md) representa um alias de conexão de servidor.</span><span class="sxs-lookup"><span data-stu-id="e459c-103">The [SqlServerAlias Class](sqlserveralias-class.md) class represents a server connection alias.</span></span>  
  
 <span data-ttu-id="e459c-104">Um alias de conexão de servidor é necessário quando as seguintes situações ocorrerem:</span><span class="sxs-lookup"><span data-stu-id="e459c-104">A server connection alias is required when both the following occur:</span></span>  
  
-   <span data-ttu-id="e459c-105">O cliente está se conectando a uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em um transporte de rede que não é o transporte de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="e459c-105">The client is connecting to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] over a network transport that is not the default network transport.</span></span>  
  
-   <span data-ttu-id="e459c-106">A instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para o qual o cliente é conectado escuta em um pipe nomeado alternativo.</span><span class="sxs-lookup"><span data-stu-id="e459c-106">The instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the client is connected listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="e459c-107">**Observação:** A [classe SqlServerAlias](sqlserveralias-class.md) herda o `Put` método da classe Provider.</span><span class="sxs-lookup"><span data-stu-id="e459c-107">**Note:** The [SqlServerAlias Class](sqlserveralias-class.md) inherits the `Put` method from the Provider class.</span></span> <span data-ttu-id="e459c-108">Porém, ela não retorna nenhum resultado como indicado pelo método `Provider::Put`.</span><span class="sxs-lookup"><span data-stu-id="e459c-108">However, it does not return any results as indicated by the `Provider::Put` method.</span></span> <span data-ttu-id="e459c-109">Para obter mais informações, consulte a documentação do WMI.</span><span class="sxs-lookup"><span data-stu-id="e459c-109">For more information, see the WMI documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e459c-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e459c-110">See Also</span></span>  
 [<span data-ttu-id="e459c-111">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="e459c-111">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
