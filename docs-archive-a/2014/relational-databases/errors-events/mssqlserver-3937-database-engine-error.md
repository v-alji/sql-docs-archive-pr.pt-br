---
title: MSSQLSERVER_3937 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3937 (Database Engine error)
ms.assetid: 312d5bbe-c8de-42db-af4b-4ccb448ce6ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac466e6eb50ad4b7a8848a1159963cb0fd35e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680429"
---
# <a name="mssqlserver_3937"></a><span data-ttu-id="0a32b-102">MSSQLSERVER_3937</span><span class="sxs-lookup"><span data-stu-id="0a32b-102">MSSQLSERVER_3937</span></span>
    
## <a name="details"></a><span data-ttu-id="0a32b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0a32b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a32b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="0a32b-104">Product Name</span></span>|<span data-ttu-id="0a32b-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0a32b-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0a32b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0a32b-106">Event ID</span></span>|<span data-ttu-id="0a32b-107">3937</span><span class="sxs-lookup"><span data-stu-id="0a32b-107">3937</span></span>|  
|<span data-ttu-id="0a32b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="0a32b-108">Event Source</span></span>|<span data-ttu-id="0a32b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0a32b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0a32b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0a32b-110">Component</span></span>|<span data-ttu-id="0a32b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0a32b-111">SQLEngine</span></span>|  
|<span data-ttu-id="0a32b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="0a32b-112">Symbolic Name</span></span>|<span data-ttu-id="0a32b-113">XACT_FILESTREAM_ROLLBACK_ERROR</span><span class="sxs-lookup"><span data-stu-id="0a32b-113">XACT_FILESTREAM_ROLLBACK_ERROR</span></span>|  
|<span data-ttu-id="0a32b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="0a32b-114">Message Text</span></span>|<span data-ttu-id="0a32b-115">Erro ao tentar notificar o driver do filtro FILESTREAM que uma transação foi revertida.</span><span class="sxs-lookup"><span data-stu-id="0a32b-115">An error occurred while trying to notify the FILESTREAM filter driver that a transaction was rolled back.</span></span> <span data-ttu-id="0a32b-116">Código de erro: 0x%0x.</span><span class="sxs-lookup"><span data-stu-id="0a32b-116">Error code: 0x%0x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a32b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="0a32b-117">Explanation</span></span>  
 <span data-ttu-id="0a32b-118">Um erro foi retornado pelo driver de RsFx ao emitir uma notificação de reversão para uma transação.</span><span class="sxs-lookup"><span data-stu-id="0a32b-118">An error was returned by the RsFx driver when issuing a rollback notification for a transaction.</span></span> <span data-ttu-id="0a32b-119">Isso provavelmente foi provocado por uma falta de recurso.</span><span class="sxs-lookup"><span data-stu-id="0a32b-119">This is probably caused by a resource shortage.</span></span> <span data-ttu-id="0a32b-120">Isso pode causar um pequeno vazamento de memória no driver do filtro de RsFx, mas ele será liberado quando o processo sqlservr.exe que criou a transação sair.</span><span class="sxs-lookup"><span data-stu-id="0a32b-120">This can cause a small memory leak in the RsFx filter driver, but this will be freed when the sqlservr.exe process that created the transaction exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a32b-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="0a32b-121">User Action</span></span>  
  
