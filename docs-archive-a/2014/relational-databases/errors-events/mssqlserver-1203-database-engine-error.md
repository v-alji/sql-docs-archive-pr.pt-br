---
title: MSSQLSERVER_1203 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1203 (Database Engine error)
ms.assetid: 33a35f00-98c8-46c6-b432-544b326b6117
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cea816a60ccd1b90d849194766edebd2d64d0b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576442"
---
# <a name="mssqlserver_1203"></a><span data-ttu-id="7e3f8-102">MSSQLSERVER_1203</span><span class="sxs-lookup"><span data-stu-id="7e3f8-102">MSSQLSERVER_1203</span></span>
    
## <a name="details"></a><span data-ttu-id="7e3f8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7e3f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e3f8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7e3f8-104">Product Name</span></span>|<span data-ttu-id="7e3f8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e3f8-105">SQL Server</span></span>|  
|<span data-ttu-id="7e3f8-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7e3f8-106">Event ID</span></span>|<span data-ttu-id="7e3f8-107">1203</span><span class="sxs-lookup"><span data-stu-id="7e3f8-107">1203</span></span>|  
|<span data-ttu-id="7e3f8-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7e3f8-108">Event Source</span></span>|<span data-ttu-id="7e3f8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7e3f8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7e3f8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7e3f8-110">Component</span></span>|<span data-ttu-id="7e3f8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7e3f8-111">SQLEngine</span></span>|  
|<span data-ttu-id="7e3f8-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7e3f8-112">Symbolic Name</span></span>|<span data-ttu-id="7e3f8-113">LK_NOT</span><span class="sxs-lookup"><span data-stu-id="7e3f8-113">LK_NOT</span></span>|  
|<span data-ttu-id="7e3f8-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7e3f8-114">Message Text</span></span>|<span data-ttu-id="7e3f8-115">A ID de processo %d tentou desbloquear um recurso que não tem: %.\*ls.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-115">Process ID %d attempted to unlock a resource it does not own: %.\*ls.</span></span> <span data-ttu-id="7e3f8-116">Tente a transação novamente, porque esse erro pode ter sido causado por uma condição de tempo.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-116">Retry the transaction, because this error may be caused by a timing condition.</span></span> <span data-ttu-id="7e3f8-117">Se o problema persistir, contate o administrador de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-117">If the problem persists, contact the database administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e3f8-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="7e3f8-118">Explanation</span></span>  
 <span data-ttu-id="7e3f8-119">Esse erro acontece quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está envolvido em alguma atividade diferente da limpeza usual de pós-processamento e acha que uma determinada página que está tentando desbloquear já está desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-119">This error occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is engaged in some activity other than ordinary post-processing cleanup and it finds that a particular page that it is trying to unlock is already unlocked.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="7e3f8-120">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="7e3f8-120">Possible Causes</span></span>  
 <span data-ttu-id="7e3f8-121">A causa subjacente deste erro pode estar relacionada a problemas estruturais dentro do banco de dados afetado.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-121">The underlying cause of this error may be related to structural problems within the affected database.</span></span> <span data-ttu-id="7e3f8-122">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerencia a aquisição e a liberação de páginas para manter o controle de simultaneidade no ambiente multiusuário.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-122">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages the acquisition and release of pages to maintain concurrency control in the multiuser environment.</span></span> <span data-ttu-id="7e3f8-123">Esse mecanismo é mantido pelo uso de várias estruturas de bloqueio interno que identificam a página e o tipo de bloqueio presente.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-123">This mechanism is maintained by using various internal lock structures that identify the page and the type of lock present.</span></span> <span data-ttu-id="7e3f8-124">Os bloqueios são adquiridos para processar páginas afetadas e são liberados quando o processamento é finalizado.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-124">Locks are acquired for processing of affected pages and released when the processing is finished.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e3f8-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7e3f8-125">User Action</span></span>  
 <span data-ttu-id="7e3f8-126">Execute o DBCC CHECKDB no banco de dados em que o objeto se encontra.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-126">Execute DBCC CHECKDB against the database in which the object belongs.</span></span> <span data-ttu-id="7e3f8-127">Se o DBCC CHECKDB não informar nenhum erro, você deverá tentar restabelecer a conexão e executar o comando.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-127">If DBCC CHECKDB reports no errors, try to reestablish the connection and execute the command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7e3f8-128">Se você estiver executando o DBCC CHECKDB com uma das cláusulas REPAIR e isso não corrigir o problema de índice, ou se você não estiver seguro de qual efeito o DBCC CHECKDB com uma cláusula de REPAIR terá sobre seus dados, entre em contato com seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="7e3f8-128">If you are executing DBCC CHECKDB with one of the REPAIR clauses does not correct the index problem, or if you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider.</span></span>  
  
  
