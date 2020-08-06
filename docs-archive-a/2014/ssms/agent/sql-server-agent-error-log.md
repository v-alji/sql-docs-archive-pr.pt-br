---
title: Log de erros do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- messages [SQL Server], SQL Server Agent
- errors [SQL Server], logs
- SQL Server Agent, errors
ms.assetid: 0b2d6e6e-cd2d-4b8b-9fa2-2bbd2fc0da41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea9a723695c6993f4f07897f49d8014a86ce78b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680275"
---
# <a name="sql-server-agent-error-log"></a><span data-ttu-id="0fa3f-102">Log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="0fa3f-102">SQL Server Agent Error Log</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0fa3f-103">O Agent cria um log de erros que registra avisos e erros por padrão.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-103">Agent creates an error log that records warnings and errors by default.</span></span> <span data-ttu-id="0fa3f-104">Os seguintes avisos e erros são exibidos no log:</span><span class="sxs-lookup"><span data-stu-id="0fa3f-104">The following warnings and errors are displayed in the log:</span></span>  
  
-   <span data-ttu-id="0fa3f-105">Mensagens de aviso que fornecem informações sobre possíveis problemas, como "o trabalho \<*job_name*> foi excluído enquanto estava em execução".</span><span class="sxs-lookup"><span data-stu-id="0fa3f-105">Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."</span></span>  
  
-   <span data-ttu-id="0fa3f-106">Mensagens de erro que normalmente requerem intervenção de um administrador de sistema, como "Não é possível iniciar a sessão de email".</span><span class="sxs-lookup"><span data-stu-id="0fa3f-106">Error messages that usually require intervention by a system administrator, such as "Unable to start mail session."</span></span> <span data-ttu-id="0fa3f-107">As mensagens de erro podem ser enviadas a um usuário ou computador específico por meio de **net send**.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-107">Error messages can be sent to a specific user or computer by **net send**.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0fa3f-108">mantém até nove logs de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-108">maintains up to nine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs.</span></span> <span data-ttu-id="0fa3f-109">Cada log arquivado tem uma extensão que indica sua idade relativa.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-109">Each archived log has an extension that indicates the relative age of the log.</span></span> <span data-ttu-id="0fa3f-110">Por exemplo, uma extensão .1 indica o log de erros arquivado mais recentemente e a extensão .9, o mais antigo.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-110">For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.</span></span>  
  
 <span data-ttu-id="0fa3f-111">Por padrão, mensagens de rastreamento de execução não são gravadas no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, pois elas podem lotá-lo.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-111">By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log, because they can fill it.</span></span> <span data-ttu-id="0fa3f-112">Quando o log de erros fica cheio, sua capacidade de selecionar e analisar erros mais difíceis é reduzida.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-112">When the error log is full, your ability to select and analyze more difficult errors is reduced.</span></span> <span data-ttu-id="0fa3f-113">Como o log é somado à carga de processamento do servidor, é importante considerar com atenção o valor obtido ao capturar mensagens de rastreamento de execução para o log de erros.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-113">Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log.</span></span> <span data-ttu-id="0fa3f-114">Geralmente, é melhor capturar todas as mensagens apenas quando você estiver depurando um problema específico.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-114">Generally, it is best to capture all messages only when you are debugging a specific problem.</span></span>  
  
 <span data-ttu-id="0fa3f-115">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é interrompido, você pode modificar o local do log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log.</span></span> <span data-ttu-id="0fa3f-116">Quando o log de erros está vazio, não é possível abri-lo.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-116">When the error log is empty, the log cannot be opened.</span></span> <span data-ttu-id="0fa3f-117">É possível reciclar o log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a qualquer hora, sem ter que interromper o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0fa3f-117">You can cycle the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="0fa3f-118">**Para exibir o log de erros do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="0fa3f-118">**To view the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="0fa3f-119">Exibir o log de erros do SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0fa3f-119">View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](view-sql-server-agent-error-log-sql-server-management-studio.md) 
  
 <span data-ttu-id="0fa3f-120">**Para renomear o log de erros do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="0fa3f-120">**To rename a SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="0fa3f-121">Renomear um log de erros do SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0fa3f-121">Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
 <span data-ttu-id="0fa3f-122">**Para enviar mensagens de erro do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="0fa3f-122">**To send SQL Server Agent error messages**</span></span>  
  
-   [<span data-ttu-id="0fa3f-123">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="0fa3f-123">Send SQL Server Agent Error Messages</span></span>](send-sql-server-agent-error-messages.md)  
  
 <span data-ttu-id="0fa3f-124">**Para gravar mensagens de rastreamento de execução no log de erros do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="0fa3f-124">**To write execution trace messages to the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="0fa3f-125">Gravar mensagens de rastreamento de execução no log de erros do SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0fa3f-125">Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
  
  
