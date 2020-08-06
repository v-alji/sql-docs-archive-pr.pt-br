---
title: Informações da publicação, tokens de rastreamento (publicação transacional, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.tracertokens.f1
ms.assetid: a115ba95-17ae-45df-91bd-5a1a35f3745f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af84ab9b9122a55367780976056ce95aa597f62a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683470"
---
# <a name="publication-information-tracer-tokens-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="6ae76-102">Informações da Publicação, Tokens de Rastreamento (publicação transacional, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="6ae76-102">Publication Information, Tracer Tokens (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="6ae76-103">A guia **Tokens de Rastreamento** permite validar conexões e medir a latência de um sistema que usa replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="6ae76-103">The **Tracer Tokens** tab allows you to validate connections and to measure the latency of a system that uses transactional replication.</span></span> <span data-ttu-id="6ae76-104">Um token (uma quantidade pequena de dados) é gravado no log de transações do banco de dados de publicação, marcado como se fosse uma transação replicada comum e enviado pelo sistema, permitindo um cálculo de:</span><span class="sxs-lookup"><span data-stu-id="6ae76-104">A token (a small amount of data) is written to the transaction log of the publication database, marked as though it were a typical replicated transaction, and sent through the system, allowing a calculation of:</span></span>  
  
-   <span data-ttu-id="6ae76-105">O tempo decorrido entre a confirmação de uma transação no Publicador e o comando correspondente inserido no banco de dados de distribuição no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6ae76-105">How much time elapses between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span>  
  
-   <span data-ttu-id="6ae76-106">O tempo decorrido entre um comando inserido no banco de dados de distribuição e a transação correspondente confirmada no Assinante.</span><span class="sxs-lookup"><span data-stu-id="6ae76-106">How much time elapses between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span>  
  
 <span data-ttu-id="6ae76-107">Desses cálculos, você pode responder várias perguntas, enquanto incluindo:</span><span class="sxs-lookup"><span data-stu-id="6ae76-107">From these calculations, you can answer a number of questions, including:</span></span>  
  
-   <span data-ttu-id="6ae76-108">Quais Assinantes levam mais tempo para receber uma alteração do Publicador?</span><span class="sxs-lookup"><span data-stu-id="6ae76-108">Which Subscribers take the longest to receive a change from the Publisher?</span></span>  
  
-   <span data-ttu-id="6ae76-109">Dos Assinantes esperados para receber o token de rastreamento quais, se houver, ainda não receberam?</span><span class="sxs-lookup"><span data-stu-id="6ae76-109">Of the Subscribers expected to receive the tracer token, which, if any, have not received it?</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ae76-110">Opções</span><span class="sxs-lookup"><span data-stu-id="6ae76-110">Options</span></span>  
 <span data-ttu-id="6ae76-111">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="6ae76-111">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="6ae76-112">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="6ae76-112">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="6ae76-113">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="6ae76-113">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="6ae76-114">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="6ae76-114">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="6ae76-115">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="6ae76-115">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="6ae76-116">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="6ae76-116">Filter settings are specific to each grid.</span></span> <span data-ttu-id="6ae76-117">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="6ae76-117">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="6ae76-118">**Inserir Rastreador**</span><span class="sxs-lookup"><span data-stu-id="6ae76-118">**Insert Tracer**</span></span>  
 <span data-ttu-id="6ae76-119">Clique para inserir um token de rastreamento no log de transações no Publicador.</span><span class="sxs-lookup"><span data-stu-id="6ae76-119">Click to insert a tracer token in the transaction log at the Publisher.</span></span>  
  
 <span data-ttu-id="6ae76-120">**Hora de inserção**</span><span class="sxs-lookup"><span data-stu-id="6ae76-120">**Time inserted**</span></span>  
 <span data-ttu-id="6ae76-121">Selecione uma hora, na qual um token de rastreamento foi inserido, para exibir informações de latência a partir daquela hora.</span><span class="sxs-lookup"><span data-stu-id="6ae76-121">Select a time at which a tracer token was inserted to display latency information from that time.</span></span> <span data-ttu-id="6ae76-122">Por padrão, informações da hora mais recente serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="6ae76-122">By default, information from the most recent time is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ae76-123">Informações de token de rastreamento são retidas para o mesmo período de tempo que outros dados históricos, os quais são governados pelo período de retenção de histórico do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="6ae76-123">Tracer token information is retained for the same time period as other historical data, which is governed by the history retention period of the distribution database.</span></span> <span data-ttu-id="6ae76-124">Para obter informações sobre como alterar as propriedades do banco de dados de distribuição, consulte [Exibir e modificar as propriedades do Distribuidor e do Publicador](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6ae76-124">For information about changing distribution database properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
 <span data-ttu-id="6ae76-125">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="6ae76-125">**Subscription**</span></span>  
 <span data-ttu-id="6ae76-126">O nome de cada assinatura na publicação.</span><span class="sxs-lookup"><span data-stu-id="6ae76-126">The name of each subscription to the publication.</span></span>  
  
 <span data-ttu-id="6ae76-127">**Publicador para Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="6ae76-127">**Publisher to Distributor**</span></span>  
 <span data-ttu-id="6ae76-128">O tempo decorrido entre a confirmação de uma transação no Publicador e o comando correspondente inserido no banco de dados de distribuição no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6ae76-128">The elapsed time between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span> <span data-ttu-id="6ae76-129">Um valor **Pendente** indica que o token ainda não alcançou o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6ae76-129">A value of **Pending** indicates that the token has not yet reached the Distributor.</span></span> <span data-ttu-id="6ae76-130">Se o estado pendente persistir, verifique se o Log Reader Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="6ae76-130">If the pending state persists, ensure that the Log Reader Agent is running.</span></span>  
  
 <span data-ttu-id="6ae76-131">**Distribuidor para Assinante**</span><span class="sxs-lookup"><span data-stu-id="6ae76-131">**Distributor to Subscriber**</span></span>  
 <span data-ttu-id="6ae76-132">O tempo decorrido entre um comando inserido no banco de dados de distribuição e a transação correspondente confirmada no Assinante.</span><span class="sxs-lookup"><span data-stu-id="6ae76-132">The elapsed time between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span> <span data-ttu-id="6ae76-133">Um valor **Pendente** indica que o token ainda não alcançou o Assinante.</span><span class="sxs-lookup"><span data-stu-id="6ae76-133">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span> <span data-ttu-id="6ae76-134">Se o estado pendente persistir, verifique se o Distribution Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="6ae76-134">If the pending state persists, ensure that the Distribution Agent is running.</span></span>  
  
 <span data-ttu-id="6ae76-135">**Latência total**</span><span class="sxs-lookup"><span data-stu-id="6ae76-135">**Total Latency**</span></span>  
 <span data-ttu-id="6ae76-136">O tempo decorrido entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="6ae76-136">The elapsed time between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="6ae76-137">Isso representa a latência completa do sistema de replicação para esse Assinante neste momento.</span><span class="sxs-lookup"><span data-stu-id="6ae76-137">This represents the end-to-end latency of the replication system for this Subscriber at this time.</span></span> <span data-ttu-id="6ae76-138">Um valor **Pendente** indica que o token ainda não alcançou o Assinante.</span><span class="sxs-lookup"><span data-stu-id="6ae76-138">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae76-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ae76-139">See Also</span></span>  
 <span data-ttu-id="6ae76-140">[Iniciar e interromper um agente de replicação &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6ae76-140">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="6ae76-141">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6ae76-141">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="6ae76-142">[Medir a latência e validar conexões para replicação transacional](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="6ae76-142">[Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span></span>  
 <span data-ttu-id="6ae76-143">[Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6ae76-143">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="6ae76-144">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="6ae76-144">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="6ae76-145">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="6ae76-145">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
