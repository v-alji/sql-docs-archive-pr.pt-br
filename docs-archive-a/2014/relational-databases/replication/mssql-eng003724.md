---
title: MSSQL_ENG003724 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dbfb68575c5ffa73276b3bbe1643381c3f0cc412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685545"
---
# <a name="mssql_eng003724"></a><span data-ttu-id="17f51-102">MSSQL_ENG003724</span><span class="sxs-lookup"><span data-stu-id="17f51-102">MSSQL_ENG003724</span></span>
    
## <a name="message-details"></a><span data-ttu-id="17f51-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="17f51-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17f51-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="17f51-104">Product Name</span></span>|<span data-ttu-id="17f51-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="17f51-105">SQL Server</span></span>|  
|<span data-ttu-id="17f51-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="17f51-106">Event ID</span></span>|<span data-ttu-id="17f51-107">3724</span><span class="sxs-lookup"><span data-stu-id="17f51-107">3724</span></span>|  
|<span data-ttu-id="17f51-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="17f51-108">Event Source</span></span>|<span data-ttu-id="17f51-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="17f51-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="17f51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="17f51-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="17f51-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="17f51-111">Symbolic Name</span></span>||  
|<span data-ttu-id="17f51-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="17f51-112">Message Text</span></span>|<span data-ttu-id="17f51-113">Não é possível %S_MSG o %S_MSG '%.\*ls' porque está sendo usado para replicação.</span><span class="sxs-lookup"><span data-stu-id="17f51-113">Cannot %S_MSG the %S_MSG '%.\*ls' because it is being used for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="17f51-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="17f51-114">Explanation</span></span>  
 <span data-ttu-id="17f51-115">Quando os objetos em um banco de dados são replicados, são marcados como replicados na tabela do sistema **sysarticles** (para publicações de instantâneo e transacionais) ou **sysmergearticles** (para publicações de mesclagem).</span><span class="sxs-lookup"><span data-stu-id="17f51-115">When objects in a database are replicated, they are marked as replicated in the system table **sysarticles** (for snapshot and transactional publications) or **sysmergearticles** (for merge publications).</span></span> <span data-ttu-id="17f51-116">Se tentar descartar um objeto replicado, ocorrerá esse erro.</span><span class="sxs-lookup"><span data-stu-id="17f51-116">If you attempt drop a replicated object, this error is raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17f51-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="17f51-117">User Action</span></span>  
 <span data-ttu-id="17f51-118">Certifique-se de que o objeto de banco de dados não está replicado antes de tentar descartá-lo.</span><span class="sxs-lookup"><span data-stu-id="17f51-118">Ensure the database object is not replicated before attempting to drop it.</span></span> <span data-ttu-id="17f51-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="17f51-119">For example:</span></span>  
  
-   <span data-ttu-id="17f51-120">Se o erro ocorrer no banco de dados de publicação, descarte o artigo da publicação antes de descartar o objeto.</span><span class="sxs-lookup"><span data-stu-id="17f51-120">If the error occurs in the publication database, drop the article from the publication before dropping the object.</span></span> <span data-ttu-id="17f51-121">Para obter mais informações, consulte [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md) (Adicionar e remover artigos para/de publicações existentes).</span><span class="sxs-lookup"><span data-stu-id="17f51-121">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
-   <span data-ttu-id="17f51-122">Se o erro ocorrer no banco de dados de assinatura, descarte a assinatura antes de descartar o objeto.</span><span class="sxs-lookup"><span data-stu-id="17f51-122">If the error occurs in the subscription database, drop the subscription before dropping the object.</span></span> <span data-ttu-id="17f51-123">Para obter mais informações, consulte [Subscribe to Publications](subscribe-to-publications.md) (Assinar publicações).</span><span class="sxs-lookup"><span data-stu-id="17f51-123">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="17f51-124">Para assinaturas de publicações transacionais, é possível descartar a assinatura de um artigo individual em vez de toda a publicação.</span><span class="sxs-lookup"><span data-stu-id="17f51-124">For subscriptions to transactional publications, it is possible to drop the subscription to an individual article rather than the entire publication.</span></span> <span data-ttu-id="17f51-125">Para obter mais informações, consulte [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17f51-125">For more information, see [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span>  
  
 <span data-ttu-id="17f51-126">Se esse erro ocorrer em um banco de dados não replicado, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para garantir que os objetos nos bancos de dados não são marcados como replicados.</span><span class="sxs-lookup"><span data-stu-id="17f51-126">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f51-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17f51-127">See Also</span></span>  
 [<span data-ttu-id="17f51-128">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="17f51-128">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
