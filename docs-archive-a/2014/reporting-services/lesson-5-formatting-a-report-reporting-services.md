---
title: 'Lição 5: Formatando um relatório (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00f0d780e957fd9ff995fefb1d033275a7da428d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582826"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a><span data-ttu-id="e2b19-102">Lesson 5: Formatting a Report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="e2b19-102">Lesson 5: Formatting a Report (Reporting Services)</span></span>
  <span data-ttu-id="e2b19-103">Agora que já adicionou uma região de dados e alguns campos ao relatório de ordens de venda, você pode formatar os campos de data e moeda, além dos cabeçalhos da coluna.</span><span class="sxs-lookup"><span data-stu-id="e2b19-103">Now that you've added a data region and some fields to the Sales Orders report, you can format the date and currency fields and the column headers.</span></span>  
  
 <span data-ttu-id="e2b19-104">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="e2b19-104">In this topic:</span></span>  
  
-   [<span data-ttu-id="e2b19-105">Formatar a data</span><span class="sxs-lookup"><span data-stu-id="e2b19-105">Format the Date</span></span>](#bkmk_format_date)  
  
-   [<span data-ttu-id="e2b19-106">Formatar a moeda</span><span class="sxs-lookup"><span data-stu-id="e2b19-106">Format the Currency</span></span>](#bkmk_format_currency)  
  
-   [<span data-ttu-id="e2b19-107">Alterar estilo do texto e larguras da coluna</span><span class="sxs-lookup"><span data-stu-id="e2b19-107">Change Text Style and Column Widths</span></span>](#bkmk_change_textstyle)  
  
##  <a name="format-the-date"></a><a name="bkmk_format_date"></a><span data-ttu-id="e2b19-108">Formatar a data</span><span class="sxs-lookup"><span data-stu-id="e2b19-108">Format the Date</span></span>  
 <span data-ttu-id="e2b19-109">Por padrão, o campo Data exibe informações de data e hora.</span><span class="sxs-lookup"><span data-stu-id="e2b19-109">The Date field displays date and time information by default.</span></span> <span data-ttu-id="e2b19-110">É possível formatá-lo para exibir apenas a data.</span><span class="sxs-lookup"><span data-stu-id="e2b19-110">You can format it to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field"></a><span data-ttu-id="e2b19-111">Para formatar um campo de data</span><span class="sxs-lookup"><span data-stu-id="e2b19-111">To format a date field</span></span>  
  
1.  <span data-ttu-id="e2b19-112">Clique na guia **Design** .</span><span class="sxs-lookup"><span data-stu-id="e2b19-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="e2b19-113">Clique com o botão direito do mouse na célula com a expressão de campo `[Date]` e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="e2b19-113">Right-click the cell with the `[Date]` field expression and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="e2b19-114">Clique em **número**e, no campo **categoria** , selecione `Date` .</span><span class="sxs-lookup"><span data-stu-id="e2b19-114">Click **Number**, and then in the **Category** field, select `Date`.</span></span>  
  
4.  <span data-ttu-id="e2b19-115">Na caixa **Tipo** , selecione **31 de janeiro de 2000**.</span><span class="sxs-lookup"><span data-stu-id="e2b19-115">In the **Type** box, select **January 31, 2000**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="e2b19-116">Visualize o relatório para ver a alteração no campo `[Date]` e, em seguida, altere de volta para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="e2b19-116">Preview the report to see the change to the `[Date]` field and then change back to design view.</span></span>  
  
##  <a name="format-the-currency"></a><a name="bkmk_format_currency"></a><span data-ttu-id="e2b19-117">Formatar a moeda</span><span class="sxs-lookup"><span data-stu-id="e2b19-117">Format the Currency</span></span>  
 <span data-ttu-id="e2b19-118">O campo LineTotal exibe um número geral.</span><span class="sxs-lookup"><span data-stu-id="e2b19-118">The LineTotal field displays a general number.</span></span> <span data-ttu-id="e2b19-119">Formate-o para exibir o número como moeda.</span><span class="sxs-lookup"><span data-stu-id="e2b19-119">Format it to display the number as currency.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="e2b19-120">Para formatar um campo de conversor de moedas</span><span class="sxs-lookup"><span data-stu-id="e2b19-120">To format a currency field</span></span>  
  
1.  <span data-ttu-id="e2b19-121">Clique com o botão direito do mouse na célula com a expressão de campo `[LineTotal]` e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="e2b19-121">Right-click the cell with the `[LineTotal]` field expression and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="e2b19-122">Clique em **Número**, e no campo **Categoria** , selecione **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="e2b19-122">Click **Number**, and in the **Category** field, select **Currency**.</span></span>  
  
3.  <span data-ttu-id="e2b19-123">Caso a configuração regional seja inglês (Estados Unidos), os padrões devem ser:</span><span class="sxs-lookup"><span data-stu-id="e2b19-123">If your regional setting is English (United States), the defaults should be:</span></span>  
  
    -   <span data-ttu-id="e2b19-124">**Casas decimais: 2**</span><span class="sxs-lookup"><span data-stu-id="e2b19-124">**Decimal places: 2**</span></span>  
  
    -   <span data-ttu-id="e2b19-125">**Números negativos: (R$ 1.2345,00)**</span><span class="sxs-lookup"><span data-stu-id="e2b19-125">**Negative numbers: ($12345.00)**</span></span>  
  
    -   <span data-ttu-id="e2b19-126">**Símbolo: R$ português (Brasil)**</span><span class="sxs-lookup"><span data-stu-id="e2b19-126">**Symbol: $ English (United States)**</span></span>  
  
4.  <span data-ttu-id="e2b19-127">Selecione **Usar separador de milhar (.)**.</span><span class="sxs-lookup"><span data-stu-id="e2b19-127">Select **Use 1000 separator (,)**.</span></span>  
  
     <span data-ttu-id="e2b19-128">Caso o texto de exemplo seja **$12.345,00**, as configurações estão corretas.</span><span class="sxs-lookup"><span data-stu-id="e2b19-128">If the sample text is:**$12,345.00**, then your settings are correct.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="e2b19-129">Visualize o relatório para ver a alteração no campo `[LineTotal]` e, em seguida, altere de volta para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="e2b19-129">Preview the report to see the change to the `[LineTotal]` field and then change back to design view.</span></span>  
  
##  <a name="change-text-style-and-column-widths"></a><a name="bkmk_change_textstyle"></a><span data-ttu-id="e2b19-130">Alterar estilo de texto e larguras de coluna</span><span class="sxs-lookup"><span data-stu-id="e2b19-130">Change Text Style and Column Widths</span></span>  
 <span data-ttu-id="e2b19-131">Também é possível alterar a formatação da linha do cabeçalho para diferenciá-la das linhas de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="e2b19-131">You can also change the formatting of the header row to differentiate it from the rows of data in the report.</span></span> <span data-ttu-id="e2b19-132">Por fim, você ajustará as larguras das colunas.</span><span class="sxs-lookup"><span data-stu-id="e2b19-132">Lastly, you will adjust the widths of the columns.</span></span>  
  
#### <a name="to-format-header-rows-and-table-columns"></a><span data-ttu-id="e2b19-133">Para formatar as linhas do cabeçalho e as colunas da tabela</span><span class="sxs-lookup"><span data-stu-id="e2b19-133">To format header rows and table columns</span></span>  
  
1.  <span data-ttu-id="e2b19-134">Clique na tabela de forma que os identificadores de coluna e linha sejam exibidos acima e ao lado da tabela.</span><span class="sxs-lookup"><span data-stu-id="e2b19-134">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="e2b19-135">![Design, Tabela com linha de cabeçalho e linha de detalhes](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Tabela com linha de cabeçalho e linha de detalhes")</span><span class="sxs-lookup"><span data-stu-id="e2b19-135">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
     <span data-ttu-id="e2b19-136">As barras em cinza ao longo da parte superior e ao lado da tabela são os identificadores de coluna e de linha.</span><span class="sxs-lookup"><span data-stu-id="e2b19-136">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
2.  <span data-ttu-id="e2b19-137">Aponte para a linha entre os identificadores de coluna para que o cursor seja alterado para uma seta dupla.</span><span class="sxs-lookup"><span data-stu-id="e2b19-137">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="e2b19-138">Arraste as colunas de acordo com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="e2b19-138">Drag the columns to the size you want.</span></span>  
  
3.  <span data-ttu-id="e2b19-139">Selecione a linha que contém rótulos de cabeçalho de coluna e, no menu **Formatar** , aponte para **Fonte** e clique em **Negrito**.</span><span class="sxs-lookup"><span data-stu-id="e2b19-139">Select the row containing column header labels and from the **Format** menu, point to **Font** and then click **Bold**.</span></span>  
  
4.  <span data-ttu-id="e2b19-140">Para visualizar o relatório, clique na guia **Visualizar** . Ele deve ser semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="e2b19-140">To preview your report, click the **Preview** tab. It should look something like this:</span></span>  
  
     <span data-ttu-id="e2b19-141">![Visualização da tabela com cabeçalhos de colunas em negrito](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Visualização da tabela com cabeçalhos de colunas em negrito")</span><span class="sxs-lookup"><span data-stu-id="e2b19-141">![Preview of table with bold column headers](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Preview of table with bold column headers")</span></span>  
  
5.  <span data-ttu-id="e2b19-142">No menu **Arquivo** , clique em **Salvar Tudo** para salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e2b19-142">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e2b19-143">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e2b19-143">Next Steps</span></span>  
 <span data-ttu-id="e2b19-144">Você formatou cabeçalhos de coluna e valores de data e moeda com êxito.</span><span class="sxs-lookup"><span data-stu-id="e2b19-144">You have successfully formatted column headers and date and currency values.</span></span> <span data-ttu-id="e2b19-145">Agora você adicionará agrupamento e totais ao relatório.</span><span class="sxs-lookup"><span data-stu-id="e2b19-145">Next, you will add grouping and totals to your report.</span></span> <span data-ttu-id="e2b19-146">Consulte a [Lição 6: Adicionando agrupamentos e totais &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="e2b19-146">See [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b19-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2b19-147">See Also</span></span>  
 <span data-ttu-id="e2b19-148">[Formatando números e datas &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2b19-148">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e2b19-149">Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e2b19-149">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
