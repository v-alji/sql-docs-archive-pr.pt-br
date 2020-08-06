---
title: Carregar assemblies SMO no Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8ca42b69-da5a-47f4-9085-34e443f0e389
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9886d80c305dba251e6e3ab22ddb4dfb39783748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678804"
---
# <a name="load-the-smo-assemblies-in-windows-powershell"></a><span data-ttu-id="6f598-102">Carregar os assemblies SMO no Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f598-102">Load the SMO Assemblies in Windows PowerShell</span></span>
  <span data-ttu-id="6f598-103">Este tópico descreve como carregar os assemblies SMO (SQL Server Management Object) em scripts do Windows PowerShell que não usam o provedor do SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f598-103">This topic describes how to load the SQL Server Management Object (SMO) assemblies in Windows PowerShell scripts that do not use the SQL Server PowerShell provider.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6f598-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6f598-104">Before You Begin</span></span>  
 <span data-ttu-id="6f598-105">O mecanismo preferido para carregar os assemblies SMO é carregar o módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6f598-105">The preferred mechanism for loading the SMO assemblies is to load the `sqlps` module.</span></span> <span data-ttu-id="6f598-106">O provedor [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] incluído automaticamente no módulo carrega os assemblies SMO e também implementa recursos que estendem a utilidade dos objetos SMO em scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f598-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider included in the module automatically loads the SMO assemblies, and also implements features that extend the usefulness of the SMO objects in PowerShell scripts.</span></span>  
  
 <span data-ttu-id="6f598-107">Há dois casos em que você pode precisar carregar diretamente os assemblies do SMO:</span><span class="sxs-lookup"><span data-stu-id="6f598-107">There are two cases where you may need to load the SMO assemblies directly:</span></span>  
  
-   <span data-ttu-id="6f598-108">Se o script fizer referência a um objeto do SMO antes do primeiro comando que faz referência ao provedor ou a cmdlets dos snap-ins do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f598-108">If your script references a SMO object before the first command that references the provider or cmdlets from the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins.</span></span>  
  
-   <span data-ttu-id="6f598-109">Você deseja portar código do SMO de outra linguagem, como C# ou Visual Basic, que não usa o provedor ou cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6f598-109">You want to port SMO code from another language, such as C# or Visual Basic, which does not use the provider or cmdlets.</span></span>  
  
## <a name="example-loading-the-sql-server-management-objects"></a><span data-ttu-id="6f598-110">Exemplo: carregando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6f598-110">Example: Loading the SQL Server Management Objects</span></span>  
 <span data-ttu-id="6f598-111">O código a seguir carrega os assemblies do SMO:</span><span class="sxs-lookup"><span data-stu-id="6f598-111">The following code loads the SMO assemblies:</span></span>  
  
```powershell
# Loads the SQL Server Management Objects (SMO)  
  
$ErrorActionPreference = "Stop"  
  
$sqlpsreg = "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.SqlServer.Management.PowerShell.sqlps"  
  
if (Get-ChildItem $sqlpsreg -ErrorAction "SilentlyContinue")  
{  
    throw "SQL Server Provider for Windows PowerShell is not installed."  
}  
else  
{  
    $item = Get-ItemProperty $sqlpsreg  
    $sqlpsPath = [System.IO.Path]::GetDirectoryName($item.Path)  
}  
  
$assemblylist =   
"Microsoft.SqlServer.Management.Common",  
"Microsoft.SqlServer.Smo",  
"Microsoft.SqlServer.Dmf ",  
"Microsoft.SqlServer.Instapi ",  
"Microsoft.SqlServer.SqlWmiManagement ",  
"Microsoft.SqlServer.ConnectionInfo ",  
"Microsoft.SqlServer.SmoExtended ",  
"Microsoft.SqlServer.SqlTDiagM ",  
"Microsoft.SqlServer.SString ",  
"Microsoft.SqlServer.Management.RegisteredServers ",  
"Microsoft.SqlServer.Management.Sdk.Sfc ",  
"Microsoft.SqlServer.SqlEnum ",  
"Microsoft.SqlServer.RegSvrEnum ",  
"Microsoft.SqlServer.WmiEnum ",  
"Microsoft.SqlServer.ServiceBrokerEnum ",  
"Microsoft.SqlServer.ConnectionInfoExtended ",  
"Microsoft.SqlServer.Management.Collector ",  
"Microsoft.SqlServer.Management.CollectorEnum",  
"Microsoft.SqlServer.Management.Dac",  
"Microsoft.SqlServer.Management.DacEnum",  
"Microsoft.SqlServer.Management.Utility"  
  
foreach ($asm in $assemblylist)  
{  
    $asm = [Reflection.Assembly]::LoadWithPartialName($asm)  
}  
  
Push-Location  
cd $sqlpsPath  
Update-FormatData -PrependPath SQLProvider.Format.ps1xml
Pop-Location  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f598-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f598-112">See Also</span></span>  
 [<span data-ttu-id="6f598-113">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f598-113">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
