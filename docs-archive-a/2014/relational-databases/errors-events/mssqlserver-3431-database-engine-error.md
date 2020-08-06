---
title: MSSQLSERVER_3431 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b62047a25d71ca05dc3ab03651e5672353bc0a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581843"
---
# <a name="mssqlserver_3431"></a><span data-ttu-id="9f9c7-102">MSSQLSERVER_3431</span><span class="sxs-lookup"><span data-stu-id="9f9c7-102">MSSQLSERVER_3431</span></span>
    
## <a name="details"></a><span data-ttu-id="9f9c7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9f9c7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f9c7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9f9c7-104">Product Name</span></span>|<span data-ttu-id="9f9c7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f9c7-105">SQL Server</span></span>|  
|<span data-ttu-id="9f9c7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9f9c7-106">Event ID</span></span>|<span data-ttu-id="9f9c7-107">3431</span><span class="sxs-lookup"><span data-stu-id="9f9c7-107">3431</span></span>|  
|<span data-ttu-id="9f9c7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9f9c7-108">Event Source</span></span>|<span data-ttu-id="9f9c7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9f9c7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9f9c7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9f9c7-110">Component</span></span>|<span data-ttu-id="9f9c7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9f9c7-111">SQLEngine</span></span>|  
|<span data-ttu-id="9f9c7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9f9c7-112">Symbolic Name</span></span>|<span data-ttu-id="9f9c7-113">UNRESOLVED_XACT</span><span class="sxs-lookup"><span data-stu-id="9f9c7-113">UNRESOLVED_XACT</span></span>|  
|<span data-ttu-id="9f9c7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9f9c7-114">Message Text</span></span>|<span data-ttu-id="9f9c7-115">Não foi possível recuperar o banco de dados '%.\*ls' (ID do banco de dados %d) devido a resultados de transação não resolvidos.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-115">Could not recover database '%.\*ls' (database ID %d) because of unresolved transaction outcomes.</span></span> <span data-ttu-id="9f9c7-116">As transações do MS DTC (Coordenador de Transações Distribuídas da Microsoft) foram preparadas, mas o MS DTC não pôde determinar a resolução.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-116">Microsoft Distributed Transaction Coordinator (MS DTC) transactions were prepared, but MS DTC was unable to determine the resolution.</span></span> <span data-ttu-id="9f9c7-117">Para resolver, corrija o MS DTC, repare o banco de dados ou restaure-o usando um backup completo.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-117">To resolve, either fix MS DTC, restore from a full backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f9c7-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="9f9c7-118">Explanation</span></span>  
 <span data-ttu-id="9f9c7-119">Uma ou mais transações distribuídas que estavam usando o MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)]) estavam incompletas quando o banco de dados foi desligado.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="9f9c7-120">A recuperação desse banco de dados falhou porque o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode concluir nem reverter as transações sem mais informações do MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot complete the transactions or roll back the transactions without more information from MS DTC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f9c7-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9f9c7-121">User Action</span></span>  
 <span data-ttu-id="9f9c7-122">Para recuperar esse banco de dados, você precisa primeiro resolver o problema no MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="9f9c7-123">Para investigar o problema com o MS DTC, examine os logs de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="9f9c7-124">Se você não conseguir resolver o problema com o MS DTC para recuperar o banco de dados, restaure um backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f9c7-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
