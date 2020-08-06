---
title: Caixa de diálogo Propriedades do conjunto de, campos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570539"
---
# <a name="dataset-properties-dialog-box-fields"></a><span data-ttu-id="873b9-102">Caixa de diálogo Propriedades do Conjunto de Dados, Campos</span><span class="sxs-lookup"><span data-stu-id="873b9-102">Dataset Properties Dialog Box, Fields</span></span>
  <span data-ttu-id="873b9-103">Selecione **Campos** na caixa de diálogo **Propriedades do Conjunto de Dados** para alterar a coleção de campos para o conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="873b9-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="873b9-104">A lista de campos é preenchida automaticamente, mas você pode usar os **Campos** para adicionar, editar e excluir campos calculados e consultas.</span><span class="sxs-lookup"><span data-stu-id="873b9-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
## <a name="options"></a><span data-ttu-id="873b9-105">Opções</span><span class="sxs-lookup"><span data-stu-id="873b9-105">Options</span></span>  
 <span data-ttu-id="873b9-106">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="873b9-106">**Add**</span></span>  
 <span data-ttu-id="873b9-107">Adicione um novo campo de consulta ou campo calculado ao conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="873b9-107">Add a new query field or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="873b9-108">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="873b9-108">**Delete**</span></span>  
 <span data-ttu-id="873b9-109">Exclua o campo selecionado do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="873b9-109">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="873b9-110">**Nome do campo**</span><span class="sxs-lookup"><span data-stu-id="873b9-110">**Field Name**</span></span>  
 <span data-ttu-id="873b9-111">Digite um nome para o campo.</span><span class="sxs-lookup"><span data-stu-id="873b9-111">Type a name for the field.</span></span> <span data-ttu-id="873b9-112">O campo deve ser exclusivo no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="873b9-112">The field must be unique within the dataset.</span></span> <span data-ttu-id="873b9-113">Para cada campo existente na consulta de conjunto de dados, o nome é populado previamente.</span><span class="sxs-lookup"><span data-stu-id="873b9-113">For each existing field in the dataset query, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="873b9-114">**Origem de Campo**</span><span class="sxs-lookup"><span data-stu-id="873b9-114">**Field Source**</span></span>  
 <span data-ttu-id="873b9-115">Insira um valor para o campo.</span><span class="sxs-lookup"><span data-stu-id="873b9-115">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="873b9-116">Para um campo calculado, a origem do campo deve ter o nome de um campo existente recuperado pela consulta do conjunto de dados ou uma expressão criada por você.</span><span class="sxs-lookup"><span data-stu-id="873b9-116">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="873b9-117">Por exemplo, para criar um campo que represente 10 vezes o valor no campo de consulta Sales, use a expressão `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="873b9-117">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="873b9-118">Para um campo de consulta, a origem do campo deve ter o nome de um campo existente recuperado pela consulta de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="873b9-118">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="873b9-119">**Expressão (fx)**</span><span class="sxs-lookup"><span data-stu-id="873b9-119">**Expression (fx)**</span></span>  
 <span data-ttu-id="873b9-120">Adicione ou altere uma expressão para o campo calculado.</span><span class="sxs-lookup"><span data-stu-id="873b9-120">Add or change an expression for the calculated field.</span></span> <span data-ttu-id="873b9-121">Esse botão só é exibido quando você clica em **Adicionar** e seleciona **Campo Calculado**.</span><span class="sxs-lookup"><span data-stu-id="873b9-121">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873b9-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="873b9-122">See Also</span></span>  
 <span data-ttu-id="873b9-123">[Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="873b9-123">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="873b9-124">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="873b9-124">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="873b9-125">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="873b9-125">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
