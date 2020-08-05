---
title: Criação de perfil de dados e notificações no DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a778bb5b-8e35-4a7b-b04a-ae2b46dec21b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cd59f0d2efc35eee62a974ea6649c774e7c0e453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570879"
---
# <a name="data-profiling-and-notifications-in-dqs"></a><span data-ttu-id="e4de0-102">Perfil de dados e notificações no DQS</span><span class="sxs-lookup"><span data-stu-id="e4de0-102">Data Profiling and Notifications in DQS</span></span>
  <span data-ttu-id="e4de0-103">A criação do perfil de dados no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) é o processo de analisar os dados em uma fonte de dados existente e exibir estatísticas sobre os dados nas atividades do DQS.</span><span class="sxs-lookup"><span data-stu-id="e4de0-103">Data profiling in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) is the process of analyzing the data in an existing data source, and displaying statistics about the data in DQS activities.</span></span> <span data-ttu-id="e4de0-104">Isso fornece a você medições automatizadas da qualidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="e4de0-104">It provides you with automated measurements of data quality.</span></span> <span data-ttu-id="e4de0-105">A criação de perfil do DQS está integrada ao gerenciamento de conhecimento do DQS e aos projetos de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="e4de0-105">DQS profiling is integrated into DQS knowledge management and data-quality projects.</span></span> <span data-ttu-id="e4de0-106">É dinâmica e ajustável.</span><span class="sxs-lookup"><span data-stu-id="e4de0-106">It is dynamic and adjustable.</span></span> <span data-ttu-id="e4de0-107">A criação de perfil tem dois objetivos principais: primeiro, orientá-lo durante os processos de qualidade de dados e dar suporte às suas decisões e, segundo, avaliar a efetividade dos processos.</span><span class="sxs-lookup"><span data-stu-id="e4de0-107">Profiling has two major goals: first, to guide you through data quality processes and support your decisions, and second, to assess the effectiveness of the processes.</span></span> <span data-ttu-id="e4de0-108">A criação de perfil do DQS tem os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="e4de0-108">The DQS profiling process has the following benefits:</span></span>  
  
-   <span data-ttu-id="e4de0-109">A criação de perfil fornece informações sobre a qualidade da sua fonte de dados e o ajuda a identificar problemas de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="e4de0-109">Profiling provides insight into the quality of your source data, and helps you identify data quality issues.</span></span>  
  
-   <span data-ttu-id="e4de0-110">A criação de perfil avalia a eficácia dos processos de qualidade de dados, orientando você na descoberta da base de dados de conhecimento, limpeza de dados, política de correspondência e trabalho de correspondência.</span><span class="sxs-lookup"><span data-stu-id="e4de0-110">Profiling assesses the effectiveness of data quality processes, guiding you in your knowledge discovery, data cleansing, matching policy, and matching work.</span></span>  
  
-   <span data-ttu-id="e4de0-111">A criação de perfil apresenta as informações mais relevantes no momento mais relevante.</span><span class="sxs-lookup"><span data-stu-id="e4de0-111">Profiling presents you with the most relevant information at the most relevant time.</span></span>  
  
-   <span data-ttu-id="e4de0-112">O processo de criação de perfil gera notificações que enfatizam estatísticas ou eventos importantes que podem exigir ações.</span><span class="sxs-lookup"><span data-stu-id="e4de0-112">The profiling process generates notifications that emphasize important statistics or events that may warrant action.</span></span> <span data-ttu-id="e4de0-113">Em muitos casos, as notificações do DQS indicarão uma condição e recomendarão a ação que você deve adotar para resolver essa condição.</span><span class="sxs-lookup"><span data-stu-id="e4de0-113">In many cases, DQS notifications will indicate a condition and recommend the action that you can take to remedy that condition.</span></span>  
  
 <span data-ttu-id="e4de0-114">A criação de perfil permite que você use o Data Quality Services não só para a descoberta da base de dados de conhecimento, limpeza e correspondência, como também como uma ferramenta de análise.</span><span class="sxs-lookup"><span data-stu-id="e4de0-114">Profiling enables you to use Data Quality Services not only for knowledge discovery, cleansing, and matching, but also as an analysis tool.</span></span> <span data-ttu-id="e4de0-115">Talvez você queira criar uma base de dados de conhecimento para análise e executar a descoberta da base de dados de conhecimento usando essa base para determinar, com base nas estatísticas de criação de perfil, se a base de dados de conhecimento atende suas necessidades de descoberta, limpeza e correspondência.</span><span class="sxs-lookup"><span data-stu-id="e4de0-115">You may want to create one knowledge base for analysis, and run knowledge discovery using that knowledge base to determine from the profiling statistics whether the knowledge base satisfies your discovery, cleansing, and matching needs.</span></span>  
  
