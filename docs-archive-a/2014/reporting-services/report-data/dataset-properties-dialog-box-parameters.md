---
title: Caixa de diálogo Propriedades do Conjunto de Dados, Parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10150"
- sql12.rtp.rptdesigner.datasetproperties.parameters.f1
ms.assetid: 43b00aab-e2c3-4e85-abe1-a2b5a21efeed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0073971de373321ce347f416657671e1f497dd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686091"
---
# <a name="dataset-properties-dialog-box-parameters"></a><span data-ttu-id="6e76e-102">Caixa de diálogo Propriedades do Conjunto de Dados, Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6e76e-102">Dataset Properties Dialog Box, Parameters</span></span>
  <span data-ttu-id="6e76e-103">Selecione **Parâmetros** na caixa de diálogo **Propriedades do Conjunto de Dados** para adicionar, alterar e excluir os parâmetros de consulta, incluindo os parâmetros de consulta que estabelecem vínculo com os parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="6e76e-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters, including query parameters that link to report parameters.</span></span>  
  
 <span data-ttu-id="6e76e-104">Sempre que a consulta é alterada na guia de consulta, o comando de consulta é analisado.</span><span class="sxs-lookup"><span data-stu-id="6e76e-104">Whenever the query is changed on the query tab, the query command is parsed.</span></span> <span data-ttu-id="6e76e-105">Para cada parâmetro de consulta identificado, um parâmetro de relatório com um nome com diferenciação de maiúsculas e minúsculas idêntico é criado.</span><span class="sxs-lookup"><span data-stu-id="6e76e-105">For each query parameter that is identified, a report parameter with an identical case-sensitive name is created.</span></span> <span data-ttu-id="6e76e-106">Por padrão, o parâmetro de consulta é adicionado automaticamente à lista de parâmetros de consulta e vinculado ao parâmetro de relatório correspondente.</span><span class="sxs-lookup"><span data-stu-id="6e76e-106">By default, the query parameter is automatically added to the query parameter list and linked to the corresponding report parameter.</span></span>  
  
 <span data-ttu-id="6e76e-107">Se houver dependências dos valores padrão de um parâmetro de relatório ou de outro parâmetro de relatório que estiver vinculado ao parâmetro de consulta, a ordem dos parâmetros de relatório (conforme são exibidos na caixa de diálogo **Propriedades de Parâmetros de Relatório** ) será importante.</span><span class="sxs-lookup"><span data-stu-id="6e76e-107">If there are dependencies for the default values of one report parameter on another report parameter that is linked to a query parameter, the order of report parameters (as they appear in the **Report Parameters Properties** dialog box) is important.</span></span> <span data-ttu-id="6e76e-108">Os últimos parâmetros de relatório da lista podem fazer referência aos primeiros parâmetros de relatório da lista.</span><span class="sxs-lookup"><span data-stu-id="6e76e-108">Report parameters later in the list can refer to report parameters earlier in the list.</span></span> <span data-ttu-id="6e76e-109">Para obter mais informações sobre parâmetros de relatório, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="6e76e-109">For more information about report parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e76e-110">Opções</span><span class="sxs-lookup"><span data-stu-id="6e76e-110">Options</span></span>  
 <span data-ttu-id="6e76e-111">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="6e76e-111">**Add**</span></span>  
 <span data-ttu-id="6e76e-112">Adicione um novo parâmetro à lista.</span><span class="sxs-lookup"><span data-stu-id="6e76e-112">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="6e76e-113">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="6e76e-113">**Delete**</span></span>  
 <span data-ttu-id="6e76e-114">Remova o parâmetro selecionado da lista.</span><span class="sxs-lookup"><span data-stu-id="6e76e-114">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="6e76e-115">**Nome do parâmetro**</span><span class="sxs-lookup"><span data-stu-id="6e76e-115">**Parameter name**</span></span>  
 <span data-ttu-id="6e76e-116">Digite o nome de um parâmetro de consulta que você adicionou ao conjunto de dados na guia **Consulta** da caixa de diálogo **Propriedades do Conjunto de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6e76e-116">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="6e76e-117">**Valor de parâmetro**</span><span class="sxs-lookup"><span data-stu-id="6e76e-117">**Parameter value**</span></span>  
 <span data-ttu-id="6e76e-118">Informe um valor para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="6e76e-118">Enter a value for the query parameter.</span></span> <span data-ttu-id="6e76e-119">Esse valor pode ser estático ou uma expressão que faça referência a um objeto dentro do relatório, mas ele não pode fazer referência a todos os itens ou campos do relatório.</span><span class="sxs-lookup"><span data-stu-id="6e76e-119">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="6e76e-120">Por padrão, **Valor** contém uma expressão que aponta para um parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="6e76e-120">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="6e76e-121">**Seta para cima**</span><span class="sxs-lookup"><span data-stu-id="6e76e-121">**Up arrow**</span></span>  
 <span data-ttu-id="6e76e-122">Mova o parâmetro selecionado para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="6e76e-122">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="6e76e-123">**Seta para baixo**</span><span class="sxs-lookup"><span data-stu-id="6e76e-123">**Down arrow**</span></span>  
 <span data-ttu-id="6e76e-124">Mova o parâmetro selecionado para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="6e76e-124">Move the selected parameter down in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e76e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e76e-125">See Also</span></span>  
 <span data-ttu-id="6e76e-126">[Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="6e76e-126">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="6e76e-127">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6e76e-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="6e76e-128">Alterar a ordem de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6e76e-128">Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
  
