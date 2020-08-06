---
title: Funções de usuário para o serviço de captura de dados de alterações para Oracle por Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: be0ec384-e03b-4483-96ca-02b289804d6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e694da0cfd8645fe594b049b6dc2394b55d1bb55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683134"
---
# <a name="user-roles-for-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="282cb-102">Funções do usuário para o serviço Change Data Capture para Oracle da Attunity</span><span class="sxs-lookup"><span data-stu-id="282cb-102">User Roles for Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="282cb-103">Esta seção descreve as funções de usuário para o Serviço Change Data Capture para Oracle da Attunity.</span><span class="sxs-lookup"><span data-stu-id="282cb-103">This section describes the user roles for the Change Data Capture Service for Oracle by Attunity.</span></span> <span data-ttu-id="282cb-104">As funções descritas são funções de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , funções do Windows ou funções de banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="282cb-104">The roles described are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database roles, Windows roles, or Oracle database roles.</span></span>  
  
## <a name="windows-user-roles"></a><span data-ttu-id="282cb-105">Funções de usuário do Windows</span><span class="sxs-lookup"><span data-stu-id="282cb-105">Windows User Roles</span></span>  
 <span data-ttu-id="282cb-106">Veja a seguir a descrição das funções de usuário do Windows usadas pelo Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-106">The following describes the Windows user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="computer-administrator-oracle-cdc-service"></a><span data-ttu-id="282cb-107">Administrador do computador: Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-107">Computer Administrator: Oracle CDC Service</span></span>  
 <span data-ttu-id="282cb-108">O administrador do computador é um usuário do Windows responsável por criar e manter o Serviço CDC no computador.</span><span class="sxs-lookup"><span data-stu-id="282cb-108">The computer administrator is a Windows user responsible for creating and maintaining the CDC Service on the computer.</span></span> <span data-ttu-id="282cb-109">Este usuário deve pertencer ao grupo de administradores do computador local.</span><span class="sxs-lookup"><span data-stu-id="282cb-109">This user must belong to the group of local machine administrators.</span></span>  
  
 <span data-ttu-id="282cb-110">As tarefas executadas pelo Administrador de Computador do Serviço Oracle CDC incluem:</span><span class="sxs-lookup"><span data-stu-id="282cb-110">The tasks performed by the Oracle CDC Service Computer Administrator include:</span></span>  
  
-   <span data-ttu-id="282cb-111">Instalar o software do Serviço CDC para Oracle</span><span class="sxs-lookup"><span data-stu-id="282cb-111">Installing the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="282cb-112">Criar um serviço Windows Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-112">Creating an Oracle CDC Windows service</span></span>  
  
-   <span data-ttu-id="282cb-113">Configurar a conexão do Serviço CDC para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino (cadeia de conexão e credenciais)</span><span class="sxs-lookup"><span data-stu-id="282cb-113">Setting up the CDC Service connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (connection string and credentials)</span></span>  
  
-   <span data-ttu-id="282cb-114">Garantir que a senha mestre do Serviço CDC com a qual as credenciais de mineração de logs da Oracle esteja protegida</span><span class="sxs-lookup"><span data-stu-id="282cb-114">Ensuring that the CDC Service Master Password with which Oracle log mining credentials are protected</span></span>  
  
-   <span data-ttu-id="282cb-115">Excluir um serviço do Windows do Serviço CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-115">Deleting a CDC Service Windows service</span></span>  
  
-   <span data-ttu-id="282cb-116">Desinstalar o software do Serviço CDC para Oracle</span><span class="sxs-lookup"><span data-stu-id="282cb-116">Uninstalling the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="282cb-117">Manter o software do Serviço CDC para Oracle (por exemplo, instalar as atualizações)</span><span class="sxs-lookup"><span data-stu-id="282cb-117">Maintaining the CDC Service for Oracle software (for example, installing updates)</span></span>  
  
-   <span data-ttu-id="282cb-118">Iniciar e parar o serviço do Windows do Serviço CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-118">Starting and stopping a CDC Service Windows service</span></span>  
  
 <span data-ttu-id="282cb-119">Ao trabalhar com configurações de alta disponibilidade, como clusters de failover da Microsoft, o administrador do computador deve ter responsabilidades e permissões adicionais como:</span><span class="sxs-lookup"><span data-stu-id="282cb-119">When working with high-availability configurations, such as Microsoft failover clusters, the computer administrator must have additional responsibilities and permissions such as:</span></span>  
  
