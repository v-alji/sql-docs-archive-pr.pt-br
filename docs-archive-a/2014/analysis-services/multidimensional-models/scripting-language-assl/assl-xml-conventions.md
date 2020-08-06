---
title: ASSL convenções XML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- whitespace [Analysis Services Scripting Language]
- trailing whitespace
- XSD data types [Analysis Services Scripting Language]
- inheritance [Analysis Services Scripting Language]
- cardinality [Analysis Services Scripting Language]
- white space [Analysis Services Scripting Language]
- ASSL, XML conventions
- defaults [Analysis Services Scripting Language]
- leading whitespace
- Analysis Services Scripting Language, XML conventions
- XML [Analysis Services Scripting Language]
- hierarchies [Analysis Services Scripting Language]
- inherited defaults [Analysis Services Scripting Language]
ms.assetid: bce4edad-4420-41ce-9672-8c00c5c0dec6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b70742b07fd6450b01cf205147a05f40c4b6121
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683744"
---
# <a name="assl-xml-conventions"></a><span data-ttu-id="2c381-102">Convenções de XML do ASSL</span><span class="sxs-lookup"><span data-stu-id="2c381-102">ASSL XML Conventions</span></span>
  <span data-ttu-id="2c381-103">A ASSL (Analysis Services Scripting Language) representa a hierarquia de objetos como um conjunto de tipos de elementos, cada um definindo os elementos filhos que podem conter.</span><span class="sxs-lookup"><span data-stu-id="2c381-103">Analysis Services Scripting Language (ASSL) represents the hierarchy of objects as a set of element types, each of which defines the child elements they can contain.</span></span>  
  
 <span data-ttu-id="2c381-104">Para representar a hierarquia de objeto, a ASSL usa as seguintes convenções XML:</span><span class="sxs-lookup"><span data-stu-id="2c381-104">To represent the object hierarchy, ASSL uses the following XML conventions:</span></span>  
  
-   <span data-ttu-id="2c381-105">Todos os objetos e propriedades são representados como elementos, exceto os atributos XML padrão, como ' XML: lang '.</span><span class="sxs-lookup"><span data-stu-id="2c381-105">All objects and properties are represented as elements, except for standard XML attributes such as 'xml:lang'.</span></span>  
  
-   <span data-ttu-id="2c381-106">Os nomes de elemento e os valores de enumeração seguem a convenção de nomenclatura do Microsoft .NET Framework de combinação de maiúsculas e minúsculas de Pascal sem sublinhados.</span><span class="sxs-lookup"><span data-stu-id="2c381-106">Both element names and enumeration values follow the Microsoft .NET Framework naming convention of Pascal casing with no underscores.</span></span>  
  
-   <span data-ttu-id="2c381-107">Os valores de maiúsculas e minúsculas é preservado.</span><span class="sxs-lookup"><span data-stu-id="2c381-107">The case of all values is preserved.</span></span> <span data-ttu-id="2c381-108">Os valores para enumerações também apresentam diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2c381-108">Values for enumerations are also case-sensitive.</span></span>  
  
 <span data-ttu-id="2c381-109">Além dessa lista de convenções, o Analysis Services segue também certas convenções relativas a cardinalidade, a herança, a espaço em branco, a tipos de dados e a valores padrão.</span><span class="sxs-lookup"><span data-stu-id="2c381-109">In addition to this list of conventions, Analysis Services also follows certain conventions regarding cardinality, inheritance, whitespace, data types, and default values.</span></span>  
  
