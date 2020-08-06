---
title: Trabalhando com tipos de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570560"
---
# <a name="working-with-data-types"></a><span data-ttu-id="420b0-102">Trabalhando com tipos de dados</span><span class="sxs-lookup"><span data-stu-id="420b0-102">Working with Data Types</span></span>
  <span data-ttu-id="420b0-103">Existem muitos tipos e tamanhos de dados, como uma cadeia de caracteres com comprimento definido, um número com uma precisão específica ou um tipo de dados definido pelo usuário que é um outro objeto com seu próprio conjunto de regras.</span><span class="sxs-lookup"><span data-stu-id="420b0-103">Data comes in many types and sizes, such as a string that has a defined length, a number that has specific accuracy, or a user-defined data type that is another object that has its own set of rules.</span></span> <span data-ttu-id="420b0-104">O <xref:Microsoft.SqlServer.Management.Smo.DataType> objeto classifica o tipo de dados para que ele possa ser manipulado corretamente pelo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="420b0-104">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object classifies the type of data so that it can be handled correctly by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="420b0-105">O objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> é associado a objetos que aceitam dados.</span><span class="sxs-lookup"><span data-stu-id="420b0-105">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object is associated with objects that accept data.</span></span> <span data-ttu-id="420b0-106">Os objetos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) a seguir aceitam dados que devem ser definidos por uma propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.DataType>:</span><span class="sxs-lookup"><span data-stu-id="420b0-106">The following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects accept data that must be defined by a <xref:Microsoft.SqlServer.Management.Smo.DataType> object property:</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 <span data-ttu-id="420b0-107">A propriedade `DataType` para objetos que aceitam dados pode ser definida de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="420b0-107">The `DataType` property for objects that accept data can be set in several ways.</span></span>  
  
-   <span data-ttu-id="420b0-108">Use o construtor padrão e especifique propriedades de objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> explicitamente.</span><span class="sxs-lookup"><span data-stu-id="420b0-108">Use the default constructor and specify <xref:Microsoft.SqlServer.Management.Smo.DataType> object properties explicitly</span></span>  
  
-   <span data-ttu-id="420b0-109">Use um construtor sobrecarregado e especifique as propriedades <xref:Microsoft.SqlServer.Management.Smo.DataType> como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="420b0-109">Use an overloaded constructor and specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> properties as parameters.</span></span>  
  
-   <span data-ttu-id="420b0-110">Especifique o <xref:Microsoft.SqlServer.Management.Smo.DataType> embutido no construtor de objeto.</span><span class="sxs-lookup"><span data-stu-id="420b0-110">Specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> inline in the object constructor.</span></span>  
  