-   <span data-ttu-id="282cb-120">Instalação e manutenção do software do Serviço CDC para Oracle em todos os nós de cluster.</span><span class="sxs-lookup"><span data-stu-id="282cb-120">Installation and maintenance of the CDC Service for Oracle software on all cluster nodes.</span></span>  
  
-   <span data-ttu-id="282cb-121">Definir recursos genéricos de serviço de cluster para o serviço do Windows do Serviço CDC em vários nós de cluster.</span><span class="sxs-lookup"><span data-stu-id="282cb-121">Defining generic cluster service resources for the CDC Service' Windows service on the various cluster nodes.</span></span>  
  
-   <span data-ttu-id="282cb-122">Agir como o administrador autorizado no computador em que o Serviço CDC para Oracle está instalado.</span><span class="sxs-lookup"><span data-stu-id="282cb-122">Acting as the computer administrator authorized as an administrator on the computer where the CDC Service for Oracle is installed.</span></span> <span data-ttu-id="282cb-123">Esta pessoa instala o Serviço CDC para Oracle e usa o Console de Configuração de Serviço CDC para configurar um Serviço CDC para Oracle em um computador local.</span><span class="sxs-lookup"><span data-stu-id="282cb-123">This person installs the CDC Service for Oracle and uses the CDC Service Configuration Console to configure a CDC Service for Oracle on a local computer.</span></span>  
  
### <a name="service-account-oracle-cdc-service"></a><span data-ttu-id="282cb-124">Conta de serviço: Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-124">Service Account: Oracle CDC Service</span></span>  
 <span data-ttu-id="282cb-125">Essa Conta de Serviço Windows do Serviço Oracle CDC é uma conta do Windows usada para executar o Serviço Oracle CDC (a conta de serviço).</span><span class="sxs-lookup"><span data-stu-id="282cb-125">This is Oracle CDC Service Windows Service Account is a Windows account used for running the Oracle CDC Service (the Service Account).</span></span>  
  
 <span data-ttu-id="282cb-126">O único privilégio exigido necessário para a conta de serviço é poder usar o cliente Oracle e o provedor ODBC do cliente nativo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="282cb-126">The only required privilege necessary for the service account is to be able to use the Oracle client and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client ODBC provider.</span></span> <span data-ttu-id="282cb-127">Esta conta não precisa acessar arquivos a menos que isso seja exigido por provedores específicos (por exemplo, se a cadeia de conexão do cliente Oracle referenciar instâncias de banco de dados Oracle em um arquivo **tnsnames.ora** , isso significará que esse arquivo estará acessível à leitura para uma conta de serviço).</span><span class="sxs-lookup"><span data-stu-id="282cb-127">This account does not need to access files unless required by specific providers (for example, if the Oracle client connection string references Oracle database instances in a **tnsnames.ora** file, then that file must be read-accessible to the service account).</span></span>  
  
 <span data-ttu-id="282cb-128">Ao criar um Serviço Oracle CDC no Windows Vista ou Windows Server 2008, a conta de serviço padrão é a conta NETWORK SERVICE.</span><span class="sxs-lookup"><span data-stu-id="282cb-128">When creating an Oracle CDC Service on Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
 <span data-ttu-id="282cb-129">No Windows 7, Windows Server 2008 R2 e posterior, a conta de serviço padrão é NT Service\\<service-name>.</span><span class="sxs-lookup"><span data-stu-id="282cb-129">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
 <span data-ttu-id="282cb-130">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado em outra máquina ou é uma instância clusterizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o serviço precisa se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando autenticação do Windows, a conta de serviço deve ser uma conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="282cb-130">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on another machine or is a clustered [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and there the service needs to connect to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows authentication, then the service account should be a domain account.</span></span>  
  
## <a name="sql-server-user-roles"></a><span data-ttu-id="282cb-131">Funções de usuário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="282cb-131">SQL Server User Roles</span></span>  
 <span data-ttu-id="282cb-132">Veja a seguir a descrição das funções de usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usadas pelo Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-132">The following describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="oracle-cdc-service-administrator"></a><span data-ttu-id="282cb-133">Administrador do Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-133">Oracle CDC Service Administrator</span></span>  
 <span data-ttu-id="282cb-134">O Administrador do Serviço CDC é um usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com controle total sobre os artefatos do Serviço Oracle CDC na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="282cb-134">The CDC Service Administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user with full control over the Oracle CDC Service artifacts in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="282cb-135">O Administrador do Serviço CDC usa o Console de Designer do Oracle CDC para criar Instâncias Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-135">The CDC Service Administrator uses the Oracle CDC Designer Console to design Oracle CDC Instances.</span></span>  
  
 <span data-ttu-id="282cb-136">O Administrador do Serviço CDC deve ter as funções de servidor fixas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] public **e** dbcreator **do**.</span><span class="sxs-lookup"><span data-stu-id="282cb-136">The CDC Service Administrator should be granted the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fixed server roles **public** and **dbcreator**.</span></span>  
  
 <span data-ttu-id="282cb-137">As tarefas executadas pelo Administrador do Serviço CDC incluem:</span><span class="sxs-lookup"><span data-stu-id="282cb-137">The tasks performed by the CDC Service Administrator include:</span></span>  
  
