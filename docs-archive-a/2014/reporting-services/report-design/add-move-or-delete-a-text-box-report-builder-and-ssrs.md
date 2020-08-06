---
title: Adicionar, mover ou excluir uma caixa de texto (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f042cf81-d933-4ac7-9287-c074a46bde98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd85415fd2f0bac2a37b3fbda06795e10f351b19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684537"
---
# <a name="add-move-or-delete-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="b01e4-102">Adicionar, mover ou excluir uma caixa de texto (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b01e4-102">Add, Move, or Delete a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b01e4-103">As caixas de texto constituem o item de relatório mais utilizado em relatórios.</span><span class="sxs-lookup"><span data-stu-id="b01e4-103">Text boxes are the most commonly used report item in reports.</span></span> <span data-ttu-id="b01e4-104">Você pode adicionar uma caixa de texto ao corpo do relatório para exibir informações como títulos, opções de parâmetro, campos internos e datas.</span><span class="sxs-lookup"><span data-stu-id="b01e4-104">You can add a text box to the report body to display information such as titles, parameter choices, built-in fields, and dates.</span></span>  
  
 <span data-ttu-id="b01e4-105">Cada célula de uma tabela ou matriz é uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-105">Every cell in a table or matrix is really a text box.</span></span> <span data-ttu-id="b01e4-106">Quase todos os dados exibidos em um relatório com tabelas e matrizes são o resultado do processador que avalia o conteúdo de cada caixa de texto no relatório.</span><span class="sxs-lookup"><span data-stu-id="b01e4-106">Almost all report data displayed in a report with tables and matrices is the result of the report processor evaluating the contents of each text box in the report.</span></span> <span data-ttu-id="b01e4-107">Desse modo, você pode formatar células da mesma maneira como formataria outras caixas de texto fora da região de dados.</span><span class="sxs-lookup"><span data-stu-id="b01e4-107">As such, you can format cells in the same way you would format other text boxes outside the data region.</span></span>  
  
 <span data-ttu-id="b01e4-108">Para adicionar uma caixa de texto a uma região de dados lista, você deve adicionar a caixa de texto e arrastá-la para a lista.</span><span class="sxs-lookup"><span data-stu-id="b01e4-108">To add a text box to a list data region, you must first add the text box and then drag it into the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b01e4-109">Quando você clica em uma caixa de texto, está editando o texto imediatamente na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-109">When you click a text box, you're immediately editing the text in the text box.</span></span> <span data-ttu-id="b01e4-110">Para selecionar a caixa de texto propriamente dita, não o texto contido, pressione ESC.</span><span class="sxs-lookup"><span data-stu-id="b01e4-110">To select the text box itself, not the text in it, press ESC.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-text-box"></a><span data-ttu-id="b01e4-111">Para adicionar uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="b01e4-111">To add a text box</span></span>  
  
1.  <span data-ttu-id="b01e4-112">Na guia **Inserir** , na exibição Design, clique em **Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="b01e4-112">On the **Insert** tab in Design view, click **Text Box**.</span></span>  
  
2.  <span data-ttu-id="b01e4-113">Na superfície de design, clique e arraste uma caixa até obter o tamanho desejado da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-113">On the design surface, click and then drag a box to the desired size of the text box.</span></span> <span data-ttu-id="b01e4-114">Se preferir, clique na superfície de design para criar uma caixa de tamanho padrão.</span><span class="sxs-lookup"><span data-stu-id="b01e4-114">Alternatively, click the design surface to create a text box of default size.</span></span>  
  
### <a name="to-add-a-text-box-in-a-list"></a><span data-ttu-id="b01e4-115">Para adicionar uma caixa de texto a uma lista</span><span class="sxs-lookup"><span data-stu-id="b01e4-115">To add a text box in a list</span></span>  
  
1.  <span data-ttu-id="b01e4-116">Na guia **Inserir** , na exibição de design de relatório, clique em **Lista**.</span><span class="sxs-lookup"><span data-stu-id="b01e4-116">On the **Insert** tab in report design view, click **List**.</span></span>  
  
2.  <span data-ttu-id="b01e4-117">Na superfície de design, clique e arraste uma caixa até obter o tamanho desejado da lista.</span><span class="sxs-lookup"><span data-stu-id="b01e4-117">On the design surface, click and then drag a box to the desired size of the list.</span></span> <span data-ttu-id="b01e4-118">Se preferir, clique na superfície de design para criar uma lista de tamanho padrão.</span><span class="sxs-lookup"><span data-stu-id="b01e4-118">Alternatively, click the design surface to create a list of default size.</span></span>  
  
3.  <span data-ttu-id="b01e4-119">Na guia **Inserir** , clique em **Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="b01e4-119">On the **Insert** tab, click **Text Box**.</span></span>  
  
4.  <span data-ttu-id="b01e4-120">Na superfície de design, clique e arraste uma caixa até obter o tamanho desejado da caixa de texto na lista que você adicionou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b01e4-120">On the design surface, click and then drag a box to the desired size of the text box inside the list you added in step 1.</span></span> <span data-ttu-id="b01e4-121">Se preferir, clique na superfície de design na lista para criar uma caixa de texto de tamanho padrão.</span><span class="sxs-lookup"><span data-stu-id="b01e4-121">Alternatively, click the design surface inside the list to create a text box of default size.</span></span>  
  
5.  <span data-ttu-id="b01e4-122">Para confirmar se a caixa de texto está aninhada corretamente dentro da lista, selecione-a.</span><span class="sxs-lookup"><span data-stu-id="b01e4-122">To confirm the text box is correctly nested inside the list, select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b01e4-123">Se você clicar na caixa de texto e estiver no modo de edição, pressione ESC para selecionar a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-123">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
6.  <span data-ttu-id="b01e4-124">No painel Propriedades, verifique se a propriedade **Pai** é um retângulo que foi adicionado automaticamente à região de dados da lista.</span><span class="sxs-lookup"><span data-stu-id="b01e4-124">In the Properties pane, verify that the **Parent** property is the rectangle that was automatically added to the list data region.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b01e4-125">Se o painel Propriedades não estiver visível, marque **Propriedades** na guia **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="b01e4-125">If the Properties pane is not visible, check **Properties** on the **View** tab.</span></span>  
  
### <a name="to-move-a-text-box"></a><span data-ttu-id="b01e4-126">Para mover uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="b01e4-126">To move a text box</span></span>  
  
1.  <span data-ttu-id="b01e4-127">Na exibição de design de relatório, clique em um espaço vazio dentro da caixa de texto para selecionar a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-127">In report design view, click any empty space within the text box to select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b01e4-128">Se você clicar na caixa de texto e estiver no modo de edição, pressione ESC para selecionar a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-128">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
2.  <span data-ttu-id="b01e4-129">Clique na alça da caixa de texto e arraste-a para o novo local.</span><span class="sxs-lookup"><span data-stu-id="b01e4-129">Click the text box handle and drag the text box to the new location.</span></span> <span data-ttu-id="b01e4-130">Se preferir, use as teclas de seta para mover a caixa de texto selecionada nas direções horizontal e vertical.</span><span class="sxs-lookup"><span data-stu-id="b01e4-130">Alternatively, you can use the arrow keys to move a selected text box horizontally or vertically.</span></span> <span data-ttu-id="b01e4-131">Para mover a caixa de texto na superfície de design em incrementos menores, pressione a tecla CTRL e as teclas de seta.</span><span class="sxs-lookup"><span data-stu-id="b01e4-131">To move the text box in smaller increments on the design surface, hold down CTRL plus the arrow keys.</span></span>  
  
### <a name="to-delete-a-text-box"></a><span data-ttu-id="b01e4-132">Para excluir uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="b01e4-132">To delete a text box</span></span>  
  
1.  <span data-ttu-id="b01e4-133">No modo de exibição de Design de relatório, clique com o botão direito do mouse em um espaço vazio dentro da caixa de texto para selecioná-la e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b01e4-133">In report design view, right-click any empty space within the text box to select it, and then click **Delete**.</span></span> <span data-ttu-id="b01e4-134">Se preferir, clique em um espaço vazio dentro da caixa de texto e pressione DELETE.</span><span class="sxs-lookup"><span data-stu-id="b01e4-134">Alternatively, click any empty space within the text box, and then press DELETE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b01e4-135">Se você clicar na caixa de texto e estiver no modo de edição, pressione ESC para selecionar a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b01e4-135">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01e4-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b01e4-136">See Also</span></span>  
 <span data-ttu-id="b01e4-137">[Caixas de texto &#40;Construtor de Relatórios e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b01e4-137">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b01e4-138">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b01e4-138">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b01e4-139">Atalhos de teclado &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="b01e4-139">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](../report-builder/keyboard-shortcuts-report-builder.md)  
  
  
