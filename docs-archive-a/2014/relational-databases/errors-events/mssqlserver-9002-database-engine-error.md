---
title: MSSQLSERVER_9002 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40fe70db8849d09f9296a06cbeed65a9c71e5a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575853"
---
# <a name="mssqlserver_9002"></a><span data-ttu-id="2ba4d-102">MSSQLSERVER_9002</span><span class="sxs-lookup"><span data-stu-id="2ba4d-102">MSSQLSERVER_9002</span></span>
    
## <a name="details"></a><span data-ttu-id="2ba4d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2ba4d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ba4d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2ba4d-104">Product Name</span></span>|<span data-ttu-id="2ba4d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ba4d-105">SQL Server</span></span>|  
|<span data-ttu-id="2ba4d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2ba4d-106">Event ID</span></span>|<span data-ttu-id="2ba4d-107">9002</span><span class="sxs-lookup"><span data-stu-id="2ba4d-107">9002</span></span>|  
|<span data-ttu-id="2ba4d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2ba4d-108">Event Source</span></span>|<span data-ttu-id="2ba4d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2ba4d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2ba4d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2ba4d-110">Component</span></span>|<span data-ttu-id="2ba4d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2ba4d-111">SQLEngine</span></span>|  
|<span data-ttu-id="2ba4d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2ba4d-112">Symbolic Name</span></span>|<span data-ttu-id="2ba4d-113">LOG_IS_FULL</span><span class="sxs-lookup"><span data-stu-id="2ba4d-113">LOG_IS_FULL</span></span>|  
|<span data-ttu-id="2ba4d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2ba4d-114">Message Text</span></span>|<span data-ttu-id="2ba4d-115">O log de transações do banco de dados '%.\*ls' está cheio.</span><span class="sxs-lookup"><span data-stu-id="2ba4d-115">The transaction log for database '%.\*ls' is full.</span></span> <span data-ttu-id="2ba4d-116">Para saber o motivo pelo qual o espaço no log não pode ser usado novamente, consulte a coluna log_reuse_wait_desc em sys.databases.</span><span class="sxs-lookup"><span data-stu-id="2ba4d-116">To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ba4d-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="2ba4d-117">Explanation</span></span>  
 <span data-ttu-id="2ba4d-118">O log de banco de dados não tem espaço.</span><span class="sxs-lookup"><span data-stu-id="2ba4d-118">The database log is out of space.</span></span> <span data-ttu-id="2ba4d-119">A coluna **log_reuse_wait_desc** em **sys.databases** descreve o motivo pelo qual o espaço no log não pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="2ba4d-119">The **log_reuse_wait_desc** column in **sys.databases** describes why space in the log cannot be reused.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ba4d-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2ba4d-120">User Action</span></span>  
 <span data-ttu-id="2ba4d-121">Use **sys.databases** para determinar por que o log está cheio e, em seguida, corrija a condição.</span><span class="sxs-lookup"><span data-stu-id="2ba4d-121">Use **sys.databases** to determine why the log is full and then correct the condition.</span></span> <span data-ttu-id="2ba4d-122">Para obter mais informações, consulte "Solucionando problemas em um log de transação completa (erro 9002)" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2ba4d-122">For more information, see "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba4d-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ba4d-123">See Also</span></span>  
 <span data-ttu-id="2ba4d-124">[Solução de problemas de um log de transações cheio &#40;Erro 9002 do SQL Server &#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span><span class="sxs-lookup"><span data-stu-id="2ba4d-124">[Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span></span>  
 [<span data-ttu-id="2ba4d-125">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2ba4d-125">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
