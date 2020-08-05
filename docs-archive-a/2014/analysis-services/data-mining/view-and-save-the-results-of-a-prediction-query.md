---
title: Exibir e salvar os resultados de uma consulta de previsão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- viewing prediction query results
- displaying prediction query results
- Mining Model Prediction [Analysis Services], viewing results
ms.assetid: abba4d24-3619-44c1-8279-88f27ad627d3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6da4b515c4280969f665dba2cf5bee5281df0a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572824"
---
# <a name="view-and-save-the-results-of-a-prediction-query"></a><span data-ttu-id="af357-102">Exibir e salvar os resultados de uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="af357-102">View and Save the Results of a Prediction Query</span></span>
  <span data-ttu-id="af357-103">Depois de definir uma consulta no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando Construtor de consultas de previsão, você pode executar a consulta e exibir os resultados alternando para a exibição de resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="af357-103">After you have defined a query in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using Prediction Query Builder, you can run the query and view the results by switching to the query result view.</span></span>  
  
 <span data-ttu-id="af357-104">Você pode salvar os resultados de uma consulta de previsão em uma tabela em qualquer fonte de dados definida em um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="af357-104">You can save the results of a prediction query to a table in any data source that is defined in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="af357-105">Você pode criar uma tabela nova ou pode salvar os resultados da consulta em uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="af357-105">You can either create a new table or save the query results to an existing table.</span></span> <span data-ttu-id="af357-106">Se você salvar os resultados em uma tabela existente, poderá decidir sobrescrever os dados que estão armazenados atualmente na tabela; caso contrário, os resultados de consulta serão anexados aos dados existentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="af357-106">If you save the results to an existing table, you can choose to overwrite the data that is currently stored in the table; otherwise, the query results are appended to the existing data in the table.</span></span>  
  
### <a name="run-a-query-and-view-the-results"></a><span data-ttu-id="af357-107">Executar uma consulta e exibir os resultados</span><span class="sxs-lookup"><span data-stu-id="af357-107">Run a query and view the results</span></span>  
  
1.  <span data-ttu-id="af357-108">Na barra de ferramentas da guia **Previsão de Modelo de Mineração** do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique em **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="af357-108">On the toolbar of the **Mining Model Prediction** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Result** .</span></span>  
  
     <span data-ttu-id="af357-109">A exibição dos resultados da consulta é aberta e a consulta é executada.</span><span class="sxs-lookup"><span data-stu-id="af357-109">The query results view opens and runs the query.</span></span> <span data-ttu-id="af357-110">Os resultados são exibidos em uma grade no visualizador.</span><span class="sxs-lookup"><span data-stu-id="af357-110">The results are displayed in a grid in the viewer.</span></span>  
  
### <a name="save-the-results-of-a-prediction-query-to-a-table"></a><span data-ttu-id="af357-111">Salvar os resultados de uma consulta de previsão em uma tabela</span><span class="sxs-lookup"><span data-stu-id="af357-111">Save the results of a prediction query to a table</span></span>  
  
1.  <span data-ttu-id="af357-112">Na barra de ferramentas da guia **Previsão de Modelo de Mineração** do Designer de Mineração de Dados, clique em **Salvar resultado de consulta**.</span><span class="sxs-lookup"><span data-stu-id="af357-112">On the toolbar of the **Mining Model Prediction** tab in Data Mining Designer, click **Save query result**.</span></span>  
  
     <span data-ttu-id="af357-113">A caixa de diálogo **Salvar Resultado da Consulta de Mineração de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="af357-113">The **Save Data Mining Query Result** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="af357-114">Selecione uma fonte de dados da lista **Fonte de Dados** ou clique em **Novo** para criar uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="af357-114">Select a data source from the **Data Source** list, or click **New** to create a new data source.</span></span>  
  
3.  <span data-ttu-id="af357-115">Na caixa **Nome da tabela** , digite o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="af357-115">In the **Table Name** box, enter the name of the table.</span></span> <span data-ttu-id="af357-116">Se a tabela já existir, selecione **Substituir se existir** para substituir o conteúdo da tabela com os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="af357-116">If the table already exists, select **Overwrite if exists** to replace the contents of the table with the query results.</span></span> <span data-ttu-id="af357-117">Se você não desejar substituir o conteúdo da tabela, não selecione esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="af357-117">If you do not want to overwrite the contents of the table, do not select this check box.</span></span> <span data-ttu-id="af357-118">Os novos resultados da consulta serão anexados aos dados existentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="af357-118">The new query results will be appended to the existing data in the table.</span></span>  
  
4.  <span data-ttu-id="af357-119">Selecione uma exibição da fonte de dados de **Adicionar a DSV** caso queira adicionar a tabela à exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="af357-119">Select a data source view from **Add to DSV** if you want to add the table to a data source view.</span></span>  
  
5.  <span data-ttu-id="af357-120">Clique em **Save** (Salvar).</span><span class="sxs-lookup"><span data-stu-id="af357-120">Click **Save**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="af357-121">Se o destino não der suporte a conjuntos de linhas hierárquicos, você poderá acrescentar a palavra-chave FALTTENED aos resultados para salvar como uma tabela plana.</span><span class="sxs-lookup"><span data-stu-id="af357-121">If the destination does not support hierarchical rowsets, you can add the FALTTENED keyword to the results to save as a flat table.</span></span>  
  
  
