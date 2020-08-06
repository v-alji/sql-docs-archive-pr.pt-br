---
title: Definir as propriedades de uma variável definida pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- modifying variables
- variables [Integration Services], properties
ms.assetid: f98ddbec-f668-4dba-a768-44ac3ae0536f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf53be469e3d377f7efb379f78e85e31b26767b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685834"
---
# <a name="set-the-properties-of-a-user-defined-variable"></a><span data-ttu-id="3241e-102">Definir as propriedades de uma variável definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="3241e-102">Set the Properties of a User-Defined Variable</span></span>
  <span data-ttu-id="3241e-103">Para definir as propriedades de uma variável definida pelo usuário no [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], você pode usar um dos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="3241e-103">To set the properties of a user-defined variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you can use one of the following features:</span></span>  
  
-   <span data-ttu-id="3241e-104">Janela Variáveis.</span><span class="sxs-lookup"><span data-stu-id="3241e-104">Variables window.</span></span>  
  
-   <span data-ttu-id="3241e-105">Janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="3241e-105">Properties window.</span></span> <span data-ttu-id="3241e-106">A janela **Propriedades** lista propriedades para configurar variáveis não disponíveis na janela **Variáveis** : Description, EvaluateAsExpression, Expression, ReadOnly, ValueType e IncludeInDebugDump.</span><span class="sxs-lookup"><span data-stu-id="3241e-106">The **Properties** window lists properties for configuring variables that are not available in the **Variables** window: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType, and IncludeInDebugDump.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3241e-107">O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] também fornece um conjunto de variáveis do sistema cujas propriedades não podem ser atualizadas, com a exceção da propriedade RaiseChangedEvent.</span><span class="sxs-lookup"><span data-stu-id="3241e-107">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] also provides a set of system variables whose properties cannot be updated, with the exception of the RaiseChangedEvent property.</span></span>  
  
 <span data-ttu-id="3241e-108">**Definindo as expressões em variáveis**</span><span class="sxs-lookup"><span data-stu-id="3241e-108">**Setting Expressions on Variables**</span></span>  
  
 <span data-ttu-id="3241e-109">Quando você usa a janela **Propriedades** para definir as expressões em uma variável definida pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="3241e-109">When you use the **Properties** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="3241e-110">O valor de uma variável pode ser definido pela propriedade Value ou Expression.</span><span class="sxs-lookup"><span data-stu-id="3241e-110">The value of a variable can be set by the Value or the Expression property.</span></span> <span data-ttu-id="3241e-111">Por padrão, a Propriedade EvaluateAsExpression é definida como `False` e o valor da variável é definido pela propriedade Value.</span><span class="sxs-lookup"><span data-stu-id="3241e-111">By default, the EvaluateAsExpression property is set to `False` and the value of the variable is set by the Value property.</span></span> <span data-ttu-id="3241e-112">Para usar uma expressão para definir o valor, você deve primeiro definir EvaluateAsExpression como `True` e, em seguida, fornecer uma expressão na Propriedade Expression.</span><span class="sxs-lookup"><span data-stu-id="3241e-112">To use an expression to set the value, you must first set EvaluateAsExpression to `True`, and then provide an expression in the Expression property.</span></span> <span data-ttu-id="3241e-113">A propriedade Value é definida automaticamente como o resultado de avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="3241e-113">The Value property is automatically set to the evaluation result of the expression.</span></span>  
  
