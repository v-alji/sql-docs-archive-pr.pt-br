---
title: Janela Comando
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582399"
---
# <a name="command-window"></a><span data-ttu-id="5e672-102">Janela Comando</span><span class="sxs-lookup"><span data-stu-id="5e672-102">Command Window</span></span>
  <span data-ttu-id="5e672-103">Use a **Janela Comando** para executar comandos como de depuração e edição na janela do Editor de Consultas do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que está atualmente em depuração.</span><span class="sxs-lookup"><span data-stu-id="5e672-103">Use the **CommandWindow** to run commands, such as debug and edit commands, against the code in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor window that is currently being debugged.</span></span> <span data-ttu-id="5e672-104">É necessário estar no modo de depuração para usar a **Janela Comando**.</span><span class="sxs-lookup"><span data-stu-id="5e672-104">You must be in debug mode to use the **Command Window**.</span></span> <span data-ttu-id="5e672-105">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] dá suporte a muitos dos comandos que também têm suporte na janela de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Comando**.</span><span class="sxs-lookup"><span data-stu-id="5e672-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports many of the commands that are also supported in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span></span> <span data-ttu-id="5e672-106">Para obter mais informações, veja [Janela Comando do Visual Studio](https://go.microsoft.com/fwlink/?LinkId=112007).</span><span class="sxs-lookup"><span data-stu-id="5e672-106">For more information, see [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="5e672-107">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="5e672-107">Task List</span></span>  
 <span data-ttu-id="5e672-108">**Para acessar a Janela de Comando**</span><span class="sxs-lookup"><span data-stu-id="5e672-108">**To access the Command Window**</span></span>  
  
-   <span data-ttu-id="5e672-109">No menu **Depurar** , clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="5e672-109">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
 <span data-ttu-id="5e672-110">**Para imprimir o valor de uma variável**</span><span class="sxs-lookup"><span data-stu-id="5e672-110">**To print the value of a variable**</span></span>  
  
-   <span data-ttu-id="5e672-111">No **janela comando**, digite \*\*debug. Print \<VariableName> \*\*e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="5e672-111">In the **CommandWindow**, type **Debug.Print \<VariableName>**, and then press ENTER.</span></span>  
  
 <span data-ttu-id="5e672-112">**Para listar as informações sobre a thread atual**</span><span class="sxs-lookup"><span data-stu-id="5e672-112">**To list information about the current thread**</span></span>  
  
-   <span data-ttu-id="5e672-113">No **janela comando**, digite `Debug.ListThread` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="5e672-113">In the **CommandWindow**, type `Debug.ListThread`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="5e672-114">**Para adicionar uma variável à janela QuickWatch.**</span><span class="sxs-lookup"><span data-stu-id="5e672-114">**To add a variable to the QuickWatch window**</span></span>  
  
-   <span data-ttu-id="5e672-115">No **janela comando**, digite \*\*debug. QUICKWATCH \<VariableName> \*\*e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="5e672-115">In the **CommandWindow**, type **Debug.QuickWatch \<VariableName>**, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e672-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5e672-116">See Also</span></span>  
 [<span data-ttu-id="5e672-117">Depurador do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e672-117">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
