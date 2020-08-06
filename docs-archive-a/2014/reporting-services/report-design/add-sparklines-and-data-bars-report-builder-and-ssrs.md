---
title: Adicionar minigráficos e barras de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55ec15354cdc78dd9678b9466f30d2fca0a73adc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570457"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="93093-102">Adicionar minigráficos e barras de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="93093-102">Add Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="93093-103">Minigráficos e barras de dados são pequenos gráficos que transmitem muitas informações com poucos detalhes externos.</span><span class="sxs-lookup"><span data-stu-id="93093-103">Sparklines and data bars are small, spare charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="93093-104">Para obter mais informações sobre eles, consulte [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93093-104">For more information about them, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="93093-105">Minigráficos e barras de dados geralmente são colocados nas células em uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="93093-105">Sparklines and data bars are most commonly placed in cells in a table or matrix.</span></span> <span data-ttu-id="93093-106">Em geral, os minigráficos exibem apenas uma série cada.</span><span class="sxs-lookup"><span data-stu-id="93093-106">Sparklines usually display only one series each.</span></span> <span data-ttu-id="93093-107">As barras de dados podem conter um ou mais pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="93093-107">Data bars can contain one or more data points.</span></span> <span data-ttu-id="93093-108">Os minigráficos e as barras de dados exibem apenas uma série cada e causam impacto por repetir as informações da série para cada linha na tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="93093-108">Both sparklines and data bars derive their impact from repeating the series information for each row in the table or matrix.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a><span data-ttu-id="93093-109">Para adicionar um minigráfico ou uma barra de dados a uma tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="93093-109">To add a sparkline or data bar to a table or matrix</span></span>  
  
1.  <span data-ttu-id="93093-110">Se você ainda não tiver feito isso, crie uma tabela ou matriz com os dados que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="93093-110">If you have not done so already, create a table or matrix with the data you want to display.</span></span> <span data-ttu-id="93093-111">Para obter mais informações, consulte [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93093-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="93093-112">Insira uma coluna em sua tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="93093-112">Insert a column in your table or matrix.</span></span> <span data-ttu-id="93093-113">Para obter mais informações, consulte [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93093-113">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="93093-114">Na guia **Inserir** , clique em **Minigráfico** ou **Barra de Dados**e clique em uma célula na nova coluna.</span><span class="sxs-lookup"><span data-stu-id="93093-114">On the **Insert** tab, click **Sparkline** or **Data Bar**, and then click in a cell in the new column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93093-115">Você não pode colocar minigráficos em um grupo de detalhes em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="93093-115">You cannot place sparklines in a detail group in a table.</span></span> <span data-ttu-id="93093-116">Eles devem ficar em uma célula associada a um grupo.</span><span class="sxs-lookup"><span data-stu-id="93093-116">They must go in a cell associated with a group.</span></span>  
  
4.  <span data-ttu-id="93093-117">Na caixa de diálogo **Alterar Tipo de Minigráfico/Barra de Dados** , clique no tipo desejado de minigráfico ou barra de dados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="93093-117">In the **Change Sparkline/Data Bar Type** dialog box, click the kind of sparkline or data bar you want, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="93093-118">Clique no minigráfico ou na barra de dados.</span><span class="sxs-lookup"><span data-stu-id="93093-118">Click the sparkline or data bar.</span></span>  
  
     <span data-ttu-id="93093-119">O painel **Dados do Gráfico** é aberto.</span><span class="sxs-lookup"><span data-stu-id="93093-119">The **Chart Data** pane opens.</span></span>  
  
6.  <span data-ttu-id="93093-120">Na área **Valores** , em **Adicionar Campos** , clique no sinal de adição (**+**) e clique no campo cujos valores você deseja inserir no gráfico.</span><span class="sxs-lookup"><span data-stu-id="93093-120">In the **Values** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want charted.</span></span>  
  
7.  <span data-ttu-id="93093-121">Na área **Grupos de Categorias** , em **Adicionar Campos** , clique no sinal de adição (**+**) e clique no campo por cujos valores você deseja agrupar.</span><span class="sxs-lookup"><span data-stu-id="93093-121">In the **Category Groups** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want to group by.</span></span>  
  
     <span data-ttu-id="93093-122">Em geral, para minigráficos e barras de dados, você não adicionará um campo à área **Grupo de Séries** porque somente deseja uma série para cada linha.</span><span class="sxs-lookup"><span data-stu-id="93093-122">Typically for sparklines and data bars, you will not add a field to the **Series Group** area because you only want one series for each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93093-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93093-123">See Also</span></span>  
 <span data-ttu-id="93093-124">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="93093-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="93093-125">Alinhar os dados de um gráfico em uma tabela ou matriz &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="93093-125">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
