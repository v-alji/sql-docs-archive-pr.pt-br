---
title: Retirar identificadores do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8a73e945-daa6-4e5d-93da-10f000f1f3a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1821187632aeeea0b7a18bf9c4d51d933e947d43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574062"
---
# <a name="escape-sql-server-identifiers"></a><span data-ttu-id="0f815-102">Retirar identificadores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f815-102">Escape SQL Server Identifiers</span></span>
  <span data-ttu-id="0f815-103">O caractere de acento grave (\`) do PowerShell pode ser usado frequentemente para substituir caracteres que são permitidos nos identificadores delimitados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , mas não nomes de caminho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f815-103">You can often use the Windows PowerShell back-tick escape character (\`) to escape characters that are allowed in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delimited identifiers but not Windows PowerShell path names.</span></span> <span data-ttu-id="0f815-104">Entretanto, alguns caracteres não podem ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="0f815-104">Some characters, however, cannot be escaped.</span></span> <span data-ttu-id="0f815-105">Por exemplo, no Windows PowerShell, não é possível substituir o caractere dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="0f815-105">For example, you cannot escape the colon character (:) in Windows PowerShell.</span></span> <span data-ttu-id="0f815-106">Os identificadores que contém esse caractere devem ser codificados.</span><span class="sxs-lookup"><span data-stu-id="0f815-106">Identifiers with that character must be encoded.</span></span> <span data-ttu-id="0f815-107">A codificação é mais segura do que a substituição, pois os trabalhos de codificação aceitam todos os caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f815-107">Encoding is more reliable than escaping because encoding works for all characters.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0f815-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0f815-108">Before You Begin</span></span>  
 <span data-ttu-id="0f815-109">O caractere de acento grave (\`) geralmente encontra-se no lado esquerdo do teclado, abaixo da tecla ESC.</span><span class="sxs-lookup"><span data-stu-id="0f815-109">The back-tick character (\`) is usually on the key in the upper left of the keyboard, under the ESC key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0f815-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0f815-110">Examples</span></span>  
 <span data-ttu-id="0f815-111">Este é um exemplo de substituição de um caractere #:</span><span class="sxs-lookup"><span data-stu-id="0f815-111">This is an example of escaping a # character:</span></span>  
  
```  
cd SQLSERVER:\SQL\MyComputer\MyInstance\MyDatabase\MySchema\`#MyTempTable  
```  
  
 <span data-ttu-id="0f815-112">Este é um exemplo de escape do parêntese ao especificar (local) como um nome de computador:</span><span class="sxs-lookup"><span data-stu-id="0f815-112">This is an example of escaping the parenthesis when specifying (local) as a computer name:</span></span>  
  
```  
Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f815-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f815-113">See Also</span></span>  
 <span data-ttu-id="0f815-114">[Identificadores de SQL Server no PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="0f815-114">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="0f815-115">[Provedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="0f815-115">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="0f815-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f815-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
