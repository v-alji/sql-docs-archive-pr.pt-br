---
title: MSSQLSERVER_601 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "601"
helpviewer_keywords:
- 601 (Database Engine error)
ms.assetid: 2039cc0a-9a43-4369-a04a-935e384388b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 459a983d72a91e628e8cc33636d3abd81998f1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583100"
---
# <a name="mssqlserver_601"></a><span data-ttu-id="4e328-102">MSSQLSERVER_601</span><span class="sxs-lookup"><span data-stu-id="4e328-102">MSSQLSERVER_601</span></span>
    
## <a name="details"></a><span data-ttu-id="4e328-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4e328-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e328-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4e328-104">Product Name</span></span>|<span data-ttu-id="4e328-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e328-105">SQL Server</span></span>|  
|<span data-ttu-id="4e328-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4e328-106">Event ID</span></span>|<span data-ttu-id="4e328-107">601</span><span class="sxs-lookup"><span data-stu-id="4e328-107">601</span></span>|  
|<span data-ttu-id="4e328-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4e328-108">Event Source</span></span>|<span data-ttu-id="4e328-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4e328-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4e328-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4e328-110">Component</span></span>|<span data-ttu-id="4e328-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4e328-111">SQLEngine</span></span>|  
|<span data-ttu-id="4e328-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4e328-112">Symbolic Name</span></span>||  
|<span data-ttu-id="4e328-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4e328-113">Message Text</span></span>|<span data-ttu-id="4e328-114">Não foi possível continuar a verificação com NOLOCK devido ao movimento de dados.</span><span class="sxs-lookup"><span data-stu-id="4e328-114">Could not continue scan with NOLOCK due to data movement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4e328-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="4e328-115">Explanation</span></span>  
 <span data-ttu-id="4e328-116">O [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] não pode continuar a execução da consulta porque está tentando ler dados atualizados ou excluídos por outra transação.</span><span class="sxs-lookup"><span data-stu-id="4e328-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot continue executing the query because it is trying to read data that was updated or deleted by another transaction.</span></span> <span data-ttu-id="4e328-117">A consulta está usando ou dicas de bloqueio NOLOCK ou o nível de isolamento da transação READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="4e328-117">The query is using either the NOLOCK locking hint or the READ UNCOMMITTED transaction isolation level.</span></span>  
  
 <span data-ttu-id="4e328-118">Geralmente, o acesso aos dados que estão sendo alterados por outra transação é negado devido aos bloqueios dos dados.</span><span class="sxs-lookup"><span data-stu-id="4e328-118">Typically, access to data that is being changed by another transaction is denied because of locks put on the data.</span></span> <span data-ttu-id="4e328-119">Porém, a dica de bloqueio NOLOCK e o nível de isolamento da transação READ UNCOMMITTED permitem que uma consulta leia dados bloqueados por outra transação.</span><span class="sxs-lookup"><span data-stu-id="4e328-119">However, the NOLOCK locking hint and READ UNCOMMITTED transaction isolation level let a query read data that is locked by another transaction.</span></span> <span data-ttu-id="4e328-120">Isso é chamado de leitura suja, porque você pode ler valores que ainda não estão confirmados e estão sujeitos a mudanças.</span><span class="sxs-lookup"><span data-stu-id="4e328-120">This is referred to as a dirty read because you can read values that have not yet been committed and that are subject to change.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4e328-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4e328-121">User Action</span></span>  
 <span data-ttu-id="4e328-122">Este erro cancela a consulta.</span><span class="sxs-lookup"><span data-stu-id="4e328-122">This error cancels the query.</span></span> <span data-ttu-id="4e328-123">Envie a consulta novamente ou remova a dica de bloqueio NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="4e328-123">Either resubmit the query or remove the NOLOCK locking hint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e328-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e328-124">See Also</span></span>  
 <span data-ttu-id="4e328-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="4e328-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span></span>  
 <span data-ttu-id="4e328-126">[Dicas de tabela &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="4e328-126">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 <span data-ttu-id="4e328-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e328-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="4e328-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e328-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
  
  
