---
title: Navegar em caminhos do PowerShell SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: d68aca48-d161-45ed-9f4f-14122ed30218
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a605479991c3e907cd9dcae254cc1bc04a49392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685195"
---
# <a name="navigate-sql-server-powershell-paths"></a><span data-ttu-id="cf60c-102">Navegar em caminhos do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf60c-102">Navigate SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="cf60c-103">O provedor do [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell expõe o conjunto de objetos em uma instância do SQL Server em uma estrutura semelhante a um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="cf60c-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell provider exposes the set of objects in an instance of SQL Server in a structure similar to a file path.</span></span> <span data-ttu-id="cf60c-104">Você pode usar cmdlets do Windows PowerShell para navegar até o caminho do provedor e criar unidades personalizadas para encurtar o caminho que você tem que digitar.</span><span class="sxs-lookup"><span data-stu-id="cf60c-104">You can use Windows PowerShell cmdlets to navigate the provider path, and create custom drives to shorten the path you have to type.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="cf60c-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cf60c-105">Before You Begin</span></span>  
 <span data-ttu-id="cf60c-106">O Windows PowerShell implementa cmdlets para navegar na estrutura do caminho que representa a hierarquia de objetos por um provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf60c-106">Windows PowerShell implements cmdlets to navigate the path structure that represent the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="cf60c-107">Ao navegar até um nó do caminho, você pode usar outros cmdlets para executar operações básicas no objeto atual.</span><span class="sxs-lookup"><span data-stu-id="cf60c-107">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span> <span data-ttu-id="cf60c-108">Como os cmdlets são usados com frequência, eles têm aliases pequenos e canônicos.</span><span class="sxs-lookup"><span data-stu-id="cf60c-108">Because the cmdlets are used frequently, they have short, canonical aliases.</span></span> <span data-ttu-id="cf60c-109">Também existe um conjunto de aliases que mapeia os cmdlets para comandos semelhantes do prompt de comando e outro conjunto para comandos shell do UNIX.</span><span class="sxs-lookup"><span data-stu-id="cf60c-109">There is also one set of aliases that maps the cmdlets to similar command prompt commands, and another set for UNIX shell commands.</span></span>  
  
 <span data-ttu-id="cf60c-110">O provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implementa um subconjunto de cmdlets do provedor, mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf60c-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements a subset of the provider cmdlets, shown in the following table.</span></span>  
  