-   <span data-ttu-id="282cb-138">Preparar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para hospedar Instâncias Oracle CDC (que são bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="282cb-138">Preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host Oracle CDC Instances (which are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases).</span></span> <span data-ttu-id="282cb-139">Nessa tarefa, um banco de dados especial chamado MSXDBCDC é criado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="282cb-139">In this task, a special database called MSXDBCDC is created in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="282cb-140">Criar um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-140">Creating an Oracle CDC Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="282cb-141">A tarefa inclui habilitar o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recém-criado para o CDC que exige um administrador do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator**sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="282cb-141">Task includes enabling the newly created [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for CDC, which requires a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator (**sysadmin**).</span></span>  
  
-   <span data-ttu-id="282cb-142">Criar uma Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-142">Designing an Oracle CDC Instance.</span></span> <span data-ttu-id="282cb-143">Esta tarefa inclui fornecer informações sobre o banco de dados Oracle de origem e tabelas capturadas que exigem um administrador de banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="282cb-143">This task includes providing information about the source Oracle database and captured tables, which requires an Oracle database administrator.</span></span>  
  
-   <span data-ttu-id="282cb-144">Manter a Instância Oracle CDC com o passar do tempo, o que inclui adição/remoção de instâncias de captura e atualização de configuração.</span><span class="sxs-lookup"><span data-stu-id="282cb-144">Maintaining the Oracle CDC Instance over time, which includes adding/removing capture instances and updating configuration.</span></span>  
  
-   <span data-ttu-id="282cb-145">Habilitar ou desabilitar uma Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-145">Enabling or disabling an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="282cb-146">Monitorar o estado de uma Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-146">Monitoring the state of an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="282cb-147">Solucionar problemas que afetam a Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-147">Troubleshooting issues that affect the Oracle CDC Instance.</span></span>  
  
 <span data-ttu-id="282cb-148">O Administrador do Serviços CDC está, pelo menos inicialmente, na função de banco de dados fixa **db_owner** para o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC associado com a Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-148">The CDC Service Administrator is, at least initially, in the **db_owner** fixed database role for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database associated with the Oracle CDC Instance.</span></span> <span data-ttu-id="282cb-149">Isto dá ao Administrador do Serviço CDC acesso aos dados de alteração armazenados no banco de dados CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-149">This gives the CDC Service Administrator access to the change data stored in the CDC database.</span></span> <span data-ttu-id="282cb-150">Uma vez criada, a função **db_owner** do banco de dados CDC pode ser atribuída a um usuário diferente que pode conduzir todas as tarefas listadas acima exceto preparar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e criar outra Instância Oracle CDC).</span><span class="sxs-lookup"><span data-stu-id="282cb-150">Once created, the **db_owner** role of the CDC database can be assigned to a different user who can carry out all of the tasks listed above except for preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and creating another Oracle CDC Instance).</span></span>  
  
 <span data-ttu-id="282cb-151">O Administrador do Serviço CDC não precisa saber a senha mestra especificada com a criação do serviço do Windows do Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-151">The CDC Service Administrator does not need to know the master password specified with the creation of the Oracle CDC Windows service.</span></span>  
  
