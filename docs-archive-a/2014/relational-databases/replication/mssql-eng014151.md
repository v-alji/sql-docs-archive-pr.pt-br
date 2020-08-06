---
title: MSSQL_ENG014151 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014151 error
ms.assetid: 54b45e70-46b3-4c7a-a5bf-06f6dd028ceb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2796451f6f681cfb0ce529ed44a946c34135649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569360"
---
# <a name="mssql_eng014151"></a><span data-ttu-id="a767b-102">MSSQL_ENG014151</span><span class="sxs-lookup"><span data-stu-id="a767b-102">MSSQL_ENG014151</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a767b-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="a767b-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a767b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a767b-104">Product Name</span></span>|<span data-ttu-id="a767b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a767b-105">SQL Server</span></span>|  
|<span data-ttu-id="a767b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a767b-106">Event ID</span></span>|<span data-ttu-id="a767b-107">14151</span><span class="sxs-lookup"><span data-stu-id="a767b-107">14151</span></span>|  
|<span data-ttu-id="a767b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a767b-108">Event Source</span></span>|<span data-ttu-id="a767b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a767b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a767b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a767b-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a767b-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a767b-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a767b-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a767b-112">Message Text</span></span>|<span data-ttu-id="a767b-113">Replicação-%s: falha no agente %s.</span><span class="sxs-lookup"><span data-stu-id="a767b-113">Replication-%s: agent %s failed.</span></span> <span data-ttu-id="a767b-114">%s</span><span class="sxs-lookup"><span data-stu-id="a767b-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a767b-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="a767b-115">Explanation</span></span>  
 <span data-ttu-id="a767b-116">Este erro ocorre para qualquer falha de agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="a767b-116">This error is raised for any replication agent failure.</span></span> <span data-ttu-id="a767b-117">O texto ao término da mensagem depende do contexto da falha.</span><span class="sxs-lookup"><span data-stu-id="a767b-117">The text at the end of the message depends on the context of the failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a767b-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a767b-118">User Action</span></span>  
 <span data-ttu-id="a767b-119">Este erro pode acontecer em várias situações; use as seguintes abordagens, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="a767b-119">This error can occur in a number of situations; use the following approaches as necessary:</span></span>  
  
-   <span data-ttu-id="a767b-120">Reinicie o agente com falha para verificar se será possível executá-lo sem falhas agora.</span><span class="sxs-lookup"><span data-stu-id="a767b-120">Restart the failed agent to see if it will now run without failures.</span></span> <span data-ttu-id="a767b-121">Para obter mais informações, consulte [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Conceitos dos executáveis do agente de replicação](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-121">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="a767b-122">Verifique o histórico de agente e o histórico de trabalho para outros erros que aconteceram quase no mesmo momento.</span><span class="sxs-lookup"><span data-stu-id="a767b-122">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="a767b-123">Para obter informações sobre exibir detalhes de status e de erro do agente no Replication Monitor, confira [Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="a767b-124">Verifique se a conectividade básica está funcionado entre os computadores acessados pelo agente e, depois, conecte-se a cada computador com um utilitário como [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-124">Verify that basic connectivity is working between the computers accessed by the agent, and then connect to each computer with a utility like the [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="a767b-125">Ao se conectar, use a mesma conta com a qual o agente faz conexões.</span><span class="sxs-lookup"><span data-stu-id="a767b-125">When connecting, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="a767b-126">Para obter mais informações sobre as permissões exigidas para cada conta de agente, consulte [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-126">For more information about the permissions required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="a767b-127">Se o erro ocorrer ao criar ou aplicar um instantâneo, verifique os arquivos no diretório de instantâneos para erros.</span><span class="sxs-lookup"><span data-stu-id="a767b-127">If the error occurs while creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="a767b-128">Se o erro continuar ocorrendo, aumente o log do agente e especifique um arquivo de saída para o log.</span><span class="sxs-lookup"><span data-stu-id="a767b-128">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="a767b-129">Dependendo do contexto do erro, isso poderá fornecer as etapas que levaram ao erro e/ou as mensagens de erros adicionais.</span><span class="sxs-lookup"><span data-stu-id="a767b-129">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a767b-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a767b-130">See Also</span></span>  
 <span data-ttu-id="a767b-131">[Administração do agente de replicação](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="a767b-131">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="a767b-132">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a767b-132">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="a767b-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="a767b-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="a767b-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="a767b-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="a767b-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="a767b-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="a767b-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="a767b-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="a767b-137">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="a767b-137">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
