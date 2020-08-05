---
title: Conectar tarefas programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- constraints [Integration Services]
ms.assetid: 23668e88-cef4-4009-a9cf-38e607eab7a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5aeeb70ed5741cc7372fdfc63e637fd53d932f91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572647"
---
# <a name="connecting-tasks-programmatically"></a><span data-ttu-id="ea32d-102">Conectando tarefas programaticamente</span><span class="sxs-lookup"><span data-stu-id="ea32d-102">Connecting Tasks Programmatically</span></span>
  <span data-ttu-id="ea32d-103">Uma restrição de precedência, representada no modelo de objeto pela classe <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, estabelece a ordem na qual objetos <xref:Microsoft.SqlServer.Dts.Runtime.Executable> são executados em um pacote.</span><span class="sxs-lookup"><span data-stu-id="ea32d-103">A precedence constraint, represented in the object model by the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> class, establishes the order in which <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects run in a package.</span></span> <span data-ttu-id="ea32d-104">A restrição de precedência permite que a execução dos contêineres e tarefas de um pacote dependam do resultado da execução de uma tarefa ou contêiner anterior.</span><span class="sxs-lookup"><span data-stu-id="ea32d-104">The precedence constraint allows the execution of the containers and tasks in a package to be dependent on the result of the execution of a previous task or container.</span></span> <span data-ttu-id="ea32d-105">Restrições de precedência são estabelecidas entre pares de objetos <xref:Microsoft.SqlServer.Dts.Runtime.Executable> através da chamada ao método <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> da coleção <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> no objeto contêiner.</span><span class="sxs-lookup"><span data-stu-id="ea32d-105">Precedence constraints are established between pairs of <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects by calling the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> collection on the container object.</span></span> <span data-ttu-id="ea32d-106">Depois de criar uma restrição entre dois objetos executáveis, defina a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> para estabelecer os critérios para executar o segundo executável definido na restrição.</span><span class="sxs-lookup"><span data-stu-id="ea32d-106">After you create a constraint between two executable objects, you set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property to establish the criteria for executing the second executable defined in the constraint.</span></span>  
  
 <span data-ttu-id="ea32d-107">Você pode usar uma restrição e uma expressão em uma única restrição de precedência, dependendo do valor especificado para a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A>, conforme descrito na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="ea32d-107">You can use both a constraint and an expression in a single precedence constraint, depending on the value that you specify for the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A> property, as described in the following table:</span></span>  
  
|<span data-ttu-id="ea32d-108">Valor da propriedade EvalOp</span><span class="sxs-lookup"><span data-stu-id="ea32d-108">Value of the EvalOp property</span></span>|<span data-ttu-id="ea32d-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ea32d-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Constraint>|<span data-ttu-id="ea32d-110">Especifica que o resultado de execução determina se o contêiner ou tarefa restrita é executada.</span><span class="sxs-lookup"><span data-stu-id="ea32d-110">Specifies that the execution outcome determines whether the constrained container or task runs.</span></span> <span data-ttu-id="ea32d-111">Defina a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> com o valor desejado da enumeração <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="ea32d-111">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> to the desired value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Expression>|<span data-ttu-id="ea32d-112">Especifica que o valor de uma expressão determina se o contêiner ou tarefa restrita é executada.</span><span class="sxs-lookup"><span data-stu-id="ea32d-112">Specifies that the value of an expression determines whether the constrained container or task runs.</span></span> <span data-ttu-id="ea32d-113">Defina a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span><span class="sxs-lookup"><span data-stu-id="ea32d-113">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionAndConstraint>|<span data-ttu-id="ea32d-114">Especifica que o resultado de restrição deve ocorrer e que a expressão deve ser avaliada para determinar se o contêiner ou tarefa restrita deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="ea32d-114">Specifies that the constraint outcome must occur and the expression must evaluate for the constrained container or task to run.</span></span> <span data-ttu-id="ea32d-115">Defina as propriedades <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, e defina sua propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> como `true`.</span><span class="sxs-lookup"><span data-stu-id="ea32d-115">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `true`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionOrConstraint>|<span data-ttu-id="ea32d-116">Especifica que o resultado de restrição deve ocorrer, ou que a expressão deve ser avaliada, para determinar se o contêiner ou tarefa restrita deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="ea32d-116">Specifies that either the constraint outcome must occur, or the expression must evaluate, for the constrained container or task to run.</span></span> <span data-ttu-id="ea32d-117">Defina as propriedades <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, e defina sua propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> como `false`.</span><span class="sxs-lookup"><span data-stu-id="ea32d-117">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `false`.</span></span>|  
  
 <span data-ttu-id="ea32d-118">O exemplo de código a seguir demonstra a adição de duas tarefas a um pacote.</span><span class="sxs-lookup"><span data-stu-id="ea32d-118">The following code sample demonstrates adding two tasks to a package.</span></span> <span data-ttu-id="ea32d-119">Um <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> é criado entre elas, impedindo a execução da segunda tarefa antes do término da primeira.</span><span class="sxs-lookup"><span data-stu-id="ea32d-119">A <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> is created between them that prevents the second task from running until the first task finishes.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
  
      // Add a File System task.  
      Executable eFileTask1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost1 = eFileTask1 as TaskHost;  
  
      // Add a second File System task.  
      Executable eFileTask2 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost2 = eFileTask2 as TaskHost;  
  
      // Put a precedence constraint between the tasks.  
      // Set the constraint to specify that the second File System task cannot run  
      // until the first File System task finishes.  
      PrecedenceConstraint pcFileTasks =   
        p.PrecedenceConstraints.Add((Executable)thFileHost1, (Executable)thFileHost2);  
      pcFileTasks.Value = DTSExecResult.Completion;  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task.  
    Dim eFileTask1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost1 As TaskHost = CType(eFileTask1, TaskHost)  
  
    ' Add a second File System task.  
    Dim eFileTask2 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost2 As TaskHost = CType(eFileTask2, TaskHost)  
  
    ' Put a precedence constraint between the tasks.  
    ' Set the constraint to specify that the second File System task cannot run  
    ' until the first File System task finishes.  
    Dim pcFileTasks As PrecedenceConstraint = _  
      p.PrecedenceConstraints.Add(CType(thFileHost1, Executable), CType(thFileHost2, Executable))  
    pcFileTasks.Value = DTSExecResult.Completion  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="ea32d-120">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ea32d-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ea32d-121">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="ea32d-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ea32d-122">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="ea32d-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ea32d-123">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="ea32d-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea32d-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea32d-124">See Also</span></span>  
 [<span data-ttu-id="ea32d-125">Adicionando a tarefa Fluxo de Dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="ea32d-125">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
  
