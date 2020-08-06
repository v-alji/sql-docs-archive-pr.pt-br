---
title: Renomear um computador que hospeda uma instância autônoma do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- remote login errors [SQL Server]
- standalone computer names [SQL Server]
- names [SQL Server], standalone instances of SQL Server
- renaming standalone instances of SQL Server
- sysservers system table
- removing remote logins
- deleting remote logins
- dropping remote logins
ms.assetid: bbaf1445-b8a2-4ebf-babe-17d8cf20b037
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 079348921900a7cbf880027433280253df1a9e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684849"
---
# <a name="rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server"></a><span data-ttu-id="5a704-102">Renomear um computador que hospeda uma instância autônoma do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a704-102">Rename a Computer that Hosts a Stand-Alone Instance of SQL Server</span></span>
  <span data-ttu-id="5a704-103">Quando você altera o nome do computador que está executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o novo nome será reconhecido durante a inicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a704-103">When you change the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the new name is recognized during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span> <span data-ttu-id="5a704-104">Não é necessário executar novamente a Instalação para redefinir o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-104">You do not have to run Setup again to reset the computer name.</span></span> <span data-ttu-id="5a704-105">Em vez disso, use as etapas a seguir para atualizar os metadados do sistema armazenados em sys.servers e relatados pela função de sistema @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="5a704-105">Instead, use the following steps to update system metadata that is stored in sys.servers and reported by the system function @@SERVERNAME.</span></span> <span data-ttu-id="5a704-106">Atualize os metadados do sistema para que reflitam as alterações de nome do computador de conexões remotas e aplicativos que usam @@SERVERNAME ou que consultam o nome do servidor em sys.servers.</span><span class="sxs-lookup"><span data-stu-id="5a704-106">Update system metadata to reflect computer name changes for remote connections and applications that use @@SERVERNAME, or that query the server name from sys.servers.</span></span>  
  
 <span data-ttu-id="5a704-107">As etapas a seguir não podem ser usadas para renomear uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a704-107">The following steps cannot be used to rename an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a704-108">Elas só podem ser usadas para renomear a parte do nome de instância que corresponde ao nome do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-108">They can be used only to rename the part of the instance name that corresponds to the computer name.</span></span> <span data-ttu-id="5a704-109">Por exemplo, você pode alterar um computador denominado MB1 que hospede uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] denominada Instance1 para outro nome, como MB2.</span><span class="sxs-lookup"><span data-stu-id="5a704-109">For example, you can change a computer named MB1 that hosts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] named Instance1 to another name, such as MB2.</span></span> <span data-ttu-id="5a704-110">Entretanto, a parte de instância do nome, Instance1, permanecerá inalterada.</span><span class="sxs-lookup"><span data-stu-id="5a704-110">However, the instance part of the name, Instance1, will remain unchanged.</span></span> <span data-ttu-id="5a704-111">Neste exemplo, \\\\*ComputerName*\\*InstanceName* seria alterado de \\\MB1\Instance1 para \\\MB2\Instance1.</span><span class="sxs-lookup"><span data-stu-id="5a704-111">In this example, the \\\\*ComputerName*\\*InstanceName* would be changed from \\\MB1\Instance1 to \\\MB2\Instance1.</span></span>  
  
 <span data-ttu-id="5a704-112">**Antes de começar**</span><span class="sxs-lookup"><span data-stu-id="5a704-112">**Before you begin**</span></span>  
  
 <span data-ttu-id="5a704-113">Antes de começar o processo de renomeação, revise as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="5a704-113">Before you begin the renaming process, review the following information:</span></span>  
  
-   <span data-ttu-id="5a704-114">Quando uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fizer parte de um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o processo de renomeação do computador difere de um computador que hospeda uma instância autônoma.</span><span class="sxs-lookup"><span data-stu-id="5a704-114">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the computer renaming process differs from a computer that hosts a stand-alone instance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5a704-115">não dá suporte à renomeação de computadores que estejam envolvidos em replicação, exceto quando você usar o envio de logs com a replicação.</span><span class="sxs-lookup"><span data-stu-id="5a704-115">does not support renaming computers that are involved in replication, except when you use log shipping with replication.</span></span> <span data-ttu-id="5a704-116">O computador secundário no envio de logs poderá ser renomeado se o computador primário for permanentemente perdido.</span><span class="sxs-lookup"><span data-stu-id="5a704-116">The secondary computer in log shipping can be renamed if the primary computer is permanently lost.</span></span> <span data-ttu-id="5a704-117">Para obter mais informações, veja [Replicação e envio de logs &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5a704-117">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
-   <span data-ttu-id="5a704-118">Quando você renomear um computador que está configurado para usar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] poderá não ficar disponível após a alteração do nome do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-118">When you rename a computer that is configured to use [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might not be available after the computer name change.</span></span> <span data-ttu-id="5a704-119">Para obter mais informações, veja [Renomear um computador de servidor de relatório](../../reporting-services/report-server/rename-a-report-server-computer.md).</span><span class="sxs-lookup"><span data-stu-id="5a704-119">For more information, see [Rename a Report Server Computer](../../reporting-services/report-server/rename-a-report-server-computer.md).</span></span>  
  
