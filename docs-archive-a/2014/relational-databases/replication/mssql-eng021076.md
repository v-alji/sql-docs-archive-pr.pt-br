---
title: MSSQL_ENG021076 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4161428767ce78726436c0cf794f5250140d35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679868"
---
# <a name="mssql_eng021076"></a><span data-ttu-id="8d075-102">MSSQL_ENG021076</span><span class="sxs-lookup"><span data-stu-id="8d075-102">MSSQL_ENG021076</span></span>
    
## <a name="message-details"></a><span data-ttu-id="8d075-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="8d075-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d075-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8d075-104">Product Name</span></span>|<span data-ttu-id="8d075-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d075-105">SQL Server</span></span>|  
|<span data-ttu-id="8d075-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8d075-106">Event ID</span></span>|<span data-ttu-id="8d075-107">21076</span><span class="sxs-lookup"><span data-stu-id="8d075-107">21076</span></span>|  
|<span data-ttu-id="8d075-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8d075-108">Event Source</span></span>|<span data-ttu-id="8d075-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8d075-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8d075-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8d075-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="8d075-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8d075-111">Symbolic Name</span></span>||  
|<span data-ttu-id="8d075-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8d075-112">Message Text</span></span>|<span data-ttu-id="8d075-113">O instantâneo inicial do artigo '%s' ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="8d075-113">The initial snapshot for article '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d075-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="8d075-114">Explanation</span></span>  
 <span data-ttu-id="8d075-115">O erro MSSQL_ENG021076 pode ser gerado se o Distribution Agent for iniciado antes do Snapshot Agent terminar de gerar o instantâneo.</span><span class="sxs-lookup"><span data-stu-id="8d075-115">Error MSSQL_ENG021076 can be raised if the Distribution Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span> <span data-ttu-id="8d075-116">Esse erro só será gerado se a publicação possuir um único artigo.</span><span class="sxs-lookup"><span data-stu-id="8d075-116">This error is raised only if the publication contains a single article.</span></span> <span data-ttu-id="8d075-117">Se a publicação possuir mais de um artigo, será gerado o erro MSSQL_ENG021075.</span><span class="sxs-lookup"><span data-stu-id="8d075-117">If the publication contains more than one article, MSSQL_ENG021075 is raised instead.</span></span> <span data-ttu-id="8d075-118">Para obter mais informações, consulte [MSSQL_ENG021075](mssql-eng021075.md).</span><span class="sxs-lookup"><span data-stu-id="8d075-118">For more information, see [MSSQL_ENG021075](mssql-eng021075.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d075-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8d075-119">User Action</span></span>  
 <span data-ttu-id="8d075-120">Se o Snapshot Agent da publicação não for iniciado até que a assinatura seja criada, ou se não tiver sido iniciado desde que você optou por reiniciar a assinatura, inicie o Snapshot Agent e aguarde sua conclusão antes de iniciar o Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="8d075-120">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent.</span></span> <span data-ttu-id="8d075-121">Para obter mais informações, consulte [Create and Apply the Snapshot](create-and-apply-the-snapshot.md) (Criar e aplicar o instantâneo).</span><span class="sxs-lookup"><span data-stu-id="8d075-121">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="8d075-122">Se o Agente de Instantâneo não for concluído, verifique o histórico do Agente de Instantâneo em relação a erros e faça o diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="8d075-122">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="8d075-123">Para obter informações sobre exibir detalhes de status e de erro do agente no Replication Monitor, confira [Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8d075-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="8d075-124">Se o erro continuar ocorrendo, aumente o log do agente e especifique um arquivo de saída para o log.</span><span class="sxs-lookup"><span data-stu-id="8d075-124">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="8d075-125">Dependendo do contexto do erro, isso poderá fornecer as etapas que levaram ao erro e/ou as mensagens de erros adicionais.</span><span class="sxs-lookup"><span data-stu-id="8d075-125">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d075-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d075-126">See Also</span></span>  
 [<span data-ttu-id="8d075-127">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="8d075-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
