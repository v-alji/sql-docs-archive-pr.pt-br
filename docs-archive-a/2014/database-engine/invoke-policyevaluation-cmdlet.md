---
title: cmdlet Invoke-PolicyEvaluation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, Invoke-PolicyEvaluation
- Policy-Based Management, PowerShell
- Invoke-PolicyEvaluation cmdlet
- Cmdlets [SQL Server], Invoke-PolicyEvaluation
- PowerShell [SQL Server], Invoke-PolicyEvaluation
ms.assetid: 3e6d4f5a-59b7-4203-b95a-f7e692c0f131
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 656fdffea191c9cf6fc42d860164bc5af1e04561
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680056"
---
# <a name="invoke-policyevaluation-cmdlet"></a><span data-ttu-id="cd2d2-102">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="cd2d2-102">Invoke-PolicyEvaluation cmdlet</span></span>
  <span data-ttu-id="cd2d2-103">O**Invoke-PolicyEvaluation** é um cmdlet do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que relata se um conjunto de objetos SQL Server de destino é compatível com as condições especificadas em uma ou mais políticas do Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-103">**Invoke-PolicyEvaluation** is a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlet that reports whether a target set of SQL Server objects complies with the conditions specified in one or more Policy-Based Management policies.</span></span>  
  
## <a name="using-invoke-policyevaluation"></a><span data-ttu-id="cd2d2-104">Usando Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="cd2d2-104">Using Invoke-PolicyEvaluation</span></span>  
 <span data-ttu-id="cd2d2-105">O**Invoke-PolicyEvaluation** avalia uma ou mais políticas em relação a um conjunto de objetos SQL Server, chamado conjunto de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-105">**Invoke-PolicyEvaluation** evaluates one or more policies against a set of SQL Server objects called the target set.</span></span> <span data-ttu-id="cd2d2-106">O conjunto de objetos de destino origina-se em um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-106">The set of target objects comes from a target server.</span></span> <span data-ttu-id="cd2d2-107">Cada política define condições, as quais são os estados permitidos dos objetos de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-107">Each policy defines conditions, which are the allowed states for the target objects.</span></span> <span data-ttu-id="cd2d2-108">Por exemplo, a política **Banco de Dados Confiável** declara que a propriedade TRUSTWORTHY do banco de dados deve ser definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-108">For example, the **Trustworthy Database** policy states that the TRUSTWORTHY database property must be set to OFF.</span></span>  
  
 <span data-ttu-id="cd2d2-109">O parâmetro **-AdHocPolicyEvaluationMode** especifica as ações tomadas:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-109">The **-AdHocPolicyEvaluationMode** parameter specifies the actions taken:</span></span>  
  
 <span data-ttu-id="cd2d2-110">Verificação</span><span class="sxs-lookup"><span data-stu-id="cd2d2-110">Check</span></span>  
 <span data-ttu-id="cd2d2-111">Relate o status de conformidade dos objetos de destino que usam as credenciais do seu logon atual.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-111">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="cd2d2-112">Não reconfigure nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-112">Do no reconfigure any objects.</span></span> <span data-ttu-id="cd2d2-113">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-113">This is the default setting.</span></span>  
  
 <span data-ttu-id="cd2d2-114">CheckSqlScriptAsProxy</span><span class="sxs-lookup"><span data-stu-id="cd2d2-114">CheckSqlScriptAsProxy</span></span>  
 <span data-ttu-id="cd2d2-115">Relate o status de conformidade dos objetos de destino que usam as credenciais do logon de proxy **##MS_PolicyTSQLExecutionLogin##** .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-115">Report the compliance status of the target objects using the credentials of the **##MS_PolicyTSQLExecutionLogin##** proxy login.</span></span> <span data-ttu-id="cd2d2-116">Não reconfigure nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-116">Do no reconfigure any objects.</span></span>  
  
 <span data-ttu-id="cd2d2-117">Configurar</span><span class="sxs-lookup"><span data-stu-id="cd2d2-117">Configure</span></span>  
 <span data-ttu-id="cd2d2-118">Relate o status de conformidade dos objetos de destino que usam as credenciais do seu logon atual.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-118">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="cd2d2-119">Reconfigure qualquer opção definível e determinística que não estejam em conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-119">Reconfigure any settable and deterministic options that are not in compliance with the policies.</span></span>  
  
