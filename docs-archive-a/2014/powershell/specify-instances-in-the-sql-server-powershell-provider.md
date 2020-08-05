---
title: Especificar instâncias no provedor do SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 9373de68-fd43-45f2-b9a6-149c96610aeb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc04bacc1ff36b0b5ce526a377fcdb750ad134a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573146"
---
# <a name="specify-instances-in-the-sql-server-powershell-provider"></a><span data-ttu-id="6ca2d-102">Especificar instâncias no provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ca2d-102">Specify Instances in the SQL Server PowerShell Provider</span></span>
  <span data-ttu-id="6ca2d-103">Os caminhos especificados para o provedor do SQL Server PowerShell devem identificar a instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] e o computador no qual ela está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-103">The paths specified for the SQL Server PowerShell provider must identify the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] and the computer it is running on.</span></span> <span data-ttu-id="6ca2d-104">A sintaxe para especificar o computador e a instância deve obedecer as regras para identificadores do SQL Server e caminhos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-104">The syntax for specifying the computer and the instance must comply with both the rules for SQL Server identifiers and Windows PowerShell paths.</span></span>  
  
1.  <span data-ttu-id="6ca2d-105">**Antes de começar:**  [Limitações e restrições](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="6ca2d-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="6ca2d-106">**Para especificar uma instância:**  [Examples](#Examples)</span><span class="sxs-lookup"><span data-stu-id="6ca2d-106">**To specify an instance:**  [Examples](#Examples)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6ca2d-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6ca2d-107">Before You Begin</span></span>  
 <span data-ttu-id="6ca2d-108">O primeiro nó depois de SQLSERVER:\SQL em um caminho de provedor SQL Server é o nome do computador que está executando a instância do [!INCLUDE[ssDE](../includes/ssde-md.md)]; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6ca2d-108">The first node following the SQLSERVER:\SQL in a SQL Server provider path is the name of the computer that is running the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer  
```  
  
 <span data-ttu-id="6ca2d-109">Se você está executando o Windows PowerShell no mesmo computador que a instância do [!INCLUDE[ssDE](../includes/ssde-md.md)], pode usar localhost ou (local) em vez do nome do computador.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-109">If you are running Windows PowerShell on the same computer as the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], you can use either localhost or (local) instead of the name of the computer.</span></span> <span data-ttu-id="6ca2d-110">Scripts que usam localhost ou (local) podem ser executados em qualquer computador sem necessidade de alterações para refletir os nomes dos computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-110">Scripts that use localhost or (local) can be run on any computer without having to be changed to reflect the different computer names.</span></span>  
  
 <span data-ttu-id="6ca2d-111">Você pode executar várias instâncias do programa executável do [!INCLUDE[ssDE](../includes/ssde-md.md)] no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-111">You can run multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] executable program on the same computer.</span></span> <span data-ttu-id="6ca2d-112">O nó depois do nome do computador em um caminho de provedor SQL Server identifica a instância; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6ca2d-112">The node following the computer name in a SQL Server provider path identifies the instance; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance  
```  
  
 <span data-ttu-id="6ca2d-113">Cada computador pode ter uma instância padrão do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ca2d-113">Each computer can have one default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="6ca2d-114">Você não especifica um nome para a instância padrão ao instalá-la.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-114">You do not specify a name for the default instance when you install it.</span></span> <span data-ttu-id="6ca2d-115">Ao especificar apenas um nome de computador em uma cadeia de conexão, você estabelecerá conexão com a instância padrão nesse computador.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-115">If you specify only a computer name in a connection string, you are connected to the default instance on that computer.</span></span> <span data-ttu-id="6ca2d-116">Todas as outras instâncias no computador devem ser instâncias nomeadas.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-116">All other instances on the computer must be named instances.</span></span> <span data-ttu-id="6ca2d-117">Você especifica o nome da instância durante a configuração e as cadeias de conexão devem especificar o nome do computador e o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-117">You specify the instance name during setup, and connection strings must specify both the computer name and the instance name.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="6ca2d-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6ca2d-118">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6ca2d-119">Você não pode usar um ponto (.) para especificar o computador local em scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-119">You cannot use a period (.) to specify the local computer in PowerShell scripts.</span></span> <span data-ttu-id="6ca2d-120">O ponto não é suportado, porque é interpretado como um comando pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-120">The period is not supported because the period is interpreted as a command by PowerShell.</span></span>  
  
 <span data-ttu-id="6ca2d-121">Os caracteres de parêntese em (local) é tratado normalmente como comandos pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-121">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="6ca2d-122">Você deve codificá-los ou reservá-los para uso em um caminho, ou colocar o caminho entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-122">You must either encode them or escape them for use in a path, or enclose the path in double-quotation marks.</span></span> <span data-ttu-id="6ca2d-123">Para obter mais informações, consulte Codifique e Decodifique Identificadores do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-123">For more information, see Encode and Decode SQL Server Identifiers.</span></span>  
  
 <span data-ttu-id="6ca2d-124">O provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requer que o nome da instância sempre seja especificado.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-124">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider requires that you always specify an instance name.</span></span> <span data-ttu-id="6ca2d-125">Para instâncias padrão, especifique o nome da instância como DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-125">For default instances, you must specify an instance name of DEFAULT.</span></span>  
  
##  <a name="examples-computer-and-instance-names"></a><a name="Examples"></a><span data-ttu-id="6ca2d-126">Disso Nomes de computador e instância</span><span class="sxs-lookup"><span data-stu-id="6ca2d-126">Examples; Computer and Instance Names</span></span>  
 <span data-ttu-id="6ca2d-127">Este exemplo usa localhost e DEFAULT para especificar a instância padrão no computador local:</span><span class="sxs-lookup"><span data-stu-id="6ca2d-127">This example uses localhost and DEFAULT to specify the default instance on the local computer:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT
```  
  
 <span data-ttu-id="6ca2d-128">Os caracteres de parêntese em (local) é tratado normalmente como comandos pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ca2d-128">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="6ca2d-129">Você deve:</span><span class="sxs-lookup"><span data-stu-id="6ca2d-129">You must either:</span></span>  
  
-   <span data-ttu-id="6ca2d-130">Incluir as cadeias de caracteres de caminho entre aspas:</span><span class="sxs-lookup"><span data-stu-id="6ca2d-130">Enclose the path string in quotes:</span></span>  
  
    ```powershell
    Set-Location "SQLSERVER:\SQL\(local)\DEFAULT"  
    ```  
  
-   <span data-ttu-id="6ca2d-131">Retirar o parêntese usando o caractere de acento grave (\`):</span><span class="sxs-lookup"><span data-stu-id="6ca2d-131">Escape the parenthesis using the back tick character (\`):</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
    ```  
  
-   <span data-ttu-id="6ca2d-132">Codificar o parêntese usando sua representação hexadecimal:</span><span class="sxs-lookup"><span data-stu-id="6ca2d-132">Encode the parenthesis using their hexadecimal representation:</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\%28local%29\DEFAULT  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ca2d-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ca2d-133">See Also</span></span>  
 <span data-ttu-id="6ca2d-134">[Identificadores de SQL Server no PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="6ca2d-134">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="6ca2d-135">[Provedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="6ca2d-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="6ca2d-136">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ca2d-136">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
