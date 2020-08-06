---
title: Ajuda do SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Help [PowerShell]
- Help [SQL Server], PowerShell
- PowerShell [SQL Server], help
ms.assetid: 968c316d-db83-4c24-8ea6-9f18736842f7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f1d97a3b694eebb924f9e1ff228d4d38da4f45ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681081"
---
# <a name="get-help-sql-server-powershell"></a><span data-ttu-id="4c486-102">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c486-102">Get Help SQL Server PowerShell</span></span>
  <span data-ttu-id="4c486-103">Há várias origens de informações sobre como usar o provedor e os cmdlets do provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c486-103">There are several sources of information about using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell and cmdlets.</span></span> <span data-ttu-id="4c486-104">Isso inclui a ajuda que está disponível no ambiente Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c486-104">This includes the help that is available in the Windows PowerShell environment.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="4c486-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c486-105">Before You Begin</span></span>  
 <span data-ttu-id="4c486-106">Para saber mais sobre o Windows PowerShell, consulte o [Guia de Introdução do Windows PowerShell](https://technet.microsoft.com/library/hh857337.aspx).</span><span class="sxs-lookup"><span data-stu-id="4c486-106">To learn about Windows PowerShell, see [Windows PowerShell Getting Started Guide](https://technet.microsoft.com/library/hh857337.aspx).</span></span>  
  
 <span data-ttu-id="4c486-107">Para obter uma visão geral do provedor e os cmdlets do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , veja [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4c486-107">For an overview of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets and provider, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="help-in-the-windows-powershell-environment"></a><span data-ttu-id="4c486-108">Ajude no ambiente de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c486-108">Help in the Windows PowerShell Environment</span></span>  
 <span data-ttu-id="4c486-109">Use o cmdlet **Get-Help** para obter ajuda no ambiente Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c486-109">Use the **Get-Help** cmdlet to get help in the Windows PowerShell environment.</span></span> <span data-ttu-id="4c486-110">**Get-Help** fornece ajuda básica para a linguagem Windows PowerShell e os diversos cmdlets e provedores disponíveis no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c486-110">**Get-Help** provides basic help for the Windows PowerShell language and the various cmdlets and providers available in Windows PowerShell.</span></span>  
  
 <span data-ttu-id="4c486-111">Para obter mais informações sobre os modos você pode usar **Get-Help**, veja [Get-Help: Obtendo Ajuda](https://go.microsoft.com/fwlink/?LinkId=102136).</span><span class="sxs-lookup"><span data-stu-id="4c486-111">For more information on the ways you can use **Get-Help**, see [Get-Help: Getting Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span></span>  
  
### <a name="sql-server-powershell-provider-help"></a><span data-ttu-id="4c486-112">Ajuda do provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c486-112">SQL Server PowerShell Provider Help</span></span>  
 <span data-ttu-id="4c486-113">O provedor [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell implementa várias pastas em uma unidade virtual SQLSERVER, como as pastas SQLSERVER:\SQL e SQLSERVER:\DAC.</span><span class="sxs-lookup"><span data-stu-id="4c486-113">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider implements several folders on a SQLSERVER virtual drive, such as the SQLSERVER:\SQL and SQLSERVER:\DAC folders.</span></span> <span data-ttu-id="4c486-114">Cada pasta é associada com um dos modelos de objeto de gerenciamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4c486-114">Each folder is associated with one of the SQL Server manageability object models.</span></span> <span data-ttu-id="4c486-115">Enquanto você puder listar os métodos e propriedades associadas com cada nó em um caminho de SQL Server, não poderá obter ajuda por eles no ambiente PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c486-115">While you can list the methods and properties associated with each node in a SQL Server path, you cannot get help for them in the PowerShell environment.</span></span> <span data-ttu-id="4c486-116">Para obter uma tabela das pastas com links para a referência de programação associada, consulte [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4c486-116">For a table of the folders with links to the associated programming reference, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
### <a name="invoke-sqlcmd-help"></a><span data-ttu-id="4c486-117">Ajuda do Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4c486-117">Invoke-Sqlcmd Help</span></span>  
 <span data-ttu-id="4c486-118">O cmdlet **Invoke-Sqlcmd** usa como entrada qualquer consulta ou arquivo de script que possa ser executado pelo utilitário **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="4c486-118">The **Invoke-Sqlcmd** cmdlet takes as input any query or script file that can be run by the **sqlcmd** utility.</span></span> <span data-ttu-id="4c486-119">Você pode usar **Get-Help** para obter informações sobre **Invoke-Sqlcmd** e seus parâmetros, mas não há cobertura de **Get-Help** para consultas **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="4c486-119">You can use **Get-Help** to get information about **Invoke-Sqlcmd** and its parameters, but there is no **Get-Help** coverage for the **sqlcmd** queries.</span></span>  
  
 <span data-ttu-id="4c486-120">A entrada *-Query* ou *-QueryFromFile* pode conter:</span><span class="sxs-lookup"><span data-stu-id="4c486-120">The *-Query* or *-QueryFromFile* input can contain:</span></span>  
  
-   <span data-ttu-id="4c486-121">Variáveis e comandos do**sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="4c486-121">**sqlcmd** variables and commands.</span></span> <span data-ttu-id="4c486-122">Para obter informações sobre essas variáveis e comandos, consulte a seção Comentários de [sqlcmd Utility](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4c486-122">For information about these variables and commands, see the Remarks section of [sqlcmd Utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="4c486-123">Instruções[!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c486-123">[!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="4c486-124">Para obter mais informações sobre a linguagem [!INCLUDE[tsql](../includes/tsql-md.md)], veja [Referência de Transact-SQL &#40;Mecanismo de Banco de Dados&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="4c486-124">For more information about the [!INCLUDE[tsql](../includes/tsql-md.md)] language, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
-   <span data-ttu-id="4c486-125">Instruções XQuery.</span><span class="sxs-lookup"><span data-stu-id="4c486-125">XQuery statements.</span></span> <span data-ttu-id="4c486-126">Para obter mais informações sobre a linguagem XQuery com suporte no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], veja [Referência de linguagem XQuery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span><span class="sxs-lookup"><span data-stu-id="4c486-126">For more information about the XQuery language supported by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span></span>  
  
## <a name="get-help-for-a-sql-server-cmdlet"></a><span data-ttu-id="4c486-127">Obtenha Ajuda para um cmdlet de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c486-127">Get Help for a SQL Server cmdlet</span></span>  
 <span data-ttu-id="4c486-128">**Para obter ajuda para um cmdlet**</span><span class="sxs-lookup"><span data-stu-id="4c486-128">**To get help for a cmdlet**</span></span>  
  
-   <span data-ttu-id="4c486-129">Execute Get-Help especificando o nome do cmdlet e o nível de ajuda a ser retornada.</span><span class="sxs-lookup"><span data-stu-id="4c486-129">Run Get-Help specifying the name of the cmdlet and the level of help to be returned.</span></span>  
  
### <a name="example-cmdlet-get-help"></a><span data-ttu-id="4c486-130">Exemplo: cmdlet Get-Help</span><span class="sxs-lookup"><span data-stu-id="4c486-130">Example: cmdlet Get-Help</span></span>  
 <span data-ttu-id="4c486-131">Os seguintes exemplos retornam vários níveis de ajuda para **Invoke-Sqlcmd**:</span><span class="sxs-lookup"><span data-stu-id="4c486-131">The following examples return various levels of help for **Invoke-Sqlcmd**:</span></span>  
  
```powershell
## Get the basic help.  
Get-Help Invoke-Sqlcmd  
  
## Get the full help.  
Get-Help Invoke-Sqlcmd -Full  
  
## Get the parameter descriptions.  
Get-Help Invoke-Sqlcmd -Parameter *  
  
## Get the code examples.  
Get-Help Invoke-Sqlcmd -Examples  
  
## Get the syntax diagram.  
Get-Help Invoke-Sqlcmd -Syntax  
```  
  
## <a name="get-a-list-of-providers"></a><span data-ttu-id="4c486-132">Obtenha uma lista de provedores</span><span class="sxs-lookup"><span data-stu-id="4c486-132">Get a List of Providers</span></span>  

### <a name="to-get-a-list-of-active-providers"></a><span data-ttu-id="4c486-133">Para obter uma lista de provedores ativos</span><span class="sxs-lookup"><span data-stu-id="4c486-133">To get a list of active providers</span></span>
  
1.  <span data-ttu-id="4c486-134">Execute Get-Help especificando a categoria de provedor.</span><span class="sxs-lookup"><span data-stu-id="4c486-134">Run Get-Help specifying the provider category.</span></span>  
  
 <span data-ttu-id="4c486-135">Para obter mais informações sobre como obter ajuda do provedor no Windows PowerShell, consulte [Unidades e Provedores](https://go.microsoft.com/fwlink/?LinkId=102137).</span><span class="sxs-lookup"><span data-stu-id="4c486-135">For more information about getting provider help in Windows PowerShell, see [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137).</span></span>  
  
### <a name="example-get-a-list-of-providers"></a><span data-ttu-id="4c486-136">Exemplo: obtenha uma lista de provedores</span><span class="sxs-lookup"><span data-stu-id="4c486-136">Example: Get a List of Providers</span></span>  
 <span data-ttu-id="4c486-137">Esse código retorna uma lista de provedores habilitados atualmente em sua sessão do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4c486-137">This code returns a list of the providers currently enabled in your Windows PowerShell session:</span></span>  
  
```powershell
Get-Help -Category provider  
```  
  
## <a name="get-help-about-the-sql-server-provider"></a><span data-ttu-id="4c486-138">Obter ajuda sobre o provedor do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c486-138">Get Help About the SQL Server Provider</span></span>  
 <span data-ttu-id="4c486-139">**Para obter ajuda sobre o provedor**</span><span class="sxs-lookup"><span data-stu-id="4c486-139">**To get help about the provider**</span></span>  
  
1.  <span data-ttu-id="4c486-140">Execute Get-Help especificando o nome SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c486-140">Run Get-Help specifying the name SQLServer</span></span>  
  
### <a name="example-get-sql-server-provider-help"></a><span data-ttu-id="4c486-141">Exemplo: Obtenha ajuda do provedor SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c486-141">Example: Get SQL Server Provider Help</span></span>  
 <span data-ttu-id="4c486-142">Este exemplo retorna informações básicas sobre o provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4c486-142">This example returns basic information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider:</span></span>  
  
```powershell
Get-Help SQLServer  
```  
  
## <a name="list-methods-and-properties"></a><span data-ttu-id="4c486-143">Listar métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="4c486-143">List Methods and Properties</span></span>  
 <span data-ttu-id="4c486-144">**Para listar os métodos e propriedades para um nó em um caminho de provedor do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4c486-144">**To list the methods and properties for a node in a SQL Server provider path**</span></span>  
  
1.  <span data-ttu-id="4c486-145">O CD para um nó no caminho do SQL Server ou crie uma variável definida para esse local.</span><span class="sxs-lookup"><span data-stu-id="4c486-145">Either CD to a node in the SQL Server path, or create a variable set to that location.</span></span>  
  
2.  <span data-ttu-id="4c486-146">Execute o cmdlet **Get-Member** com o parâmetro-type definido como métodos ou propriedades</span><span class="sxs-lookup"><span data-stu-id="4c486-146">Run the **Get-Member** cmdlet with the -Type parameter set to either Methods or Properties</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="4c486-147">Exemplos: listando métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="4c486-147">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="4c486-148">Este exemplo lista os métodos com suporte para o nó Bancos de Dados:</span><span class="sxs-lookup"><span data-stu-id="4c486-148">This example lists the methods supported for the Databases node:</span></span>  
  
```powershell
Set-Location SQL:\MyComputer\DEFAULT\Databases  
Get-Item . | Get-Member -Type Methods  
```  
  
 <span data-ttu-id="4c486-149">Esse exemplo lista as propriedades de uma variável que foi definida como um objeto Tabela SMO:</span><span class="sxs-lookup"><span data-stu-id="4c486-149">This example lists the properties for a variable that has been set to an SMO Table object:</span></span>  
  
```powershell
$MyVar = New-Object Microsoft.SqlServer.Management.SMO.Table  
$MyVar | Get-Member -Type Properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c486-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c486-150">See Also</span></span>  
 <span data-ttu-id="4c486-151">[Provedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4c486-151">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="4c486-152">Usar cmdlets do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="4c486-152">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
