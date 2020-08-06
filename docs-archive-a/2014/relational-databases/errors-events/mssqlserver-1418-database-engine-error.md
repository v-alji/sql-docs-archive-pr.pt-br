---
title: MSSQLSERVER_1418 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1418 (Database Engine error)
ms.assetid: 6e9c7241-0201-44e0-9f8b-b3c4e293f0f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1fcac03f044aacce5e907824862eb589c97a07d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681672"
---
# <a name="mssqlserver_1418"></a><span data-ttu-id="c2a32-102">MSSQLSERVER_1418</span><span class="sxs-lookup"><span data-stu-id="c2a32-102">MSSQLSERVER_1418</span></span>
    
## <a name="details"></a><span data-ttu-id="c2a32-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c2a32-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2a32-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c2a32-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="c2a32-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c2a32-105">Event ID</span></span>|<span data-ttu-id="c2a32-106">1418</span><span class="sxs-lookup"><span data-stu-id="c2a32-106">1418</span></span>|  
|<span data-ttu-id="c2a32-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c2a32-107">Event Source</span></span>|<span data-ttu-id="c2a32-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c2a32-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c2a32-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c2a32-109">Component</span></span>|<span data-ttu-id="c2a32-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c2a32-110">SQLEngine</span></span>|  
|<span data-ttu-id="c2a32-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c2a32-111">Symbolic Name</span></span>|<span data-ttu-id="c2a32-112">DBM_PARTNERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="c2a32-112">DBM_PARTNERNOTFOUND</span></span>|  
|<span data-ttu-id="c2a32-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c2a32-113">Message Text</span></span>|<span data-ttu-id="c2a32-114">O endereço de rede do servidor "%.\*ls" não pode ser acessado ou não existe.</span><span class="sxs-lookup"><span data-stu-id="c2a32-114">The server network address "%.\*ls" can not be reached or does not exist.</span></span> <span data-ttu-id="c2a32-115">Verifique o nome do endereço de rede e se as portas de pontos de extremidade local e remoto estão em operação.</span><span class="sxs-lookup"><span data-stu-id="c2a32-115">Check the network address name and that the ports for the local and remote endpoints are operational.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c2a32-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="c2a32-116">Explanation</span></span>  
 <span data-ttu-id="c2a32-117">Os pontos de extremidade de rede do servidor não responderam porque o endereço especificado de rede do servidor não pode ser acessado ou não existe.</span><span class="sxs-lookup"><span data-stu-id="c2a32-117">The server network endpoint did not respond because the specified server network address cannot be reached or does not exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2a32-118">Por padrão, o sistema operacional [!INCLUDE[msCoName](../../includes/msconame-md.md)] bloqueia todas as portas.</span><span class="sxs-lookup"><span data-stu-id="c2a32-118">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] operating system blocks all ports.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2a32-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c2a32-119">User Action</span></span>  
 <span data-ttu-id="c2a32-120">Verifique o nome de endereço de rede e envie o comando novamente.</span><span class="sxs-lookup"><span data-stu-id="c2a32-120">Verify the network address name and reissue the command.</span></span>  
  
 <span data-ttu-id="c2a32-121">A ação corretiva pode ser necessária em ambos os parceiros.</span><span class="sxs-lookup"><span data-stu-id="c2a32-121">Corrective action might be required on both partners.</span></span> <span data-ttu-id="c2a32-122">Por exemplo, se essa mensagem for gerada quando você estiver tentando executar SET PARTNER na instância do servidor principal, a mensagem poderá indicar que você precisa apenas realizar a ação corretiva na instância do servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="c2a32-122">For example, if this message is raised when you are trying to run SET PARTNER on the principal server instance, the message might imply that you only have to take corrective action on the mirror server instance.</span></span> <span data-ttu-id="c2a32-123">Contudo, ações corretivas podem ser necessárias em ambos os parceiros.</span><span class="sxs-lookup"><span data-stu-id="c2a32-123">However, corrective actions might be required on both partners.</span></span>  
  
### <a name="additional-corrective-actions"></a><span data-ttu-id="c2a32-124">Ações corretivas adicionais</span><span class="sxs-lookup"><span data-stu-id="c2a32-124">Additional Corrective Actions</span></span>  
  
-   <span data-ttu-id="c2a32-125">Verifique se o banco de dados espelho está pronto para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="c2a32-125">Make sure that the mirror database is ready for mirroring.</span></span>  
  
-   <span data-ttu-id="c2a32-126">Verifique se o nome e a porta da instância do servidor espelho estão corretos.</span><span class="sxs-lookup"><span data-stu-id="c2a32-126">Make sure that the name and port of the mirror server instance are correct.</span></span>  
  
