---
title: Codificar e depurar a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], debugging
- SSIS Script task, development environment
- SSIS Script task, debugging
- Script task [Integration Services], development environment
- Script task [Integration Services], coding
- debugging [Integration Services], scripts
- VSTA
- SSIS Script task, coding
ms.assetid: 687c262f-fcab-42e8-92ae-e956f3d92d69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f4383469368ac1fe3c70ff82f8c8bb2cf755838
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678863"
---
# <a name="coding-and-debugging-the-script-task"></a><span data-ttu-id="5ff95-102">Codificando e depurando a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-102">Coding and Debugging the Script Task</span></span>
  <span data-ttu-id="5ff95-103">Depois de configurar a tarefa Script no **Editor da Tarefa Script**, você escreve seu código personalizado no ambiente de desenvolvimento da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-103">After configuring the Script task in the **Script Task Editor**, you write your custom code in the Script task development environment.</span></span>

## <a name="script-task-development-environment"></a><span data-ttu-id="5ff95-104">Ambiente de desenvolvimento da tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-104">Script Task Development Environment</span></span>
 <span data-ttu-id="5ff95-105">A tarefa Script usa o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] VSTA (Tools for Applications) como o ambiente de desenvolvimento do script propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="5ff95-105">The Script task uses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) as the development environment for the script itself.</span></span>

 <span data-ttu-id="5ff95-106">O código de Script é escrito em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic ou em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="5ff95-106">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="5ff95-107">Você especifica a linguagem de script configurando a propriedade **ScriptLanguage** no **Editor da Tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="5ff95-107">You specify the script language by setting the **ScriptLanguage** property in the **Script Task Editor**.</span></span> <span data-ttu-id="5ff95-108">Caso prefira usar outra linguagem de programação, você pode desenvolver um assembly personalizado na linguagem de sua escolha e chamar sua funcionalidade a partir do código na tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-108">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script task.</span></span>

 <span data-ttu-id="5ff95-109">O script criado na tarefa Script é armazenado na definição do pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff95-109">The script that you create in the Script task is stored in the package definition.</span></span> <span data-ttu-id="5ff95-110">Não há arquivo de script separado.</span><span class="sxs-lookup"><span data-stu-id="5ff95-110">There is no separate script file.</span></span> <span data-ttu-id="5ff95-111">Portanto, o uso da tarefa Script não afeta a implantação do pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff95-111">Therefore, the use of the Script task does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff95-112">Quando você projeta o pacote e depura o script, o código de script é gravado temporariamente em um arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="5ff95-112">When you design the package and debug the script, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="5ff95-113">Como o fato de armazenar informações confidenciais em um arquivo é um risco em potencial à segurança, recomendamos não incluir informações confidenciais, como senhas, no código de script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-113">Because storing sensitive information in a file is a potential security risk, we recommend that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="5ff95-114">Por padrão, `Option Strict` fica desabilitado no IDE.</span><span class="sxs-lookup"><span data-stu-id="5ff95-114">By default, `Option Strict` is disabled in the IDE.</span></span>

## <a name="script-task-project-structure"></a><span data-ttu-id="5ff95-115">Estrutura do projeto da tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-115">Script Task Project Structure</span></span>
 <span data-ttu-id="5ff95-116">Quando você cria ou modifica o script contido em uma tarefa Script, o VSTA abre um novo projeto vazio ou reabre o projeto existente.</span><span class="sxs-lookup"><span data-stu-id="5ff95-116">When you create or modify the script that is contained in a Script task, VSTA opens an empty new project or reopens the existing project.</span></span> <span data-ttu-id="5ff95-117">A criação desse projeto VSTA não afeta a implantação do pacote, pois o projeto é salvo dentro do arquivo de pacote; a tarefa Script não cria arquivos adicionais.</span><span class="sxs-lookup"><span data-stu-id="5ff95-117">The creation of this VSTA project does not affect the deployment of the package, because the project is saved inside the package file; the Script task does not create additional files.</span></span>

