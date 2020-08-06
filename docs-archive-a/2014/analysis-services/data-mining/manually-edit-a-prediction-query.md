---
title: Editar manualmente uma consulta de previsão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583900"
---
# <a name="manually-edit-a-prediction-query"></a><span data-ttu-id="7f733-102">Editar manualmente uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="7f733-102">Manually Edit a Prediction Query</span></span>
  <span data-ttu-id="7f733-103">Depois de ter criado uma consulta usando o Construtor de Consultas de Previsão, você pode modificar a consulta alternando para a exibição Texto de Consulta na guia **Previsão de Modelo de Mineração** do Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="7f733-103">After you have designed a query by using the Prediction Query Builder, you can modify the query by switching to Query Text view on the **Mining Model Prediction** tab of Data Mining Designer.</span></span> <span data-ttu-id="7f733-104">Um editor de texto aparece na parte inferior da tela para exibir a consulta criada pelo construtor de consultas.</span><span class="sxs-lookup"><span data-stu-id="7f733-104">A text editor appears at the bottom of the screen to display the query that the query builder created.</span></span>  
  
 <span data-ttu-id="7f733-105">Alternar para a exibição de Texto da Consulta é útil para fazer adições à consulta.</span><span class="sxs-lookup"><span data-stu-id="7f733-105">Switching to Query Text view is useful for making additions to the query.</span></span> <span data-ttu-id="7f733-106">Por exemplo, você pode adicionar uma cláusula WHERE ou ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="7f733-106">For example, you can add a WHERE clause or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="7f733-107">Use a grade no Construtor de Consultas de Previsão para inserir os nomes de objetos e colunas, e configurar a sintaxe para funções de previsão individuais e, em seguida, alterne para o modo de edição manual para alterar os valores dos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7f733-107">Use the grid in the Prediction Query Builder to insert the names of objects and columns and set up the syntax for individual prediction functions, and then switch to manual editing mode to change parameter values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f733-108">Se você retornar ao modo de exibição de **Design** por meio da exibição **Texto de Consulta** , quaisquer alterações efetuadas na exibição **Texto de Consulta** serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="7f733-108">If you switch back to **Design** view from **Query Text** view, any changes that you made in **Query Text** view will be lost.</span></span>  
  
### <a name="modify-a-query"></a><span data-ttu-id="7f733-109">Modificar uma consulta</span><span class="sxs-lookup"><span data-stu-id="7f733-109">Modify a query</span></span>  
  
1.  <span data-ttu-id="7f733-110">Na guia **Previsão de Modelo de Mineração** no Designer de Mineração de Dados do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique em **SQL**.</span><span class="sxs-lookup"><span data-stu-id="7f733-110">On the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **SQL**.</span></span>  
  
     <span data-ttu-id="7f733-111">A grade na parte inferior da tela é substituída por um editor de texto que contém a consulta.</span><span class="sxs-lookup"><span data-stu-id="7f733-111">The grid at the bottom of the screen is replaced by a text editor that contains the query.</span></span> <span data-ttu-id="7f733-112">Digite as alterações feitas na consulta neste editor.</span><span class="sxs-lookup"><span data-stu-id="7f733-112">You can type changes to the query in this editor.</span></span>  
  
2.  <span data-ttu-id="7f733-113">Para executar a consulta, no menu **Modelo de Mineração** , selecione **Resultado**ou clique no botão para exibir os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="7f733-113">To run the query, on the **Mining Model** menu, select **Result**, or click the button to switch to query results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f733-114">Se a consulta criada for inválida, a janela Resultados não exibirá um erro e não exibirá nenhum resultado.</span><span class="sxs-lookup"><span data-stu-id="7f733-114">If the query that you have created is invalid, the Results window does not display an error and does not display any results.</span></span> <span data-ttu-id="7f733-115">Clique no botão **Design** ou selecione **Design** ou **Consulta** no menu **Modelo de Mineração** para corrigir o problema e executar a consulta novamente.</span><span class="sxs-lookup"><span data-stu-id="7f733-115">Click the **Design** button, or select **Design** or **Query** from the **Mining Model** menu to correct the problem and run the query again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f733-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f733-116">See Also</span></span>  
 <span data-ttu-id="7f733-117">[Consultas de mineração de dados](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="7f733-117">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="7f733-118">[Construtor de Consultas de &#40;de mineração de dados de previsão&#41;](../prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7f733-118">[Prediction Query Builder &#40;Data Mining&#41;](../prediction-query-builder-data-mining.md) </span></span>  
 [<span data-ttu-id="7f733-119">Lição 6: Criando e trabalhando com previsões &#40;Tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="7f733-119">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  
