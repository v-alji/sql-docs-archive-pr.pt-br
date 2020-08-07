---
title: 'Especificando a profundidade em relações recursivas usando SQL: Max-Depth | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- max-depth annotation
- XPath queries [SQLXML], recursive relationships
- depth in recursive relationships [SQLXML]
- annotated XSD schemas, recursive relationships
- relationships [SQLXML], recursive relationships
- self joins
- recursive relationships [SQLXML]
- recursion [SQLXML]
- sql:max-depth
- recursive joins [SQLXML]
ms.assetid: 0ffdd57d-dc30-44d9-a8a0-f21cadedb327
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e3ccb2de9c7b2ac8f8702b52aa990d755620e46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575048"
---
# <a name="specifying-depth-in-recursive-relationships-by-using-sqlmax-depth"></a><span data-ttu-id="0eda9-102">Especificando a profundidade em relações recursivas usando sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="0eda9-102">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>
  <span data-ttu-id="0eda9-103">Em bancos de dados relacionais, quando uma tabela está envolvida em uma relação com si mesma, a relação é chamada de relação recursiva.</span><span class="sxs-lookup"><span data-stu-id="0eda9-103">In relational databases, when a table is involved in a relationship with itself, it is called a recursive relationship.</span></span> <span data-ttu-id="0eda9-104">Por exemplo, em uma relação supervisor-supervisionado, uma tabela que armazena os registros dos funcionários está envolvida em uma relação com si mesma.</span><span class="sxs-lookup"><span data-stu-id="0eda9-104">For example, in a supervisor-supervisee relationship, a table storing employee records is involved in a relationship with itself.</span></span> <span data-ttu-id="0eda9-105">Nesse caso, a tabela de funcionários desempenha a função de supervisor em um lado da relação e a mesma tabela desempenha a função de supervisionado no outro lado.</span><span class="sxs-lookup"><span data-stu-id="0eda9-105">In this case, the employees table plays a role of supervisor on one side of the relationship, and the same table plays a role of supervisee on the other side.</span></span>  
  
 <span data-ttu-id="0eda9-106">O mapeamento de esquemas pode incluir relações recursivas, em que um elemento e seu ancestral são do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="0eda9-106">Mapping schemas can include recursive relationships where an element and its ancestor are of the same type.</span></span>  
  
## <a name="example-a"></a><span data-ttu-id="0eda9-107">Exemplo A</span><span class="sxs-lookup"><span data-stu-id="0eda9-107">Example A</span></span>  
 <span data-ttu-id="0eda9-108">Considere a seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="0eda9-108">Consider the following table:</span></span>  
  
