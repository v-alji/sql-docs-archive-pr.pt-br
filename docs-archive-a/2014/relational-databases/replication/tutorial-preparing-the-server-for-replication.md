---
title: 'Tutorial: preparando o servidor para replicação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583478"
---
# <a name="tutorial-preparing-the-server-for-replication"></a><span data-ttu-id="2b934-102">Tutorial: Preparando o servidor para replicação</span><span class="sxs-lookup"><span data-stu-id="2b934-102">Tutorial: Preparing the Server for Replication</span></span>
  <span data-ttu-id="2b934-103">É importante planejar a segurança antes de configurar a topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="2b934-103">It is important to plan for security before you configure your replication topology.</span></span> <span data-ttu-id="2b934-104">Este tutorial mostra a melhor forma de garantir a segurança de uma topologia de replicação e também como configurar a distribuição, que é a primeira etapa na replicação de dados.</span><span class="sxs-lookup"><span data-stu-id="2b934-104">This tutorial shows you how to better secure a replication topology as well as how to configure distribution, which is the first step in replicating data.</span></span> <span data-ttu-id="2b934-105">É preciso concluir este tutorial antes de qualquer outro.</span><span class="sxs-lookup"><span data-stu-id="2b934-105">You must complete this tutorial before any of the others.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b934-106">Para replicar dados com segurança entre servidores, é necessário implementar todas as recomendações em [Práticas recomendadas em relação à segurança de replicação](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="2b934-106">To replicate data securely between servers, you should implement all of the recommendations in [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="2b934-107">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="2b934-107">What You Will Learn</span></span>  
 <span data-ttu-id="2b934-108">Neste tutorial, você aprenderá como preparar um servidor para que a replicação possa ser executada de modo seguro com um mínimo de privilégios.</span><span class="sxs-lookup"><span data-stu-id="2b934-108">In this tutorial you will learn how to prepare a server so that replication can run securely with least privileges.</span></span> <span data-ttu-id="2b934-109">A primeira lição mostra como criar as contas de serviço do Windows usadas para executar os agentes de replicação.</span><span class="sxs-lookup"><span data-stu-id="2b934-109">The first lesson shows how to create the Windows service accounts used to run replication agents.</span></span> <span data-ttu-id="2b934-110">A segunda lição mostra como configurar a pasta usada para gerar e armazenar instantâneos de publicação.</span><span class="sxs-lookup"><span data-stu-id="2b934-110">The second lesson shows how to configure the folder used to generate and store publication snapshots.</span></span> <span data-ttu-id="2b934-111">A terceira lição mostra como configurar a distribuição e definir permissões.</span><span class="sxs-lookup"><span data-stu-id="2b934-111">The third lesson shows how to configure distribution and set permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b934-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b934-112">Requirements</span></span>  
 <span data-ttu-id="2b934-113">Este tutorial é destinado a usuários que estão familiarizados com operações fundamentais de bancos de dados, mas que possuem pouca experiência com replicação.</span><span class="sxs-lookup"><span data-stu-id="2b934-113">This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to replication.</span></span>  
  
 <span data-ttu-id="2b934-114">Para que você possa usar esse tutorial, os seguintes componentes devem estar instalados no sistema:</span><span class="sxs-lookup"><span data-stu-id="2b934-114">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] <span data-ttu-id="2b934-115">com o banco de dados do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b934-115">with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="2b934-116">Para reforçar a segurança, os bancos de dados de exemplo não são instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="2b934-116">To enhance security, the sample databases are not installed by default.</span></span>  
  
 <span data-ttu-id="2b934-117">**Tempo estimado para concluir este tutorial: 30 minutos.**</span><span class="sxs-lookup"><span data-stu-id="2b934-117">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="2b934-118">Lições neste tutorial</span><span class="sxs-lookup"><span data-stu-id="2b934-118">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="2b934-119">Lição 1: Criando contas do Windows para replicação</span><span class="sxs-lookup"><span data-stu-id="2b934-119">Lesson 1: Creating Windows Accounts for Replication</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [<span data-ttu-id="2b934-120">Lição 2: Preparando a pasta do instantâneo</span><span class="sxs-lookup"><span data-stu-id="2b934-120">Lesson 2: Preparing the Snapshot Folder</span></span>](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [<span data-ttu-id="2b934-121">Lição 3: Configurando a distribuição</span><span class="sxs-lookup"><span data-stu-id="2b934-121">Lesson 3: Configuring Distribution</span></span>](lesson-3-configuring-distribution.md)  
  
 [<span data-ttu-id="2b934-122">Iniciar o tutorial</span><span class="sxs-lookup"><span data-stu-id="2b934-122">Start the Tutorial</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b934-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b934-123">See Also</span></span>  
 <span data-ttu-id="2b934-124">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="2b934-124">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="2b934-125">Segurança de Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b934-125">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
