---
title: MSSQLSERVER_1101 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581914"
---
# <a name="mssqlserver_1101"></a><span data-ttu-id="bd26d-102">MSSQLSERVER_1101</span><span class="sxs-lookup"><span data-stu-id="bd26d-102">MSSQLSERVER_1101</span></span>
    
## <a name="details"></a><span data-ttu-id="bd26d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bd26d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd26d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="bd26d-104">Product Name</span></span>|<span data-ttu-id="bd26d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd26d-105">SQL Server</span></span>|  
|<span data-ttu-id="bd26d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bd26d-106">Event ID</span></span>|<span data-ttu-id="bd26d-107">1101</span><span class="sxs-lookup"><span data-stu-id="bd26d-107">1101</span></span>|  
|<span data-ttu-id="bd26d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="bd26d-108">Event Source</span></span>|<span data-ttu-id="bd26d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd26d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd26d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bd26d-110">Component</span></span>|<span data-ttu-id="bd26d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bd26d-111">SQLEngine</span></span>|  
|<span data-ttu-id="bd26d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="bd26d-112">Symbolic Name</span></span>|<span data-ttu-id="bd26d-113">NOALLOCPG</span><span class="sxs-lookup"><span data-stu-id="bd26d-113">NOALLOCPG</span></span>|  
|<span data-ttu-id="bd26d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="bd26d-114">Message Text</span></span>|<span data-ttu-id="bd26d-115">Não foi possível alocar uma nova página ao banco de dados '%.\*ls' devido a espaço em disco insuficiente no grupo de arquivos '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="bd26d-115">Could not allocate a new page for database '%.\*ls' because of insufficient disk space in filegroup '%.\*ls'.</span></span> <span data-ttu-id="bd26d-116">Crie o espaço necessário descartando objetos no grupo de arquivos, adicionando arquivos ao grupo de arquivos ou definindo o aumento automático para arquivos existentes no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd26d-116">Create the necessary space by dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd26d-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="bd26d-117">Explanation</span></span>  
 <span data-ttu-id="bd26d-118">Não há espaço disponível em disco em um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd26d-118">No disk space available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd26d-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="bd26d-119">User Action</span></span>  
 <span data-ttu-id="bd26d-120">As ações a seguir podem criar espaço disponível no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd26d-120">The following actions may make space available in the filegroup.</span></span>  
  
-   <span data-ttu-id="bd26d-121">Ative o AUTOGROW.</span><span class="sxs-lookup"><span data-stu-id="bd26d-121">Turn on AUTOGROW.</span></span>  
  
-   <span data-ttu-id="bd26d-122">Adicione mais arquivos ao grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd26d-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="bd26d-123">Libere espaço em disco descartando índices ou tabelas desnecessários no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd26d-123">Free up disk space by dropping unnecessary indexes or tables in the filegroup.</span></span>  
  
  
