---
title: Expressões de consultas e nomes de recursos uniformes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- query expressions
- unique resource names
- URN
ms.assetid: e0d30dbe-7daf-47eb-8412-1b96792b6fb9
author: stevestein
ms.author: sstein
ms.openlocfilehash: db6e311dd7d8a824b0e2f22e538e15eefa9fd9ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573159"
---
# <a name="query-expressions-and-uniform-resource-names"></a><span data-ttu-id="81fb6-102">Expressões de consultas e nomes de recursos uniformes</span><span class="sxs-lookup"><span data-stu-id="81fb6-102">Query Expressions and Uniform Resource Names</span></span>
  <span data-ttu-id="81fb6-103">Os modelos SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object) e os snap-ins do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell utilizam dois tipos de cadeia de caracteres de expressão semelhantes às expressões XPath.</span><span class="sxs-lookup"><span data-stu-id="81fb6-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object (SMO) models and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins use two types of expression strings that are similar to XPath expressions.</span></span> <span data-ttu-id="81fb6-104">As expressões de consulta são cadeias de caracteres que especificam um conjunto de critérios para enumerar um ou mais objetos em uma hierarquia de modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="81fb6-104">Query expressions are strings that specify a set of criteria used to enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="81fb6-105">Um URN (Uniform Resource Name) é um tipo específico de cadeia de caracteres de expressão de consulta que identifica exclusivamente um único objeto.</span><span class="sxs-lookup"><span data-stu-id="81fb6-105">A Uniform Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81fb6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="81fb6-106">Syntax</span></span>  
  
```
      Object1  
      [<FilterExpression1>]/ ... /ObjectN[<FilterExpressionN>]<FilterExpression>::=  
<PropertyExpression> [and <PropertyExpression>][...n]  
  
<PropertyExpression>::=@BooleanPropertyName=true()  
 | @BooleanPropertyName=false()  
 | contains(@StringPropertyName, 'PatternString')  
  | @StringPropertyName='String'  
 | @DatePropertyName=datetime('DateString')  
 | is_null(@PropertyName)  
 | not(<PropertyExpression>)  
```  
  
