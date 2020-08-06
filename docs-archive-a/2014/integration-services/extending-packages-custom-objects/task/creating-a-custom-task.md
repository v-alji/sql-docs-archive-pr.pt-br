---
title: Criar uma tarefa personalizada | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom tasks [Integration Services], creating
ms.assetid: 42965c09-1782-4cdb-9ce1-216af4c23e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f752acad7a442a8e0aad2d24e94938c14195a35d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575224"
---
# <a name="creating-a-custom-task"></a><span data-ttu-id="907e5-102">Criando uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="907e5-102">Creating a Custom Task</span></span>
  <span data-ttu-id="907e5-103">As etapas envolvidas na criação de uma tarefa personalizada são semelhantes às etapas de criação de qualquer outro objeto personalizado do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="907e5-103">The steps involved in creating a custom task are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="907e5-104">Crie uma classe nova herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="907e5-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="907e5-105">Para uma tarefa, a classe base é [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span><span class="sxs-lookup"><span data-stu-id="907e5-105">For a task, the base class is [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span></span>  
  
-   <span data-ttu-id="907e5-106">Aplique o atributo que identifica o tipo de objeto para a classe.</span><span class="sxs-lookup"><span data-stu-id="907e5-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="907e5-107">Para uma tarefa, o atributo é <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="907e5-107">For a task, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span></span>  
  
-   <span data-ttu-id="907e5-108">Substitua a implementação dos métodos e propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="907e5-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="907e5-109">Para uma tarefa, isso inclui os métodos <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="907e5-109">For a task, these include the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
-   <span data-ttu-id="907e5-110">Opcionalmente, desenvolva uma interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="907e5-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="907e5-111">Para uma tarefa, isso requer uma classe que implementa a interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>.</span><span class="sxs-lookup"><span data-stu-id="907e5-111">For a task, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface.</span></span>  
  
## <a name="getting-started-with-a-custom-task"></a><span data-ttu-id="907e5-112">Guia de introdução com uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="907e5-112">Getting Started with a Custom Task</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="907e5-113">Criando projetos e classes</span><span class="sxs-lookup"><span data-stu-id="907e5-113">Creating Projects and Classes</span></span>  
 <span data-ttu-id="907e5-114">Como todas as tarefas gerenciadas derivam da classe base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), a primeira etapa ao criar uma tarefa personalizada é criar um projeto de biblioteca de classes na linguagem de programação gerenciada de sua preferência e criar uma classe herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="907e5-114">Because all managed tasks derive from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, the first step when you create a custom task is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="907e5-115">Nessa classe derivada, você substituirá os métodos e propriedades da classe base para implementar sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="907e5-115">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="907e5-116">Na mesma solução, crie um segundo projeto de biblioteca de classe para a interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="907e5-116">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="907e5-117">Recomenda-se um assembly separado para a interface de usuário para facilitar a implantação pois ela permite que você atualize e reimplante o gerenciador de conexões ou sua interface de usuário de forma independente.</span><span class="sxs-lookup"><span data-stu-id="907e5-117">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="907e5-118">Configure ambos os projetos para atribuir os assemblies que serão gerados no momento de compilação usando um arquivo de chave de nome forte.</span><span class="sxs-lookup"><span data-stu-id="907e5-118">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtstask-attribute"></a><span data-ttu-id="907e5-119">Aplicando o atributo DtsTask</span><span class="sxs-lookup"><span data-stu-id="907e5-119">Applying the DtsTask Attribute</span></span>  
 <span data-ttu-id="907e5-120">Aplique o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> à classe que você criou para identificar isso como uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="907e5-120">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class that you have created to identify it as a task.</span></span> <span data-ttu-id="907e5-121">Esse atributo fornece informações de tempo de design como o nome, a descrição e o tipo da tarefa.</span><span class="sxs-lookup"><span data-stu-id="907e5-121">This attribute provides design-time information such as the name, description, and task type of the task.</span></span>  
  
 <span data-ttu-id="907e5-122">Use a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> para vincular a tarefa à sua interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="907e5-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property to link the task to its custom user interface.</span></span> <span data-ttu-id="907e5-123">Para obter o token de chave pública exigido para essa propriedade, você pode usar o **sn.exe -t** para exibir o token de chave pública por meio do arquivo de par de chaves (.snk) a ser usado para assinar o assembly da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="907e5-123">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
## <a name="building-deploying-and-debugging-a-custom-task"></a><span data-ttu-id="907e5-124">Compilando, implantando e depurando uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="907e5-124">Building, Deploying, and Debugging a Custom Task</span></span>  
 <span data-ttu-id="907e5-125">As etapas para compilar, implantar e depurar uma tarefa personalizada no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] são semelhantes às etapas necessárias para outros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="907e5-125">The steps for building, deploying, and debugging a custom task in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="907e5-126">Para obter mais informações, consulte [Compilar, implantar e depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="907e5-126">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="907e5-127">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="907e5-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="907e5-128">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="907e5-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="907e5-129">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="907e5-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="907e5-130">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="907e5-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907e5-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="907e5-131">See Also</span></span>  
 <span data-ttu-id="907e5-132">[Criar uma tarefa personalizada](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="907e5-132">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="907e5-133">[Codificar uma tarefa personalizada](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="907e5-133">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="907e5-134">Desenvolver uma interface do usuário para uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="907e5-134">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
