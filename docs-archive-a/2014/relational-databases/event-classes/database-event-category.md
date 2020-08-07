---
title: Categoria de Evento de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], Database event category
- Database event category [SQL Server]
- SQL Server event classes, Database event category
ms.assetid: b61af738-f144-4992-b0b2-d44cb7240991
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2860e1434611393c941a639280343f736073c709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575841"
---
# <a name="database-event-category"></a><span data-ttu-id="cbb27-102">Categoria de evento Database</span><span class="sxs-lookup"><span data-stu-id="cbb27-102">Database Event Category</span></span>
  <span data-ttu-id="cbb27-103">A categoria de evento **Database** contém classes de eventos para monitorar o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbb27-103">The **Database** event category contains event classes to monitor the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbb27-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="cbb27-104">In This Section</span></span>  
  
|<span data-ttu-id="cbb27-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="cbb27-105">Topic</span></span>|<span data-ttu-id="cbb27-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="cbb27-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cbb27-107">Classe de evento Data File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="cbb27-107">Data File Auto Grow Event Class</span></span>](data-file-auto-grow-event-class.md)|<span data-ttu-id="cbb27-108">Indica que o arquivo de dados cresceu automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cbb27-108">Indicates that the data file grew automatically.</span></span> <span data-ttu-id="cbb27-109">Este evento não será disparado se o arquivo de dados crescer explicitamente através de ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cbb27-109">This event is not triggered if the data file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="cbb27-110">Classe de evento Data File Auto Shrink</span><span class="sxs-lookup"><span data-stu-id="cbb27-110">Data File Auto Shrink Event Class</span></span>](data-file-auto-shrink-event-class.md)|<span data-ttu-id="cbb27-111">Indica que o arquivo de dados foi reduzido.</span><span class="sxs-lookup"><span data-stu-id="cbb27-111">Indicates that the data file has been shrunk.</span></span>|  
|[<span data-ttu-id="cbb27-112">Classe de evento Database Mirroring Connection</span><span class="sxs-lookup"><span data-stu-id="cbb27-112">Database Mirroring Connection Event Class</span></span>](database-mirroring-connection-event-class.md)|<span data-ttu-id="cbb27-113">Um evento gerado para informar o status de uma conexão de transporte para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cbb27-113">An event generated to report the status of a transport connection for database mirroring.</span></span>|  
|[<span data-ttu-id="cbb27-114">Classe de evento Database Mirroring State Change</span><span class="sxs-lookup"><span data-stu-id="cbb27-114">Database Mirroring State Change Event Class</span></span>](database-mirroring-state-change-event-class.md)|<span data-ttu-id="cbb27-115">Indica quando o estado de um banco de dados espelhado é alterado.</span><span class="sxs-lookup"><span data-stu-id="cbb27-115">Indicates when the state of a mirrored database changes.</span></span>|  
|[<span data-ttu-id="cbb27-116">Classe de evento Database Suspect Data Page</span><span class="sxs-lookup"><span data-stu-id="cbb27-116">Database Suspect Data Page Event Class</span></span>](database-suspect-data-page-event-class.md)|<span data-ttu-id="cbb27-117">Indica quando uma página é adicionada à tabela **suspect_pages** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="cbb27-117">Indicates when a page is added to the **suspect_pages** table in the **msdb** database.</span></span>|  
|[<span data-ttu-id="cbb27-118">Classe de evento Log File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="cbb27-118">Log File Auto Grow Event Class</span></span>](log-file-auto-grow-event-class.md)|<span data-ttu-id="cbb27-119">Indica que o arquivo de log cresceu automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cbb27-119">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="cbb27-120">Esse evento não será acionado se o arquivo de log crescer explicitamente por meio de ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cbb27-120">This event is not triggered if the log file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="cbb27-121">Classe de evento Log File Auto Shrink</span><span class="sxs-lookup"><span data-stu-id="cbb27-121">Log File Auto Shrink Event Class</span></span>](log-file-auto-shrink-event-class.md)|<span data-ttu-id="cbb27-122">Indica que o arquivo de log cresceu automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cbb27-122">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="cbb27-123">Este evento não será disparado se o arquivo de log for reduzido explicitamente através de ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cbb27-123">This event is not triggered if the log file shrinks explicitly through ALTER DATABASE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbb27-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cbb27-124">See Also</span></span>  
 [<span data-ttu-id="cbb27-125">Eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="cbb27-125">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
