---
title: Criar variáveis e colunas de tipo de dados XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- xml data type [SQL Server], columns
ms.assetid: 8994ab6e-5519-4ba2-97a1-fac8af6f72db
author: rothja
ms.author: jroth
ms.openlocfilehash: 08b79888eb47634deaccc910b2ea3c93800b7c78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684111"
---
# <a name="create-xml-data-type-variables-and-columns"></a><span data-ttu-id="6c78c-102">Criar variáveis e colunas de tipo de dados XML</span><span class="sxs-lookup"><span data-stu-id="6c78c-102">Create XML Data Type Variables and Columns</span></span>
  <span data-ttu-id="6c78c-103">O tipo de dados `xml` é um tipo de dados interno no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e é um pouco semelhante a outros tipos internos, como `int` e `varchar`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-103">The `xml` data type is a built-in data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is somewhat similar to other built-in types such as `int` and `varchar`.</span></span> <span data-ttu-id="6c78c-104">Assim como ocorre com outros tipos internos, você pode usar o `xml` tipo de dados como um tipo de coluna ao criar uma tabela como um tipo de variável, um tipo de parâmetro, um tipo de retorno de função, ou em [cast e Convert](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c78c-104">As with other built-in types, you can use the `xml` data type as a column type when you create a table as a variable type, a parameter type, a function-return type, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
## <a name="creating-columns-and-variables"></a><span data-ttu-id="6c78c-105">Criando colunas e variáveis</span><span class="sxs-lookup"><span data-stu-id="6c78c-105">Creating Columns and Variables</span></span>  
 <span data-ttu-id="6c78c-106">Para criar uma coluna de tipo `xml` como parte de uma tabela, use uma instrução `CREATE TABLE` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="6c78c-106">To create an `xml` type column as part of a table, use a `CREATE TABLE` statement, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T1(Col1 int primary key, Col2 xml)   
```  
  
 <span data-ttu-id="6c78c-107">É possível usar uma `DECLARE statement` para criar uma variável de tipo `xml` , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c78c-107">You can use a `DECLARE statement` to create a variable of `xml` type, as the following example shows.</span></span>  
  
```  
DECLARE @x xml   
```  
  
 <span data-ttu-id="6c78c-108">Crie uma variável `xml` com tipo especificando uma coleção de esquema XML, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c78c-108">Create a typed `xml` variable by specifying an XML schema collection, as shown in the following example.</span></span>  
  
```  
DECLARE @x xml (Sales.StoreSurveySchemaCollection)  
```  
  
 <span data-ttu-id="6c78c-109">Para passar um parâmetro de tipo `xml` para um procedimento armazenado, use uma instrução `CREATE PROCEDURE` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="6c78c-109">To pass an `xml` type parameter to a stored procedure, use a `CREATE PROCEDURE` statement, as shown in the following example.</span></span>  
  
```  
CREATE PROCEDURE SampleProc(@XmlDoc xml) AS ...   
```  
  
 <span data-ttu-id="6c78c-110">É possível usar XQuery para consultar instâncias XML armazenadas em colunas, parâmetros ou variáveis.</span><span class="sxs-lookup"><span data-stu-id="6c78c-110">You can use XQuery to query XML instances stored in columns, parameters, or variables.</span></span> <span data-ttu-id="6c78c-111">Também é possível usar o XML DML (linguagem de manipulação de dados) para aplicar alterações nas instâncias XML.</span><span class="sxs-lookup"><span data-stu-id="6c78c-111">You can also use the XML Data Manipulation Language (XML DML) to apply updates to the XML instances.</span></span> <span data-ttu-id="6c78c-112">Como o padrão XQuery não definiu XQuery DML durante o desenvolvimento, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduz extensões da [Linguagem de modificação de dados XML](/sql/t-sql/xml/xml-data-modification-language-xml-dml) ao XQuery.</span><span class="sxs-lookup"><span data-stu-id="6c78c-112">Because the XQuery standard did not define XQuery DML at the time of development, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduces [XML Data Modification Language](/sql/t-sql/xml/xml-data-modification-language-xml-dml) extensions to XQuery.</span></span> <span data-ttu-id="6c78c-113">Essas extensões permitem executar operações de inserção, atualização e exclusão.</span><span class="sxs-lookup"><span data-stu-id="6c78c-113">These extensions allow you to perform insert, update, and delete operations.</span></span>  
  
## <a name="assigning-defaults"></a><span data-ttu-id="6c78c-114">Atribuindo padrões</span><span class="sxs-lookup"><span data-stu-id="6c78c-114">Assigning Defaults</span></span>  
 <span data-ttu-id="6c78c-115">Em uma tabela, é possível atribuir uma instância XML padrão a uma coluna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-115">In a table, you can assign a default XML instance to a column of `xml` type.</span></span> <span data-ttu-id="6c78c-116">É possível fornecer o XML padrão de uma de duas maneiras: usando uma constante XML ou usando uma conversão explícita para o tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-116">You can provide the default XML in one of two ways: by using an XML constant, or by using an explicit cast to the `xml` type.</span></span>  
  
 <span data-ttu-id="6c78c-117">Para fornecer o XML padrão como uma constante XML, use sintaxe conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c78c-117">To provide the default XML as an XML constant, use syntax as shown in the following example.</span></span> <span data-ttu-id="6c78c-118">Observe que a cadeia de caracteres é implicitamente CAST para tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-118">Note that the string is implicitly CAST to `xml` type.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml default N'<element1/><element2/>')  
```  
  
 <span data-ttu-id="6c78c-119">Para fornecer o XML padrão como um `CAST` explícito para `xml`, use a sintaxe mostrada no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c78c-119">To provide the default XML as an explicit `CAST` to `xml`, use syntax as shown in the following example.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml   
                  default CAST(N'<element1/><element2/>' AS xml))  
