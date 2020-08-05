---
title: MSSQL_ENG014152 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 615b9cf2996653d86c44d6e43a83e01e8287b110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572503"
---
# <a name="mssql_eng014152"></a><span data-ttu-id="7ffc7-102">MSSQL_ENG014152</span><span class="sxs-lookup"><span data-stu-id="7ffc7-102">MSSQL_ENG014152</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7ffc7-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="7ffc7-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ffc7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7ffc7-104">Product Name</span></span>|<span data-ttu-id="7ffc7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ffc7-105">SQL Server</span></span>|  
|<span data-ttu-id="7ffc7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7ffc7-106">Event ID</span></span>|<span data-ttu-id="7ffc7-107">14152</span><span class="sxs-lookup"><span data-stu-id="7ffc7-107">14152</span></span>|  
|<span data-ttu-id="7ffc7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7ffc7-108">Event Source</span></span>|<span data-ttu-id="7ffc7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ffc7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ffc7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7ffc7-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7ffc7-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7ffc7-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7ffc7-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7ffc7-112">Message Text</span></span>|<span data-ttu-id="7ffc7-113">Replicação-%s: agente %s agendado para tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-113">Replication-%s: agent %s scheduled for retry.</span></span> <span data-ttu-id="7ffc7-114">%s</span><span class="sxs-lookup"><span data-stu-id="7ffc7-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ffc7-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="7ffc7-115">Explanation</span></span>  
 <span data-ttu-id="7ffc7-116">O agente de replicação especificado foi programado para repetir a operação solicitada.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-116">The specified replication agent has been scheduled to retry the requested operation.</span></span> <span data-ttu-id="7ffc7-117">O processo continua repetindo até alcançar o número máximo configurado de tentativas de repetição para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-117">The process continues to retry until it reaches the configured maximum number of retry attempts for the job step.</span></span>  
  
 <span data-ttu-id="7ffc7-118">Normalmente, uma repetição ocorre devido a um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="7ffc7-118">A retry typically occurs because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="7ffc7-119">O valor **QueryTimeout** é excedido.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-119">The **QueryTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="7ffc7-120">O valor **LoginTimeout** é excedido.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-120">The **LoginTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="7ffc7-121">O processo de replicação foi escolhido como uma vítima de deadlock.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-121">The replication process was chosen as a deadlock victim.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ffc7-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7ffc7-122">User Action</span></span>  
 <span data-ttu-id="7ffc7-123">Se a mensagem de repetição não for frequente, nenhuma ação é exigida do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-123">If the retry message is infrequent, no user action is required.</span></span>  
  
 <span data-ttu-id="7ffc7-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) para exibir a definição atual do número máximo de vezes que a etapa **Executar agente** do agente de replicação especificado será repetida.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) to view the current setting for the maximum number of times the **Run agent** step for the specified replication agent will retry.</span></span> <span data-ttu-id="7ffc7-125">Você pode usar o **@retry_attempts** parâmetro do procedimento armazenado [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) para ajustar o número de vezes que uma etapa de trabalho tenta novamente.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-125">You can use the **@retry_attempts** parameter of the [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) stored procedure to adjust the number of times a job step retries.</span></span>  
  
 <span data-ttu-id="7ffc7-126">Se a mensagem de repetição ocorrer com frequência, você deverá solucionar o problema com base na mensagem que está causando a repetição.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-126">If the retry message recurs frequently, troubleshoot the issue based on the message that is causing the retry.</span></span> <span data-ttu-id="7ffc7-127">Verifique o histórico do agente para mensagens que indicam por que a nova tentativa teve que ser programada.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-127">Check the agent's history for messages that indicate why the retry had to be scheduled.</span></span> <span data-ttu-id="7ffc7-128">Em alguns casos, talvez seja necessário habilitar o log mais detalhado do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-128">In some cases you may have to enable more detailed logging for your replication agent.</span></span> <span data-ttu-id="7ffc7-129">Para obter mais informações sobre como configurar o log para replicação, consulte o artigo [312292](https://support.microsoft.com/kb/312292)na Base de Dados de Conhecimento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ffc7-129">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ffc7-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ffc7-130">See Also</span></span>  
 [<span data-ttu-id="7ffc7-131">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="7ffc7-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
