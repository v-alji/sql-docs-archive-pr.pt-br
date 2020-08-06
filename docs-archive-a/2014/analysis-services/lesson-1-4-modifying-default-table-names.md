---
title: Modificando nomes de tabela padrão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ddd97483-a76d-43c1-8b40-fc7cc57fb0c2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 254f797be95f60211983400b019415431d4cf39c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568854"
---
# <a name="modifying-default-table-names"></a><span data-ttu-id="04392-102">Modificando nomes de tabela padrão</span><span class="sxs-lookup"><span data-stu-id="04392-102">Modifying Default Table Names</span></span>
  <span data-ttu-id="04392-103">Você pode alterar o valor da propriedade **FriendlyName** para objetos na exibição da fonte de dados para facilitar sua observação e uso.</span><span class="sxs-lookup"><span data-stu-id="04392-103">You can change the value of the **FriendlyName** property for objects in the data source view to make them easier to notice and use.</span></span>  
  
 <span data-ttu-id="04392-104">Na tarefa a seguir, você mudará o nome de cada tabela na exibição da fonte de dados removendo os prefixos "**Dim**" e "**Fact**" dessas tabelas.</span><span class="sxs-lookup"><span data-stu-id="04392-104">In the following task, you will change the friendly name of each table in the data source view by removing the "**Dim**" and "**Fact**" prefixes from these tables.</span></span> <span data-ttu-id="04392-105">Isso facilitará a observação e o uso dos objetos de cubo e dimensão (que você definirá na próxima lição).</span><span class="sxs-lookup"><span data-stu-id="04392-105">This will make the cube and dimension objects (that you will define in the next lesson) easier to notice and use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04392-106">Você também pode modificar os nomes amigáveis das colunas, definir colunas calculadas e unir tabelas ou exibições na exibição da fonte de dados para facilitar o uso.</span><span class="sxs-lookup"><span data-stu-id="04392-106">You can also change the friendly names of columns, define calculated columns, and join tables or views in the data source view to make them easier to use.</span></span>  
  
### <a name="to-modify-the-default-name-of-a-table"></a><span data-ttu-id="04392-107">Para modificar o nome padrão de uma tabela</span><span class="sxs-lookup"><span data-stu-id="04392-107">To modify the default name of a table</span></span>  
  
1.  <span data-ttu-id="04392-108">No painel **Tabelas** do **Designer de Exibição da Fonte de Dados**, clique com o botão direito do mouse na tabela **FactInternetSales** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="04392-108">In the **Tables** pane of **Data Source View Designer**, right-click the **FactInternetSales** table, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="04392-109">Se a janela Propriedades à direita da janela do Microsoft Visual Studio não for exibida, clique no botão **Ocultar Automaticamente** na barra de títulos da janela Propriedades, de modo que essa janela permaneça visível.</span><span class="sxs-lookup"><span data-stu-id="04392-109">If the Properties window on the right side of the Microsoft Visual Studio window is not displayed, click the **Auto Hide** button on the title bar of the Properties window so that this window remains visible.</span></span>  
  
     <span data-ttu-id="04392-110">É mais fácil alterar as propriedades de cada tabela na exibição da fonte de dados quando a janela Propriedades permanece aberta.</span><span class="sxs-lookup"><span data-stu-id="04392-110">It is easier to change the properties for each table in the data source view when the Properties window remains open.</span></span> <span data-ttu-id="04392-111">Caso não configure a janela para permanecer aberta usando o botão **Ocultar Automaticamente** , a janela fechará ao clicar em um objeto diferente no painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="04392-111">If you do not pin the window open by using the **Auto Hide** button, the window will close when you click a different object in the **Diagram** pane.</span></span>  
  
3.  <span data-ttu-id="04392-112">Altere a propriedade **FriendlyName** do objeto **FactInternetSales** para *`InternetSales`* .</span><span class="sxs-lookup"><span data-stu-id="04392-112">Change the **FriendlyName** property for the **FactInternetSales** object to *`InternetSales`*.</span></span>  
  
     <span data-ttu-id="04392-113">Quando você clicar fora da célula da propriedade **FriendlyName** , a alteração será aplicada.</span><span class="sxs-lookup"><span data-stu-id="04392-113">When you click away from the cell for the **FriendlyName** property, the change is applied.</span></span> <span data-ttu-id="04392-114">Na próxima lição, você definirá um grupo de medidas com base nessa tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="04392-114">In the next lesson, you will define a measure group that is based on this fact table.</span></span> <span data-ttu-id="04392-115">O nome da tabela de fatos será InternetSales em vez de FactInternetSales devido à alteração feita nessa lição.</span><span class="sxs-lookup"><span data-stu-id="04392-115">The name of the fact table will be InternetSales instead of FactInternetSales because of the change you made in this lesson.</span></span>  
  
4.  <span data-ttu-id="04392-116">Clique em **DimProduct** no painel **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="04392-116">Click **DimProduct** in the **Tables** pane.</span></span> <span data-ttu-id="04392-117">No janela Propriedades, altere a propriedade **FriendlyName** para *`Product`* .</span><span class="sxs-lookup"><span data-stu-id="04392-117">In the Properties window, change the **FriendlyName** property to *`Product`*.</span></span>  
  
5.  <span data-ttu-id="04392-118">Altere a propriedade **FriendlyName** de cada tabela restante na exibição da fonte de dados da mesma forma para remover o prefixo "**Dim**".</span><span class="sxs-lookup"><span data-stu-id="04392-118">Change the **FriendlyName** property of each remaining table in the data source view in the same way, to remove the "**Dim**" prefix.</span></span>  
  
6.  <span data-ttu-id="04392-119">Quando terminar, clique no botão **Ocultar Automaticamente** para ocultar a janela Propriedades novamente.</span><span class="sxs-lookup"><span data-stu-id="04392-119">When you have finished, click the **Auto Hide** button to hide the Properties window again.</span></span>  
  
7.  <span data-ttu-id="04392-120">No menu **Arquivo** ou na barra de ferramentas do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique em **Salvar Tudo** para salvar as alterações feitas até este momento no projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04392-120">On the **File** menu, or on the toolbar of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Save All** to save the changes you have made to this point in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="04392-121">Se preferir, você pode parar o tutorial aqui e retomá-lo mais tarde.</span><span class="sxs-lookup"><span data-stu-id="04392-121">You can stop the tutorial here if you want and resume it later.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="04392-122">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="04392-122">Next Lesson</span></span>  
 [<span data-ttu-id="04392-123">Lição 2: Definir e implantar um cubo</span><span class="sxs-lookup"><span data-stu-id="04392-123">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="04392-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04392-124">See Also</span></span>  
 <span data-ttu-id="04392-125">[Exibições da fonte de dados em modelos multidimensionais](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="04392-125">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="04392-126">Alterar propriedades em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="04392-126">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
