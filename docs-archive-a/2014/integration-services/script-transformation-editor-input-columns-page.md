---
title: Editor de transformação scripts (página colunas de entrada) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.inputcolumn.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: d6e4ce84-3335-48e6-82d3-1c359ed87f63
author: chugugrace
ms.author: chugu
ms.openlocfilehash: daffb52b62ad59ae4fe574d7fa27d4820b9cb5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678848"
---
# <a name="script-transformation-editor-input-columns-page"></a><span data-ttu-id="8acaf-102">Editor de Transformação Scripts (página Colunas de Entrada)</span><span class="sxs-lookup"><span data-stu-id="8acaf-102">Script Transformation Editor (Input Columns Page)</span></span>
  <span data-ttu-id="8acaf-103">Use a página **Colunas de Entrada** da caixa de diálogo **Editor de Transformação Scripts** para definir propriedades nas colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="8acaf-103">Use the **Input Columns** page of the **Script Transformation Editor** dialog box to set properties on input columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8acaf-104">A página **Colunas de Entrada** não é exibida para componentes de Origem que têm saídas mas não têm entradas.</span><span class="sxs-lookup"><span data-stu-id="8acaf-104">The **Input Columns** page is not displayed for Source components, which have outputs but no inputs.</span></span>  
  
 <span data-ttu-id="8acaf-105">Para obter mais informações sobre o componente Script, consulte [Script Component](data-flow/transformations/script-component.md) e [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8acaf-105">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="8acaf-106">Para obter informações sobre a programação do componente Script, consulte [Estender o fluxo de dados com o componente de Script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="8acaf-106">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8acaf-107">Opções</span><span class="sxs-lookup"><span data-stu-id="8acaf-107">Options</span></span>  
 <span data-ttu-id="8acaf-108">**Nome de entrada**</span><span class="sxs-lookup"><span data-stu-id="8acaf-108">**Input name**</span></span>  
 <span data-ttu-id="8acaf-109">Selecione na lista de entradas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8acaf-109">Select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="8acaf-110">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="8acaf-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="8acaf-111">Usando as caixas de seleção, especifique as colunas que a transformação scripts usará.</span><span class="sxs-lookup"><span data-stu-id="8acaf-111">Using the check boxes, specify the columns that the script transformation will use.</span></span>  
  
 <span data-ttu-id="8acaf-112">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="8acaf-112">**Input Column**</span></span>  
 <span data-ttu-id="8acaf-113">Selecione colunas para cada linha na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8acaf-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="8acaf-114">As seleções se refletem naquelas da caixa de seleção da tabela **Colunas de Entrada Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="8acaf-114">Your selections are reflected in the check box selections in the **Available Input Columns**table.</span></span>  
  
 <span data-ttu-id="8acaf-115">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="8acaf-115">**Output Alias**</span></span>  
 <span data-ttu-id="8acaf-116">Digite um alias para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="8acaf-116">Type an alias for each output column.</span></span> <span data-ttu-id="8acaf-117">O padrão é o nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8acaf-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="8acaf-118">**Tipo de Uso**</span><span class="sxs-lookup"><span data-stu-id="8acaf-118">**Usage Type**</span></span>  
 <span data-ttu-id="8acaf-119">Especifique se a Transformação Scripts tratará cada coluna como `ReadOnly` ou `ReadWrite`.</span><span class="sxs-lookup"><span data-stu-id="8acaf-119">Specify whether the Script Transformation will treat each column as `ReadOnly` or `ReadWrite`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acaf-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8acaf-120">See Also</span></span>  
 <span data-ttu-id="8acaf-121">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8acaf-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8acaf-122">[Selecionar tipo de componente de script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="8acaf-122">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="8acaf-123">[Editor de transformação scripts &#40;página entradas e saídas&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span><span class="sxs-lookup"><span data-stu-id="8acaf-123">[Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span></span>  
 <span data-ttu-id="8acaf-124">[Editor de transformação scripts &#40;página script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="8acaf-124">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="8acaf-125">[Editor de transformação scripts &#40;página gerenciadores de conexões&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="8acaf-125">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="8acaf-126">Exemplos de componentes Script adicionais</span><span class="sxs-lookup"><span data-stu-id="8acaf-126">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
