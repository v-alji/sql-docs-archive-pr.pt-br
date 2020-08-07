---
title: Editor da tarefa Executar SQL (página mapeamento de parâmetros) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572127"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a><span data-ttu-id="8e161-102">Editor da Tarefa Executar SQL (página Mapeamento de Parâmetros)</span><span class="sxs-lookup"><span data-stu-id="8e161-102">Execute SQL Task Editor (Parameter Mapping Page)</span></span>
  <span data-ttu-id="8e161-103">Use a página **Mapeamento de Parâmetros** da caixa de diálogo **Editor da Tarefa Executar SQL** para mapear as variáveis para os parâmetros na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="8e161-103">Use the **Parameter Mapping** page of the **Execute SQL Task Editor** dialog box to map variables to parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="8e161-104">Para saber mais sobre essa tarefa, consulte [Tarefa Executar SQL](control-flow/execute-sql-task.md) e [Parâmetros e códigos de retorno na Tarefa Executar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="8e161-104">To learn about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e161-105">Opções</span><span class="sxs-lookup"><span data-stu-id="8e161-105">Options</span></span>  
 <span data-ttu-id="8e161-106">**Nome da Variável**</span><span class="sxs-lookup"><span data-stu-id="8e161-106">**Variable Name**</span></span>  
 <span data-ttu-id="8e161-107">Após ter adicionado um mapeamento de parâmetros clicando em **Adicionar**, selecione uma variável de sistema ou definida pelo usuário na lista ou clique em \<**New variable...**> para adicionar uma nova variável usando a caixa de diálogo **Adicionar Variável**.</span><span class="sxs-lookup"><span data-stu-id="8e161-107">After you have added a parameter mapping by clicking **Add**, select a system or user-defined variable from the list or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="8e161-108">**Tópicos relacionados:** [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="8e161-108">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
 <span data-ttu-id="8e161-109">**Direção**</span><span class="sxs-lookup"><span data-stu-id="8e161-109">**Direction**</span></span>  
 <span data-ttu-id="8e161-110">Selecione a direção do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e161-110">Select the direction of the parameter.</span></span> <span data-ttu-id="8e161-111">Mapeie cada variável para um parâmetro de entrada, parâmetro de saída ou um código de retorno.</span><span class="sxs-lookup"><span data-stu-id="8e161-111">Map each variable to an input parameter, output parameter, or a return code.</span></span>  
  
 <span data-ttu-id="8e161-112">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="8e161-112">**Data Type**</span></span>  
 <span data-ttu-id="8e161-113">Selecione o tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e161-113">Select the data type of the parameter.</span></span> <span data-ttu-id="8e161-114">A lista de tipos de dados disponíveis é específica para o provedor selecionado no gerenciador de conexões usado pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="8e161-114">The list of available data types is specific to the provider selected in the connection manager used by the task.</span></span>  
  
 <span data-ttu-id="8e161-115">**Nome do parâmetro**</span><span class="sxs-lookup"><span data-stu-id="8e161-115">**Parameter Name**</span></span>  
 <span data-ttu-id="8e161-116">Forneça um nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e161-116">Provide a parameter name.</span></span>  
  
 <span data-ttu-id="8e161-117">Dependendo do tipo de gerenciador de conexões usado pela tarefa, você deve usar números ou nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e161-117">Depending on the connection manager type that the task uses, you must use numbers or parameter names.</span></span> <span data-ttu-id="8e161-118">Alguns tipos de gerenciadores de conexões exigem que o primeiro caractere do nome do parâmetro seja o sinal \@, nomes específicos como \@Param1, ou nomes de coluna como nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e161-118">Some connection manager types require that the first character of the parameter name is the \@ sign , specific names like \@Param1, or column names as parameter names.</span></span>  
  
 <span data-ttu-id="8e161-119">**Tópicos relacionados:** [Parâmetros e códigos de retorno na Tarefa Executar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="8e161-119">**Related Topics:** [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="8e161-120">**Tamanho do Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="8e161-120">**Parameter Size**</span></span>  
 <span data-ttu-id="8e161-121">Informe o tamanho dos parâmetros com comprimento variável, como cadeias de caracteres e campos binários.</span><span class="sxs-lookup"><span data-stu-id="8e161-121">Provide the size of parameters that have variable length, such as strings and binary fields.</span></span>  
  
 <span data-ttu-id="8e161-122">Esta configuração garante que o provedor aloque espaço suficiente para obter valores de parâmetro de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="8e161-122">This setting ensures that the provider allocates sufficient space for variable-length parameter values.</span></span>  
  
 <span data-ttu-id="8e161-123">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="8e161-123">**Add**</span></span>  
 <span data-ttu-id="8e161-124">Clique para adicionar um mapeamento de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="8e161-124">Click to add a parameter mapping.</span></span>  
  
 <span data-ttu-id="8e161-125">**Remover**</span><span class="sxs-lookup"><span data-stu-id="8e161-125">**Remove**</span></span>  
 <span data-ttu-id="8e161-126">Selecione um mapeamento de parâmetros na lista e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="8e161-126">Select a parameter mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e161-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e161-127">See Also</span></span>  
 <span data-ttu-id="8e161-128">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8e161-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8e161-129">[Editor da tarefa Executar SQL &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8e161-129">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="8e161-130">[Editor da tarefa Executar SQL &#40;página conjunto de resultados&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span><span class="sxs-lookup"><span data-stu-id="8e161-130">[Execute SQL Task Editor &#40;Result Set Page&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span></span>  
 [<span data-ttu-id="8e161-131">Referência do Transact-SQL &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="8e161-131">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