## <a name="cardinality"></a><span data-ttu-id="2c381-110">Cardinalidade</span><span class="sxs-lookup"><span data-stu-id="2c381-110">Cardinality</span></span>  
 <span data-ttu-id="2c381-111">Quando um elemento tiver uma cardinalidade maior do que 1, haverá uma coleção de elementos XML que encapsula esse elemento.</span><span class="sxs-lookup"><span data-stu-id="2c381-111">When an element has a cardinality that is greater than 1, there is an XML element collection that encapsulates this element.</span></span> <span data-ttu-id="2c381-112">O nome de coleção usa a forma plural dos elementos contidos na coleção.</span><span class="sxs-lookup"><span data-stu-id="2c381-112">The name of collection uses the plural form of the elements contained in the collection.</span></span> <span data-ttu-id="2c381-113">Por exemplo, o fragmento XML a seguir representa a coleção `Dimensions` em um elemento `Database`:</span><span class="sxs-lookup"><span data-stu-id="2c381-113">For example, the following XML fragment represents the `Dimensions` collection within a `Database` element:</span></span>  
  
 `<Database>`  
  
 `...`  
  
 `<Dimensions>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `</Dimensions>`  
  
 `</Database>`  
  
 ``  
  
 <span data-ttu-id="2c381-114">A ordem na qual os elementos aparecem não tem importância.</span><span class="sxs-lookup"><span data-stu-id="2c381-114">The order in which elements appear is unimportant.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="2c381-115">Herança</span><span class="sxs-lookup"><span data-stu-id="2c381-115">Inheritance</span></span>  
 <span data-ttu-id="2c381-116">A herança é usada quando existem objetos distintos com sobrepostos mas significativamente diferentes de propriedades.</span><span class="sxs-lookup"><span data-stu-id="2c381-116">Inheritance is used when there are distinct objects that have overlapping but significantly different sets of properties.</span></span> <span data-ttu-id="2c381-117">Exemplos desses objetos sobrepostos mas distintos são cubos virtuais, cubos vinculados e cubos normais.</span><span class="sxs-lookup"><span data-stu-id="2c381-117">Examples of such overlapping but distinct objects are virtual cubes, linked cubes, and regular cubes.</span></span> <span data-ttu-id="2c381-118">Para objetos sobrepostos mas distintos, o Analysis Services usa o atributo `type` padrão do Namespace da Instância XML para indicar a herança.</span><span class="sxs-lookup"><span data-stu-id="2c381-118">For overlapping but distinct object, Analysis Services uses the standard `type` attribute from the XML Instance Namespace to indicate the inheritance.</span></span> <span data-ttu-id="2c381-119">Por exemplo, o fragmento XML a seguir mostra como o atributo `type` identifica se um elemento `Cube` herda de um cubo normal ou de um cubo virtual:</span><span class="sxs-lookup"><span data-stu-id="2c381-119">For example, the following XML fragment shows how the `type` attribute identifies whether a `Cube` element inherits from a regular cube or from a virtual cube:</span></span>  
  
 `<Cubes>`  
  
 `<Cube xsi:type="RegularCube">`  
  
 `<Name>Sales</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `<Cube xsi:type="VirtualCube">`  
  
 `<Name>SalesAndInventory</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `</Cubes>`  
  
 ``  
  
 <span data-ttu-id="2c381-120">Geralmente, a herança não é usada quando vários tipos têm uma propriedade com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="2c381-120">Inheritance is generally not used when multiple types have a property of the same name.</span></span> <span data-ttu-id="2c381-121">Por exemplo, as propriedades `Name` e `ID` aparecem em muitos elementos, mas não foram elevadas a um tipo abstrato.</span><span class="sxs-lookup"><span data-stu-id="2c381-121">For example, the `Name` and `ID` properties appear on many elements, but these properties have not been promoted to an abstract type.</span></span>  
  
## <a name="whitespace"></a><span data-ttu-id="2c381-122">Espaço em branco</span><span class="sxs-lookup"><span data-stu-id="2c381-122">Whitespace</span></span>  
 <span data-ttu-id="2c381-123">O espaço em branco dentro de um valor de elemento é preservado.</span><span class="sxs-lookup"><span data-stu-id="2c381-123">Whitespace within an element value is preserved.</span></span> <span data-ttu-id="2c381-124">No entanto, os espaços em branco inicial e final são sempre retirados.</span><span class="sxs-lookup"><span data-stu-id="2c381-124">However, leading and trailing whitespace is always trimmed.</span></span> <span data-ttu-id="2c381-125">Por exemplo, os elementos a seguir contêm o mesmo texto mas quantidades diferentes de espaços em branco no texto e, portanto, são tratados como se tivessem valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="2c381-125">For example, the following elements have the same text but differing amounts of whitespace within that text, and are therefore treated as if they have different values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>My  text<Description>`  
  
 ``  
  
 <span data-ttu-id="2c381-126">Entretanto, os elementos a seguir só variam nos espaços em branco inicial e final e, portanto, serão tratados como se tivessem valores equivalentes:</span><span class="sxs-lookup"><span data-stu-id="2c381-126">However, the following elements vary only in leading and trailing whitespace, and are therefore treated as if they have equivalent values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>  My text  <Description>`  
  
 ``  
  
## <a name="data-types"></a><span data-ttu-id="2c381-127">Tipos de dados</span><span class="sxs-lookup"><span data-stu-id="2c381-127">Data Types</span></span>  
 <span data-ttu-id="2c381-128">O Analysis Services usa os seguintes tipos de dados XSD (linguagem de definição de esquema XML) padrão:</span><span class="sxs-lookup"><span data-stu-id="2c381-128">Analysis Services uses the following standard XML Schema definition language (XSD) data types:</span></span>  
  
 `Int`  
 <span data-ttu-id="2c381-129">Um valor inteiro no intervalo de-231 a 231-1.</span><span class="sxs-lookup"><span data-stu-id="2c381-129">An integer value in the range of -231 to 231 - 1.</span></span>  
  
 `Long`  
 <span data-ttu-id="2c381-130">Um valor inteiro no intervalo de-263 a 263-1.</span><span class="sxs-lookup"><span data-stu-id="2c381-130">An integer value in range of -263 to 263 - 1.</span></span>  
  
 `String`  
 <span data-ttu-id="2c381-131">Um valor de cadeia de caracteres em conformidade com as seguintes regras globais:</span><span class="sxs-lookup"><span data-stu-id="2c381-131">A string value that conforms to the following global rules:</span></span>  
  
-   <span data-ttu-id="2c381-132">Os caracteres de controle são retirados.</span><span class="sxs-lookup"><span data-stu-id="2c381-132">Control characters are stripped out.</span></span>  
  
-   <span data-ttu-id="2c381-133">Os espaços em branco inicial e final são retirados.</span><span class="sxs-lookup"><span data-stu-id="2c381-133">Leading and trailing white space is trimmed.</span></span>  
  
-   <span data-ttu-id="2c381-134">O espaço em branco interno é preservado.</span><span class="sxs-lookup"><span data-stu-id="2c381-134">Internal white space is preserved.</span></span>  
  
 <span data-ttu-id="2c381-135">As propriedades `Name` e `ID` têm limitações especiais de caracteres válidos em elementos de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2c381-135">`Name` and `ID` properties have special limitations on valid characters in string elements.</span></span> <span data-ttu-id="2c381-136">Para obter informações adicionais `Name` sobre `ID` convenções e, consulte [objetos e características do objeto ASSL](assl-objects-and-object-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="2c381-136">For additional information about `Name` and `ID` conventions, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
 `DateTime`  
 <span data-ttu-id="2c381-137">Uma `DateTime` estrutura da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c381-137">A `DateTime` structure from the .NET Framework.</span></span> <span data-ttu-id="2c381-138">Um valor `DateTime` não pode ser NULL.</span><span class="sxs-lookup"><span data-stu-id="2c381-138">A `DateTime` value cannot be NULL.</span></span> <span data-ttu-id="2c381-139">A data mais antiga suportada pelo tipo de dados `DataTime` é 1º de janeiro de 1601, disponível a programadores como `DateTime.MinValue`.</span><span class="sxs-lookup"><span data-stu-id="2c381-139">The lowest date supported by the `DataTime` data type is January 1, 1601, which is available to programmers as `DateTime.MinValue`.</span></span> <span data-ttu-id="2c381-140">A data mais antiga suportada indica que um valor `DateTime` está ausente.</span><span class="sxs-lookup"><span data-stu-id="2c381-140">The lowest supported date indicates that a `DateTime` value is missing.</span></span>  
  
 `Boolean`  
 <span data-ttu-id="2c381-141">Uma enumeração só com dois valores, como {verdadeiro, falso} ou {0, 1}.</span><span class="sxs-lookup"><span data-stu-id="2c381-141">An enumeration with only two values, such as {true, false} or {0, 1}.</span></span>  
  
## <a name="default-values"></a><span data-ttu-id="2c381-142">Valores padrão</span><span class="sxs-lookup"><span data-stu-id="2c381-142">Default Values</span></span>  
 <span data-ttu-id="2c381-143">O Analysis Services usa os padrões listados na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="2c381-143">Analysis Services uses the defaults listed in the following table.</span></span>  
  
|<span data-ttu-id="2c381-144">Tipo de dados XML</span><span class="sxs-lookup"><span data-stu-id="2c381-144">XML data type</span></span>|<span data-ttu-id="2c381-145">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="2c381-145">Default value</span></span>|  
|-------------------|-------------------|  
|`Boolean`|<span data-ttu-id="2c381-146">Falso</span><span class="sxs-lookup"><span data-stu-id="2c381-146">False</span></span>|  
|`String`|<span data-ttu-id="2c381-147">"" (cadeia de caracteres vazia)</span><span class="sxs-lookup"><span data-stu-id="2c381-147">"" (empty string)</span></span>|  
|<span data-ttu-id="2c381-148">`Integer` ou `Long`</span><span class="sxs-lookup"><span data-stu-id="2c381-148">`Integer` or `Long`</span></span>|<span data-ttu-id="2c381-149">0 (zero)</span><span class="sxs-lookup"><span data-stu-id="2c381-149">0 (zero)</span></span>|  
|`Timestamp`|<span data-ttu-id="2c381-150">12:00:00 AM, 1/1/0001 (correspondente a um .NET Framework `System.DateTime` com 0 tiques)</span><span class="sxs-lookup"><span data-stu-id="2c381-150">12:00:00 AM, 1/1/0001 (corresponding to a the .NET Frameworks `System.DateTime` with 0 ticks)</span></span>|  
  
 <span data-ttu-id="2c381-151">Um elemento que está presente mas vazio será interpretado como tendo um valor de uma cadeia de caracteres nula, e não como o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="2c381-151">An element that is present but empty is interpreted as having a value of a null string, not the default value.</span></span>  
  
### <a name="inherited-defaults"></a><span data-ttu-id="2c381-152">Padrões herdados</span><span class="sxs-lookup"><span data-stu-id="2c381-152">Inherited Defaults</span></span>  
 <span data-ttu-id="2c381-153">Algumas propriedades especificadas em um objeto fornecem valores padrão para a mesma propriedade em objetos filhos ou descendentes.</span><span class="sxs-lookup"><span data-stu-id="2c381-153">Some properties that are specified on an object provide default values for the same property on child or descendant objects.</span></span> <span data-ttu-id="2c381-154">Por exemplo, `Cube.StorageMode` fornece o valor padrão para `Partition.StorageMode`.</span><span class="sxs-lookup"><span data-stu-id="2c381-154">For example, `Cube.StorageMode` provides the default value for `Partition.StorageMode`.</span></span> <span data-ttu-id="2c381-155">As regras que o Analysis Services aplica para valores padrão herdados são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="2c381-155">The rules that Analysis Services applies for inherited default values are as follows:</span></span>  
  
-   <span data-ttu-id="2c381-156">Quando a propriedade do objeto filho for nula no XML, o padrão do seu valor será o valor herdado.</span><span class="sxs-lookup"><span data-stu-id="2c381-156">When the property for the child object is null in the XML, its value defaults to the inherited value.</span></span> <span data-ttu-id="2c381-157">No entanto, se você consultar o valor a partir do servidor, este retornará o valor nulo do elemento XML.</span><span class="sxs-lookup"><span data-stu-id="2c381-157">However, if you query the value from the server, the server returns the null value of the XML element.</span></span>  
  
-   <span data-ttu-id="2c381-158">Não é possível determinar programaticamente se a propriedade ou objeto filho foi definida corretamente no objeto filho ou herdado.</span><span class="sxs-lookup"><span data-stu-id="2c381-158">It is not possible to determine programmatically whether the property of a child object has been set directly on the child object or inherited.</span></span>  
  
 <span data-ttu-id="2c381-159">Alguns elementos definiram padrões que se aplicarão quando o elemento estiver ausente.</span><span class="sxs-lookup"><span data-stu-id="2c381-159">Some elements have defined defaults that apply when the element is missing.</span></span> <span data-ttu-id="2c381-160">Por exemplo, os elementos `Dimension` do fragmento XML a seguir são equivalentes, mesmo se um elemento `Dimension` contiver um elemento `Visible` e se o outro elemento `Dimension` não.</span><span class="sxs-lookup"><span data-stu-id="2c381-160">For example, the `Dimension` elements in the following XML fragment are equivalent even though one `Dimension` element contains a `Visible` element, but the other `Dimension` element does not.</span></span>  
  
 `<Dimension>`  
  
 `<Name>Product</Name>`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `<Name>Product</ Name>`  
  
 `<Visible>true</Visible>`  
  
 `</Dimension>`  
  
 <span data-ttu-id="2c381-161">Para obter mais informações sobre padrões herdados, consulte [objetos ASSL e características de objeto](assl-objects-and-object-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="2c381-161">For more information on inherited defaults, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
  
