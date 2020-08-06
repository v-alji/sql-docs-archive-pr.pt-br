---
title: Personalizar (página Comandos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.vs.customizecom.f1
ms.assetid: c8965f2c-51d9-437d-a6f3-8ac2075ede6b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684fb9a6266fafae00b9881eb64a3642e6c98c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681340"
---
# <a name="customize-commands-page"></a><span data-ttu-id="b6877-102">Personalizar (página Comandos)</span><span class="sxs-lookup"><span data-stu-id="b6877-102">Customize (Commands Page)</span></span>
  <span data-ttu-id="b6877-103">Esta caixa de diálogo permite adicionar e remover comandos em barras de ferramentas e menus, além de alterar as imagens usadas nos botões das barras de ferramentas ou nos comandos de menu.</span><span class="sxs-lookup"><span data-stu-id="b6877-103">This dialog box enables you to add and remove commands on toolbars and menus as well as change the images used for toolbar buttons or menu commands.</span></span> <span data-ttu-id="b6877-104">Você pode acessar a página **Comandos** clicando em **Personalizar** no menu **Ferramentas** e, em seguida, em **Comandos**.</span><span class="sxs-lookup"><span data-stu-id="b6877-104">You can access the **Commands** page by clicking **Customize** on the **Tools** menu and then clicking **Commands**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b6877-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="b6877-105">UI element list</span></span>  
 <span data-ttu-id="b6877-106">**Categorias**</span><span class="sxs-lookup"><span data-stu-id="b6877-106">**Categories**</span></span>  
 <span data-ttu-id="b6877-107">Especifica o conjunto de comandos exibidos na caixa de listagem **Comandos** .</span><span class="sxs-lookup"><span data-stu-id="b6877-107">Specifies the set of commands that are displayed in the **Commands** list box.</span></span> <span data-ttu-id="b6877-108">As categorias de comandos se baseiam em títulos de menus fornecidos pelas ferramentas e designers que o ambiente suporta no momento.</span><span class="sxs-lookup"><span data-stu-id="b6877-108">The categories of commands are based on menu titles provided by the tools and designers that the environment is currently supporting.</span></span> <span data-ttu-id="b6877-109">Essa lista de títulos é dinâmica para que a ordem das categorias e os títulos de menus mudem, de acordo coma as ferramentas e o designer, bem como as personalizações feitas.</span><span class="sxs-lookup"><span data-stu-id="b6877-109">This list of titles is dynamic so that the order of categories and the menu titles change, depending on the tools and the designer, as well as any customizations made to them.</span></span> <span data-ttu-id="b6877-110">Dessa forma, é possível que dois menus de diferentes designers tenham o mesmo nome, para que o mesmo título possa aparecer duas vezes mas oferecer conjuntos de comandos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b6877-110">Therefore, it is possible for two menus from different designers to have the same name, so the same title can appear twice but offer different command sets.</span></span>  
  
 <span data-ttu-id="b6877-111">**Comandos**</span><span class="sxs-lookup"><span data-stu-id="b6877-111">**Commands**</span></span>  
 <span data-ttu-id="b6877-112">Exibe os comandos e imagens de comandos baseadas na categoria que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="b6877-112">Displays the commands and command images based on the category you selected.</span></span> <span data-ttu-id="b6877-113">Você pode arrastar um comando sobre a barra de ferramentas que você deseja personalizar.</span><span class="sxs-lookup"><span data-stu-id="b6877-113">You can drag a command onto the toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="b6877-114">**Modificar Seleção**</span><span class="sxs-lookup"><span data-stu-id="b6877-114">**Modify Selection**</span></span>  
 <span data-ttu-id="b6877-115">Exibe uma lista de comandos você pode usar para personalizar o monitor do botão na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b6877-115">Displays a list of commands you can use to customize the display of the button on the toolbar.</span></span> <span data-ttu-id="b6877-116">Por exemplo, você pode alterar a imagem ou teclas de aceleração, assim como especificar se deve ser exibido o texto em vez de uma imagem do comando.</span><span class="sxs-lookup"><span data-stu-id="b6877-116">For example, you can change the image or accelerator keys, as well as specify whether to display text instead of an image for the command.</span></span> <span data-ttu-id="b6877-117">Este botão está disponível depois que você seleciona um botão de comando em uma barra de ferramentas que você deseja personalizar.</span><span class="sxs-lookup"><span data-stu-id="b6877-117">This button is available after you select a command button on a toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="b6877-118">**Reorganizar Comandos**</span><span class="sxs-lookup"><span data-stu-id="b6877-118">**Rearrange Commands**</span></span>  
 <span data-ttu-id="b6877-119">Exibe a caixa de diálogo **Reorganizar Comandos** , que permite renomear, reordenar, adicionar e remover comandos em menus e barras de ferramentas, além de alterar as imagens de botões e comandos.</span><span class="sxs-lookup"><span data-stu-id="b6877-119">Displays the **Rearrange Commands** dialog box, which allows you to rename, reorder, add, and remove commands on menus and toolbars as well as change button and command images.</span></span>  
  
 <span data-ttu-id="b6877-120">**Teclado**</span><span class="sxs-lookup"><span data-stu-id="b6877-120">**Keyboard**</span></span>  
 <span data-ttu-id="b6877-121">Exibe a página **Teclado** da caixa de diálogo **Opções** para que você possa especificar combinações de teclas de atalho para comandos.</span><span class="sxs-lookup"><span data-stu-id="b6877-121">Displays the **Keyboard** page of the **Options** dialog box so you can specify shortcut key combinations for commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6877-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6877-122">See Also</span></span>  
 [<span data-ttu-id="b6877-123">Personalizar menus e teclas de atalho</span><span class="sxs-lookup"><span data-stu-id="b6877-123">Customize Menus and Shortcut Keys</span></span>](../customize-menus-and-shortcut-keys.md)  
