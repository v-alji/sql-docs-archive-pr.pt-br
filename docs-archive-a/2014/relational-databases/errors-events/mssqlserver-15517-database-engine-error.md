---
title: MSSQLSERVER_15517 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e66e211faf03e1457953d0292e711cde1798ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581893"
---
# <a name="mssqlserver_15517"></a><span data-ttu-id="09788-102">MSSQLSERVER_15517</span><span class="sxs-lookup"><span data-stu-id="09788-102">MSSQLSERVER_15517</span></span>
    
## <a name="details"></a><span data-ttu-id="09788-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="09788-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09788-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="09788-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="09788-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="09788-105">Event ID</span></span>|<span data-ttu-id="09788-106">15517</span><span class="sxs-lookup"><span data-stu-id="09788-106">15517</span></span>|  
|<span data-ttu-id="09788-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="09788-107">Event Source</span></span>|<span data-ttu-id="09788-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="09788-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="09788-109">Componente</span><span class="sxs-lookup"><span data-stu-id="09788-109">Component</span></span>|<span data-ttu-id="09788-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="09788-110">SQLEngine</span></span>|  
|<span data-ttu-id="09788-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="09788-111">Symbolic Name</span></span>|<span data-ttu-id="09788-112">SEC_CANNOTEXECUTEASUSER</span><span class="sxs-lookup"><span data-stu-id="09788-112">SEC_CANNOTEXECUTEASUSER</span></span>|  
|<span data-ttu-id="09788-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="09788-113">Message Text</span></span>|<span data-ttu-id="09788-114">Não é possível executar como banco de dados de entidade, pois a entidade “*principal*” não existe, esse tipo de entidade não pode ser representada ou você não tem permissão para isso.</span><span class="sxs-lookup"><span data-stu-id="09788-114">Cannot execute as the database principal because the principal "*principal*" does not exist, this type of principal cannot be impersonated, or you do not have permission.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="09788-115">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="09788-115">User Action</span></span>  
 <span data-ttu-id="09788-116">Use o nome de uma entidade existente ou obtenha a permissão IMPERSONATE nessa entidade.</span><span class="sxs-lookup"><span data-stu-id="09788-116">Use the name of an existing principal or get the IMPERSONATE permission on that principal.</span></span>  
  
 <span data-ttu-id="09788-117">15517 também pode ocorrer depois da execução de um anexo e a restauração de um banco de dados por alguém que não seja o proprietário original do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="09788-117">15517 can also occur after performing an attach and restore of a database by someone other than the original database owner.</span></span> <span data-ttu-id="09788-118">Para resolver esse erro, altere o db_owner para um logon no servidor, executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="09788-118">To resolve this error, change the db_owner to a login on your server, by running the following command:</span></span>  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a><span data-ttu-id="09788-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="09788-119">See Also</span></span>  
 [<span data-ttu-id="09788-120">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="09788-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