|<span data-ttu-id="cf60c-111">cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf60c-111">cmdlet</span></span>|<span data-ttu-id="cf60c-112">Alias canônico</span><span class="sxs-lookup"><span data-stu-id="cf60c-112">Canonical alias</span></span>|<span data-ttu-id="cf60c-113">Alias de cmd</span><span class="sxs-lookup"><span data-stu-id="cf60c-113">cmd alias</span></span>|<span data-ttu-id="cf60c-114">Alias de shell do UNIX</span><span class="sxs-lookup"><span data-stu-id="cf60c-114">UNIX shell alias</span></span>|<span data-ttu-id="cf60c-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="cf60c-115">Description</span></span>|  
|------------|---------------------|---------------|----------------------|-----------------|  
|<span data-ttu-id="cf60c-116">**Get-Location**</span><span class="sxs-lookup"><span data-stu-id="cf60c-116">**Get-Location**</span></span>|<span data-ttu-id="cf60c-117">**gl**</span><span class="sxs-lookup"><span data-stu-id="cf60c-117">**gl**</span></span>|<span data-ttu-id="cf60c-118">**pwd**</span><span class="sxs-lookup"><span data-stu-id="cf60c-118">**pwd**</span></span>|<span data-ttu-id="cf60c-119">**pwd**</span><span class="sxs-lookup"><span data-stu-id="cf60c-119">**pwd**</span></span>|<span data-ttu-id="cf60c-120">Obtém o nó atual.</span><span class="sxs-lookup"><span data-stu-id="cf60c-120">Gets the current node.</span></span>|  
|`Set-Location`|<span data-ttu-id="cf60c-121">**SL**</span><span class="sxs-lookup"><span data-stu-id="cf60c-121">**sl**</span></span>|<span data-ttu-id="cf60c-122">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="cf60c-122">**cd, chdir**</span></span>|<span data-ttu-id="cf60c-123">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="cf60c-123">**cd, chdir**</span></span>|<span data-ttu-id="cf60c-124">Altera o nó atual.</span><span class="sxs-lookup"><span data-stu-id="cf60c-124">Changes the current node.</span></span>|  
|<span data-ttu-id="cf60c-125">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="cf60c-125">**Get-ChildItem**</span></span>|<span data-ttu-id="cf60c-126">**gci**</span><span class="sxs-lookup"><span data-stu-id="cf60c-126">**gci**</span></span>|<span data-ttu-id="cf60c-127">**dir**</span><span class="sxs-lookup"><span data-stu-id="cf60c-127">**dir**</span></span>|<span data-ttu-id="cf60c-128">**ls**</span><span class="sxs-lookup"><span data-stu-id="cf60c-128">**ls**</span></span>|<span data-ttu-id="cf60c-129">Lista os objetos armazenados no nó atual.</span><span class="sxs-lookup"><span data-stu-id="cf60c-129">Lists the objects stored at the current node.</span></span>|  
|<span data-ttu-id="cf60c-130">**Get-Item**</span><span class="sxs-lookup"><span data-stu-id="cf60c-130">**Get-Item**</span></span>|<span data-ttu-id="cf60c-131">**gi**</span><span class="sxs-lookup"><span data-stu-id="cf60c-131">**gi**</span></span>|||<span data-ttu-id="cf60c-132">Retorna as propriedades do item atual.</span><span class="sxs-lookup"><span data-stu-id="cf60c-132">Returns the properties of the current item.</span></span>|  
|<span data-ttu-id="cf60c-133">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="cf60c-133">**Rename-Item**</span></span>|<span data-ttu-id="cf60c-134">**rni**</span><span class="sxs-lookup"><span data-stu-id="cf60c-134">**rni**</span></span>|<span data-ttu-id="cf60c-135">**RN**</span><span class="sxs-lookup"><span data-stu-id="cf60c-135">**rn**</span></span>|<span data-ttu-id="cf60c-136">**ren**</span><span class="sxs-lookup"><span data-stu-id="cf60c-136">**ren**</span></span>|<span data-ttu-id="cf60c-137">Renomeia um objeto.</span><span class="sxs-lookup"><span data-stu-id="cf60c-137">Renames an object.</span></span>|  
|<span data-ttu-id="cf60c-138">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="cf60c-138">**Remove-Item**</span></span>|<span data-ttu-id="cf60c-139">**ri**</span><span class="sxs-lookup"><span data-stu-id="cf60c-139">**ri**</span></span>|<span data-ttu-id="cf60c-140">**del, rd**</span><span class="sxs-lookup"><span data-stu-id="cf60c-140">**del, rd**</span></span>|<span data-ttu-id="cf60c-141">**rm, rmdir**</span><span class="sxs-lookup"><span data-stu-id="cf60c-141">**rm, rmdir**</span></span>|<span data-ttu-id="cf60c-142">Remove um objeto.</span><span class="sxs-lookup"><span data-stu-id="cf60c-142">Removes an object.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cf60c-143">Alguns identificadores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (nomes de objeto) contêm caracteres não suportados pelos nomes de caminho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf60c-143">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers (object names) contain characters that Windows PowerShell does not support in path names.</span></span> <span data-ttu-id="cf60c-144">Para obter mais informações sobre como usar os nomes que contêm esses caracteres, consulte [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cf60c-144">For more information about how to use names that contain these characters, see [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span></span>  
  
### <a name="sql-server-information-returned-by-get-childitem"></a><span data-ttu-id="cf60c-145">Informações do SQL Server retornadas por Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="cf60c-145">SQL Server Information Returned by Get-ChildItem</span></span>  
 <span data-ttu-id="cf60c-146">A informações retornadas por **Get-ChildItem** (ou seus aliases **dir** e **ls** ) dependem de seu local em um caminho SQLSERVER:.</span><span class="sxs-lookup"><span data-stu-id="cf60c-146">The information returned by **Get-ChildItem** (or its **dir** and **ls** aliases) depends on your location in a SQLSERVER: path.</span></span>  
  
|<span data-ttu-id="cf60c-147">Local do caminho</span><span class="sxs-lookup"><span data-stu-id="cf60c-147">Path location</span></span>|<span data-ttu-id="cf60c-148">Resultados de Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="cf60c-148">Get-ChildItem results</span></span>|  
|-------------------|----------------------------|  
|<span data-ttu-id="cf60c-149">SQLSERVER:\SQL</span><span class="sxs-lookup"><span data-stu-id="cf60c-149">SQLSERVER:\SQL</span></span>|<span data-ttu-id="cf60c-150">Retorna o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="cf60c-150">Returns the name of the local computer.</span></span> <span data-ttu-id="cf60c-151">Se você usou o SMO ou o WMI para se conectar às instâncias do [!INCLUDE[ssDE](../includes/ssde-md.md)] em outros computadores, esses computadores também estarão listados.</span><span class="sxs-lookup"><span data-stu-id="cf60c-151">If you have used the SMO or WMI to connect to instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on other computers, those computers are also listed.</span></span>|  
|<span data-ttu-id="cf60c-152">SQLSERVER: \ SQL \\ *ComputerName*</span><span class="sxs-lookup"><span data-stu-id="cf60c-152">SQLSERVER:\SQL\\*ComputerName*</span></span>|<span data-ttu-id="cf60c-153">A lista de instâncias do [!INCLUDE[ssDE](../includes/ssde-md.md)] no computador.</span><span class="sxs-lookup"><span data-stu-id="cf60c-153">The list of instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on the computer.</span></span>|  
|<span data-ttu-id="cf60c-154">SqlServer: \ SQL \\ *ComputerName* \\ *InstanceName*</span><span class="sxs-lookup"><span data-stu-id="cf60c-154">SQLSERVER:\SQL\\*ComputerName*\\*InstanceName*</span></span>|<span data-ttu-id="cf60c-155">A lista de tipos de objeto de nível superior na instância, como Pontos de Extremidade, Certificados e Bancos de Dados.</span><span class="sxs-lookup"><span data-stu-id="cf60c-155">The list of top-level object types in the instance, such as Endpoints, Certificates, and Databases.</span></span>|  
|<span data-ttu-id="cf60c-156">Nó da classe de objeto, como Bancos de Dados</span><span class="sxs-lookup"><span data-stu-id="cf60c-156">Object class node, such as Databases</span></span>|<span data-ttu-id="cf60c-157">A lista de objetos desse tipo, como a lista de bancos de dados: master, model, AdventureWorks20008R2.</span><span class="sxs-lookup"><span data-stu-id="cf60c-157">The list of objects of that type, such as the list of databases: master, model, AdventureWorks20008R2.</span></span>|  
|<span data-ttu-id="cf60c-158">Nó do nome de objeto, como AdventureWorks2012</span><span class="sxs-lookup"><span data-stu-id="cf60c-158">Object name node, such as AdventureWorks2012</span></span>|<span data-ttu-id="cf60c-159">A lista de tipos de objeto contida no objeto.</span><span class="sxs-lookup"><span data-stu-id="cf60c-159">The list of object types contained within the object.</span></span> <span data-ttu-id="cf60c-160">Por exemplo, um banco de dados poderia listar tipos de objeto, como tabelas e exibições.</span><span class="sxs-lookup"><span data-stu-id="cf60c-160">For example, a database would list object types such as tables and views.</span></span>|  
  
 <span data-ttu-id="cf60c-161">Por padrão, **Get-ChildItem** não lista nenhum objeto de sistema.</span><span class="sxs-lookup"><span data-stu-id="cf60c-161">By default, **Get-ChildItem** does not list any system objects.</span></span> <span data-ttu-id="cf60c-162">Use o parâmetro *Force* para ver objetos de sistema, como os objetos no esquema **sys** .</span><span class="sxs-lookup"><span data-stu-id="cf60c-162">Use the *Force* parameter to see system objects, such as the objects in the **sys** schema.</span></span>  
  
### <a name="custom-drives"></a><span data-ttu-id="cf60c-163">Unidades personalizadas</span><span class="sxs-lookup"><span data-stu-id="cf60c-163">Custom Drives</span></span>  
 <span data-ttu-id="cf60c-164">O Windows PowerShell permite que os usuários definam unidades virtuais que são conhecidas como unidades PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf60c-164">Windows PowerShell lets users define virtual drives, which are referred to as PowerShell drives.</span></span> <span data-ttu-id="cf60c-165">Elas mapeiam os nós iniciais de uma instrução de caminho.</span><span class="sxs-lookup"><span data-stu-id="cf60c-165">These map over the starting nodes of a path statement.</span></span> <span data-ttu-id="cf60c-166">Em geral, elas são usadas para encurtar caminhos que são digitados com frequência.</span><span class="sxs-lookup"><span data-stu-id="cf60c-166">They are typically used to shorten paths that are typed frequently.</span></span> <span data-ttu-id="cf60c-167">SQLSERVER: os caminhos podem se tornar longos, ocupando muito espaço na janela do Windows PowerShell e exigindo muita digitação.</span><span class="sxs-lookup"><span data-stu-id="cf60c-167">SQLSERVER: paths can get long, taking space in the Windows PowerShell window and requiring a lot of typing.</span></span> <span data-ttu-id="cf60c-168">Se você vai trabalhar muito em um nó de caminho específico, é possível definir uma unidade personalizada do Windows PowerShell mapeada para esse nó.</span><span class="sxs-lookup"><span data-stu-id="cf60c-168">If you are going to do a lot of work at a particular path node, you can define a custom Windows PowerShell drive that maps to that node.</span></span>  
  
## <a name="use-powershell-cmdlet-aliases"></a><span data-ttu-id="cf60c-169">Usar aliases de cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf60c-169">Use PowerShell Cmdlet Aliases</span></span>  
 <span data-ttu-id="cf60c-170">**Usar um alias de cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cf60c-170">**Use a cmdlet alias**</span></span>  
  
-   <span data-ttu-id="cf60c-171">Em vez de digitar um nome de cmdlet completo, digite um alias mais curto ou um que mapeia para um prompt de comando familiar.</span><span class="sxs-lookup"><span data-stu-id="cf60c-171">Instead of typing a full cmdlet name, type a shorter alias, or one that maps to a familiar commend prompt command.</span></span>  
  
### <a name="alias-example-powershell"></a><span data-ttu-id="cf60c-172">Exemplo de alias (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cf60c-172">Alias Example (PowerShell)</span></span>  
 <span data-ttu-id="cf60c-173">Por exemplo, você pode usar um dos conjuntos de cmdlets ou aliases a seguir para recuperar uma listagem das instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] disponíveis navegando para a pasta SQLSERVER:\SQL e solicitando a lista de itens filho da pasta:</span><span class="sxs-lookup"><span data-stu-id="cf60c-173">For example, you can use one of the following sets of cmdlets or aliases to retrieve a listing of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances available to you by navigating to the SQLSERVER:\SQL folder and requesting the list of child items for the folder:</span></span>  
  
