---
title: Depurando Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7926f806f20f76c7aaac0c22b970addc5e93a78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683589"
---
# <a name="debugging-script"></a><span data-ttu-id="481dc-102">Depurando script</span><span class="sxs-lookup"><span data-stu-id="481dc-102">Debugging Script</span></span>
  <span data-ttu-id="481dc-103">Os scripts usados pela tarefa Script e um componente Script são escritos no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSTA (Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="481dc-103">You write the scripts that the Script task and Script component use, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
 <span data-ttu-id="481dc-104">É possível definir e escrever scripts de pontos de interrupção no VSTA.</span><span class="sxs-lookup"><span data-stu-id="481dc-104">You set and script breakpoints in VSTA.</span></span> <span data-ttu-id="481dc-105">Você pode administrar pontos de interrupção no VSTA, mas também pode administrar os pontos de interrupção usando a caixa de diálogo **Definir Pontos de Interrupção** fornecida pelo Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="481dc-105">You can manage breakpoints in VSTA, but you can also manage the breakpoints using the **Set Breakpoints** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="481dc-106">Para obter mais informações, consulte [Depurando o fluxo de controle](debugging-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="481dc-106">For more information, see [Debugging Control Flow](debugging-control-flow.md).</span></span>  
  
 <span data-ttu-id="481dc-107">A caixa de diálogo **Definir Pontos de Interrupção** inclui os pontos de interrupção de script.</span><span class="sxs-lookup"><span data-stu-id="481dc-107">The **Set Breakpoints** dialog box includes the script breakpoints.</span></span> <span data-ttu-id="481dc-108">Esses pontos de interrupção aparecem na parte inferior da lista de pontos de interrupção e exibem o número de linha e o nome da função em que o ponto de interrupção aparece.</span><span class="sxs-lookup"><span data-stu-id="481dc-108">These breakpoints appear at the bottom of the breakpoint list, and display the line number and the name of the function in which the breakpoint appears.</span></span> <span data-ttu-id="481dc-109">Você pode excluir um ponto de interrupção de script na caixa de diálogo **Definir Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="481dc-109">You can delete a script breakpoint from the **Set Breakpoints** dialog box.</span></span>  
  
 <span data-ttu-id="481dc-110">No tempo de execução, os pontos de interrupção definidos em linhas de código no script são integrados com o conjunto de pontos de interrupção definidos no pacote ou nas tarefas e nos contêineres do pacote.</span><span class="sxs-lookup"><span data-stu-id="481dc-110">At run time, the breakpoints set on lines of code in script are integrated with the breakpoints set on the package or the tasks and containers in the package.</span></span> <span data-ttu-id="481dc-111">O depurador pode ser executado a partir de um ponto de interrupção no script para um conjunto de pontos de interrupção no pacote, tarefa, contêiner e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="481dc-111">The debugger can run from a breakpoint in the script to a breakpoint set on the package, task, or container, and vice versa.</span></span> <span data-ttu-id="481dc-112">Por exemplo, um pacote poderia ter um conjunto de pontos de interrupção nas condições de interrupção que ocorrem quando o pacote recebe os eventos **OnPreExecute** e **OnPostExecute** e também ter uma tarefa Script com pontos de interrupção nas linhas de seu script.</span><span class="sxs-lookup"><span data-stu-id="481dc-112">For example, a package might have breakpoints set on the break conditions that occur when the package receives the **OnPreExecute** and **OnPostExecute** events, and also have a Script task that has breakpoints on lines of its script.</span></span> <span data-ttu-id="481dc-113">Nesse cenário, o pacote pode suspender a execução na condição de interrupção associada com o evento **OnPreExecute** , executado nos pontos de interrupção no script, e finalmente executar a condição de interrupção associada com o evento **OnPostExecute** .</span><span class="sxs-lookup"><span data-stu-id="481dc-113">In this scenario, the package can suspend execution on the break condition associated with the **OnPreExecute** event, run to the breakpoints in the script, and finally run to the break condition associated with the **OnPostExecute** event.</span></span>  
  
 <span data-ttu-id="481dc-114">Para obter mais informações sobre como depurar a tarefa Script e o componente Script, consulte [Codificando e depurando a tarefa Script](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) e [Codificando e depurando o componente Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="481dc-114">For more information about debugging the Script task and Script component, see [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) and [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a><span data-ttu-id="481dc-115">Para definir um ponto de interrupção no Visual Studio for Applications</span><span class="sxs-lookup"><span data-stu-id="481dc-115">To set a breakpoint in Visual Studio for Applications</span></span>  
  
-   [<span data-ttu-id="481dc-116">Depurar um script definindo pontos de interrupção em uma tarefa Script e um componente de Script</span><span class="sxs-lookup"><span data-stu-id="481dc-116">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="481dc-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="481dc-117">See Also</span></span>  
 [<span data-ttu-id="481dc-118">Ferramentas de solução de problemas para desenvolvimento de pacotes</span><span class="sxs-lookup"><span data-stu-id="481dc-118">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
