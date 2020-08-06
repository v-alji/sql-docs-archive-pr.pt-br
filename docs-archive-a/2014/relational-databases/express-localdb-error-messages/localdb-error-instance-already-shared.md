---
title: LOCALDB_ERROR_INSTANCE_ALREADY_SHARED | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 35b4d6fa-ebb9-49d3-aaab-d4e37b6f3760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 300f9753b721bc3e0a821a6b77929a9bec09312b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569484"
---
# <a name="localdb_error_instance_already_shared"></a><span data-ttu-id="ea392-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="ea392-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>
    
## <a name="details"></a><span data-ttu-id="ea392-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ea392-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea392-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ea392-104">Product Name</span></span>|<span data-ttu-id="ea392-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea392-105">SQL Server</span></span>|  
|<span data-ttu-id="ea392-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ea392-106">Event ID</span></span>|<span data-ttu-id="ea392-107">284</span><span class="sxs-lookup"><span data-stu-id="ea392-107">284</span></span>|  
|<span data-ttu-id="ea392-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ea392-108">Event Source</span></span>|<span data-ttu-id="ea392-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="ea392-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="ea392-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ea392-110">Component</span></span>|<span data-ttu-id="ea392-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="ea392-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="ea392-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ea392-112">Message Text</span></span>|<span data-ttu-id="ea392-113">A instância especificada do Banco de Dados Local já está compartilhada.</span><span class="sxs-lookup"><span data-stu-id="ea392-113">The specified Local Database Instance is already shared.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ea392-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="ea392-114">Explanation</span></span>  
 <span data-ttu-id="ea392-115">A instância especificada do Banco de Dados Local já está compartilhada com um nome compartilhado diferente.</span><span class="sxs-lookup"><span data-stu-id="ea392-115">The specified Local Database Instance is already shared with a different shared name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea392-116">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ea392-116">User Action</span></span>  
 <span data-ttu-id="ea392-117">Descompartilhe a instância compartilhada antes de compartilhá-la novamente com um nome compartilhado diferente.</span><span class="sxs-lookup"><span data-stu-id="ea392-117">Unshare the shared instance before sharing it again with a different shared name.</span></span>  
  
  
