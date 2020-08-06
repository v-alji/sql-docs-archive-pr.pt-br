---
title: Publicadores não SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f15f07dbf294d697afd385318f3dbf1447c8e2d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569356"
---
# <a name="non-sql-server-publishers"></a><span data-ttu-id="235dc-102">editores não SQL Server</span><span class="sxs-lookup"><span data-stu-id="235dc-102">Non-SQL Server Publishers</span></span>
  <span data-ttu-id="235dc-103">A publicação de dados de não [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] origens permite consolidar dados no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="235dc-103">Publishing data from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sources allows you to consolidate data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="235dc-104">O[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pode assinar um instantâneo ou dados transacionais publicados de um banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="235dc-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can subscribe to snapshot or transactional data published from an Oracle database.</span></span> <span data-ttu-id="235dc-105">Para obter mais informações sobre a publicação do Oracle, consulte [Oracle Publishing Overview](oracle-publishing-overview.md) (Visão geral de publicação do Oracle).</span><span class="sxs-lookup"><span data-stu-id="235dc-105">For more information about publishing from Oracle, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="235dc-106">A replicação heterogênea para assinantes que não são do SQL Server foi preterida.</span><span class="sxs-lookup"><span data-stu-id="235dc-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="235dc-107">A publicação Oracle foi preterida.</span><span class="sxs-lookup"><span data-stu-id="235dc-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="235dc-108">Para mover dados, crie soluções usando a captura de dados de alterações e o [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="235dc-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="235dc-109">Publicar de banco de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é o ideal para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="235dc-109">Publishing from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="235dc-110">Cenário</span><span class="sxs-lookup"><span data-stu-id="235dc-110">Scenario</span></span>|<span data-ttu-id="235dc-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="235dc-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="235dc-112">Implantações de aplicativos do[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="235dc-112">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="235dc-113">Desenvolva com o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enquanto estiver operando em dados replicados de banco de dados que não são do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="235dc-113">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="235dc-114">Servidores de preparo de data warehouse</span><span class="sxs-lookup"><span data-stu-id="235dc-114">Data warehousing staging servers</span></span>|<span data-ttu-id="235dc-115">Mantenha os bancos de dados de preparo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizado com um banco de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="235dc-115">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="235dc-116">Migração para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="235dc-116">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="235dc-117">Teste o seu aplicativo em tempo real com relação ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enquanto estiver reproduzindo as alterações do sistema de fonte.</span><span class="sxs-lookup"><span data-stu-id="235dc-117">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="235dc-118">Alterne para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando estiver satisfeito com a migração.</span><span class="sxs-lookup"><span data-stu-id="235dc-118">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="235dc-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="235dc-119">See Also</span></span>  
 [<span data-ttu-id="235dc-120">Replicação de banco de dados heterogênea</span><span class="sxs-lookup"><span data-stu-id="235dc-120">Heterogeneous Database Replication</span></span>](heterogeneous-database-replication.md)  
  
  
