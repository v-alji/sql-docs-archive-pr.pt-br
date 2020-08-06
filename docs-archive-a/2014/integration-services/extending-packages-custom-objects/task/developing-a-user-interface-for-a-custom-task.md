---
title: Desenvolver uma interface do usuário para uma tarefa personalizada | Microsoft Docs
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
- custom user interfaces [Integration Services]
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- custom tasks [Integration Services], user interface
- custom user interface [Integration Services], custom tasks
- user interface [Integration Services]
- SSIS custom tasks, user interface
ms.assetid: 1e940cd1-c5f8-4527-b678-e89ba5dc398a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed96bbc302cba4c207e5ce7b2e4fb4b74fed4ee2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582538"
---
# <a name="developing-a-user-interface-for-a-custom-task"></a><span data-ttu-id="e8844-102">Desenvolvendo uma interface do usuário para uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="e8844-102">Developing a User Interface for a Custom Task</span></span>
  <span data-ttu-id="e8844-103">O modelo de objeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permite que desenvolvedores de tarefas personalizadas criem facilmente uma interface de usuário personalizada para uma tarefa que pode ser integrada e exibida no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8844-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] object model provides custom task developers the ability to easily create a custom user interface for a task that can then be integrated and displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e8844-104">A interface de usuário pode fornecer informações úteis para o usuário no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)], e orientar usuários na configuração correta das propriedades e definições da tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="e8844-104">The user interface can provide helpful information to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and guide users to correctly configure the properties and settings of the custom task.</span></span>  
  
 <span data-ttu-id="e8844-105">O desenvolvimento de uma interface de usuário personalizada para uma tarefa envolve o uso de duas classes importantes.</span><span class="sxs-lookup"><span data-stu-id="e8844-105">Developing a custom user interface for a task involves using two important classes.</span></span> <span data-ttu-id="e8844-106">A tabela a seguir descreve essas classes.</span><span class="sxs-lookup"><span data-stu-id="e8844-106">The following table describes those classes.</span></span>  
  
|<span data-ttu-id="e8844-107">Classe</span><span class="sxs-lookup"><span data-stu-id="e8844-107">Class</span></span>|<span data-ttu-id="e8844-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e8844-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>|<span data-ttu-id="e8844-109">Um atributo que identifica uma tarefa gerenciada e fornece informações em tempo de design através de suas propriedades para controlar como o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] exibe e interage com o objeto.</span><span class="sxs-lookup"><span data-stu-id="e8844-109">An attribute that identifies a managed task, and supplies design-time information through its properties to control how [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer displays and interacts with the object.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>|<span data-ttu-id="e8844-110">Uma interface usada pela tarefa para associar a tarefa com sua interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="e8844-110">An interface used by the task to associate the task with its custom user interface.</span></span>|  
  
 <span data-ttu-id="e8844-111">Esta seção descreve a função do atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> e a interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> quando você está desenvolvendo uma interface de usuário para uma tarefa personalizada e fornece detalhes sobre como criar, integrar, implantar e depurar a tarefa dentro do Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8844-111">This section describes the role of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface when you are developing a user interface for a custom task, and provides details about how to create, integrate, deploy, and debug the task within [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e8844-112">O Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] fornece vários pontos de entrada à interface do usuário para a tarefa: o usuário pode selecionar **Editar** no menu de atalho, clicar duas vezes na tarefa ou clicar no link **Mostrar Editor** no final da folha de propriedades.</span><span class="sxs-lookup"><span data-stu-id="e8844-112">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer provides multiple entry points to the user interface for the task: the user can select **Edit** on the shortcut menu, double-click the task, or click the **Show Editor** link at the bottom of the property sheet.</span></span> <span data-ttu-id="e8844-113">Quando o usuário acessa um desses pontos de entrada, o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] localiza e carrega o assembly que contém a interface de usuário para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-113">When the user accesses one of these entry points, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer locates and loads the assembly that contains the user interface for the task.</span></span> <span data-ttu-id="e8844-114">A interface de usuário para a tarefa é responsável pela criação da caixa de diálogo de propriedades que é exibida para o usuário no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8844-114">The user interface for the task is responsible for creating the properties dialog box that is displayed to the user in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e8844-115">Uma tarefa e sua interface de usuário são entidades separadas.</span><span class="sxs-lookup"><span data-stu-id="e8844-115">A task and its user interface are separate entities.</span></span> <span data-ttu-id="e8844-116">Elas devem ser implementadas em assemblies separados para reduzir o trabalho de localização, implantação e manutenção.</span><span class="sxs-lookup"><span data-stu-id="e8844-116">They should be implemented in separate assemblies to reduce localization, deployment, and maintenance work.</span></span> <span data-ttu-id="e8844-117">Em geral, a DLL da tarefa não carrega, chama ou contém conhecimento sobre sua interface de usuário, com exceção das informações contidas nos valores de atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> codificados na tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-117">The task DLL does not load, call, or generally contain any knowledge of its user interface, except for the information that is contained in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute values coded in the task.</span></span> <span data-ttu-id="e8844-118">Essa é a única forma de associação entre uma tarefa e sua interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="e8844-118">This is the only way that a task and its user interface are associated.</span></span>  
  
