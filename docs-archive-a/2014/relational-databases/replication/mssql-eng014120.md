---
title: MSSQL_ENG014120 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014120 error
ms.assetid: 6b169a3b-30da-4981-b998-b52d61811572
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7f3484d9344a203ca8c44fee6b79605163ea069
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568476"
---
# <a name="mssql_eng014120"></a><span data-ttu-id="ab43a-102">MSSQL_ENG014120</span><span class="sxs-lookup"><span data-stu-id="ab43a-102">MSSQL_ENG014120</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ab43a-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="ab43a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab43a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ab43a-104">Product Name</span></span>|<span data-ttu-id="ab43a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab43a-105">SQL Server</span></span>|  
|<span data-ttu-id="ab43a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ab43a-106">Event ID</span></span>|<span data-ttu-id="ab43a-107">14120</span><span class="sxs-lookup"><span data-stu-id="ab43a-107">14120</span></span>|  
|<span data-ttu-id="ab43a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ab43a-108">Event Source</span></span>|<span data-ttu-id="ab43a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ab43a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ab43a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ab43a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ab43a-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ab43a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ab43a-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ab43a-112">Message Text</span></span>|<span data-ttu-id="ab43a-113">Não foi possível descartar o banco de dados de distribuição '%s'.</span><span class="sxs-lookup"><span data-stu-id="ab43a-113">Could not drop the distribution database '%s'.</span></span> <span data-ttu-id="ab43a-114">O banco de dados do distribuidor está associado a um Publicador.</span><span class="sxs-lookup"><span data-stu-id="ab43a-114">This distributor database is associated with a Publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab43a-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="ab43a-115">Explanation</span></span>  
 <span data-ttu-id="ab43a-116">O banco de dados de distribuição armazena metadados e dados de histórico para todos os tipos de replicação e transações para replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="ab43a-116">The distribution database stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="ab43a-117">Esse erro ocorre ao tentar descartar um banco de dados de distribuição associado a um ou mais Publicadores.</span><span class="sxs-lookup"><span data-stu-id="ab43a-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab43a-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ab43a-118">User Action</span></span>  
 <span data-ttu-id="ab43a-119">Para descartar um banco de dados de distribuição, é necessário primeiro descartar a associação entre o Distribuidor e o Publicador.</span><span class="sxs-lookup"><span data-stu-id="ab43a-119">To drop a distribution database you must first drop the association between the Distributor and the Publisher.</span></span> <span data-ttu-id="ab43a-120">Para obter mais informações, consulte [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab43a-120">For more information, see [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab43a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab43a-121">See Also</span></span>  
 <span data-ttu-id="ab43a-122">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ab43a-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="ab43a-123">Configurar Distribuição</span><span class="sxs-lookup"><span data-stu-id="ab43a-123">Configure Distribution</span></span>](configure-distribution.md)  
  
  