##  <a name="how-profiling-works"></a><a name="How"></a><span data-ttu-id="e4de0-116">Como a criação de perfil funciona</span><span class="sxs-lookup"><span data-stu-id="e4de0-116">How Profiling Works</span></span>  
 <span data-ttu-id="e4de0-117">A criação de perfil não mede a qualidade da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="e4de0-117">Profiling does not measure the quality of the knowledge base.</span></span> <span data-ttu-id="e4de0-118">Ela mede a qualidade dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="e4de0-118">It measures the quality of the source data.</span></span> <span data-ttu-id="e4de0-119">A criação de perfil fornece estatísticas que indicam o efeito da operação específica que você está executando no gerenciamento de conhecimento ou em um projeto de qualidade de dados nos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="e4de0-119">Profiling provides you with statistics that indicate the effect of the specific operation that you are doing in knowledge management or a data quality project on your source data.</span></span> <span data-ttu-id="e4de0-120">A criação de perfil está sempre no contexto da atividade específica que você está executando.</span><span class="sxs-lookup"><span data-stu-id="e4de0-120">Profiling is always in the context of the specific activity that you are performing.</span></span> <span data-ttu-id="e4de0-121">Você pode clicar na guia de criação de perfil em uma tela para exibir os dados da criação de perfil sem sair do estágio da atividade que está executando.</span><span class="sxs-lookup"><span data-stu-id="e4de0-121">You can click the profiling tab in a screen to display profiling data without leaving the stage of the activity that you are performing.</span></span> <span data-ttu-id="e4de0-122">A tabela de criação de perfil é populada em tempo real, à medida que o processo é executado, permitindo que você avalie as tarefas de qualidade de dados enquanto as executa.</span><span class="sxs-lookup"><span data-stu-id="e4de0-122">The profiling table is populated in real time as the process is performed, enabling you to assess data quality tasks as you are performing them.</span></span> <span data-ttu-id="e4de0-123">É possível determinar se os dados de origem ficam melhores após a limpeza ou desduplicação e o quanto melhoram.</span><span class="sxs-lookup"><span data-stu-id="e4de0-123">You can determine whether source data is better after cleansing or de-duplication, and by how much.</span></span>  
  
 <span data-ttu-id="e4de0-124">Todos os números de criação de perfil se referem ao número de vezes em que um valor aparece e, em muitos casos, o percentual do total, com a exceção de métricas de exclusividade.</span><span class="sxs-lookup"><span data-stu-id="e4de0-124">All profiling numbers refer to the number of appearances of a value, and in many cases the percent of the total, with the exception of uniqueness metrics.</span></span> <span data-ttu-id="e4de0-125">As métricas de exclusividade se referem ao número absoluto de valores, independentemente do número de vezes em que esses valores aparecem.</span><span class="sxs-lookup"><span data-stu-id="e4de0-125">Uniqueness metrics refer to the absolute number of values, regardless of the number of appearances of those values.</span></span>  
  
 <span data-ttu-id="e4de0-126">A criação de perfil faz parte da solução voltada para conhecimentos do DQS.</span><span class="sxs-lookup"><span data-stu-id="e4de0-126">Profiling is part of the DQS knowledge-driven solution.</span></span> <span data-ttu-id="e4de0-127">Ela fornece informações sobre uma base de dados de conhecimento, correspondência ou processo de limpeza de dados com base no mapeamento entre os campos da fonte de dados e os domínios da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="e4de0-127">It provides information on a knowledge base, matching, or data cleansing process based upon the mapping between data source fields and knowledge base domains.</span></span> <span data-ttu-id="e4de0-128">A criação de perfil é executada somente após a conclusão do mapeamento; nenhuma criação de perfil é executada durante o estágio de mapeamento de qualquer atividade.</span><span class="sxs-lookup"><span data-stu-id="e4de0-128">Profiling is performed only after mapping is complete; no profiling is performed during the mapping stage of any activity.</span></span> <span data-ttu-id="e4de0-129">A criação de perfil sempre está associada a uma atividade.</span><span class="sxs-lookup"><span data-stu-id="e4de0-129">Profiling is always attached to an activity.</span></span> <span data-ttu-id="e4de0-130">O processo de criação de perfil é executado nos dados que são mapeados para domínios, não nos dados nos domínios.</span><span class="sxs-lookup"><span data-stu-id="e4de0-130">The profiling process is performed on the data that is mapped to domains, not on the data in the domains.</span></span> <span data-ttu-id="e4de0-131">A criação de perfil está integrada nas seguintes etapas de atividades:</span><span class="sxs-lookup"><span data-stu-id="e4de0-131">Profiling is integrated into the following steps of activities:</span></span>  
  