## <a name="the-dtstask-attribute"></a><span data-ttu-id="e8844-119">O atributo DtsTask</span><span class="sxs-lookup"><span data-stu-id="e8844-119">The DtsTask Attribute</span></span>  
 <span data-ttu-id="e8844-120">O atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> é incluído no código da classe de tarefa para associar uma tarefa à sua interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="e8844-120">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute is included in the task class code to associate a task with its user interface.</span></span> <span data-ttu-id="e8844-121">O Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] usa as propriedades do atributo para determinar como exibir a tarefa no designer.</span><span class="sxs-lookup"><span data-stu-id="e8844-121">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the properties of the attribute to determine how to display the task in the designer.</span></span> <span data-ttu-id="e8844-122">Essas propriedades incluem o nome a ser exibido e o ícone, caso exista.</span><span class="sxs-lookup"><span data-stu-id="e8844-122">These properties include the name to display and the icon, if any.</span></span>  
  
 <span data-ttu-id="e8844-123">A tabela a seguir descreve as propriedades do atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e8844-123">The following table describes the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute.</span></span>  
  
|<span data-ttu-id="e8844-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e8844-124">Property</span></span>|<span data-ttu-id="e8844-125">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e8844-125">Description</span></span>|  
|--------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>|<span data-ttu-id="e8844-126">Exibe o nome da tarefa na caixa de ferramentas Fluxo de Controle.</span><span class="sxs-lookup"><span data-stu-id="e8844-126">Displays the task name in the Control Flow toolbox.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>|<span data-ttu-id="e8844-127">A descrição da tarefa (herdada do <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span><span class="sxs-lookup"><span data-stu-id="e8844-127">The task description (inherited from <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span></span> <span data-ttu-id="e8844-128">Essa propriedade é mostrada em Dicas de Ferramenta.</span><span class="sxs-lookup"><span data-stu-id="e8844-128">This property is shown in ToolTips.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>|<span data-ttu-id="e8844-129">O ícone exibido no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8844-129">The icon displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.RequiredProductLevel%2A>|<span data-ttu-id="e8844-130">Se ele for usado, defina-o com um dos valores da enumeração <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel>.</span><span class="sxs-lookup"><span data-stu-id="e8844-130">If used, set it to one of the values in the <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel> enumeration.</span></span> <span data-ttu-id="e8844-131">Por exemplo, `RequiredProductLevel = DTSProductLevel.None`.</span><span class="sxs-lookup"><span data-stu-id="e8844-131">For example, `RequiredProductLevel = DTSProductLevel.None`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskContact%2A>|<span data-ttu-id="e8844-132">Mantém informações de contato para ocasiões em que a tarefa exige suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e8844-132">Holds contact information for occasions when the task requires technical support.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskType%2A>|<span data-ttu-id="e8844-133">Atribui um tipo à tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-133">Assigns a type to the task.</span></span>|  
|<span data-ttu-id="e8844-134">Attribute.TypeId</span><span class="sxs-lookup"><span data-stu-id="e8844-134">Attribute.TypeId</span></span>|<span data-ttu-id="e8844-135">Quando implementado em uma classe derivada, obtém um identificador exclusivo para este Atributo.</span><span class="sxs-lookup"><span data-stu-id="e8844-135">When implemented in a derived class, gets a unique identifier for this Attribute.</span></span> <span data-ttu-id="e8844-136">Para obter mais informações, consulte a propriedade `Attribute.TypeID` na biblioteca de classes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8844-136">For more information, see `Attribute.TypeID` property in the .NET Framework Class Library.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>|<span data-ttu-id="e8844-137">O nome de tipo do assembly que é usado pelo Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] para carregar o assembly.</span><span class="sxs-lookup"><span data-stu-id="e8844-137">The type name of the assembly that is used by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to load the assembly.</span></span> <span data-ttu-id="e8844-138">Esta propriedade é usada para localizar o assembly de interface de usuário para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-138">This property is used to find the user interface assembly for the task.</span></span>|  
  
 <span data-ttu-id="e8844-139">O exemplo de código a seguir mostra a aparência do <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>, codificado acima da definição de classe.</span><span class="sxs-lookup"><span data-stu-id="e8844-139">The following code example shows the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> as it would look, coded above the class definition.</span></span>  
  
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
  
 <span data-ttu-id="e8844-140">O Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utiliza a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> do atributo que inclui o nome do assembly, o nome do tipo, a versão, a cultura e o token de chave pública, para localizar o assembly no Cache de Assembly Global (GAC) e carregá-lo para ser usado pelo designer.</span><span class="sxs-lookup"><span data-stu-id="e8844-140">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property of the attribute that includes the assembly name, type name, version, culture, and public key token, to locate the assembly in the Global Assembly Cache (GAC) and load it for use by the designer.</span></span>  
  
 <span data-ttu-id="e8844-141">Depois de o assembly ser localizado, o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utiliza as outras propriedades do atributo para exibir informações adicionais sobre a tarefa no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)], tais como nome, ícone e descrição da tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-141">After the assembly has been located, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the other properties in the attribute to display additional information about the task in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, such as the name, icon, and description of the task.</span></span>  
  
 <span data-ttu-id="e8844-142">As propriedades <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>e <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> especificam como a tarefa é apresentada ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e8844-142">The <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> properties specify how the task is presented to the user.</span></span> <span data-ttu-id="e8844-143">A propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> contém a ID do recurso do ícone inserida no assembly de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e8844-143">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> property contains the resource ID of the icon embedded in the user interface assembly.</span></span> <span data-ttu-id="e8844-144">O designer carrega o recurso de ícone pelo ID do assembly e exibe-o ao lado do nome da tarefa na caixa de ferramentas e na superfície do designer quando a tarefa é adicionada a um pacote.</span><span class="sxs-lookup"><span data-stu-id="e8844-144">The designer loads the icon resource by ID from the assembly, and displays it next to the task name in the toolbox and on the designer surface when the task is added to a package.</span></span> <span data-ttu-id="e8844-145">Se uma tarefa não fornecer um recurso de ícone, o designer usará um ícone padrão para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-145">If a task does not provide an icon resource, the designer uses a default icon for the task.</span></span>  
  
