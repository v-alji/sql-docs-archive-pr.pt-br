---
title: Acessar assemblies personalizados por meio de expressões | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- expressions [Reporting Services], custom assemblies
- static member calls
- instance member calls [Reporting Services]
- calling class members
- custom assemblies [Reporting Services], expressions
ms.assetid: 917c4d47-1a95-4f54-98b1-e8cb2165d90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99497de0456d90fd522ce27c62fd5aa1b812059f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568345"
---
# <a name="accessing-custom-assemblies-through-expressions"></a><span data-ttu-id="010bb-102">Acessando assemblies personalizados por meio de expressões</span><span class="sxs-lookup"><span data-stu-id="010bb-102">Accessing Custom Assemblies Through Expressions</span></span>
  <span data-ttu-id="010bb-103">Depois de criar um assembly personalizado, disponibilize-o para o Designer de Relatórios ou para o servidor de relatório, de ter adicionado a política de segurança apropriada, e de ter adicionado uma referência ao seu assembly personalizado à sua definição de relatório, você poderá acessar os membros das classes do seu assembly usando expressões de relatório.</span><span class="sxs-lookup"><span data-stu-id="010bb-103">Once you have created a custom assembly, made it available to Report Designer or the report server, added the appropriate security policy, and added a reference to your custom assembly in your report definition, you can access the members of the classes in your assembly using report expressions.</span></span> <span data-ttu-id="010bb-104">Para consultar o código personalizado em uma expressão, você deve chamar o membro de uma classe dentro do assembly.</span><span class="sxs-lookup"><span data-stu-id="010bb-104">To refer to custom code in an expression, you must call the member of a class within the assembly.</span></span> <span data-ttu-id="010bb-105">A maneira de fazer isso depende do método ser estático ou baseado em instância.</span><span class="sxs-lookup"><span data-stu-id="010bb-105">How you do this depends on whether the method is static or instance-based.</span></span>  
  
## <a name="calling-static-members-from-a-report-definition-file"></a><span data-ttu-id="010bb-106">Chamando membros estáticos de um arquivo de definição de relatório</span><span class="sxs-lookup"><span data-stu-id="010bb-106">Calling Static Members from a Report Definition File</span></span>  
 <span data-ttu-id="010bb-107">Os membros estáticos pertencem à própria classe ou tipo e não a um objeto instanciado.</span><span class="sxs-lookup"><span data-stu-id="010bb-107">Static members belong to the class or type itself and not to an instantiated object.</span></span> <span data-ttu-id="010bb-108">Esses membros podem ser acessados por sua chamada direta a partir da classe.</span><span class="sxs-lookup"><span data-stu-id="010bb-108">These members can be accessed by directly calling them from the class.</span></span> <span data-ttu-id="010bb-109">Você deve usar os membros estáticos para chamar funções personalizadas em um relatório sempre que possível, porque eles têm um desempenho melhor.</span><span class="sxs-lookup"><span data-stu-id="010bb-109">You should use static members to call custom functions in a report whenever possible, because static members perform best.</span></span> <span data-ttu-id="010bb-110">Para chamar um membro estático, você precisa referenciá-lo como uma expressão que usa a forma =*Namespace.Class.Method*.</span><span class="sxs-lookup"><span data-stu-id="010bb-110">To call a static member, you need to reference it as an expression that takes the form =*Namespace.Class.Method*.</span></span>  
  
#### <a name="to-call-static-members"></a><span data-ttu-id="010bb-111">Para chamar membros estáticos</span><span class="sxs-lookup"><span data-stu-id="010bb-111">To call static members</span></span>  
  
-   <span data-ttu-id="010bb-112">Para chamar um membro estático, defina a sua expressão como o nome totalmente qualificado do membro, que inclui o namespace, o nome da classe e o nome do membro.</span><span class="sxs-lookup"><span data-stu-id="010bb-112">To call a static member, set your expression equal to the fully qualified name of the member, which includes the namespace, class name, and member name.</span></span> <span data-ttu-id="010bb-113">O exemplo a seguir chama o método **ToGBP**, que converte o valor do campo **StandardCost** de dólares para libras esterlinas e o exibe em um relatório:</span><span class="sxs-lookup"><span data-stu-id="010bb-113">The following example calls the **ToGBP** method, which converts the **StandardCost** field value from dollars to pounds sterling and displays it in a report:</span></span>  
  
    ```  
    =CurrencyConversion.DollarCurrencyConversion.ToGBP(Fields!StandardCost.Value)  
    ```  
  
