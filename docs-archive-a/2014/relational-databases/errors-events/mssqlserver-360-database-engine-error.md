---
title: MSSQLSERVER_360 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 360 (Database Engine error)
ms.assetid: e2b7c1b2-3679-4206-9b25-6bd55ef96a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b30311d7f55231c1e7a6d5969d49c5d1bc07a848
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572580"
---
# <a name="mssqlserver_360"></a><span data-ttu-id="2a9e6-102">MSSQLSERVER_360</span><span class="sxs-lookup"><span data-stu-id="2a9e6-102">MSSQLSERVER_360</span></span>
    
## <a name="details"></a><span data-ttu-id="2a9e6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2a9e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a9e6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2a9e6-104">Product Name</span></span>|<span data-ttu-id="2a9e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a9e6-105">SQL Server</span></span>|  
|<span data-ttu-id="2a9e6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2a9e6-106">Event ID</span></span>|<span data-ttu-id="2a9e6-107">360</span><span class="sxs-lookup"><span data-stu-id="2a9e6-107">360</span></span>|  
|<span data-ttu-id="2a9e6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2a9e6-108">Event Source</span></span>|<span data-ttu-id="2a9e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2a9e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2a9e6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2a9e6-110">Component</span></span>|<span data-ttu-id="2a9e6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2a9e6-111">SQLEngine</span></span>|  
|<span data-ttu-id="2a9e6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2a9e6-112">Symbolic Name</span></span>|<span data-ttu-id="2a9e6-113">DML_UPDATE_SPARSE_AND_COLSET</span><span class="sxs-lookup"><span data-stu-id="2a9e6-113">DML_UPDATE_SPARSE_AND_COLSET</span></span>|  
|<span data-ttu-id="2a9e6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2a9e6-114">Message Text</span></span>|<span data-ttu-id="2a9e6-115">A lista de colunas de destino de uma instrução INSERT, UPDATE ou MERGE não pode conter uma coluna esparsa e o conjunto de colunas que contém a coluna esparsa.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-115">The target column list of an INSERT, UPDATE, or MERGE statement cannot contain both a sparse column and the column set that contains the sparse column.</span></span> <span data-ttu-id="2a9e6-116">Reescreva a instrução para incluir a coluna esparsa ou o conjunto de colunas, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-116">Rewrite the statement to include either the sparse column or the column set, but not both.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a9e6-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="2a9e6-117">Explanation</span></span>  
 <span data-ttu-id="2a9e6-118">Um conjunto de colunas é uma representação em XML sem-tipo que combina algumas colunas de uma tabela em uma saída estruturada.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-118">A column set is an untyped XML representation that combines some columns of a table into a structured output.</span></span> <span data-ttu-id="2a9e6-119">Foi realizada uma tentativa para modificar o conjunto de colunas e a coluna incluída no conjunto de colunas, gerando duas referências para a mesma coluna.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-119">An attempt was made to modify both the column set and a column that is included in the column set, causing two references to the same column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a9e6-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2a9e6-120">User Action</span></span>  
 <span data-ttu-id="2a9e6-121">Reescreva a instrução para incluir referências à coluna esparsa ou ao conjunto de colunas, mas não inclua ambos na instrução.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-121">Rewrite the statement to include references to either the column or the column set, but do not include both in the statement.</span></span>  
  
  
