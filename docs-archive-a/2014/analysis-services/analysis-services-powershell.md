---
title: Analysis Services PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 03/11/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 60bb9610-7229-42eb-a95f-a377268a8720
author: minewiskan
ms.author: owend
ms.openlocfilehash: 56af6f26c29e5c1ddb278b620b6f525c70bd1203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571199"
---
# <a name="analysis-services-powershell"></a><span data-ttu-id="0554e-102">Analysis Services PowerShell</span><span class="sxs-lookup"><span data-stu-id="0554e-102">Analysis Services PowerShell</span></span>
  <span data-ttu-id="0554e-103">O [!INCLUDE[ssASCurrent](../includes/ssascurrent-md.md)] contém um provedor SQLAS (Analysis Services PowerShell) e cmdlets para que você possa usar o Windows PowerShell para navegar em, administrar e consultar objetos do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-103">[!INCLUDE[ssASCurrent](../includes/ssascurrent-md.md)] includes an Analysis Services PowerShell (SQLAS) provider and cmdlets so that you can use Windows PowerShell to navigate, administer, and query Analysis Services objects.</span></span>  
  
 <span data-ttu-id="0554e-104">O Analysis Services PowerShell consiste no seguinte:</span><span class="sxs-lookup"><span data-stu-id="0554e-104">Analysis Services PowerShell consists of the following:</span></span>  
  
-   <span data-ttu-id="0554e-105">Provedor `SQLAS` usado para navegar na hierarquia do AMO (Objetos de Gerenciamento de Análise).</span><span class="sxs-lookup"><span data-stu-id="0554e-105">`SQLAS` provider used for navigating the Analysis Management Object (AMO) hierarchy.</span></span>  
  
-   <span data-ttu-id="0554e-106">Cmdlet `Invoke-ASCmd` usado para executar scripts MDX, DMX ou XMLA.</span><span class="sxs-lookup"><span data-stu-id="0554e-106">`Invoke-ASCmd` cmdlet used for executing MDX, DMX, or XMLA script.</span></span>  
  
-   <span data-ttu-id="0554e-107">Cmdlets específicos de tarefas para operações rotineiras, como processamento, gerenciamento de funções, gerenciamento de partições, backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="0554e-107">Task-specific cmdlets for routine operations, such as processing, role management, partition management, backup and restore.</span></span>  
  
