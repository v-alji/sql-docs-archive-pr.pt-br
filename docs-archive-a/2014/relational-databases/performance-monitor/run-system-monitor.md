---
title: Executar o Monitor do Sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], running
- Windows System Monitor [SQL Server], running
- remote procedure calls [SQL Server]
- starting Windows NT System Monitor
- RPC
ms.assetid: 05297984-bc8d-43df-829c-032387f7ea61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dd0baf32402d69e36dc5120d0259b2f8d689897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684661"
---
# <a name="run-system-monitor"></a><span data-ttu-id="54774-102">Executar o Monitor do Sistema</span><span class="sxs-lookup"><span data-stu-id="54774-102">Run System Monitor</span></span>
  <span data-ttu-id="54774-103">O Monitor do Sistema usa RPCs (chamadas de procedimento remotas) para coletar informações do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54774-103">System Monitor uses remote procedure calls (RPCs) to collect information from Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="54774-104">Qualquer usuário com permissões do Microsoft Windows para executar o Monitor do Sistema pode utilizá-lo para monitorar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54774-104">Any user who has Microsoft Windows permissions to run System Monitor can use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54774-105">Ao usar o Monitor do Sistema ou o Monitor de Desempenho, não é possível se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que seja executada em Windows 98.</span><span class="sxs-lookup"><span data-stu-id="54774-105">When using System Monitor or Performance Monitor, you cannot connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on Windows 98.</span></span>  
  
 <span data-ttu-id="54774-106">Assim como ocorre com toda ferramenta de monitoramento de desempenho, é de se esperar alguma sobrecarga quando se usa o Monitor do Sistema para monitorar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54774-106">As with all performance monitoring tools, expect some performance overhead when you use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="54774-107">A sobrecarga real em instâncias específicas depende da plataforma de hardware, do número de contadores e do intervalo de atualização selecionado.</span><span class="sxs-lookup"><span data-stu-id="54774-107">The actual overhead in any specific instance depends on the hardware platform, the number of counters, and the selected update interval.</span></span> <span data-ttu-id="54774-108">No entanto, a integração do Monitor do Sistema com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi projetada para minimizar qualquer redução no desempenho.</span><span class="sxs-lookup"><span data-stu-id="54774-108">However, the integration of System Monitor with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is designed to minimize any reduction in performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54774-109">Se tiver selecionado contadores de desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para monitoramento no snap-in do Monitor do Sistema, você verá os contadores mesmo que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="54774-109">If you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performance counters to monitor in the System Monitor snap-in, you will see the counters even if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running.</span></span>  
  
 <span data-ttu-id="54774-110">Para obter informações sobre como iniciar o Monitor do Sistema, consulte [Iniciar o Monitor do Sistema &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span><span class="sxs-lookup"><span data-stu-id="54774-110">For information about starting System Monitor, see [Start System Monitor &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span></span>  
  
  
