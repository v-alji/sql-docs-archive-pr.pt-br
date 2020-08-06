---
title: 'Lição 4: Adicionando uma tabela ao relatório (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52694168bd60b8e3807db6204f33a89815573093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570521"
---
# <a name="lesson-4-adding-a-table-to-the-report-reporting-services"></a><span data-ttu-id="eaec6-102">Lição 4: Adicionando uma tabela ao relatório (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="eaec6-102">Lesson 4: Adding a Table to the Report (Reporting Services)</span></span>
  <span data-ttu-id="eaec6-103">Depois de definir o conjunto de dados, você pode começar a criar o relatório.</span><span class="sxs-lookup"><span data-stu-id="eaec6-103">After the dataset is defined, you can start designing the report.</span></span> <span data-ttu-id="eaec6-104">Um layout de relatório é criado arrastando e soltando regiões de dados, caixas de texto, imagens e outros itens que você deseja incluir no relatório na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="eaec6-104">You create a report layout by dragging and dropping data regions, text boxes, images, and other items that you want to include in your report to the design surface.</span></span>  
  
 <span data-ttu-id="eaec6-105">Itens que contêm linhas de dados repetidas de conjuntos de dados subjacentes são chamados de *regiões de dados*.</span><span class="sxs-lookup"><span data-stu-id="eaec6-105">Items that contain repeated rows of data from underlying datasets are called *data regions*.</span></span> <span data-ttu-id="eaec6-106">Um relatório básico terá apenas uma região de dados, mas é possível adicionar mais, por exemplo, se você desejar adicionar um gráfico ao relatório tabular.</span><span class="sxs-lookup"><span data-stu-id="eaec6-106">A basic report will have only one data region, but you can add more, for example, if you want to add a chart to your tabular report.</span></span> <span data-ttu-id="eaec6-107">Depois de adicionar uma região de dados, você pode adicionar campos à região de dados.</span><span class="sxs-lookup"><span data-stu-id="eaec6-107">After you add a data region, you can add fields to the data region.</span></span>  
  
### <a name="to-add-a-table-data-region-and-fields-to-a-report-layout"></a><span data-ttu-id="eaec6-108">Para adicionar uma região de dados de Tabela e campos ao layout de um relatório</span><span class="sxs-lookup"><span data-stu-id="eaec6-108">To add a Table data region and fields to a report layout</span></span>  
  
1.  <span data-ttu-id="eaec6-109">Na **Caixa de Ferramentas**, clique em **Tabela**, clique na superfície de design e arraste o mouse.</span><span class="sxs-lookup"><span data-stu-id="eaec6-109">In the **Toolbox**, click **Table**, and then click on the design surface and drag the mouse.</span></span> <span data-ttu-id="eaec6-110">O Designer de Relatórios desenha uma região de dados de tabela com três colunas no centro da superfície de design.</span><span class="sxs-lookup"><span data-stu-id="eaec6-110">Report Designer draws a table data region with three columns in the center of the design surface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eaec6-111">A **Caixa de Ferramentas** pode aparecer como uma guia no lado esquerdo do painel **Dados do Relatório** .</span><span class="sxs-lookup"><span data-stu-id="eaec6-111">The **Toolbox** may appear as a tab on the left side of the **Report Data** pane.</span></span> <span data-ttu-id="eaec6-112">Para abrir a **caixa de ferramentas**, mova o ponteiro sobre a guia **caixa de ferramentas** . Se a **caixa de ferramentas** não estiver visível, no menu **Exibir** , clique em **caixa de ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="eaec6-112">To open the **Toolbox**, move the pointer over the **Toolbox** tab. If the **Toolbox** is not visible, from the **View** menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="eaec6-113">No painel **data do relatório** , expanda o conjunto de dados **AdventureWorksDataSet** para exibir os campos.</span><span class="sxs-lookup"><span data-stu-id="eaec6-113">In the **Report Data** pane, expand the **AdventureWorksDataset** dataset to display the fields.</span></span>  
  
