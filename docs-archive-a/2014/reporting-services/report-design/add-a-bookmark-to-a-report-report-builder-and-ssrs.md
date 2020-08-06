---
title: Adicionar um indicador a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f130562e-5673-40e3-8e01-de7227a21d41
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fae543dd1b071ff38853637a3da57ffd2410c3a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684546"
---
# <a name="add-a-bookmark-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="d02e6-102">Adicionar um indicador a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d02e6-102">Add a Bookmark to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d02e6-103">Adicione indicadores e links de indicadores a um relatório quando quiser fornecer um sumário personalizado ou links de navegação internos personalizados no relatório.</span><span class="sxs-lookup"><span data-stu-id="d02e6-103">Add bookmarks and bookmark links to a report when you want to provide a customized table of contents or to provide customized internal navigation links in the report.</span></span> <span data-ttu-id="d02e6-104">Geralmente, os indicadores são adicionados aos relatórios para conduzir os usuários aos locais para os quais deseja direcioná-los, como tabelas, gráficos ou os valores de grupo exclusivos exibidos em uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="d02e6-104">Typically, you add bookmarks to locations in the report to which you want to direct users, such as to each table or chart or to the unique group values displayed in a table or matrix.</span></span> <span data-ttu-id="d02e6-105">Você pode criar suas próprias cadeias de caracteres para usar como indicadores, ou, em grupos, pode definir o indicador para uma expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="d02e6-105">You can create your own strings to use as bookmarks, or, for groups, you can set the bookmark to the group expression.</span></span>  
  
 <span data-ttu-id="d02e6-106">Depois de criar os indicadores, é possível adicionar os itens de relatórios em que o usuário pode clicar para ir ser conduzido a cada um dos indicadores.</span><span class="sxs-lookup"><span data-stu-id="d02e6-106">After you create bookmarks, you can add report items that the user can click to go to each bookmark.</span></span> <span data-ttu-id="d02e6-107">Geralmente, esses itens são caixas de texto ou imagens.</span><span class="sxs-lookup"><span data-stu-id="d02e6-107">These items are typically text boxes or images.</span></span>  
  
 <span data-ttu-id="d02e6-108">Por exemplo, se o seu relatório exibe uma tabela agrupada por cor, você poderia adicionar um indicador ao cabeçalho do grupo com base na expressão do grupo.</span><span class="sxs-lookup"><span data-stu-id="d02e6-108">For example, if your report displays a table grouped by color, you would add a bookmark based on the group expression to the group header.</span></span> <span data-ttu-id="d02e6-109">Em seguida, você poderia adicionar uma tabela com uma caixa de texto simples no começo do relatório que exibiu os valores de cor e definir o link de indicador nessa caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="d02e6-109">Then you would add a table with a single text box at the beginning of the report that displayed the color values, and set the bookmark link on that text box.</span></span> <span data-ttu-id="d02e6-110">Ao clicar na cor, o relatório é direcionado para a página que exibe a linha de cabeçalho do grupo daquela cor.</span><span class="sxs-lookup"><span data-stu-id="d02e6-110">When you click the color, the report jumps to the page that displays the group header row for that color.</span></span>  
  
 <span data-ttu-id="d02e6-111">O indicador pode ser adicionado a qualquer item do relatório e o link de indicador pode ser adicionado a qualquer item que tenha uma propriedade **Ação** , como uma caixa de texto, uma imagem ou uma séria calculada em um gráfico.</span><span class="sxs-lookup"><span data-stu-id="d02e6-111">You can add a bookmark to any report item and add a bookmark link to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="d02e6-112">Para obter mais informações, consulte [Caixa de diálogo Propriedades da Ação &#40;Construtor de Relatórios e SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d02e6-112">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-bookmark"></a><span data-ttu-id="d02e6-113">Para adicionar um indicador</span><span class="sxs-lookup"><span data-stu-id="d02e6-113">To add a bookmark</span></span>  
  
1.  <span data-ttu-id="d02e6-114">Na exibição de design de relatório, selecione a caixa de texto, imagem, gráfico ou outro item de relatório ao qual você deseja adicionar um indicador.</span><span class="sxs-lookup"><span data-stu-id="d02e6-114">In report design view, select the text box, image, chart, or other report item to which you want to add a bookmark.</span></span> <span data-ttu-id="d02e6-115">As propriedades do item selecionado aparecem no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="d02e6-115">The properties for the selected item appear in the Properties pane.</span></span>  
  
2.  <span data-ttu-id="d02e6-116">Na caixa de texto ao lado de **Indicador**, digite uma cadeia de caracteres que sirva como rótulo para esse indicador.</span><span class="sxs-lookup"><span data-stu-id="d02e6-116">In the text box next to **Bookmark**, type a string that is the label for this bookmark.</span></span> <span data-ttu-id="d02e6-117">Por exemplo, você pode digitar **BikePhoto** como o indicador de uma imagem em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="d02e6-117">For example, you could type **BikePhoto** as the bookmark for an image in your report.</span></span> <span data-ttu-id="d02e6-118">Se preferir, clique no botão Expressão (**fx**) para abrir a caixa de diálogo **Expressão** para especificar uma expressão que seja avaliada como um rótulo.</span><span class="sxs-lookup"><span data-stu-id="d02e6-118">Alternatively, click the Expression (**fx**) button to open the **Expression** dialog box to specify an expression that evaluates to a label.</span></span> <span data-ttu-id="d02e6-119">Em um grupo, a expressão que você digitar deve estar na expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="d02e6-119">For a group, the expression you type should be the group expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d02e6-120">O indicador pode ser qualquer cadeia de caracteres, mas ele deve ser exclusivo no relatório.</span><span class="sxs-lookup"><span data-stu-id="d02e6-120">The bookmark can be any string, but it must be unique in the report.</span></span> <span data-ttu-id="d02e6-121">Caso ele não seja exclusivo, o link para o indicador em questão localizará apenas a primeiro indicador correspondente.</span><span class="sxs-lookup"><span data-stu-id="d02e6-121">If the bookmark is not unique, a link to the bookmark finds the first matching bookmark.</span></span>  
  
### <a name="to-add-a-bookmark-link"></a><span data-ttu-id="d02e6-122">Para adicionar um link de indicador</span><span class="sxs-lookup"><span data-stu-id="d02e6-122">To add a bookmark link</span></span>  
  
1.  <span data-ttu-id="d02e6-123">No modo de exibição de Design, clique com o botão direito do mouse na caixa de texto, na imagem ou no gráfico ao qual você deseja adicionar um link e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d02e6-123">In Design view, right-click the text box, image, chart, to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d02e6-124">Na caixa de diálogo **Propriedades** desse item de relatório, clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="d02e6-124">In The **Properties** dialog box for that report item, click **Action**.</span></span>  
  
3.  <span data-ttu-id="d02e6-125">Selecione **Ir para indicador**.</span><span class="sxs-lookup"><span data-stu-id="d02e6-125">Select **Go to bookmark**.</span></span> <span data-ttu-id="d02e6-126">Aparecerá uma seção adicional na caixa de diálogo para essa opção.</span><span class="sxs-lookup"><span data-stu-id="d02e6-126">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="d02e6-127">Na caixa **Selecionar indicador** , digite ou selecione um indicador ou uma expressão que seja avaliada como um indicador.</span><span class="sxs-lookup"><span data-stu-id="d02e6-127">In the **Select bookmark** box, type or select a bookmark or an expression that evaluates to a bookmark.</span></span> <span data-ttu-id="d02e6-128">Usando o exemplo anterior, digite **BikePhoto** para criar um link para a imagem em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="d02e6-128">Using the previous example, type **BikePhoto** to create a link to the image in your report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="d02e6-129">(Opcional) O texto não é formatado automaticamente como um link.</span><span class="sxs-lookup"><span data-stu-id="d02e6-129">(Optional) The text is not automatically formatted like a link.</span></span> <span data-ttu-id="d02e6-130">Para textos, é recomendável alterar sua cor e seu efeito para indicar que ele é um link.</span><span class="sxs-lookup"><span data-stu-id="d02e6-130">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="d02e6-131">Por exemplo, altere a cor para azul e o efeito para sublinhado na seção **Fonte** da guia Página Inicial da Faixa de Opções.</span><span class="sxs-lookup"><span data-stu-id="d02e6-131">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="d02e6-132">Para testar o link, clique em **Executar** para visualizar o relatório e, em seguida, no item de relatório no qual você definiu esse link.</span><span class="sxs-lookup"><span data-stu-id="d02e6-132">To test the link, click **Run** to preview the report, and then click the report item that you set this link on..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02e6-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d02e6-133">See Also</span></span>  
 <span data-ttu-id="d02e6-134">[Classificação interativa, mapas de documentos e links &#40;Construtor de Relatórios e SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d02e6-134">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d02e6-135">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d02e6-135">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d02e6-136">Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d02e6-136">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