```powershell
## Shows using the full cmdet name.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## Shows using canonical aliases.  
sl SQLSERVER:\SQL  
gci  
  
## Shows using command prompt aliases.  
cd SQLSERVER:\SQL  
dir  
  
## Shows using Unix shell aliases.  
cd SQLSERVER:\SQL  
ls  
```  
  
## <a name="use-get-childitem"></a><span data-ttu-id="cf60c-174">Usar Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="cf60c-174">Use Get-ChildItem</span></span>  

### <a name="return-information-by-using-get-childitem"></a><span data-ttu-id="cf60c-175">Retornar informações usando Get-Childitem</span><span class="sxs-lookup"><span data-stu-id="cf60c-175">Return information by using Get-Childitem</span></span>
  
1.  <span data-ttu-id="cf60c-176">Navegue até o nó para o qual você deseja uma lista de childrem</span><span class="sxs-lookup"><span data-stu-id="cf60c-176">Navigate to the node for which you want a list of childrem</span></span>  
  
2.  <span data-ttu-id="cf60c-177">Execute Get-Childitem para obter a lista.</span><span class="sxs-lookup"><span data-stu-id="cf60c-177">Run Get-Childitem to get the list.</span></span>  
  
### <a name="get-childitem-example-powershell"></a><span data-ttu-id="cf60c-178">Exemplo de Get-ChildItem (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cf60c-178">Get-ChildItem Example (PowerShell)</span></span>  
 <span data-ttu-id="cf60c-179">Estes exemplos ilustram as informações retornadas por Get-Childitem para nós diferentes em um caminho de provedor do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf60c-179">These examples illustrate the information returned by Get-Childitem for different nodes in a SQL Server provider path.</span></span>  
  
