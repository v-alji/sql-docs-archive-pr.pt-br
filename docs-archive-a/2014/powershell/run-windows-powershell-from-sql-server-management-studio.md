---
title: Executar o Windows PowerShell no SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573154"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a><span data-ttu-id="1bfc0-102">Executar o Windows PowerShell no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bfc0-102">Run Windows PowerShell from SQL Server Management Studio</span></span>
  <span data-ttu-id="1bfc0-103">Você pode iniciar sessões do Windows PowerShell no **Pesquisador de Objetos** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bfc0-103">You can start Windows PowerShell sessions from **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]<span data-ttu-id="1bfc0-104">inicia o Windows PowerShell, carrega o `sqlps` módulo e define o contexto do caminho para o nó associado na árvore do pesquisador de **objetos** .</span><span class="sxs-lookup"><span data-stu-id="1bfc0-104">launches Windows PowerShell, loads the `sqlps` module, and sets the path context to the associated node in the **Object Explorer** tree.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1bfc0-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1bfc0-105">Before You Begin</span></span>  
 <span data-ttu-id="1bfc0-106">Quando você especifica a execução do PowerShell para um objeto no Pesquisador de **objetos**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o inicia uma sessão do Windows PowerShell na qual os [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins do PowerShell foram carregados e registrados.</span><span class="sxs-lookup"><span data-stu-id="1bfc0-106">When you specify running PowerShell for an object in **Object Explorer**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starts a Windows PowerShell session in which the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins have been loaded and registered.</span></span> <span data-ttu-id="1bfc0-107">O caminho da sessão é predefinido no local do objeto em que você clicou com o botão direito no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="1bfc0-107">The path for the session is preset to the location of the object you right clicked in Object Explorer.</span></span> <span data-ttu-id="1bfc0-108">Por exemplo, se você clicar com o botão direito do mouse no objeto de banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] no Pesquisador de Objetos e selecionar **Iniciar PowerShell**, o caminho do Windows PowerShell será definido da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="1bfc0-108">For example, if you right-click the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database object in Object Explorer and select **Start PowerShell**, the Windows PowerShell path is set to the following:</span></span>  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a><span data-ttu-id="1bfc0-109">Para executar o PowerShell no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bfc0-109">To run PowerShell from SQL Server Management Studio</span></span> 
  
1.  <span data-ttu-id="1bfc0-110">Abra o **Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="1bfc0-110">Open **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="1bfc0-111">Navegue até o nó do objeto que será utilizado.</span><span class="sxs-lookup"><span data-stu-id="1bfc0-111">Navigate to the node for the object to be worked on.</span></span>  
  
3.  <span data-ttu-id="1bfc0-112">Clique com o botão direito do mouse no objeto e selecione **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1bfc0-112">Right-click the object and select **Start PowerShell**.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="1bfc0-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="1bfc0-113">Permissions</span></span>  
 <span data-ttu-id="1bfc0-114">Quando aberto no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], o PowerShell não é executado com privilégios de Administrador que podem impedir algumas atividades como chamadas ao WMI.</span><span class="sxs-lookup"><span data-stu-id="1bfc0-114">When opened from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell does not run with Administrator privileges which may prevent some activities such as calls to WMI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfc0-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1bfc0-115">See Also</span></span>  
 [<span data-ttu-id="1bfc0-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bfc0-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