## <a name="in-this-article"></a><span data-ttu-id="0554e-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="0554e-108">In this article</span></span>  
 [<span data-ttu-id="0554e-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0554e-109">Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="0554e-110">Versões e modos compatíveis do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0554e-110">Supported Versions and Modes of Analysis Services</span></span>](#bkmk_vers)  
  
 [<span data-ttu-id="0554e-111">Requisitos de autenticação e considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="0554e-111">Authentication Requirements and Security Considerations</span></span>](#bkmk_auth)  
  
 [<span data-ttu-id="0554e-112">Tarefas do Analysis Services PowerShell</span><span class="sxs-lookup"><span data-stu-id="0554e-112">Analysis Services PowerShell Tasks</span></span>](#bkmk_tasks)  

<span data-ttu-id="0554e-113">Para obter mais informações sobre sintaxe e exemplos, consulte [Analysis Services referência do PowerShell](/sql/analysis-services/powershell/analysis-services-powershell-reference).</span><span class="sxs-lookup"><span data-stu-id="0554e-113">For more information about syntax and examples, see [Analysis Services PowerShell Reference](/sql/analysis-services/powershell/analysis-services-powershell-reference).</span></span>

##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="0554e-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0554e-114">Prerequisites</span></span>  
 <span data-ttu-id="0554e-115">O Windows PowerShell 2.0 deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="0554e-115">Windows PowerShell 2.0 must be installed.</span></span> <span data-ttu-id="0554e-116">Ele é instalado por padrão em versões mais recentes dos sistemas operacionais Windows.</span><span class="sxs-lookup"><span data-stu-id="0554e-116">It is installed by default on newer versions of the Windows operating systems.</span></span> <span data-ttu-id="0554e-117">Para obter mais informações, consulte [instalar o Windows PowerShell 2,0](https://msdn.microsoft.com/library/ff637750.aspx)</span><span class="sxs-lookup"><span data-stu-id="0554e-117">For more information, see [Install Windows PowerShell 2.0](https://msdn.microsoft.com/library/ff637750.aspx)</span></span>

<!-- ff637750.aspx above is linked to by:  (https://go.microsoft.com/fwlink/?LinkId=227613). -->
  
 <span data-ttu-id="0554e-118">Você deve instalar um recurso do SQL Server que inclui o módulo do SQL Server PowerShell (SQLPS) e bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="0554e-118">You must install a SQL Server feature that includes the SQL Server PowerShell (SQLPS) module and client libraries.</span></span> <span data-ttu-id="0554e-119">O modo mais fácil de fazer isto é instalar o SQL Server Management Studio, que inclui o recurso do PowerShell e bibliotecas de cliente automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0554e-119">The easiest way to do this is by installing SQL Server Management Studio, which includes the PowerShell feature and client libraries automatically.</span></span> <span data-ttu-id="0554e-120">Um módulo SQLPS (SQL Server PowerShell) contém os provedores PowerShell e cmdlets para todos os recursos do SQL Server, incluindo o módulo SQLASCmdlets e o provedor SQLAS usados para navegar na hierarquia de objetos do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-120">The SQL Server PowerShell (SQLPS) module contains the PowerShell providers and cmdlets for all SQL Server features, including the SQLASCmdlets module and SQLAS provider used for navigating the Analysis Services object hierarchy.</span></span>  
  
 <span data-ttu-id="0554e-121">Você deve importar o módulo **sqlps** antes de poder usar o `SQLAS` provedor e os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0554e-121">You must import the **SQLPS** module before you can use the `SQLAS` provider and cmdlets.</span></span> <span data-ttu-id="0554e-122">O provedor SQLAS é uma extensão do `SQLServer` provedor.</span><span class="sxs-lookup"><span data-stu-id="0554e-122">The SQLAS provider is an extension of the `SQLServer` provider.</span></span> <span data-ttu-id="0554e-123">Há várias maneiras de importar o módulo SQLPS.</span><span class="sxs-lookup"><span data-stu-id="0554e-123">There are several ways to import the SQLPS module.</span></span> <span data-ttu-id="0554e-124">Para obter mais informações, consulte [Importar o módulo SQLPS](../../2014/database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="0554e-124">For more information, see [Import the SQLPS Module](../../2014/database-engine/import-the-sqlps-module.md).</span></span>  
  
 <span data-ttu-id="0554e-125">O acesso remoto a uma instância do Analysis Services exige a habilitação da administração remota e do compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0554e-125">Remote access to an Analysis Services instance requires that you enable remote administration and file sharing.</span></span> <span data-ttu-id="0554e-126">Para obter mais informações, consulte [habilitar a administração remota](#bkmk_remote) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0554e-126">For more information, see [Enable Remote Administration](#bkmk_remote) in this topic.</span></span>  
  
##  <a name="supported-versions-and-modes-of-analysis-services"></a><a name="bkmk_vers"></a><span data-ttu-id="0554e-127">Versões e modos de Analysis Services com suporte</span><span class="sxs-lookup"><span data-stu-id="0554e-127">Supported Versions and Modes of Analysis Services</span></span>  
 <span data-ttu-id="0554e-128">Atualmente, há suporte para o Analysis Services PowerShell em qualquer edição do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Analysis Services executada no Windows Server 2008 R2, Windows Server 2008 SP1 ou Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0554e-128">Currently, Analysis Services PowerShell is supported on any edition of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Analysis Services running on Windows Server 2008 R2, Windows Server 2008 SP1, or Windows 7.</span></span>  
  
 <span data-ttu-id="0554e-129">A tabela a seguir mostra a disponibilidade do Analysis Services PowerShell em diferentes contextos.</span><span class="sxs-lookup"><span data-stu-id="0554e-129">The following table shows the availability of Analysis Services PowerShell in different contexts.</span></span>  
  
|<span data-ttu-id="0554e-130">Contexto</span><span class="sxs-lookup"><span data-stu-id="0554e-130">Context</span></span>|<span data-ttu-id="0554e-131">Disponibilidade de recursos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0554e-131">PowerShell Feature Availability</span></span>|  
|-------------|-------------------------------------|  
|<span data-ttu-id="0554e-132">Instâncias e bancos de dados multidimensionais</span><span class="sxs-lookup"><span data-stu-id="0554e-132">Multidimensional instances and databases</span></span>|<span data-ttu-id="0554e-133">Com suporte para administração local e remota.</span><span class="sxs-lookup"><span data-stu-id="0554e-133">Supported for local and remote administration.</span></span><br /><br /> <span data-ttu-id="0554e-134">A partição de mesclagem exige uma conexão local.</span><span class="sxs-lookup"><span data-stu-id="0554e-134">Merge-partition requires a local connection.</span></span>|  
|<span data-ttu-id="0554e-135">Instâncias e bancos de dados tabulares</span><span class="sxs-lookup"><span data-stu-id="0554e-135">Tabular instances and databases</span></span>|<span data-ttu-id="0554e-136">Com suporte para administração local e remota.</span><span class="sxs-lookup"><span data-stu-id="0554e-136">Supported for local and remote administration.</span></span><br /><br /> <span data-ttu-id="0554e-137">Para obter mais informações, consulte um blog de agosto de 2011 sobre como [gerenciar modelos tabulares usando o PowerShell](https://go.microsoft.com/fwlink/?linkID=227685).</span><span class="sxs-lookup"><span data-stu-id="0554e-137">For more information, see an August 2011 blog about [Manage Tabular Models Using PowerShell](https://go.microsoft.com/fwlink/?linkID=227685).</span></span>|  
|<span data-ttu-id="0554e-138">Instâncias e bancos de dados PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="0554e-138">PowerPivot for SharePoint instances and databases</span></span>|<span data-ttu-id="0554e-139">Suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="0554e-139">Limited support.</span></span> <span data-ttu-id="0554e-140">É possível usar conexões HTTP e o provedor SQLAS para visualizar informações da instância e do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0554e-140">You can use HTTP connections and the SQLAS provider to view instance and database information.</span></span><br /><br /> <span data-ttu-id="0554e-141">Porém, não há suporte para usar os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0554e-141">However, using the cmdlets is not supported.</span></span> <span data-ttu-id="0554e-142">Você não deve usar o Analysis Services PowerShell para fazer backup e restauração de banco de dados PowerPivot na memória, nem deve adicionar ou remover funções, processar os dados ou executar script XMLA arbitrário.</span><span class="sxs-lookup"><span data-stu-id="0554e-142">You must not use Analysis Services PowerShell to backup and restore in-memory PowerPivot database, nor should you add or remove roles, process data, or run arbitrary XMLA script.</span></span><br /><br /> <span data-ttu-id="0554e-143">Para fins de configuração, o PowerPivot para SharePoint tem suporte interno ao PowerShell que é fornecido separadamente.</span><span class="sxs-lookup"><span data-stu-id="0554e-143">For configuration purposes, PowerPivot for SharePoint has built-in PowerShell support that is provided separately.</span></span> <span data-ttu-id="0554e-144">Para obter mais informações, consulte [referência do PowerShell para PowerPivot para SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="0554e-144">For more information, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>|  
|<span data-ttu-id="0554e-145">Conexões nativas a cubos locais</span><span class="sxs-lookup"><span data-stu-id="0554e-145">Native connections to local cubes</span></span><br /><br /> <span data-ttu-id="0554e-146">"Data Source = c:\backup\test.Cub"</span><span class="sxs-lookup"><span data-stu-id="0554e-146">"Data Source=c:\backup\test.cub"</span></span>|<span data-ttu-id="0554e-147">Não há suporte.</span><span class="sxs-lookup"><span data-stu-id="0554e-147">Not supported.</span></span>|  
|<span data-ttu-id="0554e-148">Conexões HTTP a arquivos de conexão do modelo semântico BI (.bism) no SharePoint</span><span class="sxs-lookup"><span data-stu-id="0554e-148">HTTP connections to BI semantic model (.bism) connection files in SharePoint</span></span><br /><br /> <span data-ttu-id="0554e-149">"Fonte de dados = http://server/shared_docs/name.bism "</span><span class="sxs-lookup"><span data-stu-id="0554e-149">"Data Source=http://server/shared_docs/name.bism"</span></span>|<span data-ttu-id="0554e-150">Não há suporte.</span><span class="sxs-lookup"><span data-stu-id="0554e-150">Not supported.</span></span>|  
|<span data-ttu-id="0554e-151">Conexões inseridas em bancos de dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="0554e-151">Embedded connections to PowerPivot databases</span></span><br /><br /> <span data-ttu-id="0554e-152">"Data Source = $Embedded $"</span><span class="sxs-lookup"><span data-stu-id="0554e-152">"Data Source=$Embedded$"</span></span>|<span data-ttu-id="0554e-153">Não há suporte.</span><span class="sxs-lookup"><span data-stu-id="0554e-153">Not supported.</span></span>|  
|<span data-ttu-id="0554e-154">Contexto de servidor local em procedimentos armazenados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0554e-154">Local server context in Analysis Services stored procedures</span></span><br /><br /> <span data-ttu-id="0554e-155">"Fonte de dados = \*"</span><span class="sxs-lookup"><span data-stu-id="0554e-155">"Data Source=\*"</span></span>|<span data-ttu-id="0554e-156">Não há suporte.</span><span class="sxs-lookup"><span data-stu-id="0554e-156">Not supported.</span></span>|  
  
##  <a name="authentication-requirements-and-security-considerations"></a><a name="bkmk_auth"></a><span data-ttu-id="0554e-157">Requisitos de autenticação e considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="0554e-157">Authentication Requirements and Security Considerations</span></span>  
 <span data-ttu-id="0554e-158">Ao conectar-se ao Analysis Services, você deve fazer a conexão usando uma identidade de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="0554e-158">When connecting to Analysis Services, you must make the connection using a Windows user identity.</span></span> <span data-ttu-id="0554e-159">Na maioria das vezes, a conexão é feita usando uma segurança integrada do Windows, onde a identidade do usuário atual define o contexto de segurança sob o qual as operações de servidor são realizadas.</span><span class="sxs-lookup"><span data-stu-id="0554e-159">For the most part, a connection is made using Windows integrated security, where the identity of the current user sets the security context under which server operations are performed.</span></span> <span data-ttu-id="0554e-160">No entanto, outros métodos de autenticação ficam disponíveis quando você configura o acesso de HTTP para o Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-160">However, additional authentication methods become available when you configure HTTP access to Analysis Services.</span></span> <span data-ttu-id="0554e-161">Esta seção explica como o tipo de conexão determina quais opções de autenticação você pode usar.</span><span class="sxs-lookup"><span data-stu-id="0554e-161">This section explains how the type of connection determines which authentication options you can use.</span></span>  
  
 <span data-ttu-id="0554e-162">As conexões para o Analysis Services são caracterizadas como conexões nativas ou conexões HTTP.</span><span class="sxs-lookup"><span data-stu-id="0554e-162">Connections to Analysis Services are characterized as either native connections or HTTP connections.</span></span> <span data-ttu-id="0554e-163">Uma conexão nativa é uma conexão direta de um aplicativo cliente para o servidor.</span><span class="sxs-lookup"><span data-stu-id="0554e-163">A native connection is a direct connection from a client application to the server.</span></span> <span data-ttu-id="0554e-164">Em uma sessão do PowerShell, o cliente PowerShell usa o provedor OLE DB para o Analysis Services conectar-se diretamente a uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-164">In a PowerShell session, the PowerShell client uses the OLE DB provider for Analysis Services to connect directly to an Analysis Services instance.</span></span> <span data-ttu-id="0554e-165">Uma conexão nativa é sempre feita usando uma segurança integrada do Windows, onde o Analysis Services PowerShell é executado como o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0554e-165">A native connection is always made using Windows integrated security, where Analysis Services PowerShell executes as the current user.</span></span> <span data-ttu-id="0554e-166">O Analysis Services não dá suporte à representação.</span><span class="sxs-lookup"><span data-stu-id="0554e-166">Analysis Services does not support impersonation.</span></span> <span data-ttu-id="0554e-167">Se você desejar realizar uma operação como um usuário específico, deverá iniciar a sessão do PowerShell como esse usuário.</span><span class="sxs-lookup"><span data-stu-id="0554e-167">If you want to perform an operation as a specific user, you must start the PowerShell session as that user.</span></span>  
  
 <span data-ttu-id="0554e-168">As conexões HTTP são feitas indiretamente por meio do IIS, permitindo opções adicionais de autenticação, como autenticação Básica, para conectar-se a uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-168">HTTP connections are made indirectly through IIS, allowing for additional authentication options, such as Basic authentication, to connect to an Analysis Services instance.</span></span> <span data-ttu-id="0554e-169">Como o IIS dá suporte à representação, você pode fornecer uma cadeia de conexão que inclui credenciais que o IIS usará para representar ao fazer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="0554e-169">Because IIS supports impersonation, you can provide a connection string that includes credentials IIS will use to impersonate when making a connection.</span></span> <span data-ttu-id="0554e-170">Para fornecer credenciais, você pode usar o parâmetro-Credential.</span><span class="sxs-lookup"><span data-stu-id="0554e-170">To provide credentials, you can use the -Credential parameter.</span></span>  
  
 <span data-ttu-id="0554e-171">**Usando o parâmetro-Credential no PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0554e-171">**Using the -Credential Parameter in PowerShell**</span></span>  
  
 <span data-ttu-id="0554e-172">O parâmetro-Credential usa um objeto PSCredential que especifica um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0554e-172">The -Credential parameter takes a PSCredential object that specifies a user name and password.</span></span> <span data-ttu-id="0554e-173">No Analysis Services PowerShell, o parâmetro-Credential está disponível para cmdlets que fazem uma solicitação de conexão para Analysis Services, ao contrário de cmdlets que são executados dentro do contexto de uma conexão existente.</span><span class="sxs-lookup"><span data-stu-id="0554e-173">In Analysis Services PowerShell, the -Credential parameter is available for cmdlets that make a connection request to Analysis Services, as opposed to cmdlets that run within the context of an existing connection.</span></span> <span data-ttu-id="0554e-174">Os cmdlets que fazem uma solicitação de conexão incluem Invoke-ASCmd, Backup-ASDatabase e Restore-ASDatabase.</span><span class="sxs-lookup"><span data-stu-id="0554e-174">Cmdlets that make a connection request include Invoke-ASCmd, Backup-ASDatabase, and Restore-ASDatabase.</span></span> <span data-ttu-id="0554e-175">Para esses cmdlets, o parâmetro-Credential pode ser usado, supondo que os critérios a seguir sejam atendidos:</span><span class="sxs-lookup"><span data-stu-id="0554e-175">For these cmdlets, the -Credential parameter can be used, assuming the following criteria are met:</span></span>  
  
1.  <span data-ttu-id="0554e-176">O servidor está configurado para acesso HTTP, o que significa que o IIS trata a conexão, lê o nome de usuário e a senha, e representa a identidade do usuário ao conectar-se ao Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-176">The server is configured for HTTP access, which means that IIS handles the connection, reads the user name and password, and impersonates that user identity when connecting to Analysis Services.</span></span> <span data-ttu-id="0554e-177">Para obter mais informações, consulte [Configurar o acesso HTTP ao Analysis Services no IIS &#40;(Serviços de Informações da Internet)&#41; 8.0](instances/configure-http-access-to-analysis-services-on-iis-8-0.md).</span><span class="sxs-lookup"><span data-stu-id="0554e-177">For more information, see [Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](instances/configure-http-access-to-analysis-services-on-iis-8-0.md).</span></span>  
  
2.  <span data-ttu-id="0554e-178">O diretório virtual IIS que foi criado para acesso HTTP do Analysis Services está configurado para autenticação Básica.</span><span class="sxs-lookup"><span data-stu-id="0554e-178">The IIS virtual directory that was created for Analysis Services HTTP access is configured for Basic authentication.</span></span>  
  
3.  <span data-ttu-id="0554e-179">O nome de usuário e a senha fornecidos pelo objeto de credencial são resolvidos para uma identidade de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="0554e-179">The user name and password provided by the credential object resolves to a Windows user identity.</span></span> <span data-ttu-id="0554e-180">O Analysis Services usa esta identidade como usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0554e-180">Analysis Services uses this identity as the current user.</span></span> <span data-ttu-id="0554e-181">Se o usuário não for Windows ou não tiver permissões suficientes para realizar a operação solicitada, a solicitação falhará.</span><span class="sxs-lookup"><span data-stu-id="0554e-181">If the user is not a Windows user, or lacks sufficient permissions to perform the requested operation, the request will fail.</span></span>  
  
 <span data-ttu-id="0554e-182">Para criar um objeto de credencial, você pode usar o cmdlet Get-Credential para coletar as credenciais do operador.</span><span class="sxs-lookup"><span data-stu-id="0554e-182">To create a credential object, you can use the Get-Credential cmdlet to collect the credentials from the operator.</span></span> <span data-ttu-id="0554e-183">Você poderá então usar o objeto de credencial em um comando que conecta-se ao Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-183">You can then use the credential object on a command that connects to Analysis Services.</span></span> <span data-ttu-id="0554e-184">O exemplo a seguir ilustra a sintaxe uma abordagem.</span><span class="sxs-lookup"><span data-stu-id="0554e-184">The following example illustrates one approach.</span></span> <span data-ttu-id="0554e-185">Neste exemplo, a conexão é para uma instância local ( `SQLSERVER:\SQLAS\HTTP_DS` ) configurada para acesso http.</span><span class="sxs-lookup"><span data-stu-id="0554e-185">In this example, the connection is to a local instance (`SQLSERVER:\SQLAS\HTTP_DS`) configured for HTTP access.</span></span>  
  
```powershell
$cred = Get-Credential adventureworks\dbadmin  
Invoke-ASCmd -Inputfile:"c:\discoverconnections.xmla" -Credential:$cred  
```  
  
 <span data-ttu-id="0554e-186">Ao usar autenticação Básica, você sempre deve usar HTTP com SSL, para que o nome de usuário e as senhas sejam enviados por meio de uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="0554e-186">When using Basic authentication, you should always use HTTPS with SSL so that username and passwords are sent over an encrypted connection.</span></span> <span data-ttu-id="0554e-187">Para obter mais informações, consulte [configurar protocolo SSL no IIS 7,0](https://go.microsoft.com/fwlink/?linkID=184299) e [Configurar a autenticação básica (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=230776).</span><span class="sxs-lookup"><span data-stu-id="0554e-187">For more information, see [Configure Secure Sockets Layer in IIS 7.0](https://go.microsoft.com/fwlink/?linkID=184299) and [Configure Basic Authentication (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=230776).</span></span>  
  
 <span data-ttu-id="0554e-188">Lembre-se de que as credenciais, as consultas e os comandos que você fornecer no PowerShell são passados inalterados para a camada de transporte.</span><span class="sxs-lookup"><span data-stu-id="0554e-188">Remember that credentials, queries, and commands that you provide in PowerShell are passed unchanged to the transport layer.</span></span> <span data-ttu-id="0554e-189">Incluir conteúdo confidencial em seus scripts aumenta o risco de um ataque de injeção mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="0554e-189">Including sensitive content in your scripts increases the risk of a malicious injection attack.</span></span>  
  
 <span data-ttu-id="0554e-190">**Fornecendo uma senha como um objeto Microsoft.Secure.String**</span><span class="sxs-lookup"><span data-stu-id="0554e-190">**Providing a password as a Microsoft.Secure.String object**</span></span>  
  
 <span data-ttu-id="0554e-191">Algumas operações, como backup e restauração, dão suporte a opções de criptografia que são ativadas quando você fornece uma senha no comando.</span><span class="sxs-lookup"><span data-stu-id="0554e-191">Some operations, such as backup and restore, support encryption options that are activated when you provide a password in the command.</span></span> <span data-ttu-id="0554e-192">Fornecer a senha sinaliza ao Analysis Services para criptografar ou descriptografar o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="0554e-192">Providing the password signals Analysis Services to encrypt or decrypt the backup file.</span></span> <span data-ttu-id="0554e-193">No Analysis Services, essa senha é instanciada como um objeto de cadeia de caracteres seguro.</span><span class="sxs-lookup"><span data-stu-id="0554e-193">In Analysis Services, this password is instantiated as a secure string object.</span></span> <span data-ttu-id="0554e-194">O exemplo a seguir fornece uma ilustração de como coletar uma senha do operador em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0554e-194">The following example provides an illustration of how to collect a password from the operator at run time.</span></span>  
  
```powershell
$pwd = read-host -AsSecureString -Prompt "Password"  
$pwd -is [System.IDisposable]  
```  
  
 <span data-ttu-id="0554e-195">Você agora pode fazer backup ou restaurar um arquivo de banco de dados criptografado, passando a variável $pwd para o parâmetro da senha.</span><span class="sxs-lookup"><span data-stu-id="0554e-195">You can now backup or restore an encrypted database file, passing the $pwd variable to the password parameter.</span></span> <span data-ttu-id="0554e-196">Para exibir um exemplo completo que combina essa ilustração com outros cmdlets, confira cmdlet [backup-asdatabase](/powershell/module/sqlserver/backup-asdatabase) e o [cmdlet Restore-asdatabase](/powershell/module/sqlserver/restore-asdatabase).</span><span class="sxs-lookup"><span data-stu-id="0554e-196">To view a complete example that combines this illustration with other cmdlets, see [Backup-ASDatabase cmdlet](/powershell/module/sqlserver/backup-asdatabase) and [Restore-ASDatabase cmdlet](/powershell/module/sqlserver/restore-asdatabase).</span></span>
  
 <span data-ttu-id="0554e-197">Como uma etapa de acompanhamento, remova a senha e a variável da sessão.</span><span class="sxs-lookup"><span data-stu-id="0554e-197">As a follow up step, remove both the password and variable from the session.</span></span>  
  
```powershell
$pwd.Dispose()  
Remove-Variable -Name pwd  
```  
  
##  <a name="analysis-services-powershell-tasks"></a><a name="bkmk_tasks"></a><span data-ttu-id="0554e-198">Analysis Services tarefas do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0554e-198">Analysis Services PowerShell Tasks</span></span>  
 <span data-ttu-id="0554e-199">É possível executar o Analysis Services PowerShell por meio do shell de gerenciamento do Windows PowerShell ou de um prompt de comando do Windows.</span><span class="sxs-lookup"><span data-stu-id="0554e-199">You can run Analysis Services PowerShell from the Windows PowerShell management shell or a Windows command prompt.</span></span> <span data-ttu-id="0554e-200">Não é possível executar o Analysis Services PowerShell por meio do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0554e-200">Running Analysis Services PowerShell from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is not supported.</span></span>  
  
 <span data-ttu-id="0554e-201">Esta seção descreve as tarefas comuns para usar o Analysis Services PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0554e-201">This section describes common tasks for using Analysis Services PowerShell.</span></span>  
  
-   [<span data-ttu-id="0554e-202">Carregar o provedor e cmdlets do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0554e-202">Load the Analysis Services Provider and Cmdlets</span></span>](#bkmk_load)  
  
-   [<span data-ttu-id="0554e-203">Habilitar a administração remota</span><span class="sxs-lookup"><span data-stu-id="0554e-203">Enable Remote Administration</span></span>](#bkmk_remote)  
  
-   [<span data-ttu-id="0554e-204">Conectar-se a um objeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0554e-204">Connect to an Analysis Services Object</span></span>](#bkmk_connect)  
  
-   [<span data-ttu-id="0554e-205">Administrar o serviço</span><span class="sxs-lookup"><span data-stu-id="0554e-205">Administer the Service</span></span>](#bkmk_admin)  
  
-   [<span data-ttu-id="0554e-206">Obter ajuda sobre o Analysis Services PowerShell</span><span class="sxs-lookup"><span data-stu-id="0554e-206">Get Help for Analysis Services PowerShell</span></span>](#bkmk_help)  
  
###  <a name="load-the-analysis-services-provider-and-cmdlets"></a><a name="bkmk_load"></a><span data-ttu-id="0554e-207">Carregar o provedor de Analysis Services e os cmdlets</span><span class="sxs-lookup"><span data-stu-id="0554e-207">Load the Analysis Services Provider and Cmdlets</span></span>  
 <span data-ttu-id="0554e-208">O provedor do Analysis Services é uma extensão do provedor raiz do SQL Server que se torna disponível quando você importa o módulo SQLPS.</span><span class="sxs-lookup"><span data-stu-id="0554e-208">The Analysis Services provider is an extension of the SQL Server root provider that becomes available when you import the SQLPS module.</span></span> <span data-ttu-id="0554e-209">Os cmdlets do Analysis Services são carregados simultaneamente; você também pode carregá-los de forma independente se desejar usá-los sem o provedor.</span><span class="sxs-lookup"><span data-stu-id="0554e-209">Analysis Services cmdlets are loaded simultaneously; you can also load them independently if you want to use them without the provider.</span></span>  
  
-   <span data-ttu-id="0554e-210">Execute o cmdlet Import-module para carregar o SQLPS que inclui toda a funcionalidade do Analysis Services PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0554e-210">Run the Import-module cmdlet to load SQLPS that includes all of the Analysis Services PowerShell functionality.</span></span> <span data-ttu-id="0554e-211">Se você não conseguir importar o módulo, poderá alterar temporariamente a política de execução para irrestrita com a finalidade de carregar o módulo.</span><span class="sxs-lookup"><span data-stu-id="0554e-211">If you cannot import the module, you can temporarily change the execution policy to unrestricted for the purpose of the loading the module.</span></span> <span data-ttu-id="0554e-212">Para obter mais informações, consulte [Importar o módulo SQLPS](../../2014/database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="0554e-212">For more information, see [Import the SQLPS Module](../../2014/database-engine/import-the-sqlps-module.md).</span></span>  
  
    ```powershell
    Import-Module "sqlps"  
    ```  
  
     <span data-ttu-id="0554e-213">Opcionalmente, use `import-module "sqlps" -disablenamechecking` para suprimir o aviso sobre nomes de verbos não aprovados.</span><span class="sxs-lookup"><span data-stu-id="0554e-213">Alternatively, use `import-module "sqlps" -disablenamechecking` to suppress the warning about unapproved verb names.</span></span>  
  
-   <span data-ttu-id="0554e-214">Para carregar apenas os cmdlets do Analysis Services específicos da tarefa, sem o provedor do Analysis Services ou o cmdlet Invoke-ASCmd, é possível carregar o módulo SQLASCmdlets como uma operação independente.</span><span class="sxs-lookup"><span data-stu-id="0554e-214">To load just the task-specific Analysis Services cmdlets, without the Analysis Services provider or the Invoke-ASCmd cmdlet, you can load the SQLASCmdlets module as an independent operation.</span></span>  
  
    ```powershell
    Import-Module "sqlascmdlets"  
    ```  
  
###  <a name="enable-remote-administration"></a><a name="bkmk_remote"></a><span data-ttu-id="0554e-215">Habilitar a administração remota</span><span class="sxs-lookup"><span data-stu-id="0554e-215">Enable Remote Administration</span></span>  
 <span data-ttu-id="0554e-216">Antes de poder usar o Analysis Services PowerShell com uma instância remota do Analysis Services, é necessário primeiramente habilitar a administração remota e o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0554e-216">Before you can use Analysis Services PowerShell with a remote Analysis Services instance, you must first enable remote administration and file sharing.</span></span> <span data-ttu-id="0554e-217">O erro a seguir indica um problema de configuração de firewall: "o servidor RPC não está disponível.</span><span class="sxs-lookup"><span data-stu-id="0554e-217">The following error indicates a firewall configuration issue: "The RPC server is unavailable.</span></span> <span data-ttu-id="0554e-218">(Exceção de HRESULT: 0x800706BA)”.</span><span class="sxs-lookup"><span data-stu-id="0554e-218">(Exception from HRESULT: 0x800706BA)".</span></span>  
  
1.  <span data-ttu-id="0554e-219">Verifique se ambos os computadores local e remoto possuem as versões [!INCLUDE[ssASCurrent](../includes/ssascurrent-md.md)] das ferramentas de cliente e servidor.</span><span class="sxs-lookup"><span data-stu-id="0554e-219">Verify that both local and remote computers have the [!INCLUDE[ssASCurrent](../includes/ssascurrent-md.md)] versions of the client and server tools.</span></span>  
  
2.  <span data-ttu-id="0554e-220">No servidor remoto que está hospedando uma instância do Analysis Services, abra porta TCP 2383 no Firewall do Windows.</span><span class="sxs-lookup"><span data-stu-id="0554e-220">On the remote server that is hosting an Analysis Services instance, open TCP port 2383 in Windows Firewall.</span></span> <span data-ttu-id="0554e-221">Se você instalou o Analysis Services como instância nomeada ou está usando uma porta personalizada, o número da porta será diferente.</span><span class="sxs-lookup"><span data-stu-id="0554e-221">If you installed Analysis Services as a named instance or are using a custom port, the port number will be different.</span></span> <span data-ttu-id="0554e-222">Para obter mais informações, consulte [Configure the Windows Firewall to Allow Analysis Services Access](instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="0554e-222">For more information, see [Configure the Windows Firewall to Allow Analysis Services Access](instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
3.  <span data-ttu-id="0554e-223">No servidor remoto, verifique se os seguintes serviços foram iniciados: serviço RPC (Chamada de Procedimento Remoto), serviço TCP/IP NetBIOS Helper, serviço WMI (Instrumentação de Gerenciamento do Windows), serviço WS-Management (Windows Remote Management).</span><span class="sxs-lookup"><span data-stu-id="0554e-223">On the remote server, verify that the followings services are started:  Remote Procedure Call (RPC) service, TCP/IP NetBIOS Helper service, Windows Management Instrumentation (WMI) service, Windows Remote Management (WS-Management) service.</span></span>  
  
4.  <span data-ttu-id="0554e-224">No servidor remoto, inicie o snap-in do Editor de Objeto de Política de Grupo (gpedit.msc).</span><span class="sxs-lookup"><span data-stu-id="0554e-224">On the remote server, start the Group Policy Object Editor snap-in (gpedit.msc).</span></span>  
  
5.  <span data-ttu-id="0554e-225">Abra: Configuração do Computador, Modelos Administrativos, Rede, Conexões de Rede, Firewall do Windows e Perfil do Domínio.</span><span class="sxs-lookup"><span data-stu-id="0554e-225">Open Computer Configuration, open Administrative Templates, open Network, open Network Connections, open Windows Firewall, and then open Domain Profile.</span></span>  
  
6.  <span data-ttu-id="0554e-226">Clique duas vezes em **Firewall do Windows: permitir exceção de administração remota de entrada**, selecione **habilitado**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0554e-226">Double-click **Windows Firewall: Allow inbound remote administration exception**, select **Enabled**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0554e-227">Clique duas vezes em **Firewall do Windows: permitir a exceção de compartilhamento de arquivos e impressoras de entrada**, selecione **habilitado**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0554e-227">Double-click **Windows Firewall: Allow inbound file and printer sharing exception**, select **Enabled**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="0554e-228">No computador local que tem as ferramentas de cliente, use os cmdlets a seguir para verificar a administração remota, substituindo o nome do servidor real para o espaço reservado de *nome de servidor remoto* .</span><span class="sxs-lookup"><span data-stu-id="0554e-228">On the local computer that has the client tools, use the following cmdlets to verify remote administration, substituting the actual server name for the *remote-server-name* placeholder.</span></span> <span data-ttu-id="0554e-229">Omita o nome da instância se o Analysis Services for instalado como instância padrão.</span><span class="sxs-lookup"><span data-stu-id="0554e-229">Omit the instance name if Analysis Services is installed as the default instance.</span></span> <span data-ttu-id="0554e-230">É necessário ter importado o módulo SQLPS previamente para que o comando funcione.</span><span class="sxs-lookup"><span data-stu-id="0554e-230">You must have previously imported the SQLPS module in order for the command to work.</span></span>  
  
    ```
    PS SQLSERVER:\> cd sqlas
    PS SQLSERVER:\sqlas> cd <remote-server-name\instance-name>  
    PS SQLSERVER:\sqlas\<remote-server-name\instance-name> dir  
    ```  
  
 <span data-ttu-id="0554e-231">Em alguns casos, as configurações adicionais podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="0554e-231">In some cases, additional configuration might be necessary.</span></span> <span data-ttu-id="0554e-232">Talvez seja necessário digitar o seguinte no servidor remoto antes de poder emitir comandos para ele de outro computador:</span><span class="sxs-lookup"><span data-stu-id="0554e-232">You might need to type the following on the remote server before you can issue commands to it from another computer:</span></span>  
  
```powershell
Enable-PSRemoting  
```  
  
  
###  <a name="connect-to-an-analysis-services-object"></a><a name="bkmk_connect"></a><span data-ttu-id="0554e-233">Conectar-se a um objeto Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0554e-233">Connect to an Analysis Services Object</span></span>  
 <span data-ttu-id="0554e-234">O provedor do Analysis Services PowerShell oferece suporte à navegação na hierarquia de objetos do Analysis Services e define o contexto para a execução de comandos.</span><span class="sxs-lookup"><span data-stu-id="0554e-234">The Analysis Services PowerShell provider supports navigation of the Analysis Services object hierarchy and sets the context for running commands.</span></span> <span data-ttu-id="0554e-235">O provedor é uma extensão do provedor raiz SQLSERVER disponível pelo módulo SQLPS.</span><span class="sxs-lookup"><span data-stu-id="0554e-235">The provider is an extension of the SQLSERVER root provider available through the SQLPS module.</span></span> <span data-ttu-id="0554e-236">Depois de carregar o módulo SQLPS, é possível navegar pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="0554e-236">After you load the SQLPS module, you can navigate the path.</span></span>  
  
 <span data-ttu-id="0554e-237">É possível conectar-se a uma instância local ou remota, mas alguns cmdlets são executados somente em uma instância local (isto é, partição de mesclagem).</span><span class="sxs-lookup"><span data-stu-id="0554e-237">You can connect to a local or remote instance, but some cmdlets only run on a local instance (namely, merge-partition).</span></span> <span data-ttu-id="0554e-238">É possível usar uma conexão nativa ou uma conexão HTTP para servidores do Analysis Services que você configurou para acesso HTTP.</span><span class="sxs-lookup"><span data-stu-id="0554e-238">You can use a native connection or an HTTP connection for Analysis Services servers that you configured for HTTP access.</span></span> <span data-ttu-id="0554e-239">As ilustrações a seguir mostram o caminho de navegação para conexões nativas e HTTP.</span><span class="sxs-lookup"><span data-stu-id="0554e-239">The following illustrations show the navigation path for native and HTTP connections.</span></span> <span data-ttu-id="0554e-240">As ilustrações a seguir mostram o caminho de navegação para conexões nativas e HTTP.</span><span class="sxs-lookup"><span data-stu-id="0554e-240">The following illustrations show the navigation path for native and HTTP connections.</span></span>  
  
 <span data-ttu-id="0554e-241">**Conexões nativas com o Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="0554e-241">**Native Connections to Analysis Services**</span></span>  
  
 <span data-ttu-id="0554e-242">![Conexão nativa com o Analysis Services](media/ssas-powershell-nativeconnection.gif "Conexão nativa com o Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="0554e-242">![Native connection to Analysis Services](media/ssas-powershell-nativeconnection.gif "Native connection to Analysis Services")</span></span>  
  
 <span data-ttu-id="0554e-243">O exemplo a seguir é uma demonstração de como usar uma conexão nativa para navegar na hierarquia de objetos.</span><span class="sxs-lookup"><span data-stu-id="0554e-243">The following example is a demonstration of how to use a native connection to navigate object hierarchy.</span></span> <span data-ttu-id="0554e-244">No provedor, é possível emitir `dir` para visualizar informações da instância.</span><span class="sxs-lookup"><span data-stu-id="0554e-244">From the provider, you can issue a `dir` to view instance information.</span></span> <span data-ttu-id="0554e-245">É possível usar `cd` para visualizar objetos dessa instância.</span><span class="sxs-lookup"><span data-stu-id="0554e-245">You can use `cd` to view objects of that instance.</span></span>  
  
```  
PS SQLSERVER:> cd sqlas  
PS SQLSERVER\sqlas:> dir  
PS SQLSERVER\sqlas:> cd localhost\default  
PS SQLSERVER\sqlas\localhost\default:> dir  
```  
  
 <span data-ttu-id="0554e-246">Você deverá ver as seguintes coleções: assemblies, bancos de dados, funções e rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="0554e-246">You should see the following collections: Assemblies, Databases, Roles, and Traces.</span></span> <span data-ttu-id="0554e-247">Se você continuar a usar `cd` e `dir`, poderá visualizar o conteúdo de cada coleção.</span><span class="sxs-lookup"><span data-stu-id="0554e-247">Continuing to use `cd` and `dir`, you can view the contents of each collection.</span></span>  
  
 <span data-ttu-id="0554e-248">**Conexões HTTP com o Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="0554e-248">**HTTP Connections to Analysis Services**</span></span>  
  
 <span data-ttu-id="0554e-249">![Conexão HTTP com o Analysis Services](media/ssas-powershell-httpconnection.gif "Conexão HTTP com o Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="0554e-249">![HTTP Connection to Analysis Services](media/ssas-powershell-httpconnection.gif "HTTP Connection to Analysis Services")</span></span>  
  
 <span data-ttu-id="0554e-250">As conexões HTTP são úteis se você configurou o servidor para acesso HTTP usando as instruções neste tópico: [Configurar o acesso http para Analysis Services em Serviços de Informações da Internet &#40;IIS&#41; 8,0](instances/configure-http-access-to-analysis-services-on-iis-8-0.md)</span><span class="sxs-lookup"><span data-stu-id="0554e-250">HTTP connections are useful if you configured your server for HTTP access using the instructions in this topic: [Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](instances/configure-http-access-to-analysis-services-on-iis-8-0.md)</span></span>  
  
 <span data-ttu-id="0554e-251">Supondo que uma URL de servidor do http://localhost/olap/msmdpump.dll , uma conexão pode ser parecida com a seguinte:</span><span class="sxs-lookup"><span data-stu-id="0554e-251">Assuming a server URL of http://localhost/olap/msmdpump.dll, a connection might look like the following:</span></span>  
  
```  
PS SQLSERVER\sqlas:> cd http_ds  
PS SQLSERVER\sqlas\http_ds:> $Url=Encode-SqlName "http://localhost/olap/msmdpump.dll"  
PS SQLSERVER\sqlas\http_ds:> cd $Url  
PS SQLSERVER\sqlas\http_ds\http%3A%2F%2Flocalhost%2olap%2msmdpump%2Edll:> dir  
```  
  
 <span data-ttu-id="0554e-252">Você deverá ver as seguintes coleções: assemblies, bancos de dados, funções e rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="0554e-252">You should see the following collections: Assemblies, Databases, Roles, and Traces.</span></span> <span data-ttu-id="0554e-253">Se você não conseguir visualizar o conteúdo dessas coleções, verifique as configurações de autenticação no diretório virtual OLAP.</span><span class="sxs-lookup"><span data-stu-id="0554e-253">If you cannot view the contents of these collections, check the authentication settings on the OLAP virtual directory.</span></span> <span data-ttu-id="0554e-254">Certifique-se de que Acesso Anônimo esteja desabilitado.</span><span class="sxs-lookup"><span data-stu-id="0554e-254">Make sure that Anonymous Access is disabled.</span></span> <span data-ttu-id="0554e-255">Se você estiver usando a Autenticação do Windows, verifique se sua conta de usuário do Windows possui permissões administrativas na instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0554e-255">If you are using Windows Authentication, be sure that your Windows user account has administrative permissions on the Analysis Services instance.</span></span>  
  
###  <a name="administer-the-service"></a><a name="bkmk_admin"></a><span data-ttu-id="0554e-256">Administrar o serviço</span><span class="sxs-lookup"><span data-stu-id="0554e-256">Administer the Service</span></span>  
 <span data-ttu-id="0554e-257">Verifique se o serviço está em execução.</span><span class="sxs-lookup"><span data-stu-id="0554e-257">Verify the service is running.</span></span> <span data-ttu-id="0554e-258">Retorna status, nome e nome para exibição dos serviços do SQL Server, incluindo Analysis Services (MSSQLServerOLAPService) e Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="0554e-258">Returns status, name, and display name for SQL Server services, including Analysis Services (MSSQLServerOLAPService) and the Database Engine.</span></span>  
  
```powershell
Get-Service mssql*  
```  
  
 <span data-ttu-id="0554e-259">Retorna as propriedades de um processo, incluindo a ID do processo, contagem de identificadores e uso da memória:</span><span class="sxs-lookup"><span data-stu-id="0554e-259">Returns properties about a process, including process ID, handle count, and memory usage:</span></span>  
  
```powershell
Get-Process msmdsrv  
```  
  
 <span data-ttu-id="0554e-260">Reinicia o serviço ao emitir o seguinte cmdlet a partir do shell de administrador:</span><span class="sxs-lookup"><span data-stu-id="0554e-260">Restarts the service when you issue the following cmdlet from the administrator shell:</span></span>  
  
```powershell
Restart-Service mssqlserverolapservice  
```  
  
###  <a name="get-help-for-analysis-services-powershell"></a><a name="bkmk_help"></a><span data-ttu-id="0554e-261">Obter ajuda para Analysis Services PowerShell</span><span class="sxs-lookup"><span data-stu-id="0554e-261">Get Help for Analysis Services PowerShell</span></span>  
 <span data-ttu-id="0554e-262">Use qualquer um dos cmdlets a seguir para verificar a disponibilidade do cmdlet e obter mais informações sobre serviços, processos e objetos.</span><span class="sxs-lookup"><span data-stu-id="0554e-262">Use any of the following cmdlets to verify cmdlet availability and to get more information about services, processes, and objects.</span></span>  
  
1.  <span data-ttu-id="0554e-263">`Get-Help` retorna a ajuda interna sobre um cmdlet do Analysis Services, incluindo exemplos:</span><span class="sxs-lookup"><span data-stu-id="0554e-263">`Get-Help` returns the built-in help for an Analysis Services cmdlet, including examples:</span></span>  
  
    ```powershell
    Get-Help invoke-ascmd -Examples  
    ```  
  
2.  <span data-ttu-id="0554e-264">`Get-Command` retorna uma lista dos onze cmdlets do Analysis Services PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0554e-264">`Get-Command` returns a list of the eleven Analysis Services PowerShell cmdlets:</span></span>  
  
    ```powershell
    Get-Command -module SQLASCmdlets  
    ```  
  
3.  <span data-ttu-id="0554e-265">`Get-Member` retorna as propriedades ou os métodos de um serviço ou processo.</span><span class="sxs-lookup"><span data-stu-id="0554e-265">`Get-Member` returns properties or methods of a service or process.</span></span>  
  
    ```powershell
    Get-Service mssqlserverolapservice | Get-Member -Type Property  
    ```  
  
    ```powershell
    Get-Service mssqlserverolapservice | Get-Member -Type Method  
    ```  
  
    ```powershell
    Get-Process msmdsrv | Get-Member -Type Property  
    ```  
  
4.  <span data-ttu-id="0554e-266">`Get-Member` também pode ser usado para retornar as propriedades ou os métodos de um objeto (por exemplo, métodos do AMO no objeto de servidor) usando o provedor SQLAS para especificar a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="0554e-266">`Get-Member` can also be used to return properties or methods of an object (for example, AMO methods on the server object) using the SQLAS provider to specify the server instance.</span></span>  
  
    ```
    PS SQLSERVER:\sqlas\localhost\default > $serverObj = New-Object Microsoft.AnalysisServices.Server  
    PS SQLSERVER:\sqlas\localhost\default > $serverObj = | Get-Member -Type Method  
    ```  
  
5.  <span data-ttu-id="0554e-267">`Get-PSdrive` retorna uma lista dos provedores instalados no momento.</span><span class="sxs-lookup"><span data-stu-id="0554e-267">`Get-PSdrive` returns a list of the providers that are currently installed.</span></span> <span data-ttu-id="0554e-268">Se você tiver importado o módulo SQLPS, verá o provedor `SQLServer` na lista (SQLAS faz parte do provedor SQLServer e nunca aparece separadamente na lista):</span><span class="sxs-lookup"><span data-stu-id="0554e-268">If you imported the SQLPS module, you will see the `SQLServer` provider in the list (SQLAS is part of the SQLServer provider and never appears separately in the list):</span></span>  
  
    ```powershell
    Get-PSDrive  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0554e-269">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0554e-269">See Also</span></span>  
 <span data-ttu-id="0554e-270">[Instalar SQL Server PowerShell](../database-engine/install-windows/install-sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="0554e-270">[Install SQL Server PowerShell](../database-engine/install-windows/install-sql-server-powershell.md) </span></span>  
 <span data-ttu-id="0554e-271">[Gerenciar modelos de tabela usando o PowerShell (blog)](https://go.microsoft.com/fwlink/?linkID=227685) </span><span class="sxs-lookup"><span data-stu-id="0554e-271">[Manage Tabular Models Using PowerShell (blog)](https://go.microsoft.com/fwlink/?linkID=227685) </span></span>  
 [<span data-ttu-id="0554e-272">Configurar o acesso HTTP ao Analysis Services no IIS &#40;(Serviços de Informações da Internet)&#41; 8.0</span><span class="sxs-lookup"><span data-stu-id="0554e-272">Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0</span></span>](instances/configure-http-access-to-analysis-services-on-iis-8-0.md)  
  
  
