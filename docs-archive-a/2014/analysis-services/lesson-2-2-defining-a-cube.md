---
title: Definindo um cubo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8aa4ac2d-857f-4048-baa0-0f314e207cf6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 354a05840dd2e091f956454858edd5c75c8c4bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568834"
---
# <a name="defining-a-cube"></a><span data-ttu-id="0c19d-102">Definindo um cubo</span><span class="sxs-lookup"><span data-stu-id="0c19d-102">Defining a Cube</span></span>
  <span data-ttu-id="0c19d-103">O Assistente para Cubos ajuda-o a definir os grupos de medidas e dimensões de um cubo.</span><span class="sxs-lookup"><span data-stu-id="0c19d-103">The Cube Wizard helps you define the measure groups and dimensions for a cube.</span></span> <span data-ttu-id="0c19d-104">Na tarefa a seguir, você usará o Assistente para Cubos para criar um cubo.</span><span class="sxs-lookup"><span data-stu-id="0c19d-104">In the following task, you will use the Cube Wizard to build a cube.</span></span>  
  
### <a name="to-define-a-cube-and-its-properties"></a><span data-ttu-id="0c19d-105">Para definir um cubo e suas propriedades</span><span class="sxs-lookup"><span data-stu-id="0c19d-105">To define a cube and its properties</span></span>  
  
1.  <span data-ttu-id="0c19d-106">Em Gerenciador de Soluções, clique com o botão direito do mouse em **cubos**e clique em **novo cubo**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-106">In Solution Explorer, right-click **Cubes**, and then click **New Cube**.</span></span> <span data-ttu-id="0c19d-107">O Assistente para Cubos é exibido.</span><span class="sxs-lookup"><span data-stu-id="0c19d-107">The Cube Wizard appears.</span></span>  
  
2.  <span data-ttu-id="0c19d-108">Na página **Bem-vindo ao Assistente para Cubos** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-108">On the **Welcome to the Cube Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="0c19d-109">Na página **Selecionar Método de Criação** , verifique se a opção **Usar tabelas existentes** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-109">On the **Select Creation Method** page, verify that the **Use existing tables** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="0c19d-110">Na página **Selecionar Tabelas de Grupos de Medidas** , verifique se a exibição da fonte de dados **Adventure Works DW 2012** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="0c19d-110">On the **Select Measure Group Tables** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="0c19d-111">Clique em **Sugerir** para que o assistente para cubos sugira as tabelas a serem usadas na criação do grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="0c19d-111">Click **Suggest** to have the cube wizard suggest tables to use to create measure groups.</span></span>  
  
     <span data-ttu-id="0c19d-112">O assistente examina as tabelas e sugere **InternetSales** como uma tabela do grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="0c19d-112">The wizard examines the tables and suggests **InternetSales** as a measure group table.</span></span> <span data-ttu-id="0c19d-113">As tabelas do grupo de medidas, também denominadas tabelas de fatos, contêm medidas que lhe interessam; por exemplo, o número de unidades vendidas.</span><span class="sxs-lookup"><span data-stu-id="0c19d-113">Measure group tables, also called fact tables, contain the measures you are interested in, such as the number of units sold.</span></span>  
  
6.  <span data-ttu-id="0c19d-114">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="0c19d-115">Na página **Selecionar Medidas** , examine as medidas selecionadas no grupo de medidas **Vendas pela Internet** e desmarque as caixas de seleção das seguintes medidas:</span><span class="sxs-lookup"><span data-stu-id="0c19d-115">On the **Select Measures** page, review the selected measures in the **Internet Sales** measure group, and then clear the check boxes for the following measures:</span></span>  
  
    -   <span data-ttu-id="0c19d-116">**Chave da Promoção**</span><span class="sxs-lookup"><span data-stu-id="0c19d-116">**Promotion Key**</span></span>  
  
    -   <span data-ttu-id="0c19d-117">**Chave da Moeda**</span><span class="sxs-lookup"><span data-stu-id="0c19d-117">**Currency Key**</span></span>  
  
    -   <span data-ttu-id="0c19d-118">**Chave da Região de Vendas**</span><span class="sxs-lookup"><span data-stu-id="0c19d-118">**Sales Territory Key**</span></span>  
  
    -   <span data-ttu-id="0c19d-119">**Número de Revisão**</span><span class="sxs-lookup"><span data-stu-id="0c19d-119">**Revision Number**</span></span>  
  
     <span data-ttu-id="0c19d-120">Por padrão, o assistente seleciona como medidas todas as colunas numéricas da tabela de fatos que não estão vinculadas a dimensões.</span><span class="sxs-lookup"><span data-stu-id="0c19d-120">By default, the wizard selects as measures all numeric columns in the fact table that are not linked to dimensions.</span></span> <span data-ttu-id="0c19d-121">Porém, essas quatro colunas não são medidas reais.</span><span class="sxs-lookup"><span data-stu-id="0c19d-121">However, these four columns are not actual measures.</span></span> <span data-ttu-id="0c19d-122">As três primeiras são valores de chave que vinculam a tabela de fatos às tabelas de dimensão que não são usadas na versão inicial deste cubo.</span><span class="sxs-lookup"><span data-stu-id="0c19d-122">The first three are key values that link the fact table with dimension tables that are not used in the initial version of this cube.</span></span>  
  
