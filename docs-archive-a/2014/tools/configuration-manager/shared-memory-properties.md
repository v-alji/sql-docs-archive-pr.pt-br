---
title: Propriedades da memória compartilhada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
ms.assetid: dc1704da-eacd-4d26-b529-c996f958ca4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6275215afdb6de3aa134dbffe74aa22b9e7b6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582712"
---
# <a name="shared-memory-properties"></a><span data-ttu-id="9d81c-102">Propriedades da memória compartilhada</span><span class="sxs-lookup"><span data-stu-id="9d81c-102">Shared Memory Properties</span></span>
  <span data-ttu-id="9d81c-103">Use a página **Protocolo**na caixa de diálogo **Propriedades de Memória Compartilhada** para habilitar ou desabilitar o protocolo de memória compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9d81c-103">Use the **Protocol**page on the **Shared Memory Properties** dialog box to enable or disable the shared memory protocol.</span></span> <span data-ttu-id="9d81c-104">A memória compartilhada é o protocolo mais simples de usar e não precisa de configurações.</span><span class="sxs-lookup"><span data-stu-id="9d81c-104">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="9d81c-105">Como os clientes que usam o protocolo de memória compartilhada só podem se conectar a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executada no mesmo computador, ele não é útil para a maior parte da atividade de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9d81c-105">Because clients using the shared memory protocol can only connect to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="9d81c-106">Use o protocolo de memória compartilhada para solucionar problemas quando você suspeitar que outros protocolos estejam configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="9d81c-106">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9d81c-107">deve ser reiniciado para habilitar ou desabilitar o protocolo.</span><span class="sxs-lookup"><span data-stu-id="9d81c-107">must be restarted to enable or disable the protocol.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d81c-108">Opções</span><span class="sxs-lookup"><span data-stu-id="9d81c-108">Options</span></span>  
 <span data-ttu-id="9d81c-109">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="9d81c-109">**Enabled**</span></span>  
 <span data-ttu-id="9d81c-110">Os valores possíveis são **Sim** e **Não**.</span><span class="sxs-lookup"><span data-stu-id="9d81c-110">Possible values are **Yes** and **No**.</span></span> <span data-ttu-id="9d81c-111">O protocolo de memória compartilhada é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9d81c-111">The shared memory protocol is enabled by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d81c-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d81c-112">See Also</span></span>  
 <span data-ttu-id="9d81c-113">[Escolhendo um protocolo de rede](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="9d81c-113">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="9d81c-114">Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada</span><span class="sxs-lookup"><span data-stu-id="9d81c-114">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
  
