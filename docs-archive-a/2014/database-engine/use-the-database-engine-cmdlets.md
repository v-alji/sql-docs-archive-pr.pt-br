---
title: Usar cmdlets do Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Convert-UrnToPath cmdlet
- PowerShell [SQL Server], cmdlets
- Cmdlets [SQL Server]
- PowerShell [SQL Server], Convert-UrnToPath
- Cmdlets [SQL Server], Convert-UrnToPath
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 720aa982-09ae-41a3-b603-a91004cfbe3e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 015500c7c985f9f1a1d190954406844f3b184932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569597"
---
# <a name="use-the-database-engine-cmdlets"></a><span data-ttu-id="e95e6-102">Usar cmdlets do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e95e6-102">Use the Database Engine cmdlets</span></span>
  <span data-ttu-id="e95e6-103">Os cmdlets Windows PowerShell são comandos de função única que normalmente contêm uma convenção de nomenclatura formada por verbo-substantivo, como **Get-Help** ou **Set-MachineName**.</span><span class="sxs-lookup"><span data-stu-id="e95e6-103">Windows PowerShell cmdlets are single-function commands that typically have a verb-noun naming convention, such as **Get-Help** or **Set-MachineName**.</span></span> <span data-ttu-id="e95e6-104">O provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para Windows PowerShell fornece cmdlets específicos para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e95e6-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell supplies cmdlets specific to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="e95e6-105">cmdlets do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e95e6-105">Database Engine cmdlets</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="e95e6-106">implementa alguns cmdlets para o [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e95e6-106">implements a small number of cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="e95e6-107">Estes cmdlets são usados para executar principalmente scripts Transact-SQL existentes de novos scripts PowerShell, avaliar políticas de gerenciamento baseadas em política e ajudar a especificar identificadores do SQL Server em caminhos do provedor do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e95e6-107">These cmdlets are primarily used to run existing Transact-SQL scripts from new PowerShell scripts, evaluate policy-based management policies, and aid in specifying SQL Server identifiers in SQL Server Provider paths.</span></span>  
  
 <span data-ttu-id="e95e6-108">A maioria dos scripts do Windows PowerShell funcionam com o [!INCLUDE[ssDE](../includes/ssde-md.md)] usando o provedor do SQL Server PowerShell e os modelos de objeto de gerenciamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e95e6-108">Most Windows PowerShell scripts work with the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using the SQL Server PowerShell provider and the SQL Server manageability object models.</span></span> <span data-ttu-id="e95e6-109">Para obter mais informações, confira [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e95e6-109">For more information, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="get-cmdlet-help"></a><span data-ttu-id="e95e6-110">Obter a ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="e95e6-110">Get Cmdlet Help</span></span>  
 <span data-ttu-id="e95e6-111">No ambiente Windows PowerShell, o cmdlet **Get-Help** fornece informações de ajuda para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95e6-111">In the Windows PowerShell environment, the **Get-Help** cmdlet provides help information for each cmdlet.</span></span> <span data-ttu-id="e95e6-112">O**Get-Help** retorna informações como sintaxe, definições de parâmetro, tipos de entrada e saída e uma descrição da ação executada pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95e6-112">**Get-Help** returns information such as the syntax, parameter definitions, input and output types, and a description of the action performed by the cmdlet.</span></span> <span data-ttu-id="e95e6-113">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e95e6-113">For more information, see [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span></span>  
  
### <a name="partial-parameter-names"></a><span data-ttu-id="e95e6-114">Nomes de parâmetro parciais</span><span class="sxs-lookup"><span data-stu-id="e95e6-114">Partial Parameter Names</span></span>  
 <span data-ttu-id="e95e6-115">Você não tem que especificar o nome inteiro de um parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95e6-115">You do not have to specify the entire name of a cmdlet parameter.</span></span> <span data-ttu-id="e95e6-116">Você só tem que especificar uma parte suficiente do nome para separá-lo exclusivamente dos outros parâmetros que são suportados pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95e6-116">You only have to specify enough of the name to uniquely separate it from the other parameters that are supported by the cmdlet.</span></span> <span data-ttu-id="e95e6-117">Por exemplo, estes exemplos mostram três modos de especificar o parâmetro **Invoke-Sqlcmd -QueryTimeout** :</span><span class="sxs-lookup"><span data-stu-id="e95e6-117">For example, these examples show three ways of specifying the **Invoke-Sqlcmd -QueryTimeout** parameter:</span></span>  
  
