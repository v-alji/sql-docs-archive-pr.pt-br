---
title: Editor de destino ODBC (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.errorhandling.f1
ms.assetid: 0a743f8d-2a51-4296-9976-8104f5ca22d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 475a2e00d67b221ddf05fdd273317fbab5248cd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681797"
---
# <a name="odbc-destination-editor-error-output-page"></a><span data-ttu-id="29f1f-102">Editor de Destinos ADO NET (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="29f1f-102">ODBC Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="29f1f-103">Use a página **Saída de Erro** da caixa de diálogo **Editor de Destino ODBC** para selecionar as opções para tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="29f1f-103">Use the **Error Output** page of the **ODBC Destination Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="29f1f-104">Para obter mais informações sobre o destino ODBC, consulte [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="29f1f-104">To learn more about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="29f1f-105">**Para abrir a página Saída de Erro do Editor de Destino ODBC**</span><span class="sxs-lookup"><span data-stu-id="29f1f-105">**To open the ODBC Destination Editor Error Output Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="29f1f-106">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="29f1f-106">Task List</span></span>  
  
-   <span data-ttu-id="29f1f-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem o destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="29f1f-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="29f1f-108">Na guia **Fluxo de Dados** , clique duas vezes no destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="29f1f-108">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="29f1f-109">No **Editor de Destino ODBC**, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="29f1f-109">In the **ODBC Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29f1f-110">Opções</span><span class="sxs-lookup"><span data-stu-id="29f1f-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="29f1f-111">Entrada/Saída</span><span class="sxs-lookup"><span data-stu-id="29f1f-111">Input/Output</span></span>  
 <span data-ttu-id="29f1f-112">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="29f1f-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="29f1f-113">Coluna</span><span class="sxs-lookup"><span data-stu-id="29f1f-113">Column</span></span>  
 <span data-ttu-id="29f1f-114">Não usado.</span><span class="sxs-lookup"><span data-stu-id="29f1f-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="29f1f-115">Erro</span><span class="sxs-lookup"><span data-stu-id="29f1f-115">Error</span></span>  
 <span data-ttu-id="29f1f-116">Selecione como o destino ODBC deve tratar erros em um fluxo: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="29f1f-116">Select how the ODBC destination should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="29f1f-117">Truncation</span><span class="sxs-lookup"><span data-stu-id="29f1f-117">Truncation</span></span>  
 <span data-ttu-id="29f1f-118">Selecione como o destino ODBC deve tratar truncamento em um fluxo: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="29f1f-118">Select how the ODBC destination should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="29f1f-119">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="29f1f-119">Description</span></span>  
 <span data-ttu-id="29f1f-120">Exiba uma descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="29f1f-120">View a description of the error.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="29f1f-121">Definir este valor para células selecionadas</span><span class="sxs-lookup"><span data-stu-id="29f1f-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="29f1f-122">Selecione como o destino ODBC trata todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="29f1f-122">Select how the ODBC destination handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="29f1f-123">Aplicar</span><span class="sxs-lookup"><span data-stu-id="29f1f-123">Apply</span></span>  
 <span data-ttu-id="29f1f-124">Aplique as opções de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="29f1f-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="29f1f-125">Opções de tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="29f1f-125">Error Handling Options</span></span>  
 <span data-ttu-id="29f1f-126">Você usa as opções a seguir para configurar como o destino ODBC trata erros e truncamentos.</span><span class="sxs-lookup"><span data-stu-id="29f1f-126">You use the following options to configure how the ODBC destination handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="29f1f-127">Falha no Componente</span><span class="sxs-lookup"><span data-stu-id="29f1f-127">Fail Component</span></span>  
 <span data-ttu-id="29f1f-128">A tarefa Fluxo de Dados falha quando ocorre um erro ou um truncamento.</span><span class="sxs-lookup"><span data-stu-id="29f1f-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="29f1f-129">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="29f1f-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="29f1f-130">Ignorar Falha</span><span class="sxs-lookup"><span data-stu-id="29f1f-130">Ignore Failure</span></span>  
 <span data-ttu-id="29f1f-131">O erro ou o truncamento é ignorado.</span><span class="sxs-lookup"><span data-stu-id="29f1f-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="29f1f-132">Redirecionar fluxo</span><span class="sxs-lookup"><span data-stu-id="29f1f-132">Redirect Flow</span></span>  
 <span data-ttu-id="29f1f-133">A linha que está causando o erro ou o truncamento é direcionada para a saída do erro do destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="29f1f-133">The row that is causing the error or the truncation is directed to the error output of the ODBC destination.</span></span> <span data-ttu-id="29f1f-134">Para obter mais informações, consulte Destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="29f1f-134">For more information, see ODBC Destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f1f-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29f1f-135">See Also</span></span>  
 <span data-ttu-id="29f1f-136">[Editor de destinos ODBC &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="29f1f-136">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="29f1f-137">Editor de Destinos ODBC &#40;Página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="29f1f-137">ODBC Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-mappings-page.md)  
  
  
