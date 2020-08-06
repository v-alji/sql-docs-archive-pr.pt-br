---
title: Editor de transformação scripts (página entradas e saídas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.columnproperties.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: 9659d2d2-5d73-4470-9768-e07b77142fc9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16adf74a1cd8f0c778bc18eaff84437b8fc13603
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678846"
---
# <a name="script-transformation-editor-inputs-and-outputs-page"></a><span data-ttu-id="a7eb7-102">Editor de Transformação Scripts (página Entradas e Saídas)</span><span class="sxs-lookup"><span data-stu-id="a7eb7-102">Script Transformation Editor (Inputs and Outputs Page)</span></span>
  <span data-ttu-id="a7eb7-103">Use a página **Entradas e Saídas** da caixa de diálogo do **Editor de Transformação Scripts** para adicionar, remover e configurar entradas e saídas para a Transformação Scripts.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-103">Use the **Inputs and Outputs** page of the **Script Transformation Editor** dialog box to add, remove, and configure inputs and outputs for the Script Transformation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7eb7-104">Os componentes de origem possuem saídas e não entradas, enquanto os componentes de destino possuem entradas mas nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-104">Source components have outputs and no inputs, while destination components have inputs but no outputs.</span></span> <span data-ttu-id="a7eb7-105">Transformações têm entradas e saídas.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-105">Transformations have both inputs and outputs.</span></span>  
  
 <span data-ttu-id="a7eb7-106">Para obter mais informações sobre o componente Script, consulte [Script Component](data-flow/transformations/script-component.md) e [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a7eb7-106">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="a7eb7-107">Para obter informações sobre a programação do componente Script, consulte [Estender o fluxo de dados com o componente de Script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="a7eb7-107">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7eb7-108">Opções</span><span class="sxs-lookup"><span data-stu-id="a7eb7-108">Options</span></span>  
 <span data-ttu-id="a7eb7-109">**Inputs and outputs**</span><span class="sxs-lookup"><span data-stu-id="a7eb7-109">**Inputs and outputs**</span></span>  
 <span data-ttu-id="a7eb7-110">Selecione uma entrada ou uma saída à esquerda para exibir suas propriedades na tabela à direita.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-110">Select an input or output on the left to view its properties in the table on the right.</span></span> <span data-ttu-id="a7eb7-111">As propriedades disponíveis para edição variam de acordo com a seleção.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-111">Properties available for editing vary according to the selection.</span></span> <span data-ttu-id="a7eb7-112">Muitas das propriedades exibidas são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-112">Many of the properties displayed are read-only.</span></span> <span data-ttu-id="a7eb7-113">Para obter mais informações sobre as propriedades individuais, consulte os tópicos abaixo.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-113">For more information on the individual properties, see the following topics.</span></span>  
  
 [<span data-ttu-id="a7eb7-114">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="a7eb7-114">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
 [<span data-ttu-id="a7eb7-115">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="a7eb7-115">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
 <span data-ttu-id="a7eb7-116">**Adicionar Saída**</span><span class="sxs-lookup"><span data-stu-id="a7eb7-116">**Add Output**</span></span>  
 <span data-ttu-id="a7eb7-117">Adicione uma saída adicional à lista.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-117">Add an additional output to the list.</span></span>  
  
 <span data-ttu-id="a7eb7-118">**Adicionar Coluna**</span><span class="sxs-lookup"><span data-stu-id="a7eb7-118">**Add Column**</span></span>  
 <span data-ttu-id="a7eb7-119">Selecione uma pasta na qual deseja colocar a nova coluna de saída e adicione a coluna clicando em **Adicionar Coluna**.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-119">Select a folder in which to place the new output column, and then add the column by clicking **Add Column**.</span></span>  
  
 <span data-ttu-id="a7eb7-120">**Remover Saída**</span><span class="sxs-lookup"><span data-stu-id="a7eb7-120">**Remove Output**</span></span>  
 <span data-ttu-id="a7eb7-121">Selecione uma saída e remova-a clicando em **Remover Saída**.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-121">Select an output, and then remove it by clicking **Remove Output**.</span></span>  
  
 <span data-ttu-id="a7eb7-122">**Remover Coluna**</span><span class="sxs-lookup"><span data-stu-id="a7eb7-122">**Remove Column**</span></span>  
 <span data-ttu-id="a7eb7-123">Selecione uma coluna e remova-a clicando em **Remover Coluna**.</span><span class="sxs-lookup"><span data-stu-id="a7eb7-123">Select a column, and then remove it by clicking **Remove Column**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7eb7-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a7eb7-124">See Also</span></span>  
 <span data-ttu-id="a7eb7-125">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb7-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a7eb7-126">[Selecionar tipo de componente de script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb7-126">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="a7eb7-127">[Editor de transformação scripts &#40;página colunas de entrada&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb7-127">[Script Transformation Editor &#40;Input Columns Page&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span></span>  
 <span data-ttu-id="a7eb7-128">[Editor de transformação scripts &#40;página script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb7-128">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="a7eb7-129">[Editor de transformação scripts &#40;página gerenciadores de conexões&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb7-129">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="a7eb7-130">Exemplos de componentes Script adicionais</span><span class="sxs-lookup"><span data-stu-id="a7eb7-130">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
