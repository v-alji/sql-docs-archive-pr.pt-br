---
title: Referência do Mecanismo de Banco de Dados com o PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3c379a43-c497-47dd-8e7d-2b015c068bb7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2d72f9fcedee02e475369c32a7c263578c9ff156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574887"
---
# <a name="database-engine-powershell-reference"></a><span data-ttu-id="ee80a-102">Referência do Mecanismo de Banco de Dados com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee80a-102">Database Engine PowerShell Reference</span></span>
  <span data-ttu-id="ee80a-103">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] inclui um conjunto de cmdlets de Windows PowerShell 2.0 para executar ações comuns no [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee80a-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] includes a set of Windows PowerShell 2.0 cmdlets for performing common actions in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="ee80a-104">Além disso, expressões de consulta e URNs podem ser convertidos em caminhos do SQL Server PowerShell ou usados para especificar um ou mais objetos no [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee80a-104">In addition, Query Expressions and Uniform Resource Names (URN) can be converted to SQL Server PowerShell paths, or used to specify one or more objects in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="ee80a-105">Cmdlets do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="ee80a-105">Database Engine Cmdlets</span></span>  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] <span data-ttu-id="ee80a-106">inclui cmdlets relativamente poucos para o [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee80a-106">includes relatively few cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="ee80a-107">A maioria dos scripts do PowerShell que funciona com o [!INCLUDE[ssDE](../includes/ssde-md.md)] usa o provedor do SQL Server PowerShell e os modelos de objeto de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ee80a-107">Most PowerShell scripts working with the [!INCLUDE[ssDE](../includes/ssde-md.md)] use the SQL Server PowerShell provider and the manageability object models.</span></span> <span data-ttu-id="ee80a-108">Para obter mais informações, consulte [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ee80a-108">For more information, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
 <span data-ttu-id="ee80a-109">Para saber como obter ajuda sobre o cmdlets do SQL Server em um ambiente do Windows PowerShell, consulte [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ee80a-109">To learn how to get help about the SQL Server cmdlets in a Windows PowerShell environment, see [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="ee80a-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ee80a-110">In This Section</span></span>  
 <span data-ttu-id="ee80a-111">Esta seção contém informações sobre esses cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ee80a-111">This section contains information about these cmdlets.</span></span>  
  
|<span data-ttu-id="ee80a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee80a-112">Description</span></span>|<span data-ttu-id="ee80a-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ee80a-113">Cmdlet</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="ee80a-114">Executa scripts Transact-SQL e XQuery, como scripts que podem ser executados usando o utilitário `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="ee80a-114">Runs Transact-SQL and XQuery scripts, such as scripts that can be run using the `sqlcmd` utility.</span></span>|[<span data-ttu-id="ee80a-115">cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="ee80a-115">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="ee80a-116">Avalia se um objeto do Mecanismo de Banco de Dados obedece a uma política gerenciamento baseado em políticas.</span><span class="sxs-lookup"><span data-stu-id="ee80a-116">Evaluates whether a Database Engine object complies with a Policy-based Management policy.</span></span>|[<span data-ttu-id="ee80a-117">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="ee80a-117">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
  
### <a name="information-about-other-cmdlets"></a><span data-ttu-id="ee80a-118">Informações sobre outros cmdlets</span><span class="sxs-lookup"><span data-stu-id="ee80a-118">Information About Other Cmdlets</span></span>  
 <span data-ttu-id="ee80a-119">Os cmdlets `Encode-Sqlname` e `Decode-Sqlname` ajudam a especificar identificadores do SQL Server que contêm caracteres sem suporte em caminhos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee80a-119">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets help you specify SQL Server identifiers that contain characters not supported in PowerShell paths.</span></span> <span data-ttu-id="ee80a-120">Para obter mais informações, consulte [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ee80a-120">For more information, see [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span></span>  
  
 <span data-ttu-id="ee80a-121">Use o cmdlet `Convert-UrnToPath` para converter um nome de recurso exclusivo de um objeto do [!INCLUDE[ssDE](../includes/ssde-md.md)] para um caminho do provedor do SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee80a-121">Use the `Convert-UrnToPath` cmdlet to convert a Unique Resource Name for a [!INCLUDE[ssDE](../includes/ssde-md.md)] object to a path for the SQL Server PowerShell provider.</span></span> <span data-ttu-id="ee80a-122">Para obter mais informações, consulte [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span><span class="sxs-lookup"><span data-stu-id="ee80a-122">For more information, see [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span></span>  
  
## <a name="query-expressions-and-unique-resource-names"></a><span data-ttu-id="ee80a-123">Expressões de consultas e URNs (Unique Resource Names)</span><span class="sxs-lookup"><span data-stu-id="ee80a-123">Query Expressions and Unique Resource Names</span></span>  
 <span data-ttu-id="ee80a-124">As expressões de consulta são cadeias de caracteres que usam sintaxe similar à do XPath para especificar um conjunto de critérios que enumera um ou mais objetos em uma hierarquia de modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="ee80a-124">Query expressions are strings that use syntax similar to XPath to specify a set of criteria that enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="ee80a-125">Um URN (Unique Resource Name) é um tipo específico de cadeia de caracteres de expressão de consulta que identifica exclusivamente um único objeto.</span><span class="sxs-lookup"><span data-stu-id="ee80a-125">A Unique Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span> <span data-ttu-id="ee80a-126">Para obter mais informações, consulte [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="ee80a-126">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee80a-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee80a-127">See Also</span></span>  
 [<span data-ttu-id="ee80a-128">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee80a-128">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
  
  