```  
Emp (EmployeeID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="0eda9-109">Nessa tabela, a coluna ReportsTo armazena a ID de funcionário do gerente.</span><span class="sxs-lookup"><span data-stu-id="0eda9-109">In this table, the ReportsTo column stores the employee ID of the manager.</span></span>  
  
 <span data-ttu-id="0eda9-110">Suponha que você deseje gerar uma hierarquia XML de funcionários na qual o funcionário gerente esteja no topo da hierarquia e na qual os funcionários subordinados a esse gerente apareçam na hierarquia correspondente como mostrado no exemplo de fragmento XML a seguir.</span><span class="sxs-lookup"><span data-stu-id="0eda9-110">Assume that you want to generate an XML hierarchy of employees in which the manager employee is at the top of the hierarchy, and in which the employees that report to that manager appear in the corresponding hierarchy as shown in the following sample XML fragment.</span></span> <span data-ttu-id="0eda9-111">O que este fragmento mostra é a *árvore recursiva* para o funcionário 1.</span><span class="sxs-lookup"><span data-stu-id="0eda9-111">What this fragment shows is the *recursive tree* for employee 1.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
     <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
     <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
        <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
          <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
...  
...  
</root>  
```  
  
 <span data-ttu-id="0eda9-112">Nesse fragmento, o funcionário 5 está subordinado ao funcionário 4, o funcionário 4 está subordinado ao funcionário 3 e os funcionários 3 e 2 estão subordinados ao funcionário 1.</span><span class="sxs-lookup"><span data-stu-id="0eda9-112">In this fragment, employee 5 reports to employee 4, employee 4 reports to employee 3, and employees 3 and 2 reports to employee 1.</span></span>  
  
 <span data-ttu-id="0eda9-113">Para gerar esse resultado, você pode usar o esquema XSD a seguir e especificar uma consulta XPath para ele.</span><span class="sxs-lookup"><span data-stu-id="0eda9-113">To produce this result, you can use the following XSD schema and specify an XPath query against it.</span></span> <span data-ttu-id="0eda9-114">O esquema descreve um **\<Emp>** elemento do tipo EmployeeType, que consiste em um **\<Emp>** elemento filho do mesmo tipo, EmployeeType.</span><span class="sxs-lookup"><span data-stu-id="0eda9-114">The schema describes an **\<Emp>** element of type EmployeeType, consisting of an **\<Emp>** child element of the same type, EmployeeType.</span></span> <span data-ttu-id="0eda9-115">Essa é uma relação recursiva (o elemento e seu ancestral são do mesmo tipo).</span><span class="sxs-lookup"><span data-stu-id="0eda9-115">This is a recursive relationship (the element and its ancestor are of the same type).</span></span> <span data-ttu-id="0eda9-116">Além disso, o esquema usa um **\<sql:relationship>** para descrever a relação pai-filho entre o supervisor e o Supervisionador.</span><span class="sxs-lookup"><span data-stu-id="0eda9-116">In addition, the schema uses a **\<sql:relationship>** to describe the parent-child relationship between the supervisor and supervisee.</span></span> <span data-ttu-id="0eda9-117">Observe que, nesse caso **\<sql:relationship>** , EMP é o pai e a tabela filho.</span><span class="sxs-lookup"><span data-stu-id="0eda9-117">Note that in this **\<sql:relationship>**, Emp is both the parent and the child table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="6" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="0eda9-118">Como a relação é recursiva, você precisa de algum modo de especificar a profundidade de recursão no esquema.</span><span class="sxs-lookup"><span data-stu-id="0eda9-118">Because the relationship is recursive, you need some way to specify the depth of recursion in the schema.</span></span> <span data-ttu-id="0eda9-119">Caso contrário, o resultado será uma recursão infinita (funcionário subordinado a funcionário subordinado a funcionário e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="0eda9-119">Otherwise, the result will be an endless recursion (employee reporting to employee reporting to employee, and so on).</span></span> <span data-ttu-id="0eda9-120">A anotação `sql:max-depth` permite especificar o nível de profundidade da recursão.</span><span class="sxs-lookup"><span data-stu-id="0eda9-120">The `sql:max-depth` annotation allows you to specify how deep in the recursion to go.</span></span> <span data-ttu-id="0eda9-121">Nesse exemplo específico, para especificar um valor para `sql:max-depth`, você precisa saber o nível de profundidade da hierarquia de gerenciamento na empresa.</span><span class="sxs-lookup"><span data-stu-id="0eda9-121">In this particular example, to specify a value for `sql:max-depth`, you must know how deep the management hierarchy goes in the company.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0eda9-122">O esquema especifica a anotação `sql:limit-field`, mas não especifica a anotação `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="0eda9-122">The schema specifies the `sql:limit-field` annotation, but does not specify the `sql:limit-value` annotation.</span></span> <span data-ttu-id="0eda9-123">Isso limita o nó superior da hierarquia resultante apenas aos funcionários que não estão subordinados a ninguém.</span><span class="sxs-lookup"><span data-stu-id="0eda9-123">This limits the top node in the resulting hierarchy to only those employees who do not report to anyone.</span></span> <span data-ttu-id="0eda9-124">(Reportto é nulo.) Especificar `sql:limit-field` e não especificar `sql:limit-value` (que usa como padrão nulo) a anotação realiza isso.</span><span class="sxs-lookup"><span data-stu-id="0eda9-124">(ReportsTo is NULL.) Specifying `sql:limit-field` and not specifying `sql:limit-value` (which defaults to NULL) annotation accomplishes this.</span></span> <span data-ttu-id="0eda9-125">Se você desejar que o XML resultante inclua todas as árvores de subordinação (a árvore de subordinação de cada funcionário da tabela), remova a anotação `sql:limit-field` do esquema.</span><span class="sxs-lookup"><span data-stu-id="0eda9-125">If you want the resulting XML to include every possible reporting tree (the reporting tree for every employee in the table), remove the `sql:limit-field` annotation from the schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0eda9-126">O procedimento a seguir usa o banco de dados tempdb.</span><span class="sxs-lookup"><span data-stu-id="0eda9-126">The following procedure uses the tempdb database.</span></span>  
  
#### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="0eda9-127">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="0eda9-127">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="0eda9-128">Crie uma tabela de exemplo chamada Emp no banco de dados tempdb para o qual a raiz virtual aponta.</span><span class="sxs-lookup"><span data-stu-id="0eda9-128">Create a sample table called Emp in the tempdb database to which the virtual root points.</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Emp (  
           EmployeeID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    ```  
  
2.  <span data-ttu-id="0eda9-129">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="0eda9-129">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Emp values (1, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Emp values (2, 'Andrew', 'Fuller',1)  
    INSERT INTO Emp values (3, 'Janet', 'Leverling',1)  
    INSERT INTO Emp values (4, 'Margaret', 'Peacock',3)  
    INSERT INTO Emp values (5, 'Steven', 'Devolio',4)  
    INSERT INTO Emp values (6, 'Nancy', 'Buchanan',5)  
    INSERT INTO Emp values (7, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="0eda9-130">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0eda9-130">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="0eda9-131">Salve o arquivo como maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="0eda9-131">Save the file as maxDepth.xml.</span></span>  
  
4.  <span data-ttu-id="0eda9-132">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0eda9-132">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="0eda9-133">Salve o arquivo como maxDepthT.xml no mesmo diretório onde você salvou maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="0eda9-133">Save the file as maxDepthT.xml in the same directory where you saved maxDepth.xml.</span></span> <span data-ttu-id="0eda9-134">A consulta no modelo retorna todos os funcionários na tabela Emp.</span><span class="sxs-lookup"><span data-stu-id="0eda9-134">The query in the template returns all the employees in the Emp table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="maxDepth.xml">  
        /Emp  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="0eda9-135">O caminho de diretório especificado para o esquema de mapeamento (maxDepth.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="0eda9-135">The directory path specified for the mapping schema (maxDepth.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="0eda9-136">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0eda9-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\maxDepth.xml"  
    ```  
  
5.  <span data-ttu-id="0eda9-137">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="0eda9-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="0eda9-138">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0eda9-138">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="0eda9-139">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="0eda9-139">This is the result:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
    <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
      <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
        <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
          <Emp FirstName="Nancy" EmployeeID="6" LastName="Buchanan">  
            <Emp FirstName="Michael" EmployeeID="7" LastName="Suyama" />   
          </Emp>  
        </Emp>  
      </Emp>  
    </Emp>  
  </Emp>  
</root>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0eda9-140">Para produzir profundidades diferentes de hierarquias no resultado, altere o valor da anotação `sql:max-depth` no esquema e execute o modelo novamente após cada alteração.</span><span class="sxs-lookup"><span data-stu-id="0eda9-140">To produce different depths of hierarchies in the result, change the value of the `sql:max-depth` annotation in the schema and execute the template again after each change.</span></span>  
  
 <span data-ttu-id="0eda9-141">No esquema anterior, todos os **\<Emp>** elementos tinham exatamente o mesmo conjunto de atributos (**EmployeeID**, **FirstName**e **LastName**).</span><span class="sxs-lookup"><span data-stu-id="0eda9-141">In the previous schema, all the **\<Emp>** elements had exactly the same set of attributes (**EmployeeID**, **FirstName**, and **LastName**).</span></span> <span data-ttu-id="0eda9-142">O esquema a seguir foi ligeiramente modificado para retornar um atributo **reportes** adicional para todos os **\<Emp>** elementos que se reportam a um gerente.</span><span class="sxs-lookup"><span data-stu-id="0eda9-142">The following schema has been slightly modified to return an additional **ReportsTo** attribute for all the **\<Emp>** elements that report to a manager.</span></span>  
  
 <span data-ttu-id="0eda9-143">Por exemplo, este fragmento XML mostra os subordinados do funcionário 1:</span><span class="sxs-lookup"><span data-stu-id="0eda9-143">For example, this XML fragment shows the subordinates of employee 1:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
<Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2"   
       ReportsTo="1" LastName="Fuller" />   
  <Emp FirstName="Janet" EmployeeID="3"   
       ReportsTo="1" LastName="Leverling">  
...  
...  
```  
  
 <span data-ttu-id="0eda9-144">Este é o esquema revisado:</span><span class="sxs-lookup"><span data-stu-id="0eda9-144">This is the revised schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:documentation>  
      Customer-Order-Order Details Schema  
      Copyright 2000 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"  
                  parent-key="EmployeeID"  
                  child="Emp"  
                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
                   type="EmpType"   
                   sql:relation="Emp"   
                   sql:key-fields="EmployeeID"   
                   sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmpType">  
    <xsd:sequence>  
       <xsd:element name="Emp"   
                    type="EmpType"   
                    sql:relation="Emp"   
                    sql:key-fields="EmployeeID"  
                    sql:relationship="SupervisorSupervisee"  
                    sql:max-depth="6"/>  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:int" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
    <xsd:attribute name="ReportsTo" type="xsd:int" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
## <a name="sqlmax-depth-annotation"></a><span data-ttu-id="0eda9-145">Anotação sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="0eda9-145">sql:max-depth Annotation</span></span>  
 <span data-ttu-id="0eda9-146">Em um esquema que consiste em relações recursivas, a profundidade de recursão deve ser especificada explicitamente no esquema.</span><span class="sxs-lookup"><span data-stu-id="0eda9-146">In a schema consisting of recursive relationships, the depth of recursion must be explicitly specified in the schema.</span></span> <span data-ttu-id="0eda9-147">Isso é necessário para gerar, com êxito, a consulta FOR XML EXPLICIT correspondente que retorna os resultados solicitados.</span><span class="sxs-lookup"><span data-stu-id="0eda9-147">This is required to successfully produce the corresponding FOR XML EXPLICIT query that returns the requested results.</span></span>  
  
 <span data-ttu-id="0eda9-148">Use a anotação `sql:max-depth` no esquema para especificar a profundidade de recursão em uma relação recursiva que é descrita no esquema.</span><span class="sxs-lookup"><span data-stu-id="0eda9-148">Use the `sql:max-depth` annotation in the schema to specify the depth of recursion in a recursive relationship that is described in the schema.</span></span> <span data-ttu-id="0eda9-149">O valor da anotação `sql:max-depth` é um inteiro positivo (de 1 a 50) que indica o número de recursões: um valor de 1 para a recursão no elemento para o qual a anotação `sql:max-depth` está especificada; um valor de 2 para a recursão no nível seguinte do elemento no qual `sql:max-depth` está especificada e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="0eda9-149">The value of the `sql:max-depth` annotation is a positive integer (1 to 50) that indicates the number of recursions:  A value of 1 stops the recursion at the element for which the `sql:max-depth` annotation is specified; a value of 2 stops the recursion at the next level from the element at which `sql:max-depth` is specified; and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0eda9-150">Na implementação subjacente, uma consulta XPath especificada em um esquema de mapeamento é convertida em SELECT... Consulta FOR XML EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="0eda9-150">In the underlying implementation, an XPath query that is specified against a mapping schema is converted to a SELECT ... FOR XML EXPLICIT query.</span></span> <span data-ttu-id="0eda9-151">Essa consulta requer que você especifique uma profundidade finita de recursão.</span><span class="sxs-lookup"><span data-stu-id="0eda9-151">This query requires you to specify a finite depth of recursion.</span></span> <span data-ttu-id="0eda9-152">Quanto mais alto for o valor especificado para `sql:max-depth`, maior será a consulta FOR XML EXPLICIT que será gerada.</span><span class="sxs-lookup"><span data-stu-id="0eda9-152">The higher the value that you specify for `sql:max-depth`, the larger the FOR XML EXPLICIT query that is generated.</span></span> <span data-ttu-id="0eda9-153">Isso poderá pode tornar mais lenta a recuperação.</span><span class="sxs-lookup"><span data-stu-id="0eda9-153">This might slow the retrieval time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0eda9-154">Updategrams e o Carregamento em Massa de XML ignoram a anotação max-depth.</span><span class="sxs-lookup"><span data-stu-id="0eda9-154">Updategrams and XML Bulk Load ignore the max-depth annotation.</span></span> <span data-ttu-id="0eda9-155">Isso significa que atualizações ou inserções recursivas acontecerão, independentemente do valor especificado para max-depth.</span><span class="sxs-lookup"><span data-stu-id="0eda9-155">This means, recursive updates or insertions will happen regardless of what value you specify for max-depth.</span></span>  
  
## <a name="specifying-sqlmax-depth-on-complex-elements"></a><span data-ttu-id="0eda9-156">Especificando sql:max-depth em elementos complexos</span><span class="sxs-lookup"><span data-stu-id="0eda9-156">Specifying sql:max-depth on Complex Elements</span></span>  
 <span data-ttu-id="0eda9-157">A anotação `sql:max-depth` pode ser especificada em qualquer elemento de conteúdo complexo.</span><span class="sxs-lookup"><span data-stu-id="0eda9-157">The `sql:max-depth` annotation can be specified on any complex content element.</span></span>  
  
### <a name="recursive-elements"></a><span data-ttu-id="0eda9-158">Elementos recursivos</span><span class="sxs-lookup"><span data-stu-id="0eda9-158">Recursive Elements</span></span>  
 <span data-ttu-id="0eda9-159">Se `sql:max-depth` for especificada no elemento pai e no elemento filho em uma relação recursiva, a anotação `sql:max-depth` especificada no pai terá precedência.</span><span class="sxs-lookup"><span data-stu-id="0eda9-159">If `sql:max-depth` is specified on both the parent element and the child element in a recursive relationship, the `sql:max-depth` annotation specified on the parent takes precedence.</span></span> <span data-ttu-id="0eda9-160">Por exemplo, no esquema a seguir, a anotação `sql:max-depth` é especificada nos elementos funcionários pai e filho.</span><span class="sxs-lookup"><span data-stu-id="0eda9-160">For example, in the following schema, the `sql:max-depth` annotation is specified on both the parent and the child employee elements.</span></span> <span data-ttu-id="0eda9-161">Nesse caso, `sql:max-depth=4` , especificado no **\<Emp>** elemento pai (desempenhando uma função de supervisor), tem precedência.</span><span class="sxs-lookup"><span data-stu-id="0eda9-161">In this case, `sql:max-depth=4`, specified on the **\<Emp>** parent element (playing a role of supervisor), takes precedence.</span></span> <span data-ttu-id="0eda9-162">O `sql:max-depth` especificado no elemento filho **\<Emp>** (desempenhando uma função de Supervisionador) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="0eda9-162">The `sql:max-depth` specified on the child **\<Emp>** element (playing a role of supervisee) is ignored.</span></span>  
  
#### <a name="example-b"></a><span data-ttu-id="0eda9-163">Exemplo B</span><span class="sxs-lookup"><span data-stu-id="0eda9-163">Example B</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo"   
                          sql:max-depth="3" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="2" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="0eda9-164">Para testar esse esquema, siga as etapas fornecidas para o exemplo A, anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0eda9-164">To test this schema, follow the steps provided for Sample A, earlier in this topic.</span></span>  
  
### <a name="nonrecursive-elements"></a><span data-ttu-id="0eda9-165">Elementos não recursivos</span><span class="sxs-lookup"><span data-stu-id="0eda9-165">Nonrecursive Elements</span></span>  
 <span data-ttu-id="0eda9-166">Se a anotação `sql:max-depth` for especificada em um elemento do esquema que não causa nenhuma recursão, ela será ignorado.</span><span class="sxs-lookup"><span data-stu-id="0eda9-166">If the `sql:max-depth` annotation is specified on an element in the schema that does not cause any recursion, it is ignored.</span></span> <span data-ttu-id="0eda9-167">No esquema a seguir, um **\<Emp>** elemento consiste em um **\<Constant>** elemento filho, que, por sua vez, tem um **\<Emp>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="0eda9-167">In the following schema, an **\<Emp>** element consists of a **\<Constant>** child element, which, in turn, has an **\<Emp>** child element.</span></span>  
  
 <span data-ttu-id="0eda9-168">Nesse esquema, a `sql:max-depth` anotação especificada no **\<Constant>** elemento é ignorada porque não há recursão entre o **\<Emp>** pai e o **\<Constant>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="0eda9-168">In this schema, the `sql:max-depth` annotation specified on the **\<Constant>** element is ignored because there is no recursion between the **\<Emp>** parent and the **\<Constant>** child element.</span></span> <span data-ttu-id="0eda9-169">Mas há uma recursão entre o **\<Emp>** ancestral e o **\<Emp>** filho.</span><span class="sxs-lookup"><span data-stu-id="0eda9-169">But there is recursion between the **\<Emp>** ancestor and the **\<Emp>** child.</span></span> <span data-ttu-id="0eda9-170">O esquema especifica a anotação `sql:max-depth` em ambos.</span><span class="sxs-lookup"><span data-stu-id="0eda9-170">The schema specifies the `sql:max-depth` annotation on both.</span></span> <span data-ttu-id="0eda9-171">Portanto, a `sql:max-depth` anotação especificada no ancestral ( **\<Emp>** na função de supervisor) tem precedência.</span><span class="sxs-lookup"><span data-stu-id="0eda9-171">Therefore, the `sql:max-depth` annotation that is specified on the ancestor (**\<Emp>** in the supervisor role) takes precedence.</span></span>  
  
#### <a name="example-c"></a><span data-ttu-id="0eda9-172">Exemplo C</span><span class="sxs-lookup"><span data-stu-id="0eda9-172">Example C</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"   
                  child="Emp"   
                  parent-key="EmployeeID"   
                  child-key="ReportsTo"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
               sql:relation="Emp"   
               type="EmpType"  
               sql:limit-field="ReportsTo"  
               sql:max-depth="1" />  
    <xsd:complexType name="EmpType" >  
      <xsd:sequence>  
       <xsd:element name="Constant"   
                    sql:is-constant="1"   
                    sql:max-depth="20" >  
         <xsd:complexType >  
           <xsd:sequence>  
            <xsd:element name="Emp"   
                         sql:relation="Emp" type="EmpType"  
                         sql:relationship="SupervisorSupervisee"   
                         sql:max-depth="3" />  
         </xsd:sequence>  
         </xsd:complexType>  
         </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="EmployeeID" type="xsd:int" />  
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="0eda9-173">Para testar esse esquema, siga as etapas fornecidas para o Exemplo A, anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0eda9-173">To test this schema, follow the steps provided for Example A, earlier in this topic.</span></span>  
  
## <a name="complex-types-derived-by-restriction"></a><span data-ttu-id="0eda9-174">Tipos complexos derivados por restrição</span><span class="sxs-lookup"><span data-stu-id="0eda9-174">Complex Types Derived by Restriction</span></span>  
 <span data-ttu-id="0eda9-175">Se você tiver uma derivação de tipo complexo por **\<restriction>** , os elementos do tipo complexo base correspondente não poderão especificar a `sql:max-depth` anotação.</span><span class="sxs-lookup"><span data-stu-id="0eda9-175">If you have a complex type derivation by **\<restriction>**, elements of the corresponding base complex type cannot specify the `sql:max-depth` annotation.</span></span> <span data-ttu-id="0eda9-176">Nesses casos, a anotação `sql:max-depth` poderá ser adicionada ao elemento do tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="0eda9-176">In these cases, the `sql:max-depth` annotation can be added to the element of the derived type.</span></span>  
  
 <span data-ttu-id="0eda9-177">Por outro lado, se você tiver uma derivação de tipo complexo, **\<extension>** os elementos do tipo complexo base correspondente poderão especificar a `sql:max-depth` anotação.</span><span class="sxs-lookup"><span data-stu-id="0eda9-177">On the other hand, if you have a complex type derivation by **\<extension>**, the elements of the corresponding base complex type can specify the `sql:max-depth` annotation.</span></span>  
  
 <span data-ttu-id="0eda9-178">Por exemplo, o esquema XSD a seguir gera um erro porque a anotação `sql:max-depth` é especificada no tipo de base.</span><span class="sxs-lookup"><span data-stu-id="0eda9-178">For example, the following XSD schema generates an error because the `sql:max-depth` annotation is specified on the base type.</span></span> <span data-ttu-id="0eda9-179">Não há suporte para esta anotação em um tipo derivado **\<restriction>** de outro tipo.</span><span class="sxs-lookup"><span data-stu-id="0eda9-179">This annotation is not supported on a type that is derived by **\<restriction>** from another type.</span></span> <span data-ttu-id="0eda9-180">Para corrigir esse problema, você deve alterar o esquema e especificar a anotação `sql:max-depth` em elemento no tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="0eda9-180">To fix this problem, you must change the schema and specify the `sql:max-depth` annotation on element in the derived type.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="0eda9-181">Exemplo D</span><span class="sxs-lookup"><span data-stu-id="0eda9-181">Example D</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:complexType name="CustomerBaseType">   
    <xsd:sequence>  
       <xsd:element name="CID" msdata:field="CustomerID" />  
       <xsd:element name="CompanyName"/>  
       <xsd:element name="Customers" msdata:max-depth="3">  
         <xsd:annotation>  
           <xsd:appinfo>  
             <msdata:relationship  
                     parent="Customers"  
                     parent-key="CustomerID"  
                     child-key="CustomerID"  
                     child="Customers" />  
           </xsd:appinfo>  
         </xsd:annotation>  
       </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
  <xsd:element name="Customers" type="CustomerType"/>  
  <xsd:complexType name="CustomerType">  
    <xsd:complexContent>  
       <xsd:restriction base="CustomerBaseType">  
          <xsd:sequence>  
            <xsd:element name="CID"   
                         type="xsd:string"/>  
            <xsd:element name="CompanyName"   
                         type="xsd:string"  
                         msdata:field="CName" />  
            <xsd:element name="Customers"   
                         type="CustomerType" />  
          </xsd:sequence>  
       </xsd:restriction>  
    </xsd:complexContent>  
  </xsd:complexType>  
</xsd:schema>   
```  
  
 <span data-ttu-id="0eda9-182">No esquema, `sql:max-depth` é especificada em um tipo complexo `CustomerBaseType`.</span><span class="sxs-lookup"><span data-stu-id="0eda9-182">In the schema, `sql:max-depth` is specified on a `CustomerBaseType` complex type.</span></span> <span data-ttu-id="0eda9-183">O esquema também especifica um **\<Customer>** elemento do tipo `CustomerType` , que é derivado de `CustomerBaseType` .</span><span class="sxs-lookup"><span data-stu-id="0eda9-183">The schema also specifies a **\<Customer>** element of type `CustomerType`, which is derived from `CustomerBaseType`.</span></span> <span data-ttu-id="0eda9-184">Uma consulta XPath especificada nesse esquema gerará um erro porque não existe suporte para `sql:max-depth` em um elemento definido em um tipo de base de restrição.</span><span class="sxs-lookup"><span data-stu-id="0eda9-184">An XPath query specified on such a schema will generate an error, because `sql:max-depth` is not supported on an element that is defined in a restriction base type.</span></span>  
  
## <a name="schemas-with-a-deep-hierarchy"></a><span data-ttu-id="0eda9-185">Esquemas com uma hierarquia profunda</span><span class="sxs-lookup"><span data-stu-id="0eda9-185">Schemas with a Deep Hierarchy</span></span>  
 <span data-ttu-id="0eda9-186">Você pode ter um esquema que inclua uma hierarquia profunda na qual um elemento contém um elemento filho que, por sua vez, contém outro elemento filho e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="0eda9-186">You might have a schema that includes a deep hierarchy in which an element contains a child element, which in turn contains another child element, and so on.</span></span> <span data-ttu-id="0eda9-187">Se a anotação `sql:max-depth` especificada nesse esquema gerar um documento XML que inclua uma hierarquia com mais de 500 níveis (com o elemento de nível superior no nível 1, seu filho no nível 2 e, assim, sucessivamente), será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="0eda9-187">If the `sql:max-depth` annotation specified in such a schema generates an XML document that includes a hierarchy of more than 500 levels (with top-level element at level 1, its child at level 2, and so on), an error is returned.</span></span>  
  
  
