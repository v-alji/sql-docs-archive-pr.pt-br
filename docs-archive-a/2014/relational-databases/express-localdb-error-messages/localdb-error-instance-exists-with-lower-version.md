---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa6db2af138bb2aeefb1a922e55db56c4ea821f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686290"
---
# <a name="localdb_error_instance_exists_with_lower_version"></a><span data-ttu-id="b2fb4-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="b2fb4-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>
    
## <a name="details"></a><span data-ttu-id="b2fb4-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b2fb4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2fb4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b2fb4-104">Product Name</span></span>|<span data-ttu-id="b2fb4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2fb4-105">SQL Server</span></span>|  
|<span data-ttu-id="b2fb4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b2fb4-106">Event ID</span></span>|<span data-ttu-id="b2fb4-107">258</span><span class="sxs-lookup"><span data-stu-id="b2fb4-107">258</span></span>|  
|<span data-ttu-id="b2fb4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b2fb4-108">Event Source</span></span>|<span data-ttu-id="b2fb4-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="b2fb4-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="b2fb4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b2fb4-110">Component</span></span>|<span data-ttu-id="b2fb4-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="b2fb4-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="b2fb4-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b2fb4-112">Message Text</span></span>|<span data-ttu-id="b2fb4-113">Não é possível criar a instância do Banco de Dados Local com a versão especificada.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-113">Unable to create the Local Database instance with specified version.</span></span> <span data-ttu-id="b2fb4-114">Já existe uma instância com o mesmo nome, mas ela pertence a uma versão inferior à especificada.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-114">An instance with the same name already exists, but it has lower version than the specified version.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2fb4-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="b2fb4-115">Explanation</span></span>  
 <span data-ttu-id="b2fb4-116">A instância especificada já existe, mas sua versão é inferior à solicitada.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-116">The specified instance already exists but its version is lower than requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2fb4-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b2fb4-117">User Action</span></span>  
 <span data-ttu-id="b2fb4-118">Exclua a instância existente e repita a operação.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-118">Delete the existing instance and retry the operation.</span></span>  
  
  
