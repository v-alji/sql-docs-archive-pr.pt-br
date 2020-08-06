---
title: Adicionar, editar e atualizar campos no painel de dados do relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2e36f0fe-8100-4513-b169-14d611646f81
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a20880b84383fc5d9f96c5611419a08facb9ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569140"
---
# <a name="add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs"></a><span data-ttu-id="f7ea7-102">Adicionar, editar e atualizar campos no painel de dados do relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f7ea7-102">Add, Edit, Refresh Fields in the Report Data Pane (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f7ea7-103">Campos do conjunto de dados são a coleção interna de nomes de campos que representam os dados retornados quando uma consulta de conjunto de dados é executado em uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-103">Dataset fields are the built-in collection of field names that represent the data that is returned when a dataset query runs on an external data source.</span></span>  
  
 <span data-ttu-id="f7ea7-104">Para um conjunto de dados interno, os campos do conjunto de dados são os campos criados após a conclusão da criação de uma consulta e o fechamento do painel Designer de Consulta, e campos calculados criados por você.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-104">For an embedded dataset, the dataset fields are the fields that are created after you finish building a query and close the Query Designer pane, and calculated fields that you create.</span></span>  
  
 <span data-ttu-id="f7ea7-105">Para um conjunto de dados compartilhado, os campos do conjunto de dados são os campos da definição do conjunto de dados compartilhado depois que você o adicionou ao relatório.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-105">For a shared dataset, the dataset fields are the fields from the shared dataset definition when you added it to your report.</span></span> <span data-ttu-id="f7ea7-106">Embora a consulta do conjunto de dados compartilhado no servidor de relatório sempre seja usada quando você executa o relatório, a lista de campos do conjunto de dados no relatório é estática.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-106">Although the query from the shared dataset on the report server is always used when you run the report, the list of dataset fields in the report is static.</span></span>  
  
 <span data-ttu-id="f7ea7-107">Use **Atualizar Campos** para atualizar a lista de campos no relatório para corresponder à lista atual de campos da consulta do conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-107">Use **Refresh Fields** to update the list of fields in the report to match the current list of fields from the shared dataset query.</span></span> <span data-ttu-id="f7ea7-108">A atualização da lista de campos não afeta os campos calculados definidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-108">Refreshing the field list does not affect the calculated fields that you define in your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-query-field"></a><span data-ttu-id="f7ea7-109">Para adicionar um campo de consulta</span><span class="sxs-lookup"><span data-stu-id="f7ea7-109">To add a query field</span></span>  
  
1.  <span data-ttu-id="f7ea7-110">No painel de dados do relatório, clique com o botão direito do mouse no conjunto de dados e clique em **Adicionar Campo de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-110">In the Report Data pane, right-click the dataset, and then click **Add Query Field**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7ea7-111">Se não conseguir ver o painel de dados do relatório, no menu **Exibir** , clique em **Dados do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-111">If you cannot see the Report Data pane, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="f7ea7-112">Na página **Campos** da caixa de diálogo **Propriedades do Conjunto de Dados** , clique em **Adicionar**e em **Campo de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-112">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Query Field**.</span></span> <span data-ttu-id="f7ea7-113">Uma linha nova é adicionada ao final da grade.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-113">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="f7ea7-114">Na caixa de texto **Nome do Campo** , digite o nome para o campo.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-114">In the **Field Name** text box, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7ea7-115">Os nomes devem ser exclusivos no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-115">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="f7ea7-116">Na caixa de texto **Origem do Campo** , digite o nome de um campo existente na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-116">In the **Field Source** text box, type the name of an existing field on the data source.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-calculated-field"></a><span data-ttu-id="f7ea7-117">Para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="f7ea7-117">To add a calculated field</span></span>  
  
1.  <span data-ttu-id="f7ea7-118">No painel de dados do relatório, clique com o botão direito do mouse no conjunto de dados e clique em **Adicionar Campo Calculado**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-118">In the Report Data pane, right-click the dataset, and then click **Add Calculated Field**.</span></span>  
  
