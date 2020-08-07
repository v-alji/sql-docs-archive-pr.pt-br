---
title: Gerenciar o editor e o modo de exibição
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], managing window behavior
- workbench view modes [SQL Server Management Studio]
- full screen mode [SQL Server Management Studio]
- fonts [SQL Server Management Studio]
- word wraps [SQL Server Management Studio]
- virtual space mode [SQL Server Management Studio]
- splitting document views
- displaying line numbers
- view modes [SQL Server Management Studio]
ms.assetid: 25c58a14-9f94-4296-9770-7d84c6bc3969
author: rothja
ms.author: jroth
ms.openlocfilehash: 36788b1fe831a6c15c4aa0668d1759c088fcaa73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582412"
---
# <a name="manage-the-editor-and-view-mode"></a><span data-ttu-id="0fb5a-102">Gerenciar o editor e o modo de exibição</span><span class="sxs-lookup"><span data-stu-id="0fb5a-102">Manage the Editor and View Mode</span></span>
  <span data-ttu-id="0fb5a-103">O Editor fornece várias maneiras para controlar a exibição do código.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-103">The Editor gives you a number of ways to control the view of your code.</span></span>  
  
## <a name="changing-the-view-mode"></a><span data-ttu-id="0fb5a-104">Alterando o modo de exibição</span><span class="sxs-lookup"><span data-stu-id="0fb5a-104">Changing the View Mode</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0fb5a-105">possui um modo de exibição denominado **Documentos com Guias**, que permite abrir vários editores e documentos simultaneamente e acessá-los por guias no topo do editor.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-105">features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor.</span></span> <span data-ttu-id="0fb5a-106">Como alternativa, você pode abrir o ambiente do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] no modo interface de documentos múltiplos (MDI), que une as janelas sem guias e permite organizar as janelas lado a lado, minimizá-las etc.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-106">You can alternatively open the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.</span></span>  
  
#### <a name="to-switch-between-view-modes"></a><span data-ttu-id="0fb5a-107">Para alternar entre modos de exibição</span><span class="sxs-lookup"><span data-stu-id="0fb5a-107">To switch between view modes</span></span>  
  
1.  <span data-ttu-id="0fb5a-108">Clique em **Opções** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="0fb5a-108">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0fb5a-109">Clique em **Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-109">Click **Environment**.</span></span> <span data-ttu-id="0fb5a-110">Clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-110">Click **General**.</span></span>  
  
3.  <span data-ttu-id="0fb5a-111">Clique em **Documentos com Guias** ou **Ambiente MDI**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-111">Click **Tabbed documents** or **MDI environment**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0fb5a-112">As mudanças não entrarão em vigor até que o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] seja reinicializado.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-112">The changes will not take effect until [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is restarted.</span></span>  
  
## <a name="splitting-the-view"></a><span data-ttu-id="0fb5a-113">Dividindo a exibição</span><span class="sxs-lookup"><span data-stu-id="0fb5a-113">Splitting the View</span></span>  
 <span data-ttu-id="0fb5a-114">Uma janela do Editor pode ser dividida em duas partes separadas para facilitar a edição.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-114">An Editor window can be split into two separate parts for easier editing.</span></span>  
  
#### <a name="to-split-a-window"></a><span data-ttu-id="0fb5a-115">Para dividir uma janela</span><span class="sxs-lookup"><span data-stu-id="0fb5a-115">To split a window</span></span>  
  
1.  <span data-ttu-id="0fb5a-116">Clique na barra de divisão (localizada sobre a barra de rolagem).</span><span class="sxs-lookup"><span data-stu-id="0fb5a-116">Click the splitter bar (located above the scroll bar).</span></span>  
  
2.  <span data-ttu-id="0fb5a-117">Arraste a barra de divisão para baixo.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-117">Drag the splitter bar downward.</span></span>  
  
3.  <span data-ttu-id="0fb5a-118">Para voltar para um único painel, clique duas vezes na barra de divisão que divide os dois painéis.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-118">To go back to a single pane, double-click the splitter bar dividing the two panes.</span></span>  
  
 <span data-ttu-id="0fb5a-119">O painel novo contém o mesmo documento e quaisquer mudanças feitas em um painel são refletidas no outro painel, contanto que aquele painel exiba o mesmo lugar no documento.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-119">The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.</span></span>  
  
## <a name="word-wrap"></a><span data-ttu-id="0fb5a-120">Quebra automática de linha</span><span class="sxs-lookup"><span data-stu-id="0fb5a-120">Word Wrap</span></span>  
 <span data-ttu-id="0fb5a-121">Quando você ativa a quebra automática de linha, a barra de rolagem horizontal é afastada e as linhas de código que excedem a largura do tamanho da janela do Editor são automaticamente quebradas para a próxima linha exibida em vez de fornecer uma barra de rolagem externa.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-121">When you activate Word Wrap, the horizontal scrollbar is removed and lines of code that exceed the width of the Editor's window size automatically wraps to the next displayed line rather than scrolling off the side of the window.</span></span>  
  
#### <a name="to-activate-word-wrap"></a><span data-ttu-id="0fb5a-122">Para ativar a quebra automática de linha</span><span class="sxs-lookup"><span data-stu-id="0fb5a-122">To activate word wrap</span></span>  
  
1.  <span data-ttu-id="0fb5a-123">Clique em **Opções** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="0fb5a-123">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0fb5a-124">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-124">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="0fb5a-125">Abra a pasta de idiomas apropriada (ou **Todos os Idiomas** para afetar todos os idiomas).</span><span class="sxs-lookup"><span data-stu-id="0fb5a-125">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="0fb5a-126">Selecione **Quebra Automática de Linha**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-126">Select **Word wrap**.</span></span>  
  