### <a name="system-administrator"></a><span data-ttu-id="282cb-152">Administrador do Sistema</span><span class="sxs-lookup"><span data-stu-id="282cb-152">System Administrator</span></span>  
 <span data-ttu-id="282cb-153">O administrador do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é um usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e deve ter a função de servidor fixa **sysadmin** na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associada com o Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-153">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user and should be granted the fixed server **sysadmin** role on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance associated with the Oracle CDC Service(s).</span></span>  
  
 <span data-ttu-id="282cb-154">Há somente uma tarefa específica do Oracle CDC conduzida com o Administrador de Sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que é habilitar o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para uma Instância Oracle CDC para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-154">There is only one Oracle CDC specific task that carried out with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] System Administrator and that is to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for an Oracle CDC Instance for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span></span> <span data-ttu-id="282cb-155">Esta tarefa é realizada usando o console de Designer do Oracle CDC ao criar uma nova Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-155">This task is performed using the Oracle CDC Designer console when creating a new Oracle CDC Instance.</span></span>  
  
### <a name="oracle-cdc-service-user"></a><span data-ttu-id="282cb-156">Usuário do Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-156">Oracle CDC Service User</span></span>  
 <span data-ttu-id="282cb-157">O usuário do Serviço Oracle CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que é usado pelo Serviço Oracle CDC para executar seu trabalho no MSXDBCDC e todas as Instâncias Oracle CDC (bancos de dados CDC) tratados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="282cb-157">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login which is used by the Oracle CDC Service to perform its work against the MSXDBCDC and all of the Oracle CDC Instances (CDC databases) handled by this service.</span></span>  
  
 <span data-ttu-id="282cb-158">O usuário do Serviço Oracle CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser concedido o seguinte:</span><span class="sxs-lookup"><span data-stu-id="282cb-158">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user should be granted the following:</span></span>  
  
-   <span data-ttu-id="282cb-159">Membro das funções de banco de dados fixas **db_dlladmin**, **db_datareader**e **db_datawriter** para todos os bancos de dados CDC tratados pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="282cb-159">Member of the fixed database roles **db_dlladmin**, **db_datareader**, and **db_datawriter** for all CDC databases handled by the server.</span></span>  
  
-   <span data-ttu-id="282cb-160">Membro das funções de banco de dados fixas **db_datareader** e **db_datawriter** para o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-160">Member of the fixed database roles **db_datareader** and **db_datawriter** for the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="282cb-161">Como o Serviço Oracle CDC usa um logon único do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para funcionar com todos os bancos de dados CDC e o banco de dados MSXDBCDC, este logon deve ser mapeado em todos estes bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="282cb-161">Because the Oracle CDC Service uses a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to work with all CDC databases and the MSXDBCDC database, this login should be mapped in all of these databases.</span></span>  
  
### <a name="oracle-cdc-change-consumer"></a><span data-ttu-id="282cb-162">Consumidor de Alteração Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="282cb-162">Oracle CDC Change Consumer</span></span>  
 <span data-ttu-id="282cb-163">O Consumidor de Alteração Oracle CDC é um usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que consome alterações armazenadas nas tabelas CDC no banco de dados da Instância Oracle CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="282cb-163">The Oracle CDC Change Consumer is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user that consumes changes stored in the CDC tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database.</span></span>  
  
 <span data-ttu-id="282cb-164">Este usuário determina a função de usuário que é necessária para acessar cada tabela CDC por meio das funções CDC geradas pela infraestrutura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-164">This user determines the user role that is required for accessing each of the CDC tables through the CDC functions generated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC infrastructure.</span></span> <span data-ttu-id="282cb-165">Se nenhuma função de usuário for especificada quando uma instância de captura é especificada, o acesso às alterações será limitado ao membro da função de banco de dados fixa **db_owner** do banco de dados CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-165">If no user role is specified when a capture instance is specified, access to the changes is limited to the member of the **db_owner** fixed database role of the CDC database.</span></span>  
  
## <a name="oracle-user-roles"></a><span data-ttu-id="282cb-166">Funções de usuário Oracle</span><span class="sxs-lookup"><span data-stu-id="282cb-166">Oracle User Roles</span></span>  
 <span data-ttu-id="282cb-167">Veja a seguir a descrição das funções de usuário do Oracle usadas pelo Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-167">The following describes the Oracle user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="database-administrator-dba"></a><span data-ttu-id="282cb-168">Administrador de banco de dados (DBA)</span><span class="sxs-lookup"><span data-stu-id="282cb-168">Database Administrator (DBA)</span></span>  
 <span data-ttu-id="282cb-169">O administrador de banco de dados Oracle (DBA) é um usuário de banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="282cb-169">The Oracle database administrator (DBA) is an Oracle database user.</span></span> <span data-ttu-id="282cb-170">As tarefas executadas pelo DBA da Oracle incluem:</span><span class="sxs-lookup"><span data-stu-id="282cb-170">The tasks performed by the Oracle DBA include:</span></span>  
  
