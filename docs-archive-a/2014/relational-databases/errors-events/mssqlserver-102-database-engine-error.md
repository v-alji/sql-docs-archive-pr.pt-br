---
title: MSSQLSERVER_102 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569547"
---
# <a name="mssqlserver_102"></a><span data-ttu-id="a660f-102">MSSQLSERVER_102</span><span class="sxs-lookup"><span data-stu-id="a660f-102">MSSQLSERVER_102</span></span>
    
## <a name="details"></a><span data-ttu-id="a660f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a660f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a660f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a660f-104">Product Name</span></span>|<span data-ttu-id="a660f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a660f-105">SQL Server</span></span>|  
|<span data-ttu-id="a660f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a660f-106">Event ID</span></span>|<span data-ttu-id="a660f-107">102</span><span class="sxs-lookup"><span data-stu-id="a660f-107">102</span></span>|  
|<span data-ttu-id="a660f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a660f-108">Event Source</span></span>|<span data-ttu-id="a660f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a660f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a660f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a660f-110">Component</span></span>|<span data-ttu-id="a660f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a660f-111">SQLEngine</span></span>|  
|<span data-ttu-id="a660f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a660f-112">Symbolic Name</span></span>|<span data-ttu-id="a660f-113">P_SYNTAXERR2</span><span class="sxs-lookup"><span data-stu-id="a660f-113">P_SYNTAXERR2</span></span>|  
|<span data-ttu-id="a660f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a660f-114">Message Text</span></span>|<span data-ttu-id="a660f-115">Sintaxe incorreta próxima a '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="a660f-115">Incorrect syntax near '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a660f-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="a660f-116">Explanation</span></span>  
 <span data-ttu-id="a660f-117">Indica um erro de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="a660f-117">Indicates a syntax error.</span></span> <span data-ttu-id="a660f-118">Informações adicionais não estão disponíveis porque o erro impede o [!INCLUDE[ssDE](../../includes/ssde-md.md)] de processar a instrução.</span><span class="sxs-lookup"><span data-stu-id="a660f-118">Additional information is not available because the error prevents the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from processing the statement.</span></span>  
  
 <span data-ttu-id="a660f-119">Pode ser causado pela tentativa de criar uma chave simétrica que usa a criptografia RC4 ou RC4_128 preterido, quando fora do modo de compatibilidade 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="a660f-119">Can be caused by attempting to create a symmetric key using the deprecated RC4 or RC4_128 encryption, when not in 90 or 100 compatibility mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a660f-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a660f-120">User Action</span></span>  
 <span data-ttu-id="a660f-121">Procure os erros de sintaxe na instrução [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a660f-121">Search the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement for syntax errors.</span></span>  
  
 <span data-ttu-id="a660f-122">Se for criar uma chave simétrica usando RC4 ou RC4_128, selecione uma criptografia mais recente, como um dos algoritmos AES.</span><span class="sxs-lookup"><span data-stu-id="a660f-122">If creating a symmetric key using the RC4 or RC4_128, select a newer encryption such as one of the AES algorithms.</span></span> <span data-ttu-id="a660f-123">(Recomendado.) Se for necessário usar RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL para definir o banco de dados com o nível de compatibilidade 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="a660f-123">(Recommended.) If you must use RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL to set the database to compatibility level 90 or 100.</span></span> <span data-ttu-id="a660f-124">(Não recomendável.)</span><span class="sxs-lookup"><span data-stu-id="a660f-124">(Not recommended.)</span></span>  
  
  
