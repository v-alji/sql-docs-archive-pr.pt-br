---
title: Depurar um pacote definindo pontos de interrupção em uma tarefa ou contêiner | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570769"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a><span data-ttu-id="b4962-102">Depurar um pacote por meio da definição de pontos de interrupção em uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="b4962-102">Debug a Package by Setting Breakpoints on a Task or a Container</span></span>
  <span data-ttu-id="b4962-103">Este procedimento descreve como definir pontos de interrupção em um pacote, uma tarefa, um contêiner Loop For, um contêiner Loop Foreach ou um contêiner Sequência.</span><span class="sxs-lookup"><span data-stu-id="b4962-103">This procedure describes how to set breakpoints in a package, a task, a For Loop container, a Foreach Loop container, or a Sequence container.</span></span>  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a><span data-ttu-id="b4962-104">Para definir pontos de interrupção em um pacote, uma tarefa ou um contêiner</span><span class="sxs-lookup"><span data-stu-id="b4962-104">To set breakpoints in a package, a task, or a container</span></span>  
  
1.  <span data-ttu-id="b4962-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="b4962-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b4962-106">Clique duas vezes no pacote em que você deseja definir pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="b4962-106">Double-click the package in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="b4962-107">No SSIS Designer, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="b4962-107">In SSIS Designer, do the following:</span></span>  
  
    -   <span data-ttu-id="b4962-108">Para definir pontos de interrupção no objeto de pacote, clique na guia **Fluxo de Controle** , coloque o cursor em qualquer lugar na tela de fundo da superfície de design e clique com o botão direito do mouse e clique em **Editar Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="b4962-108">To set breakpoints in the package object, click the **Control Flow** tab, place the cursor anywhere on the background of the design surface, right-click, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="b4962-109">Para definir pontos de interrupção em um fluxo de controle de pacote, clique na guia **Fluxo de Controle** , clique com o botão direito do mouse em uma tarefa, um contêiner Loop For, um contêiner Loop Foreach ou um contêiner Sequência, e clique em **Editar Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="b4962-109">To set breakpoints in a package control flow, click the **Control Flow** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="b4962-110">Para definir pontos de interrupção em um manipulador de eventos, clique na guia **Manipulador de Eventos** , clique com o botão direito do mouse em uma tarefa, um contêiner Loop For, um contêiner Loop Foreach ou um contêiner Sequência e clique em **Editar Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="b4962-110">To set breakpoints in an event handler, click the **Event Handler** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
4.  <span data-ttu-id="b4962-111">Na caixa de diálogo **Definir Pontos de Interrupção \<container name>** , selecione os pontos de interrupção a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="b4962-111">In the **Set Breakpoints \<container name>** dialog box, select the breakpoints to enable.</span></span>  
  
5.  <span data-ttu-id="b4962-112">Opcionalmente, modifique o tipo de contagem de ocorrências e o número de contagem de ocorrências para cada ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="b4962-112">Optionally, modify the hit count type and the hit count number for each breakpoint.</span></span>  
  
6.  <span data-ttu-id="b4962-113">Para salvar o pacote, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="b4962-113">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4962-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4962-114">See Also</span></span>  
 <span data-ttu-id="b4962-115">[Solucionando problemas de ferramentas para desenvolvimento de pacotes](troubleshooting/troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="b4962-115">[Troubleshooting Tools for Package Development](troubleshooting/troubleshooting-tools-for-package-development.md) </span></span>  
 <span data-ttu-id="b4962-116">[Depurar um script definindo pontos de interrupção em uma tarefa Script e um componente Script](data-flow/transformations/script-component.md) </span><span class="sxs-lookup"><span data-stu-id="b4962-116">[Debug a Script by Setting Breakpoints in a Script Task and Script Component](data-flow/transformations/script-component.md) </span></span>  
 <span data-ttu-id="b4962-117">[Codificando e Depurando a tarefa Script](control-flow/script-task.md) </span><span class="sxs-lookup"><span data-stu-id="b4962-117">[Coding and Debugging the Script Task](control-flow/script-task.md) </span></span>  
 [<span data-ttu-id="b4962-118">Codificar e depurar o componente de Script</span><span class="sxs-lookup"><span data-stu-id="b4962-118">Coding and Debugging the Script Component</span></span>](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
