---
title: Adicionar uma ação de detalhamento a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a429380f677a309e4e1437a2e3c5036bb4e8a455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571809"
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a><span data-ttu-id="1f299-102">Adicionar uma ação de detalhamento a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1f299-102">Add a Drillthrough Action on a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1f299-103">O relatório aberto quando você clica no link no relatório principal é conhecido como um *relatório detalhado*.</span><span class="sxs-lookup"><span data-stu-id="1f299-103">The report that opens when you click the link in the main report is known as a *drillthrough report*.</span></span> <span data-ttu-id="1f299-104">Este link de detalhamento habilita uma ação de detalhamento.</span><span class="sxs-lookup"><span data-stu-id="1f299-104">This drillthrough link enables a drillthrough action.</span></span>  
  
 <span data-ttu-id="1f299-105">Os relatórios detalhados devem ser publicados no mesmo servidor de relatório do relatório principal, mas podem estar em pastas diferentes.</span><span class="sxs-lookup"><span data-stu-id="1f299-105">Drillthrough reports must be published to the same report server as the main report, but they can be in different folders.</span></span> <span data-ttu-id="1f299-106">Você pode adicionar um link de detalhamento a qualquer item que tenha uma propriedade **Ação** , por exemplo, uma caixa de texto, uma imagem ou pontos de dados de um gráfico.</span><span class="sxs-lookup"><span data-stu-id="1f299-106">You can add a drillthrough link to any item that has an **Action** property, such as a text box, an image, or data points on a chart.</span></span>  
  
 <span data-ttu-id="1f299-107">Para adicionar um link de detalhamento a um relatório, você deve primeiro criar o relatório detalhado a que o relatório principal será vinculado.</span><span class="sxs-lookup"><span data-stu-id="1f299-107">To add a drillthrough link to a report, you must first create the drillthrough report that the main report will link to.</span></span> <span data-ttu-id="1f299-108">Um relatório detalhado contém detalhes comuns sobre um item contido no relatório resumido original e normalmente contém parâmetros que filtram o relatório detalhado com base em parâmetros passados a ele do relatório principal.</span><span class="sxs-lookup"><span data-stu-id="1f299-108">A drillthrough report commonly contains details about an item that is contained in the original summary report, and often contains parameters that filter the drillthrough report based on parameters passed to it from the main report.</span></span> <span data-ttu-id="1f299-109">Para obter mais informações sobre como criar o relatório de detalhamento, consulte [Relatórios de detalhamento &#40;Construtor de Relatórios e SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1f299-109">For more information on creating the drillthrough report, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a><span data-ttu-id="1f299-110">Para adicionar uma ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="1f299-110">To add a drillthrough action</span></span>  
  
1.  <span data-ttu-id="1f299-111">No modo de exibição de Design, clique com o botão direito do mouse na caixa de texto, na imagem ou no gráfico ao qual você quer adicionar um link e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1f299-111">In Design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1f299-112">Na caixa de diálogo **Propriedades** do item, clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="1f299-112">In the item's **Properties** dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="1f299-113">Selecione **Ir para relatório**.</span><span class="sxs-lookup"><span data-stu-id="1f299-113">Select **Go to report**.</span></span> <span data-ttu-id="1f299-114">Serão exibidas seções adicionais na caixa de diálogo para essa opção.</span><span class="sxs-lookup"><span data-stu-id="1f299-114">Additional sections appear in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="1f299-115">Em **Especificar um relatório**, clique em **Procurar** para localizar o relatório desejado ou digite o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="1f299-115">In **Specify a report**, click **Browse** to locate the report that you want to jump to, or type the name of the report.</span></span> <span data-ttu-id="1f299-116">Como alternativa, clique no botão da expressão (**fx**) para criar uma expressão para o nome de relatório.</span><span class="sxs-lookup"><span data-stu-id="1f299-116">Alternatively, click the expression (**fx**) button to create an expression for the report name.</span></span>  
  
     <span data-ttu-id="1f299-117">O formato do caminho para o relatório detalhado é diferente para os modos nativo e integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f299-117">The format of the path to the drillthrough report differs for native and SharePoint integrated mode.</span></span> <span data-ttu-id="1f299-118">Se você procurar um relatório, um caminho no formato correto será fornecido.</span><span class="sxs-lookup"><span data-stu-id="1f299-118">If you browse to the report, a path of the correct format is provided.</span></span> <span data-ttu-id="1f299-119">Para obter mais informações, consulte [Especificando caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1f299-119">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="1f299-120">Caso seja preciso especificar os parâmetros para o relatório detalhado, siga esta etapa.</span><span class="sxs-lookup"><span data-stu-id="1f299-120">If you have to specify parameters for the drillthrough report, follow the next step.</span></span>  
  
5.  <span data-ttu-id="1f299-121">Em **Use estes parâmetros para executar o relatório**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1f299-121">In **Use these parameters to run the report**, click **Add**.</span></span> <span data-ttu-id="1f299-122">Uma linha nova é adicionada à grade de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="1f299-122">A new row is added to the parameter grid.</span></span>  
  
    -   <span data-ttu-id="1f299-123">Na caixa de texto **Nome** , clique na lista suspensa ou digite o nome do parâmetro de relatório no relatório de detalhamento.</span><span class="sxs-lookup"><span data-stu-id="1f299-123">In the **Name** text box, click the drop-down list or type the name of the report parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1f299-124">Os nomes na lista de parâmetros devem corresponder exatamente aos parâmetros esperados no relatório de destino.</span><span class="sxs-lookup"><span data-stu-id="1f299-124">The names in the parameter list must match the expected parameters in the target report exactly.</span></span> <span data-ttu-id="1f299-125">Por exemplo, nomes de parâmetro devem ter maiúsculas e minúsculas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="1f299-125">For example, parameter names must match by case.</span></span> <span data-ttu-id="1f299-126">Caso não correspondam ou se algum parâmetro esperado não for listado, haverá falha no relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="1f299-126">If the names do not match, or if an expected parameter is not listed, the drillthrough report fails.</span></span>  
  
    -   <span data-ttu-id="1f299-127">Em **Valor**, digite ou selecione o valor para passar para o parâmetro no relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="1f299-127">In **Value**, type or select the value to pass to the parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1f299-128">Os valores podem conter uma expressão que seja avaliada como um valor para ser passado para o parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="1f299-128">Values can contain an expression that evaluates to a value to pass to the report parameter.</span></span> <span data-ttu-id="1f299-129">As expressões na lista de valores incluem a lista de campos para o relatório atual.</span><span class="sxs-lookup"><span data-stu-id="1f299-129">The expressions in the value list include the field list for the current report.</span></span>  
  
     <span data-ttu-id="1f299-130">Para obter informações sobre como ocultar parâmetros em relatórios, consulte [Adicionar, alterar ou excluir um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1f299-130">For information on how to hide parameters in reports, see [Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="1f299-131">(Opcional) Para caixas de texto, é útil indicar ao usuário que o texto é um link, alterando a cor e o efeito do texto na guia **Início** da Faixa de Opções.</span><span class="sxs-lookup"><span data-stu-id="1f299-131">(Optional) For text boxes, it is helpful to indicate to the user that the text is a link by changing the color and effect of the text on the **Home** tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="1f299-132">Para testar o link, execute o relatório e clique no item de relatório definido com o link.</span><span class="sxs-lookup"><span data-stu-id="1f299-132">To test the link, run the report and click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f299-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f299-133">See Also</span></span>  
 <span data-ttu-id="1f299-134">[Caixa de diálogo Propriedades de Ação &#40;Construtor de Relatórios e SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1f299-134">[Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1f299-135">[Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1f299-135">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1f299-136">Mostrar dicas de ferramenta em uma série &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1f299-136">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