-   <span data-ttu-id="5a704-120">Quando você renomear um computador que está configurado para usar espelhamento de banco de dados, deverá desativar o espelhamento de banco de dados antes da operação de renomeação.</span><span class="sxs-lookup"><span data-stu-id="5a704-120">When you rename a computer that is configured to use database mirroring, you must turn off database mirroring before the renaming operation.</span></span> <span data-ttu-id="5a704-121">Em seguida, restabeleça o espelhamento de banco de dados com o novo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-121">Then, re-establish database mirroring with the new computer name.</span></span> <span data-ttu-id="5a704-122">Os metadados para o espelhamento de banco de dados não serão atualizados automaticamente para refletir o novo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-122">Metadata for database mirroring will not be updated automatically to reflect the new computer name.</span></span> <span data-ttu-id="5a704-123">Use as etapas a seguir para atualizar os metadados de sistema.</span><span class="sxs-lookup"><span data-stu-id="5a704-123">Use the following steps to update system metadata.</span></span>  
  
-   <span data-ttu-id="5a704-124">Os usuários que se conectem ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de um grupo do Windows que use uma referência embutida em código ao nome do computador talvez não consigam se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a704-124">Users who connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through a Windows group that uses a hard-coded reference to the computer name might not be able to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a704-125">Isso pode acontecer após a renomeação se o grupo do Windows especificar o nome antigo do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-125">This can occur after the rename if the Windows group specifies the old computer name.</span></span> <span data-ttu-id="5a704-126">Para assegurar que tais grupos do Windows tenham conectividade com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] após a operação de renomeação, atualize o grupo do Windows para especificar o novo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-126">To ensure that such Windows groups have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connectivity following the renaming operation, update the Windows group to specify the new computer name.</span></span>  
  
 <span data-ttu-id="5a704-127">Você poderá se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o novo nome do computador depois de reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a704-127">You can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the new computer name after you have restarted [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a704-128">Para garantir que @@SERVERNAME retorne o nome atualizado da instância do servidor local, execute manualmente o procedimento a seguir aplicável ao seu cenário.</span><span class="sxs-lookup"><span data-stu-id="5a704-128">To ensure that @@SERVERNAME returns the updated name of the local server instance, you should manually run the following procedure that applies to your scenario.</span></span> <span data-ttu-id="5a704-129">O procedimento usado depende de a atualização ser feita em um computador que hospeda uma instância padrão ou nomeada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a704-129">The procedure you use depends on whether you are updating a computer that hosts a default or named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-rename-a-computer-that-hosts-a-stand-alone-instance-of-ssnoversion"></a><span data-ttu-id="5a704-130">Para renomear um computador que hospeda uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a704-130">To rename a computer that hosts a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="5a704-131">Para um computador renomeado que hospeda uma instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], execute os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5a704-131">For a renamed computer that hosts a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name>;  
    GO  
    sp_addserver <new_name>, local;  
    GO  
    ```  
  
     <span data-ttu-id="5a704-132">Reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a704-132">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="5a704-133">Para um computador renomeado que hospeda uma instância nomeada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], execute os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5a704-133">For a renamed computer that hosts a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name\instancename>;  
    GO  
    sp_addserver <new_name\instancename>, local;  
    GO  
    ```  
  
     <span data-ttu-id="5a704-134">Reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a704-134">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="after-the-renaming-operation"></a><span data-ttu-id="5a704-135">Após a operação de renomeação</span><span class="sxs-lookup"><span data-stu-id="5a704-135">After the Renaming Operation</span></span>  
 <span data-ttu-id="5a704-136">Depois que um computador for renomeado, quaisquer conexões que usavam o nome antigo do computador deverão ser conectadas usando o novo nome.</span><span class="sxs-lookup"><span data-stu-id="5a704-136">After a computer has been renamed, any connections that used the old computer name must connect by using the new name.</span></span>  
  
