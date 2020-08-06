---
title: Editor da tarefa Executar processo (página processo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ce8629be2c07ae4caac4586b266936a908e71499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678267"
---
# <a name="execute-process-task-editor-process-page"></a><span data-ttu-id="dfa67-102">Execute Process Task Editor (Process Page)</span><span class="sxs-lookup"><span data-stu-id="dfa67-102">Execute Process Task Editor (Process Page)</span></span>
  <span data-ttu-id="dfa67-103">Use a página **Processo** da caixa de diálogo **Editor da Tarefa Executar Processo** , para configurar as opções que executam o processo.</span><span class="sxs-lookup"><span data-stu-id="dfa67-103">Use the **Process** page of the **Execute Process Task Editor** dialog box to configure the options that execute the process.</span></span> <span data-ttu-id="dfa67-104">As opções incluem o executável a ser utilizado, seu local, argumentos do prompt de comando e as variáveis que fornecem entrada e capturam a saída.</span><span class="sxs-lookup"><span data-stu-id="dfa67-104">These options include the executable to run, its location, command prompt arguments, and the variables that provide input and capture output.</span></span>  
  
 <span data-ttu-id="dfa67-105">Para obter informações sobre essa tarefa, consulte [Execute Process Task](control-flow/execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="dfa67-105">To learn about this task, see [Execute Process Task](control-flow/execute-process-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfa67-106">Opções</span><span class="sxs-lookup"><span data-stu-id="dfa67-106">Options</span></span>  
 <span data-ttu-id="dfa67-107">**RequireFullFileName**</span><span class="sxs-lookup"><span data-stu-id="dfa67-107">**RequireFullFileName**</span></span>  
 <span data-ttu-id="dfa67-108">Indique se a tarefa deve falhar se o executável não for localizado no local especificado.</span><span class="sxs-lookup"><span data-stu-id="dfa67-108">Indicate whether the task should fail if the executable is not found at the specified location.</span></span>  
  
 <span data-ttu-id="dfa67-109">**Executável**</span><span class="sxs-lookup"><span data-stu-id="dfa67-109">**Executable**</span></span>  
 <span data-ttu-id="dfa67-110">Digite o nome do executável a utilizar.</span><span class="sxs-lookup"><span data-stu-id="dfa67-110">Type the name of the executable to run.</span></span>  
  
 <span data-ttu-id="dfa67-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="dfa67-111">**Arguments**</span></span>  
 <span data-ttu-id="dfa67-112">Forneça argumentos do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="dfa67-112">Provide command prompt arguments.</span></span>  
  
 <span data-ttu-id="dfa67-113">**WorkingDirectory**</span><span class="sxs-lookup"><span data-stu-id="dfa67-113">**WorkingDirectory**</span></span>  
 <span data-ttu-id="dfa67-114">Digite o caminho da pasta que contém o executável ou clique no botão Procurar **(…)** e localize a pasta.</span><span class="sxs-lookup"><span data-stu-id="dfa67-114">Type the path of the folder that contains the executable, or click the browse button **(...)** and locate the folder.</span></span>  
  
 <span data-ttu-id="dfa67-115">**StandardInputVariable**</span><span class="sxs-lookup"><span data-stu-id="dfa67-115">**StandardInputVariable**</span></span>  
 <span data-ttu-id="dfa67-116">Selecione a variável que fornecerá a entrada para o processo ou clique em \<**New variable...**> para criar uma variável:</span><span class="sxs-lookup"><span data-stu-id="dfa67-116">Select a variable to provide the input to the process, or click \<**New variable...**> to create a new variable:</span></span>  
  
 <span data-ttu-id="dfa67-117">**Tópicos relacionados:**  [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="dfa67-117">**Related Topics:**  [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="dfa67-118">**StandardOutputVariable**</span><span class="sxs-lookup"><span data-stu-id="dfa67-118">**StandardOutputVariable**</span></span>  
 <span data-ttu-id="dfa67-119">Selecione a variável para capturar a saída do processo ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="dfa67-119">Select a variable to capture the output of the process, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="dfa67-120">**StandardErrorVariable**</span><span class="sxs-lookup"><span data-stu-id="dfa67-120">**StandardErrorVariable**</span></span>  
 <span data-ttu-id="dfa67-121">Selecione a variável para capturar a saída de erro do processador ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="dfa67-121">Select a variable to capture the error output of the processor, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="dfa67-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span><span class="sxs-lookup"><span data-stu-id="dfa67-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span></span>  
 <span data-ttu-id="dfa67-123">Indique se a tarefa deve falhar caso o código de saída do processo seja diferente do valor especificado em **SuccessValue**.</span><span class="sxs-lookup"><span data-stu-id="dfa67-123">Indicate whether the task fails if the process exit code is different from the value specified in **SuccessValue**.</span></span>  
  
 <span data-ttu-id="dfa67-124">**SuccessValue**</span><span class="sxs-lookup"><span data-stu-id="dfa67-124">**SuccessValue**</span></span>  
 <span data-ttu-id="dfa67-125">Especifique o valor retornado pelo executável para indicar êxito.</span><span class="sxs-lookup"><span data-stu-id="dfa67-125">Specify the value returned by the executable to indicate success.</span></span> <span data-ttu-id="dfa67-126">Por padrão, esse valor está definido como **0**.</span><span class="sxs-lookup"><span data-stu-id="dfa67-126">By default this value is set to **0**.</span></span>  
  
 <span data-ttu-id="dfa67-127">**TimeOut**</span><span class="sxs-lookup"><span data-stu-id="dfa67-127">**TimeOut**</span></span>  
 <span data-ttu-id="dfa67-128">Especifique o número de segundos em que o processo pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="dfa67-128">Specify the number of seconds that the process can run.</span></span> <span data-ttu-id="dfa67-129">Um valor **0** indica que não é usado nenhum valor de tempo limite e o processo é executado até ser concluído ou até ocorrer um erro.</span><span class="sxs-lookup"><span data-stu-id="dfa67-129">A value of **0** indicates that no time-out value is used, and the process runs until it is completed or until an error occurs.</span></span>  
  
 <span data-ttu-id="dfa67-130">**TerminateProcessAfterTimeOut**</span><span class="sxs-lookup"><span data-stu-id="dfa67-130">**TerminateProcessAfterTimeOut**</span></span>  
 <span data-ttu-id="dfa67-131">Indique se o processo é forçado a terminar após o tempo limite especificado pela opção **TimeOut** .</span><span class="sxs-lookup"><span data-stu-id="dfa67-131">Indicate whether the process is forced to end after the time-out period specified by the **TimeOut** option.</span></span> <span data-ttu-id="dfa67-132">Esta opção só estará disponível se **TimeOut** não for **0**.</span><span class="sxs-lookup"><span data-stu-id="dfa67-132">This option is available only if **TimeOut** is not **0**.</span></span>  
  
 <span data-ttu-id="dfa67-133">**WindowStyle**</span><span class="sxs-lookup"><span data-stu-id="dfa67-133">**WindowStyle**</span></span>  
 <span data-ttu-id="dfa67-134">Especifique o estilo de janela no qual executar o processo.</span><span class="sxs-lookup"><span data-stu-id="dfa67-134">Specify the window style in which to run the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa67-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfa67-135">See Also</span></span>  
 <span data-ttu-id="dfa67-136">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dfa67-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="dfa67-137">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="dfa67-137">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
