---
title: Criar um enumerador Foreach personalizado | Microsoft Docs
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
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d99970d466aa53d25a80f0600f1fce7819e94956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571456"
---
# <a name="creating-a-custom-foreach-enumerator"></a><span data-ttu-id="c6da6-102">Criando um enumerador Foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="c6da6-102">Creating a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="c6da6-103">As etapas envolvidas na criação de um enumerador foreach personalizado são semelhantes às etapas da criação de qualquer outro objeto personalizado do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c6da6-103">The steps involved in creating a custom foreach enumerator are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c6da6-104">Crie uma classe nova herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="c6da6-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="c6da6-105">Para um enumerador foreach, a classe base é <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="c6da6-105">For a foreach enumerator, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span></span>  
  
-   <span data-ttu-id="c6da6-106">Aplique o atributo que identifica o tipo de objeto para a classe.</span><span class="sxs-lookup"><span data-stu-id="c6da6-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="c6da6-107">Para um enumerador foreach, o atributo é <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c6da6-107">For a foreach enumerator, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span></span>  
  
-   <span data-ttu-id="c6da6-108">Substitua a implementação dos métodos e propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="c6da6-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="c6da6-109">Para um enumerador foreach, o mais importante é o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6da6-109">For a foreach enumerator, the most important is the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
-   <span data-ttu-id="c6da6-110">Opcionalmente, desenvolva uma interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="c6da6-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="c6da6-111">Para um enumerador foreach, isso requer uma classe que implemente a interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI>.</span><span class="sxs-lookup"><span data-stu-id="c6da6-111">For a foreach enumerator, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> interface.</span></span>  
  
 <span data-ttu-id="c6da6-112">Um enumerador personalizado é hospedado pelo contêiner <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="c6da6-112">A custom enumerator is hosted by the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container.</span></span> <span data-ttu-id="c6da6-113">Durante o tempo de execução, o contêiner <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> chama o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> do enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="c6da6-113">At run time, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="c6da6-114">O enumerador personalizado retorna um objeto que implementa a interface `IEnumerable`, como uma `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="c6da6-114">The custom enumerator returns an object that implements the `IEnumerable` interface, such as an `ArrayList`.</span></span> <span data-ttu-id="c6da6-115">O <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> itera em cada elemento da coleção, fornece o valor do elemento atual para o fluxo de controle por meio de uma variável definida pelo usuário e executa o fluxo de controle no contêiner.</span><span class="sxs-lookup"><span data-stu-id="c6da6-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates over each element in the collection, provides the value of the current element to the control flow through a user-defined variable, and executes the control flow in the container.</span></span>  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a><span data-ttu-id="c6da6-116">Guia de Introdução com um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="c6da6-116">Getting Started with a Custom ForEach Enumerator</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="c6da6-117">Criando projetos e classes</span><span class="sxs-lookup"><span data-stu-id="c6da6-117">Creating Projects and Classes</span></span>  
 <span data-ttu-id="c6da6-118">Como todos os enumeradores foreach derivam da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, o primeiro passo para cria enumerador foreach é criar um projeto de biblioteca de classes na linguagem de programação gerenciada de sua preferência e criar uma classe herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="c6da6-118">Because all managed foreach enumerators derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, the first step when you create a custom foreach enumerator is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="c6da6-119">Nessa classe derivada, você substituirá os métodos e propriedades da classe base para implementar sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="c6da6-119">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="c6da6-120">Na mesma solução, crie um segundo projeto de biblioteca de classe para a interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="c6da6-120">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="c6da6-121">Recomenda-se um assembly separado para a interface de usuário para facilitar a implantação pois ela permite que você atualize e reimplante o enumerador foreach ou sua interface de usuário de forma independente.</span><span class="sxs-lookup"><span data-stu-id="c6da6-121">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the foreach enumerator or its user interface independently.</span></span>  
  
 <span data-ttu-id="c6da6-122">Configure ambos os projetos para atribuir os assemblies que serão gerados no momento de compilação usando um arquivo de chave de nome forte.</span><span class="sxs-lookup"><span data-stu-id="c6da6-122">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a><span data-ttu-id="c6da6-123">Aplicando o atributo DtsForEachEnumerator</span><span class="sxs-lookup"><span data-stu-id="c6da6-123">Applying the DtsForEachEnumerator Attribute</span></span>  
 <span data-ttu-id="c6da6-124">Aplique o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> à classe que você criou para identificá-lo como um enumerador foreach.</span><span class="sxs-lookup"><span data-stu-id="c6da6-124">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class that you have created to identify it as a foreach enumerator.</span></span> <span data-ttu-id="c6da6-125">Esse atributo fornece informações de tempo de design como o nome e a descrição do enumerador foreach.</span><span class="sxs-lookup"><span data-stu-id="c6da6-125">This attribute provides design-time information such as the name and description of the foreach enumerator.</span></span> <span data-ttu-id="c6da6-126">A `Name` propriedade aparece na lista suspensa de enumeradores disponíveis na guia **coleção** da caixa de diálogo **Editor de loop foreach** .</span><span class="sxs-lookup"><span data-stu-id="c6da6-126">The `Name` property appears in the dropdown list of available enumerators on the **Collection** tab of the **Foreach Loop Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c6da6-127">Use a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> para vincular o enumerador foreach à sua interface do usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="c6da6-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> property to link the foreach enumerator to its custom user interface.</span></span> <span data-ttu-id="c6da6-128">Para obter o token de chave pública exigido para essa propriedade, você pode usar o **sn.exe -t** para exibir o token de chave pública por meio do arquivo de par de chaves (.snk) a ser usado para assinar o assembly da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c6da6-128">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a><span data-ttu-id="c6da6-129">Compilando, implantando e depurando um enumerador personalizado</span><span class="sxs-lookup"><span data-stu-id="c6da6-129">Building, Deploying, and Debugging a Custom Enumerator</span></span>  
 <span data-ttu-id="c6da6-130">As etapas para compilar, implantar e depurar um enumerador foreach personalizado no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] são muito semelhantes às etapas necessárias para outros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c6da6-130">The steps for building, deploying, and debugging a custom foreach enumerator in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="c6da6-131">Para obter mais informações, consulte [Compilar, implantar e depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c6da6-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="c6da6-132">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c6da6-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c6da6-133">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="c6da6-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c6da6-134">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="c6da6-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c6da6-135">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="c6da6-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6da6-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6da6-136">See Also</span></span>  
 <span data-ttu-id="c6da6-137">[Codificando um enumerador foreach personalizado](coding-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="c6da6-137">[Coding a Custom Foreach Enumerator](coding-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="c6da6-138">Desenvolvendo uma interface do usuário para um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="c6da6-138">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
