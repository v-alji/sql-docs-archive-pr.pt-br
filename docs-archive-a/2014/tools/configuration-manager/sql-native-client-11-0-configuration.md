---
title: Configuração do SQL Native Client 11,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client configuration [SQL Server], SQL Server Native Client
ms.assetid: e73143e9-5e7b-4d0a-8827-ab900efdcb35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 183dd2d161b1bf0b13140a607167b81dab086fdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570419"
---
# <a name="sql-native-client-110-configuration"></a><span data-ttu-id="2757b-102">Configuração do SQL Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="2757b-102">SQL Native Client 11.0 Configuration</span></span>
  <span data-ttu-id="2757b-103">Esta seção contém os tópicos da Ajuda F1 das caixas de diálogo **Configuração do SQL Server Native Client** no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2757b-103">This section contains the F1 Help topics for the **SQL Server Native Client Configuration** dialogs in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2757b-104">Native Client é a biblioteca de rede que os computadores cliente usam para se conectarem ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] começando com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2757b-104">Native Client is the network library that client computers use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], starting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2757b-105">As definições feitas na Configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client são usadas no computador que está executando o programa cliente.</span><span class="sxs-lookup"><span data-stu-id="2757b-105">The settings configured in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Configuration, are used on the computer running the client program.</span></span> <span data-ttu-id="2757b-106">Quando definidas no computador que está executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], elas afetam somente os programas clientes executados no servidor.</span><span class="sxs-lookup"><span data-stu-id="2757b-106">When configured on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they affect only those client programs running on the server.</span></span>  
  
 <span data-ttu-id="2757b-107">Essas configurações não afetam os clientes conectados a versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a não ser que eles estejam usando as ferramentas de cliente a partir do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2757b-107">These settings do not affect clients connecting to previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], unless they are using the client tools starting with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2757b-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2757b-108">In this Section</span></span>  
  
-   [<span data-ttu-id="2757b-109">Propriedades de configuração do SQL Server Native Client &#40;Guia Sinalizadores&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-109">SQL Server Native Client Configuration Properties &#40;Flags Tab&#41;</span></span>](../../../2014/tools/configuration-manager/sql-server-native-client-configuration-properties-flags-tab.md)  
  
-   [<span data-ttu-id="2757b-110">Protocolos de cliente &#40;SQL Server Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-110">Client Protocols &#40;SQL Server Configuration Manager&#41;</span></span>](../../relational-databases/sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="2757b-111">Propriedades de Protocolos de Cliente &#40;Guia Ordem&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-111">Client Protocols Properties &#40;Order Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-properties-order-tab.md)  
  
    -   [<span data-ttu-id="2757b-112">Protocolos de Cliente – Propriedades de Memória Compartilhada &#40;Guia Protocolo&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-112">Client Protocols - Shared Memory Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-shared-memory-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="2757b-113">Protocolos de cliente – as propriedades TCP e IP &#40;guia Protocolo&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-113">Client Protocols - TCP and IP Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-tcp-and-ip-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="2757b-114">Protocolos de Cliente – Propriedades de Pipes Nomeados &#40;Guia Protocolo&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-114">Client Protocols - Named Pipes Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-named-pipes-properties-protocol-tab.md)  
  
-   [<span data-ttu-id="2757b-115">Aliases &#40;SQL Server Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-115">Aliases &#40;SQL Server Configuration Manager&#41;</span></span>](../../../2014/tools/configuration-manager/aliases-sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="2757b-116">Novo Alias &#40;Guia Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-116">New Alias &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)  
  
    -   [<span data-ttu-id="2757b-117">Propriedades &#60;Alias&#62; &#40;Guia Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="2757b-117">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
    -   [<span data-ttu-id="2757b-118">Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada</span><span class="sxs-lookup"><span data-stu-id="2757b-118">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
    -   [<span data-ttu-id="2757b-119">Criando uma cadeia de conexão válida usando TCP/IP</span><span class="sxs-lookup"><span data-stu-id="2757b-119">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
    -   [<span data-ttu-id="2757b-120">Criando uma cadeia de conexão válida usando pipes nomeados</span><span class="sxs-lookup"><span data-stu-id="2757b-120">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
