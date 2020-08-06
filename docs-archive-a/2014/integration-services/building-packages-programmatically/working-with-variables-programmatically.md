---
title: Trabalhar com variáveis programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c903ee6adb8989eaeb93efbe943eca93c73eae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684314"
---
# <a name="working-with-variables-programmatically"></a><span data-ttu-id="f661c-102">Trabalhando com variáveis programaticamente</span><span class="sxs-lookup"><span data-stu-id="f661c-102">Working with Variables Programmatically</span></span>
  <span data-ttu-id="f661c-103">As variáveis são uma forma de definir valores e controlar processos dinamicamente em pacotes, contêineres, tarefas e manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="f661c-103">Variables are a way to dynamically set values and control processes in packages, containers, tasks, and event handlers.</span></span> <span data-ttu-id="f661c-104">As variáveis também podem ser usadas por restrições de precedência para controlar a direção do fluxo de dados para tarefas diferentes.</span><span class="sxs-lookup"><span data-stu-id="f661c-104">Variables can also be used by precedence constraints to control the direction of the flow of data to different tasks.</span></span> <span data-ttu-id="f661c-105">As variáveis têm uma série de usos:</span><span class="sxs-lookup"><span data-stu-id="f661c-105">Variables have a variety of uses:</span></span>

-   <span data-ttu-id="f661c-106">Atualizar propriedades de um pacote em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f661c-106">Update properties of a package at run time.</span></span>

-   <span data-ttu-id="f661c-107">Popule valores de parâmetro para instruções Transact-SQL em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f661c-107">Populate parameter values for Transact-SQL statements at run time.</span></span>

