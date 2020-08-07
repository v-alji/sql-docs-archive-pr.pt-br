---
title: Criar uma assinatura controlada por dados (Tutorial do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], tutorials
- walkthroughs [Reporting Services]
- data-driven subscriptions
ms.assetid: 79ab0572-43e9-4dc4-9b5a-cd8b627b8274
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53be7cf793d8fa38d177643c7f366115d4df8b7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682169"
---
# <a name="create-a-data-driven-subscription-ssrs-tutorial"></a><span data-ttu-id="f479b-102">Criar uma assinatura controlada por dados (Tutorial do SSRS)</span><span class="sxs-lookup"><span data-stu-id="f479b-102">Create a Data-Driven Subscription (SSRS Tutorial)</span></span>
  <span data-ttu-id="f479b-103">O [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] fornece assinaturas controladas por dados de forma que você pode personalizar a distribuição de um relatório baseado em dados de assinante dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="f479b-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides data-driven subscriptions so that you can customize the distribution of a report based on dynamic subscriber data.</span></span> <span data-ttu-id="f479b-104">As assinaturas controladas por dados foram desenvolvidas para os seguintes tipos de cenário:</span><span class="sxs-lookup"><span data-stu-id="f479b-104">Data-driven subscriptions are intended for the following kinds of scenarios:</span></span>  
  
-   <span data-ttu-id="f479b-105">Distribuição de relatórios em um grande pool de destinatários cuja associação pode ser alterada de uma distribuição para a outra.</span><span class="sxs-lookup"><span data-stu-id="f479b-105">Distributing reports to a large recipient pool whose membership may change from one distribution to the next.</span></span> <span data-ttu-id="f479b-106">Por exemplo, distribua um relatório mensal a todos os clientes atuais.</span><span class="sxs-lookup"><span data-stu-id="f479b-106">For example, distribute a monthly report to all current customers.</span></span>  
  
