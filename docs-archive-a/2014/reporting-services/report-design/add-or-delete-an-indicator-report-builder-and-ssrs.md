---
title: Adicionar ou excluir um indicador (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 186ed4f5b6cf7cb239dc7c33a11089c11bccae14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682137"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a><span data-ttu-id="5ed9a-102">Adicionar ou excluir um indicador (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5ed9a-102">Add or Delete an Indicator (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5ed9a-103">Os indicadores são medidores mínimos que transmitem o estado de um único valor de dados em um relance.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-103">Indicators are minimal gauges that convey the state of a single data value at a glance.</span></span> <span data-ttu-id="5ed9a-104">Para obter mais informações sobre eles, consulte [Indicadores &#40;Construtor de Relatórios e SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5ed9a-104">For more information about them, see [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5ed9a-105">Geralmente, os indicadores são colocados nas células de uma tabela ou matriz, mas você também pode usar indicadores por si mesmos, lado a lado com indicadores ou indicadores inseridos.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-105">Indicators are commonly placed in cells in a table or matrix, but you can also use indicators by themselves, side-by-side with gauges, or embedded in gauges.</span></span>  
  
 <span data-ttu-id="5ed9a-106">Quando você adiciona um indicador pela primeira vez, por padrão ele é configurado para usar porcentagens como unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-106">When you first add an indicator, it is by default configured to use percentages as measurement units.</span></span> <span data-ttu-id="5ed9a-107">Os intervalos de porcentagens são distribuídos uniformemente nos membros do conjunto de indicadores, e o escopo de valores mostrados pelo indicador é o pai do indicador, como uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-107">The percentage ranges are evenly distributed across members of the indicator set, and the scope of values shown by the indicator is the parent of the indicator such as a table or matrix.</span></span>  
  
 <span data-ttu-id="5ed9a-108">Você pode atualizar os valores e os estados de indicadores.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-108">You can update the values and states of indicators.</span></span> <span data-ttu-id="5ed9a-109">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5ed9a-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5ed9a-110">Alterar os ícones de indicadores e os conjuntos de indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ed9a-110">Change Indicator Icons and Indicator Sets &#40;Report Builder and SSRS&#41;</span></span>](change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="5ed9a-111">Definir e configurar unidades de medida &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ed9a-111">Set and Configure Measurement Units &#40;Report Builder and SSRS&#41;</span></span>](set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="5ed9a-112">Definir o escopo da sincronização &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ed9a-112">Set Synchronization Scope &#40;Report Builder and SSRS&#41;</span></span>](set-synchronization-scope-report-builder-and-ssrs.md)  
  
 <span data-ttu-id="5ed9a-113">Como um indicador é posicionado dentro do painel de medidores, você precisa selecionar o indicador, em vez do painel, quando deseja configurar o indicador usando a caixa de diálogo **Propriedades de Indicadores** ou o painel **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="5ed9a-113">Because an indicator is positioned inside the gauge panel, you need to select the indicator instead of the panel when you want to configure the indicator by using the **Indicators Properties** dialog box or the **Properties** pane.</span></span> <span data-ttu-id="5ed9a-114">A imagem a seguir mostra um indicador selecionado em seu painel de medidores.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-114">The following picture shows a selected indicator in its gauge panel.</span></span>  
  
 <span data-ttu-id="5ed9a-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span><span class="sxs-lookup"><span data-stu-id="5ed9a-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ed9a-116">Dependendo da largura da coluna e do comprimento de valores de dados, pode haver quebra de texto em células da tabela ou matriz e o texto pode ser exibido em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-116">Depending on column width and the length of data values, the text in table or matrix cells might wrap and display text on multiple lines.</span></span> <span data-ttu-id="5ed9a-117">Quando isso ocorre, o ícone de indicador pode ser alongado e mudar de forma.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-117">When this occurs, the indicator icon might be stretched and change shape.</span></span> <span data-ttu-id="5ed9a-118">Isso pode tornar o ícone de indicador menos legível.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-118">This can make the indicator icon less readable.</span></span> <span data-ttu-id="5ed9a-119">Coloque o indicador dentro de um retângulo para garantir que o ícone nunca seja alongado.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-119">Place the indicator inside a rectangle to ensure that the icon is never stretched.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="5ed9a-120">Para adicionar um indicador a uma tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="5ed9a-120">To add an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="5ed9a-121">Abra um relatório existente ou crie um novo relatório que contenha uma tabela e matriz com os dados a serem exibidos.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-121">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="5ed9a-122">Para obter mais informações, consulte [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5ed9a-122">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="5ed9a-123">Insira uma coluna em sua tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-123">Insert a column in your table or matrix.</span></span> <span data-ttu-id="5ed9a-124">Para obter mais informações, consulte [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5ed9a-124">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="5ed9a-125">Opcionalmente, na guia **Inserir** , clique em **Retângulo**e em uma célula na nova coluna.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-125">Optionally, on the **Insert** tab, click **Rectangle**, and then click a cell in the new column.</span></span>  
  
4.  <span data-ttu-id="5ed9a-126">Na guia **Inserir** , clique em **Indicador**e em uma célula na nova coluna.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-126">On the **Insert** tab, click **Indicator**, and then click a cell in the new column.</span></span>  
  
     <span data-ttu-id="5ed9a-127">Se você adicionou um retângulo em uma célula, clique nessa célula.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-127">If you added a rectangle to a cell, click that cell.</span></span>  
  
5.  <span data-ttu-id="5ed9a-128">Na caixa de diálogo **Selecionar Estilo de Indicador** , no painel esquerdo, clique no tipo de indicador desejado e no conjunto de indicadores.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-128">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
6.  <span data-ttu-id="5ed9a-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="5ed9a-130">Clique no indicador.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-130">Click the indicator.</span></span> <span data-ttu-id="5ed9a-131">O painel **Dados do Medidor** é exibido.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-131">The **Gauge Data** pane opens.</span></span>  
  
8.  <span data-ttu-id="5ed9a-132">Na área **Valores** , na lista suspensa **(Não Especificado)** , clique no campo cujos valores você deseja exibir como indicador.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-132">In the **Values** area, in the **(Unspecified)** drop-down list, click the field whose values you want to display as an indicator.</span></span>  
  
     <span data-ttu-id="5ed9a-133">O indicador é configurado para usar valores padrão.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-133">The indicator is configured to use default values.</span></span> <span data-ttu-id="5ed9a-134">Por padrão, os indicadores são configurados para usar porcentagens como unidades de medida e os intervalos de porcentagens são distribuídos uniformemente entre os membros do indicador, e o valor que o indicador transmite usa o escopo do grupo mais próximo.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-134">By default, indicators are configured use percentages as measurement units and the percentage ranges are evenly distributed across the members of the indicator and the value that the indicator conveys uses the scope of the nearest group.</span></span>  
  
### <a name="to-delete-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="5ed9a-135">Para excluir um indicador de uma tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="5ed9a-135">To delete an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="5ed9a-136">Clique com o botão direito do mouse no indicador a ser excluído e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-136">Right-click the indicator to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5ed9a-137">Um indicador pode ser posicionado dentro de um painel de medidores que contenha outros indicadores ou medidores.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-137">An indicator might be positioned inside a gauge panel that contains other indicators or gauges.</span></span> <span data-ttu-id="5ed9a-138">Se os painéis de medidores contiverem vários itens, clique no indicador para excluí-lo, não no painel de medidores.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-138">If the gauge panels contain multiple items, be sure to click the indicator to delete it, not the gauge panel.</span></span> <span data-ttu-id="5ed9a-139">Se você clicar e depois excluir o painel de medidores, os painéis de medidores e todos os itens neles serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-139">If you click and then delete the gauge panel, the gauge panels and all the items in it are deleted.</span></span>  
  
2.  <span data-ttu-id="5ed9a-140">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5ed9a-140">Click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed9a-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ed9a-141">See Also</span></span>  
 [<span data-ttu-id="5ed9a-142">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ed9a-142">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
