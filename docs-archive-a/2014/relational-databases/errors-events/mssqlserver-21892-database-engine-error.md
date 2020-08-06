---
title: MSSQLSERVER_21892 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd3bfa1213f0569293991d6bd759619c6e7b596
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684761"
---
# <a name="mssqlserver_21892"></a><span data-ttu-id="c9681-102">MSSQLSERVER_21892</span><span class="sxs-lookup"><span data-stu-id="c9681-102">MSSQLSERVER_21892</span></span>
    
## <a name="details"></a><span data-ttu-id="c9681-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c9681-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9681-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c9681-104">Product Name</span></span>|<span data-ttu-id="c9681-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9681-105">SQL Server</span></span>|  
|<span data-ttu-id="c9681-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c9681-106">Event ID</span></span>|<span data-ttu-id="c9681-107">21892</span><span class="sxs-lookup"><span data-stu-id="c9681-107">21892</span></span>|  
|<span data-ttu-id="c9681-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c9681-108">Event Source</span></span>|<span data-ttu-id="c9681-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9681-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9681-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c9681-110">Component</span></span>|<span data-ttu-id="c9681-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9681-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9681-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c9681-112">Symbolic Name</span></span>|<span data-ttu-id="c9681-113">SQLErrorNum21892</span><span class="sxs-lookup"><span data-stu-id="c9681-113">SQLErrorNum21892</span></span>|  
|<span data-ttu-id="c9681-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c9681-114">Message Text</span></span>|<span data-ttu-id="c9681-115">Não é possível consultar sys.availability_replicas no primário do grupo de disponibilidade associado ao nome de rede virtual '%s' quanto aos nomes de servidor das réplicas membro: erro = %d, mensagem de erro = %s.',</span><span class="sxs-lookup"><span data-stu-id="c9681-115">Unable to query sys.availability_replicas at the availability group primary associated with virtual network name '%s' for the server names of the member replicas: error = %d, error message = %s.',</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9681-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="c9681-116">Explanation</span></span>  
 <span data-ttu-id="c9681-117">`sp_validate_replica_hosts_as_publishers` consulta a réplica primária atual do grupo de disponibilidade associado ao publicador redirecionado, a fim de determinar as instâncias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospedam as réplicas de membro.</span><span class="sxs-lookup"><span data-stu-id="c9681-117">`sp_validate_replica_hosts_as_publishers` queries the current primary of the availability group associated with the redirected publisher, to determine the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that host the member replicas.</span></span>  <span data-ttu-id="c9681-118">Quando essa consulta falha, o erro 21892 é retornado.</span><span class="sxs-lookup"><span data-stu-id="c9681-118">When this query fails, error 21892 is returned.</span></span>  
  
 <span data-ttu-id="c9681-119">`sp_validate_replica_hosts_as_publishers` é geralmente um dos primeiros usos do servidor vinculado temporário; portanto, se houver problemas de conectividade, eles provavelmente aparecerão primeiro com `sp_validate_replica_hosts_as_publishers`.</span><span class="sxs-lookup"><span data-stu-id="c9681-119">`sp_validate_replica_hosts_as_publishers` is typically on of the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with `sp_validate_replica_hosts_as_publishers`.</span></span> <span data-ttu-id="c9681-120">Diferente de `sp_validate_redirected_publisher`, o servidor vinculado usado por `sp_validate_replica_hosts_as_publishers` sempre usa as credenciais do chamador ao se conectar a qualquer host de réplica de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c9681-120">Unlike `sp_validate_redirected_publisher`, the linked server used by `sp_validate_replica_hosts_as_publishers` always uses the credentials of the caller when connecting to any of the availability group replica hosts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9681-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c9681-121">User Action</span></span>  
 <span data-ttu-id="c9681-122">Ao executar este procedimento armazenado, verifique se a execução está sendo realizada a partir de um logon válido em todas as réplicas.</span><span class="sxs-lookup"><span data-stu-id="c9681-122">When running this stored procedure, made certain that you run from a login that is valid on all of the replicas.</span></span> <span data-ttu-id="c9681-123">O logon exigirá autorização suficiente para consultar tabelas de metadados de grupo de disponibilidade, bem como para consultar as tabelas de metadados de assinatura na réplica do banco de dados publicador.</span><span class="sxs-lookup"><span data-stu-id="c9681-123">The login will require sufficient authorization to query availability group metadata tables as well as to query the subscription metadata tables in the publisher database replica.</span></span>  
  
 <span data-ttu-id="c9681-124">Examine o erro referenciado original para determinar a causa da falha e execute a ação corretiva apropriada.</span><span class="sxs-lookup"><span data-stu-id="c9681-124">Examine the original referenced error to determine the cause of the failure and appropriate corrective action.</span></span>  
  
  
