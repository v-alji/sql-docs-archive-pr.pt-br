---
title: MSSQL_ENG014114 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014114 error
ms.assetid: f5f04590-e1c6-40d8-ab2b-98c791a0fc44
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ba2a1fde59f55eecbfeeec46555567cde964f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568481"
---
# <a name="mssql_eng014114"></a><span data-ttu-id="9f9bc-102">MSSQL_ENG014114</span><span class="sxs-lookup"><span data-stu-id="9f9bc-102">MSSQL_ENG014114</span></span>
    
## <a name="message-details"></a><span data-ttu-id="9f9bc-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="9f9bc-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f9bc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9f9bc-104">Product Name</span></span>|<span data-ttu-id="9f9bc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f9bc-105">SQL Server</span></span>|  
|<span data-ttu-id="9f9bc-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9f9bc-106">Event ID</span></span>|<span data-ttu-id="9f9bc-107">14114</span><span class="sxs-lookup"><span data-stu-id="9f9bc-107">14114</span></span>|  
|<span data-ttu-id="9f9bc-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9f9bc-108">Event Source</span></span>|<span data-ttu-id="9f9bc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9f9bc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9f9bc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9f9bc-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="9f9bc-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9f9bc-111">Symbolic Name</span></span>||  
|<span data-ttu-id="9f9bc-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9f9bc-112">Message Text</span></span>|<span data-ttu-id="9f9bc-113">'%s' não está configurado como um Distributor.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-113">'%s' is not configured as a Distributor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f9bc-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="9f9bc-114">Explanation</span></span>  
 <span data-ttu-id="9f9bc-115">Se a mensagem de erro especificar uma instância em particular diferente de 'null', a instância especificada não foi configurada corretamente para ser reconhecida como um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-115">If the error message specifies a particular instance, rather than 'null', the instance specified has not been properly configured to be recognized as a Distributor.</span></span>  
  
 <span data-ttu-id="9f9bc-116">Se a mensagem especificar 'null' como um Distribuidor, não haverá entrada para o servidor local no banco de dados **mestre** ou a entrada estará incorreta (talvez porque o computador foi renomeado).</span><span class="sxs-lookup"><span data-stu-id="9f9bc-116">If the message specifies 'null' as a Distributor, there is no entry for the local server in **master** database, or the entry is incorrect (perhaps because the computer was renamed).</span></span> <span data-ttu-id="9f9bc-117">A replicação espera que todos os servidores em uma topologia sejam registrados usando o nome do computador com um nome da instância opcional (no caso de uma instância clusterizada, o nome do servidor virtual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o nome da instância opcional).</span><span class="sxs-lookup"><span data-stu-id="9f9bc-117">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="9f9bc-118">Para que a replicação funcione corretamente, o valor retornado pelo `SELECT @@SERVERNAME` para cada servidor na topologia deve corresponder ao nome do computador ou ao nome do servidor virtual com o nome da instância opcional.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-118">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="9f9bc-119">Não haverá suporte para replicação se você tiver registrado qualquer uma das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pelo endereço IP ou FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="9f9bc-119">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="9f9bc-120">Se você tinha qualquer das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registrada pelo endereço IP ou FQDN no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quando configurou a replicação, esse erro pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-120">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f9bc-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9f9bc-121">User Action</span></span>  
 <span data-ttu-id="9f9bc-122">Se a mensagem de erro especificar uma instância em particular, configure o servidor como um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-122">If the error message specifies a particular instance, configure the server as a Distributor.</span></span> <span data-ttu-id="9f9bc-123">Para obter mais informações, consulte [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="9f9bc-123">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
 <span data-ttu-id="9f9bc-124">Se a mensagem não especificar uma instância em particular ('null'), certifique-se de que a instância do Distribuidor esteja registrada corretamente.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-124">If the message does not specify a particular instance ('null'), verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="9f9bc-125">Se o nome de rede do computador e o nome da instância do SQL Server forem diferentes:</span><span class="sxs-lookup"><span data-stu-id="9f9bc-125">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="9f9bc-126">Adicione o nome da instância do SQL Server como um nome de rede válido.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-126">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="9f9bc-127">Um método para definir um nome de rede alternativo é adicionar isto ao arquivo de hosts local.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-127">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="9f9bc-128">O arquivo de hosts local fica por padrão situado em WINDOWS\system32\drivers\etc ou WINNT\system32\drivers\etc. Para obter mais informações, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-128">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="9f9bc-129">Por exemplo, se o nome do computador for comp1 e o computador possui um endereço IP 10.193.17.129, e o nome de instância for inst1/instname, adicione a entrada a seguir para os arquivos de host:</span><span class="sxs-lookup"><span data-stu-id="9f9bc-129">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="9f9bc-130">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="9f9bc-130">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="9f9bc-131">Desabilite a distribuição, registre a instância e restabeleça a distribuição.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-131">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="9f9bc-132">Se o valor @@SERVERNAME não estiver correto em uma instância não clusterizada, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9f9bc-132">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="9f9bc-133">Depois de executar o procedimento armazenado [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), você deverá reiniciar o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que a alteração no @@SERVERNAME entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-133">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="9f9bc-134">Se o valor @@SERVERNAME não estiver correto em uma instância clusterizada, você deverá alterar o nome usando o Administrador de Cluster.</span><span class="sxs-lookup"><span data-stu-id="9f9bc-134">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="9f9bc-135">Para obter mais informações, consulte [Instâncias do Cluster de Failover do AlwaysOn (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9f9bc-135">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9bc-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f9bc-136">See Also</span></span>  
 [<span data-ttu-id="9f9bc-137">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="9f9bc-137">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
