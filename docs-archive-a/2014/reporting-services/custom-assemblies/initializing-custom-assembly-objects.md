---
title: Inicializando objetos de assembly personalizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- initializing custom assemblies [Reporting Services]
- custom assemblies [Reporting Services], initializing
- OnInit method
ms.assetid: 26fd74dc-d02f-40f7-aeb3-50ce05e9e6b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2aba0bd8b71b26651067a2370728dcdff521ceaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573797"
---
# <a name="initializing-custom-assembly-objects"></a><span data-ttu-id="98242-102">Inicializando objetos assembly personalizados</span><span class="sxs-lookup"><span data-stu-id="98242-102">Initializing Custom Assembly Objects</span></span>
  <span data-ttu-id="98242-103">Em alguns casos, talvez você precise inicializar valores de propriedade e de campo em suas classes assembly personalizadas ao instanciá-las.</span><span class="sxs-lookup"><span data-stu-id="98242-103">In some cases, you may need to initialize property and field values in your custom assembly classes when you instantiate them.</span></span> <span data-ttu-id="98242-104">É mais provável que você tenha de inicializar as suas classes personalizadas com valores disponíveis a partir de coleções de objetos globais do relatório.</span><span class="sxs-lookup"><span data-stu-id="98242-104">You will most likely need to initialize your custom classes with values available to you from the report's global object collections.</span></span> <span data-ttu-id="98242-105">Faça isso substituindo o método **OnInit** do objeto **Code** de um relatório.</span><span class="sxs-lookup"><span data-stu-id="98242-105">You do this by overriding the **OnInit** method of the **Code** object of a report.</span></span> <span data-ttu-id="98242-106">Para acessar **OnInit**, use o elemento **Code** da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="98242-106">To access **OnInit**, use the **Code** element of the report definition.</span></span> <span data-ttu-id="98242-107">Existem duas técnicas para a inicialização de valores de propriedade e de campo das classes em um assembly personalizado que você pretende usar em seu relatório: você pode declarar e criar uma nova instância da classe usando **OnInit** ou chamar um método disponível publicamente usando **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="98242-107">There are two techniques for initializing property or field values of the classes in a custom assembly that you plan to use in your report: You can either declare and create a new instance of your class using **OnInit**, or you can call a publicly available method using **OnInit**.</span></span>  
  
## <a name="global-object-collections-and-initialization"></a><span data-ttu-id="98242-108">Coleções e inicialização de objetos globais</span><span class="sxs-lookup"><span data-stu-id="98242-108">Global Object Collections and Initialization</span></span>  
 <span data-ttu-id="98242-109">Várias coleções estão disponíveis para que você inicialize suas variáveis de classe personalizadas.</span><span class="sxs-lookup"><span data-stu-id="98242-109">Several collections are available to you for initializing your custom class variables.</span></span> <span data-ttu-id="98242-110">Use as coleções **Globals** e **User**.</span><span class="sxs-lookup"><span data-stu-id="98242-110">You can use the **Globals** and **User** collections.</span></span> <span data-ttu-id="98242-111">As coleções **Parameters**, **Fields** e **ReportItems** não estão disponíveis no ponto do ciclo de vida do relatório quando o método **OnInit** é invocado.</span><span class="sxs-lookup"><span data-stu-id="98242-111">The **Parameters**, **Fields** and **ReportItems** collections are not available to you at the point in the report lifecycle when the **OnInit** method is invoked.</span></span> <span data-ttu-id="98242-112">Para usar as coleções compartilhadas, **Globals** ou **User**, você precisa incluir a referência de objeto **Report**.</span><span class="sxs-lookup"><span data-stu-id="98242-112">To use the shared collections, **Globals** or **User**, you need to include the **Report** object reference.</span></span> <span data-ttu-id="98242-113">Por exemplo, para inicializar a classe personalizada com base no idioma atual do usuário que está acessando o relatório, o elemento **Code** poderá ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="98242-113">For example, to initialize your custom class based on the current language of the user accessing the report, your **Code** element might look like the following:</span></span>  
  
```  
<Code>  
   Dim m_myClass As MyClass  
  
   Protected Overrides Sub OnInit()  
      m_myClass = new MyClass(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="98242-114">Uma forma de inicializar os valores de propriedade e de campo de uma classe como mostrado anteriormente é declarar a sua classe e criar uma nova instância dela chamando um construtor substituído.</span><span class="sxs-lookup"><span data-stu-id="98242-114">One way to initialize the property and field values of a class as shown previously is to declare your class and create a new instance of it by calling an overridden constructor.</span></span>  
  
 <span data-ttu-id="98242-115">Outra forma de inicializar os valores de propriedade e de campo das classes em assemblies personalizados é chamar um método disponível publicamente definido com base no método **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="98242-115">Another way to initialize the property and field values of the classes in your custom assemblies is to call a publicly available method that you define from the **OnInit** method.</span></span> <span data-ttu-id="98242-116">Primeiro, você precisa adicionar um nome de instância para a sua classe ao arquivo de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="98242-116">You first need to add an instance name for your class in the report definition file.</span></span> <span data-ttu-id="98242-117">Depois de adicionar a referência de assembly apropriada e o nome de instância, você poderá chamar o seu método de inicialização para inicializar valores de propriedade e de campo para a sua classe.</span><span class="sxs-lookup"><span data-stu-id="98242-117">Once you have added the appropriate assembly reference and instance name, you can call your initialization method to initialize property and field values for your class.</span></span> <span data-ttu-id="98242-118">O método **OnInit** poderá ser parecido com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98242-118">Your **OnInit** method might look like the following:</span></span>  
  
```  
<Code>  
   Protected Overrides Sub OnInit()  
      m_myClass.MyInitializationMethod(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="98242-119">Para obter mais informações sobre como adicionar um nome de instância e uma referência de assembly à classe personalizada, consulte [Adicionar uma referência de assembly a um relatório &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98242-119">For more information about adding an assembly reference and instance name for your custom class, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span></span>  
  
 <span data-ttu-id="98242-120">Para obter mais informações sobre coleções de objetos globais, consulte [Coleções internas em expressões &#40;Construtor de Relatórios e SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="98242-120">For more information about the global object collections, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98242-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98242-121">See Also</span></span>  
 [<span data-ttu-id="98242-122">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="98242-122">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
