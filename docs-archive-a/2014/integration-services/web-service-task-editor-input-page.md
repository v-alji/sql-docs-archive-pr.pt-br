---
title: Editor da tarefa serviço da Web (página entrada) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.input.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 93529c88-f540-47f2-a10a-12c87318ed6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ae876572747b9bb1088fe8b0a1c2c2fdde9f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582513"
---
# <a name="web-service-task-editor-input-page"></a><span data-ttu-id="9a596-102">Editor da Tarefa Serviço da Web (página Entrada)</span><span class="sxs-lookup"><span data-stu-id="9a596-102">Web Service Task Editor (Input Page)</span></span>
  <span data-ttu-id="9a596-103">Use a página **Entrada** da caixa de diálogo do **Editor da Tarefa Serviço da Web** para especificar o Serviço da Web, o método Web e os valores a serem fornecidos ao método Web como entrada.</span><span class="sxs-lookup"><span data-stu-id="9a596-103">Use the **Input** page of the **Web Service Task Editor** dialog box to specify the Web Service, the Web method, and the values to provide to the Web method as input.</span></span> <span data-ttu-id="9a596-104">Os valores podem ser fornecidos digitando cadeias de caracteres diretamente na coluna Valor ou selecionando variáveis na coluna Valor.</span><span class="sxs-lookup"><span data-stu-id="9a596-104">The values can be provided either by typing strings directly in the Value column, or by selecting variables in the Value column.</span></span>  
  
 <span data-ttu-id="9a596-105">Para saber mais sobre essa tarefa, consulte [Tarefa Serviço da Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="9a596-105">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a596-106">Opções</span><span class="sxs-lookup"><span data-stu-id="9a596-106">Options</span></span>  
 <span data-ttu-id="9a596-107">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="9a596-107">**Service**</span></span>  
 <span data-ttu-id="9a596-108">Selecione na lista um serviço da Web a ser usado para executar o método Web.</span><span class="sxs-lookup"><span data-stu-id="9a596-108">Select a Web service from the list to use to execute the Web method.</span></span>  
  
 <span data-ttu-id="9a596-109">**Método**</span><span class="sxs-lookup"><span data-stu-id="9a596-109">**Method**</span></span>  
 <span data-ttu-id="9a596-110">Selecione na lista um método Web a ser executado pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a596-110">Select a Web method from the list for the task to execute.</span></span>  
  
 <span data-ttu-id="9a596-111">**WebMethodDocumentation**</span><span class="sxs-lookup"><span data-stu-id="9a596-111">**WebMethodDocumentation**</span></span>  
 <span data-ttu-id="9a596-112">Digite uma descrição do método Web ou clique no botão Procurar **(...)** e digite a descrição na caixa de diálogo **Documentação do Método Web**.</span><span class="sxs-lookup"><span data-stu-id="9a596-112">Type a description of Web method, or the click the browse button **(...)** and then type the description in the **Web Method Documentation** dialog box.</span></span>  
  
 <span data-ttu-id="9a596-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9a596-113">**Name**</span></span>  
 <span data-ttu-id="9a596-114">Lista os nomes das entradas no método Web.</span><span class="sxs-lookup"><span data-stu-id="9a596-114">Lists the names of the inputs to the Web method.</span></span>  
  
 <span data-ttu-id="9a596-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9a596-115">**Type**</span></span>  
 <span data-ttu-id="9a596-116">Lista o tipo de dados das entradas.</span><span class="sxs-lookup"><span data-stu-id="9a596-116">Lists the data type of the inputs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a596-117">A tarefa Serviço da Web só suporta parâmetros dos seguintes tipos de dados: tipos primitivos, como números inteiros e cadeias de caracteres; matrizes e sequências de tipos primitivos; e enumerações.</span><span class="sxs-lookup"><span data-stu-id="9a596-117">The Web Service task supports parameters of the following data types only: primitive types such as integers and strings; arrays and sequences of primitive types; and enumerations.</span></span>  
  
 <span data-ttu-id="9a596-118">**Variável**</span><span class="sxs-lookup"><span data-stu-id="9a596-118">**Variable**</span></span>  
 <span data-ttu-id="9a596-119">Marque as caixas de seleção para usar variáveis para fornecer entradas.</span><span class="sxs-lookup"><span data-stu-id="9a596-119">Select the check boxes to use variables to provide inputs.</span></span>  
  
 <span data-ttu-id="9a596-120">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9a596-120">**Value**</span></span>  
 <span data-ttu-id="9a596-121">Se as caixas de seleção Variável forem marcadas, selecione as variáveis na lista para fornecer as entradas; caso contrário, digite os valores a serem usados nas entradas.</span><span class="sxs-lookup"><span data-stu-id="9a596-121">If the Variable check-boxes are selected, select the variables in the list to provide the inputs; otherwise, type the values to use in the inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a596-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a596-122">See Also</span></span>  
 <span data-ttu-id="9a596-123">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9a596-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9a596-124">[Editor da tarefa serviço da Web &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9a596-124">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9a596-125">[Editor da tarefa serviço da Web &#40;página saída&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a596-125">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="9a596-126">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="9a596-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
