---
title: Codificando tipos definidos pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [CLR integration]
- UDTs [CLR integration], coding
- UserDefined serialization format [CLR integration]
- Point UDT
- Parse method
- null values [CLR integration]
- ToString method
- ValidatePoint method
- attributes [CLR integration]
- coding user-defined types [CLR integration]
- Read method
- Write method
- nullability [CLR integration]
- user-defined types [CLR integration], coding
- Currency UDT
- validating UDT values
- exposing UDT properties [CLR integration]
ms.assetid: 1e5b43b3-4971-45ee-a591-3f535e2ac722
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e88c4d8162e5c7c921f5c5062f5b3c23df40a2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570721"
---
# <a name="coding-user-defined-types"></a><span data-ttu-id="f5380-102">codificando tipos definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5380-102">Coding User-Defined Types</span></span>
  <span data-ttu-id="f5380-103">Ao codificar a definição UDT (tipo definido pelo usuário), você deve implementar vários recursos, dependendo da implementação da UDT como classe ou estrutura, bem como das opções de formato e de serialização escolhidas.</span><span class="sxs-lookup"><span data-stu-id="f5380-103">When coding your user-defined type (UDT) definition, you must implement various features, depending on whether you are implementing the UDT as a class or a structure, as well as on the format and serialization options you have chosen.</span></span>  
  
 <span data-ttu-id="f5380-104">O exemplo nesta seção ilustra a implementação de uma `Point` UDT como `struct` (ou `Structure` no Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f5380-104">The example in this section illustrates implementing a `Point` UDT as a `struct` (or `Structure` in Visual Basic).</span></span> <span data-ttu-id="f5380-105">A UDT `Point` consiste em coordenadas X e Y implementadas como procedimentos de propriedade.</span><span class="sxs-lookup"><span data-stu-id="f5380-105">The `Point` UDT consists of X and Y coordinates implemented as property procedures.</span></span>  
  
 <span data-ttu-id="f5380-106">Os seguintes namespaces são obrigatórios na definição de uma UDT:</span><span class="sxs-lookup"><span data-stu-id="f5380-106">The following namespaces are required when defining a UDT:</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
```  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
```  
  
 <span data-ttu-id="f5380-107">O namespace `Microsoft.SqlServer.Server` contém os objetos necessários a vários atributos da UDT, e o namespace `System.Data.SqlTypes` contém as classes que representam os tipos de dados nativos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponíveis para o assembly.</span><span class="sxs-lookup"><span data-stu-id="f5380-107">The `Microsoft.SqlServer.Server` namespace contains the objects required for various attributes of your UDT, and the `System.Data.SqlTypes` namespace contains the classes that represent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types available to the assembly.</span></span> <span data-ttu-id="f5380-108">É claro que talvez haja namespaces adicionais necessários ao funcionamento correto do assembly.</span><span class="sxs-lookup"><span data-stu-id="f5380-108">There may of course be additional namespaces that your assembly requires in order to function correctly.</span></span> <span data-ttu-id="f5380-109">A UDT `Point` também usa o namespace `System.Text` para trabalhar com cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f5380-109">The `Point` UDT also uses the `System.Text` namespace for working with strings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5380-110">Não há suporte para objetos de banco de dados do Visual C++, como UDTs. compilados com `/clr:pure` para execução.</span><span class="sxs-lookup"><span data-stu-id="f5380-110">Visual C++ database objects, such as UDTs, compiled with `/clr:pure` are not supported for execution.</span></span>  
  
## <a name="specifying-attributes"></a><span data-ttu-id="f5380-111">Especificando atributos</span><span class="sxs-lookup"><span data-stu-id="f5380-111">Specifying Attributes</span></span>  
 <span data-ttu-id="f5380-112">Os atributos determinam como a serialização é usada para construir a representação de armazenamento de UDTs e transmiti-los por valor para o cliente.</span><span class="sxs-lookup"><span data-stu-id="f5380-112">Attributes determine how serialization is used to construct the storage representation of UDTs and to transmit UDTs by value to the client.</span></span>  
  
 <span data-ttu-id="f5380-113">A `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="f5380-113">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` is required.</span></span> <span data-ttu-id="f5380-114">O atributo `Serializable` é opcional.</span><span class="sxs-lookup"><span data-stu-id="f5380-114">The `Serializable` attribute is optional.</span></span> <span data-ttu-id="f5380-115">Também é possível especificar `Microsoft.SqlServer.Server.SqlFacetAttribute` para fornecer informações sobre o tipo de retorno de uma UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-115">You can also specify the `Microsoft.SqlServer.Server.SqlFacetAttribute` to provide information about the return type of a UDT.</span></span> <span data-ttu-id="f5380-116">Para obter mais informações, confira [Atributos personalizados para rotinas do CLR (Common Language Runtime)](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span><span class="sxs-lookup"><span data-stu-id="f5380-116">For more information, see [Custom Attributes for CLR Routines](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span></span>  
  
### <a name="point-udt-attributes"></a><span data-ttu-id="f5380-117">Atributos da UDT Point</span><span class="sxs-lookup"><span data-stu-id="f5380-117">Point UDT Attributes</span></span>  
 <span data-ttu-id="f5380-118">O `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` define o formato de armazenamento para o `Point` UDT como `Native`.</span><span class="sxs-lookup"><span data-stu-id="f5380-118">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` sets the storage format for the `Point` UDT to `Native`.</span></span> <span data-ttu-id="f5380-119">`IsByteOrdered` é definido como `true`, o que garante que os resultados das comparações sejam os mesmos no SQL Server se a mesma comparação foi feita no código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f5380-119">`IsByteOrdered` is set to `true`, which guarantees that the results of comparisons are the same in SQL Server as if the same comparison had taken place in managed code.</span></span> <span data-ttu-id="f5380-120">A UDT implementa a interface `System.Data.SqlTypes.INullable` para que a UDT reconheça nulos.</span><span class="sxs-lookup"><span data-stu-id="f5380-120">The UDT implements the `System.Data.SqlTypes.INullable` interface to make the UDT null aware.</span></span>  
  
 <span data-ttu-id="f5380-121">O seguinte fragmento de código mostra os atributos da UDT `Point`.</span><span class="sxs-lookup"><span data-stu-id="f5380-121">The following code fragment shows the attributes for the `Point` UDT.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True)> _  
  Public Structure Point  
    Implements INullable  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true)]  
public struct Point : INullable  
{  
```  
  
## <a name="implementing-nullability"></a><span data-ttu-id="f5380-122">Implementando a nulidade</span><span class="sxs-lookup"><span data-stu-id="f5380-122">Implementing Nullability</span></span>  
 <span data-ttu-id="f5380-123">Além de especificar corretamente os atributos dos assemblies, a UDT também precisa oferecer suporte à nulidade.</span><span class="sxs-lookup"><span data-stu-id="f5380-123">In addition to specifying the attributes for your assemblies correctly, your UDT must also support nullability.</span></span> <span data-ttu-id="f5380-124">As UDTs carregadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reconhecem nulos, mas para que reconheça um valor nulo, a UDT deve implementar a interface `System.Data.SqlTypes.INullable`.</span><span class="sxs-lookup"><span data-stu-id="f5380-124">UDTs loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are null-aware, but in order for the UDT to recognize a null value, the UDT must implement the `System.Data.SqlTypes.INullable` interface.</span></span>  
  
 <span data-ttu-id="f5380-125">Você deve criar uma propriedade chamada `IsNull`, necessária para determinar se um valor é nulo dentro do código CLR.</span><span class="sxs-lookup"><span data-stu-id="f5380-125">You must create a property named `IsNull`, which is needed to determine whether a value is null from within CLR code.</span></span> <span data-ttu-id="f5380-126">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encontra uma instância nula de uma UDT, esta é mantida, usando métodos manipulação de nulos normais.</span><span class="sxs-lookup"><span data-stu-id="f5380-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finds a null instance of a UDT, the UDT is persisted using normal null-handling methods.</span></span> <span data-ttu-id="f5380-127">O servidor não perde tempo serializando ou desserializando a UDT caso não precise, e ele não perde espaço armazenando uma UDT nula.</span><span class="sxs-lookup"><span data-stu-id="f5380-127">The server does not waste time serializing or deserializing the UDT if it does not have to, and it does not waste space to store a null UDT.</span></span> <span data-ttu-id="f5380-128">Essa verificação de nulos é realizada sempre que uma UDT passa pelo CLR, o que significa que usar a construção [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL para verificar se há UDTs nulas deve funcionar sempre.</span><span class="sxs-lookup"><span data-stu-id="f5380-128">This check for nulls is performed every time a UDT is brought over from the CLR, which means that using the [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL construct to check for null UDTs should always work.</span></span> <span data-ttu-id="f5380-129">A propriedade `IsNull` também é usada pelo servidor para testar se uma instância é nula.</span><span class="sxs-lookup"><span data-stu-id="f5380-129">The `IsNull` property is also used by the server to test whether an instance is null.</span></span> <span data-ttu-id="f5380-130">Quando determina que a UDT é nula, o servidor pode usar a manipulação de nulos nativa.</span><span class="sxs-lookup"><span data-stu-id="f5380-130">Once the server determines that the UDT is null, it can use its native null handling.</span></span>  
  
 <span data-ttu-id="f5380-131">O método `get()` de `IsNull` não tem diferenciação de maiúsculas ou minúsculas definitivamente.</span><span class="sxs-lookup"><span data-stu-id="f5380-131">The `get()` method of `IsNull` is not special-cased in any way.</span></span> <span data-ttu-id="f5380-132">Se uma variável `Point` de `@p` for `Null`, `@p.IsNull` será, por padrão, avaliada como "NULL", e não como "1".</span><span class="sxs-lookup"><span data-stu-id="f5380-132">If a `Point` variable `@p` is `Null`, then `@p.IsNull` will, by default, evaluate to "NULL", not "1".</span></span> <span data-ttu-id="f5380-133">Isso porque o atributo `SqlMethod(OnNullCall)` do método `IsNull get()` usa falso como padrão.</span><span class="sxs-lookup"><span data-stu-id="f5380-133">This is because the `SqlMethod(OnNullCall)` attribute of the `IsNull get()` method defaults to false.</span></span> <span data-ttu-id="f5380-134">Como o objeto é `Null`, quando a propriedade é solicitada, o objeto não é desserializado, o método não é chamado e um valor padrão "NULL" é retornado.</span><span class="sxs-lookup"><span data-stu-id="f5380-134">Because the object is `Null`, when the property is requested the object is not deserialized, the method is not called, and a default value of "NULL" is returned.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f5380-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f5380-135">Example</span></span>  
 <span data-ttu-id="f5380-136">No seguinte exemplo, a variável `is_Null` é privada e mantém o estado de nulidade para a instância da UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-136">In the following example, the `is_Null` variable is private and holds the state of null for the instance of the UDT.</span></span> <span data-ttu-id="f5380-137">O código deve manter um valor apropriado para `is_Null`.</span><span class="sxs-lookup"><span data-stu-id="f5380-137">Your code must maintain an appropriate value for `is_Null`.</span></span> <span data-ttu-id="f5380-138">A UDT também deve ter uma propriedade estática chamada `Null` que retorne uma instância de valor nulo da UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-138">The UDT must also have a static property named `Null` that returns a null value instance of the UDT.</span></span> <span data-ttu-id="f5380-139">Isso permite que a UDT retorne um valor nulo caso a instância seja realmente nula no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5380-139">This allows the UDT to return a null value if the instance is indeed null in the database.</span></span>  
  
```vb  
Private is_Null As Boolean  
  
Public ReadOnly Property IsNull() As Boolean _  
   Implements INullable.IsNull  
    Get  
        Return (is_Null)  
    End Get  
End Property  
  
Public Shared ReadOnly Property Null() As Point  
    Get  
        Dim pt As New Point  
        pt.is_Null = True  
        Return (pt)  
    End Get  
End Property  
```  
  
```csharp  
private bool is_Null;  
  
public bool IsNull  
{  
    get  
    {  
        return (is_Null);  
    }  
}  
  
public static Point Null  
{  
    get  
    {  
        Point pt = new Point();  
        pt.is_Null = true;  
        return pt;  
    }  
}  
```  
  
### <a name="is-null-vs-isnull"></a><span data-ttu-id="f5380-140">IS NULL X IsNull</span><span class="sxs-lookup"><span data-stu-id="f5380-140">IS NULL vs. IsNull</span></span>  
 <span data-ttu-id="f5380-141">Considere uma tabela que contém o esquema Points(id int, location Point), em que `Point` é uma UDT CLR, além das seguintes consultas:</span><span class="sxs-lookup"><span data-stu-id="f5380-141">Consider a table that contains the schema Points(id int, location Point), where `Point` is a CLR UDT, and the following queries:</span></span>  
  
```  
--Query 1  
SELECT ID  
FROM Points  
WHERE NOT (location IS NULL) -- Or, WHERE location IS NOT NULL;  
```  
  
```  
--Query 2:  
SELECT ID  
FROM Points  
WHERE location.IsNull = 0;  
```  
  
 <span data-ttu-id="f5380-142">Ambas as consultas retornam as IDs de pontos com locais não `Null`.</span><span class="sxs-lookup"><span data-stu-id="f5380-142">Both queries return the IDs of points with non-`Null` locations.</span></span> <span data-ttu-id="f5380-143">Na Consulta 1, é usada a manipulação de nulos normal, não havendo nenhuma desserialização das UDTs obrigatória.</span><span class="sxs-lookup"><span data-stu-id="f5380-143">In Query 1, normal null-handling is used, and there no deserialization of UDTs is required.</span></span> <span data-ttu-id="f5380-144">Já a Consulta 2 precisa desserializar todos os objetos não `Null` e chamar o CLR para obter o valor da propriedade `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="f5380-144">Query 2, on the other hand, has to deserialize each non-`Null` object and call into the CLR to obtain the value of the `IsNull` property.</span></span> <span data-ttu-id="f5380-145">Claramente, usar `IS NULL` apresentará um desempenho melhor, não devendo haver nenhum motivo para ler a propriedade `IsNull` de uma UDT no código [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5380-145">Clearly, using `IS NULL` will exhibit better performance and there should never be a reason to read the `IsNull` property of a UDT from [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span>  
  
 <span data-ttu-id="f5380-146">Então, para que serve a propriedade `IsNull`?</span><span class="sxs-lookup"><span data-stu-id="f5380-146">So, what is the use of the `IsNull` property?</span></span> <span data-ttu-id="f5380-147">Primeiro, ela é necessária para determinar se um valor é `Null` dentro do código CLR.</span><span class="sxs-lookup"><span data-stu-id="f5380-147">First, it is needed to determine whether a value is `Null` from within CLR code.</span></span> <span data-ttu-id="f5380-148">Segundo, como o servidor precisa de uma forma para testar se uma instância é `Null`, essa propriedade é usada por ele.</span><span class="sxs-lookup"><span data-stu-id="f5380-148">Second, the server needs a way to test whether an instance is `Null`, so this property is used by the server.</span></span> <span data-ttu-id="f5380-149">Depois de determinar ser `Null`, ele poderá usar a manipulação de nulos nativa para tratá-la.</span><span class="sxs-lookup"><span data-stu-id="f5380-149">After it determines it is `Null`, then it can use its native null handling to handle it.</span></span>  
  
## <a name="implementing-the-parse-method"></a><span data-ttu-id="f5380-150">Implementando o método Parse</span><span class="sxs-lookup"><span data-stu-id="f5380-150">Implementing the Parse Method</span></span>  
 <span data-ttu-id="f5380-151">Os métodos `Parse` e `ToString` permitem conversões de e para representações da cadeia de caracteres da UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-151">The `Parse` and `ToString` methods allow for conversions to and from string representations of the UDT.</span></span> <span data-ttu-id="f5380-152">O método `Parse` permite converter uma cadeia de caracteres em uma UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-152">The `Parse` method allows a string to be converted into a UDT.</span></span> <span data-ttu-id="f5380-153">Ele precisa ser declarado como `static` (ou `Shared` no Visual Basic) e usar um parâmetro do tipo `System.Data.SqlTypes.SqlString`.</span><span class="sxs-lookup"><span data-stu-id="f5380-153">It must be declared as `static` (or `Shared` in Visual Basic), and take a parameter of type `System.Data.SqlTypes.SqlString`.</span></span>  
  
 <span data-ttu-id="f5380-154">O seguinte código implementa o método `Parse` para a UDT `Point`, que separa as coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="f5380-154">The following code implements the `Parse` method for the `Point` UDT, which separates out the X and Y coordinates.</span></span> <span data-ttu-id="f5380-155">O método `Parse` tem um único argumento do tipo `System.Data.SqlTypes.SqlString` e supõe que os valores X e Y sejam fornecidos como uma cadeia de caracteres delimitados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f5380-155">The `Parse` method has a single argument of type `System.Data.SqlTypes.SqlString`, and assumes that X and Y values are supplied as a comma-delimited string.</span></span> <span data-ttu-id="f5380-156">Definir o atributo `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` como `false` impede o método `Parse` de ser chamado em uma instância nula de Point.</span><span class="sxs-lookup"><span data-stu-id="f5380-156">Setting the `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` attribute to `false` prevents the `Parse` method from being called from a null instance of Point.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
    return pt;  
}  
```  
  
## <a name="implementing-the-tostring-method"></a><span data-ttu-id="f5380-157">Implementando o método ToString</span><span class="sxs-lookup"><span data-stu-id="f5380-157">Implementing the ToString Method</span></span>  
 <span data-ttu-id="f5380-158">O método `ToString` converte a UDT `Point` em um valor de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f5380-158">The `ToString` method converts the `Point` UDT to a string value.</span></span> <span data-ttu-id="f5380-159">Nesse caso, a cadeia de caracteres "NULL" é retornada para uma instância Null do tipo `Point`.</span><span class="sxs-lookup"><span data-stu-id="f5380-159">In this case, the string "NULL" is returned for a Null instance of the `Point` type.</span></span> <span data-ttu-id="f5380-160">O método `ToString` inverte o método `Parse` usando um `System.Text.StringBuilder` para retornar um `System.String` delimitado por vírgulas que consiste nos valores de coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="f5380-160">The `ToString` method reverses the `Parse` method by using a `System.Text.StringBuilder` to return a comma-delimited `System.String` consisting of the X and Y coordinate values.</span></span> <span data-ttu-id="f5380-161">Como **InvokeIfReceiverIsNull** assume false como padrão, a verificação de uma instância nula de `Point` é desnecessária.</span><span class="sxs-lookup"><span data-stu-id="f5380-161">Because **InvokeIfReceiverIsNull** defaults to false, the check for a null instance of `Point` is unnecessary.</span></span>  
  
```vb  
Private _x As Int32  
Private _y As Int32  
  
Public Overrides Function ToString() As String  
    If Me.IsNull Then  
        Return "NULL"  
    Else  
        Dim builder As StringBuilder = New StringBuilder  
        builder.Append(_x)  
        builder.Append(",")  
        builder.Append(_y)  
        Return builder.ToString  
    End If  
End Function  
```  
  
```csharp  
private Int32 _x;  
private Int32 _y;  
  
public override string ToString()  
{  
    if (this.IsNull)  
        return "NULL";  
    else  
    {  
        StringBuilder builder = new StringBuilder();  
        builder.Append(_x);  
        builder.Append(",");  
        builder.Append(_y);  
        return builder.ToString();  
    }  
}  
```  
  
## <a name="exposing-udt-properties"></a><span data-ttu-id="f5380-162">Expondo propriedades da UDT</span><span class="sxs-lookup"><span data-stu-id="f5380-162">Exposing UDT Properties</span></span>  
 <span data-ttu-id="f5380-163">A UDT `Point` expõe coordenadas X e Y que são implementadas como propriedades públicas de leitura/gravação do tipo `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="f5380-163">The `Point` UDT exposes X and Y coordinates that are implemented as public read-write properties of type `System.Int32`.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _x = Value  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _y = Value  
    End Set  
End Property  
```  
  
```csharp  
public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    set   
    {  
        _x = value;  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        _y = value;  
    }  
}  
```  
  
## <a name="validating-udt-values"></a><span data-ttu-id="f5380-164">Validando valores de UDT</span><span class="sxs-lookup"><span data-stu-id="f5380-164">Validating UDT Values</span></span>  
 <span data-ttu-id="f5380-165">Ao trabalhar com dados de UDT, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] converte automaticamente valores binários em valores de UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-165">When working with UDT data, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically converts binary values to UDT values.</span></span> <span data-ttu-id="f5380-166">Esse processo de conversão envolve verificar se os valores são apropriados ao formato de serialização do tipo e garantir que o valor possa ser desserializado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f5380-166">This conversion process involves checking that values are appropriate for the serialization format of the type and ensuring that the value can be deserialized correctly.</span></span> <span data-ttu-id="f5380-167">Isso assegura que o valor possa ser novamente convertido em um formato binário.</span><span class="sxs-lookup"><span data-stu-id="f5380-167">This ensures that the value can be converted back to binary form.</span></span> <span data-ttu-id="f5380-168">No caso das UDTs ordenadas por byte, isso também garante que o valor binário resultante corresponda ao valor binário original.</span><span class="sxs-lookup"><span data-stu-id="f5380-168">In the case of byte-ordered UDTs, this also ensures that the resulting binary value matches the original binary value.</span></span> <span data-ttu-id="f5380-169">Isso impede a manutenção de valores inválidos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5380-169">This prevents invalid values from being persisted in the database.</span></span> <span data-ttu-id="f5380-170">Em alguns casos, esse nível de verificação pode ser inadequado.</span><span class="sxs-lookup"><span data-stu-id="f5380-170">In some cases, this level of checking may be inadequate.</span></span> <span data-ttu-id="f5380-171">Talvez seja obrigatória uma validação adicional quando os valores de UDT devem estar em um domínio ou intervalo esperado.</span><span class="sxs-lookup"><span data-stu-id="f5380-171">Additional validation may be required when UDT values are required to be in an expected domain or range.</span></span> <span data-ttu-id="f5380-172">Por exemplo, uma UDT que implementa uma data pode exigir que o valor de dia seja um número positivo e que esteja em um determinado intervalo de valores válidos.</span><span class="sxs-lookup"><span data-stu-id="f5380-172">For example, a UDT that implements a date might require the day value to be a positive number that falls within a certain range of valid values.</span></span>  
  
 <span data-ttu-id="f5380-173">A propriedade `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` de `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` permite fornecer o nome de um método de avaliação executado pelo servidor quando os dados são atribuídos a uma UDT ou convertidos em uma.</span><span class="sxs-lookup"><span data-stu-id="f5380-173">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` allows you to supply the name of a validation method that the server runs when data is assigned to a UDT or converted to a UDT.</span></span> <span data-ttu-id="f5380-174">`ValidationMethodName` também é chamado durante a execução do utilitário bcp, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, consulta distribuída e operações RPC (chamada de procedimento remoto) do protocolo TDS.</span><span class="sxs-lookup"><span data-stu-id="f5380-174">`ValidationMethodName` is also called during the running of the bcp utility, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, distributed query, and tabular data stream (TDS) remote procedure call (RPC) operations.</span></span> <span data-ttu-id="f5380-175">O valor padrão de `ValidationMethodName` é null, o que indica não haver nenhum método de validação.</span><span class="sxs-lookup"><span data-stu-id="f5380-175">The default value for `ValidationMethodName` is null, indicating that there is no validation method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f5380-176">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f5380-176">Example</span></span>  
 <span data-ttu-id="f5380-177">O seguinte fragmento de código mostra a declaração da classe `Point`, que especifica um `ValidationMethodName` de `ValidatePoint`.</span><span class="sxs-lookup"><span data-stu-id="f5380-177">The following code fragment shows the declaration for the `Point` class, which specifies a `ValidationMethodName` of `ValidatePoint`.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true,   
  ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
```  
  
 <span data-ttu-id="f5380-178">Caso seja especificado, um método de validação deve ter uma assinatura semelhante ao seguinte fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="f5380-178">If a validation method is specified, it must have a signature that looks like the following code fragment.</span></span>  
  
