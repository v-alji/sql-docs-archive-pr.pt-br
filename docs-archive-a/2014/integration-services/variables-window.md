---
title: Janela Variáveis | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variables.f1
helpviewer_keywords:
- Variables Window dialog box
ms.assetid: f405e5ce-ef69-4c58-8c7d-a3d44dfe9ab0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffd6da67386291c14ebf588da9a1cf8f399214b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575901"
---
# <a name="variables-window"></a><span data-ttu-id="eb9a1-102">Janela Variáveis</span><span class="sxs-lookup"><span data-stu-id="eb9a1-102">Variables Window</span></span>
  <span data-ttu-id="eb9a1-103">Use a janela **Variáveis** para criar e modificar as variáveis definidas pelo usuário e para exibir as variáveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-103">Use the **Variables** window to create and modify user-defined variables and view system variables.</span></span>  
  
 <span data-ttu-id="eb9a1-104">Por padrão, a janela **Variáveis** está localizada abaixo da área **Gerenciadores de Conexões** no Designer SSIS, no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb9a1-104">By default, the **Variables** window is located below the **Connection Managers** area in the SSIS Designer, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="eb9a1-105">Se não aparecer a janela **Variáveis**, clique em **Variáveis** no menu **SSIS** para exibir a janela.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-105">If you don't see the **Variables** window, click **Variables** on the **SSIS** menu to display the window.</span></span>  
  
 <span data-ttu-id="eb9a1-106">Além disso, você pode exibir a janela **Variáveis** mapeando o comando View.Variables para uma combinação de teclas de sua escolha na página **Teclado** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="eb9a1-106">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb9a1-107">Os valores das propriedades `Name` e `Namespace` devem começar com uma letra de caractere alfabético, conforme definido pelo Unicode Standard 2.0 ou um sublinhado (_).</span><span class="sxs-lookup"><span data-stu-id="eb9a1-107">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="eb9a1-108">Os caracteres subsequentes podem ser letras ou números conforme definido no padrão Unicode Standard 2.0 ou o sublinhado (\_).</span><span class="sxs-lookup"><span data-stu-id="eb9a1-108">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb9a1-109">Opções</span><span class="sxs-lookup"><span data-stu-id="eb9a1-109">Options</span></span>  
 <span data-ttu-id="eb9a1-110">**Adicionar Variável**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-110">**Add Variable**</span></span>  
 <span data-ttu-id="eb9a1-111">Adicione uma variável definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-111">Add a user-defined variable.</span></span>  
  
 <span data-ttu-id="eb9a1-112">**Mover variável**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-112">**Move Variable**</span></span>  
 <span data-ttu-id="eb9a1-113">Clique em uma variável na lista e, em seguida, clique **Mover Variável** para alterar o escopo da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-113">Click a variable in the list, and then click **Move Variable** to change the variable scope.</span></span> <span data-ttu-id="eb9a1-114">Na caixa de diálogo **Selecionar Novo Escopo** , selecione o pacote ou um contêiner, tarefa ou manipulador de eventos no pacote, para alterar o escopo variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-114">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
 <span data-ttu-id="eb9a1-115">Para obter mais informações sobre escopo variável, consulte [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="eb9a1-115">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="eb9a1-116">**Excluir Variável**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-116">**Delete Variable**</span></span>  
 <span data-ttu-id="eb9a1-117">Selecione uma variável na lista e clique em **Excluir Variável**.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-117">Select a variable from the list, and then click **Delete Variable**.</span></span>  
  
 <span data-ttu-id="eb9a1-118">**Opções de grade**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-118">**Grid Options**</span></span>  
 <span data-ttu-id="eb9a1-119">Clique para abrir a caixa de diálogo **Opções de Grade Variáveis** em que é possível alterar a seleção de colunas e aplique filtros à janela **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="eb9a1-119">Click to open the **Variable Grid Options** dialog box where you can change the column selection and apply filters to the **Variables** window.</span></span> <span data-ttu-id="eb9a1-120">Para obter mais informações, consulte [Opções de Grade Variáveis](../../2014/integration-services/variable-grid-options.md).</span><span class="sxs-lookup"><span data-stu-id="eb9a1-120">For more information, see [Variable Grid Options](../../2014/integration-services/variable-grid-options.md).</span></span>  
  
 `Name`  
 <span data-ttu-id="eb9a1-121">Exiba o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-121">View the variable name.</span></span> <span data-ttu-id="eb9a1-122">Você pode atualizar o nome para as variáveis definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-122">You can update the name for user-defined variables.</span></span>  
  
 <span data-ttu-id="eb9a1-123">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-123">**Scope**</span></span>  
 <span data-ttu-id="eb9a1-124">Exiba o escopo da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-124">View the scope of the variable.</span></span> <span data-ttu-id="eb9a1-125">Uma variável tem o escopo do pacote inteiro ou o escopo de um contêiner ou tarefa.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-125">A variable has either the scope of the entire package, or the scope of a container or task.</span></span> <span data-ttu-id="eb9a1-126">O escopo da variável deve ser suficiente para que a variável fique visível às demais tarefas ou componentes que requerem a leitura ou a definição de seu valor.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-126">The scope of the variable must be sufficient so that the variable is visible to any other tasks or components that need to read or set its value.</span></span>  
  
 <span data-ttu-id="eb9a1-127">Você pode alterar o escopo clicando na variável e, em seguida, clicando em **Mover Variável** na janela **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="eb9a1-127">You can change the scope by clicking the variable and then clicking **Move Variable** in the **Variables** window.</span></span>  
  
 <span data-ttu-id="eb9a1-128">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-128">**Data Type**</span></span>  
 <span data-ttu-id="eb9a1-129">Exiba o tipo de dados da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-129">View the data type of the variable.</span></span> <span data-ttu-id="eb9a1-130">Você pode selecionar um tipo de dados na lista para as variáveis definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-130">You can select a data type from the list for user-defined variables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb9a1-131">Se você atribuir uma expressão à variável, não poderá alterar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-131">If you assign an expression to the variable, you cannot change the data type.</span></span>  
  
 <span data-ttu-id="eb9a1-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-132">**Value**</span></span>  
 <span data-ttu-id="eb9a1-133">Exiba o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-133">View the variable value.</span></span> <span data-ttu-id="eb9a1-134">Você pode atualizar o valor da variável para as variáveis definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-134">You can update the value for user-defined variables.</span></span> <span data-ttu-id="eb9a1-135">Este valor pode ser literal ou uma expressão e pode ser uma cadeia de caracteres com várias linhas.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-135">This value can be a literal or an expression, and the value can be a multi-line string.</span></span> <span data-ttu-id="eb9a1-136">Para atribuir uma expressão à variável, clique no botão de reticências ao lado da coluna **Expressão** na janela **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="eb9a1-136">To assign an expression to the variable, click the ellipse button that is next to the **Expression** column in the **Variables** window.</span></span>  
  
 `Namespace`  
 <span data-ttu-id="eb9a1-137">Exiba o nome do namespace.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-137">View the namespace name.</span></span> <span data-ttu-id="eb9a1-138">As variáveis definidas pelo usuário são inicialmente criadas no namespace do **usuário** , mas você pode alterar o nome do namespace no `Namespace` campo.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-138">User-defined variables are initially created in the **User** namespace, but you can change the namespace name in the `Namespace` field.</span></span> <span data-ttu-id="eb9a1-139">Para exibir esta coluna, clique em **Opções de Grade**.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-139">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="eb9a1-140">**Elevar Evento de Alteração**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-140">**Raise Change Event**</span></span>  
 <span data-ttu-id="eb9a1-141">Indique se precisa gerar um evento `OnVariableValueChanged` quando o valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-141">Indicate whether to raise the `OnVariableValueChanged` event when a value changes.</span></span> <span data-ttu-id="eb9a1-142">Você pode atualizar o valor para as variáveis do sistema e as definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-142">You can update the value for user-defined and system variables.</span></span> <span data-ttu-id="eb9a1-143">Por padrão, a janela **Variáveis** não lista esta coluna.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-143">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="eb9a1-144">Para exibir esta coluna, clique em **Opções de Grade**.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-144">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="eb9a1-145">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-145">**Description**</span></span>  
 <span data-ttu-id="eb9a1-146">Exiba a descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-146">View the variable description.</span></span> <span data-ttu-id="eb9a1-147">Você pode alterar a descrição para as variáveis definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-147">You can change the description for user-defined variables.</span></span> <span data-ttu-id="eb9a1-148">Por padrão, a janela **Variáveis** não lista esta coluna.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-148">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="eb9a1-149">Para exibir esta coluna, clique em **Opções de Grade**.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-149">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="eb9a1-150">**Expression**</span><span class="sxs-lookup"><span data-stu-id="eb9a1-150">**Expression**</span></span>  
 <span data-ttu-id="eb9a1-151">Exiba a expressão atribuída à variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-151">View the expression assigned to the variable.</span></span> <span data-ttu-id="eb9a1-152">Para atribuir uma expressão, clique botão de reticências.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-152">To assign an expression, click the ellipse button.</span></span>  
  
 <span data-ttu-id="eb9a1-153">Se você atribui uma expressão a uma variável, um marcador de ícone especial é exibido ao lado da variável.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-153">If you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="eb9a1-154">Esse marcador de ícone especial também é exibido ao lado de gerenciadores de conexões e tarefas que têm expressões definidas neles.</span><span class="sxs-lookup"><span data-stu-id="eb9a1-154">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9a1-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb9a1-155">See Also</span></span>  
 <span data-ttu-id="eb9a1-156">[Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="eb9a1-156">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="eb9a1-157">[Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="eb9a1-157">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="eb9a1-158">[Integration Services &#40;expressões&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="eb9a1-158">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="eb9a1-159">Gerar arquivos de despejo para execução de pacote</span><span class="sxs-lookup"><span data-stu-id="eb9a1-159">Generating Dump Files for Package Execution</span></span>](troubleshooting/generating-dump-files-for-package-execution.md)  
  
  