-   <span data-ttu-id="282cb-171">Definir o banco de dados Oracle de origem para funcionar em modo ARCHIVELOG.</span><span class="sxs-lookup"><span data-stu-id="282cb-171">Setting the source Oracle database to work in ARCHIVELOG mode.</span></span>  
  
-   <span data-ttu-id="282cb-172">Configurar um usuário de mineração de logs com as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="282cb-172">Setting up a log mining user with the required permissions.</span></span>  
  
-   <span data-ttu-id="282cb-173">Definir o log suplementar para tabelas capturadas.</span><span class="sxs-lookup"><span data-stu-id="282cb-173">Setting supplemental logging for captured tables.</span></span>  
  
-   <span data-ttu-id="282cb-174">Ajudar a restaurar arquivos de log de transação arquivados que não estão mais disponíveis para que possam ser processados.</span><span class="sxs-lookup"><span data-stu-id="282cb-174">Helping to restore archived transaction log files no longer available so they can be processed.</span></span>  
  
 <span data-ttu-id="282cb-175">O administrador de banco de dados Oracle pode obter scripts SQL de Oracle que precisam ser executados, para que possam ser avaliados antes de serem executados.</span><span class="sxs-lookup"><span data-stu-id="282cb-175">The Oracle database administrator can get Oracle SQL scripts that need to run so they can be evaluated before running them.</span></span> <span data-ttu-id="282cb-176">O administrador de banco de dados Oracle também pode executar scripts SQL de Oracle diretamente do Console de Designer do Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="282cb-176">The Oracle database administrator can also directly run Oracle SQL scripts from the Oracle CDC Designer console.</span></span>  
  
 <span data-ttu-id="282cb-177">Se o administrador do Oracle Database escolher usar o console do Oracle CDC Designer, as credenciais de administrador não serão mantidas com exceção do contexto (caixa de diálogo) no qual eles foram usados.</span><span class="sxs-lookup"><span data-stu-id="282cb-177">If the Oracle database administrator chooses to use the Oracle CDC Designer console, administrator's credentials are not kept except for the context (dialog) in which they were used.</span></span>  
  
 <span data-ttu-id="282cb-178">O administrador de banco de dados Oracle funciona em coordenação com o administrador do Serviço Oracle CDC na configuração de Instâncias Oracle CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="282cb-178">The Oracle database administrator works in coordination with the Oracle CDC Service administrator on the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instances.</span></span>  
  
### <a name="log-mining-user"></a><span data-ttu-id="282cb-179">Usuário de mineração de logs</span><span class="sxs-lookup"><span data-stu-id="282cb-179">Log Mining User</span></span>  
 <span data-ttu-id="282cb-180">O usuário do Minerador de Logs Oracle é um usuário de banco de dados Oracle especial que tem os privilégios necessários para acessar e processar os logs de transação Oracle.</span><span class="sxs-lookup"><span data-stu-id="282cb-180">The Oracle Log Miner user is a special Oracle database user that is granted the required privileges for accessing and processing the Oracle transaction logs.</span></span>  
  
 <span data-ttu-id="282cb-181">As credenciais para este usuário são armazenadas no banco de dados da Instância Oracle CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando criptografia de chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="282cb-181">The credentials for this user are stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database using asymmetric key encryption.</span></span> <span data-ttu-id="282cb-182">Eles só estão acessíveis ao Serviço Oracle CDC, mas não para o proprietário do banco de dados da Instância Oracle CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="282cb-182">They are accessible only to the Oracle CDC Service but not to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database owner.</span></span>  
  
 <span data-ttu-id="282cb-183">A lista a seguir descreve os privilégios necessários que devem ser concedidos ao usuário de mineração de logs:</span><span class="sxs-lookup"><span data-stu-id="282cb-183">The following list describes the required privileges of the log mining user should be granted:</span></span>  
  
