---
title: Referenciar a coleção de esquemas XML interna (sys) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- sys XML schema collections [SQL Server]
- schema collections [SQL Server], predefined
- predefined XML schema collections [SQL Server]
- XML schema collections [SQL Server], predefined
- built-in XML schema collections [SQL Server]
ms.assetid: 1e118303-5df0-4ee4-bd8d-14ced7544144
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fa30107e1746b33e3f9b8eb1cfa53d1f4d25fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679737"
---
# <a name="reference-the-built-in-xml-schema-collection-sys"></a><span data-ttu-id="74661-102">Referenciar a coleção de esquemas XML interna (sys)</span><span class="sxs-lookup"><span data-stu-id="74661-102">Reference the Built-in XML Schema Collection (sys)</span></span>
  <span data-ttu-id="74661-103">Todo banco de dados que você cria tem uma coleção de esquema XML **sys** predefinido no esquema relacional **sys** .</span><span class="sxs-lookup"><span data-stu-id="74661-103">Every database you create has a predefined **sys** XML schema collection in the **sys** relational schema.</span></span> <span data-ttu-id="74661-104">Ele reserva esses esquemas predefinidos que podem ser acessados de qualquer outra coleção de esquema XML criada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="74661-104">It reserves these predefined schemas, and they can be accessed from any other user-created XML schema collection.</span></span> <span data-ttu-id="74661-105">Os prefixos usados nesses esquemas predefinidos são significativos em XQuery.</span><span class="sxs-lookup"><span data-stu-id="74661-105">The prefixes used in these predefined schemas are meaningful in XQuery.</span></span> <span data-ttu-id="74661-106">Apenas **xml** é um prefixo reservado.</span><span class="sxs-lookup"><span data-stu-id="74661-106">Only **xml** is a reserved prefix.</span></span>  
  
