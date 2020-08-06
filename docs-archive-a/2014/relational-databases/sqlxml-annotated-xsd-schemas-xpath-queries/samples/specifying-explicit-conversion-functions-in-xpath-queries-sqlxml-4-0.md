---
title: Especificando funções de conversão explícitas em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit conversion functions [SQLXML]
- string function
- number function
- XPath queries [SQLXML], explicit conversion functions
ms.assetid: 1111cb5d-2bd9-4bdb-8de2-dc0e47452dd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b4b9bd5f5665c8cb86cb74c1397e2bd06e113fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569286"
---
# <a name="specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="68007-102">Especificando funções de conversão explícitas em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="68007-102">Specifying Explicit Conversion Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="68007-103">Os seguintes exemplos mostram como funções de conversão explícitas são especificadas em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="68007-103">The following examples show how explicit conversion functions are specified in XPath queries.</span></span> <span data-ttu-id="68007-104">As consultas XPath nesses exemplos são especificadas com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="68007-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="68007-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="68007-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="68007-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="68007-106">Examples</span></span>  
  
### <a name="a-use-the-number-explicit-conversion-function"></a><span data-ttu-id="68007-107">a.</span><span class="sxs-lookup"><span data-stu-id="68007-107">A.</span></span> <span data-ttu-id="68007-108">Use a função de conversão explícita number()</span><span class="sxs-lookup"><span data-stu-id="68007-108">Use the number() explicit conversion function</span></span>  
 <span data-ttu-id="68007-109">A função `number()` converte um argumento em um número.</span><span class="sxs-lookup"><span data-stu-id="68007-109">The `number()` function converts an argument to a number.</span></span>  
  
 <span data-ttu-id="68007-110">Supondo que o valor de **ContactID** seja não numérico, a consulta a seguir converte **ContactID** em um número e o compara com o valor 4.</span><span class="sxs-lookup"><span data-stu-id="68007-110">Assuming the value of **ContactID** is nonnumeric, the following query converts **ContactID** to a number and compares it with the value 4.</span></span> <span data-ttu-id="68007-111">Em seguida, a consulta retorna todos os **\<Employee>** elementos filho do nó de contexto com o atributo **ContactID** que tem um valor numérico de 4:</span><span class="sxs-lookup"><span data-stu-id="68007-111">The query then returns all **\<Employee>** element children of the context node with the **ContactID** attribute that has a numeric value of 4:</span></span>  
  
```  
/child::Contact[number(attribute::ContactID)= 4]  
```  
  
 <span data-ttu-id="68007-112">Um atalho para o `attribute` eixo (@) pode ser especificado e, como o `child` eixo é o padrão, ele pode ser omitido da consulta:</span><span class="sxs-lookup"><span data-stu-id="68007-112">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[number(@ContactID) = 4]  
```  
  
 <span data-ttu-id="68007-113">Em termos relacionais, a consulta retorna um funcionário com um **ContactID** de 4.</span><span class="sxs-lookup"><span data-stu-id="68007-113">In relational terms, the query returns an employee with a **ContactID** of 4.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="68007-114">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="68007-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="68007-115">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="68007-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="68007-116">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="68007-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="68007-117">Crie o seguinte modelo (ExplicitConversionA.xml) e salve-o no diretório onde SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="68007-117">Create the following template (ExplicitConversionA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact[number(@ContactID)=4]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="68007-118">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="68007-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="68007-119">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68007-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="68007-120">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="68007-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="68007-121">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="68007-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="68007-122">O conjunto de resultados da execução do modelo é:</span><span class="sxs-lookup"><span data-stu-id="68007-122">The result set for this template execution is:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
### <a name="b-use-the-string-explicit-conversion-function"></a><span data-ttu-id="68007-123">B.</span><span class="sxs-lookup"><span data-stu-id="68007-123">B.</span></span> <span data-ttu-id="68007-124">Use a função de conversão explícita string()</span><span class="sxs-lookup"><span data-stu-id="68007-124">Use the string() explicit conversion function</span></span>  
 <span data-ttu-id="68007-125">A função `string()` converte um argumento em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="68007-125">The `string()` function converts an argument to a string.</span></span>  
  
 <span data-ttu-id="68007-126">A consulta a seguir converte **ContactID** em uma cadeia de caracteres e a compara com o valor de cadeia de caracteres "4".</span><span class="sxs-lookup"><span data-stu-id="68007-126">The following query converts **ContactID** to a string and compares it with the string value "4".</span></span> <span data-ttu-id="68007-127">A consulta retorna todos os **\<Employee>** elementos filho do nó de contexto com um **ContactID** com um valor de cadeia de caracteres de "4":</span><span class="sxs-lookup"><span data-stu-id="68007-127">The query returns all **\<Employee>** element children of the context node with a **ContactID** with a string value of "4":</span></span>  
  
```  
/child::Contact[string(attribute::ContactID)="4"]  
```  
  
 <span data-ttu-id="68007-128">Um atalho para o `attribute` eixo (@) pode ser especificado e, como o `child` eixo é o padrão, ele pode ser omitido da consulta:</span><span class="sxs-lookup"><span data-stu-id="68007-128">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[string(@ContactID)="4"]  
```  
  
 <span data-ttu-id="68007-129">Funcionalmente, essa consulta retorna os mesmos resultados da consulta de exemplo anterior, ainda que a avaliação seja feita em relação ao valor de uma cadeia de caracteres, e não um valor numérico (ou seja, o número 4).</span><span class="sxs-lookup"><span data-stu-id="68007-129">Functionally, this query returns the same results as the previous example query, though the evaluation is done against a string value and not the numeric value (that is, the number 4).</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="68007-130">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="68007-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="68007-131">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="68007-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="68007-132">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="68007-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="68007-133">Crie o seguinte modelo (ExplicitConversionB.xml) e salve-o no diretório onde SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="68007-133">Create the following template (ExplicitConversionB.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Contact[string(@ContactID)="4"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="68007-134">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="68007-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="68007-135">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68007-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="68007-136">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="68007-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="68007-137">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="68007-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="68007-138">Aqui está o conjunto de resultados da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="68007-138">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
  
