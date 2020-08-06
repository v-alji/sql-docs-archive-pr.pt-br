---
title: MSSQLSERVER_18264 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3edfeb82601e254c02df87cc4a978b9ab5e653e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575148"
---
# <a name="mssqlserver_18264"></a><span data-ttu-id="7dcbc-102">MSSQLSERVER_18264</span><span class="sxs-lookup"><span data-stu-id="7dcbc-102">MSSQLSERVER_18264</span></span>
    
## <a name="details"></a><span data-ttu-id="7dcbc-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7dcbc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7dcbc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7dcbc-104">Product Name</span></span>|<span data-ttu-id="7dcbc-105">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7dcbc-105">Microsoft SQL Server</span></span>|  
|<span data-ttu-id="7dcbc-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7dcbc-106">Event ID</span></span>|<span data-ttu-id="7dcbc-107">18264</span><span class="sxs-lookup"><span data-stu-id="7dcbc-107">18264</span></span>|  
|<span data-ttu-id="7dcbc-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7dcbc-108">Event Source</span></span>|<span data-ttu-id="7dcbc-109">MSSQLENGINE</span><span class="sxs-lookup"><span data-stu-id="7dcbc-109">MSSQLENGINE</span></span>|  
|<span data-ttu-id="7dcbc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7dcbc-110">Component</span></span>|<span data-ttu-id="7dcbc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7dcbc-111">SQLEngine</span></span>|  
|<span data-ttu-id="7dcbc-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7dcbc-112">Symbolic Name</span></span>|<span data-ttu-id="7dcbc-113">STRMIO_DBDUMP</span><span class="sxs-lookup"><span data-stu-id="7dcbc-113">STRMIO_DBDUMP</span></span>|  
|<span data-ttu-id="7dcbc-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7dcbc-114">Message Text</span></span>|<span data-ttu-id="7dcbc-115">Backup do banco de dados efetuado.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-115">Database backed up.</span></span> <span data-ttu-id="7dcbc-116">Banco de dados: %s, data (hora) da criação: %s(%s), páginas despejadas: %d, primeiro LSN: %s, último LSN: %s, número de dispositivos de despejo: %d, informações sobre o dispositivo: (%s).</span><span class="sxs-lookup"><span data-stu-id="7dcbc-116">Database: %s, creation date(time): %s(%s), pages dumped: %d, first LSN: %s, last LSN: %s, number of dump devices: %d, device information: (%s).</span></span> <span data-ttu-id="7dcbc-117">Essa mensagem é apenas informativa.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-117">This is an informational message only.</span></span> <span data-ttu-id="7dcbc-118">Não é necessária nenhuma ação do usuário.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-118">No user action is required.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7dcbc-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="7dcbc-119">Explanation</span></span>  
 <span data-ttu-id="7dcbc-120">Por padrão, todo backup bem-sucedido adiciona essa mensagem informativa ao log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-120">By default, every successful backup adds this informational message to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the system event log.</span></span> <span data-ttu-id="7dcbc-121">Se você faz backup do log de transações com muita frequência, essas mensagens podem se acumular muito rapidamente, resultando em logs de erros imensos que podem dificultar a localização de outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-121">If you very frequently back up the transaction log, these messages can accumulate quickly, creating very large error logs that can make finding other messages difficult.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7dcbc-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7dcbc-122">User Action</span></span>  
 <span data-ttu-id="7dcbc-123">Você pode suprimir essas entradas de log usando o sinalizador de rastreamento [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**3226**.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-123">You can suppress these log entries by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trace flag **3226**.</span></span> <span data-ttu-id="7dcbc-124">Habilitar o sinalizador de rastreamento é útil quando você executa backups de logs com frequência e se nenhum dos seus scripts depende dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-124">Enabling this trace flag is useful if you are running frequent log backups and if none of your scripts depend on those entries.</span></span>  
  
 <span data-ttu-id="7dcbc-125">Para obter informações sobre como usar sinalizadores de rastreamento, consulte os Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-125">For information about using trace flags, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dcbc-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7dcbc-126">See Also</span></span>  
 [<span data-ttu-id="7dcbc-127">Sinalizadores de rastreamento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7dcbc-127">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
