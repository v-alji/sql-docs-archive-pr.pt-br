---
title: MSSQL_ENG021075 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021075 error
ms.assetid: c8c29543-d1f6-49d5-b6c8-e8c3aa373090
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f2428038326681f5f8eb877e5c3017ced30f00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576292"
---
# <a name="mssql_eng021075"></a><span data-ttu-id="2b233-102">MSSQL_ENG021075</span><span class="sxs-lookup"><span data-stu-id="2b233-102">MSSQL_ENG021075</span></span>
    
## <a name="message-details"></a><span data-ttu-id="2b233-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="2b233-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b233-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2b233-104">Product Name</span></span>|<span data-ttu-id="2b233-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b233-105">SQL Server</span></span>|  
|<span data-ttu-id="2b233-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2b233-106">Event ID</span></span>|<span data-ttu-id="2b233-107">21075</span><span class="sxs-lookup"><span data-stu-id="2b233-107">21075</span></span>|  
|<span data-ttu-id="2b233-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2b233-108">Event Source</span></span>|<span data-ttu-id="2b233-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b233-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b233-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2b233-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="2b233-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2b233-111">Symbolic Name</span></span>||  
|<span data-ttu-id="2b233-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2b233-112">Message Text</span></span>|<span data-ttu-id="2b233-113">O instantâneo inicial da publicação '%s' ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="2b233-113">The initial snapshot for publication '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b233-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="2b233-114">Explanation</span></span>  
 <span data-ttu-id="2b233-115">O erro MSSQL_ENG021075 pode ser gerado se o Distribution Agent ou o Merge Agent for iniciado antes do Snapshot Agent terminar de gerar o instantâneo.</span><span class="sxs-lookup"><span data-stu-id="2b233-115">Error MSSQL_ENG021075 is raised if the Distribution Agent or Merge Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b233-116">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2b233-116">User Action</span></span>  
 <span data-ttu-id="2b233-117">Se o Snapshot Agent da publicação não for iniciado até que a assinatura seja criada, ou se não tiver sido iniciado desde que você optou por reiniciar a assinatura, inicie o Snapshot Agent e aguarde o início do Distribution Agent ou do Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="2b233-117">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent or Merge Agent.</span></span> <span data-ttu-id="2b233-118">Para obter mais informações, consulte [Create and Apply the Snapshot](create-and-apply-the-snapshot.md) (Criar e aplicar o instantâneo).</span><span class="sxs-lookup"><span data-stu-id="2b233-118">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="2b233-119">Se o Agente de Instantâneo não for concluído, verifique o histórico do Agente de Instantâneo em relação a erros e faça o diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="2b233-119">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="2b233-120">Para obter informações sobre exibir detalhes de status e de erro do agente no Replication Monitor, confira [Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="2b233-120">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="2b233-121">Se o erro continuar ocorrendo, aumente o log do agente e especifique um arquivo de saída para o log.</span><span class="sxs-lookup"><span data-stu-id="2b233-121">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="2b233-122">Dependendo do contexto do erro, isso poderá fornecer as etapas que levaram ao erro e/ou as mensagens de erros adicionais.</span><span class="sxs-lookup"><span data-stu-id="2b233-122">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b233-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b233-123">See Also</span></span>  
 [<span data-ttu-id="2b233-124">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="2b233-124">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