#### <a name="to-verify-that-the-renaming-operation-has-completed-successfully"></a><span data-ttu-id="5a704-137">Para verificar se a operação renomeação foi concluída com êxito</span><span class="sxs-lookup"><span data-stu-id="5a704-137">To verify that the renaming operation has completed successfully</span></span>  
  
-   <span data-ttu-id="5a704-138">Selecione informações de @@SERVERNAME ou sys.servers.</span><span class="sxs-lookup"><span data-stu-id="5a704-138">Select information from either @@SERVERNAME or sys.servers.</span></span> <span data-ttu-id="5a704-139">A função @@SERVERNAME retornará o novo nome e a tabela sys.servers mostrará o novo nome.</span><span class="sxs-lookup"><span data-stu-id="5a704-139">The @@SERVERNAME function will return the new name, and the sys.servers table will show the new name.</span></span> <span data-ttu-id="5a704-140">O exemplo a seguir mostra o uso de @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="5a704-140">The following example shows the use of @@SERVERNAME.</span></span>  
  
    ```  
    SELECT @@SERVERNAME AS 'Server Name';  
    ```  
  
## <a name="additional-considerations"></a><span data-ttu-id="5a704-141">Considerações adicionais</span><span class="sxs-lookup"><span data-stu-id="5a704-141">Additional Considerations</span></span>  
 <span data-ttu-id="5a704-142">**Logons remotos** – Se o computador tiver logons remotos, a execução de **sp_dropserver** poderá gerar um erro semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="5a704-142">**Remote Logins** - If the computer has any remote logins, running **sp_dropserver** might generate an error similar to the following:</span></span>  
  
 `Server: Msg 15190, Level 16, State 1, Procedure sp_dropserver, Line 44 There are still remote logins for the server 'SERVER1'.`  
  
 <span data-ttu-id="5a704-143">Para resolver o erro, você deve descartar logons remotos para esse servidor.</span><span class="sxs-lookup"><span data-stu-id="5a704-143">To resolve the error, you must drop remote logins for this server.</span></span>  
  
#### <a name="to-drop-remote-logins"></a><span data-ttu-id="5a704-144">Para descartar logons remotos</span><span class="sxs-lookup"><span data-stu-id="5a704-144">To drop remote logins</span></span>  
  
-   <span data-ttu-id="5a704-145">Para uma instância padrão, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="5a704-145">For a default instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name;  
    GO  
    ```  
  
-   <span data-ttu-id="5a704-146">Para uma instância nomeada, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="5a704-146">For a named instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name\instancename;  
    GO  
    ```  
  
 <span data-ttu-id="5a704-147">**Configurações de servidor vinculado** – As configurações de servidor vinculado serão afetadas pela operação de renomeação de computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-147">**Linked Server Configurations** - Linked server configurations will be affected by the computer renaming operation.</span></span> <span data-ttu-id="5a704-148">Use `sp_addlinkedserver` ou `sp_setnetname` para atualizar referências de nome de computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-148">Use `sp_addlinkedserver` or `sp_setnetname` to update computer name references.</span></span> <span data-ttu-id="5a704-149">Para obter mais informações, veja [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) ou [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a704-149">For more information, see the [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) or [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span></span>  
  
 <span data-ttu-id="5a704-150">**Nomes de alias de cliente** – Os aliases de cliente que usam pipes nomeados serão afetados pela operação de renomeação do computador.</span><span class="sxs-lookup"><span data-stu-id="5a704-150">**Client Alias Names** - Client aliases that use named pipes will be affected by the computer renaming operation.</span></span> <span data-ttu-id="5a704-151">Por exemplo, se foi criado um alias "PROD_SRVR" para apontar para SRVR1 que usa o protocolo de pipes nomeados, o nome do pipe será `\\SRVR1\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="5a704-151">For example, if an alias "PROD_SRVR" was created to point to SRVR1 and uses the named pipes protocol, the pipe name will look like `\\SRVR1\pipe\sql\query`.</span></span> <span data-ttu-id="5a704-152">Depois que o computador for renomeado, o caminho do pipe nomeado deixará de ser válido.</span><span class="sxs-lookup"><span data-stu-id="5a704-152">After the computer is renamed, the path of the named pipe will no longer be valid and.</span></span> <span data-ttu-id="5a704-153">Para obter mais informações sobre pipes nomeados, veja o tópico [Criando uma cadeia de conexão válida usando pipes nomeados](https://go.microsoft.com/fwlink/?LinkId=111063).</span><span class="sxs-lookup"><span data-stu-id="5a704-153">For more information about named pipes, see the [Creating a Valid Connection String Using Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a704-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a704-154">See Also</span></span>  
 [<span data-ttu-id="5a704-155">Instalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5a704-155">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
