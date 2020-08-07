---
title: Alternar um ponto de interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581744"
---
# <a name="toggle-a-breakpoint"></a><span data-ttu-id="4a4d8-102">Alternar um ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="4a4d8-102">Toggle a Breakpoint</span></span>
  <span data-ttu-id="4a4d8-103">O ato de definir um ponto de interrupção em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é chamado de alternar um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-103">The act of setting a breakpoint on a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is called toggling a breakpoint.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="4a4d8-104">Pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="4a4d8-104">Breakpoints</span></span>  
 <span data-ttu-id="4a4d8-105">Quando o ponto de interrupção foi definido, ele é representado por um ícone na barra cinza à esquerda da instrução.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-105">Once the breakpoint has been set, it is represented by an icon in the grey bar to the left of the statement.</span></span> <span data-ttu-id="4a4d8-106">O ícone é chamado de um glifo de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-106">The icon is called a breakpoint glyph.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="4a4d8-107">são aplicados a uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] completa.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-107">breakpoints are applied to a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="4a4d8-108">Quando um ponto de interrupção é ativado, o depurador realça a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] associada.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-108">When a breakpoint is toggled on, the debugger highlights the associated [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
 <span data-ttu-id="4a4d8-109">Se houver várias instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] em uma linha, você poderá alternar um ponto de interrupção para cada instrução.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-109">If there are multiple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on a line, you can toggle a breakpoint for each statement.</span></span> <span data-ttu-id="4a4d8-110">Clicar na barra cinza à esquerda da janela alterna um ponto de interrupção na primeira instrução na linha.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-110">Clicking in the grey bar on the left of the window toggles a breakpoint on the first statement on the line.</span></span> <span data-ttu-id="4a4d8-111">Você poderá alternar um ponto de interrupção em uma instrução subsequente realçando qualquer parte da instrução, ou movendo o cursor na instrução, e pressionando F9 ou clicando em **Alternar Ponto de Interrupção** no menu **Depurar** .</span><span class="sxs-lookup"><span data-stu-id="4a4d8-111">You can toggle a breakpoint in a subsequent statement by highlighting any part of the statement, or moving the cursor into the statement, and then either pressing F9 or clicking **Toggle Breakpoint** on the **Debug** menu.</span></span> <span data-ttu-id="4a4d8-112">Se você tiver vários pontos de interrupção em uma linha, haverá somente um glifo de ponto de interrupção na barra cinza à esquerda.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-112">If you have multiple breakpoints on a line, there is only one breakpoint glyph in the grey bar on the left.</span></span>  
  
 <span data-ttu-id="4a4d8-113">Depois que um ponto de interrupção for alternado, você poderá executar várias ações no ponto de interrupção, como editar suas propriedades ou desabilitá-las temporariamente.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-113">After a breakpoint has been toggled, you can perform various actions on the breakpoint, such as editing its properties or temporarily disabling it.</span></span> <span data-ttu-id="4a4d8-114">Para obter mais informações, veja [Pontos de interrupção Transact-SQL](transact-sql-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="4a4d8-114">For more information, see [Transact-SQL Breakpoints](transact-sql-breakpoints.md).</span></span>  
  
## <a name="toggle-a-breakpoint"></a><span data-ttu-id="4a4d8-115">Alternar um ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="4a4d8-115">Toggle a Breakpoint</span></span>  
 <span data-ttu-id="4a4d8-116">**Para alternar um ponto de interrupção em uma instrução Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4a4d8-116">**To toggle a breakpoint on a Transact-SQL statement**</span></span>  
  
1.  <span data-ttu-id="4a4d8-117">Clique na barra cinza à esquerda da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a4d8-117">Click the gray bar to the left side of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
2.  <span data-ttu-id="4a4d8-118">Outra alternativa é realçar qualquer parte da instrução ou mover o cursor para a instrução, e depois executar uma das ações:</span><span class="sxs-lookup"><span data-stu-id="4a4d8-118">Alternatively, either highlight any part of the statement or move the cursor to the statement, and then perform either action:</span></span>  
  
    -   <span data-ttu-id="4a4d8-119">Pressione F9.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-119">Press F9.</span></span>  
  
    -   <span data-ttu-id="4a4d8-120">No menu **Depurar** , clique em **Alternar Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="4a4d8-120">On the **Debug** menu, click **Toggle Breakpoint**.</span></span>  
  
  
