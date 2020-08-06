---
title: Iniciar o Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cff23206923825d0e86e47ad6921c19f45e68b35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685559"
---
# <a name="start-the-replication-monitor"></a><span data-ttu-id="e226a-102">Iniciar o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="e226a-102">Start the Replication Monitor</span></span>
  <span data-ttu-id="e226a-103">O Replication Monitor pode ser iniciado no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] em qualquer instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e226a-103">Replication Monitor can be started from [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on any instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], or from the command prompt.</span></span> <span data-ttu-id="e226a-104">Depois de iniciar o Replication Monitor, adicione um ou mais Publicadores a serem monitorados.</span><span class="sxs-lookup"><span data-stu-id="e226a-104">After starting Replication Monitor, add one or more Publishers to monitor.</span></span> <span data-ttu-id="e226a-105">Para obter mais informações, veja [Adicionar e remover Publicadores do Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="e226a-105">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a><span data-ttu-id="e226a-106">Iniciar o Replication Monitor no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e226a-106">To start Replication Monitor from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e226a-107">Conecte a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]e, então, expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="e226a-107">Connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="e226a-108">Clique com o botão direito em na pasta **Replicação** ou quaisquer de suas subpastas e então clique em **Iniciar o Replication Monitor**.</span><span class="sxs-lookup"><span data-stu-id="e226a-108">Right-click the **Replication** folder or any of its subfolders, and then click **Launch Replication Monitor**.</span></span>  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a><span data-ttu-id="e226a-109">Para iniciar o Replication Monitor no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="e226a-109">To start Replication Monitor from the command prompt</span></span>  
  
1.  <span data-ttu-id="e226a-110">No prompt de comando, navegue até o diretório de instalação de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e226a-110">From the command prompt, navigate to the tools installation directory.</span></span> <span data-ttu-id="e226a-111">O caminho padrão é [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn \.</span><span class="sxs-lookup"><span data-stu-id="e226a-111">The default path is [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span></span>  
  
2.  <span data-ttu-id="e226a-112">Execute sqlmonitor.exe.</span><span class="sxs-lookup"><span data-stu-id="e226a-112">Run sqlmonitor.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e226a-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e226a-113">See Also</span></span>  
 [<span data-ttu-id="e226a-114">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="e226a-114">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
