---
title: Gerenciar o preenchimento de guias (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 6296848a-890f-4ad3-8d9f-92ed6a79aa00
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72bcf96245c536d6ea444bc1d7964b7579e793c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583684"
---
# <a name="manage-tab-completion-sql-server-powershell"></a><span data-ttu-id="54001-102">Gerenciar conclusão de guia (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="54001-102">Manage Tab Completion (SQL Server PowerShell)</span></span>
  <span data-ttu-id="54001-103">Os snap-ins do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell apresentam três variáveis (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems` e `$SqlServerIncludeSystemObjects`) para controlar a conclusão da guia Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54001-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins introduce three variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems`, and `$SqlServerIncludeSystemObjects`) to control Windows PowerShell tab completion.</span></span> <span data-ttu-id="54001-104">A conclusão da guia reduz a quantidade de digitação necessária, retornando tabelas de itens cujos nomes iniciam com a cadeia de caracteres que você está digitando.</span><span class="sxs-lookup"><span data-stu-id="54001-104">Tab completion reduces the amount of typing you must do by returning tables of items whose names start with the string you are typing.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="54001-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="54001-105">Before You Begin</span></span>  
 <span data-ttu-id="54001-106">Com a tab-completion do Windows PowerShell, quando você digita parte do nome de um caminho ou cmdlet, pode pressionar a tecla Tab para obter uma lista de itens cujos nomes correspondem aos já digitados.</span><span class="sxs-lookup"><span data-stu-id="54001-106">With Windows PowerShell tab-completion, when you have typed part of a path or cmdlet name, you can hit the Tab key to get a list of the items whose names match what you have already typed.</span></span> <span data-ttu-id="54001-107">Em seguida, é possível selecionar o item desejado da lista sem precisar digitar o restante do nome.</span><span class="sxs-lookup"><span data-stu-id="54001-107">You can then select the item you want from the list without having to type the rest of the name.</span></span>  
  
 <span data-ttu-id="54001-108">Se você estiver trabalhando em um banco de dados com muitos objetos, as listas tab-completion poderão se tornar muito grandes.</span><span class="sxs-lookup"><span data-stu-id="54001-108">If you are working in a database that has a lot of objects, the tab-completion lists can become very large.</span></span> <span data-ttu-id="54001-109">Alguns tipos de objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , como exibições, também têm vários objetos de sistema.</span><span class="sxs-lookup"><span data-stu-id="54001-109">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] object types, such as views, also have large numbers of system objects.</span></span>  
  
 <span data-ttu-id="54001-110">Os snap-ins do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] apresentam três variáveis de sistema que podem ser usadas para controlar a quantidade de informações apresentadas por tab-completion e **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="54001-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins introduces three system variables that you can use to control the amount of information presented by tab-completion and **Get-ChildItem**.</span></span>  
  
 <span data-ttu-id="54001-111">**$SqlServerMaximumTabCompletion =** *n*</span><span class="sxs-lookup"><span data-stu-id="54001-111">**$SqlServerMaximumTabCompletion =** *n*</span></span>  
 <span data-ttu-id="54001-112">Especifica o número máximo de objetos que devem ser incluídos em uma lista tab-completion.</span><span class="sxs-lookup"><span data-stu-id="54001-112">Specifies the maximum number of objects to include in a tab-completion list.</span></span> <span data-ttu-id="54001-113">Se você selecionar Tab em um nó de caminho com mais de *n* objetos, a lista tab-completion será truncada em *n*.</span><span class="sxs-lookup"><span data-stu-id="54001-113">If you select Tab at a path node having more than *n* objects, the tab-completion list is truncated at *n*.</span></span> <span data-ttu-id="54001-114">*n* é um inteiro.</span><span class="sxs-lookup"><span data-stu-id="54001-114">*n* is an integer.</span></span> <span data-ttu-id="54001-115">0 é a configuração padrão e significa que não há limite para o número de objetos na lista.</span><span class="sxs-lookup"><span data-stu-id="54001-115">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="54001-116">**$SqlServerMaximumChildItems =** *n*</span><span class="sxs-lookup"><span data-stu-id="54001-116">**$SqlServerMaximumChildItems =** *n*</span></span>  
 <span data-ttu-id="54001-117">Especifica o número máximo de objetos exibidos por **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="54001-117">Specifies the maximum number of objects displayed by **Get-ChildItem**.</span></span> <span data-ttu-id="54001-118">Se **Get-ChildItem** for executado em um nó de caminho com mais de *n* objetos, a lista será truncada em *n*.</span><span class="sxs-lookup"><span data-stu-id="54001-118">If **Get-ChildItem** is run at a path node having more than *n* objects, the list is truncated at *n*.</span></span> <span data-ttu-id="54001-119">*n* é um inteiro.</span><span class="sxs-lookup"><span data-stu-id="54001-119">*n* is an integer.</span></span> <span data-ttu-id="54001-120">0 é a configuração padrão e significa que não há limite para o número de objetos na lista.</span><span class="sxs-lookup"><span data-stu-id="54001-120">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="54001-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span><span class="sxs-lookup"><span data-stu-id="54001-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span></span>  
 <span data-ttu-id="54001-122">Se for **$True**, os objetos do sistema serão exibidos por tab-completion e **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="54001-122">If **$True**, system objects are displayed by tab-completion and **Get-ChildItem**.</span></span> <span data-ttu-id="54001-123">Se for **$False**, nenhum objeto de sistema será exibido.</span><span class="sxs-lookup"><span data-stu-id="54001-123">If **$False**, no system objects are displayed.</span></span> <span data-ttu-id="54001-124">A configuração padrão é **$False**.</span><span class="sxs-lookup"><span data-stu-id="54001-124">The default setting is **$False**.</span></span>  
  
## <a name="set-the-sql-server-tab-completion-variables"></a><span data-ttu-id="54001-125">Definir as variáveis de conclusão de guia do SQL Server</span><span class="sxs-lookup"><span data-stu-id="54001-125">Set the SQL Server Tab Completion Variables</span></span>  
 <span data-ttu-id="54001-126">Para qualquer variável a ser alterada do valor padrão, defina a variável como o novo valor.</span><span class="sxs-lookup"><span data-stu-id="54001-126">For any of the variables you want to change from the default value, set the variable to the new value.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="54001-127">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="54001-127">Example (PowerShell)</span></span>  
 <span data-ttu-id="54001-128">O exemplo a seguir define todas as três variáveis e lista suas configurações:</span><span class="sxs-lookup"><span data-stu-id="54001-128">The following example sets all three variables and lists their settings:</span></span>  
  
```powershell
$SqlServerMaximumTabCompletion = 20  
$SqlServerMaximumChildItems = 10  
$SqlServerIncludeSystemObjects = $False  
dir variable:sqlserver*  
```  
  
## <a name="see-also"></a><span data-ttu-id="54001-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54001-129">See Also</span></span>  
 [<span data-ttu-id="54001-130">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="54001-130">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
