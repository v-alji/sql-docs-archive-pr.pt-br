---
title: Criar um servidor de destino | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.tsxwiz.msx.f1
- sql12.ag.tsxwiz.cover.f1
- sql12.ag.tsxwiz.credentials.f1
- sql12.ag.tsxwiz.complete.f1
helpviewer_keywords:
- Target Server Wizard
- SQL Server Agent jobs, target servers
- target servers [SQL Server], creating
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd60a19234d186bb0912978589fa60fd8e8a8c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678566"
---
# <a name="make-a-target-server"></a><span data-ttu-id="469fa-102">Criar um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="469fa-102">Make a Target Server</span></span>
  <span data-ttu-id="469fa-103">Este tópico descreve como criar um servidor de destino no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], ou SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="469fa-103">This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="469fa-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="469fa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="469fa-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="469fa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="469fa-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="469fa-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="469fa-107">**Para criar um servidor de destino, usando:**</span><span class="sxs-lookup"><span data-stu-id="469fa-107">**To make a target server, using:**</span></span>  
  
     [<span data-ttu-id="469fa-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="469fa-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="469fa-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="469fa-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="469fa-110">SMO</span><span class="sxs-lookup"><span data-stu-id="469fa-110">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="469fa-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="469fa-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="469fa-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="469fa-112">Security</span></span>  
 <span data-ttu-id="469fa-113">Trabalhos distribuídos que possuem etapas associadas a um proxy são executados no contexto da conta proxy no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="469fa-113">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="469fa-114">Certifique-se de que as seguintes condições sejam atendidas, ou as etapas de trabalho associadas a um proxy não serão baixadas do servidor mestre para o destino:</span><span class="sxs-lookup"><span data-stu-id="469fa-114">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="469fa-115">A subchave do registro do servidor mestre **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) é definida como 1 (true).</span><span class="sxs-lookup"><span data-stu-id="469fa-115">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="469fa-116">Por padrão, essa subchave encontra-se definida como 0 (falso).</span><span class="sxs-lookup"><span data-stu-id="469fa-116">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="469fa-117">Existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="469fa-117">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="469fa-118">Se as etapas de trabalho que usam contas proxy falharem ao serem baixadas do servidor mestre para o servidor de destino, verifique a coluna **error_message** da tabela **sysdownloadlist** no banco de dados **msdb** quanto às seguintes mensagens de erro:</span><span class="sxs-lookup"><span data-stu-id="469fa-118">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="469fa-119">"A etapa do trabalho requer uma conta proxy. Entretanto, a verificação de proxy está desabilitada no servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="469fa-119">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="469fa-120">Para resolver este erro, defina a subchave **AllowDownloadedJobsToMatchProxyName** do Registro como 1.</span><span class="sxs-lookup"><span data-stu-id="469fa-120">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="469fa-121">"Proxy não localizado."</span><span class="sxs-lookup"><span data-stu-id="469fa-121">"Proxy not found."</span></span>  
  
     <span data-ttu-id="469fa-122">Para resolver este erro, certifique-se de que existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="469fa-122">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="469fa-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="469fa-123">Permissions</span></span>  
 <span data-ttu-id="469fa-124">As permissões para executar esse procedimento para membros da função de servidor fixa `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="469fa-124">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="469fa-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="469fa-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="469fa-126">Para criar um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="469fa-126">To make a target server</span></span>  
  
1.  <span data-ttu-id="469fa-127">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="469fa-127">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="469fa-128">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Tornar este de destino**.</span><span class="sxs-lookup"><span data-stu-id="469fa-128">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**.</span></span> <span data-ttu-id="469fa-129">O **Assistente de Servidor de Destino** o guiará no processo de criação de um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="469fa-129">The **Target Server Wizard** guides you through the process of making a target server.</span></span>  
  
3.  <span data-ttu-id="469fa-130">Na página **Selecione um Servidor Mestre** , selecione o servidor mestre do qual esse servidor de destino receberá trabalhos.</span><span class="sxs-lookup"><span data-stu-id="469fa-130">From the **Select a Master Server** page, select the master server that this target server will receive jobs from.</span></span>  
  
     <span data-ttu-id="469fa-131">**Escolher Servidor**</span><span class="sxs-lookup"><span data-stu-id="469fa-131">**Pick Server**</span></span>  
     <span data-ttu-id="469fa-132">Conecte-se ao servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="469fa-132">Connect to the master server.</span></span>  
  
     <span data-ttu-id="469fa-133">**Descrição deste Servidor**</span><span class="sxs-lookup"><span data-stu-id="469fa-133">**Description of this server**</span></span>  
     <span data-ttu-id="469fa-134">Digite uma descrição para esse servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="469fa-134">Type a description for this target server.</span></span> <span data-ttu-id="469fa-135">O servidor de destino carrega essa descrição no servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="469fa-135">The target server uploads this description to the master server.</span></span>  
  
4.  <span data-ttu-id="469fa-136">Na página **Credenciais de logon de servidor mestre** , crie um logon novo no servidor de destino, se necessário.</span><span class="sxs-lookup"><span data-stu-id="469fa-136">From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.</span></span>  
  
     <span data-ttu-id="469fa-137">**Criar um novo logon, se necessário, e atribuir-lhe direitos ao MSX**</span><span class="sxs-lookup"><span data-stu-id="469fa-137">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="469fa-138">Cria um novo logon no servidor de destino se o logon especificado ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="469fa-138">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="469fa-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="469fa-139">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="469fa-140">Para criar um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="469fa-140">To make a target server</span></span>  
  
1.  <span data-ttu-id="469fa-141">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="469fa-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="469fa-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="469fa-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="469fa-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="469fa-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="469fa-144">Este exemplo inscreve o servidor atual no servidor mestre AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="469fa-144">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="469fa-145">O local do servidor atual é Prédio 21, Sala 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="469fa-145">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
     <span data-ttu-id="469fa-146">Para obter mais informações, consulte [sp_msx_enlist &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="469fa-146">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="469fa-147">Usando o SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="469fa-147">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469fa-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="469fa-148">See Also</span></span>  
 [<span data-ttu-id="469fa-149">Administração automatizada em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="469fa-149">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
