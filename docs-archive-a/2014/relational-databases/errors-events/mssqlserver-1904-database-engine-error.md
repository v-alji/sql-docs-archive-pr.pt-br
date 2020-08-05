---
title: MSSQLSERVER_1904 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 568cfe7499c041c2ee6a8ac3698b31698171bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573080"
---
# <a name="mssqlserver_1904"></a><span data-ttu-id="d5bd1-102">MSSQLSERVER_1904</span><span class="sxs-lookup"><span data-stu-id="d5bd1-102">MSSQLSERVER_1904</span></span>
    
## <a name="details"></a><span data-ttu-id="d5bd1-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d5bd1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5bd1-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d5bd1-104">Product Name</span></span>|<span data-ttu-id="d5bd1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5bd1-105">SQL Server</span></span>|  
|<span data-ttu-id="d5bd1-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d5bd1-106">Event ID</span></span>|<span data-ttu-id="d5bd1-107">1904</span><span class="sxs-lookup"><span data-stu-id="d5bd1-107">1904</span></span>|  
|<span data-ttu-id="d5bd1-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d5bd1-108">Event Source</span></span>|<span data-ttu-id="d5bd1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d5bd1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d5bd1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d5bd1-110">Component</span></span>|<span data-ttu-id="d5bd1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d5bd1-111">SQLEngine</span></span>|  
|<span data-ttu-id="d5bd1-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d5bd1-112">Symbolic Name</span></span>|<span data-ttu-id="d5bd1-113">KEYCOUNT</span><span class="sxs-lookup"><span data-stu-id="d5bd1-113">KEYCOUNT</span></span>|  
|<span data-ttu-id="d5bd1-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d5bd1-114">Message Text</span></span>|<span data-ttu-id="d5bd1-115">O %S_MSG '%.\*ls' na tabela '%.\*ls' tem %d nomes de coluna na lista de chaves %S_MSG.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-115">The %S_MSG '%.\*ls' on table '%.\*ls' has %d column names in %S_MSG key list.</span></span> <span data-ttu-id="d5bd1-116">O limite máximo para lista de colunas de chaves de índice ou de estatísticas é de %d.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-116">The maximum limit for index or statistics key column list is %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5bd1-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="d5bd1-117">Explanation</span></span>  
 <span data-ttu-id="d5bd1-118">A lista de colunas de chaves do índice ou das estatísticas especificadas excede o número máximo de colunas permitidas.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-118">The key column list for the specified index or statistics exceeds the maximum number of columns allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5bd1-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d5bd1-119">User Action</span></span>  
 <span data-ttu-id="d5bd1-120">Modifique a lista de colunas de chaves para incluir não mais do que o número máximo de colunas especificado.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-120">Modify the key column list to include no more than the specified maximum number of columns.</span></span>  
  
 <span data-ttu-id="d5bd1-121">Para índices não clusterizados, considere a possibilidade de usar a cláusula INCLUDE na instrução CREATE INDEX para adicionar colunas ao índice como colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-121">For nonclustered indexes, consider using the INCLUDE clause in the CREATE INDEX statement to add columns to the index as nonkey columns.</span></span> <span data-ttu-id="d5bd1-122">Com esse método, você evita exceder o limite atual de tamanho de índice, que é de até 16 colunas de chave.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-122">This method avoids exceeding the current index size limitation of a maximum of 16 key columns.</span></span> <span data-ttu-id="d5bd1-123">Para obter mais informações, consulte [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d5bd1-123">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bd1-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5bd1-124">See Also</span></span>  
 <span data-ttu-id="d5bd1-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5bd1-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="d5bd1-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d5bd1-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-statistics-transact-sql)  
  
  