3.  <span data-ttu-id="eaec6-114">Arraste o campo Data do painel **Dados do Relatório** até a primeira coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="eaec6-114">Drag the Date field from the **Report Data** pane to the first column in the table.</span></span>  
  
     <span data-ttu-id="eaec6-115">Quando você solta o campo na primeira coluna, duas coisas acontecem.</span><span class="sxs-lookup"><span data-stu-id="eaec6-115">When you drop the field into the first column, two things happen.</span></span> <span data-ttu-id="eaec6-116">Primeiro, a célula de dados exibirá o nome do campo, conhecido como a *expressão de campo*, em colchetes: `[Date]`.</span><span class="sxs-lookup"><span data-stu-id="eaec6-116">First, the data cell will display the field name, known as the *field expression*, in brackets: `[Date]`.</span></span> <span data-ttu-id="eaec6-117">Em seguida, um valor de cabeçalho de coluna é adicionado automaticamente à linha Cabeçalho, exatamente acima da expressão de campo.</span><span class="sxs-lookup"><span data-stu-id="eaec6-117">Second, a column header value is automatically added to Header row, just above the field expression.</span></span> <span data-ttu-id="eaec6-118">Por padrão, a coluna é o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="eaec6-118">By default, the column is the name of the field.</span></span> <span data-ttu-id="eaec6-119">Você pode selecionar o texto da linha Cabeçalho e digitar um novo nome.</span><span class="sxs-lookup"><span data-stu-id="eaec6-119">You can select the Header row text and type a new name.</span></span>  
  
4.  <span data-ttu-id="eaec6-120">Arraste o campo Ordem do painel **Dados do Relatório** até a segunda coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="eaec6-120">Drag the Order field from the **Report Data** pane to the second column in the table.</span></span>  
  
5.  <span data-ttu-id="eaec6-121">Arraste o campo Produto do painel **Dados do Relatório** até a terceira coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="eaec6-121">Drag the Product field from the **Report Data** pane to the third column in the table.</span></span>  
  
6.  <span data-ttu-id="eaec6-122">Arraste o campo Quantidade para a margem direita da terceira coluna até obter um cursor vertical e o ponteiro do mouse se tornar um sinal de mais [+].</span><span class="sxs-lookup"><span data-stu-id="eaec6-122">Drag the Qty field to the right edge of the third column until you get a vertical cursor and the mouse pointer has a plus sign [+].</span></span> <span data-ttu-id="eaec6-123">Quando você liberar o botão do mouse, uma quarta coluna será criada para `[Qty]`.</span><span class="sxs-lookup"><span data-stu-id="eaec6-123">When you release the mouse button, a fourth column is created for `[Qty]`.</span></span>  
  
