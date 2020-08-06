---
title: MSSQLSERVER_3413 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3413 (Database Engine error)
ms.assetid: 3fa07637-ba93-4633-aaf2-ade7d18bc487
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a5d59ea61cff7051c3e1163a463c29443c553923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581849"
---
# <a name="mssqlserver_3413"></a><span data-ttu-id="53338-102">MSSQLSERVER_3413</span><span class="sxs-lookup"><span data-stu-id="53338-102">MSSQLSERVER_3413</span></span>
    
## <a name="details"></a><span data-ttu-id="53338-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="53338-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53338-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="53338-104">Product Name</span></span>|<span data-ttu-id="53338-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53338-105">SQL Server</span></span>|  
|<span data-ttu-id="53338-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="53338-106">Event ID</span></span>|<span data-ttu-id="53338-107">3413</span><span class="sxs-lookup"><span data-stu-id="53338-107">3413</span></span>|  
|<span data-ttu-id="53338-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="53338-108">Event Source</span></span>|<span data-ttu-id="53338-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53338-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53338-110">Componente</span><span class="sxs-lookup"><span data-stu-id="53338-110">Component</span></span>|<span data-ttu-id="53338-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53338-111">SQLEngine</span></span>|  
|<span data-ttu-id="53338-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="53338-112">Symbolic Name</span></span>|<span data-ttu-id="53338-113">MARKDB</span><span class="sxs-lookup"><span data-stu-id="53338-113">MARKDB</span></span>|  
|<span data-ttu-id="53338-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="53338-114">Message Text</span></span>|<span data-ttu-id="53338-115">ID do banco de dados %d.</span><span class="sxs-lookup"><span data-stu-id="53338-115">Database ID %d.</span></span> <span data-ttu-id="53338-116">Não foi possível marcar o banco de dados como suspeito.</span><span class="sxs-lookup"><span data-stu-id="53338-116">Could not mark database as suspect.</span></span> <span data-ttu-id="53338-117">Falha no exame de Getnext NC em sys.databases.database_id.</span><span class="sxs-lookup"><span data-stu-id="53338-117">Getnext NC scan on sys.databases.database_id failed.</span></span> <span data-ttu-id="53338-118">Consulte os erros anteriores no log de erros para identificar a causa e corrigir os problemas associados.</span><span class="sxs-lookup"><span data-stu-id="53338-118">Refer to previous errors in the error log to identify the cause and correct any associated problems.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53338-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="53338-119">Explanation</span></span>  
 <span data-ttu-id="53338-120">Houve uma falha inesperada ao tentar marcar um banco de dados de usuário como SUSPECT no catálogo.</span><span class="sxs-lookup"><span data-stu-id="53338-120">There was an unexpected failure while trying to mark a user database as SUSPECT in the catalog.</span></span> <span data-ttu-id="53338-121">O estado SUSPECT não será persistente.</span><span class="sxs-lookup"><span data-stu-id="53338-121">The SUSPECT state will not be persisted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53338-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="53338-122">User Action</span></span>  
 <span data-ttu-id="53338-123">Consulte os erros anteriores e corrija o problema.</span><span class="sxs-lookup"><span data-stu-id="53338-123">See previous errors and correct the problem.</span></span>  
  
  
