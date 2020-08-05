---
title: MSSQLSERVER_7711 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e29b2ea993e8e5332ef03b05f628dc791e20aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574021"
---
# <a name="mssqlserver_7711"></a><span data-ttu-id="e85a7-102">MSSQLSERVER_7711</span><span class="sxs-lookup"><span data-stu-id="e85a7-102">MSSQLSERVER_7711</span></span>
    
## <a name="details"></a><span data-ttu-id="e85a7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e85a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e85a7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e85a7-104">Product Name</span></span>|<span data-ttu-id="e85a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e85a7-105">SQL Server</span></span>|  
|<span data-ttu-id="e85a7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e85a7-106">Event ID</span></span>|<span data-ttu-id="e85a7-107">7711</span><span class="sxs-lookup"><span data-stu-id="e85a7-107">7711</span></span>|  
|<span data-ttu-id="e85a7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e85a7-108">Event Source</span></span>|<span data-ttu-id="e85a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e85a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e85a7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e85a7-110">Component</span></span>|<span data-ttu-id="e85a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e85a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="e85a7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e85a7-112">Symbolic Name</span></span>|<span data-ttu-id="e85a7-113">PRT_RANGE_OVERLAP</span><span class="sxs-lookup"><span data-stu-id="e85a7-113">PRT_RANGE_OVERLAP</span></span>|  
|<span data-ttu-id="e85a7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e85a7-114">Message Text</span></span>|<span data-ttu-id="e85a7-115">A opção DATA_COMPRESSION foi especificada mais de uma vez para a tabela ou o índice ou para uma de suas partições.</span><span class="sxs-lookup"><span data-stu-id="e85a7-115">The DATA_COMPRESSION option was specified more than once for the table or index or one of its partitions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e85a7-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="e85a7-116">Explanation</span></span>  
 <span data-ttu-id="e85a7-117">Ocorreu um erro na opção DATA_COMPRESSION em uma das seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="e85a7-117">An error occurred in the DATA_COMPRESSION option in one of the following statements:</span></span>  
  
-   <span data-ttu-id="e85a7-118">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="e85a7-118">CREATE TABLE</span></span>  
  
-   <span data-ttu-id="e85a7-119">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="e85a7-119">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="e85a7-120">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="e85a7-120">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="e85a7-121">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="e85a7-121">ALTER INDEX</span></span>  
  
 <span data-ttu-id="e85a7-122">Se a tabela ou o índice citado for particionado, a opção DATA_COMPRESSION foi listada mais de uma vez para pelo menos uma das partições.</span><span class="sxs-lookup"><span data-stu-id="e85a7-122">If the table or index cited is partitioned, the DATA_COMPRESSION option was listed more than one time for at least one of the partitions.</span></span> <span data-ttu-id="e85a7-123">Se a tabela ou o índice não for particionado, a opção DATA_COMPRESSION foi citada mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="e85a7-123">If the table or index is not partitioned, the DATA_COMPRESSION option was cited more than one time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e85a7-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e85a7-124">User Action</span></span>  
 <span data-ttu-id="e85a7-125">Para uma tabela ou um índice particionado, verifique se a opção DATA_COMPRESSION está especificada somente uma vez para cada partição.</span><span class="sxs-lookup"><span data-stu-id="e85a7-125">For a partitioned table or index, make sure that the DATA_COMPRESSION option is specified only one time for each partition.</span></span> <span data-ttu-id="e85a7-126">Para uma tabela ou um índice não particionado, use a opção DATA_COMPRESSION somente uma vez na instrução.</span><span class="sxs-lookup"><span data-stu-id="e85a7-126">For a table or index that is not partitioned, use the DATA_COMPRESSION option only one time in the statement.</span></span>  
  
  
