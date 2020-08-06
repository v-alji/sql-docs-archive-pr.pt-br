---
title: Consulta de Mineração de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 657e4e173815fa25458e296f7eadb3d4d0696a02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574858"
---
# <a name="data-mining-query"></a><span data-ttu-id="fd4f2-102">Consulta de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="fd4f2-102">Data Mining Query</span></span>
  <span data-ttu-id="fd4f2-103">O painel de design contém o construtor de consultas de previsão de mineração de dados, que pode ser usado para construir consultas de previsão de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-103">The design pane contains the data mining prediction query builder, which you can use to build data mining prediction queries.</span></span> <span data-ttu-id="fd4f2-104">Você pode criar tanto consultas de previsão baseadas em tabelas de entrada como consultas de previsão singleton.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-104">You can design either prediction queries based on input tables, or singleton prediction queries.</span></span> <span data-ttu-id="fd4f2-105">Alterne para a exibição de resultados para executar a consulta e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-105">Switch to the result view to run the query and view the results.</span></span> <span data-ttu-id="fd4f2-106">A exibição de consulta exibe a consulta DMX (Data Mining Extensions) criada pelo construtor de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-106">The query view displays the Data Mining Extensions (DMX) query created by the prediction query builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd4f2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="fd4f2-107">Options</span></span>  
 <span data-ttu-id="fd4f2-108">Botão para alternar a exibição</span><span class="sxs-lookup"><span data-stu-id="fd4f2-108">Switch view button</span></span>  
 <span data-ttu-id="fd4f2-109">Clique em um ícone para alternar entre o painel de design e o painel de consulta.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-109">Click an icon to switch between the design and query pane.</span></span> <span data-ttu-id="fd4f2-110">Por padrão, é aberto o painel de design.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-110">By default, the design pane is open.</span></span>  
  
 <span data-ttu-id="fd4f2-111">Para mudar para o painel de design, clique no ícone ![ícone Design](../media/ssis-designicon.gif "Ícone de design").</span><span class="sxs-lookup"><span data-stu-id="fd4f2-111">To switch to the design pane, click the ![Design icon](../media/ssis-designicon.gif "Design icon") icon.</span></span>  
  
 <span data-ttu-id="fd4f2-112">Para mudar para o painel de consulta, clique no ícone ![ícone SQL](../media/ssis-queryicon.gif "Ícone do SQL").</span><span class="sxs-lookup"><span data-stu-id="fd4f2-112">To switch to the query pane, click the ![SQL icon](../media/ssis-queryicon.gif "SQL icon") icon.</span></span>  
  
 <span data-ttu-id="fd4f2-113">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-113">**Mining Model**</span></span>  
 <span data-ttu-id="fd4f2-114">Exibe o modelo de mineração selecionado no qual você deseja basear as previsões.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-114">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="fd4f2-115">**Selecionar Modelo**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-115">**Select Model**</span></span>  
 <span data-ttu-id="fd4f2-116">Abre a caixa de diálogo **Selecionar Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="fd4f2-116">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="fd4f2-117">**Colunas de Entrada**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-117">**Input Columns**</span></span>  
 <span data-ttu-id="fd4f2-118">Exibe as colunas de entrada selecionadas usadas para gerar as previsões.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-118">Displays the selected input columns used to generate the predictions.</span></span>  
  
 <span data-ttu-id="fd4f2-119">**Origem**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-119">**Source**</span></span>  
 <span data-ttu-id="fd4f2-120">Selecione a origem que contém o campo a ser usado para a coluna da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-120">Select the source containing the field that you will use for the column from the dropdown list.</span></span> <span data-ttu-id="fd4f2-121">Você pode usar o modelo de mineração selecionado na tabela **Modelo de Mineração** , a tabela de entrada selecionada na tabela **Selecionar Tabela(s) de Entrada** , uma função de previsão ou uma expressão personalizada.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-121">You can either use the mining model selected in the **Mining Model** table, the input table(s) selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="fd4f2-122">As colunas podem ser arrastadas das tabelas que contêm o modelo de mineração e colunas de entrada para a célula.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-122">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
 <span data-ttu-id="fd4f2-123">**Campo**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-123">**Field**</span></span>  
 <span data-ttu-id="fd4f2-124">Selecione uma coluna na lista de colunas derivada da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-124">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="fd4f2-125">Se você selecionou **Função de Previsão** em **Origem**, esta célula conterá uma lista suspensa das funções de previsão disponíveis para o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-125">If you selected **Prediction Function** in **Source**, this cell contains a drop-down list of the prediction functions available for the selected mining model.</span></span>  
  
 <span data-ttu-id="fd4f2-126">**Alias**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-126">**Alias**</span></span>  
 <span data-ttu-id="fd4f2-127">Nome da coluna retornado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-127">The name of the column returned by the server.</span></span>  
  
 <span data-ttu-id="fd4f2-128">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-128">**Show**</span></span>  
 <span data-ttu-id="fd4f2-129">Selecione para retornar a coluna ou para usar só a coluna na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-129">Select to return the column or to only use the column in the WHERE clause.</span></span>  
  
 <span data-ttu-id="fd4f2-130">**Agrupar**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-130">**Group**</span></span>  
 <span data-ttu-id="fd4f2-131">Use com a coluna **E/ou** para agrupar expressões.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-131">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="fd4f2-132">Por exemplo, (expr1 OU expr2) E expr3.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-132">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="fd4f2-133">**E/Ou**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-133">**And/Or**</span></span>  
 <span data-ttu-id="fd4f2-134">Use para criar uma consulta lógica.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-134">Use to create a logical query.</span></span> <span data-ttu-id="fd4f2-135">Por exemplo, (expr1 OU expr2) E expr3.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-135">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="fd4f2-136">**Critérios/Argumento**</span><span class="sxs-lookup"><span data-stu-id="fd4f2-136">**Criteria/Argument**</span></span>  
 <span data-ttu-id="fd4f2-137">Especifique uma condição ou expressão de usuário que se aplica à coluna.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-137">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="fd4f2-138">As colunas podem ser arrastadas das tabelas que contêm o modelo de mineração e colunas de entrada para a célula.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-138">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4f2-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd4f2-139">See Also</span></span>  
 <span data-ttu-id="fd4f2-140">[Interfaces de consulta de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span><span class="sxs-lookup"><span data-stu-id="fd4f2-140">[Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span></span>  
 [<span data-ttu-id="fd4f2-141">Referência de instruções de DMX &#40extensões de Mineração de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="fd4f2-141">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