```powershell
## Return the current computer and any computer  
## to which you have made a SQL or WMI connection.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## List the instances of the Database Engine on the local computer.  
Set-Location SQLSERVER:\SQL\localhost  
Get-ChildItem  
  
## Lists the categories of objects available in the  
## default instance on the local computer.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT  
Get-ChildItem  
  
## Lists the databases from the local default instance.  
## The force parameter is used to include the system databases.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-ChildItem -force  
```  
  
## <a name="create-a-custom-drive"></a><span data-ttu-id="cf60c-180">Criar uma unidade personalizada</span><span class="sxs-lookup"><span data-stu-id="cf60c-180">Create a Custom Drive</span></span>  

### <a name="create-and-use-a-custom-drive"></a><span data-ttu-id="cf60c-181">Criar e usar uma unidade personalizada</span><span class="sxs-lookup"><span data-stu-id="cf60c-181">Create and use a custom drive</span></span>
  
1.  <span data-ttu-id="cf60c-182">Use `New-PSDrive` para definir uma unidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="cf60c-182">Use `New-PSDrive` to define a custom drive.</span></span> <span data-ttu-id="cf60c-183">Use o parâmetro `Root` para especificar o caminho que é representado pelo nome de unidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="cf60c-183">Use the `Root` parameter to specify the path that is represented by the custom drive name.</span></span>  
  