## <a name="specifying-polices"></a><span data-ttu-id="cd2d2-120">Especificando políticas</span><span class="sxs-lookup"><span data-stu-id="cd2d2-120">Specifying Polices</span></span>  
 <span data-ttu-id="cd2d2-121">A forma como você especifica uma política depende de onde ela está armazenada.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-121">How you specify a policy depends on where the policy is stored.</span></span> <span data-ttu-id="cd2d2-122">As políticas podem ser armazenadas em dois formatos:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-122">Policies can be stored in two formats:</span></span>  
  
-   <span data-ttu-id="cd2d2-123">Elas podem ser objetos armazenados em um repositório de política, como, por exemplo, uma instância do Mecanismo do Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-123">They can be objects stored in a policy store, such as an instance of the Database Engine.</span></span> <span data-ttu-id="cd2d2-124">Você pode usar a pasta SQLSERVER:\SQLPolicy para especificar o local de políticas em um repositório de políticas.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-124">You can use the SQLSERVER:\SQLPolicy folder to specify the location of policies in a policy store.</span></span> <span data-ttu-id="cd2d2-125">Você pode usar cmdlets Windows PowerShell para filtrar as diretivas de entrada com base em suas propriedades, como, por exemplo, o uso de Where-Object para filtrar na categoria da diretiva ou Get-Item para filtrar no nome da diretiva.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-125">You can use Windows PowerShell cmdlets to filter the input polices based on their properties, such as using Where-Object to filter on the policy category or Get-Item to filter on policy name.</span></span>  
  
-   <span data-ttu-id="cd2d2-126">Eles podem ser exportados como arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-126">They can be exported as XML files.</span></span> <span data-ttu-id="cd2d2-127">Você pode usar uma unidade de sistema de arquivos, por exemplo D:, para especificar o local dos arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-127">You can use a file system drive, such as D:, to specify the location of the XML files.</span></span> <span data-ttu-id="cd2d2-128">Você pode usar cmdlets Windows PowerShell, por exemplo Where-Object, para filtrar as diretivas nas propriedades de arquivo, como, por exemplo, nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-128">You can use Windows PowerShell cmdlets such as Where-Object to filter the policies on their file properties, such as file name.</span></span>  
  
 <span data-ttu-id="cd2d2-129">Se as políticas estiverem armazenadas em um repositório de políticas, você deverá passar um conjunto de PSObjects que aponte para as políticas a serem avaliadas.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-129">If the policies are stored in a policy store, you must pass in a set of PSObjects pointing to the policies to be evaluated.</span></span> <span data-ttu-id="cd2d2-130">Em geral, isso é feito indicando a saída de um cmdlet, por exemplo, Get-Item para **Invoke-PolicyEvaluation**e não exige que você especifique o parâmetro **-Policy** .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-130">This is typically done by piping the output of a cmdlet such as Get-Item to **Invoke-PolicyEvaluation**, and does not require that you specify the **-Policy** parameter.</span></span> <span data-ttu-id="cd2d2-131">Por exemplo, se você importou as políticas do Microsoft Best Practices para sua instância do mecanismo de banco de dados, esse comando avalia a política **Status do Banco de Dados** :</span><span class="sxs-lookup"><span data-stu-id="cd2d2-131">For example, if you have imported the Microsoft Best Practices policies into your instance of the database engine, this command evaluates the **Database Status** policy:</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Get-Item "Database Status" | Invoke-PolicyEvaluation -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="cd2d2-132">Este exemplo mostra o uso de Where-Object para filtrar várias políticas de um repositório de políticas com base na propriedade **PolicyCategory** .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-132">This example shows using Where-Object to filter multiple policies from a policy store based on their **PolicyCategory** property.</span></span> <span data-ttu-id="cd2d2-133">Os objetos da saída indicada de **Where-Object** são consumidos por **Invoke-PolicyEvaluation**.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-133">The objects from the piped output of **Where-Object** is consumed by **Invoke-PolicyEvaluation**.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
gci | Where-Object {$_.PolicyCategory -eq "Microsoft Best Practices: Maintenance"} | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
 <span data-ttu-id="cd2d2-134">Se as políticas forem armazenadas como arquivos XML, use o parâmetro **-Policy** para fornecer o caminho e o nome de cada política.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-134">If the policies are stored as XML files, you must use the **-Policy** parameter to supply both the path and name for each policy.</span></span> <span data-ttu-id="cd2d2-135">Se você não especificar um caminho no parâmetro **-Policy** , **Invoke-PolicyEvaulation** usará a configuração atual do caminho **sqlps** .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-135">If you do not specify a path in the **-Policy** parameter, **Invoke-PolicyEvaulation** uses the current setting of the **sqlps** path.</span></span> <span data-ttu-id="cd2d2-136">Por exemplo, este comando avalia uma das políticas do Microsoft Best Practice instaladas com SQL Server no banco de dados padrão para seu logon:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-136">For example, this command evaluates one of the Microsoft Best Practice policies installed with SQL Server against the default database for your login:</span></span>  
  