```vb  
Private Function ValidationFunction() As Boolean  
    If (validation logic here) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidationFunction()  
{  
    if (validation logic here)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="f5380-179">O método de validação pode ter qualquer escopo e deve retornar `true` caso o valor seja válido, e `false` caso contrário.</span><span class="sxs-lookup"><span data-stu-id="f5380-179">The validation method can have any scope and should return `true` if the value is valid, and `false` otherwise.</span></span> <span data-ttu-id="f5380-180">Caso o método retorne `false` ou lance uma exceção, o valor é tratado como não válido, e ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="f5380-180">If the method returns `false` or throws an exception, the value is treated as not valid and an error is raised.</span></span>  
  
 <span data-ttu-id="f5380-181">No exemplo abaixo, o código só permite valores iguais a zero ou maiores que as coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="f5380-181">In the example below, the code allows only values of zero or greater the X and Y coordinates.</span></span>  
  
```vb  
Private Function ValidatePoint() As Boolean  
    If (_x >= 0) And (_y >= 0) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidatePoint()  
{  
    if ((_x >= 0) && (_y >= 0))  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
### <a name="validation-method-limitations"></a><span data-ttu-id="f5380-182">Limitações do método de validação</span><span class="sxs-lookup"><span data-stu-id="f5380-182">Validation Method Limitations</span></span>  
 <span data-ttu-id="f5380-183">O servidor chama o método de validação ao realizar conversões, e não quando os dados são inseridos definindo propriedades individuais, ou quando eles são inseridos usando uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT.</span><span class="sxs-lookup"><span data-stu-id="f5380-183">The server calls the validation method when the server is performing conversions, not when data is inserted by setting individual properties or when data is inserted using a [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span>  
  
 <span data-ttu-id="f5380-184">Você deve chamar explicitamente o método de validação de setters de propriedade e o `Parse` método se desejar que o método de validação seja executado em todas as situações.</span><span class="sxs-lookup"><span data-stu-id="f5380-184">You must explicitly call the validation method from property setters and the `Parse` method if you want the validation method to execute in all situations.</span></span> <span data-ttu-id="f5380-185">Não se trata de um requisito e, em alguns casos, talvez não seja sequer desejável.</span><span class="sxs-lookup"><span data-stu-id="f5380-185">This is not a requirement, and in some cases may not even be desirable.</span></span>  
  
### <a name="parse-validation-example"></a><span data-ttu-id="f5380-186">Exemplo de validação de Parse</span><span class="sxs-lookup"><span data-stu-id="f5380-186">Parse Validation Example</span></span>  
 <span data-ttu-id="f5380-187">Para garantir que o `ValidatePoint` método seja invocado na `Point` classe, você deve chamá-lo do `Parse` método e dos procedimentos de propriedade que definem os valores de coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="f5380-187">To ensure that the `ValidatePoint` method is invoked in the `Point` class, you must call it from the `Parse` method and from the property procedures that set the X and Y coordinate values.</span></span> <span data-ttu-id="f5380-188">O fragmento de código a seguir mostra como chamar o `ValidatePoint` método de validação da `Parse` função.</span><span class="sxs-lookup"><span data-stu-id="f5380-188">The following code fragment shows how to call the `ValidatePoint` validation method from the `Parse` function.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
  
    ' Call ValidatePoint to enforce validation  
    ' for string conversions.  
    If Not pt.ValidatePoint() Then  
        Throw New ArgumentException("Invalid XY coordinate values.")  
    End If  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
  
    // Call ValidatePoint to enforce validation  
    // for string conversions.  
    if (!pt.ValidatePoint())   
        throw new ArgumentException("Invalid XY coordinate values.");  
    return pt;  
}  
```  
  
### <a name="property-validation-example"></a><span data-ttu-id="f5380-189">Exemplo de validação da propriedade</span><span class="sxs-lookup"><span data-stu-id="f5380-189">Property Validation Example</span></span>  
 <span data-ttu-id="f5380-190">O fragmento de código a seguir mostra como chamar o `ValidatePoint` método de validação dos procedimentos de propriedade que definem as coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="f5380-190">The following code fragment shows how to call the `ValidatePoint` validation method from the property procedures that set the X and Y coordinates.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _x  
        _x = Value  
        If Not ValidatePoint() Then  
            _x = temp  
            Throw New ArgumentException("Invalid X coordinate value.")  
        End If  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _y  
        _y = Value  
        If Not ValidatePoint() Then  
            _y = temp  
            Throw New ArgumentException("Invalid Y coordinate value.")  
        End If  
    End Set  
End Property  
```  
  
```csharp  
    public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    // Call ValidatePoint to ensure valid range of Point values.  
    set   
    {  
        Int32 temp = _x;  
        _x = value;  
        if (!ValidatePoint())  
        {  
            _x = temp;  
            throw new ArgumentException("Invalid X coordinate value.");  
        }  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        Int32 temp = _y;  
        _y = value;  
        if (!ValidatePoint())  
        {  
            _y = temp;  
            throw new ArgumentException("Invalid Y coordinate value.");  
        }  
    }  
}  
```  
  
## <a name="coding-udt-methods"></a><span data-ttu-id="f5380-191">Codificando métodos de UDT</span><span class="sxs-lookup"><span data-stu-id="f5380-191">Coding UDT Methods</span></span>  
 <span data-ttu-id="f5380-192">Durante a codificação dos métodos de UDT, considere se o algoritmo usado pode ser alterado com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="f5380-192">When coding UDT methods, consider whether the algorithm used could possibly change over time.</span></span> <span data-ttu-id="f5380-193">Em caso positivo, você talvez queira considerar a criação de uma classe separada para os métodos usados pela UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-193">If so, you may want to consider creating a separate class for the methods your UDT uses.</span></span> <span data-ttu-id="f5380-194">Caso o algoritmo seja alterado, é possível recompilar a classe com o novo código e carregar o assembly em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sem afetar a UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-194">If the algorithm changes, you can recompile the class with the new code and load the assembly into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without affecting the UDT.</span></span> <span data-ttu-id="f5380-195">Em muitos casos, as UDTs podem ser recarregadas usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY, mas isso pode causar problemas nos dados existentes.</span><span class="sxs-lookup"><span data-stu-id="f5380-195">In many cases UDTs can be reloaded using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement, but that could potentially cause problems with existing data.</span></span> <span data-ttu-id="f5380-196">Por exemplo, o `Currency` UDT incluído com o banco de dados de exemplo **AdventureWorks** usa uma função **ConvertCurrency** para converter valores de moeda, que são implementados em uma classe separada.</span><span class="sxs-lookup"><span data-stu-id="f5380-196">For example, the `Currency` UDT included with the **AdventureWorks** sample database uses a **ConvertCurrency** function to convert currency values, which is implemented in a separate class.</span></span> <span data-ttu-id="f5380-197">É possível que algoritmos de conversão sejam alterados de maneiras imprevisíveis no futuro, ou que uma nova funcionalidade seja obrigatória.</span><span class="sxs-lookup"><span data-stu-id="f5380-197">It is possible that conversion algorithms may change in unpredictable ways in the future, or that new functionality may be required.</span></span> <span data-ttu-id="f5380-198">Separar a função **ConvertCurrency** da implementação de `Currency` UDT fornece maior flexibilidade ao planejar alterações futuras.</span><span class="sxs-lookup"><span data-stu-id="f5380-198">Separating the **ConvertCurrency** function from the `Currency` UDT implementation provides greater flexibility when planning for future changes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f5380-199">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f5380-199">Example</span></span>  
 <span data-ttu-id="f5380-200">A `Point` classe contém três métodos simples para calcular a distância: **Distance**, **DistanceFrom** e **DistanceFromXY**.</span><span class="sxs-lookup"><span data-stu-id="f5380-200">The `Point` class contains three simple methods for calculating distance: **Distance**, **DistanceFrom** and **DistanceFromXY**.</span></span> <span data-ttu-id="f5380-201">Cada um retorna `double` que calcula a distância entre `Point` e zero, a distância entre um ponto especificado e `Point`, além da distância entre as coordenadas X e Y e `Point`.</span><span class="sxs-lookup"><span data-stu-id="f5380-201">Each returns a `double` calculating the distance from `Point` to zero, the distance from a specified point to `Point`, and the distance from specified X and Y coordinates to `Point`.</span></span> <span data-ttu-id="f5380-202">**Distância** e **DistanceFrom** cada chamada **DistanceFromXY**e demonstram como usar argumentos diferentes para cada método.</span><span class="sxs-lookup"><span data-stu-id="f5380-202">**Distance** and **DistanceFrom** each call **DistanceFromXY**, and demonstrate how to use different arguments for each method.</span></span>  
  
```vb  
' Distance from 0 to Point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function Distance() As Double  
    Return DistanceFromXY(0, 0)  
End Function  
  
' Distance from Point to the specified point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFrom(ByVal pFrom As Point) As Double  
    Return DistanceFromXY(pFrom.X, pFrom.Y)  
End Function  
  
' Distance from Point to the specified x and y values.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
    As Double  
    Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
End Function  
```  
  
```csharp  
// Distance from 0 to Point.  
[SqlMethod(OnNullCall = false)]  
public Double Distance()  
{  
    return DistanceFromXY(0, 0);  
}  
  
// Distance from Point to the specified point.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFrom(Point pFrom)  
{  
    return DistanceFromXY(pFrom.X, pFrom.Y);  
}  
  
// Distance from Point to the specified x and y values.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFromXY(Int32 iX, Int32 iY)  
{  
    return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
}  
```  
  
### <a name="using-sqlmethod-attributes"></a><span data-ttu-id="f5380-203">Usando atributos SqlMethod</span><span class="sxs-lookup"><span data-stu-id="f5380-203">Using SqlMethod Attributes</span></span>  
 <span data-ttu-id="f5380-204">A classe `Microsoft.SqlServer.Server.SqlMethodAttribute` fornece atributos personalizados que podem ser usados para marcar definições de método a fim de especificar determinismo, comportamento em chamada nula e determinar se um método é um modificador.</span><span class="sxs-lookup"><span data-stu-id="f5380-204">The `Microsoft.SqlServer.Server.SqlMethodAttribute` class provides custom attributes that can be used to mark method definitions in order to specify determinism, on null call behavior, and to specify whether a method is a mutator.</span></span> <span data-ttu-id="f5380-205">Os valores padrão dessas propriedades são pressupostos, e o atributo personalizado só é usado quando um valor não padrão é necessário.</span><span class="sxs-lookup"><span data-stu-id="f5380-205">Default values for these properties are assumed, and the custom attribute is only used when a non-default value is needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5380-206">A classe `SqlMethodAttribute` é herdada da classe `SqlFunctionAttribute`, assim `SqlMethodAttribute` herda os campos `FillRowMethodName` e `TableDefinition` de `SqlFunctionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="f5380-206">The `SqlMethodAttribute` class inherits from the `SqlFunctionAttribute` class, so `SqlMethodAttribute` inherits the `FillRowMethodName` and `TableDefinition` fields from `SqlFunctionAttribute`.</span></span> <span data-ttu-id="f5380-207">Isso indica que é possível escrever um método com valor de tabela, o que não é o caso.</span><span class="sxs-lookup"><span data-stu-id="f5380-207">This implies that it is possible to write a table-valued method, which is not the case.</span></span> <span data-ttu-id="f5380-208">O método é compilado e o assembly é implantado, mas um erro sobre o `IEnumerable` tipo de retorno é gerado em tempo de execução com a seguinte mensagem: "o método, a propriedade ou o campo ' \<name> ' na classe ' ' \<class> no assembly ' \<assembly> ' tem um tipo de retorno inválido."</span><span class="sxs-lookup"><span data-stu-id="f5380-208">The method compiles and the assembly deploys, but an error about the `IEnumerable` return type is raised at runtime with the following message: "Method, property, or field '\<name>' in class '\<class>' in assembly '\<assembly>' has invalid return type."</span></span>  
  
 <span data-ttu-id="f5380-209">A seguinte tabela descreve algumas das propriedades `Microsoft.SqlServer.Server.SqlMethodAttribute` relevantes que podem ser usadas em métodos de UDT, além de listar os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="f5380-209">The following table describes some of the relevant `Microsoft.SqlServer.Server.SqlMethodAttribute` properties that can be used in UDT methods, and lists their default values.</span></span>  
  
 <span data-ttu-id="f5380-210">DataAccess</span><span class="sxs-lookup"><span data-stu-id="f5380-210">DataAccess</span></span>  
 <span data-ttu-id="f5380-211">Indica se a função envolve o acesso a dados de usuário armazenados na instância local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5380-211">Indicates whether the function involves access to user data stored in the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f5380-212">O padrão é `DataAccessKind``None`.</span><span class="sxs-lookup"><span data-stu-id="f5380-212">Default is `DataAccessKind`.`None`.</span></span>  
  
 <span data-ttu-id="f5380-213">IsDeterministic</span><span class="sxs-lookup"><span data-stu-id="f5380-213">IsDeterministic</span></span>  
 <span data-ttu-id="f5380-214">Indica se a função produz os mesmos valores de saída, dados os mesmos valores de entrada e o mesmo estado de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5380-214">Indicates whether the function produces the same output values given the same input values and the same database state.</span></span> <span data-ttu-id="f5380-215">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="f5380-215">Default is `false`.</span></span>  
  
 <span data-ttu-id="f5380-216">IsMutator</span><span class="sxs-lookup"><span data-stu-id="f5380-216">IsMutator</span></span>  
 <span data-ttu-id="f5380-217">Indica se o método causa uma alteração de estado na instância da UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-217">Indicates whether the method causes a state change in the UDT instance.</span></span> <span data-ttu-id="f5380-218">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="f5380-218">Default is `false`.</span></span>  
  
 <span data-ttu-id="f5380-219">IsPrecise</span><span class="sxs-lookup"><span data-stu-id="f5380-219">IsPrecise</span></span>  
 <span data-ttu-id="f5380-220">Indica se a função envolve computações imprecisas como, por exemplo, operações de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="f5380-220">Indicates whether the function involves imprecise computations, such as floating point operations.</span></span> <span data-ttu-id="f5380-221">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="f5380-221">Default is `false`.</span></span>  
  
 <span data-ttu-id="f5380-222">OnNullCall</span><span class="sxs-lookup"><span data-stu-id="f5380-222">OnNullCall</span></span>  
 <span data-ttu-id="f5380-223">Indica se o método é chamado quando são especificados argumentos de entrada de referência nulos.</span><span class="sxs-lookup"><span data-stu-id="f5380-223">Indicates whether the method is called when null reference input arguments are specified.</span></span> <span data-ttu-id="f5380-224">O padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="f5380-224">Default is `true`.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f5380-225">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f5380-225">Example</span></span>  
 <span data-ttu-id="f5380-226">A propriedade `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` possibilita marcar um método que permite uma alteração no estado de uma instância de uma UDT</span><span class="sxs-lookup"><span data-stu-id="f5380-226">The `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` property allows you to mark a method that allows a change in the state of an instance of a UDT.</span></span> <span data-ttu-id="f5380-227">A [!INCLUDE[tsql](../../includes/tsql-md.md)] não permite definir duas propriedades de UDT na cláusula SET de uma instrução UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f5380-227">[!INCLUDE[tsql](../../includes/tsql-md.md)] does not allow you to set two UDT properties in the SET clause of one UPDATE statement.</span></span> <span data-ttu-id="f5380-228">No entanto, é possível ter um método marcado como um modificador que altera os dois membros.</span><span class="sxs-lookup"><span data-stu-id="f5380-228">However, you can have a method marked as a mutator that changes the two members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5380-229">Os métodos Mutator não são permitidos em consultas.</span><span class="sxs-lookup"><span data-stu-id="f5380-229">Mutator methods are not allowed in queries.</span></span> <span data-ttu-id="f5380-230">Eles só podem ser chamados em instruções de atribuição ou de modificação de dados.</span><span class="sxs-lookup"><span data-stu-id="f5380-230">They can be called only in assignment statements or data modification statements.</span></span> <span data-ttu-id="f5380-231">Caso um método marcado como modificador não retorne `void` (ou não é um `Sub` no Visual Basic), CREATE TYPE falha com um erro.</span><span class="sxs-lookup"><span data-stu-id="f5380-231">If a method marked as mutator does not return `void` (or is not a `Sub` in Visual Basic), CREATE TYPE fails with an error.</span></span>  
  
 <span data-ttu-id="f5380-232">A seguinte instrução supõe a existência de uma UDT `Triangles` com um método `Rotate`.</span><span class="sxs-lookup"><span data-stu-id="f5380-232">The following statement assumes the existence of a `Triangles` UDT that has a `Rotate` method.</span></span> <span data-ttu-id="f5380-233">A seguinte instrução de atualização [!INCLUDE[tsql](../../includes/tsql-md.md)] invoca o método `Rotate`:</span><span class="sxs-lookup"><span data-stu-id="f5380-233">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] update statement invokes the `Rotate` method:</span></span>  
  
