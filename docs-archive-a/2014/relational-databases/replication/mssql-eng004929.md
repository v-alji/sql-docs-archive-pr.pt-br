---
title: MSSQL_ENG004929 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG004929 error
ms.assetid: 1d9b1d88-1fbf-4089-b392-687d3b0220ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b202b28eabe1feb1ed180bda0d58d2e84c7d10d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569370"
---
# <a name="mssql_eng004929"></a><span data-ttu-id="d5dce-102">MSSQL_ENG004929</span><span class="sxs-lookup"><span data-stu-id="d5dce-102">MSSQL_ENG004929</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d5dce-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="d5dce-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5dce-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d5dce-104">Product Name</span></span>|<span data-ttu-id="d5dce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5dce-105">SQL Server</span></span>|  
|<span data-ttu-id="d5dce-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d5dce-106">Event ID</span></span>|<span data-ttu-id="d5dce-107">4929</span><span class="sxs-lookup"><span data-stu-id="d5dce-107">4929</span></span>|  
|<span data-ttu-id="d5dce-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d5dce-108">Event Source</span></span>|<span data-ttu-id="d5dce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d5dce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d5dce-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d5dce-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d5dce-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d5dce-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d5dce-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d5dce-112">Message Text</span></span>|<span data-ttu-id="d5dce-113">Não é possível alterar %S_MSG '%.\*ls' porque ele está sendo publicado para replicação.</span><span class="sxs-lookup"><span data-stu-id="d5dce-113">Cannot alter the %S_MSG '%.\*ls' because it is being published for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5dce-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="d5dce-114">Explanation</span></span>  
 <span data-ttu-id="d5dce-115">Geralmente, esse erro ocorre ao tentar descartar a restrição de chave primária em uma tabela publicada para replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="d5dce-115">This error typically occurs if you attempt to drop the primary key constraint on a table that is published for transactional replication.</span></span> <span data-ttu-id="d5dce-116">As replicações transacionais exigem uma chave primária para cada tabela publicada; portanto, não é possível descartar a restrição.</span><span class="sxs-lookup"><span data-stu-id="d5dce-116">Transactional replication requires a primary key for each published table; therefore the constraint cannot be dropped.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5dce-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d5dce-117">User Action</span></span>  
 <span data-ttu-id="d5dce-118">Para descartar a restrição, primeiro descarte o artigo associado à tabela.</span><span class="sxs-lookup"><span data-stu-id="d5dce-118">To drop the constraint, first drop the article associated with the table.</span></span> <span data-ttu-id="d5dce-119">Para obter mais informações, consulte [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md) (Adicionar e remover artigos para/de publicações existentes).</span><span class="sxs-lookup"><span data-stu-id="d5dce-119">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span> <span data-ttu-id="d5dce-120">Se esse erro ocorrer em um banco de dados não replicado, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para garantir que os objetos nos bancos de dados não são marcados como replicados.</span><span class="sxs-lookup"><span data-stu-id="d5dce-120">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5dce-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5dce-121">See Also</span></span>  
 [<span data-ttu-id="d5dce-122">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="d5dce-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
