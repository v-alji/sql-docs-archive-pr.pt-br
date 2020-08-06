---
title: Editor de origem CDC (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.errorhandling.f1
ms.assetid: 8a4c2cb8-fd2f-4c45-824f-b93473a8981e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b39532304fddfa90fabe8cafe2a6caf5b1fb5c8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582574"
---
# <a name="cdc-source-editor-error-output-page"></a><span data-ttu-id="a2a8b-102">Editor de Origem CDC (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="a2a8b-102">CDC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="a2a8b-103">Use a página **Saída de Erro** da caixa de diálogo **Editor de Origem CDC** para selecionar as opções para tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-103">Use the **Error Output** page of the **CDC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="a2a8b-104">Para obter mais informações sobre a origem CDC, consulte [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="a2a8b-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a2a8b-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="a2a8b-105">Task List</span></span>  
 <span data-ttu-id="a2a8b-106">**Para abrir a página Saída de Erro do Editor de Origem CDC**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-106">**To open the CDC Source Editor Error Output Page**</span></span>  
  
1.  <span data-ttu-id="a2a8b-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem a origem CDC.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="a2a8b-108">Na guia **Fluxo de Dados** , clique duas vezes na origem CDC.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="a2a8b-109">No **Editor de Origem CDC**, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-109">In the **CDC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2a8b-110">Opções</span><span class="sxs-lookup"><span data-stu-id="a2a8b-110">Options</span></span>  
 <span data-ttu-id="a2a8b-111">**Entrada/Saída**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-111">**Input/Output**</span></span>  
 <span data-ttu-id="a2a8b-112">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-112">View the name of the data source.</span></span>  
  
 <span data-ttu-id="a2a8b-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-113">**Column**</span></span>  
 <span data-ttu-id="a2a8b-114">Exiba as colunas externas (origem) selecionadas na página **Gerenciador de Conexões** da caixa de diálogo **CDC Source Editor (Editor de Origem CDC)** .</span><span class="sxs-lookup"><span data-stu-id="a2a8b-114">View the external (source) columns that you selected on the **Connection Manager** page of the **CDC Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="a2a8b-115">**Erro**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-115">**Error**</span></span>  
 <span data-ttu-id="a2a8b-116">Selecione como a origem CDC deve tratar erros em um fluxo: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-116">Select how the CDC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="a2a8b-117">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-117">**Truncation**</span></span>  
 <span data-ttu-id="a2a8b-118">Selecione como a origem CDC deve tratar o truncamento em um fluxo: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-118">Select how the CDC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="a2a8b-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-119">**Description**</span></span>  
 <span data-ttu-id="a2a8b-120">Não usado.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-120">Not used.</span></span>  
  
 <span data-ttu-id="a2a8b-121">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="a2a8b-122">Selecione como a origem CDC trata todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-122">Select how the CDC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="a2a8b-123">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-123">**Apply**</span></span>  
 <span data-ttu-id="a2a8b-124">Aplique as opções de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="a2a8b-125">Opções de tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="a2a8b-125">Error Handling Options</span></span>  
 <span data-ttu-id="a2a8b-126">Você usa as opções a seguir para configurar como a origem CDC trata erros e truncamentos.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-126">You use the following options to configure how the CDC source handles errors and truncations.</span></span>  
  
 <span data-ttu-id="a2a8b-127">**Falha no Componente**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-127">**Fail Component**</span></span>  
 <span data-ttu-id="a2a8b-128">A tarefa Fluxo de Dados falha quando ocorre um erro ou um truncamento.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="a2a8b-129">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-129">This is the default behavior.</span></span>  
  
 <span data-ttu-id="a2a8b-130">**Ignorar Falha**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-130">**Ignore Failure**</span></span>  
 <span data-ttu-id="a2a8b-131">O erro ou truncamento é ignorado e a linha de dados é direcionada para a saída da origem CDC.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-131">The error or the truncation is ignored and the data row is directed to the CDC source output.</span></span>  
  
 <span data-ttu-id="a2a8b-132">**Redirecionar fluxo**</span><span class="sxs-lookup"><span data-stu-id="a2a8b-132">**Redirect Flow**</span></span>  
 <span data-ttu-id="a2a8b-133">O erro ou a linha de dados de truncamento é direcionada para a saída do erro da origem CDC.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-133">The error or the truncation data row is directed to the error output of the CDC source.</span></span> <span data-ttu-id="a2a8b-134">Neste caso, o tratamento de erro da origem CDC é usado.</span><span class="sxs-lookup"><span data-stu-id="a2a8b-134">In this case the CDC source error handling is used.</span></span> <span data-ttu-id="a2a8b-135">Para obter mais informações, consulte [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="a2a8b-135">For more information, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a8b-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2a8b-136">See Also</span></span>  
 <span data-ttu-id="a2a8b-137">[Editor de Origem CDC &#40;Página Gerenciador de Conexões&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a2a8b-137">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a2a8b-138">Editor de Origem CDC &#40;página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="a2a8b-138">CDC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-columns-page.md)  
  
  