```  
UPDATE Triangles SET t.RotateY(0.6) WHERE id=5  
```  
  
 <span data-ttu-id="f5380-234">O método `Rotate` é decorado com a configuração de atributo `SqlMethod``IsMutator` como `true` para que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possa marcar o método como modificador.</span><span class="sxs-lookup"><span data-stu-id="f5380-234">The `Rotate` method is decorated with the `SqlMethod` attribute setting `IsMutator` to `true` so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can mark the method as a mutator method.</span></span> <span data-ttu-id="f5380-235">O código também define `OnNullCall` como `false`, o que indica para o servidor que o método retorna uma referência nula (`Nothing` no Visual Basic), caso alguma dos parâmetros de entrada sejam referências nulas.</span><span class="sxs-lookup"><span data-stu-id="f5380-235">The code also sets `OnNullCall` to `false`, which indicates to the server that the method returns a null reference (`Nothing` in Visual Basic) if any of the input parameters are null references.</span></span>  
  
```vb  
<SqlMethod(IsMutator:=True, OnNullCall:=False)> _  
Public Sub Rotate(ByVal anglex as Double, _  
  ByVal angley as Double, ByVal anglez As Double)   
   RotateX(anglex)  
   RotateY(angley)  
   RotateZ(anglez)  
End Sub  
```  
  
