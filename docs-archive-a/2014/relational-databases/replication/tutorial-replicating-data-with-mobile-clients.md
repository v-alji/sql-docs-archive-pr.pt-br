---
title: 'Tutorial: replicando dados com clientes móveis | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: af673514-30c7-403a-9d18-d01e1a095115
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdf8be7cb0da11f0aa1022ba656d50c10826ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583474"
---
# <a name="tutorial-replicating-data-with-mobile-clients"></a><span data-ttu-id="b5128-102">Tutorial: Replicando dados com clientes móveis</span><span class="sxs-lookup"><span data-stu-id="b5128-102">Tutorial: Replicating Data with Mobile Clients</span></span>
  <span data-ttu-id="b5128-103">A replicação é uma boa solução para o problema de mover dados entre um servidor central e clientes móveis que são conectados apenas ocasionalmente.</span><span class="sxs-lookup"><span data-stu-id="b5128-103">Replication is a good solution to the problem of moving data between a central server and mobile clients that are only occasionally connected.</span></span> <span data-ttu-id="b5128-104">Usando os assistentes de replicação, você pode configurar e administrar uma topologia de replicação facilmente.</span><span class="sxs-lookup"><span data-stu-id="b5128-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="b5128-105">Este tutorial mostra como você deve configurar uma topologia de replicação para clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="b5128-105">This tutorial shows you how to configure a replication topology for mobile clients.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="b5128-106">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="b5128-106">What You Will Learn</span></span>  
 <span data-ttu-id="b5128-107">Neste tutorial você usará a replicação de mesclagem para publicar dados de um banco de dados central para um ou mais usuários móveis de forma que cada usuário obtenha um subconjunto dos dados filtrado exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="b5128-107">In this tutorial you will use merge replication to publish data from a central database to one or more mobile users so that each user gets a uniquely filtered subset of the data.</span></span> <span data-ttu-id="b5128-108">A primeira lição mostra como usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar uma publicação.</span><span class="sxs-lookup"><span data-stu-id="b5128-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="b5128-109">Lições posteriores mostram como criar e sincronizar uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="b5128-109">Later lessons show how to create and synchronize a subscription.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5128-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5128-110">Requirements</span></span>  
 <span data-ttu-id="b5128-111">Este tutorial é destinado a usuários que estão familiarizados com operações fundamentais de bancos de dados, mas que possuem pouca experiência com replicação.</span><span class="sxs-lookup"><span data-stu-id="b5128-111">This tutorial is intended for users familiar with fundamental database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="b5128-112">Antes de iniciar este tutorial, você deve concluir [o tutorial: preparando o servidor para replicação](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b5128-112">Before you start this tutorial, you must complete [Tutorial: Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="b5128-113">Para que você possa usar esse tutorial, os seguintes componentes devem estar instalados no sistema:</span><span class="sxs-lookup"><span data-stu-id="b5128-113">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   <span data-ttu-id="b5128-114">No servidor do Publicador (fonte):</span><span class="sxs-lookup"><span data-stu-id="b5128-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="b5128-115">Qualquer edição do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], menos a Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) ou [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5128-115">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="b5128-116">Essas edições não podem ser Publicadores de replicação.</span><span class="sxs-lookup"><span data-stu-id="b5128-116">These editions cannot be a replication Publisher.</span></span>  
  
    -   <span data-ttu-id="b5128-117">O banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5128-117">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="b5128-118">Para reforçar a segurança, os bancos de dados de exemplo não são instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="b5128-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="b5128-119">Servidor de assinante (destino):</span><span class="sxs-lookup"><span data-stu-id="b5128-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="b5128-120">Qualquer edição do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], exceto para [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5128-120">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="b5128-121">.</span><span class="sxs-lookup"><span data-stu-id="b5128-121">is not supported by the publication created in this tutorial.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5128-122">A replicação não é instalada por padrão no [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5128-122">Replication is not installed by default on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5128-123">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], você deve se conectar ao Publicador e ao Assinante usando um logon que seja membro da função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="b5128-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the sysadmin fixed server role.</span></span>  
  
 <span data-ttu-id="b5128-124">**Tempo estimado para concluir este tutorial: 30 minutos.**</span><span class="sxs-lookup"><span data-stu-id="b5128-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="b5128-125">Lições neste tutorial</span><span class="sxs-lookup"><span data-stu-id="b5128-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="b5128-126">Lição 1: publicando dados usando a replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="b5128-126">Lesson 1: Publishing Data Using Merge Replication</span></span>](lesson-1-publishing-data-using-merge-replication.md)  
  
-   [<span data-ttu-id="b5128-127">Lição 2: criando uma assinatura para a publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="b5128-127">Lesson 2: Creating a Subscription to the Merge Publication</span></span>](lesson-2-creating-a-subscription-to-the-merge-publication.md)  
  
 [<span data-ttu-id="b5128-128">Iniciar o tutorial</span><span class="sxs-lookup"><span data-stu-id="b5128-128">Start the Tutorial</span></span>](merge/merge-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5128-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5128-129">See Also</span></span>  
 [<span data-ttu-id="b5128-130">Conceitos de programação de replicação</span><span class="sxs-lookup"><span data-stu-id="b5128-130">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
