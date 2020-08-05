---
title: Exibir o estado de um banco de dados espelhado (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc691e8b746a816ab88448e3399aebad6d8844e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572678"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a><span data-ttu-id="7c7c6-102">Exibir o estado de um banco de dados espelho (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7c7c6-102">View the State of a Mirrored Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7c7c6-103">Durante uma sessão de espelhamento de banco de dados, você pode exibir o estado na página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="7c7c6-103">During a database mirroring session, you can view the status on the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a><span data-ttu-id="7c7c6-104">Para exibir o estado de uma sessão de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="7c7c6-104">To view the status of a database mirroring session</span></span>  
  
1.  <span data-ttu-id="7c7c6-105">Depois de se conectar à instância do servidor principal, no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-105">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7c7c6-106">Expanda os **Bancos de Dados**e selecione o banco de dados a ser espelhado.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-106">Expand **Databases**, and select the database to be mirrored.</span></span>  
  
3.  <span data-ttu-id="7c7c6-107">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-107">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="7c7c6-108">Isso abre a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="7c7c6-108">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="7c7c6-109">Depois do início do espelhamento, o painel **Status** exibe o status da sessão de espelhamento de banco de dados a partir de quando você selecionou a página **Espelhamento** ou clicou o botão **Atualizar** .</span><span class="sxs-lookup"><span data-stu-id="7c7c6-109">After mirroring begins, the **Status** panel displays the status of the database mirroring session as of when you selected the **Mirroring** page or clicked the **Refresh** button.</span></span> <span data-ttu-id="7c7c6-110">Os possíveis estados são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="7c7c6-110">The possible states are as follows:</span></span>  
  
    |<span data-ttu-id="7c7c6-111">Estados</span><span class="sxs-lookup"><span data-stu-id="7c7c6-111">States</span></span>|<span data-ttu-id="7c7c6-112">Explicação</span><span class="sxs-lookup"><span data-stu-id="7c7c6-112">Explanation</span></span>|  
    |------------|-----------------|  
    |\<blank>|<span data-ttu-id="7c7c6-113">Não existe nenhuma sessão de espelhamento de banco de dados e não há nenhuma atividade a ser reportada na página **Espelhamento** .</span><span class="sxs-lookup"><span data-stu-id="7c7c6-113">No database mirroring session exists and there is no activity to report on the **Mirroring** page.</span></span>|  
    |<span data-ttu-id="7c7c6-114">Em Pausa</span><span class="sxs-lookup"><span data-stu-id="7c7c6-114">Paused</span></span>|<span data-ttu-id="7c7c6-115">O banco de dados principal está em execução mas não está enviando nenhum log ao servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-115">The principal database is running but is not sending any logs to the mirror server.</span></span> <span data-ttu-id="7c7c6-116">A cópia espelhada do banco de dados não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-116">The mirror copy of the database is not available.</span></span>|  
    |<span data-ttu-id="7c7c6-117">Nenhuma conexão</span><span class="sxs-lookup"><span data-stu-id="7c7c6-117">No connection</span></span>|<span data-ttu-id="7c7c6-118">A instância do servidor principal não pode conectar com seu parceiro ou com a instância de servidor testemunha (se houver)</span><span class="sxs-lookup"><span data-stu-id="7c7c6-118">The principal server instance cannot connect to its partner or to the witness server instance (if any)</span></span>|  
    |<span data-ttu-id="7c7c6-119">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="7c7c6-119">Synchronizing</span></span>|<span data-ttu-id="7c7c6-120">O conteúdo do banco de dados espelho está ficando atrás do conteúdo do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-120">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="7c7c6-121">A instância do servidor principal está enviando registros de log para a instância do servidor espelho, a qual está aplicando as alterações ao banco de dados espelho para rolagem para frente.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-121">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="7c7c6-122">Ao início de uma sessão de espelhamento de banco de dados, os bancos de dados espelho e principal encontram-se no estado de sincronização.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-122">At the start of a database mirroring session, the mirror and principal databases are in the synchronizing state.</span></span>|  
    |<span data-ttu-id="7c7c6-123">Failover</span><span class="sxs-lookup"><span data-stu-id="7c7c6-123">Failover</span></span>|<span data-ttu-id="7c7c6-124">Na instância de servidor principal, um failover manual (troca de papel) começou mas ainda não foi aceito pelo espelho.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-124">On the principal server instance, a manual failover (role swap) has begun but has not yet accepted by the mirror.</span></span>|  
    |<span data-ttu-id="7c7c6-125">Sincronizado</span><span class="sxs-lookup"><span data-stu-id="7c7c6-125">Synchronized</span></span>|<span data-ttu-id="7c7c6-126">O banco de dados espelho contém os mesmos dados que o banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-126">The mirror database contains the same data as the principal database.</span></span> <span data-ttu-id="7c7c6-127">Failover manuais e automáticos *apenas* são possíveis no estado sincronizado.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-127">Manual and automatic failover are possible *only* in the synchronized state.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c7c6-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c7c6-128">See Also</span></span>  
 [<span data-ttu-id="7c7c6-129">Estados de espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7c7c6-129">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  
