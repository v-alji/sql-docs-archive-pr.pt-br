---
title: Trabalhar com caminhos do SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f31d8e2c-8d59-4fee-ac2a-324668e54262
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d2647251eb1c8843d4ab7a95d2c439e47f5bb6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680502"
---
# <a name="work-with-sql-server-powershell-paths"></a><span data-ttu-id="eba16-102">Trabalhar com caminhos do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="eba16-102">Work With SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="eba16-103">Depois de navegar para um nó em um caminho de provedor do [!INCLUDE[ssDE](../includes/ssde-md.md)] , pode executar trabalho ou recuperar informações usando os métodos e as propriedades do objeto de gerenciamento do [!INCLUDE[ssDE](../includes/ssde-md.md)] associado com o nó.</span><span class="sxs-lookup"><span data-stu-id="eba16-103">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform work or retrieve information by using the methods and properties from the [!INCLUDE[ssDE](../includes/ssde-md.md)] management object associated with the node.</span></span>  
  
1.  [<span data-ttu-id="eba16-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="eba16-104">Before You Begin</span></span>](#BeforeYouBegin)  
  
2.  <span data-ttu-id="eba16-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span><span class="sxs-lookup"><span data-stu-id="eba16-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eba16-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="eba16-106">Before You Begin</span></span>  
 <span data-ttu-id="eba16-107">Depois de navegar até um nó em um caminho do provedor do [!INCLUDE[ssDE](../includes/ssde-md.md)] , você poderá executar dois tipos de ações:</span><span class="sxs-lookup"><span data-stu-id="eba16-107">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform two types of actions:</span></span>  
  
-   <span data-ttu-id="eba16-108">Você pode executar os cmdlets do Windows PowerShell que funcionam em nós, como **Rename-Item**.</span><span class="sxs-lookup"><span data-stu-id="eba16-108">You can run Windows PowerShell cmdlets that operate on nodes, such as **Rename-Item**.</span></span>  
  
-   <span data-ttu-id="eba16-109">Você pode chamar os métodos do modelo de objeto de gerenciamento associado do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , como SMO.</span><span class="sxs-lookup"><span data-stu-id="eba16-109">You can call the methods from the associated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] management object model, such as SMO.</span></span> <span data-ttu-id="eba16-110">Por exemplo, se você navegar até o nó Banco de Dados em um caminho, poderá usar os métodos e as propriedades da classe <xref:Microsoft.SqlServer.Management.Smo.Database> .</span><span class="sxs-lookup"><span data-stu-id="eba16-110">For example, if you navigate to the Databases node in a path, you can use the methods and properties of the <xref:Microsoft.SqlServer.Management.Smo.Database> class.</span></span>  
  
 <span data-ttu-id="eba16-111">O provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] é usado para gerenciar os objetos em uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eba16-111">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider is used to manage the objects in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="eba16-112">Ele não é usado para trabalhar com dados em bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="eba16-112">It is not used to work with the data in databases.</span></span> <span data-ttu-id="eba16-113">Se você navegou até uma tabela ou exibição, não é possível usar o provedor para selecionar, inserir, atualizar ou excluir dados.</span><span class="sxs-lookup"><span data-stu-id="eba16-113">If you have navigated to a table or view, you cannot use the provider to select, insert, update, or delete data.</span></span> <span data-ttu-id="eba16-114">Use o cmdlet **Invoke-Sqlcmd** para consultar ou alterar dados em tabelas e exibições do ambiente do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eba16-114">Use the **Invoke-Sqlcmd** cmdlet to query or change data in tables and views from the Windows PowerShell environment.</span></span> <span data-ttu-id="eba16-115">Para obter mais informações, veja [Cmdlet Invoke-Sqlcmd](../database-engine/invoke-sqlcmd-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="eba16-115">For more information, see [Invoke-Sqlcmd cmdlet](../database-engine/invoke-sqlcmd-cmdlet.md).</span></span>  
  
##  <a name="listing-methods-and-properties"></a><a name="ListPropMeth"></a> <span data-ttu-id="eba16-116">Listando métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="eba16-116">Listing Methods and Properties</span></span>
  
 <span data-ttu-id="eba16-117">Para exibir os métodos e as propriedades disponíveis para objetos ou classes de objetos específicos, use o cmdlet **Get-Member** .</span><span class="sxs-lookup"><span data-stu-id="eba16-117">To view the methods and properties available for specific objects or object classes, use the **Get-Member** cmdlet.</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="eba16-118">Exemplos: listando métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="eba16-118">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="eba16-119">Este exemplo define uma variável do Windows PowerShell para a classe SMO <xref:Microsoft.SqlServer.Management.Smo.Database> e lista os métodos e as propriedades:</span><span class="sxs-lookup"><span data-stu-id="eba16-119">This example sets a Windows PowerShell variable to the SMO <xref:Microsoft.SqlServer.Management.Smo.Database> class and lists the methods and properties:</span></span>  
  
```powershell
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar | Get-Member -Type Methods  
$MyDBVar | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="eba16-120">Você também pode usar **Get-Member** para listar os métodos e as propriedades associadas ao nó final de um caminho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eba16-120">You can also use **Get-Member** to list the methods and properties that are associated with the end node of a Windows PowerShell path.</span></span>  
  
 <span data-ttu-id="eba16-121">Este exemplo navega até o nó Bancos de Dados em um caminho SQLSERVER: e lista as propriedades da coleção:</span><span class="sxs-lookup"><span data-stu-id="eba16-121">This example navigates to the Databases node in a SQLSERVER: path and lists the collection properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-Item . | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="eba16-122">Este exemplo navega até o nó AdventureWorks2012 em um caminho SQLSERVER: e lista as propriedades dos objetos:</span><span class="sxs-lookup"><span data-stu-id="eba16-122">This example navigates to the AdventureWorks2012 node in a SQLSERVER: path and lists the object properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
Get-Item . | Get-Member -Type Properties  
```  
  
##  <a name="using-smo-methods-and-properties"></a><a name="UsePropMeth"></a><span data-ttu-id="eba16-123">Usando métodos e propriedades do SMO</span><span class="sxs-lookup"><span data-stu-id="eba16-123">Using SMO Methods and Properties</span></span>  
  
 <span data-ttu-id="eba16-124">Para executar trabalhos em objetos de um caminho de provedor do [!INCLUDE[ssDE](../includes/ssde-md.md)] , você pode usar métodos e propriedades do SMO.</span><span class="sxs-lookup"><span data-stu-id="eba16-124">To perform work on objects from a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can use SMO methods and properties.</span></span>  
  
### <a name="examples-using-methods-and-properties"></a><span data-ttu-id="eba16-125">Exemplos: usando métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="eba16-125">Examples: Using Methods and Properties</span></span>  
 <span data-ttu-id="eba16-126">Este exemplo usa a propriedade SMO **Schema** para obter a lista de tabelas do esquema Sales em AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="eba16-126">This example uses the SMO **Schema** property to get a list of the tables from the Sales schema in AdventureWorks2012:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Tables  
Get-ChildItem | Where {$_.Schema -eq "Sales"}  
```  
  
 <span data-ttu-id="eba16-127">Este exemplo usa o método de **script** Smo para gerar um script que contém as `CREATE VIEW` instruções que você deve ter para recriar as exibições em AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="eba16-127">This example uses the SMO **Script** method to generate a script that contains the `CREATE VIEW` statements you must have to re-create the views in AdventureWorks2012:</span></span>  
  
```powershell
Remove-Item C:\PowerShell\CreateViews.sql  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Views  
foreach ($Item in Get-ChildItem) { $Item.Script() | Out-File -Filepath C:\PowerShell\CreateViews.sql -append }  
```  
  
 <span data-ttu-id="eba16-128">Este exemplo usa o método **Create** do SMO para criar um banco de dados e usa a propriedade **State** para mostrar se o banco de dados existe:</span><span class="sxs-lookup"><span data-stu-id="eba16-128">This example uses the SMO **Create** method to create a database, and then uses the **State** property to show whether the database exists:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar.Parent = (Get-Item ..)  
$MyDBVar.Name = "NewDB"  
$MyDBVar.Create()  
$MyDBVar.State  
```  
  
## <a name="see-also"></a><span data-ttu-id="eba16-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eba16-129">See Also</span></span>  
 <span data-ttu-id="eba16-130">[Provedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="eba16-130">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="eba16-131">[Navegar SQL Server PowerShell caminhos](navigate-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="eba16-131">[Navigate SQL Server PowerShell Paths](navigate-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="eba16-132">[Converter URNs em caminhos de provedor SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="eba16-132">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="eba16-133">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="eba16-133">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
