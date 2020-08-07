---
title: MSSQL_ENG020557 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020557 error
ms.assetid: c43c6952-5b60-4347-b881-11a0004dce24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45c24d453eb95abaa967ae65ceb5934b7dee969e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583539"
---
# <a name="mssql_eng020557"></a><span data-ttu-id="9979f-102">MSSQL_ENG020557</span><span class="sxs-lookup"><span data-stu-id="9979f-102">MSSQL_ENG020557</span></span>
    
## <a name="message-details"></a><span data-ttu-id="9979f-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="9979f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9979f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9979f-104">Product Name</span></span>|<span data-ttu-id="9979f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9979f-105">SQL Server</span></span>|  
|<span data-ttu-id="9979f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9979f-106">Event ID</span></span>|<span data-ttu-id="9979f-107">20557</span><span class="sxs-lookup"><span data-stu-id="9979f-107">20557</span></span>|  
|<span data-ttu-id="9979f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9979f-108">Event Source</span></span>|<span data-ttu-id="9979f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9979f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9979f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9979f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="9979f-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9979f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="9979f-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9979f-112">Message Text</span></span>|<span data-ttu-id="9979f-113">Desligamento do agente.</span><span class="sxs-lookup"><span data-stu-id="9979f-113">Agent shutdown.</span></span> <span data-ttu-id="9979f-114">Para obter mais informações, consulte o histórico de trabalho do SQL Server Agent relacionado ao trabalho '%s'.</span><span class="sxs-lookup"><span data-stu-id="9979f-114">For more information, see the SQL Server Agent job history for job '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9979f-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="9979f-115">Explanation</span></span>  
 <span data-ttu-id="9979f-116">Um agente de replicação foi desligado sem gravar um motivo para a tabela de histórico apropriada ou, então, o agente foi desligado no meio de um processo.</span><span class="sxs-lookup"><span data-stu-id="9979f-116">A replication agent has shut down without writing a reason to the appropriate history table, or the agent was shut down while in the middle of a process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9979f-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9979f-117">User Action</span></span>  
  
-   <span data-ttu-id="9979f-118">Reinicie o agente para verificar se agora será possível executá-lo sem falhas.</span><span class="sxs-lookup"><span data-stu-id="9979f-118">Restart the agent to see whether it will now run without failures.</span></span> <span data-ttu-id="9979f-119">Para obter mais informações, consulte [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Conceitos dos executáveis do agente de replicação](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="9979f-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="9979f-120">Verifique o histórico de agente e o histórico de trabalho para outros erros que aconteceram quase no mesmo momento.</span><span class="sxs-lookup"><span data-stu-id="9979f-120">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="9979f-121">Para obter informações sobre como exibir detalhes de status e de erro do agente no Replication Monitor, confira [Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9979f-121">For information about how to view agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>
-   <span data-ttu-id="9979f-122">Verifique se a conectividade básica está funcionado entre os computadores acessados pelo agente e, em seguida, conecte-se a cada computador usando um utilitário, como o **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="9979f-122">Verify that basic connectivity is working between the computers that are accessed by the agent, and then connect to each computer by using a utility, such as the **sqlcmd** utility.</span></span> <span data-ttu-id="9979f-123">Ao se conectar, use a mesma conta com a qual o agente faz conexões.</span><span class="sxs-lookup"><span data-stu-id="9979f-123">When you connect, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="9979f-124">Para obter mais informações sobre as permissões necessárias para cada conta de agente, consulte [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="9979f-124">For more information about the permissions that are required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="9979f-125">Se o erro ocorrer ao criar ou aplicar um instantâneo, verifique os arquivos no diretório de instantâneos com relação a erros.</span><span class="sxs-lookup"><span data-stu-id="9979f-125">If the error occurs while you are creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="9979f-126">Se o erro continuar ocorrendo, aumente o log do agente e especifique um arquivo de saída para o log.</span><span class="sxs-lookup"><span data-stu-id="9979f-126">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="9979f-127">Dependendo do contexto do erro, isso poderá fornecer as etapas que levam ao erro e às mensagens de erro adicionais.</span><span class="sxs-lookup"><span data-stu-id="9979f-127">Depending on the context of the error, this could provide the steps leading up to the error and additional error messages.</span></span> <span data-ttu-id="9979f-128">Para obter mais informações sobre como configurar o log para replicação, consulte o artigo [312292](https://support.microsoft.com/kb/312292)na Base de Dados de Conhecimento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9979f-128">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9979f-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9979f-129">See Also</span></span>  
 [<span data-ttu-id="9979f-130">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="9979f-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