-   <span data-ttu-id="e4de0-132">As etapas **Descobrir** e **Gerenciar valores de domínio** da atividade Descoberta da base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="e4de0-132">The **Discover** and **Manage domain values** steps of the Knowledge discovery activity</span></span>  
  
-   <span data-ttu-id="e4de0-133">As etapas **Limpar** e **Gerenciar e exibir resultados** da atividade Limpeza</span><span class="sxs-lookup"><span data-stu-id="e4de0-133">The **Cleanse** and **Manage and view results** steps of the Cleansing activity</span></span>  
  
-   <span data-ttu-id="e4de0-134">As etapas **Política de correspondência** e **Resultados correspondentes** da atividade Política de correspondência</span><span class="sxs-lookup"><span data-stu-id="e4de0-134">The **Matching policy** and **Matching results** steps of the Matching policy activity</span></span>  
  
-   <span data-ttu-id="e4de0-135">As etapas **Correspondência** e **Exportar** da atividade Correspondência</span><span class="sxs-lookup"><span data-stu-id="e4de0-135">The **Matching** and **Export** steps of the Matching activity</span></span>  
  
 <span data-ttu-id="e4de0-136">O DQS não fornece estatísticas de criação de perfil para a atividade Gerenciamento de Domínio.</span><span class="sxs-lookup"><span data-stu-id="e4de0-136">DQS does not provide profiling statistics for the Domain Management activity.</span></span>  
  
##  <a name="profiling-data-by-activity"></a><a name="Activity"></a><span data-ttu-id="e4de0-137">Criação de perfil de dados por atividade</span><span class="sxs-lookup"><span data-stu-id="e4de0-137">Profiling Data by Activity</span></span>  
 <span data-ttu-id="e4de0-138">A criação de perfil do DQS usa dimensões de qualidade de dados padrão para representar a qualidade dos dados: integridade (a extensão até a qual os dados estão presentes), precisão (a extensão até a qual os dados podem ser utilizados para seu uso pretendido) e exclusividade (a extensão até a qual valores diferentes representam entidades diferentes).</span><span class="sxs-lookup"><span data-stu-id="e4de0-138">DQS profiling uses standard data quality dimensions to represent the quality of the data: completeness (the extent to which data is present), accuracy (the extent to which data can be used for its intended use), and uniqueness (the extent to which different values represent different entities).</span></span> <span data-ttu-id="e4de0-139">Por padrão, valores NULL e vazios são considerados ausentes ou reduzem o percentual de integridade; no entanto, você também pode definir outros valores como equivalentes a NULL, caso em que eles também poderão ser considerados ausentes.</span><span class="sxs-lookup"><span data-stu-id="e4de0-139">By default, NULL and empty values are considered to be missing, or lower the completeness percentage; however, you can also define other values to be NULL-equivalent, in which case they will also be considered to be missing.</span></span>  
  
 <span data-ttu-id="e4de0-140">A criação de perfil fornece as estatísticas de que você precisa para avaliar seus processos, mas é necessário interpretá-las.</span><span class="sxs-lookup"><span data-stu-id="e4de0-140">Profiling provides you with the statistics you need to assess your processes, but you must interpret the statistics.</span></span> <span data-ttu-id="e4de0-141">Entenda o que a criação de perfil está informando a você examinando as estatísticas coluna por coluna.</span><span class="sxs-lookup"><span data-stu-id="e4de0-141">Make sense of what profiling is telling you by looking at the statistics column by column.</span></span>  
  
 <span data-ttu-id="e4de0-142">As atividades do DQS têm conjuntos diferentes de estatísticas de criação de perfil, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e4de0-142">The DQS activities have different sets of profiling statistics, as follows:</span></span>  
  
