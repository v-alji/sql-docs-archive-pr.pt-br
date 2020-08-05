---
title: Visualizador do Arquivo de Log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer
ms.assetid: a4ea7fc8-1cb2-4c98-bc86-8991c5e748b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5139a32838070b817fce3bccf22b9fe08b5012e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572541"
---
# <a name="log-file-viewer"></a><span data-ttu-id="797c1-102">Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="797c1-102">Log File Viewer</span></span>
  <span data-ttu-id="797c1-103">O Visualizador do Arquivo de Log no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] é usado para acessar informações sobre erros e eventos capturados em arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="797c1-103">Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is used to access information about errors and events that are captured in log files.</span></span>  
  
## <a name="benefits-of-using-log-file-viewer"></a><span data-ttu-id="797c1-104">Benefícios do uso do Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="797c1-104">Benefits of using Log File Viewer</span></span>  
 <span data-ttu-id="797c1-105">Você pode exibir arquivos de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de uma instância local ou remota do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando a instância de destino estiver offline ou não iniciar.</span><span class="sxs-lookup"><span data-stu-id="797c1-105">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span> <span data-ttu-id="797c1-106">Você pode acessar os arquivos de log offline de Servidores Registrados, ou programaticamente por WMI e o WQL (Linguagem WQL) consulta.</span><span class="sxs-lookup"><span data-stu-id="797c1-106">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span> <span data-ttu-id="797c1-107">Para obter mais informações, veja [Exibir arquivos de log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="797c1-107">For more information, see [View Offline Log Files](view-offline-log-files.md).</span></span> <span data-ttu-id="797c1-108">Estes são tipos de arquivos de log que você pode acessar usando o Visualizador do Arquivo de Log:</span><span class="sxs-lookup"><span data-stu-id="797c1-108">Following are the types of log files you can access using Log File Viewer:</span></span>  
  
-   <span data-ttu-id="797c1-109">Coleta de Auditoria</span><span class="sxs-lookup"><span data-stu-id="797c1-109">Audit Collection</span></span>  
  
-   <span data-ttu-id="797c1-110">Coleta de dados</span><span class="sxs-lookup"><span data-stu-id="797c1-110">Data Collection</span></span>  
  
-   <span data-ttu-id="797c1-111">Database Mail</span><span class="sxs-lookup"><span data-stu-id="797c1-111">Database Mail</span></span>  
  
-   <span data-ttu-id="797c1-112">Histórico de Trabalhos</span><span class="sxs-lookup"><span data-stu-id="797c1-112">Job History</span></span>  
  
-   <span data-ttu-id="797c1-113">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="797c1-113">Maintenance Plans</span></span>  
  
-   <span data-ttu-id="797c1-114">Planos de Manutenção Remotos</span><span class="sxs-lookup"><span data-stu-id="797c1-114">Remote Maintenance Plans</span></span>  
  
-   <span data-ttu-id="797c1-115">SQL Server</span><span class="sxs-lookup"><span data-stu-id="797c1-115">SQL Server</span></span>  
  
-   <span data-ttu-id="797c1-116">SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="797c1-116">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="797c1-117">Windows NT (eventos do Windows que também podem ser acessados a partir do Visualizador de Eventos)</span><span class="sxs-lookup"><span data-stu-id="797c1-117">Windows NT (These are Windows events that can also be accessed from Event Viewer.)</span></span>  
  
## <a name="log-file-viewer-tasks"></a><span data-ttu-id="797c1-118">Tarefas do Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="797c1-118">Log File Viewer Tasks</span></span>  
  
|<span data-ttu-id="797c1-119">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="797c1-119">Task Description</span></span>|<span data-ttu-id="797c1-120">Tópico</span><span class="sxs-lookup"><span data-stu-id="797c1-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="797c1-121">Descreve como abrir o Visualizador do Arquivo de Log, dependendo das informações que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="797c1-121">Describes how to open Log File Viewer depending on the information that you want to view.</span></span>|[<span data-ttu-id="797c1-122">Abrir o Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="797c1-122">Open Log File Viewer</span></span>](open-log-file-viewer.md)|  
|<span data-ttu-id="797c1-123">Descreve como exibir arquivos de log offline através de servidores registrados e como verificar permissões de WMI.</span><span class="sxs-lookup"><span data-stu-id="797c1-123">Describes how to view offline log files through registered servers and how to verify WMI permissions.</span></span>|[<span data-ttu-id="797c1-124">Exibir arquivos de log offline</span><span class="sxs-lookup"><span data-stu-id="797c1-124">View Offline Log Files</span></span>](view-offline-log-files.md)|  
|<span data-ttu-id="797c1-125">Oferece ajuda F1 do Visualizador de Arquivo de Log.</span><span class="sxs-lookup"><span data-stu-id="797c1-125">Provides Log File Viewer F1 Help.</span></span>|[<span data-ttu-id="797c1-126">Ajuda F1 do Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="797c1-126">Log File Viewer F1 Help</span></span>](log-file-viewer-f1-help.md)|  
  
## <a name="see-also"></a><span data-ttu-id="797c1-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="797c1-127">See Also</span></span>  
 <span data-ttu-id="797c1-128">[Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="797c1-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="797c1-129">Log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="797c1-129">SQL Server Agent Error Log</span></span>](../../ssms/agent/sql-server-agent-error-log.md)  
  
  
