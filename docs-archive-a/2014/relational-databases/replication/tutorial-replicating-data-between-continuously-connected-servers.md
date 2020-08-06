---
title: 'Tutorial: replicando dados entre servidores que estão continuamente conectados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- replication [SQL Server], tutorials
- wizards [SQL Server replication]
ms.assetid: 7b18a04a-2c3d-4efe-a0bc-c3f92be72fd0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 415cac62112c1c1d2aa6c42ec189c2614ec03923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583476"
---
# <a name="tutorial-replicating-data-between-continuously-connected-servers"></a><span data-ttu-id="f5c67-102">Tutorial: Replicando dados entre servidores que estão continuamente conectados</span><span class="sxs-lookup"><span data-stu-id="f5c67-102">Tutorial: Replicating Data Between Continuously Connected Servers</span></span>
  <span data-ttu-id="f5c67-103">Replicação é uma boa solução ao problema de mover dados entre servidores que estão continuamente conectados.</span><span class="sxs-lookup"><span data-stu-id="f5c67-103">Replication is a good solution to the problem of moving data between continuously connected servers.</span></span> <span data-ttu-id="f5c67-104">Usando os assistentes de replicação, você pode configurar e administrar uma topologia de replicação facilmente.</span><span class="sxs-lookup"><span data-stu-id="f5c67-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="f5c67-105">Este tutorial mostra a você como configurar uma topologia de replicação para servidores continuamente conectados.</span><span class="sxs-lookup"><span data-stu-id="f5c67-105">This tutorial shows you how to configure a replication topology for continuously connected servers.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="f5c67-106">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="f5c67-106">What You Will Learn</span></span>  
 <span data-ttu-id="f5c67-107">Este tutorial mostrará a você como publicar dados de um banco de dados para outro usando replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="f5c67-107">This tutorial will show you how to publish data from one database to another using transactional replication.</span></span> <span data-ttu-id="f5c67-108">A primeira lição mostra como usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar uma publicação.</span><span class="sxs-lookup"><span data-stu-id="f5c67-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="f5c67-109">Depois, as lições mostrarão como criar e validar uma assinatura e como medir a latência.</span><span class="sxs-lookup"><span data-stu-id="f5c67-109">Later lessons show how to create and validate a subscription and how to measure latency.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c67-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5c67-110">Requirements</span></span>  
 <span data-ttu-id="f5c67-111">Este tutorial é destinado a usuários que estão familiarizados com operações básicas de banco de dados, mas que possuem pouca experiência com replicação.</span><span class="sxs-lookup"><span data-stu-id="f5c67-111">This tutorial is intended for users who are familiar with basic database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="f5c67-112">Este tutorial exige a conclusão do tutorial anterior, [Preparando o servidor para replicação](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="f5c67-112">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="f5c67-113">Para usar este tutorial, os seguintes componentes devem fazer parte do seu sistema:</span><span class="sxs-lookup"><span data-stu-id="f5c67-113">To use this tutorial, your system must have the following components:</span></span>  
  
-   <span data-ttu-id="f5c67-114">No servidor do Publicador (fonte):</span><span class="sxs-lookup"><span data-stu-id="f5c67-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="f5c67-115">Qualquer edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], menos a Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) ou [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5c67-115">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="f5c67-116">Estas edições não podem ser Publicadores de replicação.</span><span class="sxs-lookup"><span data-stu-id="f5c67-116">These editions cannot be replication Publishers.</span></span>  
  
    -   [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] <span data-ttu-id="f5c67-117">banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f5c67-117">sample database.</span></span> <span data-ttu-id="f5c67-118">Para reforçar a segurança, os bancos de dados de exemplo não são instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="f5c67-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="f5c67-119">Servidor de assinante (destino):</span><span class="sxs-lookup"><span data-stu-id="f5c67-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="f5c67-120">Qualquer edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exceto [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5c67-120">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="f5c67-121">não pode ser um Assinante em uma replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="f5c67-121">cannot be a Subscriber in transactional replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5c67-122">A replicação não é instalada por padrão no [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5c67-122">Replication is not installed on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5c67-123">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , você deve se conectar ao Publicador e ao Assinante usando um logon que seja membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f5c67-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="f5c67-124">**Tempo estimado para concluir este tutorial: 30 minutos.**</span><span class="sxs-lookup"><span data-stu-id="f5c67-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="f5c67-125">Lições neste tutorial</span><span class="sxs-lookup"><span data-stu-id="f5c67-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="f5c67-126">Lição 1: publicando dados que usam replicação transacional</span><span class="sxs-lookup"><span data-stu-id="f5c67-126">Lesson 1: Publishing Data Using Transactional Replication</span></span>](lesson-1-publishing-data-using-transactional-replication.md)  
  
-   [<span data-ttu-id="f5c67-127">Lição 2: Criando uma assinatura na publicação transacional</span><span class="sxs-lookup"><span data-stu-id="f5c67-127">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>](lesson-2-creating-a-subscription-to-the-transactional-publication.md)  
  
-   [<span data-ttu-id="f5c67-128">Lição 3: Validando a assinatura e medindo a latência</span><span class="sxs-lookup"><span data-stu-id="f5c67-128">Lesson 3: Validating the Subscription and Measuring Latency</span></span>](lesson-3-validating-the-subscription-and-measuring-latency.md)  
  
 [<span data-ttu-id="f5c67-129">Iniciar o tutorial</span><span class="sxs-lookup"><span data-stu-id="f5c67-129">Start the Tutorial</span></span>](transactional/transactional-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5c67-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5c67-130">See Also</span></span>  
 [<span data-ttu-id="f5c67-131">Conceitos de programação de replicação</span><span class="sxs-lookup"><span data-stu-id="f5c67-131">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
