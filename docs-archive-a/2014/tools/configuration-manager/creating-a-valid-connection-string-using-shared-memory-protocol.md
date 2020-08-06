---
title: Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca97332a09a33fcfc15a3dbb2599af27dbe0e1db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678464"
---
# <a name="creating-a-valid-connection-string-using-shared-memory-protocol"></a><span data-ttu-id="54e62-102">Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada</span><span class="sxs-lookup"><span data-stu-id="54e62-102">Creating a Valid Connection String Using Shared Memory Protocol</span></span>
  <span data-ttu-id="54e62-103">As conexões com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um cliente executado no mesmo computador usam o protocolo de memória compartilhada.</span><span class="sxs-lookup"><span data-stu-id="54e62-103">Connections to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client running on the same computer use the shared memory protocol.</span></span> <span data-ttu-id="54e62-104">A memória compartilhada não tem propriedades configuráveis.</span><span class="sxs-lookup"><span data-stu-id="54e62-104">Shared memory has no configurable properties.</span></span> <span data-ttu-id="54e62-105">Essa memória sempre é tentada primeiro e não pode ser movida da posição superior da lista **Protocolos Habilitados** na lista **Propriedades de Protocolos de Cliente** .</span><span class="sxs-lookup"><span data-stu-id="54e62-105">Shared memory is always tried first, and cannot be moved from the top position of the **Enabled Protocols** list in the **Client Protocols Properties** list.</span></span> <span data-ttu-id="54e62-106">O protocolo de Memória Compartilhada pode ser desabilitado, o que é útil ao solucionar problemas dos outros protocolos.</span><span class="sxs-lookup"><span data-stu-id="54e62-106">The Shared Memory protocol can be disabled, which is useful when troubleshooting one of the other protocols.</span></span>  
  
 <span data-ttu-id="54e62-107">Não é possível criar um alias usando o protocolo de memória compartilhada, mas se a memória compartilhada estiver habilitada, a conexão com o [!INCLUDE[ssDE](../../includes/ssde-md.md)] pelo nome criará uma conexão de memória compartilhada.</span><span class="sxs-lookup"><span data-stu-id="54e62-107">You cannot create an alias using the shared memory protocol, but if shared memory is enabled, then connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by name, creates a shared memory connection.</span></span> <span data-ttu-id="54e62-108">Uma cadeia de conexão de memória compartilhada usa o formato `lpc:<servername>[\instancename]`.</span><span class="sxs-lookup"><span data-stu-id="54e62-108">A shared memory connection string uses the format `lpc:<servername>[\instancename]`.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="54e62-109">Conectando-se ao servidor local</span><span class="sxs-lookup"><span data-stu-id="54e62-109">Connecting to the Local Server</span></span>  
 <span data-ttu-id="54e62-110">Ao conectar-se ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no mesmo computador que o cliente, você pode usar **(local)** como o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="54e62-110">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use **(local)** as the server name.</span></span> <span data-ttu-id="54e62-111">Esse procedimento não é incentivado, pois leva a ambiguidade. No entanto, ele pode ser útil quando se sabe que o cliente está sendo executado no computador pretendido.</span><span class="sxs-lookup"><span data-stu-id="54e62-111">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="54e62-112">Por exemplo, ao criar um aplicativo para usuários móveis desconectados, como uma força de vendas, em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será executado em computadores laptop e armazenará dados de projeto, um cliente conectado a **(local)** sempre se conectaria ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no laptop.</span><span class="sxs-lookup"><span data-stu-id="54e62-112">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to **(local)** would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="54e62-113">A palavra **localhost** ou um ponto ( **.** ) pode ser usado em lugar de **(local)** .</span><span class="sxs-lookup"><span data-stu-id="54e62-113">The word **localhost** or a period (**.**) can be used in place of **(local)**.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="54e62-114">Verificando o protocolo de conexão</span><span class="sxs-lookup"><span data-stu-id="54e62-114">Verifying your Connection Protocol</span></span>  
 <span data-ttu-id="54e62-115">A consulta a seguir retornará o protocolo usado para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="54e62-115">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="54e62-116">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="54e62-116">Examples:</span></span>  
 <span data-ttu-id="54e62-117">Os seguintes nomes se conectarão ao computador local com o protocolo da memória compartilhada, se ele estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="54e62-117">The following names will connect to the local computer with the shared memory protocol if it is enabled:</span></span>  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 <span data-ttu-id="54e62-118">Não é possível criar um alias para uma conexão de memória compartilhada.</span><span class="sxs-lookup"><span data-stu-id="54e62-118">You cannot create an alias for a shared memory connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54e62-119">A especificação de um Endereço IP na caixa **Servidor** resultará em uma conexão TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="54e62-119">Specifying an IP Address in the **Server** box will result in a TCP/IP connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e62-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54e62-120">See Also</span></span>  
 <span data-ttu-id="54e62-121">[Criando uma cadeia de conexão válida usando TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="54e62-121">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 <span data-ttu-id="54e62-122">[Criando uma cadeia de conexão válida usando pipes nomeados](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="54e62-122">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="54e62-123">Escolhendo um protocolo de rede</span><span class="sxs-lookup"><span data-stu-id="54e62-123">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
