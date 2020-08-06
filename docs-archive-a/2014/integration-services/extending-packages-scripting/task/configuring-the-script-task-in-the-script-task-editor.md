---
title: Configurar a tarefa Script no Editor da Tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], configuring
- Script Task Editor
- SSIS Script task, configuring
ms.assetid: 232de0c9-b24d-4c38-861d-6c1f4a75bdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b75b4a030e6c5baa2e26c610b0e8216843c8cca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571452"
---
# <a name="configuring-the-script-task-in-the-script-task-editor"></a><span data-ttu-id="d7b24-102">Configurando a tarefa Script no Editor da Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="d7b24-102">Configuring the Script Task in the Script Task Editor</span></span>
  <span data-ttu-id="d7b24-103">Antes de escrever um código personalizado na tarefa Script, configure suas propriedades de entidade de segurança nas três páginas do **Editor da Tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="d7b24-103">Before you write custom code in the Script task, you configure its principal properties in the three pages of the **Script Task Editor**.</span></span> <span data-ttu-id="d7b24-104">É possível configurar propriedades de tarefa adicionais que não são exclusivas da tarefa Script através da janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="d7b24-104">You can configure additional task properties that are not unique to the Script task by using the Properties window.</span></span>

> [!NOTE]
>  <span data-ttu-id="d7b24-105">Ao contrário das versões anteriores onde você podia indicar se os scripts seriam pré-compilados, todos os scripts são pré-compilados a partir do [!INCLUDE[ssISversion10](../../../includes/ssisversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7b24-105">Unlike earlier versions where you could indicate whether scripts were precompiled, all scripts are precompiled beginning in [!INCLUDE[ssISversion10](../../../includes/ssisversion10-md.md)].</span></span>

## <a name="general-page-of-the-script-task-editor"></a><span data-ttu-id="d7b24-106">Página Geral do Editor da Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="d7b24-106">General Page of the Script Task Editor</span></span>
 <span data-ttu-id="d7b24-107">Na página **Geral** do **Editor da Tarefa Script**, você atribui um nome exclusivo e uma descrição para a tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="d7b24-107">On the **General** page of the **Script Task Editor**, you assign a unique name and a description for the Script task.</span></span>

## <a name="script-page-of-the-script-task-editor"></a><span data-ttu-id="d7b24-108">Página Script do Editor da Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="d7b24-108">Script Page of the Script Task Editor</span></span>
 <span data-ttu-id="d7b24-109">A página **Script** do **Editor da Tarefa Script** exibe as propriedades personalizadas da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="d7b24-109">The **Script** page of the **Script Task Editor** displays the custom properties of the Script task.</span></span>

### <a name="scriptlanguage-property"></a><span data-ttu-id="d7b24-110">Propriedade ScriptLanguage</span><span class="sxs-lookup"><span data-stu-id="d7b24-110">ScriptLanguage Property</span></span>
 <span data-ttu-id="d7b24-111">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] VSTA ([!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications) dá suporte às linguagens de programação do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic ou do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d7b24-111">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) supports the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# programming languages.</span></span> <span data-ttu-id="d7b24-112">Depois de criar um script na tarefa Script, você não poderá alterar o valor da propriedade **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="d7b24-112">After you create a script in the Script task, you cannot change value of the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="d7b24-113">Para definir a linguagem de script padrão para componentes e tarefas de Script, use a propriedade **ScriptLanguage** na página **Geral** da caixa de diálogo **Opções**.</span><span class="sxs-lookup"><span data-stu-id="d7b24-113">To set the default script language for Script tasks and Script components, use the **ScriptLanguage** property on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="d7b24-114">Para obter mais informações, consulte [General Page](../../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="d7b24-114">For more information, see [General Page](../../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="entrypoint-property"></a><span data-ttu-id="d7b24-115">Propriedade EntryPoint</span><span class="sxs-lookup"><span data-stu-id="d7b24-115">EntryPoint Property</span></span>
 <span data-ttu-id="d7b24-116">A propriedade `EntryPoint` especifica o método da classe `ScriptMain` no projeto do VSTA que o [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] chama, em runtime, como ponto de entrada no código da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="d7b24-116">The `EntryPoint` property specifies the method on the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="d7b24-117">A `ScriptMain` classe é a classe padrão gerada pelos modelos de script.</span><span class="sxs-lookup"><span data-stu-id="d7b24-117">The `ScriptMain` class is the default class generated by the script templates.</span></span>

 <span data-ttu-id="d7b24-118">Se você alterar o nome do método no projeto do VSTA, altere o valor da propriedade `EntryPoint`.</span><span class="sxs-lookup"><span data-stu-id="d7b24-118">If you change the name of the method in the VSTA project, you must change the value of the `EntryPoint` property.</span></span>

### <a name="readonlyvariables-and-readwritevariables-properties"></a><span data-ttu-id="d7b24-119">Propriedades ReadOnlyVariables e ReadWriteVariables</span><span class="sxs-lookup"><span data-stu-id="d7b24-119">ReadOnlyVariables and ReadWriteVariables Properties</span></span>
 <span data-ttu-id="d7b24-120">Você pode inserir listas de variáveis existentes, delimitadas por vírgulas, como os valores dessas propriedades a fim de disponibilizar as variáveis para acesso somente leitura ou leitura/gravação dentro do código de tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="d7b24-120">You can enter comma-delimited lists of existing variables as the values of these properties to make the variables available for read-only or read/write access within the Script task code.</span></span> <span data-ttu-id="d7b24-121">Variáveis de ambos os tipos são acessadas em código através da propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> do objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="d7b24-121">Variables of both types are accessed in code through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="d7b24-122">Para obter mais informações, consulte [Usando variáveis na tarefa Script](../../extending-packages-scripting/task/using-variables-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="d7b24-122">For more information, see [Using Variables in the Script Task](../../extending-packages-scripting/task/using-variables-in-the-script-task.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="d7b24-123">Nomes de variáveis diferenciam maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d7b24-123">Variable names are case-sensitive.</span></span>

 <span data-ttu-id="d7b24-124">Para selecionar as variáveis, clique no botão de reticências ( **...** ) ao lado do campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="d7b24-124">To select the variables, click the ellipsis (**...**) button next to the property field.</span></span> <span data-ttu-id="d7b24-125">Para obter mais informações, consulte [Página Selecionar Variáveis](../../control-flow/select-variables-page.md).</span><span class="sxs-lookup"><span data-stu-id="d7b24-125">For more information, see [Select Variables Page](../../control-flow/select-variables-page.md).</span></span>

### <a name="edit-script-button"></a><span data-ttu-id="d7b24-126">Botão Editar Script</span><span class="sxs-lookup"><span data-stu-id="d7b24-126">Edit Script Button</span></span>
 <span data-ttu-id="d7b24-127">O botão **Editar Script** inicia o ambiente de desenvolvimento do VSTA no qual você escreve seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="d7b24-127">The **Edit Script** button launches the VSTA development environment in which you write your custom script.</span></span> <span data-ttu-id="d7b24-128">Para obter mais informações, consulte [Codificar e depurar a Tarefa Script](coding-and-debugging-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="d7b24-128">For more information, see [Coding and Debugging the Script Task](coding-and-debugging-the-script-task.md).</span></span>

## <a name="expressions-page-of-the-script-task-editor"></a><span data-ttu-id="d7b24-129">Página Expressões do Editor da Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="d7b24-129">Expressions Page of the Script Task Editor</span></span>
 <span data-ttu-id="d7b24-130">Na página **Expressões** do **Editor da Tarefa Script**, você pode usar expressões para fornecer valores para as propriedades da tarefa Script listadas anteriormente e para muitas outras propriedades da tarefa.</span><span class="sxs-lookup"><span data-stu-id="d7b24-130">On the **Expressions** page of the **Script Task Editor**, you can use expressions to provide values for the properties of the Script task listed above and for many other task properties.</span></span> <span data-ttu-id="d7b24-131">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d7b24-131">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>

<span data-ttu-id="d7b24-132">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d7b24-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d7b24-133">Para obter os downloads, artigos, exemplos e vídeos mais recentes da [!INCLUDE[msCoName](../../../includes/msconame-md.md)], bem como as soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="d7b24-133">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d7b24-134">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="d7b24-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d7b24-135">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="d7b24-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7b24-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7b24-136">See Also</span></span>
 [<span data-ttu-id="d7b24-137">Codificando e depurando a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="d7b24-137">Coding and Debugging the Script Task</span></span>](coding-and-debugging-the-script-task.md)