## <a name="the-idtstaskui-interface"></a><span data-ttu-id="e8844-146">The IDTSTaskUI Interface</span><span class="sxs-lookup"><span data-stu-id="e8844-146">The IDTSTaskUI Interface</span></span>  
 <span data-ttu-id="e8844-147">A interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> define a coleção de métodos e propriedades chamados pelo Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] para inicializar e exibir a interface de usuário associada à tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-147">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface defines the collection of methods and properties called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to initialize and display the user interface associated with the task.</span></span> <span data-ttu-id="e8844-148">Quando a interface de usuário para uma tarefa é invocada, o designer chama o método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A>, implementado pela interface de usuário da tarefa quando você o escreveu, e depois fornece as coleções <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e <xref:Microsoft.SqlServer.Dts.Runtime.Connections> da tarefa e pacote, respectivamente, como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e8844-148">When the user interface for a task is invoked, the designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A> method, implemented by the task user interface when you wrote it, and then provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collections of the task and package, respectively, as parameters.</span></span> <span data-ttu-id="e8844-149">Essas coleções são armazenadas localmente e usadas subsequentemente no método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8844-149">These collections are stored locally, and used subsequently in the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method.</span></span>  
  
 <span data-ttu-id="e8844-150">O designer chama o método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> para solicitar a janela que é exibida no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8844-150">The designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method to request the window that is displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e8844-151">A tarefa cria uma instância da janela que contém a interface de usuário para a tarefa e retorna a interface de usuário a ser exibida pelo designer.</span><span class="sxs-lookup"><span data-stu-id="e8844-151">The task creates an instance of the window that contains the user interface for the task, and returns the user interface to the designer for display.</span></span> <span data-ttu-id="e8844-152">Normalmente, são fornecidos os objetos <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e <xref:Microsoft.SqlServer.Dts.Runtime.Connections> para a janela através de um construtor sobrecarregado; assim, eles podem ser usados para configurar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-152">Typically, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> objects are provided to the window through an overloaded constructor so they can be used to configure the task.</span></span>  
  
 <span data-ttu-id="e8844-153">O Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] chama o método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> da tarefa UI para exibir a interface de usuário para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8844-153">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method of the task UI to display the user interface for the task.</span></span> <span data-ttu-id="e8844-154">A interface de usuário da tarefa retorna o formulário Windows desse método e o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] mostra esse formulário como uma caixa de diálogo modal.</span><span class="sxs-lookup"><span data-stu-id="e8844-154">The task user interface returns the Windows form from this method, and [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer shows this form as a modal dialog box.</span></span> <span data-ttu-id="e8844-155">Quando o formulário é fechado, o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] verifica o valor da propriedade `DialogResult` do formulário para determinar se a tarefa foi modificada e se essas modificações devem ser salvas.</span><span class="sxs-lookup"><span data-stu-id="e8844-155">When the form is closed, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer examines the value of the `DialogResult` property of the form to determine whether the task has been modified and if these modifications should be saved.</span></span> <span data-ttu-id="e8844-156">Se o valor da propriedade `DialogResult` for `OK`, o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] chamará os métodos de persistência da tarefa para salvar as alterações; caso contrário, as alterações serão descartadas.</span><span class="sxs-lookup"><span data-stu-id="e8844-156">If the value of the `DialogResult` property is `OK`, the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the persistence methods of the task to save the changes; otherwise, the changes are discarded.</span></span>  
  
 <span data-ttu-id="e8844-157">O exemplo de código a seguir implementa a interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> e pressupõe a existência de uma classe de formulário do Windows nomeada SampleTaskForm.</span><span class="sxs-lookup"><span data-stu-id="e8844-157">The following code sample implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface, and assumes the existence of a Windows form class named SampleTaskForm.</span></span>  
  