-   <span data-ttu-id="f479b-107">Distribuição de relatórios para um grupo específico de destinatários baseado em critérios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="f479b-107">Distributing reports to a specific group of recipients based on predefined criteria.</span></span> <span data-ttu-id="f479b-108">Por exemplo, envie um relatório de desempenho de vendas para os dez principais gerentes de vendas em uma organização.</span><span class="sxs-lookup"><span data-stu-id="f479b-108">For example, send a sales performance report to the top ten sales managers in an organization.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="f479b-109">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="f479b-109">What You Will Learn</span></span>  
 <span data-ttu-id="f479b-110">Este tutorial mostra como usar assinaturas controladas por dados usando um exemplo simples para ilustrar os conceitos.</span><span class="sxs-lookup"><span data-stu-id="f479b-110">This tutorial shows you how to use data-driven subscriptions using a simple example to illustrate the concepts.</span></span>  
  
 <span data-ttu-id="f479b-111">Este tutorial divide-se em três lições:</span><span class="sxs-lookup"><span data-stu-id="f479b-111">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="f479b-112">Lição 1: Criando um banco de dados do assinante de exemplo</span><span class="sxs-lookup"><span data-stu-id="f479b-112">Lesson 1: Creating a Sample Subscriber Database</span></span>](lesson-1-creating-a-sample-subscriber-database.md)  
 <span data-ttu-id="f479b-113">Nesta lição, você aprenderá a criar um banco de dados local do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que contém informações de assinante.</span><span class="sxs-lookup"><span data-stu-id="f479b-113">In this lesson you will learn how to create a local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database that contains subscriber information.</span></span>  
  
 [<span data-ttu-id="f479b-114">Lição 2: Modificando as propriedades de fonte de dados de relatório</span><span class="sxs-lookup"><span data-stu-id="f479b-114">Lesson 2: Modifying the Report Data Source Properties</span></span>](lesson-2-modifying-the-report-data-source-properties.md)  
 <span data-ttu-id="f479b-115">Nesta lição, você aprenderá a modificar propriedades da fonte de dados de relatório de forma que o relatório possa ser executado de forma autônoma.</span><span class="sxs-lookup"><span data-stu-id="f479b-115">In this lesson, you will learn how to modify report data source properties so that the report can run unattended.</span></span> <span data-ttu-id="f479b-116">O processamento autônomo exige credenciais armazenadas.</span><span class="sxs-lookup"><span data-stu-id="f479b-116">Unattended processing requires stored credentials.</span></span> <span data-ttu-id="f479b-117">Você também modificará o conjunto de dados de relatório para incluir um parâmetro que é fornecido pelos dados do assinante.</span><span class="sxs-lookup"><span data-stu-id="f479b-117">You will also modify the report dataset to include a parameter that is supplied by the subscriber data.</span></span>  
  
 [<span data-ttu-id="f479b-118">Lição 3: Definindo uma assinatura controlada por dados</span><span class="sxs-lookup"><span data-stu-id="f479b-118">Lesson 3: Defining a Data-Driven Subscription</span></span>](lesson-3-defining-a-data-driven-subscription.md)  
 <span data-ttu-id="f479b-119">Nesta lição, você aprenderá a definir uma assinatura controlada por dados.</span><span class="sxs-lookup"><span data-stu-id="f479b-119">In this lesson you will learn how to define a data-driven subscription.</span></span> <span data-ttu-id="f479b-120">Esta lição o guia por cada página do Assistente de Assinatura Controlada por Dados.</span><span class="sxs-lookup"><span data-stu-id="f479b-120">This lesson guides you through each page in the Data-Driven Subscription Wizard.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f479b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f479b-121">Requirements</span></span>  
 <span data-ttu-id="f479b-122">As assinaturas controladas por dados normalmente são criadas e mantidas por administradores de servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="f479b-122">Data-driven subscriptions are typically created and maintained by report server administrators.</span></span> <span data-ttu-id="f479b-123">A capacidade de criar assinaturas controladas por dados requer experiência em criação de consultas, conhecimento das fontes de dados que contêm dados de assinante e permissões elevadas em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f479b-123">The ability to create data-driven subscriptions requires expertise in building queries, knowledge of data sources that contain subscriber data, and elevated permissions on a report server.</span></span>  
  
 <span data-ttu-id="f479b-124">O tutorial usará o relatório criado no tutorial [criar um relatório de tabela básico &#40;tutorial do SSRS&#41;](create-a-basic-table-report-ssrs-tutorial.md) e dados de[!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f479b-124">The tutorial will use the report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](create-a-basic-table-report-ssrs-tutorial.md) and data from [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]</span></span>  
  
 <span data-ttu-id="f479b-125">Para que você possa usar o tutorial, os itens a seguir devem estar instalados no sistema:</span><span class="sxs-lookup"><span data-stu-id="f479b-125">Your system must have the following installed to use this tutorial:</span></span>  
  
-   <span data-ttu-id="f479b-126">Uma edição do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que dá suporte a assinaturas controladas por dados.</span><span class="sxs-lookup"><span data-stu-id="f479b-126">An edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that supports data-driven subscriptions.</span></span> <span data-ttu-id="f479b-127">Para obter mais informações, consulte [edições e componentes do SQL Server 2014](../sql-server/editions-and-components-of-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="f479b-127">For more information, see [Editions and Components of SQL Server 2014](../sql-server/editions-and-components-of-sql-server-2016.md).</span></span>  
  
-   <span data-ttu-id="f479b-128">É necessário que o servidor de relatório esteja sendo executado no modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f479b-128">The report server must be running in native mode.</span></span> <span data-ttu-id="f479b-129">A interface do usuário descrita neste tutorial é baseada em um servidor de relatório de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f479b-129">The user interface described in this tutorial is based on a native mode report server.</span></span> <span data-ttu-id="f479b-130">As assinaturas têm suporte em servidores de relatórios do modo do SharePoint, mas a interface do usuário será diferente do que está descrito neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="f479b-130">Subscriptions are supported on SharePoint mode report servers but the user interface will be different than what is described in this tutorial.</span></span>  
  
-   <span data-ttu-id="f479b-131">O serviço do SQL Server Agent deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="f479b-131">SQL Server Agent service must be running.</span></span>  
  
-   <span data-ttu-id="f479b-132">Um relatório que inclui parâmetros.</span><span class="sxs-lookup"><span data-stu-id="f479b-132">A report that includes parameters.</span></span> <span data-ttu-id="f479b-133">Este tutorial presume o uso do relatório de exemplo, `Sales Orders` , criado por meio do tutorial [Criar um relatório de tabela básico &#40;Tutorial do SSRS&#41;](create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f479b-133">This tutorial assumes the sample report, `Sales Orders` you create using the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](create-a-basic-table-report-ssrs-tutorial.md).</span></span>  
  
-   <span data-ttu-id="f479b-134">O banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)], que fornece dados ao relatório de amostra.</span><span class="sxs-lookup"><span data-stu-id="f479b-134">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database, which provides data to the sample report.</span></span>  
  
-   <span data-ttu-id="f479b-135">Uma atribuição de função que inclua a tarefa Gerenciar todas as assinaturas no relatório de amostra.</span><span class="sxs-lookup"><span data-stu-id="f479b-135">A role assignment that includes the Manage all subscriptions task on the sample report.</span></span> <span data-ttu-id="f479b-136">Esta tarefa é obrigatória para definir uma assinatura controlada por dados.</span><span class="sxs-lookup"><span data-stu-id="f479b-136">This task is required for defining a data-driven subscription.</span></span> <span data-ttu-id="f479b-137">Se você for administrador no computador, a atribuição de função padrão para administradores locais fornecerá as permissões necessárias para criar assinaturas controladas por dados.</span><span class="sxs-lookup"><span data-stu-id="f479b-137">If you are an administrator on the computer, the default role assignment for local administrators provides the permissions necessary for creating data-driven subscriptions.</span></span> <span data-ttu-id="f479b-138">Para obter mais informações, consulte [Concedendo permissões em um servidor de relatório no modo nativo](security/granting-permissions-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="f479b-138">For more information, see [Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md).</span></span>  
  
-   <span data-ttu-id="f479b-139">Uma pasta compartilhada na qual você tenha permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="f479b-139">A shared folder for which you have write permissions.</span></span> <span data-ttu-id="f479b-140">A pasta compartilhada deve ser acessada por uma conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="f479b-140">The shared folder must be accessible over a network connection.</span></span>  
  
 <span data-ttu-id="f479b-141">**Tempo estimado para concluir o tutorial:** 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="f479b-141">**Estimated time to complete the tutorial:** 30 minutes.</span></span> <span data-ttu-id="f479b-142">Mais 30 minutos se você não concluiu o tutorial de relatório básico.</span><span class="sxs-lookup"><span data-stu-id="f479b-142">An additional 30 minutes if you have not completed the basic report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f479b-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f479b-143">See Also</span></span>  
 <span data-ttu-id="f479b-144">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="f479b-144">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="f479b-145">Criar um relatório de tabela básico &#40;Tutorial do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f479b-145">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