2.  <span data-ttu-id="f7ea7-119">Na página **Campos** da caixa de diálogo **Propriedades do Conjunto de Dados** , clique em **Adicionar**e em **Campo Calculado**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-119">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Calculated Field**.</span></span> <span data-ttu-id="f7ea7-120">Uma linha nova é adicionada ao final da grade.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-120">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="f7ea7-121">Na caixa de texto **Nome do Campo** , digite o nome para o campo.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-121">In the **Field Name** text bo, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7ea7-122">Os nomes devem ser exclusivos no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-122">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="f7ea7-123">Na caixa de texto **Origem do Campo** , digite a expressão para o campo.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-123">In the **Field Source** text box, type the expression for the field.</span></span> <span data-ttu-id="f7ea7-124">Clique no botão de expressão (**fx**) para criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-124">Click the expression (**fx**) button to build an expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7ea7-125">A expressão de um campo calculado não pode conter agregações ou referências a itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-125">The expression for a calculated field cannot contain aggregates or references to report items.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-query-field-or-a-dataset-field"></a><span data-ttu-id="f7ea7-126">Para editar um campo de consulta ou de conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="f7ea7-126">To edit a query field or a dataset field</span></span>  
  
1.  <span data-ttu-id="f7ea7-127">No painel de dados do relatório, clique com o botão direito do mouse no campo e clique em **Propriedades do Campo**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-127">In the Report Data pane, right-click the field, and then click **Field Properties**.</span></span>  
  
2.  <span data-ttu-id="f7ea7-128">Na página **Campos** da caixa de diálogo **Propriedades do Conjunto de Dados** , clique em um campo existente para selecionar a linha.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-128">In the **Fields** page of the **Dataset Properties** dialog box, click an existing field to select the row.</span></span>  
  
3.  <span data-ttu-id="f7ea7-129">Altere o nome ou o valor do campo.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-129">Change the name of the field or the value of the field.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-query-field-or-a-calculated-field"></a><span data-ttu-id="f7ea7-130">Para excluir um campo de consulta ou um campo calculado</span><span class="sxs-lookup"><span data-stu-id="f7ea7-130">To delete a query field or a calculated field</span></span>  
  
1.  <span data-ttu-id="f7ea7-131">No painel de dados do relatório, expanda o conjunto de dados para exibir a coleção de campos.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-131">In the Report Data pane, expand the dataset to display the field collection.</span></span>  
  
2.  <span data-ttu-id="f7ea7-132">Clique com o botão direito do mouse no campo que você deseja remover e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-132">Right-click the field you want to remove, and then click **Delete**.</span></span>  
  
### <a name="to-refresh-the-field-collection-in-the-report-data-pane-for-a-shared-dataset"></a><span data-ttu-id="f7ea7-133">Para atualizar a coleção de campos no Painel Dados do Relatório para um conjunto de dados compartilhado</span><span class="sxs-lookup"><span data-stu-id="f7ea7-133">To refresh the field collection in the Report Data Pane for a shared dataset</span></span>  
  
1.  <span data-ttu-id="f7ea7-134">No painel Dados do Relatório, clique com o botão direito do mouse no conjunto de dados e clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-134">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
2.  <span data-ttu-id="f7ea7-135">Clique em **Atualizar Campos**.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-135">Click **Refresh Fields**.</span></span>  
  
     <span data-ttu-id="f7ea7-136">No servidor de relatório, a consulta do banco de dados compartilhado é executada e retorna a coleção de campos atual.</span><span class="sxs-lookup"><span data-stu-id="f7ea7-136">On the report server, the shared dataset query runs and returns the current field collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ea7-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7ea7-137">See Also</span></span>  
 <span data-ttu-id="f7ea7-138">[Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f7ea7-138">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f7ea7-139">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f7ea7-139">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="f7ea7-140">[Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f7ea7-140">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f7ea7-141">[Designers de Consultas do Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="f7ea7-141">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 [<span data-ttu-id="f7ea7-142">Designers de Consultas &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="f7ea7-142">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
