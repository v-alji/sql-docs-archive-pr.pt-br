---
title: Criar uma auditoria de servidor e uma especificação de auditoria de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLAUDIT.FILTER.F1
- sql12.swb.sqlaudit.srvaudit.general.f1
- sql12.swb.sqlaudit.general.f1
helpviewer_keywords:
- server audit [SQL Server]
- audits [SQL Server], specification
ms.assetid: 6624b1ab-7ec8-44ce-8292-397edf644394
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a648a975ae9f2c4139a8ebd584f6998f4d0fa1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680873"
---
# <a name="create-a-server-audit-and-server-audit-specification"></a><span data-ttu-id="64154-102">Criar uma auditoria de servidor e uma especificação de auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="64154-102">Create a Server Audit and Server Audit Specification</span></span>
  <span data-ttu-id="64154-103">Este tópico descreve como criar uma especificação de auditoria de servidor no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64154-103">This topic describes how to create a server audit and server audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="64154-104">*Auditar* uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] envolve eventos de rastreamento e de log que ocorrem no sistema.</span><span class="sxs-lookup"><span data-stu-id="64154-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="64154-105">O objeto *SQL Server Audit* coleta uma instância única de ações no nível do servidor e/ou do banco de dados e grupos de ações a serem monitoradas.</span><span class="sxs-lookup"><span data-stu-id="64154-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="64154-106">A auditoria está no nível de instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64154-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="64154-107">Você pode ter várias auditorias por instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64154-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="64154-108">O objeto *Especificação da Auditoria do Servidor* pertence a uma auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-108">The *Server Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="64154-109">É possível criar uma especificação de auditoria de servidor por auditoria, já que ambas são criadas no escopo da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64154-109">You can create one server audit specification per audit, because both are created at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance scope.</span></span> <span data-ttu-id="64154-110">Para obter mais informações, veja [Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="64154-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="64154-111">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="64154-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="64154-112">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="64154-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="64154-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="64154-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="64154-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="64154-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="64154-115">**Para criar uma auditoria de servidor e uma especificação de auditoria de servidor usando:**</span><span class="sxs-lookup"><span data-stu-id="64154-115">**To create a server audit and server audit specification, using:**</span></span>  
  
     [<span data-ttu-id="64154-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64154-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="64154-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64154-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64154-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="64154-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="64154-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="64154-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="64154-120">Deve existir uma auditoria antes da criação de uma especificação de auditoria de servidor para ela.</span><span class="sxs-lookup"><span data-stu-id="64154-120">An audit must exist before creating a server audit specification for it.</span></span> <span data-ttu-id="64154-121">Quando uma especificação de auditoria de servidor é criada, ela fica em um estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="64154-121">When a server audit specification is created, it is in a disabled state.</span></span>  
  
-   <span data-ttu-id="64154-122">A instrução CREATE SERVER AUDIT está no escopo de uma transação.</span><span class="sxs-lookup"><span data-stu-id="64154-122">The CREATE SERVER AUDIT statement is in a transaction's scope.</span></span> <span data-ttu-id="64154-123">Se a transação for revertida, a instrução também será revertida.</span><span class="sxs-lookup"><span data-stu-id="64154-123">If the transaction is rolled back, the statement is also rolled back.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64154-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="64154-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64154-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="64154-125">Permissions</span></span>  
  
-   <span data-ttu-id="64154-126">Para criar, alterar ou descartar uma auditoria de servidor, as entidades devem ter a permissão ALTER ANY SERVER AUDIT ou CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="64154-126">To create, alter, or drop a server audit, principals require the ALTER ANY SERVER AUDIT or the CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="64154-127">Os usuários que têm a permissão ALTER ANY SERVER AUDIT podem criar especificações de auditoria de servidor e associá-las a qualquer auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-127">Users with the ALTER ANY SERVER AUDIT permission can create server audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="64154-128">Depois que uma especificação de auditoria de servidor é criada, ela pode ser exibida por entidades que tenham a permissão CONTROL SERVER ou ALTER ANY SERVER AUDIT, com a conta sysadmin, ou por entidades que tenham acesso explícito à auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-128">After a server audit specification is created, it can be viewed by principals with the CONTROL SERVER or ALTER ANY SERVER AUDIT permissions, the sysadmin account, or principals having explicit access to the audit.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="64154-129">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64154-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="64154-130">Para criar uma auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="64154-130">To create a server audit</span></span>  
  
1.  <span data-ttu-id="64154-131">No Pesquisador de Objetos, expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="64154-131">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="64154-132">Clique com o botão direito do mouse na pasta **Auditorias** e selecione **Nova Auditoria...** .</span><span class="sxs-lookup"><span data-stu-id="64154-132">Right-click the **Audits** folder and select **New Audit...**.</span></span>  
  
     <span data-ttu-id="64154-133">As opções a seguir estão disponíveis na página **Geral** da caixa de diálogo **Criar Auditoria** :</span><span class="sxs-lookup"><span data-stu-id="64154-133">The following options are available on the **General** page of the **Create Audit** dialog box.</span></span>  
  
     <span data-ttu-id="64154-134">**Nome da auditoria**</span><span class="sxs-lookup"><span data-stu-id="64154-134">**Audit name**</span></span>  
     <span data-ttu-id="64154-135">O nome da auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-135">The name of the audit.</span></span> <span data-ttu-id="64154-136">Esse nome é gerado automaticamente quando você cria uma nova auditoria, mas é editável.</span><span class="sxs-lookup"><span data-stu-id="64154-136">This is generated automatically when you create a new audit but is editable.</span></span>  
  
     <span data-ttu-id="64154-137">**Atraso de fila (em milissegundos)**</span><span class="sxs-lookup"><span data-stu-id="64154-137">**Queue delay (in milliseconds)**</span></span>  
     <span data-ttu-id="64154-138">Especifica o período máximo, em milissegundos, que pode decorrer antes de as ações de auditorias serem forçadas a serem processadas.</span><span class="sxs-lookup"><span data-stu-id="64154-138">Specifies the amount of time in milliseconds that can elapse before audit actions are forced to be processed.</span></span>  <span data-ttu-id="64154-139">Um valor 0 indica entrega síncrona.</span><span class="sxs-lookup"><span data-stu-id="64154-139">A value of 0 indicates synchronous delivery.</span></span> <span data-ttu-id="64154-140">O valor padrão mínimo é **1000** (1 segundo).</span><span class="sxs-lookup"><span data-stu-id="64154-140">The default minimum value is **1000** (1 second).</span></span> <span data-ttu-id="64154-141">O máximo é 2.147.483.647 (2.147.483.647 segundos ou 24 dias, 20 horas, 31 minutos, 23.647 segundos).</span><span class="sxs-lookup"><span data-stu-id="64154-141">The maximum is 2,147,483,647 (2,147,483.647 seconds or 24 days, 20 hours, 31 minutes, 23.647 seconds).</span></span>  
  
     <span data-ttu-id="64154-142">**Em caso de falha de log de auditoria:**</span><span class="sxs-lookup"><span data-stu-id="64154-142">**On Audit Log Failure:**</span></span>  
     <span data-ttu-id="64154-143">**Continuar**</span><span class="sxs-lookup"><span data-stu-id="64154-143">**Continue**</span></span>  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="64154-144">As operações continuam.</span><span class="sxs-lookup"><span data-stu-id="64154-144">operations continue.</span></span> <span data-ttu-id="64154-145">Os registros de auditoria não são retidos.</span><span class="sxs-lookup"><span data-stu-id="64154-145">Audit records are not retained.</span></span> <span data-ttu-id="64154-146">A auditoria retomará tentando registrar eventos em log e será retomada se a condição de falha for resolvida.</span><span class="sxs-lookup"><span data-stu-id="64154-146">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="64154-147">A seleção da opção **Continuar** pode permitir atividade não auditada, o que pode violar suas políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="64154-147">Selecting the **Continue** option can allow unaudited activity which could violate your security policies.</span></span> <span data-ttu-id="64154-148">Selecionar essa opção ao continuar a operação do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] é mais importante do que manter uma auditoria completa.</span><span class="sxs-lookup"><span data-stu-id="64154-148">Select this option when continuing operation of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] is more important than maintaining a complete audit.</span></span> <span data-ttu-id="64154-149">Essa é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="64154-149">This is the default selection.</span></span>  
  
     <span data-ttu-id="64154-150">**Desligar servidor**</span><span class="sxs-lookup"><span data-stu-id="64154-150">**Shut down server**</span></span>  
     <span data-ttu-id="64154-151">Força o desligamento de um servidor quando a instância do servidor que grava no destino não puder gravar dados no destino de auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-151">Forces a server shut down when the server instance writing to the target cannot write data to the audit target.</span></span> <span data-ttu-id="64154-152">O logon que emite isso deve ter a permissão `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="64154-152">The login issuing this must have the `SHUTDOWN` permission.</span></span> <span data-ttu-id="64154-153">Se o logon não tiver essa permissão, essa função apresentará falha e será exibida uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="64154-153">If the logon does not have this permission, this function will fail and an error message will be raised.</span></span> <span data-ttu-id="64154-154">Não ocorre nenhum evento auditado.</span><span class="sxs-lookup"><span data-stu-id="64154-154">No audited events occur.</span></span> <span data-ttu-id="64154-155">Selecione essa opção quando uma falha de auditoria puder comprometer a segurança ou a integridade do sistema.</span><span class="sxs-lookup"><span data-stu-id="64154-155">Select this option when an audit failure could compromise the security or integrity of the system.</span></span>  
  
     <span data-ttu-id="64154-156">**Operação com falha**</span><span class="sxs-lookup"><span data-stu-id="64154-156">**Fail operation**</span></span>  
     <span data-ttu-id="64154-157">Em casos onde o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit não pode gravar no log de auditoria, essa opção provocará falha nas ações de banco de dados se elas forem, de outra forma, provocar eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="64154-157">In cases where the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit cannot write to the audit log this option causes database actions to fail if they would otherwise cause audited events.</span></span> <span data-ttu-id="64154-158">Não ocorre nenhum evento auditado.</span><span class="sxs-lookup"><span data-stu-id="64154-158">No audited events occur.</span></span> <span data-ttu-id="64154-159">As ações que não provocam eventos auditados podem continuar.</span><span class="sxs-lookup"><span data-stu-id="64154-159">Actions which do not cause audited events can continue.</span></span> <span data-ttu-id="64154-160">A auditoria retomará tentando registrar eventos em log e será retomada se a condição de falha for resolvida.</span><span class="sxs-lookup"><span data-stu-id="64154-160">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="64154-161">Selecione essa opção quando manter uma auditoria completa for mais importante do que o acesso total ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64154-161">Select this option when maintaining a complete audit is more important than full access to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="64154-162">Quando a auditoria estiver em um estado com falha, a Conexão de administrador dedicada poderá continuar executando eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="64154-162">When the audit is in a failed state, the Dedicated Administrator Connection can continue to perform audited events.</span></span>  
  
     <span data-ttu-id="64154-163">Lista**Destino da auditoria**</span><span class="sxs-lookup"><span data-stu-id="64154-163">**Audit destination** list</span></span>  
     <span data-ttu-id="64154-164">Especifica o destino para dados de auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-164">Specifies the target for auditing data.</span></span> <span data-ttu-id="64154-165">As opções disponíveis são um arquivo binário, o log de aplicativos do Windows ou o log de segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="64154-165">The available options are a binary file, the Windows Application log, or the Windows Security log.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="64154-166">não poderá gravar no log de segurança do Windows se não forem definidas configurações adicionais no Windows.</span><span class="sxs-lookup"><span data-stu-id="64154-166">cannot write to the Windows Security log without configuring additional settings in Windows.</span></span> <span data-ttu-id="64154-167">Para obter mais informações, veja [Gravar eventos de auditoria do SQL Server no log de segurança](write-sql-server-audit-events-to-the-security-log.md).</span><span class="sxs-lookup"><span data-stu-id="64154-167">For more information, see [Write SQL Server Audit Events to the Security Log](write-sql-server-audit-events-to-the-security-log.md).</span></span>  
  
     <span data-ttu-id="64154-168">**Caminho do arquivo**</span><span class="sxs-lookup"><span data-stu-id="64154-168">**File path**</span></span>  
     <span data-ttu-id="64154-169">Especifica a localização da pasta em que os dados de auditoria serão gravados quando o **Destino da auditoria** for um arquivo.</span><span class="sxs-lookup"><span data-stu-id="64154-169">Specifies the location of the folder where audit data is written when the **Audit destination** is a file.</span></span>  
  
     <span data-ttu-id="64154-170">**Reticências (...)**</span><span class="sxs-lookup"><span data-stu-id="64154-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="64154-171">Abre a caixa de diálogo **Localizar pasta-**_server_name_ para especificar um caminho de arquivo ou criar uma pasta na qual o arquivo de auditoria é gravado.</span><span class="sxs-lookup"><span data-stu-id="64154-171">Opens the **Locate Folder -**_server_name_ dialog box to specify a file path or create a folder where the audit file is written.</span></span>  
  
     <span data-ttu-id="64154-172">**Audite o limite máximo de arquivo:**</span><span class="sxs-lookup"><span data-stu-id="64154-172">**Audit File Maximum Limit:**</span></span>  
     <span data-ttu-id="64154-173">**Máximo de arquivos de substituição**</span><span class="sxs-lookup"><span data-stu-id="64154-173">**Maximum rollover files**</span></span>  
     <span data-ttu-id="64154-174">Especifica que, quando o número máximo de arquivos de auditoria é atingido, os arquivos de auditoria mais antigos são substituídos por novo conteúdo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="64154-174">Specifies that, when the maximum number of audit files is reached, the oldest audit files are overwritten by new file content.</span></span>  
  
     <span data-ttu-id="64154-175">**Máximo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="64154-175">**Maximum files**</span></span>  
     <span data-ttu-id="64154-176">Especifica que, quando o número máximo de arquivos de auditoria for atingido, haverá falha com um erro em qualquer ação que provoque a geração de eventos de auditoria adicionais.</span><span class="sxs-lookup"><span data-stu-id="64154-176">Specifies that, when the maximum number of audit files is reached, any action that causes additional audit events to be generated will fail with an error.</span></span>  
  
     <span data-ttu-id="64154-177">Caixa de seleção**Ilimitado**</span><span class="sxs-lookup"><span data-stu-id="64154-177">**Unlimited** check box</span></span>  
     <span data-ttu-id="64154-178">Quando a caixa de seleção **Ilimitado** sob **Máximo de arquivos de substituição** for marcada, não haverá nenhum limite imposto para o número de arquivos de auditoria a serem criados.</span><span class="sxs-lookup"><span data-stu-id="64154-178">When the **Unlimited** check box under **Maximum rollover files** is selected, there is no limit imposed on the number of audit files that will be created.</span></span> <span data-ttu-id="64154-179">A caixa de seleção **Ilimitado** é marcada por padrão e se aplica às seleções **Máximo de arquivos de substituição** e **Máximo de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="64154-179">The **Unlimited** check box is selected by default and applies to both the **Maximum rollover files** and **Maximum files** selections.</span></span>  
  
     <span data-ttu-id="64154-180">Caixa**Número de arquivos**</span><span class="sxs-lookup"><span data-stu-id="64154-180">**Number of files** box</span></span>  
     <span data-ttu-id="64154-181">Especifica o número de arquivos de auditoria a serem criados, até 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="64154-181">Specifies the number of audit files to be created, up to 2,147,483,647.</span></span> <span data-ttu-id="64154-182">Essa opção estará disponível somente se **Ilimitado** estiver desmarcado.</span><span class="sxs-lookup"><span data-stu-id="64154-182">This option is only available if **Unlimited** is unchecked.</span></span>  
  
     <span data-ttu-id="64154-183">**Tamanho máximo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="64154-183">**Maximum file size**</span></span>  
     <span data-ttu-id="64154-184">Especifica o tamanho máximo para um arquivo de auditoria em megabytes (MB), gigabytes (GB) ou terabytes (TB).</span><span class="sxs-lookup"><span data-stu-id="64154-184">Specifies the maximum size for an audit file in either megabytes (MB), gigabytes (GB), or terabytes (TB).</span></span> <span data-ttu-id="64154-185">Você pode especificar entre 1024 MB e 2.147.483.647 TB.</span><span class="sxs-lookup"><span data-stu-id="64154-185">You can specify between 1024 MB and 2,147,483,647 TB.</span></span> <span data-ttu-id="64154-186">Marcar a caixa de seleção **Ilimitado** não estabelece um limite para o tamanho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="64154-186">Selecting the **Unlimited** check box does not place a limit on the size of the file.</span></span> <span data-ttu-id="64154-187">A especificação de um valor abaixo de 1024 MB falhará, gerando um erro.</span><span class="sxs-lookup"><span data-stu-id="64154-187">Specifying a value lower than 1024 MB will fail, returning an error.</span></span> <span data-ttu-id="64154-188">A caixa de seleção **Ilimitada** fica marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="64154-188">The **Unlimited** check box is selected by default.</span></span>  
  
     <span data-ttu-id="64154-189">Caixa de seleção**Reservar espaço em disco**</span><span class="sxs-lookup"><span data-stu-id="64154-189">**Reserve disk space** check box</span></span>  
     <span data-ttu-id="64154-190">Especifica o espaço pré-alocado no disco que é igual ao tamanho de arquivo máximo especificado.</span><span class="sxs-lookup"><span data-stu-id="64154-190">Specifies that space is pre-allocated on the disk equal to the specified maximum file size.</span></span> <span data-ttu-id="64154-191">Essa configuração pode ser usada se a caixa de seleção **Ilimitada** sob **Tamanho máximo do arquivo** não for marcada.</span><span class="sxs-lookup"><span data-stu-id="64154-191">This setting can only be used if the **Unlimited** check box under **Maximum file size** is not selected.</span></span> <span data-ttu-id="64154-192">Essa caixa de seleção não é marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="64154-192">This check box is not selected by default.</span></span>  
  