```csharp  
[SqlMethod(IsMutator = true, OnNullCall = false)]  
public void Rotate(double anglex, double angley, double anglez)   
{  
   RotateX(anglex);  
   RotateY(angley);  
   RotateZ(anglez);  
}  
```  
  
## <a name="implementing-a-udt-with-a-user-defined-format"></a><span data-ttu-id="f5380-236">Implementando uma UDT com um formato definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5380-236">Implementing a UDT with a User-Defined Format</span></span>  
 <span data-ttu-id="f5380-237">Ao implementar uma UDT com um formato definido pelo usuário, você deve implementar os métodos `Read` e `Write` que implementam a interface Microsoft.SqlServer.Server.IBinarySerialize para tratar dados de UDT de serialização e de desserialização.</span><span class="sxs-lookup"><span data-stu-id="f5380-237">When implementing a UDT with a user-defined format, you must implement `Read` and `Write` methods that implement the Microsoft.SqlServer.Server.IBinarySerialize interface to handle serializing and deserializing UDT data.</span></span> <span data-ttu-id="f5380-238">Também é possível especificar a propriedade `MaxByteSize` de `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="f5380-238">You must also specify the `MaxByteSize` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span></span>  
  
### <a name="the-currency-udt"></a><span data-ttu-id="f5380-239">A UDT Currency</span><span class="sxs-lookup"><span data-stu-id="f5380-239">The Currency UDT</span></span>  
 <span data-ttu-id="f5380-240">A UDT `Currency` está incluída n as amostras do CLR que podem ser instaladas com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5380-240">The `Currency` UDT is included with the CLR samples that can be installed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="f5380-241">A UDT `Currency` oferece suporte à manipulação de valores em dinheiro no sistema financeiro de uma determinada cultura.</span><span class="sxs-lookup"><span data-stu-id="f5380-241">The `Currency` UDT supports handling amounts of money in the monetary system of a particular culture.</span></span> <span data-ttu-id="f5380-242">Você deve definir dois campos: `string` para `CultureInfo`, que especifica quem emitiu a moeda (pt-br, por exemplo) e `decimal` para `CurrencyValue`, o volume de dinheiro.</span><span class="sxs-lookup"><span data-stu-id="f5380-242">You must define two fields: a `string` for `CultureInfo`, which specifies who issued the currency (en-us, for example) and a `decimal` for `CurrencyValue`, the amount of money.</span></span>  
  
 <span data-ttu-id="f5380-243">Embora não seja usada pelo servidor para realizar comparações, a UDT `Currency` implementa a interface `System.IComparable`, que expõe um único método, `System.IComparable.CompareTo`.</span><span class="sxs-lookup"><span data-stu-id="f5380-243">Although it is not used by the server for performing comparisons, the `Currency` UDT implements the `System.IComparable` interface, which exposes a single method, `System.IComparable.CompareTo`.</span></span> <span data-ttu-id="f5380-244">Isso é usado do lado de cliente, em situações nas quais é desejável comparar com precisão ou ordenar valores de moeda dentro de culturas.</span><span class="sxs-lookup"><span data-stu-id="f5380-244">This is used on the client side in situations where it is desirable to accurately compare or order currency values within cultures.</span></span>  
  
 <span data-ttu-id="f5380-245">O código em execução no CLR compara a cultura separadamente do valor de moeda.</span><span class="sxs-lookup"><span data-stu-id="f5380-245">Code running in the CLR compares the culture separately from the currency value.</span></span> <span data-ttu-id="f5380-246">Para o código [!INCLUDE[tsql](../../includes/tsql-md.md)], as seguintes ações determinam a comparação:</span><span class="sxs-lookup"><span data-stu-id="f5380-246">For [!INCLUDE[tsql](../../includes/tsql-md.md)] code, the following actions determine the comparison:</span></span>  
  
1.  <span data-ttu-id="f5380-247">Defina o atributo `IsByteOrdered` como true, que informa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para usar a representação binária mantida em disco para comparações.</span><span class="sxs-lookup"><span data-stu-id="f5380-247">Set the `IsByteOrdered` attribute to true, which tells [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use the persisted binary representation on disk for comparisons.</span></span>  
  
2.  <span data-ttu-id="f5380-248">Use o método `Write` da UDT `Currency` para determinar como a UDT é mantida em disco e, assim, a forma como os valores da UDT são comparados e ordenados para as operações [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5380-248">Use the `Write` method for the `Currency` UDT to determine how the UDT is persisted on disk and therefore how UDT values are compared and ordered for [!INCLUDE[tsql](../../includes/tsql-md.md)] operations.</span></span>  
  
3.  <span data-ttu-id="f5380-249">Salve a UDT `Currency` que usa o seguinte formato binário:</span><span class="sxs-lookup"><span data-stu-id="f5380-249">Save the `Currency` UDT using the following binary format:</span></span>  
  
    1.  <span data-ttu-id="f5380-250">Salve a cultura como uma cadeia de caracteres codificada UTF-16 para bytes de 0 a 19 com preenchimento à direita com caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="f5380-250">Save the culture as a UTF-16 encoded string for bytes 0-19 with padding to the right with null characters.</span></span>  
  
    2.  <span data-ttu-id="f5380-251">Use bytes 20 e acima para conter o valor decimal da moeda.</span><span class="sxs-lookup"><span data-stu-id="f5380-251">Use bytes 20 and above to contain the decimal value of the currency.</span></span>  
  
 <span data-ttu-id="f5380-252">O propósito do preenchimento é assegurar que a cultura seja totalmente separada do valor de moeda, para que quando uma UDT seja comparada com outra no código [!INCLUDE[tsql](../../includes/tsql-md.md)], os bytes de cultura sejam comparados com os bytes de cultura e os valores de byte da moeda, com os valores de byte da moeda.</span><span class="sxs-lookup"><span data-stu-id="f5380-252">The purpose of the padding is to ensure that the culture is completely separated from the currency value, so that when one UDT is compared against another in [!INCLUDE[tsql](../../includes/tsql-md.md)] code, culture bytes are compared against culture bytes, and currency byte values are compared against currency byte values.</span></span>  
  
 <span data-ttu-id="f5380-253">Para obter a listagem de código completa para o `Currency` UDT, siga as instruções para instalar os exemplos de CLR em [exemplos de Mecanismo de Banco de Dados de SQL Server](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="f5380-253">For the complete code listing for the `Currency` UDT, follow the directions for installing the CLR samples in [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
### <a name="currency-attributes"></a><span data-ttu-id="f5380-254">Atributos Currency</span><span class="sxs-lookup"><span data-stu-id="f5380-254">Currency Attributes</span></span>  
 <span data-ttu-id="f5380-255">A UDT `Currency` é definida com os atributos a seguir.</span><span class="sxs-lookup"><span data-stu-id="f5380-255">The `Currency` UDT is defined with the following attributes.</span></span>  
  
```vb  
<Serializable(), Microsoft.SqlServer.Server.SqlUserDefinedType( _  
    Microsoft.SqlServer.Server.Format.UserDefined, _  
    IsByteOrdered:=True, MaxByteSize:=32), _  
    CLSCompliant(False)> _  
