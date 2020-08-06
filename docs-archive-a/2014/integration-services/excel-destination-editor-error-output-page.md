---
title: Editor de destino do Excel (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.erroroutput.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: 72ae01cc-1774-4a36-9674-a0f2b2bf8c42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bee679f563105cade3053a13eb122f6d482a7d86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574803"
---
# <a name="excel-destination-editor-error-output-page"></a><span data-ttu-id="7cb68-102">Editor de Destino do Excel (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="7cb68-102">Excel Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="7cb68-103">Use a página **Avançado** da caixa de diálogo **Editor de Destinos do Excel** para especificar opções de tratamento de erro.</span><span class="sxs-lookup"><span data-stu-id="7cb68-103">Use the **Advanced** page of the **Excel Destination Editor** dialog box to specify options for error handling.</span></span>  
  
 <span data-ttu-id="7cb68-104">Para obter mais informações sobre destinos do Excel, consulte [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="7cb68-104">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7cb68-105">Opções</span><span class="sxs-lookup"><span data-stu-id="7cb68-105">Options</span></span>  
 <span data-ttu-id="7cb68-106">**Entrada ou Saída**</span><span class="sxs-lookup"><span data-stu-id="7cb68-106">**Input or Output**</span></span>  
 <span data-ttu-id="7cb68-107">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7cb68-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="7cb68-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7cb68-108">**Column**</span></span>  
 <span data-ttu-id="7cb68-109">Veja as colunas externas (origem) que você selecionou no nó **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem do Excel**.</span><span class="sxs-lookup"><span data-stu-id="7cb68-109">View the external (source) columns that you selected in the **Connection Manager** node of the **Excel Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="7cb68-110">**Erro**</span><span class="sxs-lookup"><span data-stu-id="7cb68-110">**Error**</span></span>  
 <span data-ttu-id="7cb68-111">Especifique o que deve acontecer quando ocorre um erro: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="7cb68-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7cb68-112">**Tópicos relacionados:** [Tratamento de erro em dados](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="7cb68-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="7cb68-113">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="7cb68-113">**Truncation**</span></span>  
 <span data-ttu-id="7cb68-114">Especifique o que deve acontecer quando ocorre um truncamento: ignorar a falha, redirecionar a linha ou causar falha do componente.</span><span class="sxs-lookup"><span data-stu-id="7cb68-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7cb68-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7cb68-115">**Description**</span></span>  
 <span data-ttu-id="7cb68-116">Exiba a descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="7cb68-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="7cb68-117">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="7cb68-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="7cb68-118">Especifique o que deve acontecer a todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="7cb68-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7cb68-119">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="7cb68-119">**Apply**</span></span>  
 <span data-ttu-id="7cb68-120">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="7cb68-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb68-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7cb68-121">See Also</span></span>  
 <span data-ttu-id="7cb68-122">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7cb68-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7cb68-123">[Editor de destino do Excel &#40;página do Gerenciador de conexões&#41;](../../2014/integration-services/excel-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="7cb68-123">[Excel Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="7cb68-124">[Página Mapeamentos &#40;editor de destinos do Excel&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="7cb68-124">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="7cb68-125">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="7cb68-125">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