-   <span data-ttu-id="e4de0-143">Somente a atividade Limpeza tem estatísticas de criação de perfil quanto à precisão (em percentual por domínio).</span><span class="sxs-lookup"><span data-stu-id="e4de0-143">Only the Cleansing activity has profiling statistics for accuracy (in percent by domain).</span></span> <span data-ttu-id="e4de0-144">A precisão é afetada pela validade, consistência, erros de sintaxe e regras de domínio.</span><span class="sxs-lookup"><span data-stu-id="e4de0-144">Accuracy is affecting by validity, consistency, syntax errors, and domain rules.</span></span>  
  
-   <span data-ttu-id="e4de0-145">Somente a atividade Limpeza tem estatísticas de criação de perfil quanto a valores corretos, corrigidos e sugeridos na origem e valores corrigidos e sugeridos pelo domínio (ambos de número de percentual).</span><span class="sxs-lookup"><span data-stu-id="e4de0-145">Only the Cleansing activity has profiling statistics for correct, corrected, and suggested in the source, and corrected and suggested values by domain (both number of percent).</span></span>  
  
-   <span data-ttu-id="e4de0-146">As atividades Limpeza e Descoberta da Base de Dados de Conhecimento têm estatísticas de criação de perfil quanto à validade (Limpeza por registro, Descoberta da Base de Dados de Conhecimento por registro e domínio).</span><span class="sxs-lookup"><span data-stu-id="e4de0-146">The Cleansing and Knowledge Discovery activities have profiling statistics for validity (Cleansing by record, Knowledge Discovery by record and domain).</span></span> <span data-ttu-id="e4de0-147">As atividades Política de Correspondência e Correspondência não têm estatísticas de validade.</span><span class="sxs-lookup"><span data-stu-id="e4de0-147">The Matching Policy and Matching activities do not have statistics for validity.</span></span>  
  
-   <span data-ttu-id="e4de0-148">A atividade Limpeza não tem estatísticas de criação de perfil quanto à exclusividade.</span><span class="sxs-lookup"><span data-stu-id="e4de0-148">The Cleansing activity does not have profiling statistics for uniqueness.</span></span> <span data-ttu-id="e4de0-149">As atividades Descoberta da Base de Dados de Conhecimento, Política de Correspondência e Correspondência têm estatísticas de criação de perfil quanto à exclusividade no número e percentual de origem e por domínio.</span><span class="sxs-lookup"><span data-stu-id="e4de0-149">The Knowledge Discovery, Matching Policy, and Matching activities have profiling statistics for uniqueness in number and percent for the source and by domain.</span></span>  
  
 <span data-ttu-id="e4de0-150">Para obter mais informações sobre as estatísticas específicas de criação de perfil relacionadas a uma atividade, consulte as seções sobre Criação de Perfil nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e4de0-150">For more information about the specific profiling statistics related to an activity, see the Profiling sections in the following topics:</span></span>  
  
-   [<span data-ttu-id="e4de0-151">Executar a descoberta da base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="e4de0-151">Perform Knowledge Discovery</span></span>](../../2014/data-quality-services/perform-knowledge-discovery.md)  
  
