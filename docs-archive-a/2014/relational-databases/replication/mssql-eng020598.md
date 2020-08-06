---
title: MSSQL_ENG020598 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cef26001c353dea94ec9b658dfb38285231bc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679871"
---
# <a name="mssql_eng020598"></a><span data-ttu-id="41cb5-102">MSSQL_ENG020598</span><span class="sxs-lookup"><span data-stu-id="41cb5-102">MSSQL_ENG020598</span></span>
    
## <a name="message-details"></a><span data-ttu-id="41cb5-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="41cb5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41cb5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="41cb5-104">Product Name</span></span>|<span data-ttu-id="41cb5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="41cb5-105">SQL Server</span></span>|  
|<span data-ttu-id="41cb5-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="41cb5-106">Event ID</span></span>|<span data-ttu-id="41cb5-107">20598</span><span class="sxs-lookup"><span data-stu-id="41cb5-107">20598</span></span>|  
|<span data-ttu-id="41cb5-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="41cb5-108">Event Source</span></span>|<span data-ttu-id="41cb5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="41cb5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="41cb5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="41cb5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="41cb5-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="41cb5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="41cb5-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="41cb5-112">Message Text</span></span>|<span data-ttu-id="41cb5-113">A linha não foi encontrada no Assinante ao aplicar o comando replicado.</span><span class="sxs-lookup"><span data-stu-id="41cb5-113">The row was not found at the Subscriber when applying the replicated command.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41cb5-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="41cb5-114">Explanation</span></span>  
 <span data-ttu-id="41cb5-115">Esse erro ocorre na replicação transacional quando o Distribution Agent tenta atualizar uma linha no Assinante, mas a linha foi excluída ou a chave primária da linha foi alterada.</span><span class="sxs-lookup"><span data-stu-id="41cb5-115">This error is raised in transactional replication if the Distribution Agent attempts to update a row at the Subscriber, but the row has been deleted or the primary key of the row has been changed.</span></span> <span data-ttu-id="41cb5-116">Por padrão, os Assinantes de publicações transacionais devem ser tratados como somente leitura, porque as alterações não são propagadas de volta para o Publicador.</span><span class="sxs-lookup"><span data-stu-id="41cb5-116">By default, Subscribers to transactional publications should be treated as read-only, because changes are not propagated back to the Publisher.</span></span> <span data-ttu-id="41cb5-117">Para a replicação transacional, as alterações do usuário devem ser realizadas no Assinante somente se forem usadas assinaturas que podem ser atualizadas ou replicação ponto a ponto (P2P).</span><span class="sxs-lookup"><span data-stu-id="41cb5-117">For transactional replication, user changes should be made at the Subscriber only if updatable subscriptions or peer-to-peer replication is used.</span></span> <span data-ttu-id="41cb5-118">Para obter mais informações sobre essas opções, consulte [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) e [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="41cb5-118">For information about these options, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) and [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41cb5-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="41cb5-119">User Action</span></span>  
 <span data-ttu-id="41cb5-120">**Para resolver esse problema:**</span><span class="sxs-lookup"><span data-stu-id="41cb5-120">**To resolve this problem:**</span></span>  
  
1.  <span data-ttu-id="41cb5-121">Se for necessário que a replicação continue enquanto você identifica a origem do erro, especifique o parâmetro **-SkipErrors 20598** para o Agente de Distribuição.</span><span class="sxs-lookup"><span data-stu-id="41cb5-121">If replication must continue while you identify the source of the error, specify the parameter **-SkipErrors 20598** for the Distribution Agent.</span></span> <span data-ttu-id="41cb5-122">Isso permite que o agente ignore alterações que resultem no erro 20598, enquanto permite que outras alterações sejam replicadas.</span><span class="sxs-lookup"><span data-stu-id="41cb5-122">This allows the agent to skip changes that result in error 20598, while allowing other changes to be replicated.</span></span>  
  
2.  <span data-ttu-id="41cb5-123">Identifique quais linhas no Assinante foram excluídas ou possuem uma chave primária diferente daquela das linhas correspondentes no Publicador.</span><span class="sxs-lookup"><span data-stu-id="41cb5-123">Identify which rows at the Subscriber have been deleted or have a different primary key than the corresponding rows at the Publisher.</span></span> <span data-ttu-id="41cb5-124">É possível usar o [tablediff Utility](../../tools/tablediff-utility.md) para determinar quais linhas são diferentes nos bancos de dados de publicação e de assinatura.</span><span class="sxs-lookup"><span data-stu-id="41cb5-124">You can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span> <span data-ttu-id="41cb5-125">Para obter informações sobre como usar esse utilitário com bancos de dados replicados, consulte [Comparar diferenças em tabelas replicadas &#40;programação de replicação&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span><span class="sxs-lookup"><span data-stu-id="41cb5-125">For information about using this utility with replicated databases, see [Compare Replicated Tables for Differences &#40;Replication Programming&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span></span>  
  
3.  <span data-ttu-id="41cb5-126">Corrija as linhas no Assinante usando o utilitário **tablediff** ou qualquer outro método.</span><span class="sxs-lookup"><span data-stu-id="41cb5-126">Correct the rows at the Subscriber using the **tablediff** utility or another method.</span></span>  
  
4.  <span data-ttu-id="41cb5-127">(Opcional) Remova o parâmetro **-SkipErrors** .</span><span class="sxs-lookup"><span data-stu-id="41cb5-127">(Optional) Remove the **-SkipErrors** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cb5-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="41cb5-128">See Also</span></span>  
 [<span data-ttu-id="41cb5-129">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="41cb5-129">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