-   <span data-ttu-id="c2a32-127">Verifique se a instância do servidor espelho de destino não está protegida por um firewall.</span><span class="sxs-lookup"><span data-stu-id="c2a32-127">Make sure that the destination mirror server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="c2a32-128">Verifique se a instância do servidor principal não está protegida por um firewall.</span><span class="sxs-lookup"><span data-stu-id="c2a32-128">Make sure that the principal server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="c2a32-129">Verifique se os pontos de extremidade são iniciados nos parceiros usando a coluna **state** ou **state_desc** da exibição do catálogo **sys.database_mirroring_endpoints**.</span><span class="sxs-lookup"><span data-stu-id="c2a32-129">Verify that the endpoints are started on the partners by using the **state** or **state_desc** column the of the **sys.database_mirroring_endpoints** catalog view.</span></span> <span data-ttu-id="c2a32-130">Se algum ponto de extremidade não foi iniciado, execute uma instrução ALTER ENDPOINT para iniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="c2a32-130">If either endpoint is not started, execute an ALTER ENDPOINT statement to start it.</span></span>  
  
-   <span data-ttu-id="c2a32-131">Verifique se a instância do servidor principal está escutando na porta atribuída a seu ponto de extremidade de espelhamento de banco de dados e se a instância do servidor de espelho está escutando em sua porta.</span><span class="sxs-lookup"><span data-stu-id="c2a32-131">Make sure that the principal server instance is listening on the port assigned to its database mirroring endpoint and that and the mirror server instance is listening on its port.</span></span> <span data-ttu-id="c2a32-132">Para obter mais informações, consulte "Verificando a disponibilidade da porta", posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c2a32-132">For more information, see "Verifying Port Availability," later in this topic.</span></span> <span data-ttu-id="c2a32-133">Se um parceiro não estiver escutando em sua porta designada, modifique o ponto de extremidade de espelhamento de banco de dados para escutar em uma porta diferente.</span><span class="sxs-lookup"><span data-stu-id="c2a32-133">If a partner is not listening on its assigned port, modify the database mirroring endpoint to listen on a different port.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c2a32-134">A segurança configurada incorretamente pode causar uma mensagem de erro de configuração geral.</span><span class="sxs-lookup"><span data-stu-id="c2a32-134">Improperly configured security can cause a general setup error message.</span></span> <span data-ttu-id="c2a32-135">Normalmente, a instância do servidor descarta a solicitação incorreta de conexão sem responder.</span><span class="sxs-lookup"><span data-stu-id="c2a32-135">Typically, the server instance drops the bad connection request without responding.</span></span> <span data-ttu-id="c2a32-136">Para o chamador, um erro de configuração de segurança pode ocorrer por diversos motivos, como banco de dados espelho em um estado ruim ou inexistente, permissões incorretas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c2a32-136">To the caller, a security-configuration error could appear to have occurred for a variety of other reasons, such as the mirror database in a bad state or does not exist, incorrect permissions, and so on.</span></span>  
  
### <a name="using-the-error-log-file-for-diagnosis"></a><span data-ttu-id="c2a32-137">Usando o arquivo de log de erros para diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c2a32-137">Using the Error Log File for Diagnosis</span></span>  
 <span data-ttu-id="c2a32-138">Em alguns casos, os arquivos de log de erros estão disponíveis para investigação.</span><span class="sxs-lookup"><span data-stu-id="c2a32-138">In some cases, only error log files are available for investigation.</span></span> <span data-ttu-id="c2a32-139">Nesses casos, determine se o log de erros contém a mensagem de erro 26023 para a porta TCP do ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c2a32-139">In these cases, determine whether the error log contains error message 26023 for the TCP port of the database mirroring endpoint.</span></span> <span data-ttu-id="c2a32-140">Esse erro, de severidade 16, pode indicar que o ponto de extremidade de espelhamento de banco de dados não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c2a32-140">This error, which is severity 16, might indicate that the database mirroring endpoint is not started.</span></span> <span data-ttu-id="c2a32-141">Essa mensagem pode ocorrer mesmo que o **sys.database_mirroring_endpoints** mostre o estado do ponto de extremidade como iniciado.</span><span class="sxs-lookup"><span data-stu-id="c2a32-141">This message can occur even if **sys.database_mirroring_endpoints** shows the endpoint state as started.</span></span>  
  
 <span data-ttu-id="c2a32-142">Depois de resolver os problemas encontrados, execute novamente a instrução SET PARTNER do ALTER DATABASE *database_name* no servidor de entidade.</span><span class="sxs-lookup"><span data-stu-id="c2a32-142">After resolving any issues that you encounter, rerun the ALTER DATABASE *database_name* SET PARTNER statement on the principal server.</span></span>  
  