```powershell
Invoke-PolicyEvaluation -Policy "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033\Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="cd2d2-137">Esse comando faz a mesma coisa, apenas usa o caminho **sqlps** atual para estabelecer o local do arquivo XML da política:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-137">This command does the same thing, only it uses the current **sqlps** path to establish the location of the policy XML file:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="cd2d2-138">Esse exemplo mostra o uso do cmdlet **Get-ChildItem** para recuperar vários arquivos XML de políticas e indicar os objetos em **Invoke-PolicyEvaluation**:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-138">This example shows using the **Get-ChildItem** cmdlet to retrieve multiple policy XML files and pipe the objects into **Invoke-PolicyEvaluation**:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
gci "Database Status.xml", "Trustworthy Database.xml" | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
## <a name="specifying-the-target-set"></a><span data-ttu-id="cd2d2-139">Especificando o conjunto de destino</span><span class="sxs-lookup"><span data-stu-id="cd2d2-139">Specifying the Target Set</span></span>  
 <span data-ttu-id="cd2d2-140">Use três parâmetros para especificar o conjunto de objetos de destino:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-140">Use three parameters to specify the set of target objects:</span></span>  
  
-   <span data-ttu-id="cd2d2-141">O **-TargetServerName** especifica a instância do SQL Server que contém os objetos de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-141">**-TargetServerName** specifies the instance of SQL Server containing the target objects.</span></span> <span data-ttu-id="cd2d2-142">Você pode especificar as informações em uma cadeia de caracteres que use o formato definido para a propriedade ConnectionString da classe <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-142">You can specify the information in a string that uses the format defined for the ConnectionString property of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="cd2d2-143">Você pode usar a classe <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para criar uma cadeia de conexão formatada corretamente.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-143">You can use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to build a correctly formatted connection string.</span></span> <span data-ttu-id="cd2d2-144">Você pode criar também um objeto <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> e transmiti-lo para **-TargetServer**.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-144">You can also create a <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> object and pass it to **-TargetServer**.</span></span> <span data-ttu-id="cd2d2-145">Se você fornecer uma cadeia de caracteres que tenha apenas o nome do servidor, **Invoke-PolicyEvaluation** usará a Autenticação do Windows para se conectar ao servidor.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-145">If you supply a string that has only the name of the server, **Invoke-PolicyEvaluation** uses Windows Authentication to connect to the server.</span></span>  
  
-   <span data-ttu-id="cd2d2-146">O **-TargetObjects** utiliza um objeto ou uma matriz de objetos que representam os objetos SQL Server no conjunto de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-146">**-TargetObjects** takes an object or array of objects that represent the SQL Server objects in the target set.</span></span> <span data-ttu-id="cd2d2-147">Por exemplo, você pode criar uma matriz de objetos da classe <xref:Microsoft.SqlServer.Management.Smo.Database> para transmitir para **-TargetObjects**.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-147">For example, you could create an array of <xref:Microsoft.SqlServer.Management.Smo.Database> class objects to pass in to **-TargetObjects**.</span></span>  
  
-   <span data-ttu-id="cd2d2-148">O **-TargetExpressions** utiliza uma cadeia de caracteres que contém uma expressão de consulta que especifica os objetos no conjunto de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-148">**-TargetExpressions** takes a string containing a query expression that specifies the objects in the target set.</span></span> <span data-ttu-id="cd2d2-149">A expressão de consulta está na forma de nós separados pelo caractere '/'.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-149">The query expression is in the form of nodes separated by the '/' character.</span></span> <span data-ttu-id="cd2d2-150">Cada nó está na forma ObjectType[Filtro].</span><span class="sxs-lookup"><span data-stu-id="cd2d2-150">Each node is in the form ObjectType[Filter].</span></span> <span data-ttu-id="cd2d2-151">O tipo de objeto é um dos objetos em uma hierarquia de objetos do SMO (SQL Server Management Object).</span><span class="sxs-lookup"><span data-stu-id="cd2d2-151">Object type is one of the objects in a SQL Server Management Object (SMO) object hierarchy.</span></span> <span data-ttu-id="cd2d2-152">O filtro é uma expressão que filtra objetos desse nó.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-152">Filter is an expression that filters for objects at that node.</span></span> <span data-ttu-id="cd2d2-153">Para obter mais informações, consulte [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="cd2d2-153">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
 <span data-ttu-id="cd2d2-154">Especifique **-TargetObjects** ou **-TargetExpression**, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-154">Specify either **-TargetObjects** or **-TargetExpression**, not both.</span></span>  
  
 <span data-ttu-id="cd2d2-155">Este exemplo usa um objeto Sfc.SqlStoreConnection para especificar o servidor de destino:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-155">This example uses an Sfc.SqlStoreConnection object to specify the target server:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
$conn = New-Object Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection("server='MYCOMPUTER';Trusted_Connection=True")  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName $conn  
```  
  
 <span data-ttu-id="cd2d2-156">Este exemplo usa **-TargetExpression** para identificar o banco de dados específico a avaliar:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-156">This example uses **-TargetExpression** to identify the specific database to evaluate:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MyComputer" -TargetExpression "Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']"  