-   [<span data-ttu-id="e4de0-152">Limpar dados usando o conhecimento &#40;interno&#41; do DQS</span><span class="sxs-lookup"><span data-stu-id="e4de0-152">Cleanse Data Using DQS &#40;Internal&#41; Knowledge</span></span>](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md)  
  
-   [<span data-ttu-id="e4de0-153">Criar uma política de correspondência</span><span class="sxs-lookup"><span data-stu-id="e4de0-153">Create a Matching Policy</span></span>](../../2014/data-quality-services/create-a-matching-policy.md)  
  
-   [<span data-ttu-id="e4de0-154">Executar um projeto de correspondência</span><span class="sxs-lookup"><span data-stu-id="e4de0-154">Run a Matching Project</span></span>](../../2014/data-quality-services/run-a-matching-project.md)  
  
##  <a name="profiling-data-in-activity-monitoring"></a><a name="Monitoring"></a><span data-ttu-id="e4de0-155">Criação de perfil de dados no monitoramento de atividades</span><span class="sxs-lookup"><span data-stu-id="e4de0-155">Profiling Data in Activity Monitoring</span></span>  
 <span data-ttu-id="e4de0-156">Informações de criação de perfil para as atividades Descoberta da Base de Dados de Conhecimento, Política de Correspondência, Correspondência e Limpeza estão disponíveis não só nas páginas de atividades no cliente Data Quality, como também no monitoramento da atividade.</span><span class="sxs-lookup"><span data-stu-id="e4de0-156">Profiling information for the Knowledge Discovery, Matching Policy, Matching, and Cleansing activities is available not only in the activity pages in the Data Quality client, but also in activity monitoring.</span></span> <span data-ttu-id="e4de0-157">O monitoramento da atividade apresenta uma visão geral das atividades atuais e passadas.</span><span class="sxs-lookup"><span data-stu-id="e4de0-157">Activity monitoring provides you with an overview of current and past activities.</span></span> <span data-ttu-id="e4de0-158">Além das propriedades e processos de atividades computacionais relacionados, você pode exibir as informações de criação de perfil geradas para cada atividade em um local.</span><span class="sxs-lookup"><span data-stu-id="e4de0-158">In addition to the properties and related computational processes of activities, you can view the profiling information generated for each activity in one location.</span></span> <span data-ttu-id="e4de0-159">Selecione uma atividade na tabela de atividades para exibir os resultados da criação de perfil em uma tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="e4de0-159">You select an activity in the activity table to display profiling results in a table below.</span></span> <span data-ttu-id="e4de0-160">Também é possível exportar os resultados da criação de perfil.</span><span class="sxs-lookup"><span data-stu-id="e4de0-160">You can also export the profiling results.</span></span> <span data-ttu-id="e4de0-161">Para obter mais informações, consulte [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="e4de0-161">For more information, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
##  <a name="notifications"></a><a name="Notifications"></a> <span data-ttu-id="e4de0-162">Notificações</span><span class="sxs-lookup"><span data-stu-id="e4de0-162">Notifications</span></span>  
 <span data-ttu-id="e4de0-163">Além de coletar e exibir estatísticas e métricas importantes por meio da criação de perfil, o DQS gerará notificações (se habilitado) para indicar quando talvez você queira executar uma ação com base nas estatísticas de criação de perfil exibidas.</span><span class="sxs-lookup"><span data-stu-id="e4de0-163">In addition to collecting and displaying important statistics and metrics through profiling, DQS will generate notifications (if enabled) to indicate when you may want to take an action based on the displayed profiling statistics.</span></span> <span data-ttu-id="e4de0-164">O DQS usa notificações para enfatizar fatos importantes sobre a fonte de dados e mostrar a efetividade da atividade atual relativa ao objetivo para o qual foi executado.</span><span class="sxs-lookup"><span data-stu-id="e4de0-164">DQS uses notifications to emphasize important facts about the data source, and to show the effectiveness of the current activity relative to the purpose for which it was executed.</span></span> <span data-ttu-id="e4de0-165">As notificações fornecem dicas e recomendações que indicam uma condição e recomendam como você pode aprimorar uma atividade de descoberta da base de dados de conhecimento, limpeza de dados ou correspondência de dados.</span><span class="sxs-lookup"><span data-stu-id="e4de0-165">Notifications provide tips and recommendations that indicate a condition and recommend how you could improve a knowledge discovery, data cleansing, or data matching activity.</span></span>  
  
 <span data-ttu-id="e4de0-166">Uma notificação do DQS é usada para gerar uma questão que pode ser interessante para você ou abordar um problema potencial.</span><span class="sxs-lookup"><span data-stu-id="e4de0-166">A DQS notification is used to raise an issue that may interest you, or to address a potential problem.</span></span> <span data-ttu-id="e4de0-167">Se você vai agir ao receber a notificação dependerá se ela é relevante para os seus objetivos.</span><span class="sxs-lookup"><span data-stu-id="e4de0-167">Whether you act upon the notification depends upon whether it is relevant to your purposes.</span></span> <span data-ttu-id="e4de0-168">Por exemplo, vamos supor que o DQS publique uma notificação quando a limpeza de dados não produzir valores corrigidos ou valores sugeridos quando a integridade e a exatidão forem 100%.</span><span class="sxs-lookup"><span data-stu-id="e4de0-168">For example, suppose DQS posts a notification when data cleansing produces no corrected values or suggested values while completeness and accuracy are both 100%.</span></span> <span data-ttu-id="e4de0-169">Esta notificação indicaria que a atividade talvez não precise ser executada.</span><span class="sxs-lookup"><span data-stu-id="e4de0-169">This notification would indicate that the activity may not need to be run.</span></span> <span data-ttu-id="e4de0-170">Se você vai optar por executar a atividade, no entanto, essa é uma decisão sua.</span><span class="sxs-lookup"><span data-stu-id="e4de0-170">Whether you choose to run the activity, however, is your decision.</span></span>  
  
 <span data-ttu-id="e4de0-171">Uma notificação é indicada por uma dica de ferramenta com um ponto de exclamação na guia **criação de perfil** . as estatísticas associadas à notificação são coloridas em vermelho para indicar a justificação estatística da notificação.</span><span class="sxs-lookup"><span data-stu-id="e4de0-171">A notification is indicated by a tool tip with an exclamation point in the **Profiling** tab. Statistics associated with the notification are colored red to indicate the statistical justification for the notification.</span></span>  
  
 <span data-ttu-id="e4de0-172">Você pode habilitar (o padrão) ou desabilitar as notificações na guia **Configurações Gerais** da seção **Administração** da página inicial Cliente Data Quality.</span><span class="sxs-lookup"><span data-stu-id="e4de0-172">You can enable (the default) or disable notifications in the **General Settings** tab of the **Administration** section of the Data Quality Client home page.</span></span> <span data-ttu-id="e4de0-173">Quando a notificação está desabilitada, as dicas de ferramenta não são exibidas e as estatísticas não aparecem em vermelho.</span><span class="sxs-lookup"><span data-stu-id="e4de0-173">When notification is disabled, tool tips are not displayed and statistics are not colored red.</span></span> <span data-ttu-id="e4de0-174">Não há nenhum aprimoramento significativo no desempenho com a desabilitação de notificações.</span><span class="sxs-lookup"><span data-stu-id="e4de0-174">There is no significant improvement in performance by disabling notifications.</span></span> <span data-ttu-id="e4de0-175">A criação de perfil ainda estará operacional se você desabilitar as notificações.</span><span class="sxs-lookup"><span data-stu-id="e4de0-175">Profiling will still be operational if you disable notifications.</span></span>  
  
 <span data-ttu-id="e4de0-176">Para condições específicas associadas às notificações de uma atividade, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e4de0-176">For specific conditions associated with notifications for an activity, see the following:</span></span>  
  
-   [<span data-ttu-id="e4de0-177">Executar a descoberta da base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="e4de0-177">Perform Knowledge Discovery</span></span>](../../2014/data-quality-services/perform-knowledge-discovery.md)  
  
-   [<span data-ttu-id="e4de0-178">Limpar dados usando o conhecimento &#40;interno&#41; do DQS</span><span class="sxs-lookup"><span data-stu-id="e4de0-178">Cleanse Data Using DQS &#40;Internal&#41; Knowledge</span></span>](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md)  
  
-   [<span data-ttu-id="e4de0-179">Criar uma política de correspondência</span><span class="sxs-lookup"><span data-stu-id="e4de0-179">Create a Matching Policy</span></span>](../../2014/data-quality-services/create-a-matching-policy.md)  
  
-   [<span data-ttu-id="e4de0-180">Executar um projeto de correspondência</span><span class="sxs-lookup"><span data-stu-id="e4de0-180">Run a Matching Project</span></span>](../../2014/data-quality-services/run-a-matching-project.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e4de0-181">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e4de0-181">Related Tasks</span></span>  
  
|<span data-ttu-id="e4de0-182">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="e4de0-182">Task Description</span></span>|<span data-ttu-id="e4de0-183">Tópico</span><span class="sxs-lookup"><span data-stu-id="e4de0-183">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="e4de0-184">Descreve como habilitar ou desabilitar as notificações no DQS.</span><span class="sxs-lookup"><span data-stu-id="e4de0-184">Describes how to enable or disable notifications in DQS.</span></span>|[<span data-ttu-id="e4de0-185">Habilitar ou desabilitar notificações de criação de perfil no DQS</span><span class="sxs-lookup"><span data-stu-id="e4de0-185">Enable or Disable Profiling Notifications in DQS</span></span>](../../2014/data-quality-services/enable-or-disable-profiling-notifications-in-dqs.md)|  
  
  