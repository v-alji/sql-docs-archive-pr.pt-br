---
title: MSSQLSERVER_11409 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569541"
---
# <a name="mssqlserver_11409"></a><span data-ttu-id="fd1a5-102">MSSQLSERVER_11409</span><span class="sxs-lookup"><span data-stu-id="fd1a5-102">MSSQLSERVER_11409</span></span>
    
## <a name="details"></a><span data-ttu-id="fd1a5-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fd1a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd1a5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="fd1a5-104">Product Name</span></span>|<span data-ttu-id="fd1a5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd1a5-105">SQL Server</span></span>|  
|<span data-ttu-id="fd1a5-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fd1a5-106">Event ID</span></span>|<span data-ttu-id="fd1a5-107">11409</span><span class="sxs-lookup"><span data-stu-id="fd1a5-107">11409</span></span>|  
|<span data-ttu-id="fd1a5-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="fd1a5-108">Event Source</span></span>|<span data-ttu-id="fd1a5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fd1a5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fd1a5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fd1a5-110">Component</span></span>|<span data-ttu-id="fd1a5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fd1a5-111">SQLEngine</span></span>|  
|<span data-ttu-id="fd1a5-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="fd1a5-112">Symbolic Name</span></span>|<span data-ttu-id="fd1a5-113">ALTERCOL_COLSET_DROP</span><span class="sxs-lookup"><span data-stu-id="fd1a5-113">ALTERCOL_COLSET_DROP</span></span>|  
|<span data-ttu-id="fd1a5-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fd1a5-114">Message Text</span></span>|<span data-ttu-id="fd1a5-115">Não é possível remover o conjunto de colunas '%.\*ls' na tabela '%.\*ls' porque ela contém mais de 1.025 colunas.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-115">Cannot drop column set '%.\*ls' in table '%.\*ls' because the table contains more than 1025 columns.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fd1a5-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="fd1a5-116">Explanation</span></span>  
 <span data-ttu-id="fd1a5-117">As tabelas podem conter no máximo 1024 colunas que não estejam designadas como esparsas ou computadas.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-117">Tables can contain a maximum of 1024 columns that are not designated as sparse, or computed.</span></span> <span data-ttu-id="fd1a5-118">Quando colunas esparsas fazem com que a tabela exceda as 1024 colunas, é necessário definir um conjunto de colunas para ela.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-118">When sparse columns cause the table to exceed 1024 columns, a column set must be defined for the table.</span></span> <span data-ttu-id="fd1a5-119">A tabela referenciada tem mais de 1024 colunas, e você tentou remover o conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-119">The table referenced has more than 1024 columns and you have attempted to remove the column set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd1a5-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fd1a5-120">User Action</span></span>  
 <span data-ttu-id="fd1a5-121">Com as colunas atuais da tabela, você deve reter o conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-121">With the current columns in the table, you must retain the column set.</span></span>  
  
 <span data-ttu-id="fd1a5-122">Para remover o conjunto de colunas, remova primeiro as colunas da tabela até que o número de colunas não ultrapasse 1024.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-122">To remove the column set, first remove columns from the table, until you have no more than 1024 columns.</span></span> <span data-ttu-id="fd1a5-123">Em seguida, você poderá remover o conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="fd1a5-123">Then, you can remove the column set.</span></span>  
  
  
