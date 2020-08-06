---
title: Opção de configuração de servidor Agent XPs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Agent XPs option
- extended stored procedures [SQL Server], SQL Server Agent
ms.assetid: 2e1c6c64-5ce7-4357-98c7-ac7763a9f9de
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 541c81ea8d9f782a9c1ea391824b90a6fee772d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575352"
---
# <a name="agent-xps-server-configuration-option"></a><span data-ttu-id="93438-102">Opção Agent XPs de configuração do servidor</span><span class="sxs-lookup"><span data-stu-id="93438-102">Agent XPs Server Configuration Option</span></span>
  <span data-ttu-id="93438-103">Use a opção **Agent XPs** para habilitar os procedimentos armazenados estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent neste servidor.</span><span class="sxs-lookup"><span data-stu-id="93438-103">Use the **Agent XPs** option to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures on this server.</span></span> <span data-ttu-id="93438-104">Quando esta opção não está habilitada, o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não fica disponível no Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93438-104">When this option is not enabled, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer.</span></span>  
  
 <span data-ttu-id="93438-105">Quando a ferramenta [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] é usada para iniciar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, esses procedimentos armazenados estendidos são habilitados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="93438-105">When you use the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tool to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, these extended stored procedures are enabled automatically.</span></span> <span data-ttu-id="93438-106">Para obter mais informações, consulte [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="93438-106">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93438-107">O Pesquisador de Objetos do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] não exibe o conteúdo do nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent, a menos que os procedimentos armazenados estendidos estejam habilitados, independentemente do estado do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="93438-107">[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer does not display the contents of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent node unless these extended stored procedures are enabled regardless of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service state.</span></span>  
  
 <span data-ttu-id="93438-108">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="93438-108">The possible values are:</span></span>  
  
-   <span data-ttu-id="93438-109">**0**, indicando que os procedimentos armazenados estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não estão disponíveis (o padrão).</span><span class="sxs-lookup"><span data-stu-id="93438-109">**0**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are not available (the default).</span></span>  
  
-   <span data-ttu-id="93438-110">**1**, indicando que os procedimentos armazenados estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="93438-110">**1**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are available.</span></span>  
  
 <span data-ttu-id="93438-111">A configuração entra em vigor imediatamente, sem que o servidor seja parado e reiniciado.</span><span class="sxs-lookup"><span data-stu-id="93438-111">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="93438-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="93438-112">Examples</span></span>  
 <span data-ttu-id="93438-113">O exemplo a seguir habilita os procedimentos armazenados estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="93438-113">The following example enables the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Agent XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="93438-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93438-114">See Also</span></span>  
 <span data-ttu-id="93438-115">[Tarefas de administração automatizadas &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="93438-115">[Automated Administration Tasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="93438-116">Iniciar, parar ou pausar o serviço do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="93438-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