```  
  
 <span data-ttu-id="6c78c-120">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] também oferece suporte a restrições de NULL e NOT NULL em colunas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also supports NULL and NOT NULL constraints on columns of `xml` type.</span></span> <span data-ttu-id="6c78c-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6c78c-121">For example:</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml NOT NULL)  
```  
  
## <a name="specifying-constraints"></a><span data-ttu-id="6c78c-122">Especificando restrições</span><span class="sxs-lookup"><span data-stu-id="6c78c-122">Specifying Constraints</span></span>  
 <span data-ttu-id="6c78c-123">Ao criar colunas de tipo `xml`, é possível definir nível de coluna ou restrições em nível de tabela.</span><span class="sxs-lookup"><span data-stu-id="6c78c-123">When you create columns of `xml` type, you can define column-level or table-level constraints.</span></span> <span data-ttu-id="6c78c-124">Use restrições nas situações seguintes:</span><span class="sxs-lookup"><span data-stu-id="6c78c-124">Use constraints in the following situations:</span></span>  
  
-   <span data-ttu-id="6c78c-125">Suas regras de negócio não podem ser expressas em esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="6c78c-125">Your business rules cannot be expressed in XML schemas.</span></span> <span data-ttu-id="6c78c-126">Por exemplo, o endereço de entrega de uma floricultura deve estar dentro de 50 milhas do local da empresa.</span><span class="sxs-lookup"><span data-stu-id="6c78c-126">For example, the delivery address of a flower shop must be within 50 miles of its business location.</span></span> <span data-ttu-id="6c78c-127">Isto pode ser escrito como uma restrição na coluna XML.</span><span class="sxs-lookup"><span data-stu-id="6c78c-127">This can be written as a constraint on the XML column.</span></span> <span data-ttu-id="6c78c-128">A restrição pode envolver métodos de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-128">The constraint may involve `xml` data type methods.</span></span>  
  
