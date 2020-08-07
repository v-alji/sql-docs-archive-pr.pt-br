---
title: Navegando no cubo implantado | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 849c6109-1453-4fe4-a892-c49a982cfadb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b876c8b2876aaf4ad28b0f4ea3fb8bab32cd787b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575434"
---
# <a name="browsing-the-deployed-cube"></a><span data-ttu-id="d40b3-102">Navegando no cubo implantado</span><span class="sxs-lookup"><span data-stu-id="d40b3-102">Browsing the Deployed Cube</span></span>
  <span data-ttu-id="d40b3-103">Na tarefa a seguir, você navegará no cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d40b3-103">In the following task, you browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="d40b3-104">Como nossa análise compara medidas em várias dimensões, você usará uma Tabela Dinâmica do Excel para procurar seus dados.</span><span class="sxs-lookup"><span data-stu-id="d40b3-104">Because our analysis compares measure across multiple dimensions, you will use an Excel PivotTable to browse your data.</span></span> <span data-ttu-id="d40b3-105">Usar uma Tabela Dinâmica permite colocar informações de cliente, data e produto em eixos diferentes, de forma que você possa ver como as Vendas pela Internet são alteradas quando exibidas por períodos de tempo específicos, demografia de cliente e linhas de produto.</span><span class="sxs-lookup"><span data-stu-id="d40b3-105">Using a PivotTable lets you place customer, date, and product information on different axes so that you can see how Internet Sales change when viewed across specific time periods, customer demographics, and product lines.</span></span>  
  
### <a name="to-browse-the-deployed-cube"></a><span data-ttu-id="d40b3-106">Para navegar no cubo implantado</span><span class="sxs-lookup"><span data-stu-id="d40b3-106">To browse the deployed cube</span></span>  
  
1.  <span data-ttu-id="d40b3-107">Para alternar para o designer de cubo no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , clique duas vezes no cubo do \*\* [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tutorial\*\* na pasta **cubos** do Gerenciador de soluções.</span><span class="sxs-lookup"><span data-stu-id="d40b3-107">To switch to Cube Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], double-click the **[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial** cube in the **Cubes** folder of the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="d40b3-108">Abra a guia **Navegador** e clique no botão **Reconectar** da barra de ferramentas do designer.</span><span class="sxs-lookup"><span data-stu-id="d40b3-108">Open the **Browser** tab, and then click the **Reconnect** button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="d40b3-109">Clique no ícone de Excel para iniciar o Excel usando o banco de dados de workspace como a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d40b3-109">Click the Excel icon to launch Excel using the workspace database as the data source.</span></span> <span data-ttu-id="d40b3-110">Quando for solicitado para habilitar conexões, clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="d40b3-110">When prompted to enable connections, click **Enable**.</span></span>  
  
4.  <span data-ttu-id="d40b3-111">Na Lista de Campos da Tabela Dinâmica, expanda **Internet Sales**e depois arraste a medida **Sales Amount** para a área de **Valores** .</span><span class="sxs-lookup"><span data-stu-id="d40b3-111">In the PivotTable Field List, expand **Internet Sales**, and then drag the **Sales Amount** measure to the **Values** area.</span></span>  
  
5.  <span data-ttu-id="d40b3-112">Na Lista de Campos da Tabela Dinâmica, expanda **Product**.</span><span class="sxs-lookup"><span data-stu-id="d40b3-112">In the PivotTable Field List, expand **Product**.</span></span>  
  
6.  <span data-ttu-id="d40b3-113">Arraste a hierarquia de usuário **Product Model Lines** para a área **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="d40b3-113">Drag the **Product Model Lines** user hierarchy to the **Columns** area.</span></span>  
  
7.  <span data-ttu-id="d40b3-114">Na Lista de Campos da Tabela Dinâmica, expanda **Customer**e **Local**. Depois, arraste a hierarquia **Customer Geography** da pasta de exibição Local na dimensão Customer para a área **Linhas** .</span><span class="sxs-lookup"><span data-stu-id="d40b3-114">In the PivotTable Field List, expand **Customer**, expand **Location**, and then drag the **Customer Geography** hierarchy from the Location display folder in the Customer dimension to the **Rows** area.</span></span>  
  
8.  <span data-ttu-id="d40b3-115">Na Lista de Campos da Tabela Dinâmica, expanda **Order Date**e depois arraste a hierarquia **Order Date.Calendar Date** para a área **Filtro de Relatório** .</span><span class="sxs-lookup"><span data-stu-id="d40b3-115">In the PivotTable Field List, expand **Order Date**, and then drag the **Order Date.Calendar Date** hierarchy to the **Report Filter** area.</span></span>  
  
9. <span data-ttu-id="d40b3-116">Clique na seta à direita do filtro **Order Date.Calendar Date** no painel de dados, desmarque a caixa de seleção do nível **(Todos)** , expanda **2006**, **H1 CY 2006**, **Q1 CY 2006**, marque a caixa de seleção como **Fevereiro de 2006**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d40b3-116">Click the arrow to the right of the **Order Date.Calendar Date** filter in the data pane, clear the check box for the **(All)** level, expand **2006**, expand **H1 CY 2006**, expand **Q1 CY 2006**, select the check box for **February 2006**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d40b3-117">As vendas pela Internet por região e a linha de produto referentes ao mês de fevereiro de 2006 são exibidas, como mostra a imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="d40b3-117">Internet sales by region and product line for the month of February, 2006 appear as shown in the following image.</span></span>  
  
     <span data-ttu-id="d40b3-118">![Vendas pela Internet por região e linha de produtos](../../2014/tutorials/media/l3-cube-browser-finish.gif "Vendas pela Internet por região e linha de produtos")</span><span class="sxs-lookup"><span data-stu-id="d40b3-118">![Internet sales by region and product line](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet sales by region and product line")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d40b3-119">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="d40b3-119">Next Lesson</span></span>  
 [<span data-ttu-id="d40b3-120">Lição 4: Como definir propriedades avançadas de dimensão e de atributo</span><span class="sxs-lookup"><span data-stu-id="d40b3-120">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>](lesson-4-defining-advanced-attribute-and-dimension-properties.md)  
  
  
