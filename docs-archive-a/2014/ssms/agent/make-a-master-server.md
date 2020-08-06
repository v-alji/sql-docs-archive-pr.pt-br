---
title: Criar um servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.msxwiz.complete.f1
- sql12.ag.msxwiz.target.f1
- sql12.ag.msxwiz.login.f1
- sql12.ag.msxwiz.cover.f1
- sql12.ag.msxwiz.operator.f1
helpviewer_keywords:
- master servers [SQL Server], creating
- wizards [SQL Server Management Studio], Master Server Wizard
- SQL Server Agent jobs, master servers
- Master Server Wizard
ms.assetid: 05739a73-1fdf-4d9d-92a6-70f328380322
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce8e7428aaf8ba459bcf6831988c61da3f192bac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573360"
---
# <a name="make-a-master-server"></a><span data-ttu-id="0182b-102">Make a Master Server</span><span class="sxs-lookup"><span data-stu-id="0182b-102">Make a Master Server</span></span>
  <span data-ttu-id="0182b-103">Este tópico descreve como criar um servidor mestre do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0182b-103">This topic describes how to make a master server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0182b-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0182b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0182b-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0182b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0182b-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="0182b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0182b-107">**Para criar um servidor mestre, usando:**</span><span class="sxs-lookup"><span data-stu-id="0182b-107">**To make a master server, using:**</span></span>  
  
     [<span data-ttu-id="0182b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0182b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0182b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0182b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0182b-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0182b-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0182b-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="0182b-111">Security</span></span>  
 <span data-ttu-id="0182b-112">Trabalhos distribuídos que possuem etapas associadas a um proxy são executados no contexto da conta proxy no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="0182b-113">Certifique-se de que as seguintes condições sejam atendidas, ou as etapas de trabalho associadas a um proxy não serão baixadas do servidor mestre para o destino:</span><span class="sxs-lookup"><span data-stu-id="0182b-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="0182b-114">A subchave do registro do servidor mestre **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) é definida como 1 (true).</span><span class="sxs-lookup"><span data-stu-id="0182b-114">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="0182b-115">Por padrão, essa subchave encontra-se definida como 0 (falso).</span><span class="sxs-lookup"><span data-stu-id="0182b-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="0182b-116">Existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="0182b-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="0182b-117">Se as etapas de trabalho que usam contas proxy falharem ao serem baixadas do servidor mestre para o servidor de destino, verifique a coluna **error_message** da tabela **sysdownloadlist** no banco de dados **msdb** quanto às seguintes mensagens de erro:</span><span class="sxs-lookup"><span data-stu-id="0182b-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="0182b-118">"A etapa do trabalho requer uma conta proxy. Entretanto, a verificação de proxy está desabilitada no servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="0182b-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="0182b-119">Para resolver este erro, defina a subchave **AllowDownloadedJobsToMatchProxyName** do Registro como 1.</span><span class="sxs-lookup"><span data-stu-id="0182b-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="0182b-120">"Proxy não localizado."</span><span class="sxs-lookup"><span data-stu-id="0182b-120">"Proxy not found."</span></span>  
  
     <span data-ttu-id="0182b-121">Para resolver este erro, certifique-se de que existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="0182b-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0182b-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="0182b-122">Permissions</span></span>  
 <span data-ttu-id="0182b-123">As permissões para executar esse procedimento para membros da função de servidor fixa `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="0182b-123">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0182b-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0182b-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="0182b-125">Para criar um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="0182b-125">To make a master server</span></span>  
  
1.  <span data-ttu-id="0182b-126">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="0182b-126">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0182b-127">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Tornar este um mestre**.</span><span class="sxs-lookup"><span data-stu-id="0182b-127">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Master**.</span></span> <span data-ttu-id="0182b-128">O **Assistente de Servidor Mestre** o guiará no processo de criação de um servidor mestre e de adição de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-128">The **Master Server Wizard** guides you through the process of making a master server and adding target servers.</span></span>  
  
3.  <span data-ttu-id="0182b-129">Na página **Operador de Servidor Mestre** , configure um operador para o servidor mestre. Para enviar notificações a operadores usando email ou pagers, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve estar configurado para enviar email.</span><span class="sxs-lookup"><span data-stu-id="0182b-129">From the **Master Server Operator** page, configure an operator for the master server To send notifications to operators by using e-mail or pagers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to send e-mail.</span></span> <span data-ttu-id="0182b-130">Para enviar notificações aos operadores usando **net send**, o serviço Messenger deve estar sendo executado no servidor no qual está o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0182b-130">To send notifications to operators by using **net send**, the Messenger service must be running on the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent resides.</span></span>  
  
     <span data-ttu-id="0182b-131">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="0182b-131">**E-mail address**</span></span>  
     <span data-ttu-id="0182b-132">Define o endereço de email para o operador.</span><span class="sxs-lookup"><span data-stu-id="0182b-132">Sets the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="0182b-133">**Endereço de pager**</span><span class="sxs-lookup"><span data-stu-id="0182b-133">**Pager address**</span></span>  
     <span data-ttu-id="0182b-134">Define o endereço de email de pager para o operador.</span><span class="sxs-lookup"><span data-stu-id="0182b-134">Sets the pager e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="0182b-135">**Endereço de net send**</span><span class="sxs-lookup"><span data-stu-id="0182b-135">**Net send address**</span></span>  
     <span data-ttu-id="0182b-136">Define o endereço de **net send** para o operador.</span><span class="sxs-lookup"><span data-stu-id="0182b-136">Sets the **net send** address for the operator.</span></span>  
  
4.  <span data-ttu-id="0182b-137">Na página **Servidor de Destino** , selecione servidores de destino para o servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="0182b-137">From the **Target Server** page, select target servers for the master server.</span></span>  
  
     <span data-ttu-id="0182b-138">**Servidores Registrados**</span><span class="sxs-lookup"><span data-stu-id="0182b-138">**Registered Servers**</span></span>  
     <span data-ttu-id="0182b-139">Lista os servidores registrados no Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] que já não são servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-139">Lists the servers registered in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] that are not already target servers.</span></span>  
  
     <span data-ttu-id="0182b-140">**Servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="0182b-140">**Target Servers**</span></span>  
     <span data-ttu-id="0182b-141">Lista os servidores que são servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-141">Lists the servers that are target servers.</span></span>  
  
     **>**  
     <span data-ttu-id="0182b-142">Mova o servidor selecionado para a lista de servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-142">Move the selected server to the target server list.</span></span>  
  
     **>>**  
     <span data-ttu-id="0182b-143">Mova todos os servidores para a lista de servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-143">Move all servers to the target server list.</span></span>  
  
     **<**  
     <span data-ttu-id="0182b-144">Remova o servidor selecionado da lista de servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-144">Remove the selected server from the target server list.</span></span>  
  
     **<<**  
     <span data-ttu-id="0182b-145">Remova todos os servidores da lista de servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0182b-145">Remove all servers from the target server list.</span></span>  
  
     <span data-ttu-id="0182b-146">**Adicionar Conexão**</span><span class="sxs-lookup"><span data-stu-id="0182b-146">**Add connection**</span></span>  
     <span data-ttu-id="0182b-147">Adicione um servidor à lista de servidor de destino sem registrar o servidor.</span><span class="sxs-lookup"><span data-stu-id="0182b-147">Add a server to the target server list without registering the server.</span></span>  
  
     <span data-ttu-id="0182b-148">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="0182b-148">**Connection**</span></span>  
     <span data-ttu-id="0182b-149">Altere as propriedades de conexão para o servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="0182b-149">Change the connection properties for the selected server.</span></span>  
  
5.  <span data-ttu-id="0182b-150">Na página **Credenciais de logon de servidor mestre** , para especificar se você deseja criar um novo logon para o servidor de destino e atribuir-lhe direitos ao servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="0182b-150">From the **Master Server Login Credentials** page to specify if you want to create a new login for the target server, if necessary, and assign it rights to the master server.</span></span>  
  
     <span data-ttu-id="0182b-151">**Criar um novo logon, se necessário, e atribuir-lhe direitos ao MSX**</span><span class="sxs-lookup"><span data-stu-id="0182b-151">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="0182b-152">Cria um novo logon no servidor de destino se o logon especificado ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="0182b-152">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0182b-153">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0182b-153">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="0182b-154">Para criar um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="0182b-154">To make a master server</span></span>  
  
1.  <span data-ttu-id="0182b-155">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0182b-155">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0182b-156">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="0182b-156">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0182b-157">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0182b-157">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0182b-158">Este exemplo inscreve o servidor atual no servidor mestre AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="0182b-158">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="0182b-159">O local do servidor atual é Prédio 21, Sala 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="0182b-159">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;   
GO;  
```  
  
 <span data-ttu-id="0182b-160">Para obter mais informações, consulte [sp_msx_enlist &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0182b-160">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0182b-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0182b-161">See Also</span></span>  
 <span data-ttu-id="0182b-162">[Criar um ambiente multisservidor](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="0182b-162">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 [<span data-ttu-id="0182b-163">Administração automatizada em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="0182b-163">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
