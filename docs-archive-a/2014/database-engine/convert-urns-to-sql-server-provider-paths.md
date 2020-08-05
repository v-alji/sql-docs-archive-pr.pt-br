---
title: Converter URNs em caminhos do provedor do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574270"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a><span data-ttu-id="613ec-102">Converter URNs em caminhos de provedor SQL Server</span><span class="sxs-lookup"><span data-stu-id="613ec-102">Convert URNs to SQL Server Provider Paths</span></span>
  <span data-ttu-id="613ec-103">O modelo SMO, Objeto de Gerenciamento do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , cria nomes de recurso uniformes (URN) para seus objetos.</span><span class="sxs-lookup"><span data-stu-id="613ec-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object model (SMO) builds Uniform Resource Names (URN) for its objects.</span></span> <span data-ttu-id="613ec-104">Cada URN identifica um objeto SMO exclusivamente e pode ser convertido em um caminho de provedor do SQL Server PowerShell usando o cmdlet `Convert-UrnToPath`.</span><span class="sxs-lookup"><span data-stu-id="613ec-104">Each URN uniquely identifies a SMO object, and can be converted to a SQL Server PowerShell provider path by using the `Convert-UrnToPath` cmdlet.</span></span>  
  
## <a name="converting-urns-to-paths"></a><span data-ttu-id="613ec-105">Convertendo URNs em caminhos</span><span class="sxs-lookup"><span data-stu-id="613ec-105">Converting URNs to Paths</span></span>  
 <span data-ttu-id="613ec-106">Cada URN tem as mesmas informações, como um caminho para o objeto, mas em um formulário diferente.</span><span class="sxs-lookup"><span data-stu-id="613ec-106">Each URN has the same information as a path to the object, but in a different form.</span></span> <span data-ttu-id="613ec-107">Por exemplo, este é o caminho para uma tabela:</span><span class="sxs-lookup"><span data-stu-id="613ec-107">For example, this is the path to a table:</span></span>  
  
 <span data-ttu-id="613ec-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span><span class="sxs-lookup"><span data-stu-id="613ec-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span></span>  
  
 <span data-ttu-id="613ec-109">E esta é a URN para o mesmo objeto:</span><span class="sxs-lookup"><span data-stu-id="613ec-109">And this is the URN to the same object:</span></span>  
  
 <span data-ttu-id="613ec-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span><span class="sxs-lookup"><span data-stu-id="613ec-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span></span>  
  
 <span data-ttu-id="613ec-111">Se você criou um objeto SMO em um script do PowerShell, poderá referenciar a propriedade `Urn` para obter o URN do objeto e, depois, usar o cmdlet `Convert-UrnToPath` para converter a cadeia de caracteres do URN de SMO para um caminho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="613ec-111">If you have created a SMO object in a PowerShell script, you can reference the `Urn` property to get the URN for the object, and then use the `Convert-UrnToPath` cmdlet to convert the SMO URN string to a Windows PowerShell path.</span></span> <span data-ttu-id="613ec-112">Você pode usar o provedor para navegar até locais diferentes no caminho.</span><span class="sxs-lookup"><span data-stu-id="613ec-112">You can then use the provider to navigate to different locations on the path.</span></span>  
  
 <span data-ttu-id="613ec-113">Se os nomes de nó contiverem caracteres estendidos sem suporte em nomes de caminho do Windows PowerShell, o `Convert-UrnToPath` irá codificá-los em sua representação hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="613ec-113">If node names contain extended characters that are not supported in Windows PowerShell path names, `Convert-UrnToPath` encodes them in their hexadecimal representation.</span></span> <span data-ttu-id="613ec-114">Por exemplo "My:Table" será retornado como "My%3ATable".</span><span class="sxs-lookup"><span data-stu-id="613ec-114">For example "My:Table" is returned as "My%3ATable".</span></span>  
  
 <span data-ttu-id="613ec-115">Para obter exemplos de utilização do cmdlet, no Windows PowerShell, execute:</span><span class="sxs-lookup"><span data-stu-id="613ec-115">For examples of using the cmdlet, in Windows PowerShell, run:</span></span>  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a><span data-ttu-id="613ec-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="613ec-116">See Also</span></span>  
 <span data-ttu-id="613ec-117">[Expressões de consulta e nomes de recursos uniformes](../powershell/query-expressions-and-uniform-resource-names.md) </span><span class="sxs-lookup"><span data-stu-id="613ec-117">[Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span></span>  
 <span data-ttu-id="613ec-118">[Provedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="613ec-118">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="613ec-119">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="613ec-119">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