## <a name="enabling-virtual-space-mode"></a><span data-ttu-id="0fb5a-127">Ativando o modo Espaço Virtual</span><span class="sxs-lookup"><span data-stu-id="0fb5a-127">Enabling Virtual Space Mode</span></span>  
 <span data-ttu-id="0fb5a-128">No modo **Espaço Virtual** , o Editor age como se o espaço após o término de cada linha estivesse cheio com um número infinito de espaços, permitindo que as linhas de código continuem fora da área visível da tela.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-128">In **Virtual Space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.</span></span>  
  
#### <a name="to-enable-virtual-space-mode"></a><span data-ttu-id="0fb5a-129">Para habilitar o modo Espaço Virtual</span><span class="sxs-lookup"><span data-stu-id="0fb5a-129">To enable Virtual Space mode</span></span>  
  
1.  <span data-ttu-id="0fb5a-130">Clique em **Opções** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="0fb5a-130">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0fb5a-131">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-131">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="0fb5a-132">Abra a pasta de idiomas apropriada (ou **Todos os Idiomas** para afetar todos os idiomas).</span><span class="sxs-lookup"><span data-stu-id="0fb5a-132">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="0fb5a-133">Selecione **Habilitar espaço virtual**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-133">Select **Enable virtual space**.</span></span>  
  
 <span data-ttu-id="0fb5a-134">Quando o modo Espaço Virtual não é habilitado, o cursor faz uma quebra automática do final da primeira linha até o primeiro caractere da próxima linha e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-134">When Virtual Space mode is not enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.</span></span>  
  
## <a name="displaying-line-numbers"></a><span data-ttu-id="0fb5a-135">exibindo números de linha</span><span class="sxs-lookup"><span data-stu-id="0fb5a-135">Displaying Line Numbers</span></span>  
 <span data-ttu-id="0fb5a-136">Você pode ativar a numeração de linhas em seu código.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-136">You can turn on line numbering in your code.</span></span> <span data-ttu-id="0fb5a-137">Os números de linha são úteis para navegar por código.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-137">Line numbers are useful for navigating code.</span></span> <span data-ttu-id="0fb5a-138">Para obter mais informações, veja [Navegar em código e texto](navigate-code-and-text.md).</span><span class="sxs-lookup"><span data-stu-id="0fb5a-138">For more information, see [Navigate Code and Text](navigate-code-and-text.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0fb5a-139">Ativar a numeração de linhas não significa que o documento será impresso com números de linha.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-139">Turning on line numbering does not mean that the document will print with line numbers.</span></span> <span data-ttu-id="0fb5a-140">Para imprimir os números de linha, marque a caixa de seleção **Números de linha** no comando **Configurar Página** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="0fb5a-140">For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.</span></span>  
  
#### <a name="to-display-line-numbers-in-code"></a><span data-ttu-id="0fb5a-141">Para exibir números de linha em código</span><span class="sxs-lookup"><span data-stu-id="0fb5a-141">To display line numbers in code</span></span>  
  
1.  <span data-ttu-id="0fb5a-142">Clique em **Opções** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="0fb5a-142">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0fb5a-143">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-143">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="0fb5a-144">Clique em **Todos os Idiomas**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-144">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="0fb5a-145">Clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-145">Click **General**.</span></span>  
  
5.  <span data-ttu-id="0fb5a-146">Selecione **Números de linha**.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-146">Select **Line numbers**.</span></span>  
  
 <span data-ttu-id="0fb5a-147">Para especificar a numeração de linhas para apenas algumas linguagens de programação, selecione **Números de Linha** na pasta apropriada.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-147">To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.</span></span>  
  
## <a name="enabling-full-screen-mode"></a><span data-ttu-id="0fb5a-148">Ativando o modo de tela inteira</span><span class="sxs-lookup"><span data-stu-id="0fb5a-148">Enabling Full Screen Mode</span></span>  
 <span data-ttu-id="0fb5a-149">Você pode optar por ocultar todas as janelas de ferramenta e exibir apenas janelas de documentos habilitando o modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-149">You can choose to hide all tool windows and view only document windows by enabling Full Screen mode.</span></span>  
  
#### <a name="to-enable-full-screen-mode"></a><span data-ttu-id="0fb5a-150">Para habilitar o modo de tela inteira</span><span class="sxs-lookup"><span data-stu-id="0fb5a-150">To enable Full Screen mode</span></span>  
  
1.  <span data-ttu-id="0fb5a-151">Pressione ALT+SHIFT+ENTER para alternar para o modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="0fb5a-151">Press ALT+SHIFT+ENTER to toggle Full Screen mode.</span></span>  
  
## <a name="using-auto-hide-all"></a><span data-ttu-id="0fb5a-152">Usando Ocultar Tudo Automaticamente</span><span class="sxs-lookup"><span data-stu-id="0fb5a-152">Using Auto Hide All</span></span>  
  
#### <a name="to-hide-all-the-tool-windows-at-once"></a><span data-ttu-id="0fb5a-153">Para ocultar todas as janelas de ferramentas de uma só vez</span><span class="sxs-lookup"><span data-stu-id="0fb5a-153">To hide all the tool windows at once</span></span>  
  
1.  <span data-ttu-id="0fb5a-154">Selecione **Ocultar Tudo Automaticamente** no menu **Janela** .</span><span class="sxs-lookup"><span data-stu-id="0fb5a-154">Select **Auto Hide All** on the **Window** menu.</span></span>  
  
  
