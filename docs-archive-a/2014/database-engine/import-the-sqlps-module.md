---
title: Importar o módulo SQLPS | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 37e66db05615ce8a285a80e5ac26b0cae411abeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681838"
---
# <a name="import-the-sqlps-module"></a><span data-ttu-id="e548b-102">Importar o módulo SQLPS</span><span class="sxs-lookup"><span data-stu-id="e548b-102">Import the SQLPS Module</span></span>
  <span data-ttu-id="e548b-103">A maneira recomendada para gerenciar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no PowerShell é importar o módulo `sqlps` para um ambiente do Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="e548b-103">The recommended way to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] from PowerShell is to import the `sqlps` module into a Windows PowerShell 2.0 environment.</span></span> <span data-ttu-id="e548b-104">O módulo carrega e registra os snap-ins do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e assemblies de capacidade de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="e548b-104">The module loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins and manageability assemblies.</span></span>  
  
1.  <span data-ttu-id="e548b-105">**Antes de começar:**  [segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="e548b-105">**Before You Begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="e548b-106">**Para carregar o módulo:**  [Carregar o módulo sqlps](#LoadSqlps)</span><span class="sxs-lookup"><span data-stu-id="e548b-106">**To load the module:**  [Load the sqlps Module](#LoadSqlps)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e548b-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e548b-107">Before You Begin</span></span>  
 <span data-ttu-id="e548b-108">Depois de importar o módulo `sqlps` no Windows PowerShell, você poderá:</span><span class="sxs-lookup"><span data-stu-id="e548b-108">After importing the `sqlps` module into Windows PowerShell, you can then:</span></span>  
  
-   <span data-ttu-id="e548b-109">Executar comandos do Windows PowerShell de forma interativa.</span><span class="sxs-lookup"><span data-stu-id="e548b-109">Interactively run Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="e548b-110">Executar arquivos de script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e548b-110">Run Windows PowerShell script files.</span></span>  
  
-   <span data-ttu-id="e548b-111">Executar cmdlets do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e548b-111">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="e548b-112">Usar os caminhos de provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para navegar pela hierarquia dos objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e548b-112">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="e548b-113">Usar os modelos de objeto de gerenciamento do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (como Microsoft.SqlServer.Management.Smo) para gerenciar objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e548b-113">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manageability object models (such as Microsoft.SqlServer.Management.Smo) to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e548b-114">Os verbos usados nos nomes de dois cmdlets de SQL Server (`Encode-Sqlname` e `Decode-Sqlname`) não correspondem aos verbos aprovados para o Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="e548b-114">The verbs used in the names of two SQL Server cmdlets (`Encode-Sqlname` and `Decode-Sqlname`) do not match the approved verbs for Windows PowerShell 2.0.</span></span> <span data-ttu-id="e548b-115">Isso não tem efeito na sua operação, mas o Windows PowerShell gera um aviso quando o módulo `sqlps` é importado para uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e548b-115">This has no effect on their operation, but Windows PowerShell raises a warning when the `sqlps` module is imported to a session.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e548b-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="e548b-116">Security</span></span>  
 <span data-ttu-id="e548b-117">Por padrão, o Windows PowerShell é executado em conjunto com a política de execução de scripts definida como **Restrita**, que evita a execução de qualquer script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e548b-117">By default, Windows PowerShell runs with the scripting execution policy set to **Restricted**, which prevents running any Windows PowerShell scripts.</span></span> <span data-ttu-id="e548b-118">Para carregar o módulo `sqlps` module, você pode usar o cmdlet `Set-ExecutionPolicy` a fim de habilitar a execução de scripts assinados ou de quaisquer outros scripts.</span><span class="sxs-lookup"><span data-stu-id="e548b-118">To load the `sqlps` module, you can use the `Set-ExecutionPolicy` cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="e548b-119">Somente os scripts de origem confiável devem ser executados, e é preciso verificar se todos os arquivos de entrada e de saída estão usando as permissões NTFS adequadas.</span><span class="sxs-lookup"><span data-stu-id="e548b-119">Only run scripts from trusted sources, and secure all input and output files using the appropriate NTFS permissions.</span></span> <span data-ttu-id="e548b-120">Para obter mais informações sobre como habilitar scripts do Windows PowerShell, consulte [Executando scripts do Windows PowerShell](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span><span class="sxs-lookup"><span data-stu-id="e548b-120">For more information about enabling Windows PowerShell scripts, see [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span></span>  
  
##  <a name="load-the-sqlps-module"></a><a name="LoadSqlps"></a> <span data-ttu-id="e548b-121">Carregar o módulo sqlps</span><span class="sxs-lookup"><span data-stu-id="e548b-121">Load the sqlps Module</span></span>  

### <a name="to-load-the-sqlps-module-in-windows-powershell"></a><span data-ttu-id="e548b-122">Para carregar o módulo sqlps no Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e548b-122">To load the sqlps module in Windows PowerShell</span></span>
  
1.  <span data-ttu-id="e548b-123">Use o cmdlet `Set-ExecutionPolicy` para definir a política de execução de script adequada.</span><span class="sxs-lookup"><span data-stu-id="e548b-123">Use the `Set-ExecutionPolicy` cmdlet to set the appropriate script execution policy.</span></span>  
  
2.  <span data-ttu-id="e548b-124">Use o cmdlet `Import-Module` para importar o módulo sqlps.</span><span class="sxs-lookup"><span data-stu-id="e548b-124">Use the `Import-Module` cmdlet to import the sqlps module.</span></span> <span data-ttu-id="e548b-125">Especifique o parâmetro `DisableNameChecking` se você desejar suprimir o aviso sobre `Encode-Sqlname` e `Decode-Sqlname`.</span><span class="sxs-lookup"><span data-stu-id="e548b-125">Specify the `DisableNameChecking` parameter if you want to suppress the warning about `Encode-Sqlname` and `Decode-Sqlname`.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="e548b-126">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e548b-126">Example (PowerShell)</span></span>  
 <span data-ttu-id="e548b-127">Este exemplo carrega o módulo `sqlps` com verificação de nome desligado.</span><span class="sxs-lookup"><span data-stu-id="e548b-127">This example loads the `sqlps` module with name checking turned off.</span></span>  
  
```powershell
## Import the SQL Server Module.  
  
Import-Module "sqlps" -DisableNameChecking  
```  

## <a name="see-also"></a><span data-ttu-id="e548b-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e548b-128">See Also</span></span>  
 <span data-ttu-id="e548b-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="e548b-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="e548b-130">[Provedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e548b-130">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="e548b-131">Usar cmdlets do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e548b-131">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