### <a name="important-information-regarding-static-fields-and-properties"></a><span data-ttu-id="010bb-114">Informações importantes sobre campos estáticos e propriedades</span><span class="sxs-lookup"><span data-stu-id="010bb-114">Important Information Regarding Static Fields and Properties</span></span>  
 <span data-ttu-id="010bb-115">Atualmente, todos os relatórios são executados no mesmo domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="010bb-115">Currently, all reports are executed in the same application domain.</span></span> <span data-ttu-id="010bb-116">Isso significa que relatórios com dados específicos do usuário e estáticos exibem esses dados a outras instâncias do mesmo relatório.</span><span class="sxs-lookup"><span data-stu-id="010bb-116">This means that reports with user-specific, static data expose this data to other instances of the same report.</span></span> <span data-ttu-id="010bb-117">Essa condição pode fazer com que os dados estáticos de um usuário estejam disponíveis a todos os usuários que executam um relatório específico no momento.</span><span class="sxs-lookup"><span data-stu-id="010bb-117">This condition might make it possible for the static data of one user to be available to all users currently running a particular report.</span></span> <span data-ttu-id="010bb-118">Por esse motivo, é altamente recomendável que você não use campos estáticos ou propriedades em assemblies personalizados ou no elemento **Code**. Em vez disso, use campos de instância ou propriedades em seus relatórios.</span><span class="sxs-lookup"><span data-stu-id="010bb-118">For this reason, it is highly recommended that you not use static fields or properties in custom assemblies or in the **Code** element; instead, use instance fields or properties in your reports.</span></span> <span data-ttu-id="010bb-119">Os métodos estáticos ainda poderão ser usados, já que não armazenam estado ou dados.</span><span class="sxs-lookup"><span data-stu-id="010bb-119">Static methods can still be used, because they do not store state or data.</span></span>  
  
## <a name="calling-instance-members-from-a-report-definition-file"></a><span data-ttu-id="010bb-120">Chamando membros de instância de um arquivo de definição de relatório</span><span class="sxs-lookup"><span data-stu-id="010bb-120">Calling Instance Members from a Report Definition File</span></span>  
 <span data-ttu-id="010bb-121">Se o seu assembly personalizado contém membros de instância que você precisa acessar em uma definição de relatório, adicione um nome de instância para a sua classe ao relatório.</span><span class="sxs-lookup"><span data-stu-id="010bb-121">If your custom assembly contains instance members that you need to access in a report definition, you must add an instance name for your class to the report.</span></span> <span data-ttu-id="010bb-122">Você pode adicionar um nome de instância a uma classe usando a guia **Código** da caixa de diálogo **Propriedades do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="010bb-122">You can add an instance name for a class using the **Code** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="010bb-123">Para obter mais informações sobre adição de instâncias de classes a um relatório, consulte [Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="010bb-123">For more information about adding instances of classes to a report, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="010bb-124">Para chamar um membro estático, você precisa fazer referência a ele como uma expressão que usa o formato = código *. InstanceName. Method*.</span><span class="sxs-lookup"><span data-stu-id="010bb-124">To call a static member, you need to reference it as an expression that takes the form = Code *.InstanceName.Method*.</span></span>  
  
#### <a name="to-call-instance-members"></a><span data-ttu-id="010bb-125">Para chamar membros de instância</span><span class="sxs-lookup"><span data-stu-id="010bb-125">To call instance members</span></span>  
  
-   <span data-ttu-id="010bb-126">Para chamar um membro de instância de um assembly personalizado, referencie a palavra-chave **Code** seguida pelo nome de instância e o método.</span><span class="sxs-lookup"><span data-stu-id="010bb-126">To call an instance member of a custom assembly, you must reference the **Code** keyword followed by the instance name and the method.</span></span> <span data-ttu-id="010bb-127">O exemplo a seguir chama um método de instância **ToEUR** que converte o valor do campo **StandardCost** de dólares para euros e o exibe em um relatório:</span><span class="sxs-lookup"><span data-stu-id="010bb-127">The following example calls an instance method **ToEUR** which converts the **StandardCost** field value from dollars to euros and displays it in a report:</span></span>  
  
    ```  
    =Code.m_myDollarCoversion.ToEUR(Fields!StandardCost.Value)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="010bb-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="010bb-128">See Also</span></span>  
 [<span data-ttu-id="010bb-129">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="010bb-129">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
