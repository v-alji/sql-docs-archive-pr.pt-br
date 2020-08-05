---
title: MSSQLSERVER_825 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 825 (Database Engine error)
ms.assetid: f69f8214-5af1-4769-878b-117ad6eaff52
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b17dfac371ad3c805fdbb0b5d3269fc451dd9d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573057"
---
# <a name="mssqlserver_825"></a><span data-ttu-id="d3bcd-102">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="d3bcd-102">MSSQLSERVER_825</span></span>
    
## <a name="details"></a><span data-ttu-id="d3bcd-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d3bcd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3bcd-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d3bcd-104">Product Name</span></span>|<span data-ttu-id="d3bcd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3bcd-105">SQL Server</span></span>|  
|<span data-ttu-id="d3bcd-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d3bcd-106">Event ID</span></span>|<span data-ttu-id="d3bcd-107">825</span><span class="sxs-lookup"><span data-stu-id="d3bcd-107">825</span></span>|  
|<span data-ttu-id="d3bcd-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d3bcd-108">Event Source</span></span>|<span data-ttu-id="d3bcd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d3bcd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d3bcd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d3bcd-110">Component</span></span>|<span data-ttu-id="d3bcd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d3bcd-111">SQLEngine</span></span>|  
|<span data-ttu-id="d3bcd-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d3bcd-112">Symbolic Name</span></span>|<span data-ttu-id="d3bcd-113">B_RETRYWORKED</span><span class="sxs-lookup"><span data-stu-id="d3bcd-113">B_RETRYWORKED</span></span>|  
|<span data-ttu-id="d3bcd-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d3bcd-114">Message Text</span></span>|<span data-ttu-id="d3bcd-115">Uma leitura do arquivo '%ls' no deslocamento %#016I64x teve êxito depois de falhar %d vezes com o erro: %ls.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-115">A read of the file '%ls' at offset %#016I64x succeeded after failing %d time(s) with error: %ls.</span></span> <span data-ttu-id="d3bcd-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="d3bcd-117">Essa condição de erro ameaça a integridade do banco de dados e precisa ser corrigida.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-117">This error condition threatens database integrity and must be corrected.</span></span> <span data-ttu-id="d3bcd-118">Faça uma verificação completa da consistência do banco de dados (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="d3bcd-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="d3bcd-119">Esse erro pode ter sido causado por vários fatores. Para obter mais informações, consulte os Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d3bcd-120">Explicação</span><span class="sxs-lookup"><span data-stu-id="d3bcd-120">Explanation</span></span>  
 <span data-ttu-id="d3bcd-121">Essa mensagem indica que a operação de leitura precisou ser reemitida pelo menos uma vez e indica um problema importante com o hardware de disco.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-121">This message indicates that the read operation had to be reissued at least one time, and indicates a major problem with the disk hardware.</span></span> <span data-ttu-id="d3bcd-122">Essa mensagem não indica um problema atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o problema de disco pode causar perda de dados ou corrupção no banco de dados se não for resolvido.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-122">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem, but the disk problem could cause data loss or database corruption if it is not resolved.</span></span> <span data-ttu-id="d3bcd-123">O log de eventos do sistema pode conter eventos relacionados que ajudem a diagnosticar o problema.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-123">The system event log may contain related events that help to diagnose the problem.</span></span> <span data-ttu-id="d3bcd-124">Para obter mais informações sobre erros de E/S, consulte [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) (Noções básicas de E/S do Microsoft SQL Server, Capítulo 2).</span><span class="sxs-lookup"><span data-stu-id="d3bcd-124">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d3bcd-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d3bcd-125">User Action</span></span>  
 <span data-ttu-id="d3bcd-126">As seguintes ações podem ajudá-lo a identificar e resolver o problema subjacente:</span><span class="sxs-lookup"><span data-stu-id="d3bcd-126">The following actions may help you identify and resolve the underlying problem:</span></span>  
  
-   <span data-ttu-id="d3bcd-127">Revise o log de erros e o texto variável nesta mensagem para encontrar pistas que expliquem o problema.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-127">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="d3bcd-128">Verifique seu sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-128">Check your disk system.</span></span> <span data-ttu-id="d3bcd-129">O problema pode estar relacionado aos discos, aos controladores de disco, aos cartões de matriz ou aos drivers de disco.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-129">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="d3bcd-130">Entre em contato com o fabricante do disco para obter os utilitários mais recentes para verificar o status do sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-130">Contact the disk manufacturer for the latest utilities for checking the status of your disk system.</span></span>  
  
-   <span data-ttu-id="d3bcd-131">Contate o fabricante do disco para obter as mais recentes atualizações de driver.</span><span class="sxs-lookup"><span data-stu-id="d3bcd-131">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
  