2.  <span data-ttu-id="cf60c-184">Referencie o nome de unidade personalizada em cmdlets de navegação do caminho como `Set-Location`.</span><span class="sxs-lookup"><span data-stu-id="cf60c-184">Reference the custom drive name in path navigation cmdlets such as `Set-Location`.</span></span>  
  
### <a name="custom-drive-example-powershell"></a><span data-ttu-id="cf60c-185">Exemplo de unidade personalizada (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cf60c-185">Custom Drive Example (PowerShell)</span></span>  
 <span data-ttu-id="cf60c-186">Este exemplo cria uma unidade virtual chamada AWDB que é mapeada para o nó de uma cópia implantada do banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="cf60c-186">This example creates a virtual drive named AWDB that maps to the node for a deployed copy of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="cf60c-187">A unidade virtual é usada para navegar até uma tabela no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cf60c-187">The virtual drive is then used to navigate to a table in the database.</span></span>  
  
```powershell
## Create a new virtual drive.  
New-PSDrive -Name AWDB -Root SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
  
## Use AWDB: to navigate to a specific table.  
Set-Location AWDB:\Tables\Purchasing.Vendor  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf60c-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cf60c-188">See Also</span></span>  
 <span data-ttu-id="cf60c-189">[Provedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="cf60c-189">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="cf60c-190">[Trabalhar com caminhos de SQL Server PowerShell](work-with-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="cf60c-190">[Work With SQL Server PowerShell Paths](work-with-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="cf60c-191">[Converter URNs em caminhos de provedor SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="cf60c-191">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="cf60c-192">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf60c-192">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
