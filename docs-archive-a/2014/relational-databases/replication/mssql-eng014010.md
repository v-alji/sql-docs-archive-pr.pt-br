---
title: MSSQL_ENG014010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014010 error
ms.assetid: 6ea84f2f-e7a2-4028-9ea9-af0d2eba660e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c3d989eb7ae78562fb77d9896545539ba4ca3c7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569365"
---
# <a name="mssql_eng014010"></a><span data-ttu-id="ad499-102">MSSQL_ENG014010</span><span class="sxs-lookup"><span data-stu-id="ad499-102">MSSQL_ENG014010</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ad499-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="ad499-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad499-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ad499-104">Product Name</span></span>|<span data-ttu-id="ad499-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad499-105">SQL Server</span></span>|  
|<span data-ttu-id="ad499-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ad499-106">Event ID</span></span>|<span data-ttu-id="ad499-107">14010</span><span class="sxs-lookup"><span data-stu-id="ad499-107">14010</span></span>|  
|<span data-ttu-id="ad499-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ad499-108">Event Source</span></span>|<span data-ttu-id="ad499-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ad499-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ad499-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ad499-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ad499-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ad499-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ad499-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ad499-112">Message Text</span></span>|<span data-ttu-id="ad499-113">O servidor '%s' não está definido como um servidor de assinatura.</span><span class="sxs-lookup"><span data-stu-id="ad499-113">The server '%s' is not defined as a subscription server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad499-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="ad499-114">Explanation</span></span>  
 <span data-ttu-id="ad499-115">A replicação espera que todos os servidores em uma topologia sejam registrados usando o nome do computador com um nome da instância opcional (no caso de uma instância clusterizada, o nome do servidor virtual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o nome da instância opcional).</span><span class="sxs-lookup"><span data-stu-id="ad499-115">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="ad499-116">Para que a replicação funcione corretamente, o valor retornado pelo `SELECT @@SERVERNAME` para cada servidor na topologia deve corresponder ao nome do computador ou ao nome do servidor virtual com o nome da instância opcional.</span><span class="sxs-lookup"><span data-stu-id="ad499-116">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="ad499-117">Não haverá suporte para replicação se você tiver registrado qualquer uma das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pelo endereço IP ou FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="ad499-117">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="ad499-118">Se qualquer das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver registrada por endereço IP ou por FQDN no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quando a replicação tiver sido configurada, esse erro poderá ocorrer.</span><span class="sxs-lookup"><span data-stu-id="ad499-118">If you have any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad499-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ad499-119">User Action</span></span>  
 <span data-ttu-id="ad499-120">Certifique-se de que todas as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na topologia foram registradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="ad499-120">Verify that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances in the topology are registered properly.</span></span> <span data-ttu-id="ad499-121">Se o nome de rede do computador e o nome da instância do SQL Server forem diferentes:</span><span class="sxs-lookup"><span data-stu-id="ad499-121">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="ad499-122">Adicione o nome da instância do SQL Server como um nome de rede válido.</span><span class="sxs-lookup"><span data-stu-id="ad499-122">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="ad499-123">Um método para definir um nome de rede alternativo é adicionar isto ao arquivo de hosts local.</span><span class="sxs-lookup"><span data-stu-id="ad499-123">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="ad499-124">O arquivo de hosts local fica por padrão situado em WINDOWS\system32\drivers\etc ou WINNT\system32\drivers\etc. Para obter mais informações, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="ad499-124">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="ad499-125">Por exemplo, se o nome do computador for comp1 e o computador possui um endereço IP 10.193.17.129, e o nome de instância for inst1/instname, adicione a entrada a seguir para os arquivos de host:</span><span class="sxs-lookup"><span data-stu-id="ad499-125">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="ad499-126">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="ad499-126">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="ad499-127">Remova a replicação, registre cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, depois, restabeleça a replicação.</span><span class="sxs-lookup"><span data-stu-id="ad499-127">Remove replication, register each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then reestablish replication.</span></span> <span data-ttu-id="ad499-128">Se o valor @@SERVERNAME não estiver correto em uma instância não clusterizada, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ad499-128">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="ad499-129">Depois de executar o procedimento armazenado [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), você deverá reiniciar o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que a alteração no @@SERVERNAME entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="ad499-129">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="ad499-130">Se o valor @@SERVERNAME não estiver correto em uma instância clusterizada, você deverá alterar o nome usando o Administrador de Cluster.</span><span class="sxs-lookup"><span data-stu-id="ad499-130">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="ad499-131">Para obter mais informações, veja [Instâncias do cluster de failover do AlwaysOn &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ad499-131">For more information, see [AlwaysOn Failover Cluster Instances &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad499-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ad499-132">See Also</span></span>  
 <span data-ttu-id="ad499-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad499-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span></span>  
 [<span data-ttu-id="ad499-134">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="ad499-134">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
