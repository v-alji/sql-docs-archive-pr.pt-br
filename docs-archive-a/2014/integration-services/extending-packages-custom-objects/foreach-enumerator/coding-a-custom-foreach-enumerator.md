---
title: Codificar um enumerador Foreach personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services], coding
ms.assetid: 279cf6de-d06f-40e7-b8ca-569310449f36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b7e6c16124f4682dbdc98f602417bf8f68ce099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571458"
---
# <a name="coding-a-custom-foreach-enumerator"></a><span data-ttu-id="7bdcb-102">Codificando um enumerador Foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="7bdcb-102">Coding a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="7bdcb-103">Depois de criar uma classe que herda da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> e aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> a essa classe, você deve substituir a implementação das propriedades e dos métodos da classe base para fornecer sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="7bdcb-104">Para obter um exemplo de funcionamento de um enumerador personalizado, consulte [Desenvolvendo uma interface do usuário para um enumerador ForEach personalizado](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span><span class="sxs-lookup"><span data-stu-id="7bdcb-104">For a working sample of a custom enumerator, see [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span></span>  
  
## <a name="initializing-the-enumerator"></a><span data-ttu-id="7bdcb-105">Inicializando o enumerador</span><span class="sxs-lookup"><span data-stu-id="7bdcb-105">Initializing the Enumerator</span></span>  
 <span data-ttu-id="7bdcb-106">Você substitui o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> para referências aos gerenciadores de conexões definidos no pacote, e para referências de cache à interface de eventos que você pode usar para gerar erros, avisos e mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-106">You can override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> method to cache references to the connection managers defined in the package, and to cache references to the events interface that you can use to raise errors, warnings, and informational messages.</span></span>  
  
## <a name="validating-the-enumerator"></a><span data-ttu-id="7bdcb-107">Validando o enumerador</span><span class="sxs-lookup"><span data-stu-id="7bdcb-107">Validating the Enumerator</span></span>  
 <span data-ttu-id="7bdcb-108">Você substitui o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> para verificar se o enumerador está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-108">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> method to verify that the enumerator is correctly configured.</span></span> <span data-ttu-id="7bdcb-109">Se o método retornar `Failure`, o enumerador e o pacote contendo o enumerador não serão executados.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-109">If the method returns `Failure`, the enumerator and the package that contains the enumerator will not be executed.</span></span> <span data-ttu-id="7bdcb-110">A implementação desse método é específica de cada enumerador, mas se o enumerador depender de objetos <xref:Microsoft.SqlServer.Dts.Runtime.Variable> ou <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, adicione código para verificar se esses objetos existem nas coleções fornecidas para o método.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-110">The implementation of this method is specific to each enumerator, but if the enumerator relies on <xref:Microsoft.SqlServer.Dts.Runtime.Variable> or <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects, you should add code to verify that these objects exist in the collections that are provided to the method.</span></span>  
  
 <span data-ttu-id="7bdcb-111">O exemplo de código a seguir demonstra uma implementação de <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> que verifica uma variável especificada em uma propriedade do enumerador.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-111">The following code example demonstrates an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> that checks for a variable specified in a property of the enumerator.</span></span>  
  
```csharp  
private string variableNameValue;  
  
public string VariableName  
{  
    get{ return this.variableNameValue; }  
    set{ this.variableNameValue = value; }  
}  
  
public override DTSExecResult Validate(Connections connections, VariableDispenser variableDispenser, IDTSInfoEvents infoEvents, IDTSLogging log)  
{  
    if (!variableDispenser.Contains(this.variableNameValue))  
    {  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + this.variableNameValue + " does not exist in the collection.", "", 0);  
            return DTSExecResult.Failure;  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Private variableNameValue As String  
  
Public Property VariableName() As String  
    Get   
         Return Me.variableNameValue  
    End Get  
    Set (ByVal Value As String)   
         Me.variableNameValue = value  
    End Set  
End Property  
  
Public Overrides Function Validate(ByVal connections As Connections, ByVal variableDispenser As VariableDispenser, ByVal infoEvents As IDTSInfoEvents, ByVal log As IDTSLogging) As DTSExecResult  
    If Not variableDispenser.Contains(Me.variableNameValue) Then  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + Me.variableNameValue + " does not exist in the collection.", "", 0)  
            Return DTSExecResult.Failure  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
## <a name="returning-the-collection"></a><span data-ttu-id="7bdcb-112">Retornando a coleção</span><span class="sxs-lookup"><span data-stu-id="7bdcb-112">Returning the Collection</span></span>  
 <span data-ttu-id="7bdcb-113">Durante execução, o contêiner <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> chama o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> do enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-113">During execution, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="7bdcb-114">Nesse método, o enumerador cria, preenche e retorna sua coleção de itens.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-114">In this method, the enumerator creates and populates its collection of items, and then returns the collection.</span></span> <span data-ttu-id="7bdcb-115">O <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> itera os itens na coleção e executa seu fluxo de controle para cada item da coleção.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates the items in the collection, and executes its control flow for each item in the collection.</span></span>  
  
 <span data-ttu-id="7bdcb-116">O exemplo a seguir mostra uma implementação de <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> que retorna uma matriz de inteiros aleatórios.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-116">The following example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> that returns an array of random integers.</span></span>  
  
```csharp  
public override object GetEnumerator()  
{  
    ArrayList numbers = new ArrayList();  
  
    Random randomNumber = new Random(DateTime.Now);  
  
    for( int x=0; x < 100; x++ )  
        numbers.Add( randomNumber.Next());  
  
    return numbers;  
}  
```  
  
```vb  
Public Overrides Function GetEnumerator() As Object  
    Dim numbers As ArrayList =  New ArrayList()   
  
    Dim randomNumber As Random =  New Random(DateTime.Now)   
  
        Dim x As Integer  
        For  x = 0 To  100- 1  Step  x + 1  
        numbers.Add(randomNumber.Next())  
        Next  
  
    Return numbers  
End Function  
```  
  
<span data-ttu-id="7bdcb-117">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7bdcb-117">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7bdcb-118">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="7bdcb-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7bdcb-119">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="7bdcb-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7bdcb-120">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="7bdcb-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bdcb-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7bdcb-121">See Also</span></span>  
 <span data-ttu-id="7bdcb-122">[Criando um enumerador foreach personalizado](creating-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="7bdcb-122">[Creating a Custom Foreach Enumerator](creating-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="7bdcb-123">Desenvolvendo uma interface do usuário para um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="7bdcb-123">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
