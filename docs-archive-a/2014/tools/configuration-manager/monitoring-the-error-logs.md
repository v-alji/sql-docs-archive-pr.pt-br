---
title: Monitorando os logs de erros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a47891599dbe735bd437f5239c73bfd34c422ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573342"
---
# <a name="monitoring-the-error-logs"></a><span data-ttu-id="c7dcc-102">Monitorando os logs de erros</span><span class="sxs-lookup"><span data-stu-id="c7dcc-102">Monitoring the Error Logs</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c7dcc-103">registra determinados eventos de sistema e eventos definidos pelo usuário no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e no log do aplicativo do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-103">logs certain system events and user-defined events to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span> <span data-ttu-id="c7dcc-104">Ambos os logs registram automaticamente todos os eventos com carimbos de hora.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-104">Both logs automatically timestamp all recorded events.</span></span> <span data-ttu-id="c7dcc-105">Use as informações do log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para solucionar problemas relacionados ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7dcc-105">Use the information in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to troubleshoot problems related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c7dcc-106">O log do aplicativo do Windows fornece um panorama dos eventos que ocorrem no sistema operacional Windows, bem como dos eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-106">The Windows application log provides an overall picture of events that occur on the Windows operating system, as well as events in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="c7dcc-107">Use o Visualizador de Eventos do Windows para exibir o log do aplicativo e para filtrar as informações.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-107">Use the Windows Event Viewer to view the Windows application log and to filter the information.</span></span> <span data-ttu-id="c7dcc-108">Por exemplo, você pode filtrar eventos, como informações, advertência, erro, auditoria com êxito ou sem êxito.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-108">For example, you can filter events, such as information, warning, error, success audit, and failure audit.</span></span>  
  
## <a name="comparing-error-and-application-log-output"></a><span data-ttu-id="c7dcc-109">comparando a saída do log de erros e do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c7dcc-109">Comparing Error and Application Log Output</span></span>  
 <span data-ttu-id="c7dcc-110">Você pode usar o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o log do aplicativo do Windows para identificar a causa dos problemas.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-110">You can use both the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows application log to identify the cause of problems.</span></span> <span data-ttu-id="c7dcc-111">Por exemplo, enquanto monitora o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , você pode encontrar mensagens de erro que não contêm as informações do ocorrido.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-111">For example, while monitoring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, you may encounter error messages that do not contain cause information.</span></span> <span data-ttu-id="c7dcc-112">Comparando as datas e as horas dos eventos entre esses logs, você pode reduzir a lista de causas prováveis.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-112">By comparing the dates and times for events between these logs, you can narrow the list of probable causes.</span></span> <span data-ttu-id="c7dcc-113">O Visualizador do Arquivo de Log do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permite integrar os logs do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e do Windows à uma única lista, simplificando a compreensão dos eventos relativos ao servidor e aos eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7dcc-113">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Log File Viewer lets you integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and the Windows logs into a single list, making it easy to understand related server events and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="c7dcc-114">Para obter mais informações, consulte o tópico "Visualizador do Arquivo de Log" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-114">For more information, see the topic "Log File Viewer" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7dcc-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c7dcc-115">In This Section</span></span>  
  
|<span data-ttu-id="c7dcc-116">Tópico</span><span class="sxs-lookup"><span data-stu-id="c7dcc-116">Topic</span></span>|<span data-ttu-id="c7dcc-117">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c7dcc-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c7dcc-118">Exibir o log de erros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7dcc-118">Viewing the SQL Server Error Log</span></span>](../../../2014/tools/configuration-manager/viewing-the-sql-server-error-log.md)|<span data-ttu-id="c7dcc-119">Contém informações sobre o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e como exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-119">Contains information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and how to view it.</span></span>|  
|[<span data-ttu-id="c7dcc-120">Exibir o log do aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="c7dcc-120">Viewing the Windows Application Log</span></span>](viewing-the-windows-application-log.md)|<span data-ttu-id="c7dcc-121">Contém informações sobre o log do aplicativo do Windows e como exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="c7dcc-121">Contains information about the Windows application log and how to view it.</span></span>|  
  
  
