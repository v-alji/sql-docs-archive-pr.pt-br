---
title: Editor da tarefa serviço da Web (página saída) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582510"
---
# <a name="web-service-task-editor-output-page"></a><span data-ttu-id="8d5ef-102">Editor da Tarefa Serviço da Web (página Saída)</span><span class="sxs-lookup"><span data-stu-id="8d5ef-102">Web Service Task Editor (Output Page)</span></span>
  <span data-ttu-id="8d5ef-103">Use a página **Saída** da caixa de diálogo **Editor da Tarefa Serviço da Web** para especificar onde armazenar o resultado retornado pelo método Web.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-103">Use the **Output** page of the **Web Service Task Editor** dialog box to specify where to store the result returned by the Web method.</span></span>  
  
 <span data-ttu-id="8d5ef-104">Para saber mais sobre essa tarefa, consulte [Tarefa Serviço da Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="8d5ef-104">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="8d5ef-105">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="8d5ef-105">Static Options</span></span>  
 <span data-ttu-id="8d5ef-106">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="8d5ef-106">**OutputType**</span></span>  
 <span data-ttu-id="8d5ef-107">Selecione o tipo de armazenamento a usar para os resultados.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-107">Select the storage type to use when storing the results.</span></span> <span data-ttu-id="8d5ef-108">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8d5ef-109">Valor</span><span class="sxs-lookup"><span data-stu-id="8d5ef-109">Value</span></span>|<span data-ttu-id="8d5ef-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d5ef-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d5ef-111">**File Connection**</span><span class="sxs-lookup"><span data-stu-id="8d5ef-111">**File Connection**</span></span>|<span data-ttu-id="8d5ef-112">Armazene os resultados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-112">Store the results in a file.</span></span> <span data-ttu-id="8d5ef-113">A seleção deste valor exibe a opção dinâmica **File**.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-113">Selecting this value displays the dynamic option, **File**.</span></span>|  
|<span data-ttu-id="8d5ef-114">**Variável**</span><span class="sxs-lookup"><span data-stu-id="8d5ef-114">**Variable**</span></span>|<span data-ttu-id="8d5ef-115">Armazene os resultados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-115">Store the results in a variable.</span></span> <span data-ttu-id="8d5ef-116">A seleção deste valor exibe a opção dinâmica **Variable**.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-116">Selecting this value displays the dynamic option, **Variable**.</span></span>|  
  
## <a name="outputtype-dynamic-options"></a><span data-ttu-id="8d5ef-117">Opções dinâmicas de OutputType</span><span class="sxs-lookup"><span data-stu-id="8d5ef-117">OutputType Dynamic Options</span></span>  
  
### <a name="outputtype--file-connection"></a><span data-ttu-id="8d5ef-118">OutputType = File Connection</span><span class="sxs-lookup"><span data-stu-id="8d5ef-118">OutputType = File Connection</span></span>  
 <span data-ttu-id="8d5ef-119">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="8d5ef-119">**File**</span></span>  
 <span data-ttu-id="8d5ef-120">Selecione um gerenciador de conexões de Arquivos na lista ou clique em \<**New Connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-120">Select a File connection manager in the list or click \<**New Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="8d5ef-121">**Tópicos relacionados:** [Gerenciador de conexões de arquivos](connection-manager/file-connection-manager.md), [Editor do Gerenciador de conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="8d5ef-121">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="outputtype--variable"></a><span data-ttu-id="8d5ef-122">OutputType = Variable</span><span class="sxs-lookup"><span data-stu-id="8d5ef-122">OutputType = Variable</span></span>  
 <span data-ttu-id="8d5ef-123">**Variável**</span><span class="sxs-lookup"><span data-stu-id="8d5ef-123">**Variable**</span></span>  
 <span data-ttu-id="8d5ef-124">Selecione uma variável na lista ou clique em \<**New Variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="8d5ef-124">Select a variable in the list or click \<**New Variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="8d5ef-125">**Tópicos relacionados:**  [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="8d5ef-125">**Related Topics:**  [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5ef-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d5ef-126">See Also</span></span>  
 <span data-ttu-id="8d5ef-127">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ef-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8d5ef-128">[Editor da tarefa serviço da Web &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ef-128">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="8d5ef-129">[Editor da tarefa serviço Web &#40;página de entrada&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ef-129">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 [<span data-ttu-id="8d5ef-130">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="8d5ef-130">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
