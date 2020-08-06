---
title: MSSQLSERVER_3417 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 680e5a4266c7d0d9aaacb7b3deb9525a002077e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581845"
---
# <a name="mssqlserver_3417"></a><span data-ttu-id="69e81-102">MSSQLSERVER_3417</span><span class="sxs-lookup"><span data-stu-id="69e81-102">MSSQLSERVER_3417</span></span>
    
## <a name="details"></a><span data-ttu-id="69e81-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="69e81-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69e81-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="69e81-104">Product Name</span></span>|<span data-ttu-id="69e81-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="69e81-105">SQL Server</span></span>|  
|<span data-ttu-id="69e81-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="69e81-106">Event ID</span></span>|<span data-ttu-id="69e81-107">3417</span><span class="sxs-lookup"><span data-stu-id="69e81-107">3417</span></span>|  
|<span data-ttu-id="69e81-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="69e81-108">Event Source</span></span>|<span data-ttu-id="69e81-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="69e81-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="69e81-110">Componente</span><span class="sxs-lookup"><span data-stu-id="69e81-110">Component</span></span>|<span data-ttu-id="69e81-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="69e81-111">SQLEngine</span></span>|  
|<span data-ttu-id="69e81-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="69e81-112">Symbolic Name</span></span>|<span data-ttu-id="69e81-113">REC_BADMASTER</span><span class="sxs-lookup"><span data-stu-id="69e81-113">REC_BADMASTER</span></span>|  
|<span data-ttu-id="69e81-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="69e81-114">Message Text</span></span>|<span data-ttu-id="69e81-115">Não é possível recuperar o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="69e81-115">Cannot recover the master database.</span></span> <span data-ttu-id="69e81-116">O SQL Server não pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="69e81-116">SQL Server is unable to run.</span></span> <span data-ttu-id="69e81-117">Restaure o banco de dados mestre usando um backup completo, repare-o ou recrie-o.</span><span class="sxs-lookup"><span data-stu-id="69e81-117">Restore master from a full backup, repair it, or rebuild it.</span></span> <span data-ttu-id="69e81-118">Para obter mais informações sobre como recriar o banco de dados mestre, consulte os Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69e81-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69e81-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="69e81-119">Explanation</span></span>  
 <span data-ttu-id="69e81-120">O SQL Server não pode iniciar o banco de dados **mestre**.</span><span class="sxs-lookup"><span data-stu-id="69e81-120">SQL Server cannot start the **master** database.</span></span> <span data-ttu-id="69e81-121">Se o banco de dados **master** ou **tempdb** não puderem ficar online, o SQL Server não poderá ser executado.</span><span class="sxs-lookup"><span data-stu-id="69e81-121">If the **master** or **tempdb** cannot be brought online, SQL Server cannot run.</span></span> <span data-ttu-id="69e81-122">Esse erro normalmente é precedido por outros erros.</span><span class="sxs-lookup"><span data-stu-id="69e81-122">This error is usually preceded by other errors.</span></span> <span data-ttu-id="69e81-123">Revise os logs de erros para encontrar a causa original.</span><span class="sxs-lookup"><span data-stu-id="69e81-123">Review error logs to find the root cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69e81-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="69e81-124">User Action</span></span>  
 <span data-ttu-id="69e81-125">Restaure o backup do banco de dados ou repare o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="69e81-125">Restore backup of the database or repair the database.</span></span>  
  
  