7.  <span data-ttu-id="eaec6-124">Adicione o campo LineTotal da mesma maneira criando uma quinta coluna.</span><span class="sxs-lookup"><span data-stu-id="eaec6-124">Add the LineTotal field in the same way, creating a fifth column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eaec6-125">O cabeçalho de coluna é Total de Linha.</span><span class="sxs-lookup"><span data-stu-id="eaec6-125">The column header is Line Total.</span></span> <span data-ttu-id="eaec6-126">O Designer de Relatórios cria automaticamente um nome amigável para a coluna dividindo LineTotal em duas palavras.</span><span class="sxs-lookup"><span data-stu-id="eaec6-126">Report Designer automatically creates a friendly name for the column by splitting LineTotal into two words.</span></span>  
  
     <span data-ttu-id="eaec6-127">O diagrama a seguir mostra uma região de dados de tabela que foi populada com estes campos: Data, Ordem, Produto, Quantidade e Total da Linha.</span><span class="sxs-lookup"><span data-stu-id="eaec6-127">The following diagram shows a table data region that has been populated with these fields: Date, Order, Product, Qty, and Line Total.</span></span>  
  
     <span data-ttu-id="eaec6-128">![Design, Tabela com linha de cabeçalho e linha de detalhes](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Tabela com linha de cabeçalho e linha de detalhes")</span><span class="sxs-lookup"><span data-stu-id="eaec6-128">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
## <a name="preview-your-report"></a><span data-ttu-id="eaec6-129">Visualize o relatório</span><span class="sxs-lookup"><span data-stu-id="eaec6-129">Preview Your Report</span></span>  
 <span data-ttu-id="eaec6-130">A visualização de um relatório permite exibir o relatório renderizado sem que seja necessário publicá-lo primeiro em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eaec6-130">Previewing a report enables you to view the rendered report without having to first publish it to a report server.</span></span> <span data-ttu-id="eaec6-131">Provavelmente, você desejará visualizar o relatório com frequência durante o tempo de design.</span><span class="sxs-lookup"><span data-stu-id="eaec6-131">You will probably want to preview your report frequently during design time.</span></span> <span data-ttu-id="eaec6-132">Visualizar o relatório também executará a validação nas conexões de design e de dados, para que você possa corrigir erros e problemas antes de publicar o relatório em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eaec6-132">Previewing the report will also run validation on the design and data connections so you can correct errors and issues before publishing the report to a report server.</span></span>  
  
#### <a name="to-preview-a-report"></a><span data-ttu-id="eaec6-133">Para visualizar um relatório</span><span class="sxs-lookup"><span data-stu-id="eaec6-133">To preview a report</span></span>  
  
-   <span data-ttu-id="eaec6-134">Clique na guia **Visualizar** . Report Designer executa o relatório e o exibe no modo de exibição de visualização.</span><span class="sxs-lookup"><span data-stu-id="eaec6-134">Click the **Preview** tab. Report Designer runs the report and displays it in Preview view.</span></span>  
  
     <span data-ttu-id="eaec6-135">O diagrama a seguir mostra parte do relatório na exibição Visualização.</span><span class="sxs-lookup"><span data-stu-id="eaec6-135">The following diagram shows part of the report in Preview view.</span></span>  
  
     <span data-ttu-id="eaec6-136">![Visualização, Linhas de detalhes da tabela com 5 colunas](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Visualização, Linhas de detalhes da tabela com 5 colunas")</span><span class="sxs-lookup"><span data-stu-id="eaec6-136">![Preview, Detail rows of table with 5 columns](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Preview, Detail rows of table with 5 columns")</span></span>  
  
     <span data-ttu-id="eaec6-137">Observe que a moeda (na coluna Total da Linha) tem seis casas decimais e a data inclui um carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="eaec6-137">Notice that the currency (in the Line Total column) has six places after the decimal, and the date has includes a time stamp.</span></span> <span data-ttu-id="eaec6-138">Você vai corrigir essa formatação na próxima lição.</span><span class="sxs-lookup"><span data-stu-id="eaec6-138">You're going to fix that formatting in the next lesson.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eaec6-139">No menu **Arquivo** , clique em **Salvar Tudo** para salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="eaec6-139">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eaec6-140">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="eaec6-140">Next Steps</span></span>  
 <span data-ttu-id="eaec6-141">Você adicionou uma região de dados de Tabela ao relatório, adicionou campos à região de dados e visualizou o relatório com êxito.</span><span class="sxs-lookup"><span data-stu-id="eaec6-141">You have successfully added a Table data region to your report, added fields to the data region, and previewed your report.</span></span> <span data-ttu-id="eaec6-142">Em seguida, você formatará cabeçalhos de colunas e valores de data e de moeda.</span><span class="sxs-lookup"><span data-stu-id="eaec6-142">Next, you will format column headers and date and currency values.</span></span> <span data-ttu-id="eaec6-143">Consulte [Lição 5: Formatando um relatório &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="eaec6-143">See [Lesson 5: Formatting a Report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaec6-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eaec6-144">See Also</span></span>  
 <span data-ttu-id="eaec6-145">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="eaec6-145">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="eaec6-146">Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eaec6-146">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
  
  