3.  <span data-ttu-id="64154-193">Opcionalmente, na página **Filtro** , insira um predicado ou a cláusula `WHERE` , para a auditoria de servidor para especificar opções adicionais não disponíveis da página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="64154-193">Optionally, on the **Filter** page, enter a predicate, or `WHERE` clause, to the server audit to specify additional options not available from the **General** page.</span></span> <span data-ttu-id="64154-194">Inclua o predicado em parênteses; por exemplo: `(object_name = 'EmployeesTable')`.</span><span class="sxs-lookup"><span data-stu-id="64154-194">Enclose the predicate in parentheses; for example: `(object_name = 'EmployeesTable')`.</span></span>  
  
4.  <span data-ttu-id="64154-195">Quando terminar de selecionar as opções, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="64154-195">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="64154-196">Para criar uma especificação de auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="64154-196">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="64154-197">No Pesquisador de Objetos, clique no sinal de mais para expandir a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="64154-197">In Object Explorer, click the plus sign to expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="64154-198">Clique com o botão direito do mouse na pasta **Especificações de Auditoria de Servidor** e selecione **Nova Especificação de Auditoria de Servidor...** .</span><span class="sxs-lookup"><span data-stu-id="64154-198">Right-click the **Server Audit Specifications** folder and select **New Server Audit Specification...**.</span></span>  
  
     <span data-ttu-id="64154-199">As opções a seguir estão disponíveis na caixa de diálogo **Criar Especificação de Auditoria de Servidor** .</span><span class="sxs-lookup"><span data-stu-id="64154-199">The following options are available on the **Create Server Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="64154-200">**Nome**</span><span class="sxs-lookup"><span data-stu-id="64154-200">**Name**</span></span>  
     <span data-ttu-id="64154-201">O nome da especificação de auditoria de servidor.</span><span class="sxs-lookup"><span data-stu-id="64154-201">The name of the server audit specification.</span></span> <span data-ttu-id="64154-202">Esse nome é gerado automaticamente quando você cria uma nova especificação de auditoria de servidor, mas é editável.</span><span class="sxs-lookup"><span data-stu-id="64154-202">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="64154-203">**Auditoria**</span><span class="sxs-lookup"><span data-stu-id="64154-203">**Audit**</span></span>  
     <span data-ttu-id="64154-204">O nome de uma auditoria de servidor existente.</span><span class="sxs-lookup"><span data-stu-id="64154-204">The name of an existing server audit.</span></span> <span data-ttu-id="64154-205">Digite o nome da auditoria ou selecione-o na lista.</span><span class="sxs-lookup"><span data-stu-id="64154-205">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="64154-206">**Tipo de Ação de Auditoria**</span><span class="sxs-lookup"><span data-stu-id="64154-206">**Audit Action Type**</span></span>  
     <span data-ttu-id="64154-207">Especifica os grupos de ação de auditoria no nível de servidor e as ações de auditoria a capturar.</span><span class="sxs-lookup"><span data-stu-id="64154-207">Specifies the server-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="64154-208">Para a lista de grupos de ação de auditoria no nível de servidor, ações de auditoria e uma descrição dos eventos que eles contêm, veja [Ações e grupos de ações de auditoria do SQL Server](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="64154-208">For the list of server-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="64154-209">**Esquema de Objeto**</span><span class="sxs-lookup"><span data-stu-id="64154-209">**Object Schema**</span></span>  
     <span data-ttu-id="64154-210">Exibe o esquema para **Object Name**especificado.</span><span class="sxs-lookup"><span data-stu-id="64154-210">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="64154-211">**Object Name**</span><span class="sxs-lookup"><span data-stu-id="64154-211">**Object Name**</span></span>  
     <span data-ttu-id="64154-212">Nome do objeto a ser auditado.</span><span class="sxs-lookup"><span data-stu-id="64154-212">The name of the object to audit.</span></span> <span data-ttu-id="64154-213">Isso só está disponível para ações de auditoria e não se aplica a grupos de auditoria.</span><span class="sxs-lookup"><span data-stu-id="64154-213">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="64154-214">**Reticências (...)**</span><span class="sxs-lookup"><span data-stu-id="64154-214">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="64154-215">Abre a caixa de diálogo **Selecionar Objetos** para procurar e selecionar um objeto disponível, com base no **Tipo de Ação de Auditoria**especificado.</span><span class="sxs-lookup"><span data-stu-id="64154-215">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="64154-216">**Nome Principal**</span><span class="sxs-lookup"><span data-stu-id="64154-216">**Principal Name**</span></span>  
     <span data-ttu-id="64154-217">A conta para filtrar a auditoria para o objeto que está sendo auditado.</span><span class="sxs-lookup"><span data-stu-id="64154-217">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="64154-218">**Reticências (...)**</span><span class="sxs-lookup"><span data-stu-id="64154-218">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="64154-219">Abre a caixa de diálogo **Selecionar Objetos** para procurar e selecionar um objeto disponível, com base no **Nome do Objeto**especificado.</span><span class="sxs-lookup"><span data-stu-id="64154-219">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
3.  <span data-ttu-id="64154-220">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="64154-220">When you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="64154-221">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64154-221">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="64154-222">Para criar uma auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="64154-222">To create a server audit</span></span>  
  
1.  <span data-ttu-id="64154-223">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64154-223">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="64154-224">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="64154-224">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="64154-225">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="64154-225">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a server audit called "HIPAA_Audit" with a binary file as the target and no options.  
    CREATE SERVER AUDIT HIPAA_Audit  
        TO FILE ( FILEPATH ='\\SQLPROD_1\Audit\' );  
    ```  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="64154-226">Para criar uma especificação de auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="64154-226">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="64154-227">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64154-227">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="64154-228">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="64154-228">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="64154-229">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="64154-229">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    /*Creates a server audit specification called "HIPAA_Audit_Specification" that audits failed logins for the SQL Server audit "HIPAA_Audit" created above.  
    */  
  
    CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
    FOR SERVER AUDIT HIPAA_Audit  
        ADD (FAILED_LOGIN_GROUP);  
    GO  
    -- Enables the audit.   
  
    ALTER SERVER AUDIT HIPAA_Audit  
    WITH (STATE = ON);  
    GO  
    ```  
  
 <span data-ttu-id="64154-230">Para obter mais informações, veja [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) e [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64154-230">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span></span>  
  
  
