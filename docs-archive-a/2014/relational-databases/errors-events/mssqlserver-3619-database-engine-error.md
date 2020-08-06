---
title: MSSQLSERVER_3619 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3619 (Database Engine error)
ms.assetid: 7d94f8d9-65ca-4fde-9c17-7b83e94a3779
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2328ee6366d47130a02c444bce65b7b655af7965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581837"
---
# <a name="mssqlserver_3619"></a><span data-ttu-id="cde23-102">MSSQLSERVER_3619</span><span class="sxs-lookup"><span data-stu-id="cde23-102">MSSQLSERVER_3619</span></span>
    
## <a name="details"></a><span data-ttu-id="cde23-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cde23-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cde23-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="cde23-104">Product Name</span></span>|<span data-ttu-id="cde23-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cde23-105">SQL Server</span></span>|  
|<span data-ttu-id="cde23-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="cde23-106">Event ID</span></span>|<span data-ttu-id="cde23-107">3619</span><span class="sxs-lookup"><span data-stu-id="cde23-107">3619</span></span>|  
|<span data-ttu-id="cde23-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="cde23-108">Event Source</span></span>|<span data-ttu-id="cde23-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cde23-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cde23-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cde23-110">Component</span></span>|<span data-ttu-id="cde23-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cde23-111">SQLEngine</span></span>|  
|<span data-ttu-id="cde23-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="cde23-112">Symbolic Name</span></span>|<span data-ttu-id="cde23-113">SYS_NOLOG</span><span class="sxs-lookup"><span data-stu-id="cde23-113">SYS_NOLOG</span></span>|  
|<span data-ttu-id="cde23-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="cde23-114">Message Text</span></span>|<span data-ttu-id="cde23-115">Não foi possível gravar um registro de ponto de verificação na ID do banco de dados %d porque não há espaço no log.</span><span class="sxs-lookup"><span data-stu-id="cde23-115">Could not write a checkpoint record in database ID %d because the log is out of space.</span></span> <span data-ttu-id="cde23-116">Entre em contato com o administrador de banco de dados para truncar o log ou aloque mais espaço para os arquivos de log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cde23-116">Contact the database administrator to truncate the log or allocate more space to the database log files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cde23-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="cde23-117">Explanation</span></span>  
 <span data-ttu-id="cde23-118">O log de transações tem espaço em disco insuficiente.</span><span class="sxs-lookup"><span data-stu-id="cde23-118">The transaction log is out of disk space.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cde23-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="cde23-119">User Action</span></span>  
 <span data-ttu-id="cde23-120">Trunque o log para liberar espaço ou aloque mais espaço para o log.</span><span class="sxs-lookup"><span data-stu-id="cde23-120">Truncate the log to release some space, or allocate more space to the log.</span></span> <span data-ttu-id="cde23-121">Para obter mais informações, consulte “Solucionando problemas em um log de transação completa (erro 9002)” nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cde23-121">For more information see, "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
  
