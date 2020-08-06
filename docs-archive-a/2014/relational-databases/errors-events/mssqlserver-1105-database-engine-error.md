---
title: MSSQLSERVER_1105 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dea326fab7edd6a5c155c8f0182bffc044505eb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569545"
---
# <a name="mssqlserver_1105"></a><span data-ttu-id="eee76-102">MSSQLSERVER_1105</span><span class="sxs-lookup"><span data-stu-id="eee76-102">MSSQLSERVER_1105</span></span>
    
## <a name="details"></a><span data-ttu-id="eee76-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="eee76-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eee76-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="eee76-104">Product Name</span></span>|<span data-ttu-id="eee76-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee76-105">SQL Server</span></span>|  
|<span data-ttu-id="eee76-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="eee76-106">Event ID</span></span>|<span data-ttu-id="eee76-107">1105</span><span class="sxs-lookup"><span data-stu-id="eee76-107">1105</span></span>|  
|<span data-ttu-id="eee76-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="eee76-108">Event Source</span></span>|<span data-ttu-id="eee76-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eee76-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eee76-110">Componente</span><span class="sxs-lookup"><span data-stu-id="eee76-110">Component</span></span>|<span data-ttu-id="eee76-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eee76-111">SQLEngine</span></span>|  
|<span data-ttu-id="eee76-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="eee76-112">Symbolic Name</span></span>|<span data-ttu-id="eee76-113">NO_MORE_SPACE_IN_FG</span><span class="sxs-lookup"><span data-stu-id="eee76-113">NO_MORE_SPACE_IN_FG</span></span>|  
|<span data-ttu-id="eee76-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="eee76-114">Message Text</span></span>|<span data-ttu-id="eee76-115">Não foi possível alocar espaço ao objeto '%.\*ls'%.\*ls no banco de dados '%.\*ls' porque o grupo de arquivos '%.\*ls' está cheio.</span><span class="sxs-lookup"><span data-stu-id="eee76-115">Could not allocate space for object '%.\*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full.</span></span> <span data-ttu-id="eee76-116">Crie espaço em disco excluindo arquivos desnecessários, descartando objetos no grupo de arquivos, adicionando arquivos ao grupo de arquivos ou definindo o aumento automático para arquivos existentes no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="eee76-116">Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eee76-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="eee76-117">Explanation</span></span>  
 <span data-ttu-id="eee76-118">Não há espaço disponível em disco em um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="eee76-118">No disk space is available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eee76-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="eee76-119">User Action</span></span>  
 <span data-ttu-id="eee76-120">As seguintes ações podem criar espaço disponível no grupo de arquivos:</span><span class="sxs-lookup"><span data-stu-id="eee76-120">The following actions may make space available in the filegroup:</span></span>  
  
-   <span data-ttu-id="eee76-121">Ative o aumento automático.</span><span class="sxs-lookup"><span data-stu-id="eee76-121">Turn on autogrow.</span></span>  
  
-   <span data-ttu-id="eee76-122">Adicione mais arquivos ao grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="eee76-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="eee76-123">Libere espaço em disco descartando índices ou tabelas que não sejam mais necessários.</span><span class="sxs-lookup"><span data-stu-id="eee76-123">Free disk space by dropping index or tables that are no longer needed.</span></span>  
  
-   <span data-ttu-id="eee76-124">Para obter mais informações, consulte “Solucionando problemas de espaço de dados insuficiente no disco” nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee76-124">For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eee76-125">Quando um índice encontra-se em vários arquivos, o `ALTER INDEX REORGANIZE` pode retornar um erro 1105 quando um desses arquivos estiver cheio.</span><span class="sxs-lookup"><span data-stu-id="eee76-125">When an index is located on several files, `ALTER INDEX REORGANIZE` can return error 1105 when one of the files is full.</span></span> <span data-ttu-id="eee76-126">O processo de reorganização é bloqueado quando o processo tenta mover as linhas para o arquivo cheio.</span><span class="sxs-lookup"><span data-stu-id="eee76-126">The reorganization process is blocked when the process tries to move rows to the full file.</span></span> <span data-ttu-id="eee76-127">Como alternativa a esta limitação, execute um `ALTER INDEX REBUILD` em vez de `ALTER INDEX REORGANIZE` ou aumente o limite de crescimento dos arquivos cheios.</span><span class="sxs-lookup"><span data-stu-id="eee76-127">To work around this limitation perform an `ALTER INDEX REBUILD` instead of `ALTER INDEX REORGANIZE` or increase the file growth limit of any files that are full.</span></span>  
  
  
