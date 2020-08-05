---
title: Painel de consulta (exibição de previsão do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.query.f1
ms.assetid: fdeec72e-d0bd-4453-9eaa-46436e4d6edc
author: minewiskan
ms.author: owend
ms.openlocfilehash: e17a27190891ea9e00be21d5013d0767d61ac148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572250"
---
# <a name="query-pane-mining-model-prediction-view"></a><span data-ttu-id="8c6d7-102">Painel Consulta (Exibição da Previsão do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="8c6d7-102">Query Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="8c6d7-103">O painel **Consulta** exibe as instruções DMX (extensões DMX) criadas pelo Construtor de Consultas de Previsão.</span><span class="sxs-lookup"><span data-stu-id="8c6d7-103">The **Query** pane displays the Data Mining Expressions (DMX) statements created by Prediction Query Builder.</span></span> <span data-ttu-id="8c6d7-104">Você pode modificar as instruções e, depois, clicar no botão **Alternar para a exibição de resultado da consulta** para retornar os resultados.</span><span class="sxs-lookup"><span data-stu-id="8c6d7-104">You can modify the statements and then click the **Switch to query result view** button to return the results.</span></span> <span data-ttu-id="8c6d7-105">Se você retornar à exibição de **Design** , quaisquer alterações efetuadas na instrução serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="8c6d7-105">If you switch back to the **Design** view, any changes you made to the statement will be lost.</span></span>  
  
 <span data-ttu-id="8c6d7-106">**Para obter mais informações:** [Instruções de manipulação de dados DMX &#40;extensões DMX&#41;](/sql/dmx/dmx-statements-data-manipulation), [Criar uma consulta DMX no SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="8c6d7-106">**For More Information:** [Data Mining Extensions &#40;DMX&#41; Data Manipulation Statements](/sql/dmx/dmx-statements-data-manipulation), [Create a DMX Query in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="8c6d7-107">Opções</span><span class="sxs-lookup"><span data-stu-id="8c6d7-107">Options</span></span>  
 <span data-ttu-id="8c6d7-108">**Alternar para a exibição de resultado da consulta**</span><span class="sxs-lookup"><span data-stu-id="8c6d7-108">**Switch to query result view**</span></span>  
 <span data-ttu-id="8c6d7-109">Clique para mudar entre os painéis **Design**, **Consulta**e **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="8c6d7-109">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="8c6d7-110">A consulta é executada ao alternar para o painel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="8c6d7-110">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="8c6d7-111">**Salvar o resultado da consulta**</span><span class="sxs-lookup"><span data-stu-id="8c6d7-111">**Save the query result**</span></span>  
 <span data-ttu-id="8c6d7-112">Abre a caixa de diálogo **Salvar Resultado da Consulta de Mineração de Dados** .</span><span class="sxs-lookup"><span data-stu-id="8c6d7-112">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="8c6d7-113">**Consulta singleton**</span><span class="sxs-lookup"><span data-stu-id="8c6d7-113">**Singleton query**</span></span>  
 <span data-ttu-id="8c6d7-114">Permite que você crie uma consulta singleton, na qual você fornecerá os dados de entrada diretamente na consulta em vez de fornecer uma referência para a tabela de valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="8c6d7-114">Lets you create a singleton query, in which you provide the input data directly in your query instead of providing a reference to a table of input values.</span></span> <span data-ttu-id="8c6d7-115">A tabela **Selecionar Tabela(s) de Entrada** será substituída por uma tabela **Entrada de Consultas Singleton** .</span><span class="sxs-lookup"><span data-stu-id="8c6d7-115">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span> <span data-ttu-id="8c6d7-116">A consulta de previsão atual será perdida se você alternar para uma consulta singleton.</span><span class="sxs-lookup"><span data-stu-id="8c6d7-116">The current prediction query will be lost if you switch to a singleton query.</span></span>  
  
 <span data-ttu-id="8c6d7-117">**Atualizar resultados de consulta**</span><span class="sxs-lookup"><span data-stu-id="8c6d7-117">**Refresh query results**</span></span>  
 <span data-ttu-id="8c6d7-118">Processa novamente a consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="8c6d7-118">Reprocesses the prediction query.</span></span> <span data-ttu-id="8c6d7-119">Isso está habilitado apenas no painel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="8c6d7-119">This is enabled only in the **Result** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6d7-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c6d7-120">See Also</span></span>  
 <span data-ttu-id="8c6d7-121">[Interfaces de consulta de mineração de dados](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8c6d7-121">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 <span data-ttu-id="8c6d7-122">[Referência de instrução&#41; &#40;DMX de extensões de mineração de dados](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="8c6d7-122">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 [<span data-ttu-id="8c6d7-123">Construtor de Consultas de previsão &#40;Mineração de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="8c6d7-123">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