## <a name="arguments"></a><span data-ttu-id="81fb6-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="81fb6-107">Arguments</span></span>  
 <span data-ttu-id="81fb6-108">*Objeto*</span><span class="sxs-lookup"><span data-stu-id="81fb6-108">*Object*</span></span>  
 <span data-ttu-id="81fb6-109">Especifica o tipo de objeto que é representado no nó da cadeia de caracteres de expressão.</span><span class="sxs-lookup"><span data-stu-id="81fb6-109">Specifies the type of object that is represented at that node of the expression string.</span></span> <span data-ttu-id="81fb6-110">Cada objeto representa uma classe de coleção desses namespaces de modelos de objetos SMO:</span><span class="sxs-lookup"><span data-stu-id="81fb6-110">Each object represents a collection class from these SMO object model namespaces:</span></span>  
  
 <xref:Microsoft.SqlServer.Management.Smo>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Agent>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Mail>  
  
 <xref:Microsoft.SqlServer.Management.Dmf>  
  
 <xref:Microsoft.SqlServer.Management.Facets>  
  
 <xref:Microsoft.SqlServer.Management.RegisteredServers>  
  
 <xref:Microsoft.SqlServer.Management.Smo.RegSvrEnum>  
  
 <span data-ttu-id="81fb6-111">Por exemplo, especifique o Servidor para a classe **ServerCollection** , o Banco de dados para a classe **DatabaseCollection** .</span><span class="sxs-lookup"><span data-stu-id="81fb6-111">For example, specify Server for the **ServerCollection** class, Database for the **DatabaseCollection** class.</span></span>  
  
 <span data-ttu-id="81fb6-112">\@*PropertyName*</span><span class="sxs-lookup"><span data-stu-id="81fb6-112">\@*PropertyName*</span></span>  
 <span data-ttu-id="81fb6-113">Especifica o nome de uma das propriedades da classe associada ao objeto especificado em *Objeto*.</span><span class="sxs-lookup"><span data-stu-id="81fb6-113">Specifies the name of one of the properties of the class that is associated with the object specified in *Object*.</span></span> <span data-ttu-id="81fb6-114">O nome da propriedade deve ser prefixado com o caractere \@.</span><span class="sxs-lookup"><span data-stu-id="81fb6-114">The name of the property must be prefixed with the \@ character.</span></span> <span data-ttu-id="81fb6-115">Por exemplo, especifique \@ IsAnsiNull para a propriedade de classe de **banco de dados** **IsAnsiNull**.</span><span class="sxs-lookup"><span data-stu-id="81fb6-115">For example, specify \@IsAnsiNull for the **Database** class property **IsAnsiNull**.</span></span>  
  
 <span data-ttu-id="81fb6-116">\@*BooleanPropertyName*= true ()</span><span class="sxs-lookup"><span data-stu-id="81fb6-116">\@*BooleanPropertyName*=true()</span></span>  
 <span data-ttu-id="81fb6-117">Enumera todos os objetos em que a propriedade booliana especificada está definida como TRUE.</span><span class="sxs-lookup"><span data-stu-id="81fb6-117">Enumerates all objects where the specified Boolean property is set to TRUE.</span></span>  
  
 <span data-ttu-id="81fb6-118">\@*BooleanPropertyName*= false ()</span><span class="sxs-lookup"><span data-stu-id="81fb6-118">\@*BooleanPropertyName*=false()</span></span>  
 <span data-ttu-id="81fb6-119">Enumera todos os objetos em que a propriedade booliana especificada está definida como FALSE.</span><span class="sxs-lookup"><span data-stu-id="81fb6-119">Enumerates all objects where the specified Boolean property is set to FALSE.</span></span>  
  
 <span data-ttu-id="81fb6-120">contains(\@*StringPropertyName*, '*PatternString*')</span><span class="sxs-lookup"><span data-stu-id="81fb6-120">contains(\@*StringPropertyName*, '*PatternString*')</span></span>  
 <span data-ttu-id="81fb6-121">Enumera todos os objetos em que a propriedade da cadeia de caracteres especificada contém pelo menos uma ocorrência do conjunto de caracteres especificado em “*PatternString*”.</span><span class="sxs-lookup"><span data-stu-id="81fb6-121">Enumerates all objects where the specified string property contains at least one occurrence of the set of characters that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="81fb6-122">\@*StringPropertyName*='*PatternString*'</span><span class="sxs-lookup"><span data-stu-id="81fb6-122">\@*StringPropertyName*='*PatternString*'</span></span>  
 <span data-ttu-id="81fb6-123">Enumera todos os objetos em que o valor da propriedade da cadeia de caracteres especificada é exatamente igual ao padrão de caractere especificado em “*PatternString*”.</span><span class="sxs-lookup"><span data-stu-id="81fb6-123">Enumerates all objects where the value of the specified string property is exactly the same as the character pattern that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="81fb6-124">\@*DatePropertyName*= datetime('*DateString*')</span><span class="sxs-lookup"><span data-stu-id="81fb6-124">\@*DatePropertyName*= datetime('*DateString*')</span></span>  
 <span data-ttu-id="81fb6-125">Enumera todos os objetos em que o valor da propriedade de data especificada corresponde à data especificada em “*DateString*”.</span><span class="sxs-lookup"><span data-stu-id="81fb6-125">Enumerates all objects where the value of the specified date property matches the date that is specified in '*DateString*'.</span></span> <span data-ttu-id="81fb6-126">*DateString* deve seguir o formato aaaa-mm-dd hh:min:ss.mmm</span><span class="sxs-lookup"><span data-stu-id="81fb6-126">*DateString* must follow the format yyyy-mm-dd hh:mi:ss.mmm</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81fb6-127">yyyy</span><span class="sxs-lookup"><span data-stu-id="81fb6-127">yyyy</span></span>|<span data-ttu-id="81fb6-128">Ano com quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="81fb6-128">Four digit year.</span></span>|  
