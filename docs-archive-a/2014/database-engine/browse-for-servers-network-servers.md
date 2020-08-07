---
title: Procurar servidores (servidores de rede) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.browseservers.network.f1
ms.assetid: a59ffcd6-4b69-4c5c-9740-699ccb2183fb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ba5e4e5dd6d9a6541a98e0cb30229d7335bac24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575376"
---
# <a name="browse-for-servers-network-servers"></a><span data-ttu-id="be63b-102">Procurar servidores (Servidores de Rede)</span><span class="sxs-lookup"><span data-stu-id="be63b-102">Browse for Servers (Network Servers)</span></span>
  <span data-ttu-id="be63b-103">Se você está se conectando a um componente do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e não sabe o nome exato da instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], clique em **Procurar mais** na caixa **Nome do servidor** para abrir a caixa de diálogo **Procurar Servidores**.</span><span class="sxs-lookup"><span data-stu-id="be63b-103">If you are connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] component and you do not know the exact name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance, click **Browse for more** in the **Server name** box to open the **Browse for Servers** dialog box.</span></span>  
  
 <span data-ttu-id="be63b-104">Esta caixa de diálogo é populada pelo serviço [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser nos computadores de servidor.</span><span class="sxs-lookup"><span data-stu-id="be63b-104">This dialog is populated by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service on the server computers.</span></span> <span data-ttu-id="be63b-105">Há várias razões pelas quais o nome de uma instância pode não aparecer na lista:</span><span class="sxs-lookup"><span data-stu-id="be63b-105">There are several reasons why the name of an instance might not appear in the list:</span></span>  
  
-   <span data-ttu-id="be63b-106">O serviço [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser pode não estar executando no computador que executa o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be63b-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service might not be running on the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="be63b-107">A porta 1434 UDP pode estar bloqueada por um firewall.</span><span class="sxs-lookup"><span data-stu-id="be63b-107">UDP port 1434 might be blocked by a firewall.</span></span>  
  
-   <span data-ttu-id="be63b-108">O sinalizador **HideInstance** pode estar configurado.</span><span class="sxs-lookup"><span data-stu-id="be63b-108">The **HideInstance** flag might be set.</span></span>  
  
 <span data-ttu-id="be63b-109">Para se conectar a uma instância que não apareça na lista, digite uma cadeia de caracteres de conexão completa para a instância, incluindo o número da porta TCP/IP ou o nome pipe dos pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="be63b-109">To connect to an instance that does not appear in the list, type a full connection string for the instance, including the TCP/IP port number or the named pipes pipe name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be63b-110">Opções</span><span class="sxs-lookup"><span data-stu-id="be63b-110">Options</span></span>  
 <span data-ttu-id="be63b-111">**Selecione uma instância do SQL Server na rede para sua conexão**</span><span class="sxs-lookup"><span data-stu-id="be63b-111">**Select a SQL Server instance in the network for your connection**</span></span>  
 <span data-ttu-id="be63b-112">Designe o servidor ao qual você deseja se conectar clicando na instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] exibida na árvore.</span><span class="sxs-lookup"><span data-stu-id="be63b-112">Designate the server you want to connect to by clicking on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance displayed in the tree.</span></span> <span data-ttu-id="be63b-113">Você pode mostrar ou ocultar partes do modo de exibição de árvore clicando nos nós marcados com um **+** **-** símbolo ou.</span><span class="sxs-lookup"><span data-stu-id="be63b-113">You can show or hide portions of the tree view by clicking on the nodes marked with a **+** or **-** symbol.</span></span>  
  
  