8.  <span data-ttu-id="0c19d-123">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-123">Click **Next**.</span></span>  
  
9. <span data-ttu-id="0c19d-124">Na página **Selecionar Dimensões Existentes** , verifique se a dimensão **Data** criada anteriormente está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-124">On the **Select Existing Dimensions** page, make sure the **Date** dimension that you created earlier is selected, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="0c19d-125">Na página **Selecionar Novas Dimensões** , selecione as novas dimensões que serão criadas.</span><span class="sxs-lookup"><span data-stu-id="0c19d-125">On the **Select New Dimensions** page, select the new dimensions to be created.</span></span> <span data-ttu-id="0c19d-126">Para fazer isso, verifique se as caixas de seleção **Cliente**, **Geografia**e **Produto** estão marcadas e desmarque a caixa de seleção **InternetSales** .</span><span class="sxs-lookup"><span data-stu-id="0c19d-126">To do this, verify that the **Customer**, **Geography**, and **Product** check boxes are selected, and then clear the **InternetSales** check box.</span></span>  
  
11. <span data-ttu-id="0c19d-127">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-127">Click **Next**.</span></span>  
  
12. <span data-ttu-id="0c19d-128">Na página **concluindo o assistente** , altere o nome do cubo para `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="0c19d-128">On the **Completing the Wizard** page, change the name of the cube to `Analysis Services Tutorial`.</span></span> <span data-ttu-id="0c19d-129">No painel Visualização, você pode ver o grupo de medidas **InternetSales** e suas medidas.</span><span class="sxs-lookup"><span data-stu-id="0c19d-129">In the Preview pane, you can see the **InternetSales** measure group and its measures.</span></span> <span data-ttu-id="0c19d-130">É possível ver também as dimensões **Data**, **Cliente** e **Produto** .</span><span class="sxs-lookup"><span data-stu-id="0c19d-130">You can also see the **Date**, **Customer,** and **Product** dimensions.</span></span>  
  
13. <span data-ttu-id="0c19d-131">Clique em **Concluir** para finalizar o assistente.</span><span class="sxs-lookup"><span data-stu-id="0c19d-131">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="0c19d-132">No Gerenciador de Soluções, no projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , o cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] é exibido na pasta **Cubos** e as dimensões de banco de dados Cliente e Produto são exibidas na pasta **Dimensões** .</span><span class="sxs-lookup"><span data-stu-id="0c19d-132">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube appears in the **Cubes** folder, and the Customer and Product database dimensions appear in the **Dimensions** folder.</span></span> <span data-ttu-id="0c19d-133">Além disso, no centro do ambiente de desenvolvimento, a guia Estrutura do Cubo exibe o cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c19d-133">Additionally, in the center of the development environment, the Cube Structure tab displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
14. <span data-ttu-id="0c19d-134">Na barra de ferramentas da guia Estrutura do Cubo, altere o nível **Zoom** para 50%, de forma que fique mais fácil ver as dimensões e tabelas de fatos no cubo.</span><span class="sxs-lookup"><span data-stu-id="0c19d-134">On the toolbar of the Cube Structure tab, change the **Zoom** level to 50 percent, so that you can more easily see the dimensions and fact tables in the cube.</span></span> <span data-ttu-id="0c19d-135">Observe que a tabela de fato é amarela e as tabelas de dimensão são azuis.</span><span class="sxs-lookup"><span data-stu-id="0c19d-135">Notice that the fact table is yellow and the dimension tables are blue.</span></span>  
  
15. <span data-ttu-id="0c19d-136">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="0c19d-136">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0c19d-137">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="0c19d-137">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0c19d-138">Adicionando atributos em dimensões</span><span class="sxs-lookup"><span data-stu-id="0c19d-138">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a><span data-ttu-id="0c19d-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c19d-139">See Also</span></span>  
 <span data-ttu-id="0c19d-140">[Cubos em modelos multidimensionais](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="0c19d-140">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="0c19d-141">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="0c19d-141">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