|<span data-ttu-id="81fb6-129">MM</span><span class="sxs-lookup"><span data-stu-id="81fb6-129">mm</span></span>|<span data-ttu-id="81fb6-130">Mês com dois dígitos (01 a 12).</span><span class="sxs-lookup"><span data-stu-id="81fb6-130">Two digit month (01 through 12).</span></span>|  
|<span data-ttu-id="81fb6-131">dd</span><span class="sxs-lookup"><span data-stu-id="81fb6-131">dd</span></span>|<span data-ttu-id="81fb6-132">Dia com dois dígitos (01 a 31).</span><span class="sxs-lookup"><span data-stu-id="81fb6-132">Two digit date (01 through 31).</span></span>|  
|<span data-ttu-id="81fb6-133">hh</span><span class="sxs-lookup"><span data-stu-id="81fb6-133">hh</span></span>|<span data-ttu-id="81fb6-134">Hora com dois dígitos usando o formato de 24 horas (01 a 23).</span><span class="sxs-lookup"><span data-stu-id="81fb6-134">Two digit hour using a 24 hour clock (01 through 23).</span></span>|  
|<span data-ttu-id="81fb6-135">min</span><span class="sxs-lookup"><span data-stu-id="81fb6-135">mi</span></span>|<span data-ttu-id="81fb6-136">Minutos com dois dígitos (01 a 59).</span><span class="sxs-lookup"><span data-stu-id="81fb6-136">Two digit minutes (01 through 59).</span></span>|  
|<span data-ttu-id="81fb6-137">ss</span><span class="sxs-lookup"><span data-stu-id="81fb6-137">ss</span></span>|<span data-ttu-id="81fb6-138">Segundos com dois dígitos (01 a 59).</span><span class="sxs-lookup"><span data-stu-id="81fb6-138">Two digit seconds (01 through 59).</span></span>|  
|<span data-ttu-id="81fb6-139">mmm</span><span class="sxs-lookup"><span data-stu-id="81fb6-139">mmm</span></span>|<span data-ttu-id="81fb6-140">Número de milissegundos (001 a 999).</span><span class="sxs-lookup"><span data-stu-id="81fb6-140">Number of milliseconds (001 through 999).</span></span>|  
  
 <span data-ttu-id="81fb6-141">As datas especificadas nesse formato podem ser avaliadas em relação a qualquer formato de data armazenado no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81fb6-141">The dates that are specified in this format can be evaluated against any date format that is stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="81fb6-142">is_null(\@*PropertyName*)</span><span class="sxs-lookup"><span data-stu-id="81fb6-142">is_null(\@*PropertyName*)</span></span>  
 <span data-ttu-id="81fb6-143">Enumera todos os objetos em que a propriedade especificada tenha um valor NULL.</span><span class="sxs-lookup"><span data-stu-id="81fb6-143">Enumerates all objects where the specified property has a value of NULL.</span></span>  
  
 <span data-ttu-id="81fb6-144">Não ( \<*PropertyExpression*> )</span><span class="sxs-lookup"><span data-stu-id="81fb6-144">not(\<*PropertyExpression*>)</span></span>  
 <span data-ttu-id="81fb6-145">Nega o valor de avaliação de *PropertyExpression*, enumerando todos os objetos que não correspondem à condição especificada em *PropertyExpression*.</span><span class="sxs-lookup"><span data-stu-id="81fb6-145">Negates the evaluation value of the *PropertyExpression*, enumerating all objects that do not match the condition specified in *PropertyExpression*.</span></span> <span data-ttu-id="81fb6-146">Por exemplo, not(contains(\@Name, 'xyz')) enumera todos os objetos que não têm a cadeia de caracteres xyz em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="81fb6-146">For example, not(contains(\@Name, 'xyz')) enumerates all objects that do not have the string xyz in their names.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81fb6-147">Comentários</span><span class="sxs-lookup"><span data-stu-id="81fb6-147">Remarks</span></span>  
 <span data-ttu-id="81fb6-148">Expressões de consulta são cadeias de caracteres que enumeram os nós em uma hierarquia de modelos SMO.</span><span class="sxs-lookup"><span data-stu-id="81fb6-148">Query expressions are strings that enumerate the nodes in an SMO model hierarchy.</span></span> <span data-ttu-id="81fb6-149">Cada nó tem uma expressão de filtro que especifica os critérios de determinação dos objetos desse nó que são enumerados.</span><span class="sxs-lookup"><span data-stu-id="81fb6-149">Each node has a filter expression that specifies the criteria for determining which objects at that node are enumerated.</span></span> <span data-ttu-id="81fb6-150">As expressões de consultas são modeladas na linguagem de expressão XPath.</span><span class="sxs-lookup"><span data-stu-id="81fb6-150">Query expressions are modeled on the XPath expression language.</span></span> <span data-ttu-id="81fb6-151">As expressões de consulta implementam um pequeno subconjunto de expressões com suporte em XPath e também possuem algumas expressões que não são encontradas em XPath.</span><span class="sxs-lookup"><span data-stu-id="81fb6-151">Query expressions implement a small subset of the expressions that are supported by XPath, and also have some extensions that are not found in XPath.</span></span> <span data-ttu-id="81fb6-152">As expressões Xpath são cadeias de caracteres que especificam um conjunto de critérios usados para enumerar uma ou mais marcas em um documento XML.</span><span class="sxs-lookup"><span data-stu-id="81fb6-152">XPath expressions are strings that specify a set of criteria that are used to enumerate one or more of the tags in an XML document.</span></span> <span data-ttu-id="81fb6-153">Para obter mais informações sobre XPath, consulte [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span><span class="sxs-lookup"><span data-stu-id="81fb6-153">For more information about XPath, see [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span></span>  
  
 <span data-ttu-id="81fb6-154">As expressões de consulta devem iniciar com uma referência absoluta ao objeto Servidor.</span><span class="sxs-lookup"><span data-stu-id="81fb6-154">Query expressions must start with an absolute reference to the Server object.</span></span> <span data-ttu-id="81fb6-155">Não são permitidas expressões relativas com uma / à esquerda.</span><span class="sxs-lookup"><span data-stu-id="81fb6-155">Relative expressions with a leading / are not allowed.</span></span> <span data-ttu-id="81fb6-156">A sequência de objetos especificados em uma expressão de consulta deve seguir a hierarquia dos objetos de coleção do modelo de objetos associado.</span><span class="sxs-lookup"><span data-stu-id="81fb6-156">The sequence of objects that are specified in a query expression must follow the hierarchy of collection objects in the associated object model.</span></span> <span data-ttu-id="81fb6-157">Por exemplo, uma expressão de consulta que faz referência a objetos no namespace Microsoft.SqlServer.Management.Smo deve começar com um nó Servidor, seguido por um nó Banco de Dados e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="81fb6-157">For example, a query expression that references objects in the Microsoft.SqlServer.Management.Smo namespace must start with a Server node followed by a Database node, and so on.</span></span>  
  
 <span data-ttu-id="81fb6-158">Se um *\<FilterExpression>* não for especificado para um objeto, todos os objetos desse nó serão enumerados.</span><span class="sxs-lookup"><span data-stu-id="81fb6-158">If a *\<FilterExpression>* is not specified for an object, all the objects at that node are enumerated.</span></span>  
  
## <a name="uniform-resource-names-urn"></a><span data-ttu-id="81fb6-159">URN (Uniform Resource Names)</span><span class="sxs-lookup"><span data-stu-id="81fb6-159">Uniform Resource Names (URN)</span></span>  
 <span data-ttu-id="81fb6-160">URNs são um subconjunto de expressões de consulta.</span><span class="sxs-lookup"><span data-stu-id="81fb6-160">URNs are a subset of query expressions.</span></span> <span data-ttu-id="81fb6-161">Cada URN forma uma referência totalmente qualificada a um único objeto.</span><span class="sxs-lookup"><span data-stu-id="81fb6-161">Each URN forms a fully-qualified reference to a single object.</span></span> <span data-ttu-id="81fb6-162">Um URN típico usa a propriedade Nome para identificar um único objeto em cada nó.</span><span class="sxs-lookup"><span data-stu-id="81fb6-162">A typical URN uses the Name property to identify a single object at each node.</span></span> <span data-ttu-id="81fb6-163">Por exemplo, este URN faz referência a uma coluna específica:</span><span class="sxs-lookup"><span data-stu-id="81fb6-163">For example, this URN refers to a specific column:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[@Name='SalesPerson' and @Schema='Sales']/Column[@Name='SalesPersonID']  
```  
  
## <a name="examples"></a><span data-ttu-id="81fb6-164">Exemplos</span><span class="sxs-lookup"><span data-stu-id="81fb6-164">Examples</span></span>  
  
### <a name="a-enumerating-objects-using-false"></a><span data-ttu-id="81fb6-165">a.</span><span class="sxs-lookup"><span data-stu-id="81fb6-165">A.</span></span> <span data-ttu-id="81fb6-166">Enumerando objetos usando false()</span><span class="sxs-lookup"><span data-stu-id="81fb6-166">Enumerating objects using false()</span></span>  
 <span data-ttu-id="81fb6-167">Esta expressão de consulta enumera todos os bancos de dados que têm o atributo **AutoClose** definido como false na instância padrão em **MyComputer**.</span><span class="sxs-lookup"><span data-stu-id="81fb6-167">This query expression enumerates all the databases that have the **AutoClose** attribute set to false in the default instance on **MyComputer**.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@AutoClose=false()]  
```  
  
### <a name="b-enumerating-objects-using-contains"></a><span data-ttu-id="81fb6-168">B.</span><span class="sxs-lookup"><span data-stu-id="81fb6-168">B.</span></span> <span data-ttu-id="81fb6-169">Enumerando objetos usando contains</span><span class="sxs-lookup"><span data-stu-id="81fb6-169">Enumerating objects using contains</span></span>  
 <span data-ttu-id="81fb6-170">Esta expressão de consulta enumera todos os bancos de dados que não diferenciam maiúsculas de minúsculas e têm o caractere 'm' no nome.</span><span class="sxs-lookup"><span data-stu-id="81fb6-170">This query expression enumerates all the databases that are case-insensitive and have the character 'm' in their name.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@CaseSensitive=false() and contains(@Name, 'm')]   
```  
  
### <a name="c-enumerating-objects-using-not"></a><span data-ttu-id="81fb6-171">C.</span><span class="sxs-lookup"><span data-stu-id="81fb6-171">C.</span></span> <span data-ttu-id="81fb6-172">Enumerando objetos usando not</span><span class="sxs-lookup"><span data-stu-id="81fb6-172">Enumerating objects using not</span></span>  
 <span data-ttu-id="81fb6-173">Esta expressão de consulta enumera todas as tabelas [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] que não estão no esquema de **Produção** e que contêm a palavra Histórico no nome da tabela:</span><span class="sxs-lookup"><span data-stu-id="81fb6-173">This query expression enumerates all of [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tables that are not in the **Production** schema and contain the word History in the table name:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[not(@Schema='Production') and contains(@Name, 'History')]  
```  
  
### <a name="d-not-supplying-a-filter-expression-for-the-final-node"></a><span data-ttu-id="81fb6-174">D.</span><span class="sxs-lookup"><span data-stu-id="81fb6-174">D.</span></span> <span data-ttu-id="81fb6-175">Não fornecendo uma expressão de filtro para o nó final</span><span class="sxs-lookup"><span data-stu-id="81fb6-175">Not supplying a filter expression for the final node</span></span>  
 <span data-ttu-id="81fb6-176">Esta expressão de consulta enumera todas as colunas na tabela **AdventureWorks2012.Sales.SalesPerson** :</span><span class="sxs-lookup"><span data-stu-id="81fb6-176">This query expression enumerates all the columns in the **AdventureWorks2012.Sales.SalesPerson** table:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@Schema='Sales' and @Name='SalesPerson']/Columns  
