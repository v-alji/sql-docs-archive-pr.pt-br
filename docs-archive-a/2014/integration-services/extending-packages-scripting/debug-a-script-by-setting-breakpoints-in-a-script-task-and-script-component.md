---
title: Depurar um script configurando pontos de interrupção em uma tarefa Script e um componente de Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- breakpoints [Integration Services]
- scripts [Integration Services], breakpoints
ms.assetid: 6c03464f-3f7d-4882-b7f8-8e396f8e2944
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45e7ffc6680c33e3b17b9b39fba0aabd8fa4028c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571453"
---
# <a name="debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component"></a><span data-ttu-id="1cb38-102">Depurar um script definindo pontos de interrupção em uma tarefa Script e um componente Script</span><span class="sxs-lookup"><span data-stu-id="1cb38-102">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>
  <span data-ttu-id="1cb38-103">Este procedimento descreve como definir pontos de interrupção nos scripts que são usados na tarefa Script e componente Script.</span><span class="sxs-lookup"><span data-stu-id="1cb38-103">This procedure describes how to set breakpoints in the scripts that are used in the Script task and Script component.</span></span>  
  
 <span data-ttu-id="1cb38-104">Após você definir pontos de interrupção no script, a caixa de diálogo **Definir Pontos de Interrupção - \<object name>** lista os pontos de interrupção, bem como os pontos de interrupção inseridos.</span><span class="sxs-lookup"><span data-stu-id="1cb38-104">After you set breakpoints in the script, the **Set Breakpoints - \<object name>** dialog box lists the breakpoints, along with the built-in breakpoints.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1cb38-105">Em determinadas circunstâncias, os pontos de interrupção na tarefa Script e no componente Script são ignorados.</span><span class="sxs-lookup"><span data-stu-id="1cb38-105">Under certain circumstances, breakpoints in the Script task and Script component are ignored.</span></span> <span data-ttu-id="1cb38-106">Para obter mais informações, consulte a seção **Depurando a tarefa Script** em [codificando e Depurando a tarefa Script](../control-flow/script-task.md) e a seção **Depurando o componente Script** em [codificando e Depurando o componente Script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="1cb38-106">For more information, see the **Debugging the Script Task** section in [Coding and Debugging the Script Task](../control-flow/script-task.md) and the **Debugging the Script Component** section in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span></span>  
  
### <a name="to-set-a-breakpoint-in-script"></a><span data-ttu-id="1cb38-107">Para definir um ponto de interrupção em script</span><span class="sxs-lookup"><span data-stu-id="1cb38-107">To set a breakpoint in script</span></span>  
  
1.  <span data-ttu-id="1cb38-108">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="1cb38-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1cb38-109">Clique duas vezes no pacote que contém o script em que você quer definir pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="1cb38-109">Double-click the package that contains the script in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="1cb38-110">Para abrir a tarefa Script, clique nela duas vezes após abrir a guia **Fluxo de Controle**.</span><span class="sxs-lookup"><span data-stu-id="1cb38-110">To open the Script task, click the **Control Flow** tab, and then double-click the Script task.</span></span>  
  
4.  <span data-ttu-id="1cb38-111">Para abrir o componente Script, clique na guia **Fluxo de Dados** e então clique duas vezes no componente Script.</span><span class="sxs-lookup"><span data-stu-id="1cb38-111">To open the Script component, click the **Data Flow** tab, and then double-click the Script component.</span></span>  
  
5.  <span data-ttu-id="1cb38-112">Clique em **Script** e então clique em **Editar Script**.</span><span class="sxs-lookup"><span data-stu-id="1cb38-112">Click **Script** and then click **Edit Script**.</span></span>  
  
6.  <span data-ttu-id="1cb38-113">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] VSTA ([!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications), localize a linha de script em que deseja definir um ponto de interrupção, clique com o botão direito do mouse na linha, aponte para **Ponto de Interrupção** e, em seguida, clique em **Inserir Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="1cb38-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), locate the line of script on which you want to set a breakpoint, right-click that line, point to **Breakpoint**, and then click **Insert Breakpoint**.</span></span>  
  
     <span data-ttu-id="1cb38-114">O ícone de ponto de interrupção é exibido na linha de código.</span><span class="sxs-lookup"><span data-stu-id="1cb38-114">The breakpoint icon appears on the line of code.</span></span>  
  
7.  <span data-ttu-id="1cb38-115">No menu **Arquivo** , clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="1cb38-115">On the **File** menu, click **Exit**.</span></span>  
  
8.  <span data-ttu-id="1cb38-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cb38-116">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1cb38-117">Para salvar o pacote, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="1cb38-117">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
  
