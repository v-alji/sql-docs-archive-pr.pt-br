---
title: MSSQL_ENG021385 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679864"
---
# <a name="mssql_eng021385"></a><span data-ttu-id="100ba-102">MSSQL_ENG021385</span><span class="sxs-lookup"><span data-stu-id="100ba-102">MSSQL_ENG021385</span></span>
    
## <a name="message-details"></a><span data-ttu-id="100ba-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="100ba-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="100ba-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="100ba-104">Product Name</span></span>|<span data-ttu-id="100ba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="100ba-105">SQL Server</span></span>|  
|<span data-ttu-id="100ba-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="100ba-106">Event ID</span></span>|<span data-ttu-id="100ba-107">21385</span><span class="sxs-lookup"><span data-stu-id="100ba-107">21385</span></span>|  
|<span data-ttu-id="100ba-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="100ba-108">Event Source</span></span>|<span data-ttu-id="100ba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="100ba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="100ba-110">Componente</span><span class="sxs-lookup"><span data-stu-id="100ba-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="100ba-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="100ba-111">Symbolic Name</span></span>||  
|<span data-ttu-id="100ba-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="100ba-112">Message Text</span></span>|<span data-ttu-id="100ba-113">Falha no instantâneo ao processar a publicação '%s'.</span><span class="sxs-lookup"><span data-stu-id="100ba-113">Snapshot failed to process publication '%s'.</span></span> <span data-ttu-id="100ba-114">Possivelmente devido à atividade de alteração de esquema ativa ou à adição de novos artigos.</span><span class="sxs-lookup"><span data-stu-id="100ba-114">Possibly due to active schema change activity or new articles being added.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="100ba-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="100ba-115">Explanation</span></span>  
 <span data-ttu-id="100ba-116">Esse erro é gerado se o Snapshot Agent é executado quando há alterações em andamento no banco de dados de publicação, incluindo adição ou descarte de artigos e alterações de esquema nos objetos publicados.</span><span class="sxs-lookup"><span data-stu-id="100ba-116">This error is raised if the Snapshot Agent starts running when there are ongoing changes to the publication database, including adding or dropping articles and performing schema changes on published objects.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="100ba-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="100ba-117">User Action</span></span>  
 <span data-ttu-id="100ba-118">Reinicie o Snapshot Agent após a conclusão das alterações no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="100ba-118">Restart the Snapshot Agent after changes to the publication database are complete.</span></span> <span data-ttu-id="100ba-119">Para obter mais informações, consulte [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Conceitos dos executáveis do agente de replicação](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="100ba-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="100ba-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="100ba-120">See Also</span></span>  
 [<span data-ttu-id="100ba-121">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="100ba-121">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
