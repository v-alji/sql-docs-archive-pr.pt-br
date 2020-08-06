---
title: Replicação de banco de dados heterogênea | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, about heterogeneous database replication
- replication [SQL Server], heterogeneous database replication
- heterogeneous database replication
ms.assetid: 3fd983ad-e206-45db-9054-417c9b5bb815
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d8988a425bc9519d43b8100e4cd34418114edae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683472"
---
# <a name="heterogeneous-database-replication"></a><span data-ttu-id="992f0-102">replicação de banco de dados heterogênea</span><span class="sxs-lookup"><span data-stu-id="992f0-102">Heterogeneous Database Replication</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="992f0-103">oferece suporte aos seguintes cenários heterogêneos para replicação transacional e de instantâneo:</span><span class="sxs-lookup"><span data-stu-id="992f0-103">supports the following heterogeneous scenarios for transactional and snapshot replication:</span></span>  
  
-   <span data-ttu-id="992f0-104">Publicando dados do Oracle no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="992f0-104">Publishing data from Oracle to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="992f0-105">Publicando dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para não assinantes do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="992f0-105">Publishing data from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="992f0-106">A replicação heterogênea para assinantes que não são do SQL Server foi preterida.</span><span class="sxs-lookup"><span data-stu-id="992f0-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="992f0-107">A publicação Oracle foi preterida.</span><span class="sxs-lookup"><span data-stu-id="992f0-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="992f0-108">Para mover dados, crie soluções usando a captura de dados de alterações e o [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="992f0-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="publishing-data-from-oracle"></a><span data-ttu-id="992f0-109">Publicando dados do Oracle</span><span class="sxs-lookup"><span data-stu-id="992f0-109">Publishing Data from Oracle</span></span>  
 <span data-ttu-id="992f0-110">Você pode usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para publicar dados do Oracle com grande parte dos mesmos recursos e a facilidade de uso do instantâneo do e das replicações transacionais do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="992f0-110">You can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to publish data from Oracle with most of the same features and ease-of-use as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] snapshot and transactional replication.</span></span> <span data-ttu-id="992f0-111">Publicando dados do Oracle é o ideal para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="992f0-111">Publishing data from Oracle is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="992f0-112">Cenário</span><span class="sxs-lookup"><span data-stu-id="992f0-112">Scenario</span></span>|<span data-ttu-id="992f0-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="992f0-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="992f0-114">Implantações de aplicativos do[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="992f0-114">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="992f0-115">Desenvolva com o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enquanto estiver operando em dados replicados de banco de dados que não são do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="992f0-115">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="992f0-116">Servidores de preparo de data warehouse</span><span class="sxs-lookup"><span data-stu-id="992f0-116">Data warehousing staging servers</span></span>|<span data-ttu-id="992f0-117">Mantenha os bancos de dados de preparo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizado com um banco de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="992f0-117">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="992f0-118">Migração para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="992f0-118">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="992f0-119">Teste o seu aplicativo em tempo real com relação ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enquanto estiver reproduzindo as alterações do sistema de fonte.</span><span class="sxs-lookup"><span data-stu-id="992f0-119">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="992f0-120">Alterne para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando estiver satisfeito com a migração.</span><span class="sxs-lookup"><span data-stu-id="992f0-120">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
 <span data-ttu-id="992f0-121">Para obter mais informações, consulte [Visão geral da publicação Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="992f0-121">For more information, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
## <a name="publishing-data-to-non-sql-server-subscribers"></a><span data-ttu-id="992f0-122">Publicando dados para assinantes não SQL Server</span><span class="sxs-lookup"><span data-stu-id="992f0-122">Publishing Data to Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="992f0-123">Os seguintes bancos de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com suporte como Assinantes para as publicações transacionais e instantâneos:</span><span class="sxs-lookup"><span data-stu-id="992f0-123">The following non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases are supported as Subscribers to snapshot and transactional publications:</span></span>  
  
-   <span data-ttu-id="992f0-124">Oracle para todas as plataformas que o Oracle oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="992f0-124">Oracle for all platforms that Oracle supports.</span></span>  
  
-   <span data-ttu-id="992f0-125">IBM DB2 para AS400, MVS, Unix, Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="992f0-125">IBM DB2 for AS400, MVS, Unix, Linux, and Windows.</span></span>  
  
 <span data-ttu-id="992f0-126">Para obter mais informações, consulte [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="992f0-126">For more information, see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span>  
  
  