### <a name="project-items-and-classes-in-the-script-task-project"></a><span data-ttu-id="5ff95-118">Itens e classes de projeto no projeto da tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-118">Project Items and Classes in the Script Task Project</span></span>
 <span data-ttu-id="5ff95-119">Por padrão, o projeto da tarefa Script exibido na janela Explorador de Projeto VSTA contém um único item, `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-119">By default, the Script task project displayed in the VSTA Project Explorer window contains a single item, `ScriptMain`.</span></span> <span data-ttu-id="5ff95-120">O item `ScriptMain`, por sua vez, contém uma única classe, também nomeada `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-120">The `ScriptMain` item, in turn, contains a single class, also named `ScriptMain`.</span></span> <span data-ttu-id="5ff95-121">Os elementos de código na classe variam de acordo com a linguagem de programação selecionada para a tarefa Script:</span><span class="sxs-lookup"><span data-stu-id="5ff95-121">The code elements in the class vary depending on the programming language that you selected for the Script task:</span></span>

-   <span data-ttu-id="5ff95-122">Quando a tarefa Script é configurada para a [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] linguagem de programação, a `ScriptMain` classe tem uma sub-rotina pública, `Main` .</span><span class="sxs-lookup"><span data-stu-id="5ff95-122">When the Script task is configured for the [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] programming language, the `ScriptMain` class has a public subroutine, `Main`.</span></span> <span data-ttu-id="5ff95-123">A sub-rotina `ScriptMain.Main` é o método que o runtime chama quando você executa sua tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-123">The `ScriptMain.Main` subroutine is the method that the runtime calls when you run your Script task.</span></span>

     <span data-ttu-id="5ff95-124">Por padrão, o único código na sub-rotina `Main` de um script novo é a linha `Dts.TaskResult = ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-124">By default, the only code in the `Main` subroutine of a new script is the line `Dts.TaskResult = ScriptResults.Success`.</span></span> <span data-ttu-id="5ff95-125">Essa linha informa o runtime em que a tarefa teve êxito em sua operação.</span><span class="sxs-lookup"><span data-stu-id="5ff95-125">This line informs the runtime that the task was successful in its operation.</span></span> <span data-ttu-id="5ff95-126">A `Dts.TaskResult` propriedade é discutida em [retornando resultados da tarefa Script](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="5ff95-126">The `Dts.TaskResult` property is discussed in [Returning Results from the Script Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>

-   <span data-ttu-id="5ff95-127">Quando a tarefa Script é configurada para a linguagem de programação Visual C#, a classe `ScriptMain` tem um método público, `Main`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-127">When the Script task is configured for the Visual C# programming language, the `ScriptMain` class has a public method, `Main`.</span></span> <span data-ttu-id="5ff95-128">O método é chamado quando a tarefa Script é executada.</span><span class="sxs-lookup"><span data-stu-id="5ff95-128">The method is called when the Script task runs.</span></span>

     <span data-ttu-id="5ff95-129">Por padrão, o método `Main` inclui a linha `Dts.TaskResult = (int)ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-129">By default, the `Main` method includes the line `Dts.TaskResult = (int)ScriptResults.Success`.</span></span> <span data-ttu-id="5ff95-130">Essa linha informa o runtime em que a tarefa teve êxito em sua operação.</span><span class="sxs-lookup"><span data-stu-id="5ff95-130">This line informs the runtime that the task was successful in its operation.</span></span>

 <span data-ttu-id="5ff95-131">O item `ScriptMain` pode conter classes que não sejam a classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-131">The `ScriptMain` item can contain classes other than the `ScriptMain` class.</span></span> <span data-ttu-id="5ff95-132">Classes só estão disponíveis à tarefa Script na qual elas residem.</span><span class="sxs-lookup"><span data-stu-id="5ff95-132">Classes are available only to the Script task in which they reside.</span></span>

 <span data-ttu-id="5ff95-133">Por padrão, o item de projeto `ScriptMain` contém o código a seguir gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5ff95-133">By default, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="5ff95-134">O modelo de código também fornece uma visão geral da tarefa Script e informações adicionais sobre como recuperar e manipular objetos SSIS, como variáveis, eventos e conexões.</span><span class="sxs-lookup"><span data-stu-id="5ff95-134">The code template also provides an overview of the Script task, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Task
' Write scripts using Microsoft Visual Basic 2008.
' The ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Runtime.VSTAProxy

<System.AddIn.AddIn("ScriptMain", Version:="1.0", Publisher:="", Description:="")> _
Partial Class ScriptMain

