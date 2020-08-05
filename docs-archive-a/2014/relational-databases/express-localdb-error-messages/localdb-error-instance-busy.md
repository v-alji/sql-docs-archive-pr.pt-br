---
title: LOCALDB_ERROR_INSTANCE_BUSY | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 0ed9d0f8-3297-4e31-a3e9-4a827f381789
author: stevestein
ms.author: sstein
ms.openlocfilehash: c587ada5f08d3743f4fe7eafccfc923c38a2b7b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573005"
---
# <a name="localdb_error_instance_busy"></a><span data-ttu-id="e7410-102">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="e7410-102">LOCALDB_ERROR_INSTANCE_BUSY</span></span>
    
## <a name="details"></a><span data-ttu-id="e7410-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e7410-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7410-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e7410-104">Product Name</span></span>|<span data-ttu-id="e7410-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7410-105">SQL Server</span></span>|  
|<span data-ttu-id="e7410-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e7410-106">Event ID</span></span>|<span data-ttu-id="e7410-107">274</span><span class="sxs-lookup"><span data-stu-id="e7410-107">274</span></span>|  
|<span data-ttu-id="e7410-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e7410-108">Event Source</span></span>|<span data-ttu-id="e7410-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="e7410-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="e7410-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e7410-110">Component</span></span>|<span data-ttu-id="e7410-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="e7410-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="e7410-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e7410-112">Message Text</span></span>|<span data-ttu-id="e7410-113">A operação solicitada na instância de Banco de Dados Local não pode ser executada porque a instância especificada está em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="e7410-113">Requested operation on Local Database instance cannot be performed because specified instance is currently in use.</span></span> <span data-ttu-id="e7410-114">Interrompa a instância e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="e7410-114">Stop the instance and try again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e7410-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="e7410-115">Explanation</span></span>  
 <span data-ttu-id="e7410-116">A instância especificada está em execução.</span><span class="sxs-lookup"><span data-stu-id="e7410-116">The specified instance is running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7410-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e7410-117">User Action</span></span>  
 <span data-ttu-id="e7410-118">Interrompa a instância especificada do Runtime do Banco de Dados Local e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="e7410-118">Stop the specified Local Database Runtime instance and try again.</span></span>  
  
  
