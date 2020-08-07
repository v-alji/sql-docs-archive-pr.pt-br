---
title: MSSQLSERVER_10737 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576445"
---
# <a name="mssqlserver_10737"></a><span data-ttu-id="bb33a-102">MSSQLSERVER_10737</span><span class="sxs-lookup"><span data-stu-id="bb33a-102">MSSQLSERVER_10737</span></span>
    
## <a name="details"></a><span data-ttu-id="bb33a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bb33a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb33a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="bb33a-104">Product Name</span></span>|<span data-ttu-id="bb33a-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb33a-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb33a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bb33a-106">Event ID</span></span>|<span data-ttu-id="bb33a-107">10737</span><span class="sxs-lookup"><span data-stu-id="bb33a-107">10737</span></span>|  
|<span data-ttu-id="bb33a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="bb33a-108">Event Source</span></span>|<span data-ttu-id="bb33a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb33a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb33a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bb33a-110">Component</span></span>|<span data-ttu-id="bb33a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb33a-111">SQLEngine</span></span>|  
|<span data-ttu-id="bb33a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="bb33a-112">Symbolic Name</span></span>|<span data-ttu-id="bb33a-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span><span class="sxs-lookup"><span data-stu-id="bb33a-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span></span>|  
|<span data-ttu-id="bb33a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="bb33a-114">Message Text</span></span>|<span data-ttu-id="bb33a-115">Em uma instrução ALTER TABLE REBUILD ou ALTER INDEX REBUILD, quando uma partição é especificada em uma cláusula DATA_COMPRESSION, especifique PARTITION=ALL.</span><span class="sxs-lookup"><span data-stu-id="bb33a-115">In an ALTER TABLE REBUILD or ALTER INDEX REBUILD statement, when a partition is specified in a DATA_COMPRESSION clause, PARTITION=ALL must be specified.</span></span> <span data-ttu-id="bb33a-116">A cláusula PARTITION=ALL é usada para reforçar que todas as partições da tabela ou do índice serão reconstruídas, mesmo que apenas um subconjunto seja especificado na cláusula DATA_COMPRESSION.</span><span class="sxs-lookup"><span data-stu-id="bb33a-116">The PARTITION=ALL clause is used to reinforce that all partitions of the table or index will be rebuilt, even if only a subset is specified in the DATA_COMPRESSION clause.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="bb33a-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="bb33a-117">User Action</span></span>  
 <span data-ttu-id="bb33a-118">Adicione a cláusula PARTITION=ALL à instrução ALTER TABLE ou ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="bb33a-118">Add the PARTITION=ALL clause to the ALTER TABLE or ALTER INDEX statement.</span></span> <span data-ttu-id="bb33a-119">Se preferir, recompile uma partição específica e use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span><span class="sxs-lookup"><span data-stu-id="bb33a-119">Or, to rebuild a specific partition, use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span></span>  
  
  
