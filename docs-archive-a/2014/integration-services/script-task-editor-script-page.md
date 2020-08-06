---
title: Editor da tarefa Script (página script) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scripttask.script.f1
helpviewer_keywords:
- Script Task Editor
ms.assetid: 93da0e0d-83f5-406d-b144-4cce216571cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4eec491cc689d7d5c616e0819075e1ee5159d4e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678853"
---
# <a name="script-task-editor-script-page"></a><span data-ttu-id="72f53-102">Editor da Tarefa Script (página Script)</span><span class="sxs-lookup"><span data-stu-id="72f53-102">Script Task Editor (Script Page)</span></span>
  <span data-ttu-id="72f53-103">Use a página **Script** da caixa de diálogo **Editor da Tarefa Script** para definir propriedades de script e especificar variáveis que podem ser acessados pelo script.</span><span class="sxs-lookup"><span data-stu-id="72f53-103">Use the **Script** page of the **Script Task Editor** dialog box to set script properties and specify variables that can be accessed by the script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72f53-104">No [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] e versões posteriores, todos os scripts são pré-compilados.</span><span class="sxs-lookup"><span data-stu-id="72f53-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] and later versions, all scripts are precompiled.</span></span> <span data-ttu-id="72f53-105">Em versões anteriores, devia ser definida uma propriedade **PrecompileScriptIntoBinaryCode** para especificar que o script estava pré-compilado.</span><span class="sxs-lookup"><span data-stu-id="72f53-105">In earlier versions, you set a **PrecompileScriptIntoBinaryCode** property to specify that the script was precompiled.</span></span>  
  
 <span data-ttu-id="72f53-106">Para obter mais informações sobre a tarefa Script, consulte [Script Task](control-flow/script-task.md) e [Configurando a tarefa Script no Editor da Tarefa Script](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="72f53-106">To learn more about the Script task, see [Script Task](control-flow/script-task.md) and [Configuring the Script Task in the Script Task Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span></span> <span data-ttu-id="72f53-107">Para obter informações sobre a programação da tarefa Script, consulte [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="72f53-107">To learn about programming the Script task, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="72f53-108">Opções</span><span class="sxs-lookup"><span data-stu-id="72f53-108">Options</span></span>  
 <span data-ttu-id="72f53-109">**ScriptLanguage**</span><span class="sxs-lookup"><span data-stu-id="72f53-109">**ScriptLanguage**</span></span>  
 <span data-ttu-id="72f53-110">Selecione a linguagem de criação de scripts para a tarefa, o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic ou o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="72f53-110">Select the scripting language for the task, either [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="72f53-111">Depois de criar um script para a tarefa, você não poderá alterar o valor da propriedade **ScriptLanguage** .</span><span class="sxs-lookup"><span data-stu-id="72f53-111">After you have created a script for the task, you cannot change the value of the **ScriptLanguage** property.</span></span>  
  
 <span data-ttu-id="72f53-112">Para definir a linguagem de criação de scripts padrão para a tarefa Script, use a opção **Idiomas de script** na página **Geral** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="72f53-112">To set the default scripting language for the Script task, use the **Scripting language** option on **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="72f53-113">Para obter mais informações, consulte [General Page](general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="72f53-113">For more information, see [General Page](general-page-of-integration-services-designers-options.md).</span></span>  
  
 <span data-ttu-id="72f53-114">**EntryPoint**</span><span class="sxs-lookup"><span data-stu-id="72f53-114">**EntryPoint**</span></span>  
 <span data-ttu-id="72f53-115">Especifique o método a ser chamado pelo runtime do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] como ponto de entrada no código da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="72f53-115">Specify the method that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime calls as the entry point into the code of the Script task.</span></span> <span data-ttu-id="72f53-116">O método especificado deve estar na classe ScriptMain do projeto do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] VSTA (Tools for Applications), a classe ScriptMain é a classe padrão gerada pelos modelos de script.</span><span class="sxs-lookup"><span data-stu-id="72f53-116">The specified method must be in the ScriptMain class of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) project The ScriptMain class is the default class generated by the script templates.</span></span>  
  
 <span data-ttu-id="72f53-117">Caso altere o nome do método no projeto do VSTA, será preciso alterar o valor da propriedade **EntryPoint** .</span><span class="sxs-lookup"><span data-stu-id="72f53-117">If you change the name of the method in the VSTA project, you must change the value of the **EntryPoint** property.</span></span>  
  
 <span data-ttu-id="72f53-118">**ReadOnlyVariables**</span><span class="sxs-lookup"><span data-stu-id="72f53-118">**ReadOnlyVariables**</span></span>  
 <span data-ttu-id="72f53-119">Digite uma lista, separada por vírgulas, de variáveis somente leitura disponíveis para o script ou clique no botão de reticências (**...**) e selecione as variáveis na caixa de diálogo **Selecionar variáveis**.</span><span class="sxs-lookup"><span data-stu-id="72f53-119">Type a comma-separated list of read-only variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72f53-120">Nomes de variáveis fazem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="72f53-120">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="72f53-121">**ReadWriteVariables**</span><span class="sxs-lookup"><span data-stu-id="72f53-121">**ReadWriteVariables**</span></span>  
 <span data-ttu-id="72f53-122">Digite uma lista, separada por vírgulas, de variáveis de leitura/gravação disponíveis para o script ou clique no botão de reticências (**…**) e selecione as variáveis na caixa de diálogo **Selecionar variáveis**.</span><span class="sxs-lookup"><span data-stu-id="72f53-122">Type a comma-separated list of read/write variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72f53-123">Nomes de variáveis fazem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="72f53-123">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="72f53-124">**Editar Script**</span><span class="sxs-lookup"><span data-stu-id="72f53-124">**Edit Script**</span></span>  
 <span data-ttu-id="72f53-125">Abre o VSTA IDE, onde você pode criar ou modificar o script.</span><span class="sxs-lookup"><span data-stu-id="72f53-125">Opens the VSTA IDE where you can create or modify the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f53-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72f53-126">See Also</span></span>  
 <span data-ttu-id="72f53-127">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="72f53-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="72f53-128">[Página geral](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="72f53-128">[General Page](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="72f53-129">[Editor da tarefa Script &#40;página Geral&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="72f53-129">[Script Task Editor &#40;General Page&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="72f53-130">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="72f53-130">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="72f53-131">[Exemplos de tarefas de script](extending-packages-scripting-task-examples/script-task-examples.md) </span><span class="sxs-lookup"><span data-stu-id="72f53-131">[Script Task Examples](extending-packages-scripting-task-examples/script-task-examples.md) </span></span>  
 <span data-ttu-id="72f53-132">[Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="72f53-132">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="72f53-133">Adicionar, excluir, alterar o escopo de uma variável definida pelo usuário em um pacote</span><span class="sxs-lookup"><span data-stu-id="72f53-133">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
