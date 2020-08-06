---
title: Categoria de evento TSQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, TSQL event category
- TSQL event category [SQL Server]
- event classes [SQL Server], TSQL event category
ms.assetid: 215f8747-64b5-4bf3-9845-d476b10cda3a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 763d5f31fd3562f54b274a74324ed4715b623a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678757"
---
# <a name="tsql-event-category"></a><span data-ttu-id="4c0a6-102">Categoria de evento TSQL</span><span class="sxs-lookup"><span data-stu-id="4c0a6-102">TSQL Event Category</span></span>
  <span data-ttu-id="4c0a6-103">A categoria de evento **TSQL** contém eventos gerais TSQL.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-103">The **TSQL** event category contains general TSQL events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c0a6-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4c0a6-104">In This Section</span></span>  
  
|<span data-ttu-id="4c0a6-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="4c0a6-105">Topic</span></span>|<span data-ttu-id="4c0a6-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4c0a6-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4c0a6-107">Classe de evento Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="4c0a6-107">Exec Prepared SQL Event Class</span></span>](exec-prepared-sql-event-class.md)|<span data-ttu-id="4c0a6-108">Indica que SqlClient, ODBC, OLE DB ou DB-Library executou uma ou mais instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] preparadas.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-108">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has executed a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="4c0a6-109">Classe de evento Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="4c0a6-109">Prepare SQL Event Class</span></span>](prepare-sql-event-class.md)|<span data-ttu-id="4c0a6-110">Indica que SqlClient, ODBC, OLE DB ou DB-Library preparou uma ou mais instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] para uso.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-110">Indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>|  
|[<span data-ttu-id="4c0a6-111">Classe de evento SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="4c0a6-111">SQL:BatchCompleted Event Class</span></span>](sql-batchcompleted-event-class.md)|<span data-ttu-id="4c0a6-112">Indica que o lote [!INCLUDE[tsql](../../includes/tsql-md.md)] foi concluído.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-112">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch has completed.</span></span>|  
|[<span data-ttu-id="4c0a6-113">Classe de evento SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="4c0a6-113">SQL:BatchStarting Event Class</span></span>](sql-batchstarting-event-class.md)|<span data-ttu-id="4c0a6-114">Indica que o lote [!INCLUDE[tsql](../../includes/tsql-md.md)] está iniciando.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-114">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch is starting.</span></span>|  
|[<span data-ttu-id="4c0a6-115">Classe de evento SQL:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="4c0a6-115">SQL:StmtCompleted Event Class</span></span>](sql-stmtcompleted-event-class.md)|<span data-ttu-id="4c0a6-116">Indica que uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] foi concluída.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-116">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement has completed.</span></span>|  
|[<span data-ttu-id="4c0a6-117">Classe de evento SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="4c0a6-117">SQL:StmtRecompile Event Class</span></span>](sql-stmtrecompile-event-class.md)|<span data-ttu-id="4c0a6-118">Indica recompilações em nível de instrução causadas por todos os tipos de lotes: procedimentos armazenados, gatilhos, lotes ad hoc e consultas.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-118">Indicates statement-level recompilations caused by all types of batches: stored procedures, triggers, ad hoc batches, and queries.</span></span>|  
|[<span data-ttu-id="4c0a6-119">Classe de evento SQL:StmtStarting</span><span class="sxs-lookup"><span data-stu-id="4c0a6-119">SQL:StmtStarting Event Class</span></span>](sql-stmtstarting-event-class.md)|<span data-ttu-id="4c0a6-120">Indica que uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] está iniciando.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-120">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is starting.</span></span>|  
|[<span data-ttu-id="4c0a6-121">Classe de evento Unprepare SQL</span><span class="sxs-lookup"><span data-stu-id="4c0a6-121">Unprepare SQL Event Class</span></span>](unprepare-sql-event-class.md)|<span data-ttu-id="4c0a6-122">Indica que SqlClient, ODBC, OLE DB ou DB-Library excluiu uma ou mais instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] preparadas.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-122">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has deleted a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="4c0a6-123">Classe de evento XQuery Static Type</span><span class="sxs-lookup"><span data-stu-id="4c0a6-123">XQuery Static Type Event Class</span></span>](xquery-static-type-event-class.md)|<span data-ttu-id="4c0a6-124">Ocorre quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa uma expressão XQuery.</span><span class="sxs-lookup"><span data-stu-id="4c0a6-124">Occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an XQuery expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c0a6-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c0a6-125">See Also</span></span>  
 [<span data-ttu-id="4c0a6-126">Referência do Transact-SQL &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="4c0a6-126">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