-   <span data-ttu-id="6c78c-129">A restrição envolve outras colunas XML ou não XML na tabela.</span><span class="sxs-lookup"><span data-stu-id="6c78c-129">Your constraint involves other XML or non-XML columns in the table.</span></span> <span data-ttu-id="6c78c-130">Um exemplo é a imposição da ID de um cliente (`/Customer/@CustId`) localizado em uma instância XML para que corresponda ao valor em uma coluna CustomerID relacional.</span><span class="sxs-lookup"><span data-stu-id="6c78c-130">An example is the enforcement of the ID of a Customer (`/Customer/@CustId`) found in an XML instance to match the value in a relational CustomerID column.</span></span>  
  
 <span data-ttu-id="6c78c-131">Você pode especificar restrições para colunas de tipo de dados `xml` com tipo ou sem-tipo.</span><span class="sxs-lookup"><span data-stu-id="6c78c-131">You can specify constraints for typed or untyped `xml` data type columns.</span></span> <span data-ttu-id="6c78c-132">No entanto não é possível usar os [Métodos de tipo de dados XML](/sql/t-sql/xml/xml-data-type-methods) quando você especifica restrições.</span><span class="sxs-lookup"><span data-stu-id="6c78c-132">However, you cannot use the [XML data type methods](/sql/t-sql/xml/xml-data-type-methods) when you specify constraints.</span></span> <span data-ttu-id="6c78c-133">Observe também que o tipo de dados `xml` não oferece suporte às seguintes restrições de tabela e coluna:</span><span class="sxs-lookup"><span data-stu-id="6c78c-133">Also, note that the `xml` data type does not support the following column and table constraints:</span></span>  
  
-   <span data-ttu-id="6c78c-134">PRIMARY KEY/ FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="6c78c-134">PRIMARY KEY/ FOREIGN KEY</span></span>  
  
-   <span data-ttu-id="6c78c-135">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6c78c-135">UNIQUE</span></span>  
  
-   <span data-ttu-id="6c78c-136">COLLATE</span><span class="sxs-lookup"><span data-stu-id="6c78c-136">COLLATE</span></span>  
  
     <span data-ttu-id="6c78c-137">O XML fornece sua própria codificação.</span><span class="sxs-lookup"><span data-stu-id="6c78c-137">XML provides its own encoding.</span></span> <span data-ttu-id="6c78c-138">Ordenações são aplicadas apenas a tipos de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6c78c-138">Collations apply to string types only.</span></span> <span data-ttu-id="6c78c-139">O tipo de dados `xml` não é um tipo de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6c78c-139">The `xml` data type is not a string type.</span></span> <span data-ttu-id="6c78c-140">No entanto ele tem representação de cadeia de caracteres e permite conversão em tipos de cadeia de caracteres e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="6c78c-140">However, it does have string representation and allows casting to and from string data types.</span></span>  
  
-   <span data-ttu-id="6c78c-141">RULE</span><span class="sxs-lookup"><span data-stu-id="6c78c-141">RULE</span></span>  
  
 <span data-ttu-id="6c78c-142">Uma alternativa ao uso de restrições é criar um wrapper, função definida pelo usuário para encapsular o método de tipo de dados `xml` e especificar função definida pelo usuário na restrição de verificação, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c78c-142">An alternative to using constraints is to create a wrapper, user-defined function to wrap the `xml` data type method and specify user-defined function in the check constraint as shown in the following example.</span></span>  
  
 <span data-ttu-id="6c78c-143">No exemplo a seguir, a restrição na `Col2` especifica que cada instância XML armazenada nessa coluna deve ter um elemento `<ProductDescription>` que contém um atributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="6c78c-143">In the following example, the constraint on `Col2` specifies that each XML instance stored in this column must have a `<ProductDescription>` element that contains a `ProductID` attribute.</span></span> <span data-ttu-id="6c78c-144">Essa restrição é imposta pela função definida pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="6c78c-144">This constraint is enforced by this user-defined function:</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns bit  
AS BEGIN   
RETURN @var.exist('/ProductDescription/@ProductID')  
END  
GO  
```  
  
 <span data-ttu-id="6c78c-145">Observe que o método `exist()` do tipo de dados `xml` retornará `1` se o elemento `<ProductDescription>` na instância contiver o atributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="6c78c-145">Note that the `exist()` method of the `xml` data type returns `1` if the `<ProductDescription>` element in the instance contains the `ProductID` attribute.</span></span> <span data-ttu-id="6c78c-146">Caso contrário, ele retornará `0`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-146">Otherwise, it returns `0`.</span></span>  
  
 <span data-ttu-id="6c78c-147">Agora, você pode criar uma tabela com uma restrição em nível de coluna da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6c78c-147">Now, you can create a table with a column-level constraint as follows:</span></span>  
  
```  
CREATE TABLE T (  
    Col1 int primary key,   
    Col2 xml check(dbo.my_udf(Col2)=1))  
