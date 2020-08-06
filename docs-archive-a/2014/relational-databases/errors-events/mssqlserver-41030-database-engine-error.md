---
title: MSSQLSERVER_41030 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41030 (Database Engine error)
ms.assetid: c85341ae-0fbf-42ae-9275-4cfe678238f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b137b739d4c1641b88983708df62d2e52fd0eab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683544"
---
# <a name="mssqlserver_41030"></a><span data-ttu-id="ecd93-102">MSSQLSERVER_41030</span><span class="sxs-lookup"><span data-stu-id="ecd93-102">MSSQLSERVER_41030</span></span>
    
## <a name="details"></a><span data-ttu-id="ecd93-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ecd93-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecd93-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ecd93-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="ecd93-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ecd93-105">Event ID</span></span>|<span data-ttu-id="ecd93-106">41030</span><span class="sxs-lookup"><span data-stu-id="ecd93-106">41030</span></span>|  
|<span data-ttu-id="ecd93-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ecd93-107">Event Source</span></span>|<span data-ttu-id="ecd93-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ecd93-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ecd93-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ecd93-109">Component</span></span>|<span data-ttu-id="ecd93-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ecd93-110">SQLEngine</span></span>|  
|<span data-ttu-id="ecd93-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ecd93-111">Symbolic Name</span></span>|<span data-ttu-id="ecd93-112">OPEN_CLUSTER_SUB_KEY</span><span class="sxs-lookup"><span data-stu-id="ecd93-112">OPEN_CLUSTER_SUB_KEY</span></span>|  
|<span data-ttu-id="ecd93-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ecd93-113">Message Text</span></span>|<span data-ttu-id="ecd93-114">Falha ao abrir a subchave do Registro '%.\*ls' do Windows Server Failover Clustering (código de erro %d).</span><span class="sxs-lookup"><span data-stu-id="ecd93-114">Failed to open the Windows Server Failover Clustering registry subkey '%.\*ls' (Error code %d).</span></span>  <span data-ttu-id="ecd93-115">A chave pai é a chave raiz do cluster.</span><span class="sxs-lookup"><span data-stu-id="ecd93-115">The parent key is the cluster root key.</span></span>  <span data-ttu-id="ecd93-116">O serviço WSFC não pode estar em execução ou não pode estar acessível em seu estado atual; do contrário, os argumentos especificados não serão válidos.</span><span class="sxs-lookup"><span data-stu-id="ecd93-116">The WSFC service may not be running or may not be accessible in its current state, or the specified arguments are invalid.</span></span> <span data-ttu-id="ecd93-117">Se o grupo de disponibilidade correspondente foi removido, esse erro será provável.</span><span class="sxs-lookup"><span data-stu-id="ecd93-117">If the corresponding availability group has been dropped, this error is expected.</span></span> <span data-ttu-id="ecd93-118">Para obter informações sobre esse código de erro, consulte "Códigos de erro do sistema" na documentação do Windows Development.</span><span class="sxs-lookup"><span data-stu-id="ecd93-118">For information about this error code, see "System Error Codes" in the Windows Development documentation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecd93-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="ecd93-119">Explanation</span></span>  
 <span data-ttu-id="ecd93-120">Se um cluster WSFC for destruído, ele removerá todas as chaves do Registro relacionadas a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd93-120">If a WSFC cluster is destroyed, it removes all registry keys related to [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecd93-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ecd93-121">User Action</span></span>  
 <span data-ttu-id="ecd93-122">Após recriar um cluster WSFC, desabilite e habilite novamente o AlwaysOn em cada nó de cluster no qual uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitada para AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ecd93-122">After re-creating a WSFC cluster, disable and then re-enable AlwaysOn on every cluster node on which an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is enabled for AlwaysOn.</span></span> <span data-ttu-id="ecd93-123">Você pode usar o Gerenciador de Configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="ecd93-123">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for this task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd93-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ecd93-124">See Also</span></span>  
 <span data-ttu-id="ecd93-125">[Habilitar e desabilitar Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ecd93-125">[Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ecd93-126">WSFC &#40;Windows Server Failover Clustering&#41; com o SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecd93-126">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  
