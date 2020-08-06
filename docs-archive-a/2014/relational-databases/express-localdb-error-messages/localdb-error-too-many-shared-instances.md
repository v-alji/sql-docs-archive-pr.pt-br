---
title: LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c1595263-6264-4a43-9535-5eb76ece3a57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0896f3e70e6c65a1fcd0de4169249fb622e6b5f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569478"
---
# <a name="localdb_error_too_many_shared_instances"></a><span data-ttu-id="a3619-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span><span class="sxs-lookup"><span data-stu-id="a3619-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span></span>
    
## <a name="details"></a><span data-ttu-id="a3619-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a3619-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3619-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a3619-104">Product Name</span></span>|<span data-ttu-id="a3619-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3619-105">SQL Server</span></span>|  
|<span data-ttu-id="a3619-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a3619-106">Event ID</span></span>|<span data-ttu-id="a3619-107">287</span><span class="sxs-lookup"><span data-stu-id="a3619-107">287</span></span>|  
|<span data-ttu-id="a3619-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a3619-108">Event Source</span></span>|<span data-ttu-id="a3619-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="a3619-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="a3619-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3619-110">Component</span></span>|<span data-ttu-id="a3619-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="a3619-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="a3619-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a3619-112">Message Text</span></span>|<span data-ttu-id="a3619-113">Há muitas instâncias compartilhadas e não podemos gerar um Nome da Instância de Usuário exclusivo.</span><span class="sxs-lookup"><span data-stu-id="a3619-113">There are too many shared instance and we cannot generate unique User Instance Name.</span></span> <span data-ttu-id="a3619-114">Descompartilhe algumas das instâncias compartilhadas existentes.</span><span class="sxs-lookup"><span data-stu-id="a3619-114">Unshare some of the existing shared instances.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3619-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="a3619-115">Explanation</span></span>  
 <span data-ttu-id="a3619-116">Há muitas instâncias compartilhadas e não podemos gerar um Nome da Instância de Usuário exclusivo.</span><span class="sxs-lookup"><span data-stu-id="a3619-116">There are too many shared instance and we cannot generate unique User Instance Name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3619-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a3619-117">User Action</span></span>  
 <span data-ttu-id="a3619-118">Descompartilhe uma ou mais das instâncias compartilhadas do Runtime do Banco de Dados Local e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="a3619-118">Unshare one or more of the shared Local Database Runtime instances and try again.</span></span>  
  
  