GO  
```  
  
 <span data-ttu-id="6c78c-148">A seguinte inserção é feita com êxito:</span><span class="sxs-lookup"><span data-stu-id="6c78c-148">The following insert succeeds:</span></span>  
  
```  
INSERT INTO T values(1,'<ProductDescription ProductID="1" />')  
```  
  
 <span data-ttu-id="6c78c-149">Por causa da restrição, a seguinte inserção não tem êxito:</span><span class="sxs-lookup"><span data-stu-id="6c78c-149">Because of the constraint, the following insert fails:</span></span>  
  
```  
INSERT INTO T values(1,'<Product />')  
```  
  
## <a name="same-or-different-table"></a><span data-ttu-id="6c78c-150">Mesma tabela ou tabela diferente</span><span class="sxs-lookup"><span data-stu-id="6c78c-150">Same or Different Table</span></span>  
 <span data-ttu-id="6c78c-151">Uma `xml` coluna de tipo de dados pode ser criada em uma tabela que contém outras colunas relacionais ou em uma tabela separada com uma relação de chave estrangeira com uma tabela principal.</span><span class="sxs-lookup"><span data-stu-id="6c78c-151">An `xml` data type column can be created in a table that contains other relational columns, or in a separate table with a foreign key relationship to a main table.</span></span>  
  
 <span data-ttu-id="6c78c-152">Crie uma `xml` coluna de tipo de dados na mesma tabela quando uma das seguintes condições for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="6c78c-152">Create an `xml` data type column in the same table when one of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="6c78c-153">O aplicativo executa recuperação de dados na coluna XML e não requer um índice XML na coluna XML.</span><span class="sxs-lookup"><span data-stu-id="6c78c-153">Your application performs data retrieval on the XML column and does not require an XML index on the XML column.</span></span>  
  
-   <span data-ttu-id="6c78c-154">Você deseja criar um índice XML na coluna de tipo de dados `xml` e a chave primária da tabela principal é a mesma que sua chave de clustering.</span><span class="sxs-lookup"><span data-stu-id="6c78c-154">You want to build an XML index on the `xml` data type column and the primary key of the main table is the same as its clustering key.</span></span> <span data-ttu-id="6c78c-155">Para obter mais informações, veja [Índices XML &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-155">For more information, see [XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span></span>  
  
 <span data-ttu-id="6c78c-156">Crie uma coluna de tipo de dados `xml`na mesma tabela quando um das seguintes condições for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="6c78c-156">Create the `xml` data type column in a separate table if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="6c78c-157">Você deseja criar um índice XML na coluna de tipo de dados `xml`, mas a chave primária da tabela principal é diferente de sua chave de clustering ou a tabela principal não tem uma chave primária ou a tabela principal é um heap (sem chave de clustering).</span><span class="sxs-lookup"><span data-stu-id="6c78c-157">You want to build an XML index on the `xml` data type column, but the primary key of the main table is different from its clustering key, or the main table does not have a primary key, or the main table is a heap (no clustering key).</span></span> <span data-ttu-id="6c78c-158">Isto poderá ser verdade se a tabela principal já existir.</span><span class="sxs-lookup"><span data-stu-id="6c78c-158">This may be true if the main table already exists.</span></span>  
  
-   <span data-ttu-id="6c78c-159">Você não deseja que as verificações de tabela se tornem mais lentas por causa da presença da coluna XML na tabela.</span><span class="sxs-lookup"><span data-stu-id="6c78c-159">You do not want table scans to slow down because of the presence of the XML column in the table.</span></span> <span data-ttu-id="6c78c-160">Isso usará espaço se for armazenado dentro da linha ou fora da linha.</span><span class="sxs-lookup"><span data-stu-id="6c78c-160">This uses space whether it is stored in-row or out-of-row.</span></span>  
  
  
