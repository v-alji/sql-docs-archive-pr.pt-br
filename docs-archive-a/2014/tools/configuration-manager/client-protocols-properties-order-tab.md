---
title: Propriedades de protocolos de cliente (guia ordem) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679600"
---
# <a name="client-protocols-properties-order-tab"></a><span data-ttu-id="10195-102">Propriedades de Protocolos de Cliente (guia Ordem)</span><span class="sxs-lookup"><span data-stu-id="10195-102">Client Protocols Properties (Order Tab)</span></span>
  <span data-ttu-id="10195-103">Use a página **Ordem**na caixa de diálogo **Propriedades de Protocolos de Cliente** para exibir e habilitar os protocolos de cliente.</span><span class="sxs-lookup"><span data-stu-id="10195-103">Use the **Order**page on the **Client Protocols Properties** dialog box to view and enable the client protocols.</span></span>  
  
 <span data-ttu-id="10195-104">Clique em um protocolo e, em seguida, em **Habilitar** ou **Desabilitar** para mover o protocolo selecionado para a lista **Protocolos Desabilitados** ou **Protocolos Habilitados** .</span><span class="sxs-lookup"><span data-stu-id="10195-104">Click a protocol, and then click **Enable** or **Disable** to move the selected protocol to the **Disabled Protocols** or **Enabled Protocols** list.</span></span>  
  
 <span data-ttu-id="10195-105">Os protocolos são testados na ordem listada, tentando conectar usando o primeiro protocolo da lista, depois o segundo protocolo e assim por diante. Mova protocolos para cima ou para baixo na lista **Protocolos Habilitados** , clicando nos botões de seta para cima e para baixo.</span><span class="sxs-lookup"><span data-stu-id="10195-105">Protocols are tried in the order listed, attempting to connect using the top protocol first, and then the second listed protocol, etc. Move protocols up or down the **Enabled Protocols** list, by clicking the up arrow and down arrow buttons.</span></span> <span data-ttu-id="10195-106">Na conexão com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de um cliente nesse computador, o protocolo **Memória Compartilhada** sempre será tentado primeiro, se habilitado.</span><span class="sxs-lookup"><span data-stu-id="10195-106">When connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer, the **Shared Memory** protocol will always be tried first, if enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10195-107">Essas configurações não são usadas pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span><span class="sxs-lookup"><span data-stu-id="10195-107">These settings are not used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span></span> <span data-ttu-id="10195-108">A ordem dos protocolos para o .NET SqlClient é primeiro o TCP, e, em seguida, pipes nomeados que não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="10195-108">The protocol order for .NET SqlClient is first TCP, and then named pipes, which cannot be changed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="10195-109">Opções</span><span class="sxs-lookup"><span data-stu-id="10195-109">Options</span></span>  
 <span data-ttu-id="10195-110">**Protocolos Desabilitados**</span><span class="sxs-lookup"><span data-stu-id="10195-110">**Disabled Protocols**</span></span>  
 <span data-ttu-id="10195-111">Lista os protocolos que estão instalados, mas não são usados atualmente.</span><span class="sxs-lookup"><span data-stu-id="10195-111">Lists protocols which are installed but are not currently used.</span></span>  
  
 <span data-ttu-id="10195-112">**Protocolos Habilitados**</span><span class="sxs-lookup"><span data-stu-id="10195-112">**Enabled Protocols**</span></span>  
 <span data-ttu-id="10195-113">Lista os protocolos que estão disponíveis para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clientes neste computador.</span><span class="sxs-lookup"><span data-stu-id="10195-113">Lists protocols which are available for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this computer.</span></span>  
  
 **>**  
 <span data-ttu-id="10195-114">Habilita o protocolo realçado na caixa **Protocolos Desabilitados** , movendo-o para a caixa **Protocolos Habilitados** .</span><span class="sxs-lookup"><span data-stu-id="10195-114">Enables the currently highlighted protocol in the **Disabled Protocols** box, moving it to the **Enabled Protocols** box.</span></span>  
  
 **\<**  
 <span data-ttu-id="10195-115">Desabilita o protocolo realçado na caixa **Protocolos Habilitados** , movendo-o para a caixa **Protocolos Desabilitados** .</span><span class="sxs-lookup"><span data-stu-id="10195-115">Disables the currently highlighted protocol in the **Enabled Protocols** box, moving it to the **Disabled Protocols** box.</span></span>  
  
 <span data-ttu-id="10195-116">Seta para cima</span><span class="sxs-lookup"><span data-stu-id="10195-116">Up arrow</span></span>  
 <span data-ttu-id="10195-117">Move o protocolo realçado para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="10195-117">Moves the highlighted protocol up in the list.</span></span> <span data-ttu-id="10195-118">Isso permite aumentar a prioridade com que a Biblioteca de Rede tentará usar o protocolo selecionado para conexões.</span><span class="sxs-lookup"><span data-stu-id="10195-118">This allows you to increase the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="10195-119">Seta para baixo</span><span class="sxs-lookup"><span data-stu-id="10195-119">Down arrow</span></span>  
 <span data-ttu-id="10195-120">Move o protocolo realçado para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="10195-120">Moves the highlighted protocol down in the list.</span></span> <span data-ttu-id="10195-121">Isso permite diminuir a prioridade com que a Biblioteca de Rede tentará usar o protocolo selecionado para conexões.</span><span class="sxs-lookup"><span data-stu-id="10195-121">This allows you to decrease the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="10195-122">**Habilitar Protocolo de Memória Compartilhada**</span><span class="sxs-lookup"><span data-stu-id="10195-122">**Enable Shared Memory Protocol**</span></span>  
 <span data-ttu-id="10195-123">Habilita o protocolo de memória compartilhada que sempre é tentado primeiro (se habilitado), ao conectar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de um cliente nesse computador.</span><span class="sxs-lookup"><span data-stu-id="10195-123">Enables the shared memory protocol which is always tried first (if enabled), when connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10195-124">Se o protocolo for especificado por meio de um prefixo ou como parte da cadeia de conexão, somente o protocolo especificado será tentado.</span><span class="sxs-lookup"><span data-stu-id="10195-124">If the protocol is specified through a prefix or as part of the connection string, only the specified protocol is attempted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10195-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10195-125">See Also</span></span>  
 [<span data-ttu-id="10195-126">Escolhendo um protocolo de rede</span><span class="sxs-lookup"><span data-stu-id="10195-126">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
