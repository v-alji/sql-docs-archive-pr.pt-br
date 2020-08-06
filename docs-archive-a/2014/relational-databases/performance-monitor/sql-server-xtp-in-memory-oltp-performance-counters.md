---
title: Contadores de desempenho XTP (OLTP na memória) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: fe3cbaf4-65f4-44c5-acc6-7b735cda0c5d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4363a526ada3694e92d18cac0d7abe8a26f6a92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679901"
---
# <a name="xtp-in-memory-oltp-performance-counters"></a><span data-ttu-id="bb61f-102">Contadores de desempenho de XTP (OLTP na memória)</span><span class="sxs-lookup"><span data-stu-id="bb61f-102">XTP (In-Memory OLTP) Performance Counters</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb61f-103">fornece objetos e contadores que podem ser usados pelo Monitor de Desempenho para monitorar a atividade OLTP in-memory.</span><span class="sxs-lookup"><span data-stu-id="bb61f-103">provides objects and counters that can be used by Performance Monitor to monitor In-Memory OLTP activity.</span></span>  
  
##  <a name="xtp-in-memory-oltp-performance-objects"></a><a name="SQLServerPOs"></a><span data-ttu-id="bb61f-104">Objetos de desempenho XTP (OLTP na memória)</span><span class="sxs-lookup"><span data-stu-id="bb61f-104">XTP (In-Memory OLTP) Performance Objects</span></span>  
 <span data-ttu-id="bb61f-105">A tabela a seguir descreve objetos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb61f-105">The following table describes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span>  
  
|<span data-ttu-id="bb61f-106">Objeto de desempenho</span><span class="sxs-lookup"><span data-stu-id="bb61f-106">Performance object</span></span>|<span data-ttu-id="bb61f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb61f-107">Description</span></span>|  
|------------------------|-----------------|  
|[<span data-ttu-id="bb61f-108">Cursores de XTP</span><span class="sxs-lookup"><span data-stu-id="bb61f-108">XTP Cursors</span></span>](../cursors.md)|<span data-ttu-id="bb61f-109">O objeto de desempenho Cursores de XTP contém os contadores relacionados aos cursores do mecanismo de XTP interno.</span><span class="sxs-lookup"><span data-stu-id="bb61f-109">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="bb61f-110">Os cursores são os blocos de construção de baixo nível que o mecanismo de XTP usa para processar consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb61f-110">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="bb61f-111">Como tal, você normalmente não tem controle direto sobre eles.</span><span class="sxs-lookup"><span data-stu-id="bb61f-111">As such, you do not typically have direct control over them.</span></span>|  
|[<span data-ttu-id="bb61f-112">Coleta de Lixo de XTP</span><span class="sxs-lookup"><span data-stu-id="bb61f-112">XTP Garbage Collection</span></span>](sql-server-xtp-garbage-collection.md)|<span data-ttu-id="bb61f-113">O objeto de desempenho Coleta de Lixo de XTP contém os contadores relacionados ao coletor de lixo do mecanismo de XTP.</span><span class="sxs-lookup"><span data-stu-id="bb61f-113">The XTP Garbage Collection performance object contains counters related to the XTP engine's garbage collector.</span></span>|  
|[<span data-ttu-id="bb61f-114">Processador Fantasma de XTP</span><span class="sxs-lookup"><span data-stu-id="bb61f-114">XTP Phantom Processor</span></span>](sql-server-xtp-phantom-processor.md)|<span data-ttu-id="bb61f-115">O objeto de desempenho Processador Fantasma de XTP contém os contadores relacionados ao subsistema de processamento fantasma do mecanismo de XTP.</span><span class="sxs-lookup"><span data-stu-id="bb61f-115">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="bb61f-116">Esse componente é responsável por detectar as linhas fantasmas nas transações que são executadas no nível de isolamento SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="bb61f-116">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>|  
|[<span data-ttu-id="bb61f-117">Armazenamento de XTP</span><span class="sxs-lookup"><span data-stu-id="bb61f-117">XTP Storage</span></span>](sql-server-xtp-storage.md)|<span data-ttu-id="bb61f-118">O objeto de desempenho do Armazenamento de XTP contém os contadores relacionados ao Armazenamento de XTP no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb61f-118">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="bb61f-119">Log de Transações de XTP</span><span class="sxs-lookup"><span data-stu-id="bb61f-119">XTP Transaction Log</span></span>](sql-server-xtp-transaction-log.md)|<span data-ttu-id="bb61f-120">O objeto de desempenho Log de Transações de XTP contém os contadores relacionados ao log de transações de XTP no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb61f-120">The XTP Transaction Log performance object contains counters related to XTP transaction logging in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="bb61f-121">Transações de XTP</span><span class="sxs-lookup"><span data-stu-id="bb61f-121">XTP Transactions</span></span>](sql-server-xtp-transactions.md)|<span data-ttu-id="bb61f-122">O objeto de desempenho Transações de XTP contém os contadores relacionados às transações do mecanismo de XTP no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb61f-122">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
  