### <a name="verifying-port-availability"></a><span data-ttu-id="c2a32-143">Verificando a disponibilidade da porta</span><span class="sxs-lookup"><span data-stu-id="c2a32-143">Verifying Port Availability</span></span>  
 <span data-ttu-id="c2a32-144">Quando estiver configurando a rede para uma sessão de espelhamento de banco de dados, verifique se o ponto de extremidade de espelhamento de banco de dados de cada instância do servidor é usado apenas pelo processo de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c2a32-144">When you are configuring the network for a database mirroring session, make sure the database mirroring endpoint of each server instance is used by only the database mirroring process.</span></span> <span data-ttu-id="c2a32-145">Se outro processo estiver escutando na porta atribuída a um ponto de extremidade de espelhamento de banco de dados, os processos de espelhamento de banco de dados das outras instâncias de servidor não poderão se conectar ao ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c2a32-145">If another process is listening on the port assigned to a database mirroring endpoint, the database mirroring processes of the other server instances cannot connect to the endpoint.</span></span>  
  
 <span data-ttu-id="c2a32-146">Para exibir todas as portas escutadas por um servidor baseado no Windows, use o utilitário de prompt de comando **netstat**.</span><span class="sxs-lookup"><span data-stu-id="c2a32-146">To display all the ports on which a Windows-based server is listening, use the **netstat** command-prompt utility.</span></span> <span data-ttu-id="c2a32-147">A sintaxe de **netstat** depende da versão do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="c2a32-147">The syntax for **netstat** depends on the version of the Windows operating system.</span></span> <span data-ttu-id="c2a32-148">Para obter mais informações, consulte a documentação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c2a32-148">For more information, see the operating system documentation.</span></span>  
  
#### <a name="windows-server-2003-service-pack-1-sp1"></a><span data-ttu-id="c2a32-149">Windows Server 2003 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c2a32-149">Windows Server 2003 Service Pack 1 (SP1)</span></span>  
 <span data-ttu-id="c2a32-150">Para listar as portas de escuta e os processos que abriram essas portas, insira o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="c2a32-150">To list listening ports and the processes that have those ports opened, enter the following command at the Windows command prompt:</span></span>  
  
 <span data-ttu-id="c2a32-151">**netstat -abn**</span><span class="sxs-lookup"><span data-stu-id="c2a32-151">**netstat -abn**</span></span>  
  
#### <a name="windows-server-2003-pre-sp1"></a><span data-ttu-id="c2a32-152">Windows Server 2003 (pre-SP1)</span><span class="sxs-lookup"><span data-stu-id="c2a32-152">Windows Server 2003 (pre-SP1)</span></span>  
 <span data-ttu-id="c2a32-153">Para identificar as portas de escuta e os processos que abriram essas portas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c2a32-153">To identify the listening ports and the processes that have those ports opened, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c2a32-154">Obtenha a ID do processo.</span><span class="sxs-lookup"><span data-stu-id="c2a32-154">Obtain the process ID.</span></span>  
  
     <span data-ttu-id="c2a32-155">Para saber a ID do processo de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], conecte-se àquela instância e use a seguinte instrução do [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c2a32-155">To learn the process ID of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connect to that instance and use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT SERVERPROPERTY('ProcessID')   
    ```  
  
     <span data-ttu-id="c2a32-156">Para obter mais informações, consulte "SERVERPROPERTY (Transact-SQL)" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2a32-156">For more information, see "SERVERPROPERTY (Transact-SQL)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="c2a32-157">Faça a correspondência da ID do processo à saída do seguinte comando **netstat**:</span><span class="sxs-lookup"><span data-stu-id="c2a32-157">Match the process ID with the output of the following **netstat** command:</span></span>  
  
     <span data-ttu-id="c2a32-158">**netstat -ano**</span><span class="sxs-lookup"><span data-stu-id="c2a32-158">**netstat -ano**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a32-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2a32-159">See Also</span></span>  
 <span data-ttu-id="c2a32-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2a32-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="c2a32-161">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c2a32-161">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="c2a32-162">[Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c2a32-162">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c2a32-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2a32-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="c2a32-164">[Especificar um endereço de rede do servidor &#40;espelhamento de banco de dados&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="c2a32-164">[Specify a Server Network Address &#40;Database Mirroring&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="c2a32-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2a32-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="c2a32-166">Solução de problemas de configuração de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c2a32-166">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
