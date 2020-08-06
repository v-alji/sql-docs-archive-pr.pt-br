---
title: Segurança do coletor de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- security [data collector]
- data collector [SQL Server], security
ms.assetid: e75d6975-641e-440a-a642-cb39a583359a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c89f1658f6ae1b5bd79de96f20222b0b19529df2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570712"
---
# <a name="data-collector-security"></a><span data-ttu-id="bb3e9-102">Segurança do coletor de dados</span><span class="sxs-lookup"><span data-stu-id="bb3e9-102">Data Collector Security</span></span>
  <span data-ttu-id="bb3e9-103">O coletor de dados usa o modelo de segurança baseado em função implementado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-103">The data collector uses the role-based security model implemented by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="bb3e9-104">Esse modelo permite que o administrador do banco de dados execute várias tarefas de coletor de dados em um contexto de segurança que tem apenas as permissões exigidas para executar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-104">This model lets the database administrator run the various data collector tasks in a security context that has only the permissions required to perform that task.</span></span> <span data-ttu-id="bb3e9-105">Essa abordagem também é usada para operações que envolvem tabelas internas que só podem ser acessadas usando um procedimento armazenado ou exibição.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-105">This approach is also used for operations involving internal tables, which can only be accessed by using a stored procedure or view.</span></span> <span data-ttu-id="bb3e9-106">Nenhuma permissão é concedida a tabelas internas.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-106">No permissions are granted to internal tables.</span></span> <span data-ttu-id="bb3e9-107">Em vez disso, as permissões são verificadas no usuário do procedimento armazenado ou na exibição usada para acessar a tabela.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-107">Instead, permissions are checked on the user of the stored procedure or view that is used to access a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bb3e9-108">Outro aspecto fundamental desse modelo de segurança são as permissões concêntricas.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-108">Another key aspect of this security model is concentric permissions.</span></span> <span data-ttu-id="bb3e9-109">Nas permissões concêntricas, funções mais privilegiadas herdam as permissões de funções menos privilegiadas nos objetos (incluindo alertas, operadores, tarefas, agendas e proxy).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-109">Under concentric permissions, more privileged roles inherit the permissions of less privileged roles on objects (including alerts, operators, jobs, schedules, and proxies).</span></span> <span data-ttu-id="bb3e9-110">Para obter mais informações, consulte [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-110">For more information, see [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="bb3e9-111">As próximas seções descrevem a segurança da coleta de dados em geral, assim como as funções que você deve conceder aos usuários para que eles possam configurar e usar o coletor de dados e executar tarefas associadas ao data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-111">The following sections describe data collection security in general, as well as the roles you must grant to users so they can configure and use the data collector, and carry out tasks associated with the management data warehouse.</span></span>  
  
## <a name="general-security"></a><span data-ttu-id="bb3e9-112">Segurança em geral</span><span class="sxs-lookup"><span data-stu-id="bb3e9-112">General Security</span></span>  
 <span data-ttu-id="bb3e9-113">O coletor de dados é instalado de acordo com os padrões documentados especificados para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb3e9-113">The data collector is installed according to the documented standards specified for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
### <a name="network-security"></a><span data-ttu-id="bb3e9-114">Segurança de rede</span><span class="sxs-lookup"><span data-stu-id="bb3e9-114">Network Security</span></span>  
 <span data-ttu-id="bb3e9-115">Informações confidenciais podem ser passadas entre instâncias de destino, a instância relacional associada ao servidor de configuração, os conjuntos de coleta em execução e o servidor que hospeda o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-115">Sensitive information can be passed between target instances, the relational instance associated with the configuration server, the collection sets that are running, and the server that hosts the management data warehouse.</span></span>  
  
 <span data-ttu-id="bb3e9-116">Para proteger qualquer dado transferido em uma rede, são implementados mecanismos de segurança padrão, como criptografia de protocolo para [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb3e9-116">To protect any data that is transferred over a network, the standard security mechanisms are implemented, such as protocol encryption for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-data-collector"></a><span data-ttu-id="bb3e9-117">Permissões para configurar e usar o coletor de dados</span><span class="sxs-lookup"><span data-stu-id="bb3e9-117">Permissions for Configuring and Using the Data Collector</span></span>  
 <span data-ttu-id="bb3e9-118">Dependendo da tarefa, os usuários devem ser membros de uma ou mais das funções de banco de dados fixas fornecidas para o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-118">Depending on the task, users must be members of one or more of the fixed database roles provided for the data collector.</span></span> <span data-ttu-id="bb3e9-119">Em ordem de acesso mais privilegiado para acesso menos privilegiado, as funções são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-119">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   `dc_admin`  
  
-   <span data-ttu-id="bb3e9-120">**dc_operator**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-120">**dc_operator**</span></span>  
  
-   <span data-ttu-id="bb3e9-121">**dc_proxy**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-121">**dc_proxy**</span></span>  
  
 <span data-ttu-id="bb3e9-122">Essas funções são armazenadas no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-122">These roles are stored in the msdb database.</span></span> <span data-ttu-id="bb3e9-123">Por padrão, nenhum usuário é membro dessas funções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-123">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="bb3e9-124">A associação do usuário a elas deve ser explicitamente concedida.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-124">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="bb3e9-125">Os usuários que são membros da `sysadmin` função de servidor fixa têm acesso completo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos de agente e exibições do coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-125">Users who are members of the `sysadmin` fixed server role have full access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent objects and data collector views.</span></span> <span data-ttu-id="bb3e9-126">Porém, eles precisam ser adicionados explicitamente à funções de coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-126">However, they need to be explicitly added to data collector roles.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bb3e9-127">Os membros das funções db_ssisadmin e dc_admin podem elevar seus privilégios para sysadmin.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-127">Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="bb3e9-128">Essa elevação de privilégios pode ocorrer porque essas funções podem modificar os pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e os pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] podem ser executados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o contexto de segurança sysadmin do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="bb3e9-129">Para se proteger contra essa elevação de privilégios ao executar planos de manutenção, conjuntos de coletas de dados e outros pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configure os trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que executam pacotes para usar uma conta proxy com privilégios limitados ou apenas adicione membros sysadmin às funções db_ssisadmin e dc_admin.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>  
  
### <a name="dc_admin-role"></a><span data-ttu-id="bb3e9-130">Função dc_admin</span><span class="sxs-lookup"><span data-stu-id="bb3e9-130">dc_admin Role</span></span>  
 <span data-ttu-id="bb3e9-131">Os usuários atribuídos à `dc_admin` função têm acesso de administrador completo (criar, ler, atualizar e excluir) à configuração do coletor de dados em uma instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-131">Users assigned to the `dc_admin` role have full administrator access (Create, Read, Update, and Delete) to the data collector configuration on a server instance.</span></span> <span data-ttu-id="bb3e9-132">Membros dessa função podem executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-132">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bb3e9-133">Definir propriedades de nível de coletor.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-133">Set collector-level properties.</span></span>  
  
-   <span data-ttu-id="bb3e9-134">Adicionar novos conjuntos de coleta.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-134">Add new collection sets.</span></span>  
  
-   <span data-ttu-id="bb3e9-135">Instalar novos tipos de coleta.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-135">Install new collection types.</span></span>  
  
-   <span data-ttu-id="bb3e9-136">Execute todas as operações permitidas à função **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="bb3e9-136">Perform all the operations permitted to the **dc_operator** role.</span></span>  
  
 <span data-ttu-id="bb3e9-137">A `dc_admin` função é um membro das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-137">The `dc_admin` role is a member of the following roles:</span></span>  
  
-   <span data-ttu-id="bb3e9-138">**SQLAgentUserRole**.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-138">**SQLAgentUserRole**.</span></span> <span data-ttu-id="bb3e9-139">Essa função é necessária para criar agendas e executar tarefas.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-139">This role is required to create schedules and run jobs.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb3e9-140">Os proxies criados para o coletor de dados devem conceder acesso ao `dc_admin` para criá-los e usá-los em qualquer etapa de trabalho que exija um proxy.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-140">Proxies created for the data collector must grant access to `dc_admin` to create them and use them in any job steps that require a proxy.</span></span>  
  
-   <span data-ttu-id="bb3e9-141">**dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-141">**dc_operator**.</span></span> <span data-ttu-id="bb3e9-142">Os membros `dc_admin` herdam as permissões dadas a **dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-142">Members of `dc_admin` inherit the permissions given to **dc_operator**.</span></span>  
  
### <a name="dc_operator-role"></a><span data-ttu-id="bb3e9-143">Função dc_operator</span><span class="sxs-lookup"><span data-stu-id="bb3e9-143">dc_operator Role</span></span>  
 <span data-ttu-id="bb3e9-144">Membros da função **dc_operator** têm acesso de Leitura e Atualização.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-144">Members of the **dc_operator** role have Read and Update access.</span></span> <span data-ttu-id="bb3e9-145">Essa função suporta tarefas de operações relacionadas com a execução e configuração de conjuntos de coleta.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-145">This role supports operations tasks related to running and configuring collection sets.</span></span> <span data-ttu-id="bb3e9-146">Membros dessa função podem executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-146">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bb3e9-147">Iniciar ou parar um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-147">Start or stop a collection set.</span></span>  
  
-   <span data-ttu-id="bb3e9-148">Enumerar conjuntos de coleta existentes.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-148">Enumerate existing collection sets.</span></span>  
  
-   <span data-ttu-id="bb3e9-149">Exibir informações detalhadas (por exemplo, itens e frequência de coleta) associadas a um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-149">View the detailed information (for example, collection items, and collection frequency) associated with a collection set.</span></span>  
  
-   <span data-ttu-id="bb3e9-150">Alterar a frequência de carregamento de conjuntos de coleta existentes.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-150">Change the upload frequency for existing collection sets.</span></span>  
  
-   <span data-ttu-id="bb3e9-151">Alterar a frequência de coleta de itens de coleta que fazem parte de um conjunto de coleta existente.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-151">Change the collection frequency for collection items that are part of an existing collection set.</span></span>  
  
 <span data-ttu-id="bb3e9-152">A função **dc_operator** é membro das funções a seguir que são necessárias para enumerar e exibir pacotes do coletor de dados:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-152">The **dc_operator** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="bb3e9-153">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-153">**db_ssisltduser**</span></span>  
  
-   <span data-ttu-id="bb3e9-154">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-154">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="bb3e9-155">Para obter mais informações, veja [Funções do Integration Services &#40;Serviço do SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-155">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
### <a name="dc_proxy-role"></a><span data-ttu-id="bb3e9-156">Função dc_proxy</span><span class="sxs-lookup"><span data-stu-id="bb3e9-156">dc_proxy Role</span></span>  
 <span data-ttu-id="bb3e9-157">Membros da função **dc_proxy** têm acesso de Leitura aos conjuntos de coleta do coletor de dados e às propriedades de nível de coletor.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-157">Members of the **dc_proxy** role have Read access to data collector collection sets and collector-level properties.</span></span> <span data-ttu-id="bb3e9-158">Os membros dessa função também podem executar tarefas de sua propriedade e criar etapas de tarefa executadas como uma conta proxy existente.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-158">Members of this role can also execute jobs that they own and create job steps that run as an existing proxy account.</span></span>  
  
 <span data-ttu-id="bb3e9-159">Membros dessa função podem executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-159">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bb3e9-160">Exibir informações de configuração do conjunto de coleta (por exemplo, parâmetros de entrada de itens de coleta e a frequência de coleta desses itens).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-160">View collection set configuration information (for example, input parameters for collection items, and the collection frequency for these items).</span></span>  
  
-   <span data-ttu-id="bb3e9-161">Obter informações internas criptografadas que só podem ser acessadas por um procedimento armazenado assinado (por exemplo, informações de conexão de data warehouse usadas para carregamento de dados).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-161">Obtain internal encrypted information that can only be accessed by a signed stored procedure (for example, data warehouse connection information used for data uploads).</span></span>  
  
-   <span data-ttu-id="bb3e9-162">Registrar em log eventos de tempo de execução do conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-162">Log collection-set run-time events.</span></span>  
  
 <span data-ttu-id="bb3e9-163">A função **dc_proxy** é membro das seguintes funções que são necessárias para enumerar e exibir pacotes do coletor de dados:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-163">The **dc_proxy** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="bb3e9-164">**db_ssisltduser**.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-164">**db_ssisltduser**.</span></span>  
  
-   <span data-ttu-id="bb3e9-165">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-165">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="bb3e9-166">Para obter mais informações, veja [Funções do Integration Services &#40;Serviço do SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-166">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-management-data-warehouse"></a><span data-ttu-id="bb3e9-167">Permissões para configurar e usar o Data Warehouse de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="bb3e9-167">Permissions for Configuring and Using the Management Data Warehouse</span></span>  
 <span data-ttu-id="bb3e9-168">Dependendo da tarefa, os usuários devem ser membros de uma ou mais das funções de banco de dados fixas fornecidas para acessar o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-168">Depending on the task, users must be members of one or more of the fixed database roles provided for accessing the management data warehouse.</span></span> <span data-ttu-id="bb3e9-169">Em ordem de acesso mais privilegiado para acesso menos privilegiado, as funções são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-169">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   <span data-ttu-id="bb3e9-170">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-170">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="bb3e9-171">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-171">**mdw_writer**</span></span>  
  
-   <span data-ttu-id="bb3e9-172">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-172">**mdw_reader**</span></span>  
  
 <span data-ttu-id="bb3e9-173">Essas funções são armazenadas no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-173">These roles are stored in the msdb database.</span></span> <span data-ttu-id="bb3e9-174">Por padrão, nenhum usuário é membro dessas funções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-174">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="bb3e9-175">A associação do usuário a elas deve ser explicitamente concedida.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-175">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="bb3e9-176">Os usuários que são membros da `sysadmin` função de servidor fixa têm acesso completo às exibições do coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-176">Users who are members of the `sysadmin` fixed server role have full access to data collector views.</span></span> <span data-ttu-id="bb3e9-177">Porém, eles precisam ser adicionados explicitamente à funções do banco de dados para executar outras operações.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-177">However, they need to be explicitly added to database roles to perform other operations.</span></span>  
  
### <a name="mdw_admin-role"></a><span data-ttu-id="bb3e9-178">Função mdw_admin</span><span class="sxs-lookup"><span data-stu-id="bb3e9-178">mdw_admin Role</span></span>  
 <span data-ttu-id="bb3e9-179">Membros da função **mdw_admin** têm acesso de Leitura, Gravação, Atualização e Exclusão no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-179">Members of the **mdw_admin** role have Read, Write, Update, and Delete access to the management data warehouse.</span></span>  
  
 <span data-ttu-id="bb3e9-180">Membros dessa função podem executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-180">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bb3e9-181">Alterar o esquema do data warehouse de gerenciamento quando necessário (por exemplo, adicionando uma tabela nova quando é instalado um novo tipo de coleta).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-181">Change the management data warehouse schema when required (for example, adding a new table when a new collection type is installed).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb3e9-182">Quando há uma alteração de esquema, o usuário também deve ser um membro da `dc_admin` função para instalar um novo tipo de coletor, pois essa ação requer permissão para atualizar a configuração do coletor de dados no msdb.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-182">Where there is a schema change, the user must also be a member of the `dc_admin` role to install a new collector type, since this action requires permission to update the data collector configuration in msdb.</span></span>  
  
-   <span data-ttu-id="bb3e9-183">Executar tarefas de manutenção no data warehouse de gerenciamento, como arquivo ou limpeza.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-183">Run maintenance jobs on the management data warehouse, such as archive or cleanup.</span></span>  
  
### <a name="mdw_writer-role"></a><span data-ttu-id="bb3e9-184">Função mdw_writer</span><span class="sxs-lookup"><span data-stu-id="bb3e9-184">mdw_writer Role</span></span>  
 <span data-ttu-id="bb3e9-185">Membros da função **mdw_writer** podem carregar e gravar dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-185">Members of the **mdw_writer** role can upload and write data to the management data warehouse.</span></span> <span data-ttu-id="bb3e9-186">Qualquer coletor que armazena dados no data warehouse de gerenciamento deve ser membro dessa função.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-186">Any data collector that stores data in the management data warehouse has to be a member of this role.</span></span>  
  
### <a name="mdw_reader-role"></a><span data-ttu-id="bb3e9-187">Função mdw_reader</span><span class="sxs-lookup"><span data-stu-id="bb3e9-187">mdw_reader Role</span></span>  
 <span data-ttu-id="bb3e9-188">Membros da função **mdw_reader** têm acesso de Leitura ao data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-188">Members of the **mdw_reader** role have Read access to the management data warehouse.</span></span> <span data-ttu-id="bb3e9-189">Como o objetivo dessa função é dar suporte à solução de problemas fornecendo acesso a dados históricos, os membros dessa função não podem exibir outros elementos do esquema do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-189">Because the purpose of this role is to support troubleshooting by providing access to historical data, members of this role cannot view other elements of the management data warehouse schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3e9-190">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb3e9-190">See Also</span></span>  
 [<span data-ttu-id="bb3e9-191">Implementar a segurança do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="bb3e9-191">Implement SQL Server Agent Security</span></span>](../../ssms/agent/implement-sql-server-agent-security.md)  
  
  
