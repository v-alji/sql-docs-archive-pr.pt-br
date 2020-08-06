---
title: MSSQLSERVER_1462 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1462 (Database Engine error)
ms.assetid: 680e9c1c-a9d6-4765-b601-956d0a83324c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 704b847bde2d7b4da9da91b4b24bfe2b9e2afa07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581895"
---
# <a name="mssqlserver_1462"></a><span data-ttu-id="46ff0-102">MSSQLSERVER_1462</span><span class="sxs-lookup"><span data-stu-id="46ff0-102">MSSQLSERVER_1462</span></span>
    
## <a name="details"></a><span data-ttu-id="46ff0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="46ff0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46ff0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="46ff0-104">Product Name</span></span>|<span data-ttu-id="46ff0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46ff0-105">SQL Server</span></span>|  
|<span data-ttu-id="46ff0-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="46ff0-106">Event ID</span></span>|<span data-ttu-id="46ff0-107">1462</span><span class="sxs-lookup"><span data-stu-id="46ff0-107">1462</span></span>|  
|<span data-ttu-id="46ff0-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="46ff0-108">Event Source</span></span>|<span data-ttu-id="46ff0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46ff0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46ff0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="46ff0-110">Component</span></span>|<span data-ttu-id="46ff0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46ff0-111">SQLEngine</span></span>|  
|<span data-ttu-id="46ff0-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="46ff0-112">Symbolic Name</span></span>|<span data-ttu-id="46ff0-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span><span class="sxs-lookup"><span data-stu-id="46ff0-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span></span>|  
|<span data-ttu-id="46ff0-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="46ff0-114">Message Text</span></span>|<span data-ttu-id="46ff0-115">O espelhamento de banco de dados foi desabilitado devido a uma falha na operação refazer.</span><span class="sxs-lookup"><span data-stu-id="46ff0-115">Database mirroring is disabled due to a failed redo operation.</span></span> <span data-ttu-id="46ff0-116">Não é possível retomar.</span><span class="sxs-lookup"><span data-stu-id="46ff0-116">Unable to resume.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46ff0-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="46ff0-117">Explanation</span></span>  
 <span data-ttu-id="46ff0-118">Houve falha no espelhamento de banco de dados ao refazer um registro de log no espelho.</span><span class="sxs-lookup"><span data-stu-id="46ff0-118">Database mirroring failed to redo a log record on the mirror.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="46ff0-119">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="46ff0-119">Possible Causes</span></span>  
 <span data-ttu-id="46ff0-120">A causa mais provável é que uma operação de adicionar arquivo tenha sido concluída no banco de dados principal, mas tenha apresentado falha no banco de dados espelho porque os nomes de arquivo ou as estruturas de diretório diferiam no servidor principal e no servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="46ff0-120">The most likely cause is that an add-file operation completed on the principal database but then failed on the mirror database because file names or directory structures differ on the principal server and mirror server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46ff0-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="46ff0-121">User Action</span></span>  
 <span data-ttu-id="46ff0-122">Procure a causa desse erro no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46ff0-122">Look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the cause of this error.</span></span> <span data-ttu-id="46ff0-123">Tente resolver a causa e retomar o espelhamento no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="46ff0-123">Try to resolve the cause and resume mirroring on the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ff0-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46ff0-124">See Also</span></span>  
 [<span data-ttu-id="46ff0-125">Solução de problemas de configuração de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="46ff0-125">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
