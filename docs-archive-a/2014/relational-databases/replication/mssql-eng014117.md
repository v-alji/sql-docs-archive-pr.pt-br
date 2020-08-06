---
title: MSSQL_ENG014117 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014117 error
ms.assetid: e5906a76-9511-4c47-8826-8c765b58a39d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4694aacc7d1f5ee31f4ff54d8cdd4256b48f713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568482"
---
# <a name="mssql_eng014117"></a><span data-ttu-id="030a9-102">MSSQL_ENG014117</span><span class="sxs-lookup"><span data-stu-id="030a9-102">MSSQL_ENG014117</span></span>
    
## <a name="message-details"></a><span data-ttu-id="030a9-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="030a9-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="030a9-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="030a9-104">Product Name</span></span>|<span data-ttu-id="030a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="030a9-105">SQL Server</span></span>|  
|<span data-ttu-id="030a9-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="030a9-106">Event ID</span></span>|<span data-ttu-id="030a9-107">14117</span><span class="sxs-lookup"><span data-stu-id="030a9-107">14117</span></span>|  
|<span data-ttu-id="030a9-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="030a9-108">Event Source</span></span>|<span data-ttu-id="030a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="030a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="030a9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="030a9-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="030a9-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="030a9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="030a9-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="030a9-112">Message Text</span></span>|<span data-ttu-id="030a9-113">'%s' não está configurado como um banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="030a9-113">'%s' is not configured as a distribution database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="030a9-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="030a9-114">Explanation</span></span>  
 <span data-ttu-id="030a9-115">Esse erro poderá acontecer se uma ou ambas as situações forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="030a9-115">This error can occur if one or both of the following are true:</span></span>  
  
-   <span data-ttu-id="030a9-116">A entrada para o banco de dados de distribuição especificado está ausente de **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="030a9-116">The entry for the specified distribution database is missing from **msdb..MSdistributiondbs**.</span></span>  
  
-   <span data-ttu-id="030a9-117">Não há uma entrada para o servidor local no banco de dados **mestre** ou a entrada localizada está incorreta.</span><span class="sxs-lookup"><span data-stu-id="030a9-117">There is not an entry for the local server in the **master** database, or the entry that is there is incorrect.</span></span>  
  
     <span data-ttu-id="030a9-118">A replicação espera que todos os servidores em uma topologia sejam registrados usando o nome do computador com um nome da instância opcional (no caso de uma instância clusterizada, o nome do servidor virtual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o nome da instância opcional).</span><span class="sxs-lookup"><span data-stu-id="030a9-118">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="030a9-119">Para que a replicação funcione corretamente, o valor retornado pelo `SELECT @@SERVERNAME` para cada servidor na topologia deve corresponder ao nome do computador ou ao nome do servidor virtual com o nome da instância opcional.</span><span class="sxs-lookup"><span data-stu-id="030a9-119">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
     <span data-ttu-id="030a9-120">Não haverá suporte para replicação se você tiver registrado qualquer uma das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pelo endereço IP ou FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="030a9-120">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="030a9-121">Se você tinha qualquer das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registrada pelo endereço IP ou FQDN no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quando configurou a replicação, esse erro pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="030a9-121">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="030a9-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="030a9-122">User Action</span></span>  
 <span data-ttu-id="030a9-123">Certifique-se de que a instância do Distribuidor esteja corretamente registrada.</span><span class="sxs-lookup"><span data-stu-id="030a9-123">Verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="030a9-124">Se o nome de rede do computador e o nome da instância do SQL Server forem diferentes:</span><span class="sxs-lookup"><span data-stu-id="030a9-124">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="030a9-125">Adicione o nome da instância do SQL Server como um nome de rede válido.</span><span class="sxs-lookup"><span data-stu-id="030a9-125">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="030a9-126">Um método para definir um nome de rede alternativo é adicionar isto ao arquivo de hosts local.</span><span class="sxs-lookup"><span data-stu-id="030a9-126">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="030a9-127">O arquivo de hosts local fica por padrão situado em WINDOWS\system32\drivers\etc ou WINNT\system32\drivers\etc. Para obter mais informações, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="030a9-127">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="030a9-128">Por exemplo, se o nome do computador for comp1 e o computador possui um endereço IP 10.193.17.129, e o nome de instância for inst1/instname, adicione a entrada a seguir para os arquivos de host:</span><span class="sxs-lookup"><span data-stu-id="030a9-128">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="030a9-129">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="030a9-129">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="030a9-130">Desabilite a distribuição, registre a instância e restabeleça a distribuição.</span><span class="sxs-lookup"><span data-stu-id="030a9-130">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="030a9-131">Se o valor @@SERVERNAME não estiver correto em uma instância não clusterizada, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="030a9-131">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="030a9-132">Depois de executar o procedimento armazenado [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), você deverá reiniciar o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que a alteração no @@SERVERNAME entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="030a9-132">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="030a9-133">Se o valor @@SERVERNAME não estiver correto em uma instância clusterizada, você deverá alterar o nome usando o Administrador de Cluster.</span><span class="sxs-lookup"><span data-stu-id="030a9-133">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="030a9-134">Para obter mais informações, consulte [Instâncias do Cluster de Failover do AlwaysOn (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="030a9-134">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
 <span data-ttu-id="030a9-135">Depois de verificar que a instância do Distribuidor está registrada corretamente, certifique-se de que o banco de dados de distribuição esteja listado em **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="030a9-135">After verifying that the Distributor instance is registered properly, verify that the distribution database is listed in **msdb..MSdistributiondbs**.</span></span> <span data-ttu-id="030a9-136">Se não estiver listado:</span><span class="sxs-lookup"><span data-stu-id="030a9-136">If it is not listed:</span></span>  
  
1.  <span data-ttu-id="030a9-137">Gere um script para a configuração de distribuição.</span><span class="sxs-lookup"><span data-stu-id="030a9-137">Script out the distribution configuration.</span></span> <span data-ttu-id="030a9-138">Para obter mais informações, consulte [Scripting Replication](scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="030a9-138">For more information, see [Scripting Replication](scripting-replication.md).</span></span>  
  
2.  <span data-ttu-id="030a9-139">Desabilite a distribuição e habilite-a novamente.</span><span class="sxs-lookup"><span data-stu-id="030a9-139">Disable distribution and then re-enable it.</span></span> <span data-ttu-id="030a9-140">Para obter mais informações, consulte [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="030a9-140">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="030a9-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="030a9-141">See Also</span></span>  
 [<span data-ttu-id="030a9-142">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="030a9-142">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
