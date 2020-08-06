---
title: MSSQLSERVER_2516 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6be0809b3560d94bb883cf3a4acfa3d2c484b8b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679374"
---
# <a name="mssqlserver_2516"></a><span data-ttu-id="04289-102">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="04289-102">MSSQLSERVER_2516</span></span>
    
## <a name="details"></a><span data-ttu-id="04289-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="04289-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04289-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="04289-104">Product Name</span></span>|<span data-ttu-id="04289-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="04289-105">SQL Server</span></span>|  
|<span data-ttu-id="04289-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="04289-106">Event ID</span></span>|<span data-ttu-id="04289-107">2516</span><span class="sxs-lookup"><span data-stu-id="04289-107">2516</span></span>|  
|<span data-ttu-id="04289-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="04289-108">Event Source</span></span>|<span data-ttu-id="04289-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="04289-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="04289-110">Componente</span><span class="sxs-lookup"><span data-stu-id="04289-110">Component</span></span>|<span data-ttu-id="04289-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="04289-111">SQLEngine</span></span>|  
|<span data-ttu-id="04289-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="04289-112">Symbolic Name</span></span>|<span data-ttu-id="04289-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span><span class="sxs-lookup"><span data-stu-id="04289-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span></span>|  
|<span data-ttu-id="04289-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="04289-114">Message Text</span></span>|<span data-ttu-id="04289-115">A correção invalidou o bitmap diferencial do banco de dados NAME.</span><span class="sxs-lookup"><span data-stu-id="04289-115">Repair has invalidated the differential bitmap for database NAME.</span></span> <span data-ttu-id="04289-116">A cadeia de backup diferencial foi quebrada.</span><span class="sxs-lookup"><span data-stu-id="04289-116">The differential backup chain is broken.</span></span> <span data-ttu-id="04289-117">Execute um backup total de banco de dados antes de executar um backup diferencial.</span><span class="sxs-lookup"><span data-stu-id="04289-117">You must perform a full database backup before you can perform a differential backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="04289-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="04289-118">Explanation</span></span>  
 <span data-ttu-id="04289-119">Essa mensagem informativa é retornada quando o erro MSSQLEngine_2515 é corrigido.</span><span class="sxs-lookup"><span data-stu-id="04289-119">This informational message is returned when error MSSQLEngine_2515 is repaired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04289-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="04289-120">User Action</span></span>  
 <span data-ttu-id="04289-121">Execute um backup total do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04289-121">Perform a full database backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04289-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04289-122">See Also</span></span>  
 [<span data-ttu-id="04289-123">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="04289-123">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
  