-   <span data-ttu-id="f661c-108">Controlar o fluxo de um loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="f661c-108">Control the flow of a Foreach loop.</span></span> <span data-ttu-id="f661c-109">Para obter mais informações, consulte [Adicionar enumeração a um fluxo de controle](../control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-109">For more information, see [Add Enumeration to a Control Flow](../control-flow/control-flow.md).</span></span>

-   <span data-ttu-id="f661c-110">Controlar uma restrição de precedência por seu uso em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="f661c-110">Control a precedence constraint by its use in an expression.</span></span> <span data-ttu-id="f661c-111">Uma restrição de precedência pode incluir variáveis na definição de restrição.</span><span class="sxs-lookup"><span data-stu-id="f661c-111">A precedence constraint can include variables in the constraint definition.</span></span> <span data-ttu-id="f661c-112">Para obter mais informações, consulte [Adicionar expressões a restrições de precedência](../control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-112">For more information, see [Add Expressions to Precedence Constraints](../control-flow/precedence-constraints.md).</span></span>

-   <span data-ttu-id="f661c-113">Controlar a repetição condicional de um contêiner de Loop For.</span><span class="sxs-lookup"><span data-stu-id="f661c-113">Control the conditional repeat of a For Loop container.</span></span> <span data-ttu-id="f661c-114">Para obter mais informações, consulte [Adicionar iteração a um fluxo de controle](../add-iteration-to-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-114">For more information, see [Add Iteration to a Control Flow](../add-iteration-to-a-control-flow.md).</span></span>

-   <span data-ttu-id="f661c-115">Crie expressões que incluam valores de variáveis.</span><span class="sxs-lookup"><span data-stu-id="f661c-115">Build expressions that include variable values.</span></span>

-   <span data-ttu-id="f661c-116">Você pode criar variáveis personalizadas para todos os tipos de contêineres: pacotes, contêineres **Loop Foreach**, contêineres **Loop For**, contêineres de **Sequência**, TaskHosts e manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="f661c-116">You can create custom variables for all container types: packages, **Foreach Loop** containers, **For Loop** containers, **Sequence** containers, TaskHosts, and event handlers.</span></span> <span data-ttu-id="f661c-117">Para obter mais informações, consulte [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Usar variáveis em pacotes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-117">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>

## <a name="scope"></a><span data-ttu-id="f661c-118">Escopo</span><span class="sxs-lookup"><span data-stu-id="f661c-118">Scope</span></span>
 <span data-ttu-id="f661c-119">Cada contêiner tem sua própria coleção <xref:Microsoft.SqlServer.Dts.Runtime.Variables>.</span><span class="sxs-lookup"><span data-stu-id="f661c-119">Each container has its own <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection.</span></span> <span data-ttu-id="f661c-120">Quando uma nova variável é criada, ela fica dentro do escopo de seu contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="f661c-120">When a new variable is created, it is within the scope of its parent container.</span></span> <span data-ttu-id="f661c-121">Como o contêiner de pacote está no topo da hierarquia de contêineres, as variáveis com escopo de pacote funcionam como variáveis globais e ficam visíveis para todos os contêineres de pacote.</span><span class="sxs-lookup"><span data-stu-id="f661c-121">Because the package container is at the top of the container hierarchy, variables with package scope function like global variables, and are visible to all containers within the package.</span></span> <span data-ttu-id="f661c-122">A coleção de variáveis para o contêiner também pode ser acessada pelos filhos do contêiner através da coleção <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, usando o nome da variável ou o índice da variável na coleção.</span><span class="sxs-lookup"><span data-stu-id="f661c-122">The collection of variables for the container can also be accessed by the children of the container through the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection, by using either the variable name or the variable's index in the collection.</span></span>

 <span data-ttu-id="f661c-123">Como a visibilidade de uma variável tem um escopo de cima para baixo, as variáveis declaradas no nível do pacote são visíveis para todos os contêineres do pacote.</span><span class="sxs-lookup"><span data-stu-id="f661c-123">Because the visibility of a variable is scoped from the top down, variables declared at the package level are visible to all the containers in the package.</span></span> <span data-ttu-id="f661c-124">Portanto, a coleção <xref:Microsoft.SqlServer.Dts.Runtime.Variables> em um contêiner inclui todas as variáveis que pertencem a seu pai além de suas próprias variáveis.</span><span class="sxs-lookup"><span data-stu-id="f661c-124">Therefore, the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection on a container includes all the variables that belong to its parent in addition to its own variables</span></span>

 <span data-ttu-id="f661c-125">Por outro lado, as variáveis contidas em uma tarefa têm escopo e visibilidade limitados e são visíveis somente para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="f661c-125">Conversely, the variables that are contained in a task are limited in scope and visibility, and are only visible to the task.</span></span>

 <span data-ttu-id="f661c-126">Se um pacote executar outros pacotes, as variáveis definidas no escopo do pacote de chamada estarão disponíveis ao pacote chamado.</span><span class="sxs-lookup"><span data-stu-id="f661c-126">If a package runs other packages, the variables defined in the scope of the calling package are available to the called package.</span></span> <span data-ttu-id="f661c-127">A única exceção ocorre quando há uma variável do mesmo nome no pacote chamado.</span><span class="sxs-lookup"><span data-stu-id="f661c-127">The only exception occurs when a same-named variable exists in the called package.</span></span> <span data-ttu-id="f661c-128">Quando essa colisão ocorre, o valor variável no pacote chamado anula o valor do pacote de chamada.</span><span class="sxs-lookup"><span data-stu-id="f661c-128">When this collision occurs, the variable value in the called package overrides the value from the calling package.</span></span> <span data-ttu-id="f661c-129">As variáveis definidas no escopo do pacote chamado não podem ficar disponíveis para o pacote de chamada de novo.</span><span class="sxs-lookup"><span data-stu-id="f661c-129">Variables defined in the scope of the called package are never available back to the calling package.</span></span>

 <span data-ttu-id="f661c-130">O exemplo de código seguinte cria programaticamente uma variável, `myCustomVar`, no escopo do pacote, e itera todas as variáveis visíveis do pacote, imprimindo seu nome, tipo de dados e valor.</span><span class="sxs-lookup"><span data-stu-id="f661c-130">The following code example programmatically creates a variable, `myCustomVar`, at the package scope, and then iterates through all the variables visible to the package, printing their name, data type, and value.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Application app = new Application();
      // Load a sample package that contains a variable that sets the file name.
      Package pkg = app.LoadPackage(
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",
        null);
      Variables pkgVars = pkg.Variables;
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");
      foreach (Variable pkgVar in pkgVars)
      {
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,
          pkgVar.DataType, pkgVar.Value.ToString());
      }
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim app As Application = New Application()
    ' Load a sample package that contains a variable that sets the file name.
    Dim pkg As Package = app.LoadPackage( _
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _
      Nothing)
    Dim pkgVars As Variables = pkg.Variables
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")
    Dim pkgVar As Variable
    For Each pkgVar In pkgVars
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _
        pkgVar.DataType, pkgVar.Value.ToString())
    Next
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="f661c-131">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="f661c-131">**Sample Output:**</span></span>

 `Variable: CancelEvent, Int32, 0`

 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`

 `Variable: CreatorComputerName, String,`

 `Variable: CreatorName, String,`

 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`

 `Variable: FileName, String, Junk`

 `Variable: InteractiveMode, Boolean, False`

 `Variable: LocaleID, Int32, 1033`

 `Variable: MachineName, String, MYCOMPUTERNAME`

 `Variable: myCustomVar, String, 3`

 `Variable: OfflineMode, Boolean, False`

 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`

 `Variable: PackageName, String, DTSPackage1`

 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`

 `Variable: UserName, String, <domain>\<userid>`

 `Variable: VersionBuild, Int32, 198`

 `Variable: VersionComments, String,`

 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`

 `Variable: VersionMajor, Int32, 1`

 `Variable: VersionMinor, Int32, 0`

 <span data-ttu-id="f661c-132">Observe que todas as variáveis com escopo no namespace **System** estão disponíveis para o pacote.</span><span class="sxs-lookup"><span data-stu-id="f661c-132">Notice that all the variables scoped in the **System** namespace are available to the package.</span></span> <span data-ttu-id="f661c-133">Para obter mais informações, consulte [Variáveis de sistema](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-133">For more information, see [System Variables](../system-variables.md).</span></span>

## <a name="namespaces"></a><span data-ttu-id="f661c-134">Namespaces</span><span class="sxs-lookup"><span data-stu-id="f661c-134">Namespaces</span></span>
 <span data-ttu-id="f661c-135">O   [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) fornece dois namespaces padrão em que as variáveis residem; os namespaces **User** e **System**.</span><span class="sxs-lookup"><span data-stu-id="f661c-135">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) provides two default namespaces where variables reside; **User** and **System** namespaces.</span></span> <span data-ttu-id="f661c-136">Por padrão, qualquer variável personalizada criada pelo desenvolvedor é adicionada ao namespace **User**.</span><span class="sxs-lookup"><span data-stu-id="f661c-136">By default, any custom variable created by the developer is added to the **User** namespace.</span></span> <span data-ttu-id="f661c-137">As variáveis de sistema residem no namespace **System**.</span><span class="sxs-lookup"><span data-stu-id="f661c-137">System variables reside in the **System** namespace.</span></span> <span data-ttu-id="f661c-138">Você pode criar namespaces adicionais, além do namespace **User** para manter variáveis personalizadas e você pode alterar o nome do namespace **User**, mas não pode adicionar ou modificar variáveis no namespace **System** nem atribuir variáveis do sistema a outro namespace.</span><span class="sxs-lookup"><span data-stu-id="f661c-138">You can create additional namespaces other than the **User** namespace to hold custom variables, and you can change the name of the **User** namespace, but you cannot add or modify variables in the **System** namespace, or assign system variables to a different namespace.</span></span>

 <span data-ttu-id="f661c-139">As variáveis de sistema que estão disponíveis diferem dependendo do tipo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="f661c-139">The system variables that are available differ depending on the container type.</span></span> <span data-ttu-id="f661c-140">Para uma lista das variáveis de sistema disponíveis para pacotes, contêineres, tarefas e manipuladores de eventos, consulte [System Variables](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-140">For a list of the system variables available to packages, containers, tasks, and event handlers, see [System Variables](../system-variables.md).</span></span>

## <a name="value"></a><span data-ttu-id="f661c-141">Valor</span><span class="sxs-lookup"><span data-stu-id="f661c-141">Value</span></span>
 <span data-ttu-id="f661c-142">O valor de uma variável personalizada pode ser literal ou uma expressão:</span><span class="sxs-lookup"><span data-stu-id="f661c-142">The value of a custom variable can be a literal or an expression:</span></span>

-   <span data-ttu-id="f661c-143">Se você quiser a variável para conter um valor literal, defina o valor de sua propriedade <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="f661c-143">If you want the variable to contain a literal value, set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property.</span></span>

-   <span data-ttu-id="f661c-144">Se você deseja que a variável contenha uma expressão para que você possa usar os resultados da expressão como seu valor, defina a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> da variável como `true` e forneça uma expressão na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="f661c-144">If you want the variable to contain an expression, so that you can use the results of the expression as its value, set the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> property of the variable to `true`, and provide an expression in the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> property.</span></span> <span data-ttu-id="f661c-145">Em tempo de execução, a expressão é avaliada e o resultado da expressão é usado como valor da variável.</span><span class="sxs-lookup"><span data-stu-id="f661c-145">At run time, the expression is evaluated, and the result of the expression is used as the value of the variable.</span></span> <span data-ttu-id="f661c-146">Por exemplo, se a propriedade da expressão de uma variável for `"100 * 2""100 * 2"`, a variável avaliará a um valor de 200.</span><span class="sxs-lookup"><span data-stu-id="f661c-146">For example, if the expression property of a variable is `"100 * 2""100 * 2"`, the variable evaluates to a value of 200.</span></span>

 <span data-ttu-id="f661c-147">Para uma variável, você não pode definir o valor de seu <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> explicitamente.</span><span class="sxs-lookup"><span data-stu-id="f661c-147">For a variable, you cannot explicitly set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span></span> <span data-ttu-id="f661c-148">O valor <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> é inferido do valor inicial atribuído à variável e não pode ser alterado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f661c-148">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> value is inferred from the initial value assigned to the variable, and cannot be changed afterward.</span></span> <span data-ttu-id="f661c-149">Para obter mais informações sobre tipos de dados de variável, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-149">For more information about variable data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="f661c-150">O exemplo de código a seguir cria uma nova variável, define <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> como `true`, atribui a expressão `"100 * 2"` à propriedade da expressão da variável e produz o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="f661c-150">The following code example creates a new variable, sets <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> to `true`, assigns the expression `"100 * 2"` to the expression property of the variable, and then outputs the value of the variable.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package pkg = new Package();
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);
      v100.EvaluateAsExpression = true;
      v100.Expression = "100 * 2";
      Console.WriteLine("Expression for myVar: {0}", 
        v100.Properties["Expression"].GetValue(v100));
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim pkg As Package = New Package
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)
    v100.EvaluateAsExpression = True
    v100.Expression = "100 * 2"
    Console.WriteLine("Expression for myVar: {0}", _
      v100.Properties("Expression").GetValue(v100))
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="f661c-151">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="f661c-151">**Sample Output:**</span></span>

 `Expression for myVar: 100 * 2`

 `Value of myVar: 200`

 <span data-ttu-id="f661c-152">A expressão deve ser uma expressão válida que usa a sintaxe da expressão [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f661c-152">The expression must be a valid expression that uses the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="f661c-153">Literais são permitidos em expressões variáveis, além dos operadores e funções que a sintaxe da expressão fornece, mas as expressões não podem fazer referência a outras variáveis ou colunas.</span><span class="sxs-lookup"><span data-stu-id="f661c-153">Literals are permitted in variable expressions, in addition to the operators and functions that the expression syntax provides, but expressions cannot reference other variables or columns.</span></span> <span data-ttu-id="f661c-154">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-154">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="f661c-155">Arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="f661c-155">Configuration Files</span></span>
 <span data-ttu-id="f661c-156">Se um arquivo de configuração incluir uma variável personalizada, a variável poderá ser atualizada em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f661c-156">If a configuration file includes a custom variable, the variable can be updated at run time.</span></span> <span data-ttu-id="f661c-157">Isso significa que quando o pacote é executado, o valor da variável originalmente no pacote é substituído por um novo valor do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="f661c-157">What this means is that when the package runs, the value of the variable originally in the package is replaced with a new value from the configuration file.</span></span> <span data-ttu-id="f661c-158">Essa técnica de substituição é útil quando um pacote é implantado em vários servidores que requerem valores de variável diferentes.</span><span class="sxs-lookup"><span data-stu-id="f661c-158">This replacement technique is useful when a package is deployed to multiple servers that require different variable values.</span></span> <span data-ttu-id="f661c-159">Por exemplo, uma variável pode especificar o número de vezes que um contêiner **Loop Foreach** repete seu fluxo de trabalho ou então listar os recipientes para os quais um manipulador de eventos envia email quando um erro é gerado ou alterar o número de erros que podem ocorrer antes de o pacote falhar.</span><span class="sxs-lookup"><span data-stu-id="f661c-159">For example, a variable can specify the number of times a **Foreach Loop** container repeats its workflow, or list the recipients that an event handler sends e-mail to when an error is raised, or change the number of errors that can occur before the package fails.</span></span> <span data-ttu-id="f661c-160">Essas variáveis são fornecidas dinamicamente em arquivos de configuração para cada ambiente.</span><span class="sxs-lookup"><span data-stu-id="f661c-160">These variables are dynamically provided in configuration files for each environment.</span></span> <span data-ttu-id="f661c-161">Portanto, somente as variáveis de leitura/gravação são permitidas em arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="f661c-161">Therefore, only variables that are read/write are allowed in configuration files.</span></span> <span data-ttu-id="f661c-162">Para obter mais informações, consulte [Criar configurações de pacote](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f661c-162">For more information, see [Create Package Configurations](../create-package-configurations.md).</span></span>

<span data-ttu-id="f661c-163">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f661c-163">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f661c-164">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="f661c-164">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f661c-165">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="f661c-165">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f661c-166">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="f661c-166">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="f661c-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f661c-167">See Also</span></span>
 <span data-ttu-id="f661c-168">[Integration Services &#40;as variáveis do SSIS&#41;](../integration-services-ssis-variables.md) [usam variáveis em pacotes](../use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="f661c-168">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) [Use Variables in Packages](../use-variables-in-packages.md)</span></span>