-   <span data-ttu-id="282cb-184">SELECT em \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="282cb-184">SELECT on \<any-captured-table></span></span>  
  
-   <span data-ttu-id="282cb-185">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="282cb-185">SELECT ANY TRANSACTION</span></span>  
  
-   <span data-ttu-id="282cb-186">EXECUTE em DBMS_LOGMNR</span><span class="sxs-lookup"><span data-stu-id="282cb-186">EXECUTE on DBMS_LOGMNR</span></span>  
  
-   <span data-ttu-id="282cb-187">SELECT em V$LOGMNR_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="282cb-187">SELECT on V$LOGMNR_CONTENTS</span></span>  
  
-   <span data-ttu-id="282cb-188">SELECT em V$ARCHIVED_LOG</span><span class="sxs-lookup"><span data-stu-id="282cb-188">SELECT on V$ARCHIVED_LOG</span></span>  
  
-   <span data-ttu-id="282cb-189">SELECT em V$LOG</span><span class="sxs-lookup"><span data-stu-id="282cb-189">SELECT on V$LOG</span></span>  
  
-   <span data-ttu-id="282cb-190">SELECT em V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="282cb-190">SELECT on V$LOGFILE</span></span>  
  
-   <span data-ttu-id="282cb-191">SELECT em V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="282cb-191">SELECT on V$DATABASE</span></span>  
  
-   <span data-ttu-id="282cb-192">SELECT em V$THREAD</span><span class="sxs-lookup"><span data-stu-id="282cb-192">SELECT on V$THREAD</span></span>  
  
-   <span data-ttu-id="282cb-193">SELECT em V$PARAMETER</span><span class="sxs-lookup"><span data-stu-id="282cb-193">SELECT on V$PARAMETER</span></span>  
  
-   <span data-ttu-id="282cb-194">SELECT em DBA_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="282cb-194">SELECT on DBA_REGISTRY</span></span>  
  
-   <span data-ttu-id="282cb-195">SELECT em ALL_INDEXES</span><span class="sxs-lookup"><span data-stu-id="282cb-195">SELECT on ALL_INDEXES</span></span>  
  
-   <span data-ttu-id="282cb-196">SELECT em ALL_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="282cb-196">SELECT on ALL_OBJECTS</span></span>  
  
-   <span data-ttu-id="282cb-197">SELECT em DBA_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="282cb-197">SELECT on DBA_OBJECTS</span></span>  
  
-   <span data-ttu-id="282cb-198">SELECT em ALL_TABLES</span><span class="sxs-lookup"><span data-stu-id="282cb-198">SELECT on ALL_TABLES</span></span>  
  
 <span data-ttu-id="282cb-199">Se algum destes privilégios não puder ser concedido a um V$xxx, ele deverá ser concedido ao V $xxx.</span><span class="sxs-lookup"><span data-stu-id="282cb-199">If any of these privileges cannot be granted to a V$xxx, then they should be granted to the V $xxx.</span></span>  
  
### <a name="schema-user"></a><span data-ttu-id="282cb-200">Usuário do esquema</span><span class="sxs-lookup"><span data-stu-id="282cb-200">Schema User</span></span>  
 <span data-ttu-id="282cb-201">O Usuário do Esquema Oracle é um usuário do Oracle com acesso de leitura para o esquema das tabelas do Oracle a ser capturado.</span><span class="sxs-lookup"><span data-stu-id="282cb-201">The Oracle Schema User is an Oracle user with read access to the schema of the Oracle tables to be captured.</span></span> <span data-ttu-id="282cb-202">Este usuário é necessário ao trabalhar com o console de Designer do Oracle CDC para recuperar a lista de esquema do Oracle, tabelas a serem capturadas e suas colunas, índices e chaves.</span><span class="sxs-lookup"><span data-stu-id="282cb-202">This user is necessary when working with the Oracle CDC Designer console to retrieve the list of Oracle schema, tables to be captured and their columns, indexes and keys.</span></span>  
  
 <span data-ttu-id="282cb-203">As credenciais para este usuário nunca são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="282cb-203">The credentials for this user are never stored.</span></span> <span data-ttu-id="282cb-204">Elas são solicitadas pelo console de Designer CDC toda vez em que são necessárias e são mantidas para o restante das sessões da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="282cb-204">They are requested by the CDC Designer console each time they are needed and they are kept for the rest of the UI sessions.</span></span>  
  
  
