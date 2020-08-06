---
title: MSSQL_ENG014144 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d93f06a585bcc01c52438ff7b99bbd635532402
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568472"
---
# <a name="mssql_eng014144"></a><span data-ttu-id="a8689-102">MSSQL_ENG014144</span><span class="sxs-lookup"><span data-stu-id="a8689-102">MSSQL_ENG014144</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a8689-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="a8689-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8689-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a8689-104">Product Name</span></span>|<span data-ttu-id="a8689-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8689-105">SQL Server</span></span>|  
|<span data-ttu-id="a8689-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a8689-106">Event ID</span></span>|<span data-ttu-id="a8689-107">14144</span><span class="sxs-lookup"><span data-stu-id="a8689-107">14144</span></span>|  
|<span data-ttu-id="a8689-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a8689-108">Event Source</span></span>|<span data-ttu-id="a8689-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a8689-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a8689-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a8689-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a8689-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a8689-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a8689-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a8689-112">Message Text</span></span>|<span data-ttu-id="a8689-113">Não é possível descartar o Assinante '%s'.</span><span class="sxs-lookup"><span data-stu-id="a8689-113">Cannot drop Subscriber '%s'.</span></span> <span data-ttu-id="a8689-114">Existem assinaturas para ele no banco de dados de publicação '%s'.</span><span class="sxs-lookup"><span data-stu-id="a8689-114">There are subscriptions for it in the publication database '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8689-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="a8689-115">Explanation</span></span>  
 <span data-ttu-id="a8689-116">Uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configurada como Assinante não pode ser removida da função de Assinante enquanto houver assinaturas ativas configuradas para a instância.</span><span class="sxs-lookup"><span data-stu-id="a8689-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Subscriber cannot be removed from the role of Subscriber while there are active subscriptions configured for the instance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8689-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a8689-117">User Action</span></span>  
 <span data-ttu-id="a8689-118">Descarte todas as assinaturas associadas antes de tentar alterar o status Assinante da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a8689-118">Drop all associated subscriptions before attempting to change the Subscriber status of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance:</span></span>  
  
1.  <span data-ttu-id="a8689-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) no banco de dados de publicação no Publicador para encontrar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a8689-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in the publication database at the Publisher to find subscriptions.</span></span>  
  
2.  <span data-ttu-id="a8689-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) no banco de dados de publicação para remover assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a8689-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in the publication database to drop subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8689-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8689-121">See Also</span></span>  
 <span data-ttu-id="a8689-122">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a8689-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="a8689-123">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="a8689-123">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
