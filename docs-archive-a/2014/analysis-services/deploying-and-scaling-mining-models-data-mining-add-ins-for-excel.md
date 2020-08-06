---
title: Implantando e dimensionando modelos de mineração (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- manage
ms.assetid: 4c617375-6b01-4a71-9680-de0cbf2cff05
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd2839144d4d1667da09830aaabd1ec3f17a9c21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576053"
---
# <a name="deploying-and-scaling-mining-models-data-mining-add-ins-for-excel"></a><span data-ttu-id="6635a-102">Implantando e dimensionando modelos de mineração (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="6635a-102">Deploying and Scaling Mining Models (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="6635a-103">As ferramentas no grupo de **Gerenciamento** e **uso do modelo** são fornecidas para ajudá-lo a gerenciar e navegar nos modelos de mineração existentes.</span><span class="sxs-lookup"><span data-stu-id="6635a-103">The tools in the **Model Usage** and **Management** group are provided to help you manage and browse existing mining models.</span></span> <span data-ttu-id="6635a-104">Você pode usar essas ferramentas para exibir quaisquer modelos que sejam armazenados em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], e não apenas aqueles criados usando os suplementos.</span><span class="sxs-lookup"><span data-stu-id="6635a-104">You can use these tools to view any models that are stored on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], not just those created using the add-ins.</span></span>  
  
 <span data-ttu-id="6635a-105">Se você tiver as permissões necessárias, poderá excluir, modificar, renomear ou processar as estruturas e os modelos de mineração existentes, sem sair do Excel.</span><span class="sxs-lookup"><span data-stu-id="6635a-105">If you have the necessary permissions, you can delete, modify, rename, or process existing mining models and structures without leaving Excel.</span></span>  
  
## <a name="model-usage-toolbar"></a><span data-ttu-id="6635a-106">Barra de ferramentas Uso do Modelo</span><span class="sxs-lookup"><span data-stu-id="6635a-106">Model Usage Toolbar</span></span>  
  
### <a name="browse"></a><span data-ttu-id="6635a-107">Procurar</span><span class="sxs-lookup"><span data-stu-id="6635a-107">Browse</span></span>  
 <span data-ttu-id="6635a-108">Use o assistente de **navegação** para selecionar um modelo de Data Mining existente e, em seguida, exiba e explore o modelo em um visualizador que contenha vários grafos e ferramentas.</span><span class="sxs-lookup"><span data-stu-id="6635a-108">Use the **Browse** wizard to select an existing data mining model, and then view and explore the model in a viewer that contains multiple graphs and tools.</span></span>  
  
 <span data-ttu-id="6635a-109">Para obter mais informações, consulte [procurando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6635a-109">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="document-model"></a><span data-ttu-id="6635a-110">Modelo de Documento</span><span class="sxs-lookup"><span data-stu-id="6635a-110">Document Model</span></span>  
 <span data-ttu-id="6635a-111">Clique em **modelo de documento** para iniciar um assistente que cria um relatório das estruturas de mineração e dos modelos de mineração que você criou.</span><span class="sxs-lookup"><span data-stu-id="6635a-111">Click **Document Model** to start a wizard that creates a report of the mining structures and mining models that you have created.</span></span> <span data-ttu-id="6635a-112">Você pode criar relatórios básicos ou avançadas.</span><span class="sxs-lookup"><span data-stu-id="6635a-112">You can create basic or advanced reports.</span></span> <span data-ttu-id="6635a-113">Os relatórios incluem metadados de coluna e modelo; então, eles são úteis para documentar seu trabalho e rastrear as alterações em modelos.</span><span class="sxs-lookup"><span data-stu-id="6635a-113">The reports include column and model metadata, so are useful for documenting your work and tracking changes in models.</span></span>  
  
 <span data-ttu-id="6635a-114">Para obter mais informações, consulte [documentando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6635a-114">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
### <a name="query"></a><span data-ttu-id="6635a-115">Consulta</span><span class="sxs-lookup"><span data-stu-id="6635a-115">Query</span></span>  
 <span data-ttu-id="6635a-116">Clique em **consulta** para iniciar o assistente de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="6635a-116">Click **Query** to start the **Query** wizard.</span></span> <span data-ttu-id="6635a-117">O assistente o orienta interativamente no processo de criar uma consulta de previsão em um modelo de mineração de dados existente.</span><span class="sxs-lookup"><span data-stu-id="6635a-117">The wizard interactively walks you through the process of creating a prediction query against an existing data mining model.</span></span>  
  
 <span data-ttu-id="6635a-118">Para personalizar ainda mais a consulta ou criar consultas não incluídas no assistente, basta clicar no botão **avançado** para iniciar a **consulta de mineração de dados editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="6635a-118">To further customize the query, or build queries not included in the wizard, just click the **Advanced** button to start the **Data Mining Query Advanced Editor**.</span></span>  
  
 <span data-ttu-id="6635a-119">Para obter mais informações, consulte [consultas &#40;SQL Server suplementos de mineração de dados&#41;](query-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6635a-119">For more information, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="data-mining-advanced-query-editor"></a><span data-ttu-id="6635a-120">Editor de Consulta Avançada de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="6635a-120">Data Mining Advanced Query Editor</span></span>  
 <span data-ttu-id="6635a-121">Neste editor, você pode usar modelos DMX para iniciar uma consulta. Também pode modificar as entradas, as saídas, os algoritmos e os parâmetros para criar um modelo de mineração personalizado, uma estrutura de mineração ou uma consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="6635a-121">In this editor, you can use Data Mining Extensions (DMX) templates to jumpstart a query, and then modify the inputs, outputs, algorithms, and parameters to create a custom mining model, mining structure, or prediction query.</span></span>  
  
 <span data-ttu-id="6635a-122">Para obter mais informações, consulte [Editor de consulta de mineração de dados avançado](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6635a-122">For more information, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="management"></a><span data-ttu-id="6635a-123">Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="6635a-123">Management</span></span>  
 <span data-ttu-id="6635a-124">Use o assistente para **gerenciar modelos** para exibir os modelos existentes na conexão atual.</span><span class="sxs-lookup"><span data-stu-id="6635a-124">Use the **Manage Models** wizard to view existing models on the current connection.</span></span> <span data-ttu-id="6635a-125">Você também pode excluir, renomear, processar, ou importar e exportar modelos e estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="6635a-125">You can also delete, rename, process, or import and export mining models and structures.</span></span>  
  
 <span data-ttu-id="6635a-126">Para obter mais informações, consulte [Manage models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6635a-126">For more information, see [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6635a-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6635a-127">See Also</span></span>  
 <span data-ttu-id="6635a-128">[Criando um modelo de mineração de dados](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="6635a-128">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="6635a-129">Validando modelos e usando modelos para previsão &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6635a-129">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
