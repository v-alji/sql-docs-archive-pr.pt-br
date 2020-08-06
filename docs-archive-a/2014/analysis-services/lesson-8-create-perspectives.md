---
title: 'Lição 9: criar perspectivas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 417b6a4d3b16857f48bcc2f39dc8ec4c010a2b10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684423"
---
# <a name="lesson-9-create-perspectives"></a><span data-ttu-id="50878-102">Lição 9: Criar perspectivas</span><span class="sxs-lookup"><span data-stu-id="50878-102">Lesson 9: Create Perspectives</span></span>
  <span data-ttu-id="50878-103">Nesta lição, você criará uma perspectiva de Vendas pela Internet.</span><span class="sxs-lookup"><span data-stu-id="50878-103">In this lesson, you will create an Internet Sales perspective.</span></span> <span data-ttu-id="50878-104">Uma perspectiva define um subconjunto exibível de um modelo que fornece pontos de vista concentrados, específicos da empresa ou específicos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="50878-104">A perspective defines a viewable subset of a model that provides focused, business-specific, or application-specific viewpoints.</span></span> <span data-ttu-id="50878-105">Quando um usuário se conecta a um modelo usando uma perspectiva, ele vê apenas os objetos de modelo (tabelas, colunas, medidas e KPIs) como campos definidos nessa perspectiva.</span><span class="sxs-lookup"><span data-stu-id="50878-105">When a user connects to a model using a perspective, they see only those model objects (tables, columns, measures, hierarchies, and KPIs) as fields defined in that perspective.</span></span>  
  
 <span data-ttu-id="50878-106">A perspectiva Vendas pela Internet que você criou nesta lição excluirá o objeto de tabela Cliente.</span><span class="sxs-lookup"><span data-stu-id="50878-106">The Internet Sales perspective you create in this lesson will exclude the Customer table object.</span></span> <span data-ttu-id="50878-107">Quando você cria uma perspectiva que exclui determinados objetos da exibição, esse objeto ainda existe no modelo; porém, não está visível em uma lista de campo de cliente de relatório.</span><span class="sxs-lookup"><span data-stu-id="50878-107">When you create a perspective that excludes certain objects from view, that object still exists in the model; however, it is not visible in a reporting client field list.</span></span> <span data-ttu-id="50878-108">Colunas calculadas e medidas incluídas ou não em uma perspectiva ainda podem ser calculadas de dados de objeto que são excluídos.</span><span class="sxs-lookup"><span data-stu-id="50878-108">Calculated columns and measures either included in a perspective or not can still calculate from object data that is excluded.</span></span>  
  
 <span data-ttu-id="50878-109">A finalidade desta lição é descrever como criar perspectivas e se familiarizar com as ferramentas de criação de modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="50878-109">The purpose of this lesson is to describe how to create perspectives and become familiar with the tabular model authoring tools.</span></span> <span data-ttu-id="50878-110">Se você expandir este modelo posteriormente para incluir tabelas adicionais, poderá criar perspectivas adicionais para definir diferentes pontos de vista do modelo; por exemplo, Inventário e Força de Vendas.</span><span class="sxs-lookup"><span data-stu-id="50878-110">If you later expand this model to include additional tables, you can create additional perspectives to define different viewpoints of the model, for example, Inventory and Sales Force.</span></span>  
  
 <span data-ttu-id="50878-111">Para saber mais, consulte [Perspectivas &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="50878-111">To learn more, see [Perspectives &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="50878-112">Tempo estimado para concluir esta lição: **5 minutos**</span><span class="sxs-lookup"><span data-stu-id="50878-112">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50878-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="50878-113">Prerequisites</span></span>  
 <span data-ttu-id="50878-114">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="50878-114">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="50878-115">Antes de executar as tarefas desta lição, você deve ter concluído a lição anterior: [Lição 8: Criar Indicadores Chave de Desempenho](lesson-7-create-key-performance-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="50878-115">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 8: Create Key Performance Indicators](lesson-7-create-key-performance-indicators.md).</span></span>  
  
## <a name="create-perspectives"></a><span data-ttu-id="50878-116">Criar perspectivas</span><span class="sxs-lookup"><span data-stu-id="50878-116">Create Perspectives</span></span>  
  
#### <a name="to-create-an-internet-sales-perspective"></a><span data-ttu-id="50878-117">Para criar uma perspectiva Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="50878-117">To create an Internet Sales perspective</span></span>  
  
1.  <span data-ttu-id="50878-118">No designer de modelos, clique no menu **modelo** e em **perspectivas**.</span><span class="sxs-lookup"><span data-stu-id="50878-118">In the model designer, click the **Model** menu, and then click **Perspectives**.</span></span>  
  
2.  <span data-ttu-id="50878-119">Na caixa de diálogo **Perspectivas** , clique em **Nova Perspectiva**.</span><span class="sxs-lookup"><span data-stu-id="50878-119">In the **Perspectives** dialog box, click **New Perspective**.</span></span>  
  
3.  <span data-ttu-id="50878-120">Para renomear a perspectiva, clique duas vezes no título da coluna **nova perspectiva 1** e digite `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="50878-120">To rename the perspective, double-click the **New Perspective 1** column heading, and then type `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="50878-121">Em **campos**, selecione a seguinte **Data**de tabelas, **geografia**, **produto**, **categoria de produto**, **subcategoria de produto**e `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="50878-121">In **Fields**, select the following tables **Date**, **Geography**, **Product**, **Product Category**, **Product Subcategory**, and `Internet Sales`.</span></span>  
  
     <span data-ttu-id="50878-122">Observe que você excluiu a tabela Cliente e todas as suas colunas desta perspectiva.</span><span class="sxs-lookup"><span data-stu-id="50878-122">Notice you excluded the Customer table and all of its columns from this perspective.</span></span> <span data-ttu-id="50878-123">Posteriormente, na Lição 12, você usará o recurso Analisar no Excel para testar esta perspectiva.</span><span class="sxs-lookup"><span data-stu-id="50878-123">Later, in Lesson 12, you will use the Analyze in Excel feature to test this perspective.</span></span> <span data-ttu-id="50878-124">A Lista de Campos da Tabela Dinâmica do Excel incluirá cada tabela exceto a tabela Cliente.</span><span class="sxs-lookup"><span data-stu-id="50878-124">The Excel PivotTable Field List will include each table except the Customer table.</span></span>  
  
5.  <span data-ttu-id="50878-125">Verifique as seleções, garantindo que a tabela **Customer** não está marcada e clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="50878-125">Verify your selections, making sure the **Customer** table is not checked, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="50878-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="50878-126">Next Steps</span></span>  
 <span data-ttu-id="50878-127">Para continuar este tutorial, vá para a próxima lição: [Lição 10: Criar hierarquias](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="50878-127">To continue this tutorial, go to the next lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
  
