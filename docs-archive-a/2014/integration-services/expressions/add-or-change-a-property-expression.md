---
title: Adicionar ou alterar uma expressão de propriedade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d6d12fbe46930818af2b47b59620963d39616e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575981"
---
# <a name="add-or-change-a-property-expression"></a><span data-ttu-id="3904b-102">Adicionar ou alterar uma expressão de propriedade</span><span class="sxs-lookup"><span data-stu-id="3904b-102">Add or Change a Property Expression</span></span>
  <span data-ttu-id="3904b-103">Você pode criar expressões de propriedade para pacotes, tarefas contêineres Loop Foreach, contêineres Loop For, contêineres de Sequência, manipuladores de eventos, gerenciadores de conexões de nível de pacote e projeto, e provedores de logs.</span><span class="sxs-lookup"><span data-stu-id="3904b-103">You can create property expressions for packages, tasks, Foreach Loop containers, For Loop containers, Sequence containers, event handlers, package and project level connection managers, and log providers.</span></span>  
  
 <span data-ttu-id="3904b-104">Para criar ou alterar expressões de propriedade, você pode usar o **Editor de Expressão de Propriedades** ou o **Construtor de Expressões**.</span><span class="sxs-lookup"><span data-stu-id="3904b-104">To create or change property expressions, you can use either the **Property Expressions Editor** or **Expression Builder**.</span></span> <span data-ttu-id="3904b-105">O **Editor de Expressão de Propriedades** pode ser acessados dos editores personalizados que estão disponíveis para tarefas e contêineres ou da janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="3904b-105">The **Property Expressions Editor** can be accessed from either the custom editors that are available for tasks and containers, or from the **Properties** window.</span></span> <span data-ttu-id="3904b-106">O**Construtor de Expressões** pode ser acessado de dentro do **Editor de Expressão de Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3904b-106">**Expression Builder** can be accessed from inside the **Property Expressions Editor**.</span></span> <span data-ttu-id="3904b-107">Embora você possa gravar expressões no **Editor de Expressões de Propriedade** ou no **Construtor de Expressões**, o **Construtor de Expressões** oferece um conjunto gráfico de ferramentas que facilitam a criação de expressões complexas.</span><span class="sxs-lookup"><span data-stu-id="3904b-107">While you can write expressions in either the **Property Expressions Editor** or **Expression Builder**, **Expression Builder** provides a graphical set of tools that makes it simple to build complex expressions.</span></span>  
  
 <span data-ttu-id="3904b-108">Para obter mais informações sobre a sintaxe, operadores e funções que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornece, consulte [Operadores &#40; Expressão SSIS&#41;](operators-ssis-expression.md) e [Funções &#40;Expressão SSIS&#41;](functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3904b-108">To learn more about the syntax, operators, and functions that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides, see [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) and [Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md).</span></span> <span data-ttu-id="3904b-109">Os tópicos sobre cada operador ou função incluem exemplos de como usar o operador ou a função em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="3904b-109">The topic for each operator or function includes examples of using that operator or function in an expression.</span></span> <span data-ttu-id="3904b-110">Para obter exemplos de expressões mais complexas, consulte [Usar expressões de propriedade em pacotes](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="3904b-110">For examples of more complex expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
### <a name="to-create-or-change-a-property-expression"></a><span data-ttu-id="3904b-111">Para criar ou alterar uma expressão de propriedade</span><span class="sxs-lookup"><span data-stu-id="3904b-111">To create or change a property expression</span></span>  
  
1.  <span data-ttu-id="3904b-112">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="3904b-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="3904b-113">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3904b-113">In Solution Explorer, double-click the package to open it, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="3904b-114">Se o item for uma tarefa ou um contêiner, clique duas vezes nele e clique em **Expressões** no editor.</span><span class="sxs-lookup"><span data-stu-id="3904b-114">If the item is a task or a container, double-click the item, and then click **Expressions** in the editor.</span></span>  
  
    -   <span data-ttu-id="3904b-115">Clique com o botão direito do mouse no item e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3904b-115">Right-click the item and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3904b-116">Clique na caixa **Expressões** e, em seguida, clique nas reticências (...).</span><span class="sxs-lookup"><span data-stu-id="3904b-116">Click in the **Expressions** box and then click the ellipsis (...).</span></span>  
  
4.  <span data-ttu-id="3904b-117">No **Editor de Propriedades de Expressões**, selecione uma propriedade na lista **Propriedade** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3904b-117">In the **Property Expressions Editor**, select a property in the **Property** list, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="3904b-118">Digite ou altere a expressão de propriedade diretamente na coluna **Expressão** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3904b-118">Type or change the property expression directly in the **Expression** column, and then click **OK**.</span></span>  
  
         <span data-ttu-id="3904b-119">-ou-</span><span class="sxs-lookup"><span data-stu-id="3904b-119">-or-</span></span>  
  
    -   <span data-ttu-id="3904b-120">Clique nas reticências (...) na linha de expressão da propriedade para abrir o **Construtor de Expressões**.</span><span class="sxs-lookup"><span data-stu-id="3904b-120">Click the ellipsis (...) in the expression row of the property to open the **Expression Builder**.</span></span>  
  
5.  <span data-ttu-id="3904b-121">(Opcional) No **Construtor de Expressões**, execute qualquer uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="3904b-121">(Optional) In the **Expression Builder**, do any of the following tasks:</span></span>  
  
    -   <span data-ttu-id="3904b-122">Para acessar variáveis de sistema e definidas pelo usuário, expanda **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="3904b-122">To access system and user-defined variables, expand **Variables**.</span></span>  
  
    -   <span data-ttu-id="3904b-123">Para acessar as funções, as conversões e os operadores fornecidos pela linguagem de expressão do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , expanda **Funções Matemáticas**, **Funções de Cadeia de Caracteres**, **Funções de Data/Hora**, **Funções NULL**, **Conversões de Tipos**e **Operadores**.</span><span class="sxs-lookup"><span data-stu-id="3904b-123">To access the functions, the casts, and the operators that the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression language provides, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators**.</span></span>  
  
    -   <span data-ttu-id="3904b-124">Para criar ou alterar uma expressão no **Construtor de Expressões**, arraste variáveis, colunas, funções, operadores e conversões até a caixa **Expressão** ou digite a expressão na caixa.</span><span class="sxs-lookup"><span data-stu-id="3904b-124">To build or change an expression in the **Expression Builder**, drag variables, columns, functions, operators, and casts to the **Expression** box, or type the expression in the box.</span></span>  
  
    -   <span data-ttu-id="3904b-125">Para exibir o resultado de avaliação da expressão, clique em **Avaliar Expressão** no **Construtor de Expressões**.</span><span class="sxs-lookup"><span data-stu-id="3904b-125">To view the evaluation result of the expression, click **Evaluate Expression** in the **Expression Builder**.</span></span>  
  
         <span data-ttu-id="3904b-126">Se a expressão não for válida, será exibido um alerta descrevendo os erros de sintaxe na expressão.</span><span class="sxs-lookup"><span data-stu-id="3904b-126">If the expression is not valid, an alert appears that describes the syntax errors in the expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3904b-127">A avaliação de uma expressão não atribui o resultado da avaliação à propriedade.</span><span class="sxs-lookup"><span data-stu-id="3904b-127">Evaluating an expression does not assign the evaluation result to the property.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3904b-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3904b-128">See Also</span></span>  
 <span data-ttu-id="3904b-129">[Expressões do SSIS &#40;Integration Services&#41;](integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-129">[Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="3904b-130">[Usar expressões de propriedade em pacotes](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-130">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="3904b-131">[Pacotes do Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-131">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="3904b-132">[Contêineres do Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-132">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="3904b-133">[Tarefas do Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-133">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="3904b-134">[Manipuladores de eventos do SSIS &#40;Integration Services&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="3904b-135">[Conexões do SSIS &#40;Integration Services&#41;](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="3904b-135">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="3904b-136">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3904b-136">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)  
  
  
