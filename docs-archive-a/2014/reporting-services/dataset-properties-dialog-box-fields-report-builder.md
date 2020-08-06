---
title: Caixa de diálogo Propriedades do conjunto de, campos (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10021"
ms.assetid: 75c7e54a-3d20-4c9a-88da-ab36dce2ce42
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b766aa23cce390bc3ffdcf10efdb38efc91f3e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570540"
---
# <a name="dataset-properties-dialog-box-fields-report-builder"></a><span data-ttu-id="4a0d2-102">Caixa de diálogo Propriedades do Conjunto de Dados, Campos (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="4a0d2-102">Dataset Properties Dialog Box, Fields (Report Builder)</span></span>
  <span data-ttu-id="4a0d2-103">Selecione **Campos** na caixa de diálogo **Propriedades do Conjunto de Dados** para alterar a coleção de campos para o conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="4a0d2-104">A lista de campos é preenchida automaticamente, mas você pode usar os **Campos** para adicionar, editar e excluir campos calculados e consultas.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
 <span data-ttu-id="4a0d2-105">Somente há suporte para campos calculados em conjuntos de dados inseridos.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-105">Calculated fields are supported only on embedded datasets.</span></span> <span data-ttu-id="4a0d2-106">Para obter mais informações, consulte [Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4a0d2-106">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4a0d2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="4a0d2-107">Options</span></span>  
 <span data-ttu-id="4a0d2-108">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="4a0d2-108">**Add**</span></span>  
 <span data-ttu-id="4a0d2-109">Adicione uma nova consulta ou campo calculado ao conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-109">Add a new query or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="4a0d2-110">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="4a0d2-110">**Delete**</span></span>  
 <span data-ttu-id="4a0d2-111">Exclua o campo selecionado do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-111">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="4a0d2-112">**Nome do campo**</span><span class="sxs-lookup"><span data-stu-id="4a0d2-112">**Field Name**</span></span>  
 <span data-ttu-id="4a0d2-113">Digite um nome para o campo.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-113">Type a name for the field.</span></span> <span data-ttu-id="4a0d2-114">O campo deve ser exclusivo no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-114">The field must be unique within the dataset.</span></span> <span data-ttu-id="4a0d2-115">Para cada campo existente no conjunto de dados, o nome é pré-preenchido.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-115">For each existing field in the dataset, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="4a0d2-116">**Origem de Campo**</span><span class="sxs-lookup"><span data-stu-id="4a0d2-116">**Field Source**</span></span>  
 <span data-ttu-id="4a0d2-117">Insira um valor para o campo.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-117">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="4a0d2-118">Para um campo calculado, a origem do campo deve ter o nome de um campo existente recuperado pela consulta do conjunto de dados ou uma expressão criada por você.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-118">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="4a0d2-119">Por exemplo, para criar um campo que represente 10 vezes o valor no campo de consulta Sales, use a expressão `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-119">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="4a0d2-120">Para um campo de consulta, a origem do campo deve ter o nome de um campo existente recuperado pela consulta de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-120">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="4a0d2-121">**Expressão (fx)**</span><span class="sxs-lookup"><span data-stu-id="4a0d2-121">**Expression (fx)**</span></span>  
 <span data-ttu-id="4a0d2-122">Adicione ou altere uma expressão para o novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-122">Add or change an expression for the new calculated field.</span></span> <span data-ttu-id="4a0d2-123">Esse botão só é exibido quando você clica em **Adicionar** e seleciona **Campo Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4a0d2-123">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0d2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a0d2-124">See Also</span></span>  
 <span data-ttu-id="4a0d2-125">[Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-125">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4a0d2-126">[Criar um conjunto de um DataSet compartilhado ou um conjunto de &#40;inserido Construtor de Relatórios e SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-126">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4a0d2-127">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-127">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="4a0d2-128">[Caixa de diálogo Propriedades do conjunto de, opções &#40;Construtor de Relatórios&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-128">[Dataset Properties Dialog Box, Options &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span></span>  
 <span data-ttu-id="4a0d2-129">[Caixa de diálogo Propriedades do conjunto de, filtros &#40;Construtor de Relatórios&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-129">[Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span></span>  
 <span data-ttu-id="4a0d2-130">[Caixa de diálogo Propriedades do conjunto de, parâmetros &#40;Construtor de Relatórios&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-130">[Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span></span>  
 <span data-ttu-id="4a0d2-131">[Caixa de diálogo Propriedades do conjunto de &#40;, Construtor de Relatórios de consulta&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-131">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="4a0d2-132">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a0d2-132">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4a0d2-133">Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4a0d2-133">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
