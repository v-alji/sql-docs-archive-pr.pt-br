---
title: MSSQLSERVER_3437 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3437 (Database Engine error)
ms.assetid: b38216e2-b650-43bd-97af-061d54f60031
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ed8f2050f6f1b38bc5f3fcb7a9700b80e52f2763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581838"
---
# <a name="mssqlserver_3437"></a><span data-ttu-id="a28f6-102">MSSQLSERVER_3437</span><span class="sxs-lookup"><span data-stu-id="a28f6-102">MSSQLSERVER_3437</span></span>
    
## <a name="details"></a><span data-ttu-id="a28f6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a28f6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a28f6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a28f6-104">Product Name</span></span>|<span data-ttu-id="a28f6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a28f6-105">SQL Server</span></span>|  
|<span data-ttu-id="a28f6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a28f6-106">Event ID</span></span>|<span data-ttu-id="a28f6-107">3437</span><span class="sxs-lookup"><span data-stu-id="a28f6-107">3437</span></span>|  
|<span data-ttu-id="a28f6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a28f6-108">Event Source</span></span>|<span data-ttu-id="a28f6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a28f6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a28f6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a28f6-110">Component</span></span>|<span data-ttu-id="a28f6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a28f6-111">SQLEngine</span></span>|  
|<span data-ttu-id="a28f6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a28f6-112">Symbolic Name</span></span>|<span data-ttu-id="a28f6-113">NODTC</span><span class="sxs-lookup"><span data-stu-id="a28f6-113">NODTC</span></span>|  
|<span data-ttu-id="a28f6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a28f6-114">Message Text</span></span>|<span data-ttu-id="a28f6-115">Ocorreu um erro ao recuperar o banco de dados '%.\*ls.'</span><span class="sxs-lookup"><span data-stu-id="a28f6-115">An error occurred while recovering database '%.\*ls'.</span></span> <span data-ttu-id="a28f6-116">Não é possível se conectar ao MS DTC (Coordenador de Transações Distribuídas da Microsoft) para verificar o status de conclusão da transação %S_XID.</span><span class="sxs-lookup"><span data-stu-id="a28f6-116">Unable to connect to Microsoft Distributed Transaction Coordinator (MS DTC) to check the completion status of transaction %S_XID.</span></span> <span data-ttu-id="a28f6-117">Corrija o MS DTC e execute a recuperação novamente.</span><span class="sxs-lookup"><span data-stu-id="a28f6-117">Fix MS DTC, and run recovery again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a28f6-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="a28f6-118">Explanation</span></span>  
 <span data-ttu-id="a28f6-119">Uma ou mais transações distribuídas que estavam usando o MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)]) estavam incompletas quando o banco de dados foi desligado.</span><span class="sxs-lookup"><span data-stu-id="a28f6-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="a28f6-120">A recuperação desse banco de dados falhou porque o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar ao MS DTC para concluir ou reverter as transações.</span><span class="sxs-lookup"><span data-stu-id="a28f6-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot connect to MS DTC to complete or roll back the transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a28f6-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a28f6-121">User Action</span></span>  
 <span data-ttu-id="a28f6-122">Para recuperar esse banco de dados, você precisa primeiro resolver o problema no MS DTC.</span><span class="sxs-lookup"><span data-stu-id="a28f6-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="a28f6-123">Para investigar o problema com o MS DTC, examine os logs de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="a28f6-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="a28f6-124">Se você não conseguir resolver o problema com o MS DTC para recuperar o banco de dados, restaure um backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a28f6-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