```csharp  
using System;  
using System.Windows.Forms;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Design;  
  
namespace Sample  
{  
   public class HelloWorldTaskUI : IDtsTaskUI  
   {  
      TaskHost   taskHost;  
      Connections connections;  
      public void Initialize(TaskHost taskHost, IServiceProvider serviceProvider)  
      {  
         this.taskHost = taskHost;  
         IDtsConnectionService cs = serviceProvider.GetService  
         ( typeof( IDtsConnectionService ) ) as   IDtsConnectionService;   
         this.connections = cs.GetConnections();  
      }  
      public ContainerControl GetView()  
      {  
        return new HelloWorldTaskForm(this.taskHost, this.connections);  
      }  
     public void Delete(IWin32Window parentWindow)  
     {  
     }  
     public void New(IWin32Window parentWindow)  
     {  
     }  
   }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Design  
Imports System.Windows.Forms  
  
Public Class HelloWorldTaskUI  
  Implements IDtsTaskUI  
  
  Dim taskHost As TaskHost  
  Dim connections As Connections  
  
  Public Sub Initialize(ByVal taskHost As TaskHost, ByVal serviceProvider As IServiceProvider) _  
    Implements IDtsTaskUI.Initialize  
  
    Dim cs As IDtsConnectionService  
  
    Me.taskHost = taskHost  
    cs = DirectCast(serviceProvider.GetService(GetType(IDtsConnectionService)), IDtsConnectionService)  
    Me.connections = cs.GetConnections()  
  
  End Sub  
  
  Public Function GetView() As ContainerControl _  
    Implements IDtsTaskUI.GetView  
  
    Return New HelloWorldTaskForm(Me.taskHost, Me.connections)  
  
  End Function  
  
  Public Sub Delete(ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.Delete  
  
  End Sub  
  
  Public Sub [New](ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.[New]  
  
  End Sub  
  
End Class  
```  
  
<span data-ttu-id="e8844-158">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e8844-158">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e8844-159">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="e8844-159">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e8844-160">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="e8844-160">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e8844-161">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="e8844-161">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8844-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8844-162">See Also</span></span>  
 <span data-ttu-id="e8844-163">[Criar uma tarefa personalizada](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="e8844-163">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="e8844-164">[Codificar uma tarefa personalizada](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="e8844-164">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="e8844-165">Desenvolver uma interface do usuário para uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="e8844-165">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
