---
title: Criar um gerenciador de conexões personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857efebbe311e5510e15cae9e78a2b424559ded7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685853"
---
# <a name="creating-a-custom-connection-manager"></a><span data-ttu-id="109a5-102">Criando um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="109a5-102">Creating a Custom Connection Manager</span></span>
  <span data-ttu-id="109a5-103">As etapas a seguir para criar um gerenciador de conexões personalizado são semelhantes às etapas de criação de qualquer outro objeto personalizado do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="109a5-103">The steps that you must follow to create a custom connection manager are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="109a5-104">Crie uma classe nova herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="109a5-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="109a5-105">Para um gerenciador de conexões, a classe base é <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="109a5-105">For a connection manager, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span></span>  
  
-   <span data-ttu-id="109a5-106">Aplique o atributo que identifica o tipo de objeto para a classe.</span><span class="sxs-lookup"><span data-stu-id="109a5-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="109a5-107">Para um gerenciador de conexões, o atributo é <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="109a5-107">For a connection manager, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
-   <span data-ttu-id="109a5-108">Substitua a implementação dos métodos e propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="109a5-108">Override the implementation of the methods and properties of the base class.</span></span> <span data-ttu-id="109a5-109">Para um gerenciador de conexões, eles incluem a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> e os métodos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="109a5-109">For a connection manager, these include the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods.</span></span>  
  
-   <span data-ttu-id="109a5-110">Opcionalmente, desenvolva uma interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="109a5-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="109a5-111">Para um gerenciador de conexões, isso requer uma classe que implemente a interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>.</span><span class="sxs-lookup"><span data-stu-id="109a5-111">For a connection manager, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="109a5-112">A maioria das tarefas, fontes e destinos incluídos no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funcionam somente com tipos específicos de gerenciadores de conexões internos.</span><span class="sxs-lookup"><span data-stu-id="109a5-112">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="109a5-113">Portanto, esses exemplos não podem ser testados com as tarefas e componentes internos.</span><span class="sxs-lookup"><span data-stu-id="109a5-113">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="getting-started-with-a-custom-connection-manager"></a><span data-ttu-id="109a5-114">Guia de Introdução com um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="109a5-114">Getting Started with a Custom Connection Manager</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="109a5-115">Criando projetos e classes</span><span class="sxs-lookup"><span data-stu-id="109a5-115">Creating Projects and Classes</span></span>  
 <span data-ttu-id="109a5-116">Como todos os gerenciadores de conexões gerenciados derivam da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, o primeiro passo para criar um gerenciador de conexões personalizado é criar um projeto de biblioteca de classes na linguagem de programação gerenciada de sua preferência e criar uma classe herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="109a5-116">Because all managed connection managers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, the first step when you create a custom connection manager is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="109a5-117">Nessa classe derivada, você substituirá os métodos e propriedades da classe base para implementar sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="109a5-117">In this derived class, you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="109a5-118">Na mesma solução, crie um segundo projeto de biblioteca de classe para a interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="109a5-118">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="109a5-119">Recomenda-se um assembly separado para a interface do usuário para facilitar a implantação, pois ela permite que você atualize e implemente de novo o gerenciador de conexões ou sua interface do usuário de forma independente.</span><span class="sxs-lookup"><span data-stu-id="109a5-119">A separate assembly for the user interface is recommended for ease of deployment because it lets you update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="109a5-120">Configure ambos os projetos para atribuir os assemblies que serão gerados no momento de compilação usando um arquivo de chave de nome forte.</span><span class="sxs-lookup"><span data-stu-id="109a5-120">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsconnection-attribute"></a><span data-ttu-id="109a5-121">Aplicando o atributo DtsConnection</span><span class="sxs-lookup"><span data-stu-id="109a5-121">Applying the DtsConnection Attribute</span></span>  
 <span data-ttu-id="109a5-122">Aplique o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> à classe que você criou para identificá-la como um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="109a5-122">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class that you have created to identify it as a connection manager.</span></span> <span data-ttu-id="109a5-123">Esse atributo fornece informações de tempo de design como o nome, a descrição e o tipo de conexão do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="109a5-123">This attribute provides design-time information such as the name, description, and connection type of the connection manager.</span></span> <span data-ttu-id="109a5-124">As <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> `Description` Propriedades e correspondem ao **tipo** e às `Description` colunas exibidas na caixa de diálogo **Adicionar Gerenciador de conexões SSIS** , que é exibida ao configurar conexões para um pacote no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="109a5-124">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> and `Description` properties correspond to the **Type** and `Description` columns displayed in the **Add SSIS Connection Manager** dialog box, which is displayed when configuring connections for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="109a5-125">Use a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> para vincular o gerenciador de conexões à sua interface do usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="109a5-125">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property to link the connection manager to its custom user interface.</span></span> <span data-ttu-id="109a5-126">Para obter o token de chave pública exigido para essa propriedade, você pode usar o **sn.exe -t** para exibir o token de chave pública por meio do arquivo de par de chaves (.snk) a ser usado para assinar o assembly da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="109a5-126">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a><span data-ttu-id="109a5-127">Compilando, implantando e depurando um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="109a5-127">Building, Deploying, and Debugging a Custom Connection Manager</span></span>  
 <span data-ttu-id="109a5-128">As etapas para compilar, implantar e depurar um gerenciador de conexões personalizado no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] são semelhantes às etapas para outros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="109a5-128">The steps for building, deploying, and debugging a custom connection manager in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps for other types of custom objects.</span></span> <span data-ttu-id="109a5-129">Para obter mais informações, consulte [Compilar, implantar e depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="109a5-129">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="109a5-130">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="109a5-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="109a5-131">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="109a5-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="109a5-132">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="109a5-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="109a5-133">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="109a5-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="109a5-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="109a5-134">See Also</span></span>  
 <span data-ttu-id="109a5-135">[Codificando um Gerenciador de conexões personalizado](coding-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="109a5-135">[Coding a Custom Connection Manager](coding-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="109a5-136">Desenvolvendo uma interface do usuário para um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="109a5-136">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
