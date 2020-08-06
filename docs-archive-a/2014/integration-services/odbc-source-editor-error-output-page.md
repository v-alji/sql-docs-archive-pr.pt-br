---
title: Editor de origem ODBC (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.errorhandling.f1
ms.assetid: b2f6866c-db07-4cb3-9f38-889f8d2b03e6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a8e169875a26efbe0a7f1ac3d06856b393266eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681791"
---
# <a name="odbc-source-editor-error-output-page"></a><span data-ttu-id="dcbd4-102">Editor de Origem ODBC (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="dcbd4-102">ODBC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="dcbd4-103">Use a página **Saída de Erro** da caixa de diálogo **Editor de Origem ODBC** para selecionar as opções para tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-103">Use the **Error Output** page of the **ODBC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="dcbd4-104">Para obter mais informações sobre a origem ODBC, consulte [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="dcbd4-104">To learn more about the ODBC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="dcbd4-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="dcbd4-105">Task List</span></span>  
 <span data-ttu-id="dcbd4-106">**Para abrir a página Saída de Erro do Editor de Origem ODBC**</span><span class="sxs-lookup"><span data-stu-id="dcbd4-106">**To open the ODBC Source Editor Error Output Page**</span></span>  
  
-   <span data-ttu-id="dcbd4-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem a fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="dcbd4-108">Na guia **Fluxo de Dados** , clique duas vezes na fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
-   <span data-ttu-id="dcbd4-109">No **Editor de Origem ODBC**, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-109">In the **ODBC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dcbd4-110">Opções</span><span class="sxs-lookup"><span data-stu-id="dcbd4-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="dcbd4-111">Entrada/Saída</span><span class="sxs-lookup"><span data-stu-id="dcbd4-111">Input/Output</span></span>  
 <span data-ttu-id="dcbd4-112">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="dcbd4-113">Coluna</span><span class="sxs-lookup"><span data-stu-id="dcbd4-113">Column</span></span>  
 <span data-ttu-id="dcbd4-114">Não usado.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="dcbd4-115">Erro</span><span class="sxs-lookup"><span data-stu-id="dcbd4-115">Error</span></span>  
 <span data-ttu-id="dcbd4-116">Selecione como a origem ODBC deve tratar erros em um fluxo: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-116">Select how the ODBC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="dcbd4-117">Truncation</span><span class="sxs-lookup"><span data-stu-id="dcbd4-117">Truncation</span></span>  
 <span data-ttu-id="dcbd4-118">Selecione como a origem ODBC deve tratar o truncamento em um fluxo: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-118">Select how the ODBC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="dcbd4-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="dcbd4-119">Description</span></span>  
 <span data-ttu-id="dcbd4-120">Não usado.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-120">Not used.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="dcbd4-121">Definir este valor para células selecionadas</span><span class="sxs-lookup"><span data-stu-id="dcbd4-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="dcbd4-122">Selecione como a origem ODBC trata todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-122">Select how the ODBC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="dcbd4-123">Aplicar</span><span class="sxs-lookup"><span data-stu-id="dcbd4-123">Apply</span></span>  
 <span data-ttu-id="dcbd4-124">Aplique as opções de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="dcbd4-125">Opções de tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="dcbd4-125">Error Handling Options</span></span>  
 <span data-ttu-id="dcbd4-126">Você usa as opções a seguir para configurar como a origem ODBC trata erros e truncamentos.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-126">You use the following options to configure how the ODBC source handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="dcbd4-127">Falha no Componente</span><span class="sxs-lookup"><span data-stu-id="dcbd4-127">Fail Component</span></span>  
 <span data-ttu-id="dcbd4-128">A tarefa Fluxo de Dados falha quando ocorre um erro ou um truncamento.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="dcbd4-129">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="dcbd4-130">Ignorar Falha</span><span class="sxs-lookup"><span data-stu-id="dcbd4-130">Ignore Failure</span></span>  
 <span data-ttu-id="dcbd4-131">O erro ou o truncamento é ignorado.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="dcbd4-132">Redirecionar fluxo</span><span class="sxs-lookup"><span data-stu-id="dcbd4-132">Redirect Flow</span></span>  
 <span data-ttu-id="dcbd4-133">A linha que está causando o erro ou o truncamento é direcionada para a saída do erro da origem ODBC.</span><span class="sxs-lookup"><span data-stu-id="dcbd4-133">The row that is causing the error or the truncation is directed to the error output of the ODBC source.</span></span> <span data-ttu-id="dcbd4-134">Para obter mais informações, consulte [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="dcbd4-134">For more information, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbd4-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dcbd4-135">See Also</span></span>  
 <span data-ttu-id="dcbd4-136">[Editor de origem ODBC &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="dcbd4-136">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="dcbd4-137">Editor de Origem ODBC &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="dcbd4-137">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-columns-page.md)  
  
  