Private Sub ScriptMain_Startup(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Startup

End Sub

Private Sub ScriptMain_Shutdown(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Shutdown
Try
' Unlock variables from the read-only and read-write variable collection properties
If (Dts.Variables.Count <> 0) Then
Dts.Variables.Unlock()
End If
Catch ex As Exception
        End Try
End Sub

Enum ScriptResults
Success = DTSExecResult.Success
Failure = DTSExecResult.Failure
End Enum

' The execution engine calls this method when the task executes.
' To access the object model, use the Dts property. Connections, variables, events,
' and logging features are available as members of the Dts property as shown in the following examples.
'
' To reference a variable, call Dts.Variables("MyCaseSensitiveVariableName").Value
' To post a log entry, call Dts.Log("This is my log text", 999, Nothing)
' To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, True)
'
' To use the connections collection use something like the following:
' ConnectionManager cm = Dts.Connections.Add("OLEDB")
' cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;"
'
' Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.
' 
' To open Help, press F1.

Public Sub Main()
'
' Add your code here
'
Dts.TaskResult = ScriptResults.Success
End Sub

End Class
```

```csharp
/*
   Microsoft SQL Server Integration Services Script Task
   Write scripts using Microsoft Visual C# 2008.
   The ScriptMain is the entry point class of the script.
*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Runtime.VSTAProxy;
using System.Windows.Forms;

namespace ST_1bcfdbad36d94f8ba9f23a10375abe53.csproj
{
    [System.AddIn.AddIn("ScriptMain", Version = "1.0", Publisher = "", Description = "")]
    public partial class ScriptMain
    {
        private void ScriptMain_Startup(object sender, EventArgs e)
        {

        }

        private void ScriptMain_Shutdown(object sender, EventArgs e)
        {
            try
            {
                // Unlock variables from the read-only and read-write variable collection properties
                if (Dts.Variables.Count != 0)
                {
                    Dts.Variables.Unlock();
                }
            }
            catch
            {
            }
        }

        #region VSTA generated code
        private void InternalStartup()
        {
            this.Startup += new System.EventHandler(ScriptMain_Startup);
            this.Shutdown += new System.EventHandler(ScriptMain_Shutdown);
        }
        enum ScriptResults
        {
            Success = DTSExecResult.Success,
            Failure = DTSExecResult.Failure
        };

        #endregion

        /*
The execution engine calls this method when the task executes.
To access the object model, use the Dts property. Connections, variables, events,
and logging features are available as members of the Dts property as shown in the following examples.

To reference a variable, call Dts.Variables["MyCaseSensitiveVariableName"].Value;
To post a log entry, call Dts.Log("This is my log text", 999, null);
To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, true);

To use the connections collection use something like the following:
ConnectionManager cm = Dts.Connections.Add("OLEDB");
cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;";

Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.

To open Help, press F1.
*/

        public void Main()
        {
            // TODO: Add your code here
            Dts.TaskResult = (int)ScriptResults.Success;
        }
    }
```

### <a name="additional-project-items-in-the-script-task-project"></a><span data-ttu-id="5ff95-135">Itens de projeto adicionais no projeto da tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-135">Additional Project Items in the Script Task Project</span></span>
 <span data-ttu-id="5ff95-136">O projeto da tarefa Script pode incluir itens que não sejam o item padrão `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-136">The Script task project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="5ff95-137">Você pode adicionar classes, módulos e arquivos de código ao projeto.</span><span class="sxs-lookup"><span data-stu-id="5ff95-137">You can add classes, modules, and code files to the project.</span></span> <span data-ttu-id="5ff95-138">Você também pode usar pastas para organizar grupos de itens.</span><span class="sxs-lookup"><span data-stu-id="5ff95-138">You can also use folders to organize groups of items.</span></span> <span data-ttu-id="5ff95-139">Todos os itens que você adiciona persistem dentro do pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff95-139">All the items that you add are persisted inside the package.</span></span>

### <a name="references-in-the-script-task-project"></a><span data-ttu-id="5ff95-140">Referências no projeto da tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-140">References in the Script Task Project</span></span>
 <span data-ttu-id="5ff95-141">Você pode adicionar referências a assemblies gerenciados clicando com o botão direito do mouse no projeto da tarefa Script no **Explorador de Projeto** e clicando em **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="5ff95-141">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="5ff95-142">Para obter mais informações, consulte [Referenciar outros assemblies em soluções de script](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="5ff95-142">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff95-143">Você pode exibir as referências do projeto no IDE VSTA no **Modo de Exibição de Classe** ou no **Explorador de Projeto**.</span><span class="sxs-lookup"><span data-stu-id="5ff95-143">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="5ff95-144">É possível abrir qualquer uma dessas janelas no menu **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="5ff95-144">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="5ff95-145">Você pode adicionar uma referência nova no menu **Projeto**, de **Explorador de Projeto** ou de **Modo de Exibição de Classe**.</span><span class="sxs-lookup"><span data-stu-id="5ff95-145">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-task"></a><span data-ttu-id="5ff95-146">Interagindo com o pacote na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-146">Interacting with the Package in the Script Task</span></span>
 <span data-ttu-id="5ff95-147">A tarefa Script usa o objeto global `Dts`, que é uma instância da classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> e de seus membros para interagir com o pacote que a contém e com o runtime do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ff95-147">The Script task uses the global `Dts` object, which is an instance of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, and its members to interact with the containing package and with the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

 <span data-ttu-id="5ff95-148">A tabela a seguir lista os membros públicos principais da classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, que é exposta ao código da tarefa Script através do objeto global `Dts`.</span><span class="sxs-lookup"><span data-stu-id="5ff95-148">The following table lists the principal public members of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, which is exposed to Script task code through the global `Dts` object.</span></span> <span data-ttu-id="5ff95-149">Os tópicos dessa seção apresentam uma discussão detalhada sobre o uso desses membros.</span><span class="sxs-lookup"><span data-stu-id="5ff95-149">The topics in this section discuss the use of these members in more detail.</span></span>

|<span data-ttu-id="5ff95-150">Membro</span><span class="sxs-lookup"><span data-stu-id="5ff95-150">Member</span></span>|<span data-ttu-id="5ff95-151">Finalidade</span><span class="sxs-lookup"><span data-stu-id="5ff95-151">Purpose</span></span>|
|------------|-------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>|<span data-ttu-id="5ff95-152">Fornece acesso a gerenciadores de conexões definidos no pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff95-152">Provides access to connection managers defined in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>|<span data-ttu-id="5ff95-153">Fornece uma interface de eventos para deixar a tarefa Script gerar erros, avisos e mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="5ff95-153">Provides an events interface to let the Script task raise errors, warnings, and informational messages.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>|<span data-ttu-id="5ff95-154">Apresenta uma forma simples de retornar um único objeto ao runtime (além do `TaskResult`) que também pode ser usado para a ramificação de fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5ff95-154">Provides a simple way to return a single object to the runtime (in addition to the `TaskResult`) that can also be used for workflow branching.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>|<span data-ttu-id="5ff95-155">Registra informações tais como o progresso da tarefa e resultados para provedores de log habilitados.</span><span class="sxs-lookup"><span data-stu-id="5ff95-155">Logs information such as task progress and results to enabled log providers.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>|<span data-ttu-id="5ff95-156">Reporta o êxito ou falha da tarefa.</span><span class="sxs-lookup"><span data-stu-id="5ff95-156">Reports the success or failure of the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Transaction%2A>|<span data-ttu-id="5ff95-157">Fornece a transação, caso exista, dentro da qual o contêiner da tarefa está em execução.</span><span class="sxs-lookup"><span data-stu-id="5ff95-157">Provides the transaction, if any, within which the task's container is running.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>|<span data-ttu-id="5ff95-158">Fornece acesso às variáveis listadas nas propriedades de tarefa `ReadOnlyVariables` e `ReadWriteVariables` para uso dentro do script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-158">Provides access to the variables listed in the `ReadOnlyVariables` and `ReadWriteVariables` task properties for use within the script.</span></span>|

 <span data-ttu-id="5ff95-159">A classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> também contém alguns membros públicos que você provavelmente não usará.</span><span class="sxs-lookup"><span data-stu-id="5ff95-159">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class also contains some public members that you will probably not use.</span></span>

|<span data-ttu-id="5ff95-160">Membro</span><span class="sxs-lookup"><span data-stu-id="5ff95-160">Member</span></span>|<span data-ttu-id="5ff95-161">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5ff95-161">Description</span></span>|
|------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>|<span data-ttu-id="5ff95-162">A propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> fornece acesso mais conveniente a variáveis.</span><span class="sxs-lookup"><span data-stu-id="5ff95-162">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property provides more convenient access to variables.</span></span> <span data-ttu-id="5ff95-163">Embora você possa usar o <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, chame explicitamente métodos para bloquear e desbloquear variáveis para leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="5ff95-163">Although you can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must explicitly call methods to lock and unlock variables for reading and writing.</span></span> <span data-ttu-id="5ff95-164">A tarefa Script trata de semânticas de bloqueio quando você usa a propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ff95-164">The Script task handles locking semantics for you when you use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property.</span></span>|

## <a name="debugging-the-script-task"></a><span data-ttu-id="5ff95-165">Depurando a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="5ff95-165">Debugging the Script Task</span></span>
 <span data-ttu-id="5ff95-166">Para depurar o código na sua tarefa Script, defina pelo menos um ponto de interrupção no código e, depois, feche o VSTA IDE para executar o pacote no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ff95-166">To debug the code in your Script task, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5ff95-167">Quando a execução do pacote insere a tarefa Script, o VSTA IDE é reaberto e exibe seu código em modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5ff95-167">When package execution enters the Script task, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="5ff95-168">Depois que a execução atingir seu ponto de interrupção, você poderá examinar valores de variáveis e passar pelo código restante.</span><span class="sxs-lookup"><span data-stu-id="5ff95-168">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!WARNING]
>  <span data-ttu-id="5ff95-169">Você pode depurar a tarefa Script quando executar o pacote no modo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5ff95-169">You can debug the Script task when you run the package in 64-bit mode.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff95-170">Execute o pacote para depurar em sua tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-170">You must execute the package to debug into your Script task.</span></span> <span data-ttu-id="5ff95-171">Se você executar apenas a tarefa individual, os pontos de interrupção no código da tarefa Script serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="5ff95-171">If you execute only the individual task, breakpoints in the Script task code are ignored.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff95-172">Você não pode depurar uma tarefa Script quando executa-a como parte de um pacote filho que é executado a partir de uma tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff95-172">You cannot debug a Script task when you run the Script task as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="5ff95-173">Nessas circunstâncias, os pontos de interrupção definidos na tarefa Script no pacote filho são desconsiderados.</span><span class="sxs-lookup"><span data-stu-id="5ff95-173">Breakpoints that you set in the Script task in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="5ff95-174">Você pode depurar o pacote filho normalmente, executando-o separadamente.</span><span class="sxs-lookup"><span data-stu-id="5ff95-174">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff95-175">Quando você depura um pacote que contém várias tarefas Script, o depurador depura uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="5ff95-175">When you debug a package that contains multiple Script tasks, the debugger debugs one Script task.</span></span> <span data-ttu-id="5ff95-176">O sistema poderá depurar outra tarefa Script se o depurador for concluído, como no caso de um contêiner Loop Foreach ou Loop For.</span><span class="sxs-lookup"><span data-stu-id="5ff95-176">The system can debug another Script task if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

## <a name="external-resources"></a><span data-ttu-id="5ff95-177">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="5ff95-177">External Resources</span></span>

-   <span data-ttu-id="5ff95-178">Entrada de blog, [Problemas de instalação e configuração de VSTA nas instalações de SSIS 2008 e R2](https://go.microsoft.com/fwlink/?LinkId=215661), em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="5ff95-178">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="5ff95-179">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5ff95-179">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5ff95-180">Para obter os downloads, artigos, exemplos e vídeos mais recentes da [!INCLUDE[msCoName](../../../includes/msconame-md.md)], bem como as soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="5ff95-180">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5ff95-181">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="5ff95-181">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5ff95-182">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="5ff95-182">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ff95-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ff95-183">See Also</span></span>
 <span data-ttu-id="5ff95-184">[Fazendo referência a outros assemblies em soluções de script](../referencing-other-assemblies-in-scripting-solutions.md) [Configurando a tarefa script no editor da tarefa Script](configuring-the-script-task-in-the-script-task-editor.md)</span><span class="sxs-lookup"><span data-stu-id="5ff95-184">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) [Configuring the Script Task in the Script Task Editor](configuring-the-script-task-in-the-script-task-editor.md)</span></span>


