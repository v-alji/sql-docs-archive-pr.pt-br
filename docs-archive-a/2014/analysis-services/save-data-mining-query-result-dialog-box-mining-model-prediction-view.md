---
title: Caixa de diálogo Salvar resultado da consulta de mineração de dados (exibição de previsão do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dm.savedataminingqueryresult.f1
helpviewer_keywords:
- Save Data Mining Query Result dialog box
ms.assetid: 112fb527-7466-4fd4-9cf1-75596135648f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0838c90f0797a0db9c8a66cd8c5f877aaecdad0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570927"
---
# <a name="save-data-mining-query-result-dialog-box-mining-model-prediction-view"></a><span data-ttu-id="de5be-102">Caixa de diálogo Salvar Resultado da Consulta de Mineração de Dados (Exibição de Previsão do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="de5be-102">Save Data Mining Query Result Dialog Box (Mining Model Prediction View)</span></span>
  <span data-ttu-id="de5be-103">Use a caixa de diálogo **Salvar Resultado da Consulta da Mineração de Dados** para salvar os resultados de uma consulta de mineração de dados em uma nova tabela.</span><span class="sxs-lookup"><span data-stu-id="de5be-103">Use the **Save Data Mining Query Result** dialog box to save the results of a data mining query to a new table.</span></span>  
  
 <span data-ttu-id="de5be-104">A nova tabela será criada no banco de dados definido pela fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="de5be-104">The new table will be created in the database defined by the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="de5be-105">Opções</span><span class="sxs-lookup"><span data-stu-id="de5be-105">Options</span></span>  
 <span data-ttu-id="de5be-106">**Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="de5be-106">**Data Source**</span></span>  
 <span data-ttu-id="de5be-107">Selecione uma fonte de dados do projeto atual.</span><span class="sxs-lookup"><span data-stu-id="de5be-107">Select a data source from the current project.</span></span> <span data-ttu-id="de5be-108">Se a fonte de dados correta não existir, clique em **Novo** para criar uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="de5be-108">If the correct data source does not exist, click **New** to create a new data source.</span></span>  
  
 <span data-ttu-id="de5be-109">**Novo**</span><span class="sxs-lookup"><span data-stu-id="de5be-109">**New**</span></span>  
 <span data-ttu-id="de5be-110">Abre o **Assistente de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="de5be-110">Opens the **Data Source Wizard**.</span></span>  
  
 <span data-ttu-id="de5be-111">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="de5be-111">**Table Name**</span></span>  
 <span data-ttu-id="de5be-112">Digite um nome para a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="de5be-112">Type a name for the new table.</span></span>  
  
 <span data-ttu-id="de5be-113">**Substitua se existir**</span><span class="sxs-lookup"><span data-stu-id="de5be-113">**Overwrite if exists**</span></span>  
 <span data-ttu-id="de5be-114">Selecione esta opção se você quiser substituir uma tabela existente com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="de5be-114">Select this option if you want to overwrite an existing table with the same name.</span></span>  
  
 <span data-ttu-id="de5be-115">Substituir a tabela existente será necessário se qualquer um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="de5be-115">Overwriting the existing table is required if any of the following is true:</span></span>  
  
-   <span data-ttu-id="de5be-116">Você adicionou colunas à consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="de5be-116">You added columns to the prediction query.</span></span>  
  
-   <span data-ttu-id="de5be-117">Você alterou os nomes ou tipos de dados de todas as colunas na consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="de5be-117">You changed the names or data types of any columns in the prediction query.</span></span>  
  
-   <span data-ttu-id="de5be-118">Você executou uma instrução ALTER na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="de5be-118">You ran an ALTER statement on the destination table.</span></span>  
  
 <span data-ttu-id="de5be-119">Se várias colunas tiverem o mesmo nome (por exemplo, várias colunas derivadas podem ter o nome da coluna padrão **Expression**), você deverá criar um alias para cada coluna com um nome duplicado.</span><span class="sxs-lookup"><span data-stu-id="de5be-119">If multiple columns have the same name (for example, several derived columns might have the default column name **Expression**), you must create an alias for each column with a duplicate name.</span></span> <span data-ttu-id="de5be-120">Se as colunas não tiverem nomes exclusivos, um erro será gerado quando o designer tentar salvar os resultados no SQL Server, porque as colunas em uma tabela devem ter nomes exclusivos.</span><span class="sxs-lookup"><span data-stu-id="de5be-120">If the columns do not have unique names, an error will be raised when the designer tries to save the results to SQL Server, because columns in a table must have unique names.</span></span>  
  
 <span data-ttu-id="de5be-121">**Adicione à DSV**</span><span class="sxs-lookup"><span data-stu-id="de5be-121">**Add to DSV**</span></span>  
 <span data-ttu-id="de5be-122">(Opcional) Selecione uma exibição de fonte de dados contida no projeto se quiser adicionar a tabela a uma fonte de dados existente.</span><span class="sxs-lookup"><span data-stu-id="de5be-122">(Optional) Select a data source view contained in the project if you want to add the table to an existing data source.</span></span>  
  
 <span data-ttu-id="de5be-123">Essa opção será útil se você quiser manter todas as tabelas relacionadas para um modelo, como dados de treinamento, dados de origem de previsão e resultados da consulta, na mesma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="de5be-123">This option is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5be-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de5be-124">See Also</span></span>  
 <span data-ttu-id="de5be-125">[Construtor de Consultas de &#40;de mineração de dados de previsão&#41;](prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="de5be-125">[Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md) </span></span>  
 <span data-ttu-id="de5be-126">[Interfaces de consulta de mineração de dados](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="de5be-126">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="de5be-127">Referência de instruções de DMX &#40extensões de Mineração de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="de5be-127">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
