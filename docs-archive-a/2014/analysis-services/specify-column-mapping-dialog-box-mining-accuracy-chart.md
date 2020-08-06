---
title: Caixa de diálogo especificar mapeamento de coluna (gráfico de precisão de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.coltotablecolmapping.f1
ms.assetid: 68e9e2d2-173f-4363-a515-fc60bfee3af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ede835567f678f4152b3d1944f3c2c7160c6837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581512"
---
# <a name="specify-column-mapping-dialog-box-mining-accuracy-chart"></a><span data-ttu-id="c3670-102">Caixa de diálogo Especificar Mapeamento de Coluna (gráfico de precisão de mineração)</span><span class="sxs-lookup"><span data-stu-id="c3670-102">Specify Column Mapping Dialog Box (Mining Accuracy Chart)</span></span>
  <span data-ttu-id="c3670-103">Use a guia **Especificar Mapeamento de Coluna** para selecionar tabelas de uma fonte de dados externa e mapear as colunas para um modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="c3670-103">Use the **Specify Column Mapping** tab to select tables from an external data source and map the columns to a data mining model.</span></span> <span data-ttu-id="c3670-104">É possível usar os dados externos para testar a precisão de um modelo de mineração e mostrar os resultados no gráfico de precisão.</span><span class="sxs-lookup"><span data-stu-id="c3670-104">You can then use the external data to test the accuracy of a mining model and displays the results in the accuracy chart.</span></span>  
  
 <span data-ttu-id="c3670-105">\*\*Para obter mais informações: \*\* [Teste e validação &#40;Mineração de dados&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="c3670-105">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c3670-106">Opções</span><span class="sxs-lookup"><span data-stu-id="c3670-106">Options</span></span>  
 <span data-ttu-id="c3670-107">**Estrutura de mineração**</span><span class="sxs-lookup"><span data-stu-id="c3670-107">**Mining Structure**</span></span>  
 <span data-ttu-id="c3670-108">Exibe a estrutura de mineração selecionada que contém o modelo que será testado.</span><span class="sxs-lookup"><span data-stu-id="c3670-108">Displays the selected mining structure that contains the model that you will test.</span></span>  
  
 <span data-ttu-id="c3670-109">**Selecionar Estrutura**</span><span class="sxs-lookup"><span data-stu-id="c3670-109">**Select Structure**</span></span>  
 <span data-ttu-id="c3670-110">Clique para abrir a caixa de diálogo **Selecionar Estrutura de Mineração** e selecione uma estrutura de mineração diferente.</span><span class="sxs-lookup"><span data-stu-id="c3670-110">Click to open the **Select Mining Structure** dialog box and select a different mining structure.</span></span>  
  
 <span data-ttu-id="c3670-111">**Selecionar Tabela(s) de Entrada**</span><span class="sxs-lookup"><span data-stu-id="c3670-111">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="c3670-112">Exibe as tabelas de entrada selecionadas que são usadas para gerar o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="c3670-112">Displays the selected input tables that are used to generate the lift chart.</span></span> <span data-ttu-id="c3670-113">Selecione a tabela que contém os dados de teste que você deseja usar para testar a precisão dos modelos.</span><span class="sxs-lookup"><span data-stu-id="c3670-113">Select the table that contains the test data that you will use to test the accuracy of the models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3670-114">Se o painel não contiver nenhuma tabela, clique em **Selecionar Tabela de Casos** para adicionar tabelas de uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c3670-114">If the pane does not contain any tables, click **Select Case Table** to add tables from a data source view.</span></span>  
  
 <span data-ttu-id="c3670-115">**Remover Tabela**</span><span class="sxs-lookup"><span data-stu-id="c3670-115">**Remove Table**</span></span>  
 <span data-ttu-id="c3670-116">Remove a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3670-116">Removes the selected table.</span></span> <span data-ttu-id="c3670-117">Este botão será desabilitado se nenhuma tabela tiver sido selecionada ou se nenhuma tabela for exibida na lista **Selecionar Tabelas de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="c3670-117">This button is disabled if a table has not been selected or if no tables are displayed in the **Select Input Tables** list.</span></span>  
  
 <span data-ttu-id="c3670-118">**Selecionar Tabela de Casos**</span><span class="sxs-lookup"><span data-stu-id="c3670-118">**Select Case Table**</span></span>  
 <span data-ttu-id="c3670-119">Clique para abrir a caixa de diálogo **Selecionar Tabela** e selecione uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c3670-119">Click to open the **Select Table** dialog box and select a data source view.</span></span>  
  
 <span data-ttu-id="c3670-120">**Observação** Esse botão só será exibido se uma tabela de casos não tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3670-120">**Note** This button appears only if a case table has not been selected.</span></span> <span data-ttu-id="c3670-121">Para habilitar o botão de modo que você possa selecionar uma tabela de casos diferente, limpe a lista selecionando todas as tabelas existentes e clicando em **Remover Tabela**.</span><span class="sxs-lookup"><span data-stu-id="c3670-121">To enable the button so that you can select a different case table, clear the list by selecting all existing tables and then clicking **Remove Table**.</span></span>  
  
 <span data-ttu-id="c3670-122">**Selecionar Tabela Aninhada**</span><span class="sxs-lookup"><span data-stu-id="c3670-122">**Select Nested Table**</span></span>  
 <span data-ttu-id="c3670-123">Abre a caixa de diálogo **Selecionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="c3670-123">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="c3670-124">Esse botão só será exibido se uma tabela do casos tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3670-124">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="c3670-125">Se a estrutura de mineração associada não contiver uma tabela aninhada, esse botão será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c3670-125">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="c3670-126">**Modificar Junção**</span><span class="sxs-lookup"><span data-stu-id="c3670-126">**Modify Join**</span></span>  
 <span data-ttu-id="c3670-127">Abre a caixa de diálogo **Especificar Junção Aninhada** .</span><span class="sxs-lookup"><span data-stu-id="c3670-127">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="c3670-128">Esse botão só será ativado se a tabela aninhada for selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3670-128">This button is active only if the nested table is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3670-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3670-129">See Also</span></span>  
 <span data-ttu-id="c3670-130">[Tarefas de teste e validação e instruções &#40;mineração de dados&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c3670-130">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="c3670-131">Designer de gráfico de precisão de mineração &#40;mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="c3670-131">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