```  
  
### <a name="e-enumerating-objects-using-datetime"></a><span data-ttu-id="81fb6-177">E.</span><span class="sxs-lookup"><span data-stu-id="81fb6-177">E.</span></span> <span data-ttu-id="81fb6-178">Enumerando objetos usando datetime</span><span class="sxs-lookup"><span data-stu-id="81fb6-178">Enumerating objects using datetime</span></span>  
 <span data-ttu-id="81fb6-179">Esta expressão de consulta enumera todas as tabelas que são criadas no banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] em um momento específico:</span><span class="sxs-lookup"><span data-stu-id="81fb6-179">This query expression enumerates all the tables that are created in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database at a specific time:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@CreateDate=datetime('2008-03-21 19:49:32.647')]  
```  
  
### <a name="f-enumerating-objects-using-is_null"></a><span data-ttu-id="81fb6-180">F.</span><span class="sxs-lookup"><span data-stu-id="81fb6-180">F.</span></span> <span data-ttu-id="81fb6-181">Enumerando objetos usando is_null</span><span class="sxs-lookup"><span data-stu-id="81fb6-181">Enumerating objects using is_null</span></span>  
 <span data-ttu-id="81fb6-182">Esta expressão de consulta enumera todas as tabelas do banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] que não têm o NULL para a última propriedade modificada:</span><span class="sxs-lookup"><span data-stu-id="81fb6-182">This query expression enumerates all the tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database that do not have NULL for their date last modified property:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[Not(is_null(@DateLastModified))]  
```  
  
## <a name="see-also"></a><span data-ttu-id="81fb6-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81fb6-183">See Also</span></span>  
 <span data-ttu-id="81fb6-184">[Cmdlet Invoke-PolicyEvaluation](../database-engine/invoke-policyevaluation-cmdlet.md) </span><span class="sxs-lookup"><span data-stu-id="81fb6-184">[Invoke-PolicyEvaluation cmdlet](../database-engine/invoke-policyevaluation-cmdlet.md) </span></span>  
 [<span data-ttu-id="81fb6-185">Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="81fb6-185">SQL Server Audit &#40;Database Engine&#41;</span></span>](../relational-databases/security/auditing/sql-server-audit-database-engine.md)  