Public Structure Currency  
Implements INullable, IComparable, _  
Microsoft.SqlServer.Server.IBinarySerialize  
```  
  
```csharp  
[Serializable]  
[SqlUserDefinedType(Format.UserDefined,   
    IsByteOrdered = true, MaxByteSize = 32)]  
    [CLSCompliant(false)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
```  
  
## <a name="creating-read-and-write-methods-with-ibinaryserialize"></a><span data-ttu-id="f5380-256">Criando métodos Read e Write com IBinarySerialize</span><span class="sxs-lookup"><span data-stu-id="f5380-256">Creating Read and Write Methods with IBinarySerialize</span></span>  
 <span data-ttu-id="f5380-257">Ao escolher o formato de serialização `UserDefined`, você também deve implementar a interface `IBinarySerialize` e criar seus próprios métodos `Read` e `Write`.</span><span class="sxs-lookup"><span data-stu-id="f5380-257">When you choose `UserDefined` serialization format, you also must implement the `IBinarySerialize` interface and create your own `Read` and `Write` methods.</span></span> <span data-ttu-id="f5380-258">Os seguintes procedimentos na UDT `Currency` usam `System.IO.BinaryReader` e `System.IO.BinaryWriter` para ler e gravar na UDT.</span><span class="sxs-lookup"><span data-stu-id="f5380-258">The following procedures from the `Currency` UDT use the `System.IO.BinaryReader` and `System.IO.BinaryWriter` to read from and write to the UDT.</span></span>  
  
```vb  
' IBinarySerialize methods  
' The binary layout is as follow:  
'    Bytes 0 - 19: Culture name, padded to the right with null  
'    characters, UTF-16 encoded  
'    Bytes 20+: Decimal value of money  
' If the culture name is empty, the currency is null.  
Public Sub Write(ByVal w As System.IO.BinaryWriter) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Write  
    If Me.IsNull Then  
        w.Write(nullMarker)  
        w.Write(System.Convert.ToDecimal(0))  
        Return  
    End If  
  
    If cultureName.Length > cultureNameMaxSize Then  
        Throw New ApplicationException(String.Format(CultureInfo.CurrentUICulture, _  
           "{0} is an invalid culture name for currency as it is too long.", cultureNameMaxSize))  
    End If  
  
    Dim paddedName As String = cultureName.PadRight(cultureNameMaxSize, CChar(vbNullChar))  
  
    For i As Integer = 0 To cultureNameMaxSize - 1  
        w.Write(paddedName(i))  
    Next i  
  
    ' Normalize decimal value to two places  
    currencyVal = Decimal.Floor(currencyVal * 100) / 100  
    w.Write(currencyVal)  
End Sub  
  
Public Sub Read(ByVal r As System.IO.BinaryReader) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Read  
    Dim name As Char() = r.ReadChars(cultureNameMaxSize)  
    Dim stringEnd As Integer = Array.IndexOf(name, CChar(vbNullChar))  
  
    If stringEnd = 0 Then  
        cultureName = Nothing  
        Return  
    End If  
  
    cultureName = New String(name, 0, stringEnd)  
    currencyVal = r.ReadDecimal()  
End Sub  
  
```  
  
```csharp  
// IBinarySerialize methods  
// The binary layout is as follow:  
//    Bytes 0 - 19:Culture name, padded to the right   
//    with null characters, UTF-16 encoded  
//    Bytes 20+:Decimal value of money  
// If the culture name is empty, the currency is null.  
public void Write(System.IO.BinaryWriter w)  
{  
    if (this.IsNull)  
    {  
        w.Write(nullMarker);  
        w.Write((decimal)0);  
        return;  
    }  
  
    if (cultureName.Length > cultureNameMaxSize)  
    {  
        throw new ApplicationException(string.Format(  
            CultureInfo.InvariantCulture,   
            "{0} is an invalid culture name for currency as it is too long.",   
            cultureNameMaxSize));  
    }  
  
    String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
    for (int i = 0; i < cultureNameMaxSize; i++)  
    {  
        w.Write(paddedName[i]);  
    }  
  
    // Normalize decimal value to two places  
    currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
    w.Write(currencyValue);  
}  
public void Read(System.IO.BinaryReader r)  
{  
    char[] name = r.ReadChars(cultureNameMaxSize);  
    int stringEnd = Array.IndexOf(name, '\0');  
  
    if (stringEnd == 0)  
    {  
        cultureName = null;  
        return;  
    }  
  
    cultureName = new String(name, 0, stringEnd);  
    currencyValue = r.ReadDecimal();  
}  
```  
  
 <span data-ttu-id="f5380-259">Para obter a listagem de código completa para o `Currency` UDT, consulte [SQL Server mecanismo de banco de dados Samples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="f5380-259">For the complete code listing for the `Currency` UDT, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5380-260">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5380-260">See Also</span></span>  
 [<span data-ttu-id="f5380-261">Criando um tipo definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5380-261">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
  