-   <span data-ttu-id="420b0-111">Use um dos membros estáticos da classe <xref:Microsoft.SqlServer.Management.Smo.DataType>, por exemplo `Int`.</span><span class="sxs-lookup"><span data-stu-id="420b0-111">Use one of the static members of the <xref:Microsoft.SqlServer.Management.Smo.DataType> class, for example `Int`.</span></span> <span data-ttu-id="420b0-112">Isso retornará, na realidade, uma instância de um objeto <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="420b0-112">This will in fact return an instance of a <xref:Microsoft.SqlServer.Management.Smo.DataType> object.</span></span>  
  
 <span data-ttu-id="420b0-113">O objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> tem várias propriedades que definem o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="420b0-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object has several properties that define the type of data.</span></span> <span data-ttu-id="420b0-114">Por exemplo, a propriedade <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> especifica o tipo de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="420b0-114">For example, the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> property specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.</span></span> <span data-ttu-id="420b0-115">Os valores constantes que representam tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] são listados na enumeração <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="420b0-115">The constant values that represent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types are listed in the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="420b0-116">Isso se refere a tipos de dados como `varchar`, `nchar`, `currency`, `integer`, `float` e `datetime`.</span><span class="sxs-lookup"><span data-stu-id="420b0-116">This refers to data types such as `varchar`, `nchar`, `currency`, `integer`, `float`, and `datetime`.</span></span>  
  
 <span data-ttu-id="420b0-117">Quando o tipo de dados for estabelecido, propriedades específicas deverão ser definidas para os dados.</span><span class="sxs-lookup"><span data-stu-id="420b0-117">When the data type is established, specific properties must be set for the data.</span></span> <span data-ttu-id="420b0-118">Por exemplo, se ele for um tipo `nchar`, o comprimento dos dados de cadeia de caracteres deverá ser definido na propriedade `Length`.</span><span class="sxs-lookup"><span data-stu-id="420b0-118">For example, if it is an `nchar` type, the length of the string data must be set in the `Length` property.</span></span> <span data-ttu-id="420b0-119">O mesmo se aplica a valores numéricos, nos quais você teria que especificar a precisão e a escala.</span><span class="sxs-lookup"><span data-stu-id="420b0-119">The same applies for numeric values, where you would have to specify precision and scale.</span></span>  
  
 <span data-ttu-id="420b0-120">Os tipos de dados<xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> se referem a objetos que contêm a definição do tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="420b0-120"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> data types refer to objects that contain the definition of the type of data defined by the user.</span></span> <span data-ttu-id="420b0-121">O <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> se baseia em tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] da enumeração <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="420b0-121">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> is based on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types from the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="420b0-122">O <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> é baseado em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] tipos de dados do .net.</span><span class="sxs-lookup"><span data-stu-id="420b0-122">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> is based on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET data types.</span></span> <span data-ttu-id="420b0-123">Normalmente, esses representariam dados de um tipo específico que é reutilizado com frequência pelo banco de dados por causa de regras comerciais definidas pela organização.</span><span class="sxs-lookup"><span data-stu-id="420b0-123">Typically, these would represent data of a specific type that is frequently reused by the database because of business rules defined by the organization.</span></span> <span data-ttu-id="420b0-124">Por exemplo, um tipo de dados que armazena uma quantia de dinheiro e um denominador monetário seria útil em uma empresa que trabalha com várias moedas.</span><span class="sxs-lookup"><span data-stu-id="420b0-124">For example, a data type that stores an amount of money and a currency denominator would be helpful in a company that deals in multiple currencies.</span></span>  
  
 <span data-ttu-id="420b0-125">A enumeração <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> contém uma lista de todos os tipos de dados com suporte no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="420b0-125">The <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration contains a list of all the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-supported data types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="420b0-126">Exemplos</span><span class="sxs-lookup"><span data-stu-id="420b0-126">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a><span data-ttu-id="420b0-127">Construindo um objeto DataType com a especificação do construtor no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="420b0-127">Constructing a DataType Object with the Specification in the Constructor in Visual Basic</span></span>  
 <span data-ttu-id="420b0-128">Este exemplo de código mostra como usar o construtor para criar instâncias de tipos de dados baseadas em diferentes tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="420b0-128">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="420b0-129">Todos os tipos <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e XML exigem um valor de nome para identificação do objeto.</span><span class="sxs-lookup"><span data-stu-id="420b0-129">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a><span data-ttu-id="420b0-130">Construindo um objeto DataType com a especificação do construtor no Visual C#</span><span class="sxs-lookup"><span data-stu-id="420b0-130">Constructing a DataType Object with the Specification in the Constructor in Visual C#</span></span>  
 <span data-ttu-id="420b0-131">Este exemplo de código mostra como usar o construtor para criar instâncias de tipos de dados baseadas em diferentes tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="420b0-131">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="420b0-132">Todos os tipos <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e XML exigem um valor de nome para identificação do objeto.</span><span class="sxs-lookup"><span data-stu-id="420b0-132">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a><span data-ttu-id="420b0-133">Construindo um objeto DataType com o construtor padrão no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="420b0-133">Constructing a DataType Object by Using the Default Constructor in Visual Basic</span></span>  
 <span data-ttu-id="420b0-134">Este exemplo de código mostra como usar o construtor padrão para criar instâncias de tipos de dados baseadas em diferentes tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="420b0-134">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="420b0-135">As propriedades são, então, usadas para especificar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="420b0-135">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="420b0-136">**Observação** <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>Todos os <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipos XML,, e exigem um valor Name para identificar o objeto.</span><span class="sxs-lookup"><span data-stu-id="420b0-136">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a><span data-ttu-id="420b0-137">Construindo um objeto DataType com o construtor padrão no Visual C#</span><span class="sxs-lookup"><span data-stu-id="420b0-137">Constructing a DataType Object by Using the Default Constructor in Visual C#</span></span>  
 <span data-ttu-id="420b0-138">Este exemplo de código mostra como usar o construtor padrão para criar instâncias de tipos de dados baseadas em diferentes tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="420b0-138">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="420b0-139">As propriedades são, então, usadas para especificar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="420b0-139">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="420b0-140">**Observação** <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>Todos os <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipos XML,, e exigem um valor Name para identificar o objeto.</span><span class="sxs-lookup"><span data-stu-id="420b0-140">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