```powershell
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTimeout 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTime 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryT 3  
```  
  
## <a name="database-engine-cmdlet-tasks"></a><span data-ttu-id="e95e6-118">Tarefas cmdlet do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e95e6-118">Database Engine cmdlet Tasks</span></span>  
  
|<span data-ttu-id="e95e6-119">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="e95e6-119">Task Description</span></span>|<span data-ttu-id="e95e6-120">Tópico</span><span class="sxs-lookup"><span data-stu-id="e95e6-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="e95e6-121">Descreve o uso de **Invoke-Sqlcmd** para executar scripts **sqlcmd** ou comandos contendo [!INCLUDE[tsql](../includes/tsql-md.md)] ou instruções XQuery.</span><span class="sxs-lookup"><span data-stu-id="e95e6-121">Describes using **Invoke-Sqlcmd** to run **sqlcmd** scripts or commands that contain [!INCLUDE[tsql](../includes/tsql-md.md)] or XQuery statements.</span></span> <span data-ttu-id="e95e6-122">Ele pode aceitar a entrada **sqlcmd** como um parâmetro de entrada da cadeia de caracteres do caractere ou como o nome de um arquivo de script a ser aberto.</span><span class="sxs-lookup"><span data-stu-id="e95e6-122">It can accept the **sqlcmd** input as either a character string input parameter, or as the name of a script file to open.</span></span>|[<span data-ttu-id="e95e6-123">cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e95e6-123">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="e95e6-124">Descreve o uso de **Invoke-PolicyEvaluation** para relatar se um conjunto de destino de objetos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] é compatível com as condições definidas em políticas de gerenciamento baseadas em políticas.</span><span class="sxs-lookup"><span data-stu-id="e95e6-124">Describes using **Invoke-PolicyEvaluation** to report whether a target set of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects comply with the conditions that are defined in policy-based management policies.</span></span> <span data-ttu-id="e95e6-125">Opcionalmente, o cmdlet pode ser usado para reconfigurar qualquer opção definível nos objetos de destino que não obedecem às condições de políticas.</span><span class="sxs-lookup"><span data-stu-id="e95e6-125">Optionally, the cmdlet can be used to reconfigure any settable options in the target objects that do not comply with the policy conditions.</span></span>|[<span data-ttu-id="e95e6-126">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="e95e6-126">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
|<span data-ttu-id="e95e6-127">Descreve o uso de `Encode-Sqlname` e `Decode-Sqlname` para tratar identificadores SQL Server que contêm caracteres sem suporte em caminhos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e95e6-127">Describes using `Encode-Sqlname` and `Decode-Sqlname` to handle SQL Server identifiers that contain characters not supported in Windows PowerShell paths.</span></span>|[<span data-ttu-id="e95e6-128">Codificar e decodificar identificadores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e95e6-128">Encode and Decode SQL Server Identifiers</span></span>](../powershell/encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="e95e6-129">Descreve o uso de `Convert-UrnToPath` para converter um URN (Nome de Recurso Uniforme) de Objeto de Gerenciamento SQL Server no caminho de provedor SQL Server equivalente.</span><span class="sxs-lookup"><span data-stu-id="e95e6-129">Describes using `Convert-UrnToPath` to convert a SQL Server Manageability Object Uniform Resource Name (URN) to the equivalent SQL Server Provider path.</span></span>|[<span data-ttu-id="e95e6-130">Converter URNs em caminhos de provedor SQL Server</span><span class="sxs-lookup"><span data-stu-id="e95e6-130">Convert URNs to SQL Server Provider Paths</span></span>](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e95e6-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e95e6-131">See Also</span></span>  
 <span data-ttu-id="e95e6-132">[Provedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e95e6-132">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="e95e6-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="e95e6-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="e95e6-134">Visão geral dos cmdlets do PowerShell para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e95e6-134">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
  