```  
  
## <a name="evaluating-analysis-services-policies"></a><span data-ttu-id="cd2d2-157">Avaliando políticas do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cd2d2-157">Evaluating Analysis Services Policies</span></span>  
 <span data-ttu-id="cd2d2-158">Para avaliar as políticas com base em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], carregue e registre um assembly no PowerShell, crie uma variável com o objeto de conexão do Analysis Services e passe a variável para o parâmetro **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-158">To evaluate policies against an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you must load and register an assembly into PowerShell, create a variable with an Analysis Services connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="cd2d2-159">Este exemplo mostra como avaliar a política de configuração da área da superfície das Práticas Recomendadas para o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-159">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\AnalysisServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.AnalysisServices")  
$SSASsvr = New-Object Microsoft.AnalysisServices.Server  
$SSASsvr.Connect("Data Source=Localhost")  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Analysis Services Features.xml" -TargetObject $SSASsvr  
```  
  
## <a name="evaluating-reporting-services-policies"></a><span data-ttu-id="cd2d2-160">Avaliando políticas do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cd2d2-160">Evaluating Reporting Services Policies</span></span>  
 <span data-ttu-id="cd2d2-161">Para avaliar as políticas do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , carregue e registre um assembly no PowerShell, crie uma variável com um objeto de conexão do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e passe a variável para o parâmetro **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="cd2d2-161">To evaluate [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] policies, you must load and register an assembly into PowerShell, create a variable with a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="cd2d2-162">Este exemplo mostra como avaliar a política de configuração da área da superfície das Práticas Recomendadas para o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cd2d2-162">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\ReportingServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Dmf.Adapters")  
$SSRSsvr = new-object Microsoft.SqlServer.Management.Adapters.RSContainer('MyComputer')  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Reporting Services 2008 Features.xml" -TargetObject $SSRSsvr  
```  
  
## <a name="formatting-output"></a><span data-ttu-id="cd2d2-163">Formatando a saída</span><span class="sxs-lookup"><span data-stu-id="cd2d2-163">Formatting Output</span></span>  
 <span data-ttu-id="cd2d2-164">Por padrão, a saída de **Invoke-PolicyEvaluation** é exibida na janela do prompt de comando como um relatório conciso em formato legível.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-164">By default, the output of **Invoke-PolicyEvaluation** is displayed in the command prompt window as a concise report in human-readable format.</span></span> <span data-ttu-id="cd2d2-165">Você pode usar o parâmetro **-OutputXML** para especificar que, em vez disso, o cmdlet deve produzir um relatório detalhado como um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-165">You can use the **-OutputXML** parameter to specify that the cmdlet instead produce a detailed report as an XML file.</span></span> <span data-ttu-id="cd2d2-166">**Invoke-PolicyEvaluation** usa o esquema SML-IF (Systems Modeling Language Interchange Format) para que o arquivo possa ser lido por leitores de SML-IF.</span><span class="sxs-lookup"><span data-stu-id="cd2d2-166">**Invoke-PolicyEvaluation** uses the Systems Modeling Language Interchange Format (SML-IF) schema so the file can be read by SML-IF readers.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Invoke-PolicyEvaluation -Policy "Datbase Status" -TargetServer "MYCOMPUTER" -OutputXML > C:\MyReports\DatabaseStatusReport.xml  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd2d2-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd2d2-167">See Also</span></span>  
 [<span data-ttu-id="cd2d2-168">Usar cmdlets do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="cd2d2-168">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
