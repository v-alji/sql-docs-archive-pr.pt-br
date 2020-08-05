---
title: MSSQLSERVER_9955 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573027"
---
# <a name="mssqlserver_9955"></a><span data-ttu-id="e7592-102">MSSQLSERVER_9955</span><span class="sxs-lookup"><span data-stu-id="e7592-102">MSSQLSERVER_9955</span></span>
    
## <a name="details"></a><span data-ttu-id="e7592-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e7592-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7592-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e7592-104">Product Name</span></span>|<span data-ttu-id="e7592-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7592-105">SQL Server</span></span>|  
|<span data-ttu-id="e7592-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e7592-106">Event ID</span></span>|<span data-ttu-id="e7592-107">9955</span><span class="sxs-lookup"><span data-stu-id="e7592-107">9955</span></span>|  
|<span data-ttu-id="e7592-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e7592-108">Event Source</span></span>|<span data-ttu-id="e7592-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e7592-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e7592-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e7592-110">Component</span></span>|<span data-ttu-id="e7592-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e7592-111">SQLEngine</span></span>|  
|<span data-ttu-id="e7592-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e7592-112">Symbolic Name</span></span>|<span data-ttu-id="e7592-113">FTXT2_MSSEARCHACCESSDENY</span><span class="sxs-lookup"><span data-stu-id="e7592-113">FTXT2_MSSEARCHACCESSDENY</span></span>|  
|<span data-ttu-id="e7592-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e7592-114">Message Text</span></span>|<span data-ttu-id="e7592-115">Falha no SQL Server ao criar o pipe nomeado '%ls' para se comunicar com o daemon de filtro de texto completo (erro do Windows: %d).</span><span class="sxs-lookup"><span data-stu-id="e7592-115">SQL Server failed to create named pipe '%ls' to communicate with the full-text filter daemon (Windows error: %d).</span></span> <span data-ttu-id="e7592-116">Já existe um pipe nomeado para um processo de host do daemon de filtro, o sistema tem recursos insuficientes ou ocorreu uma falha na pesquisa de SID (número de identificação de segurança) referente ao grupo de contas do daemon de filtro.</span><span class="sxs-lookup"><span data-stu-id="e7592-116">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span> <span data-ttu-id="e7592-117">Para resolver esse erro, encerre quaisquer processos do daemon de filtro de texto completo e, se necessário, reconfigure a conta de serviço iniciador de daemon de texto completo.</span><span class="sxs-lookup"><span data-stu-id="e7592-117">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon launcher service account.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e7592-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="e7592-118">Explanation</span></span>  
 <span data-ttu-id="e7592-119">Essa mensagem é exibida porque o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não conseguiu criar um pipe nomeado para se comunicar com o daemon de filtro de texto completo.</span><span class="sxs-lookup"><span data-stu-id="e7592-119">This message occurs because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to create a named pipe to communicate with the full-text filter daemon.</span></span> <span data-ttu-id="e7592-120">Já existe um pipe nomeado para um processo de host do daemon de filtro, o sistema tem recursos insuficientes ou ocorreu uma falha na pesquisa de SID (número de identificação de segurança) referente ao grupo de contas do daemon de filtro.</span><span class="sxs-lookup"><span data-stu-id="e7592-120">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7592-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e7592-121">User Action</span></span>  
 <span data-ttu-id="e7592-122">Para corrigir esse erro, encerre todos os processos do daemon de filtro de texto completo em execução e, se necessário, reconfigure a conta de host do daemon de texto completo usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e7592-122">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon host account by using the SQL Server Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7592-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7592-123">See Also</span></span>  
 <span data-ttu-id="e7592-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e7592-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="e7592-125">[Definir a conta de serviço para o iniciador do daemon de filtro de texto completo](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="e7592-125">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 [<span data-ttu-id="e7592-126">Pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="e7592-126">Full-Text Search</span></span>](../search/full-text-search.md)  
  
  
