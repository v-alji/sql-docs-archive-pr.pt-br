---
title: MSSQLSERVER_905 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 905 (Database Engine error)
ms.assetid: c828bb2e-e554-4f81-b76c-2b3740d2b944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7dd3c8c5a287e2d123e2a9d1430ecd49b27f29f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573045"
---
# <a name="mssqlserver_905"></a><span data-ttu-id="f0b10-102">MSSQLSERVER_905</span><span class="sxs-lookup"><span data-stu-id="f0b10-102">MSSQLSERVER_905</span></span>
    
## <a name="details"></a><span data-ttu-id="f0b10-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f0b10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0b10-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f0b10-104">Product Name</span></span>|<span data-ttu-id="f0b10-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0b10-105">SQL Server</span></span>|  
|<span data-ttu-id="f0b10-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f0b10-106">Event ID</span></span>|<span data-ttu-id="f0b10-107">905</span><span class="sxs-lookup"><span data-stu-id="f0b10-107">905</span></span>|  
|<span data-ttu-id="f0b10-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f0b10-108">Event Source</span></span>|<span data-ttu-id="f0b10-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f0b10-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f0b10-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f0b10-110">Component</span></span>|<span data-ttu-id="f0b10-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f0b10-111">SQLEngine</span></span>|  
|<span data-ttu-id="f0b10-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f0b10-112">Symbolic Name</span></span>|<span data-ttu-id="f0b10-113">DBSTARTUP_EE_PARTITIONING</span><span class="sxs-lookup"><span data-stu-id="f0b10-113">DBSTARTUP_EE_PARTITIONING</span></span>|  
|<span data-ttu-id="f0b10-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f0b10-114">Message Text</span></span>|<span data-ttu-id="f0b10-115">O banco de dados '%.\*ls' não pode ser iniciado nesta edição do SQL Server porque ele contém uma função de partição '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="f0b10-115">Database '%.\*ls' cannot be started in this edition of SQL Server because it contains a partition function '%.\*ls'.</span></span> <span data-ttu-id="f0b10-116">Somente a edição Enterprise do SQL Server oferece suporte ao particionamento.</span><span class="sxs-lookup"><span data-stu-id="f0b10-116">Only Enterprise edition of SQL Server supports partitioning.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0b10-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="f0b10-117">Explanation</span></span>  
 <span data-ttu-id="f0b10-118">O banco de dados contém uma ou mais tabelas ou índices particionados.</span><span class="sxs-lookup"><span data-stu-id="f0b10-118">The database contains one or more partitioned tables or indexes.</span></span> <span data-ttu-id="f0b10-119">Esta edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode usar particionamento.</span><span class="sxs-lookup"><span data-stu-id="f0b10-119">This edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot use partitioning.</span></span> <span data-ttu-id="f0b10-120">Portanto, o banco de dados não pode ser iniciado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f0b10-120">Therefore, the database cannot be started correctly.</span></span> <span data-ttu-id="f0b10-121">As tabelas e os índices particionados não estão disponíveis em todas as edições de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0b10-121">Partitioned tables and indexes are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f0b10-122">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f0b10-122">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0b10-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f0b10-123">User Action</span></span>  
 <span data-ttu-id="f0b10-124">Desanexe o banco de dados usando o procedimento armazenado sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="f0b10-124">Detach the database by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="f0b10-125">Mova os arquivos, se necessário, e anexe o banco de dados a uma instância de uma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com suporte usando CREATE DATABASE com a opção FOR ATTACH ou FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="f0b10-125">Move the files if it is needed, and then attach the database to an instance of a supported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition by using the CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="f0b10-126">Desabilite o particionamento em todas as tabelas e remova as funções de particionamento.</span><span class="sxs-lookup"><span data-stu-id="f0b10-126">Disable partitioning on all tables and remove the partitioning functions.</span></span> <span data-ttu-id="f0b10-127">Desanexe e anexe novamente o banco de dados ao servidor atual.</span><span class="sxs-lookup"><span data-stu-id="f0b10-127">Detach the database again, and reattach the database to the current server.</span></span>  
  
  
