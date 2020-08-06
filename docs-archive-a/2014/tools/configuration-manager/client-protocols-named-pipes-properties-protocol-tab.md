---
title: Protocolos de cliente – Propriedades de pipes nomeados (guia Protocolo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
author: stevestein
ms.author: sstein
ms.openlocfilehash: 169b6d98212c724b8d6c43615ae2fa7eba9cfc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679115"
---
# <a name="client-protocols---named-pipes-properties-protocol-tab"></a><span data-ttu-id="6f36a-102">Protocolos de Cliente – Propriedades de Pipes Nomeados (guia Protocolo)</span><span class="sxs-lookup"><span data-stu-id="6f36a-102">Client Protocols - Named Pipes Properties (Protocol Tab)</span></span>
  <span data-ttu-id="6f36a-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use a guia **Protocolo** na caixa de diálogo **Propriedades de Pipes Nomeados** para exibir ou modificar a descrição do pipe padrão.</span><span class="sxs-lookup"><span data-stu-id="6f36a-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager use the **Protocol** tab on the **Named Pipes Properties** dialog box to view or modify the description of default pipe.</span></span> <span data-ttu-id="6f36a-104">Para se conectar a um pipe diferente, digite o pipe na caixa **Pipe Padrão** .</span><span class="sxs-lookup"><span data-stu-id="6f36a-104">To connect to a different pipe, type the pipe in the **Default Pipe** box.</span></span> <span data-ttu-id="6f36a-105">Para obter mais informações sobre cadeias de conexão, consulte [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span><span class="sxs-lookup"><span data-stu-id="6f36a-105">For more information about connection strings, see [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f36a-106">Opções</span><span class="sxs-lookup"><span data-stu-id="6f36a-106">Options</span></span>  
 <span data-ttu-id="6f36a-107">**Pipe Padrão**</span><span class="sxs-lookup"><span data-stu-id="6f36a-107">**Default Pipe**</span></span>  
 <span data-ttu-id="6f36a-108">Especifica o pipe padrão que a biblioteca de rede Pipes Nomeados usará para tentar se conectar à instância de destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f36a-108">Specifies the default pipe the Named Pipes Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6f36a-109">Por padrão, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuta em: `\\.\pipe\sql\query`</span><span class="sxs-lookup"><span data-stu-id="6f36a-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query`</span></span>  
  
 <span data-ttu-id="6f36a-110">Para se conectar ao pipe padrão, digite `sql\query`</span><span class="sxs-lookup"><span data-stu-id="6f36a-110">To connect to the default pipe, enter `sql\query`</span></span>  
  
 <span data-ttu-id="6f36a-111">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="6f36a-111">**Enabled**</span></span>  
 <span data-ttu-id="6f36a-112">Os valores possíveis são **Sim** e **Não**.</span><span class="sxs-lookup"><span data-stu-id="6f36a-112">Possible values are **Yes** and **No**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f36a-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f36a-113">See Also</span></span>  
 [<span data-ttu-id="6f36a-114">Escolhendo um protocolo de rede</span><span class="sxs-lookup"><span data-stu-id="6f36a-114">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