-   <span data-ttu-id="3241e-114">A propriedade ValueType contém o tipo de dados do valor na propriedade Value.</span><span class="sxs-lookup"><span data-stu-id="3241e-114">The ValueType property contains the data type of the value in the Value property.</span></span> <span data-ttu-id="3241e-115">Quando Value é definido por uma expressão, ValueType é atualizado automaticamente para um tipo de dados compatível com o resultado da avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="3241e-115">When Value is set by an expression, ValueType is automatically updated to a data type that is compatible with the evaluation result of the expression.</span></span> <span data-ttu-id="3241e-116">Por exemplo, se o valor contiver 0 e a propriedade ValueType contiver **Int32** e você definir Expression como GETDATE (), Value conterá a data e a hora atuais e ValueType será definido como `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="3241e-116">For example, if Value contains 0 and ValueType property contains **Int32** and you then set Expression to GETDATE(), Value contains the current date and time and ValueType is set to `DateTime`.</span></span>  
  
-   <span data-ttu-id="3241e-117">A janela **Propriedades** para a variável fornece acesso à caixa de diálogo **Construtor de Expressões** .</span><span class="sxs-lookup"><span data-stu-id="3241e-117">The **Properties** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="3241e-118">É possível usar essa ferramenta para criar, validar e avaliar expressões.</span><span class="sxs-lookup"><span data-stu-id="3241e-118">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="3241e-119">Para obter mais informações, consulte [Construtor de Expressões](expressions/expression-builder.md) e [Expressões do Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3241e-119">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="3241e-120">Quando você usa a janela **Variáveis** para definir as expressões em uma variável definida pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="3241e-120">When you use the **Variables** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="3241e-121">Para usar uma expressão para definir o valor da variável, primeiro confirme se o tipo de dados da variável é compatível com o resultado da avaliação da expressão e, em seguida, forneça uma expressão na `Expression` coluna da janela **variáveis** .</span><span class="sxs-lookup"><span data-stu-id="3241e-121">To use an expression to set the variable value, first confirm that the variable data type is compatible with the evaluation result of the expression and then provide an expression in the `Expression` column of the **Variables** window.</span></span> <span data-ttu-id="3241e-122">A Propriedade EvaluateAsExpression na janela **Propriedades** é automaticamente definida como `True` .</span><span class="sxs-lookup"><span data-stu-id="3241e-122">The EvaluateAsExpression property in the **Properties** window is automatically set to `True`.</span></span>  
  
-   <span data-ttu-id="3241e-123">Quando você atribui uma expressão a uma variável, um marcador de ícone especial é exibido ao lado da variável.</span><span class="sxs-lookup"><span data-stu-id="3241e-123">When you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="3241e-124">Esse marcador de ícone especial também é exibido ao lado de gerenciadores de conexões e tarefas que têm expressões definidas neles.</span><span class="sxs-lookup"><span data-stu-id="3241e-124">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
-   <span data-ttu-id="3241e-125">A janela **Variáveis** para a variável fornece acesso à caixa de diálogo **Construtor de Expressões** .</span><span class="sxs-lookup"><span data-stu-id="3241e-125">The **Variables** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="3241e-126">É possível usar essa ferramenta para criar, validar e avaliar expressões.</span><span class="sxs-lookup"><span data-stu-id="3241e-126">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="3241e-127">Para obter mais informações, consulte [Construtor de Expressões](expressions/expression-builder.md) e [Expressões do Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3241e-127">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="3241e-128">Na janela **variáveis** e **Propriedades** , se você atribuir uma expressão à variável e `EvaluateAsExpression` estiver definido como `True` , não poderá alterar o tipo de dados Variable.</span><span class="sxs-lookup"><span data-stu-id="3241e-128">In both the **Variables** and **Properties** window, if you assign an expression to the variable, and `EvaluateAsExpression` is set to `True`, you cannot change the variable data type.</span></span>  
  
 <span data-ttu-id="3241e-129">**Definindo o namespace e as propriedades do nome**</span><span class="sxs-lookup"><span data-stu-id="3241e-129">**Setting the Namespace and Name Properties**</span></span>  
  
 <span data-ttu-id="3241e-130">Os valores das propriedades `Name` e `Namespace` devem começar com uma letra de caractere alfabético, conforme definido pelo Unicode Standard 2.0 ou um sublinhado (_).</span><span class="sxs-lookup"><span data-stu-id="3241e-130">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="3241e-131">Os caracteres subsequentes podem ser letras ou números conforme definido no padrão Unicode Standard 2.0 ou o sublinhado (\_).</span><span class="sxs-lookup"><span data-stu-id="3241e-131">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="using-the-variables-window-to-set-properties"></a><span data-ttu-id="3241e-132">Usando a janela Variáveis para definir propriedades</span><span class="sxs-lookup"><span data-stu-id="3241e-132">Using the Variables Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-variables-window"></a><span data-ttu-id="3241e-133">Para definir as propriedades de uma variável usando a janela Variáveis</span><span class="sxs-lookup"><span data-stu-id="3241e-133">To set the properties of a variable by using the Variables window</span></span>  
  
1.  <span data-ttu-id="3241e-134">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="3241e-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3241e-135">No Gerenciador de Soluções, clique com o botão direito do mouse no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="3241e-135">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3241e-136">No menu **SSIS** , clique em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="3241e-136">On the **SSIS** menu, click **Variables**.</span></span>  
  
     <span data-ttu-id="3241e-137">Além disso, você pode exibir a janela **Variáveis** mapeando o comando View.Variables para uma combinação de teclas de sua escolha na página **Teclado** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="3241e-137">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="3241e-138">Opcionalmente, na janela **Variáveis** , clique em **Opções de Grade**e selecione as colunas para serem exibidas na janela **Variáveis** e selecione os filtros para serem aplicados na lista de variáveis.</span><span class="sxs-lookup"><span data-stu-id="3241e-138">Optionally, in the **Variables** window click **Grid Options**, and then select the columns to appear in the **Variables** window and select the filters to apply to the list of variables.</span></span>  
  
5.  <span data-ttu-id="3241e-139">Selecione a variável na lista e, em seguida, atualize os valores no `Name` , **tipo de dados**,,, `Value` `Namespace` **gerar evento de alteração**, **Descrição** e `Expression` colunas.</span><span class="sxs-lookup"><span data-stu-id="3241e-139">Select the variable in the list, and then update values in the `Name`, **Data Type**, `Value`, `Namespace`, **Raise Change Event**, **Description,** and `Expression` columns.</span></span>  
  
6.  <span data-ttu-id="3241e-140">Selecione a variável na lista e, em seguida, clique **Mover Variável** para alterar o escopo.</span><span class="sxs-lookup"><span data-stu-id="3241e-140">Select the variable in the list, and then click **Move Variable** to change the scope.</span></span>  
  
7.  <span data-ttu-id="3241e-141">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3241e-141">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="using-the-properties-window-to-set-properties"></a><span data-ttu-id="3241e-142">Usando a janela Propriedades para definir propriedades</span><span class="sxs-lookup"><span data-stu-id="3241e-142">Using the Properties Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-properties-window"></a><span data-ttu-id="3241e-143">Para definir as propriedades de uma variável usando a janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="3241e-143">To set the properties of a variable by using the Properties window</span></span>  
  
1.  <span data-ttu-id="3241e-144">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="3241e-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3241e-145">No Gerenciador de Soluções, clique com o botão direito do mouse no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="3241e-145">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3241e-146">No menu **Exibir** , clique em **Janela Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3241e-146">On the **View** menu, click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="3241e-147">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique na guia **Explorador de Pacotes** e expanda o nó do Pacote.</span><span class="sxs-lookup"><span data-stu-id="3241e-147">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Package Explorer** tab and expand the Package node.</span></span>  
  
5.  <span data-ttu-id="3241e-148">Para modificar variáveis com escopo no pacote, expanda o nó Variáveis; caso contrário, expanda os Manipuladores de Evento ou os nós Executáveis até que localize o nó Variáveis que contém a variável que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="3241e-148">To modify variables with package scope, expand the Variables node; otherwise, expand the Event Handlers or Executables nodes until you locate the Variables node that contains the variable that you want to modify.</span></span>  
  
6.  <span data-ttu-id="3241e-149">Clique na variável cujas propriedades você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="3241e-149">Click the variable whose properties you want to modify.</span></span>  
  
7.  <span data-ttu-id="3241e-150">Na janela **Propriedades** , atualize as propriedades da variável de leitura/escrita.</span><span class="sxs-lookup"><span data-stu-id="3241e-150">In the **Properties** window, update the read/write variable properties.</span></span> <span data-ttu-id="3241e-151">Algumas propriedades são de leitura/somente leitura para variáveis definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3241e-151">Some properties are read/read only for user-defined variables.</span></span>  
  
     <span data-ttu-id="3241e-152">Para obter mais informações sobre as propriedades, consulte [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="3241e-152">For more information about the properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
8.  <span data-ttu-id="3241e-153">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3241e-153">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3241e-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3241e-154">See Also</span></span>  
 <span data-ttu-id="3241e-155">[Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3241e-155">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="3241e-156">[Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3241e-156">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="3241e-157">Adicionar, excluir, alterar o escopo de uma variável definida pelo usuário em um pacote</span><span class="sxs-lookup"><span data-stu-id="3241e-157">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