```  
xml = http://www.w3.org/XML/1998/namespace  
xs = http://www.w3.org/2001/XMLSchema  
xsi = http://www.w3.org/2001/XMLSchema-instance  
fn = http://www.w3.org/2004/07/xpath-functions  
sqltypes = https://schemas.microsoft.com/sqlserver/2004/sqltypes  
xdt = http://www.w3.org/2004/07/xpath-datatypes  
(no prefix) = urn:schemas-microsoft-com:xml-sql  
(no prefix) = https://schemas.microsoft.com/sqlserver/2004/SOAP  
```  
  
 <span data-ttu-id="74661-107">Observe que o namespace **sqltypes** contém componentes que podem ser referidos de qualquer coleção de esquema XML criada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="74661-107">Note that the **sqltypes** namespace contains components that can be referenced from any user-created XML schema collection.</span></span> <span data-ttu-id="74661-108">Você pode baixar o esquema **sqltypes** deste [site da Microsoft](https://go.microsoft.com/fwlink/?linkid=31850).</span><span class="sxs-lookup"><span data-stu-id="74661-108">You can download the **sqltypes** schema from this [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=31850).</span></span> <span data-ttu-id="74661-109">Os componentes internos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74661-109">The built-in components include the following:</span></span>  
  
-   <span data-ttu-id="74661-110">Tipos XSD</span><span class="sxs-lookup"><span data-stu-id="74661-110">XSD types</span></span>  
  
-   <span data-ttu-id="74661-111">Atributos XML **lang**, **base**e **space**</span><span class="sxs-lookup"><span data-stu-id="74661-111">XML attributes **lang**, **base**, and **space**</span></span>  
  
-   <span data-ttu-id="74661-112">Componentes do namespace **sqltypes**</span><span class="sxs-lookup"><span data-stu-id="74661-112">Components of the **sqltypes** namespace</span></span>  
  
 <span data-ttu-id="74661-113">A consulta a seguir retorna componentes internos que podem ser referidos a partir de uma coleção de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="74661-113">The following query returns built-in components that can be referenced from a user-created XML schema collection:</span></span>  
  
```  
SELECT C.name, N.name, C.symbol_space_desc from sys.xml_schema_components C join sys.xml_schema_namespaces N  
on ((C.xml_namespace_id = N.xml_namespace_id) AND (C.xml_collection_id = N.xml_collection_id))  
join sys.xml_schema_collections SC  
on SC.xml_collection_id = C.xml_collection_id  
where ((C.xml_collection_id = 1) AND (C.name is not null) AND (C.scoping_xml_component_id is null)   
AND (SC.schema_id = 4))  
GO  
```  
  
 <span data-ttu-id="74661-114">O exemplo a seguir mostra como esses componentes são referenciados em um esquema de usuário.</span><span class="sxs-lookup"><span data-stu-id="74661-114">The following example shows how these components are referenced in a user schema.</span></span> <span data-ttu-id="74661-115">`CREATE XML SCHEMA COLLECTION` cria uma coleção de esquemas XML que referencia o tipo `varchar` definido no namespace `sqltypes` .</span><span class="sxs-lookup"><span data-stu-id="74661-115">`CREATE XML SCHEMA COLLECTION` creates an XML schema collection that references the `varchar` type defined in the `sqltypes` namespace.</span></span> <span data-ttu-id="74661-116">O exemplo também referencia o atributo `lang` que está definido no namespace `xml` .</span><span class="sxs-lookup"><span data-stu-id="74661-116">The example also references the `lang` attribute that is defined in the `xml` namespace.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema   
   xmlns="http://www.w3.org/2001/XMLSchema"   
   targetNamespace="myNS"  
   xmlns:ns="myNS"  
   xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
   <import namespace="http://www.w3.org/XML/1998/namespace"/>  
   <import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
   <element name="root">  
      <complexType>  
          <sequence>  
             <element name="a" type="string"/>  
             <element name="b" type="string"/>  
             <!-- varchar type is defined in the sys.sys collection and   
                  can be referenced in any user-defined schema -->  
             <element name="c" type="s:varchar"/>  
          </sequence>  
          <attribute name="att" type="int"/>  
          <!-- xml:lang attribute is defined in the sys.sys collection   
               and can be referenced in any user-defined schema -->  
          <attribute ref="xml:lang"/>  
      </complexType>  
    </element>  
 </schema>'  
GO  
 -- Cleanup  
DROP xml schema collection SC   
GO  
```  
  
 <span data-ttu-id="74661-117">Você deve observar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74661-117">You should note the following:</span></span>  
  
-   <span data-ttu-id="74661-118">Não é possível modificar esquemas XML com esses namespaces em nenhuma coleção de esquema XML definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="74661-118">You cannot modify XML schemas with these namespaces in any user-defined XML schema collection.</span></span> <span data-ttu-id="74661-119">Por exemplo, há uma falha na seguinte coleção de esquema XML porque ela está adicionando um componente ao namespace `sqltypes` protegido:</span><span class="sxs-lookup"><span data-stu-id="74661-119">For example, the following XML schema collection fails, because it is adding a component to the `sqltypes` protected namespace:</span></span>  
  
    ```  
    CREATE XML SCHEMA COLLECTION SC AS '  
    <schema xmlns="http://www.w3.org/2001/XMLSchema"   
    targetNamespace    
        ="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
          <element name="root" type="string"/>  
    </schema>'  
    GO  
    ```  
  
-   <span data-ttu-id="74661-120">Não é possível usar a coleção de esquema XML `sys` para digitar colunas, variáveis ou parâmetros `xml` .</span><span class="sxs-lookup"><span data-stu-id="74661-120">You cannot use the `sys` XML schema collection to type `xml` columns, variables, or parameters.</span></span> <span data-ttu-id="74661-121">Por exemplo, o seguinte código retorna um erro:</span><span class="sxs-lookup"><span data-stu-id="74661-121">For example, the following code returns an error:</span></span>  
  
    ```  
    DECLARE @x xml (sys.sys)  
    ```  
  
-   <span data-ttu-id="74661-122">Não há suporte para serialização desses esquemas internos.</span><span class="sxs-lookup"><span data-stu-id="74661-122">Serialization of these built-in schemas is not supported.</span></span> <span data-ttu-id="74661-123">Por exemplo, o seguinte código retorna um erro:</span><span class="sxs-lookup"><span data-stu-id="74661-123">For example, the following code returns an error:</span></span>  
  
    ```  
    SELECT XML_SCHEMA_NAMESPACE(N'sys',N'sys')  
    GO  
    ```  
  
 <span data-ttu-id="74661-124">O código a seguir é outro exemplo no qual uma coleção de esquema XML que usa o tipo `varchar` definido no namespace `sqltypes` é criada:</span><span class="sxs-lookup"><span data-stu-id="74661-124">The following code is another example in which you create an XML schema collection that uses the `varchar` type defined in the `sqltypes` namespace:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="myNS" xmlns:ns="myNS"  
        xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes">  
   <import     
     namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
      <simpleType name="myType">  
            <restriction base="s:varchar">  
                  <maxLength value="20"/>  
            </restriction>  
      </simpleType>  
      <element name="root" type="ns:myType"/>  
</schema>'  
go  
```  
  
 <span data-ttu-id="74661-125">Conforme mostrado a seguir, é possível criar uma variável `XML` com tipo, atribuir uma instância XML a ela e verificar se o valor do tipo do elemento <`root`> é de um tipo `varchar`.</span><span class="sxs-lookup"><span data-stu-id="74661-125">As shown in the following, you can create a typed `XML` variable, assign an XML instance to it, and verify that the value of the <`root`> element type is a `varchar` type.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xmlns="myNS">My data</root>'  
SELECT @var.query('declare namespace sqltypes = "https://schemas.microsoft.com/sqlserver/2004/sqltypes";  
declare namespace ns="myNS";   
data(/ns:root[1]) instance of sqltypes:varchar?')  
GO  
```  
  
 <span data-ttu-id="74661-126">A expressão `instance of sqltypes:varchar?` retorna TRUE, porque o valor do elemento <`root`> é de um tipo derivado de **varchar** de acordo com o esquema associado à variável `@var`.</span><span class="sxs-lookup"><span data-stu-id="74661-126">The `instance of sqltypes:varchar?` expression returns TRUE, because the <`root`> element value is of a type derived from **varchar** according to the schema that is associated with the `@var` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74661-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74661-127">See Also</span></span>  
 [<span data-ttu-id="74661-128">Coleções de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="74661-128">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
