---
title: Processo de geração de registro (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], record generation process
- node scopes [SQLXML]
- record subsets [SQLXML]
- scope [SQLXML]
- key ordering rules [SQLXML]
- record generation process for bulk loads [SQLXML]
- entering node scope [SQLXML]
- bulk load [SQLXML], record generation process
- leaving node scope [SQLXML]
- schema mapping [SQLXML]
ms.assetid: d8885bbe-6f15-4fb9-9684-ca7883cfe9ac
author: rothja
ms.author: jroth
ms.openlocfilehash: 5734776864aecbda7adaf0b9b16180b5ebd55ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678685"
---
# <a name="record-generation-process-sqlxml-40"></a><span data-ttu-id="5181e-102">Registrar processo de geração (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5181e-102">Record Generation Process (SQLXML 4.0)</span></span>
  <span data-ttu-id="5181e-103">O Carregamento em massa XML processa os dados de entrada XML e prepara os registros para as tabelas apropriadas no Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5181e-103">XML Bulk Load processes the XML input data and prepares records for the appropriate tables in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5181e-104">A lógica no Carregamento em massa XML determina quando gerar um novo registro, quais valores de elemento filho ou de atributo copiar nos campos do registro e quando o registro está completo e pronto para ser enviado ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para inserção.</span><span class="sxs-lookup"><span data-stu-id="5181e-104">The logic in XML Bulk Load determines when to generate a new record, what child element or attribute values to copy into the fields of the record, and when the record is complete and ready to be sent to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="5181e-105">O Carregamento em massa XML não carrega todos os dados XML de entrada na memória e não produz conjuntos de registros completos antes de enviar dados ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5181e-105">XML Bulk Load does not load the entire XML input data into memory, and does not produce complete record sets before sending data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5181e-106">Isto é porque os dados de entrada XML podem ser um documento grande e carregar o documento inteiro na memória pode ser caro.</span><span class="sxs-lookup"><span data-stu-id="5181e-106">This is because XML input data can be a large document and loading the entire document in memory can be expensive.</span></span> <span data-ttu-id="5181e-107">Em vez disso, o Carregamento em massa XML faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5181e-107">Instead, XML Bulk Load does the following:</span></span>  
  
1.  <span data-ttu-id="5181e-108">Analisa o esquema de mapeamento e prepara o plano de execução necessário.</span><span class="sxs-lookup"><span data-stu-id="5181e-108">Analyzes the mapping schema and prepares the necessary execution plan.</span></span>  
  
2.  <span data-ttu-id="5181e-109">Aplica o plano de execução aos dados no fluxo de entrada.</span><span class="sxs-lookup"><span data-stu-id="5181e-109">Applies the execution plan to the data in the input stream.</span></span>  
  
 <span data-ttu-id="5181e-110">Esse processamento sequencial torna importante o fornecimento de dados de entrada XML de um modo específico.</span><span class="sxs-lookup"><span data-stu-id="5181e-110">This sequential processing makes it important to provide the XML input data in a specific way.</span></span> <span data-ttu-id="5181e-111">Você deve entender como o Carregamento em massa XML analisa o esquema de mapeamento e como o processo de geração de registro ocorre.</span><span class="sxs-lookup"><span data-stu-id="5181e-111">You must understand how XML Bulk Load analyzes the mapping schema and how the record generation process occurs.</span></span> <span data-ttu-id="5181e-112">Ao compreender isso, você pode fornecer um esquema de mapeamento ao Carregamento em massa XML que gera os resultados desejados.</span><span class="sxs-lookup"><span data-stu-id="5181e-112">With this understanding, you can provide a mapping schema to XML Bulk Load that produces the results you want.</span></span>  
  
 <span data-ttu-id="5181e-113">O Carregamento em massa XML trata as anotações do esquema de mapeamento comum, incluindo mapeamentos de coluna e tabela (especificados explicitamente, usando anotações, ou implicitamente, através do mapeamento padrão), e relacionamentos de junção.</span><span class="sxs-lookup"><span data-stu-id="5181e-113">XML Bulk Load handles common mapping schema annotations, including column and table mappings (specified explicitly by using annotations or implicitly through the default mapping), and join relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5181e-114">Parte-se do pressuposto que você está familiarizado com esquemas de mapeamento anotados XSD ou XDR.</span><span class="sxs-lookup"><span data-stu-id="5181e-114">It is assumed that you are familiar with annotated XSD or XDR mapping schemas.</span></span> <span data-ttu-id="5181e-115">Para obter mais informações sobre esquemas, consulte [introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) ou [esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5181e-115">For more information about schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) or [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5181e-116">Compreender a geração de registros requer o conhecimento dos seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="5181e-116">Understanding record generation requires understanding the following concepts:</span></span>  
  
-   <span data-ttu-id="5181e-117">Escopo de um nó</span><span class="sxs-lookup"><span data-stu-id="5181e-117">Scope of a node</span></span>  
  
-   <span data-ttu-id="5181e-118">Regra de geração de registro</span><span class="sxs-lookup"><span data-stu-id="5181e-118">Record Generation Rule</span></span>  
  
-   <span data-ttu-id="5181e-119">Subconjunto de registro e regra de ordenação de chaves</span><span class="sxs-lookup"><span data-stu-id="5181e-119">Record subset and the Key Ordering Rule</span></span>  
  
-   <span data-ttu-id="5181e-120">Exceções à regra de geração de registros</span><span class="sxs-lookup"><span data-stu-id="5181e-120">Exceptions to the Record Generation Rule</span></span>  
  
## <a name="scope-of-a-node"></a><span data-ttu-id="5181e-121">Escopo de um nó</span><span class="sxs-lookup"><span data-stu-id="5181e-121">Scope of a Node</span></span>  
 <span data-ttu-id="5181e-122">Um nó (um elemento ou um atributo) em um documento XML entra no *escopo* quando o carregamento em massa de XML o encontra no fluxo de dados de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="5181e-122">A node (an element or an attribute) in an XML document enters *into scope* when XML Bulk Load encounters it in the XML input data stream.</span></span> <span data-ttu-id="5181e-123">Para um nó de elemento, a marca inicial do elemento coloca o elemento no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-123">For an element node, the start tag of the element brings the element in scope.</span></span> <span data-ttu-id="5181e-124">Para um nó de atributo, o nome do atributo coloca o atributo no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-124">For an attribute node, the attribute name brings the attribute in scope.</span></span>  
  
 <span data-ttu-id="5181e-125">Um nó sai do escopo quando não há mais dados para ele: seja na marca final (no caso de um nó de elemento) ou no final do valor de um atributo (no caso de um nó de atributo).</span><span class="sxs-lookup"><span data-stu-id="5181e-125">A node leaves scope when there is no more data for it: either at the end tag (in the case of an element node) or at the end of an attribute value (in the case of an attribute node).</span></span>  
  
## <a name="record-generation-rule"></a><span data-ttu-id="5181e-126">Regra de geração de registro</span><span class="sxs-lookup"><span data-stu-id="5181e-126">Record Generation Rule</span></span>  
 <span data-ttu-id="5181e-127">Quando um nó (elemento ou atributo) entra no escopo, existe uma possibilidade de geração de um registro a partir desse nó.</span><span class="sxs-lookup"><span data-stu-id="5181e-127">When a node (element or attribute) enters into scope, there is a potential for generating a record from that node.</span></span> <span data-ttu-id="5181e-128">O registro dura enquanto o nó associado estiver no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-128">The record lives as long as the associated node is in scope.</span></span> <span data-ttu-id="5181e-129">Quando o nó sair do escopo, o Carregamento em massa XML considera o registro gerado completo (com dados) e o envia ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para inserção.</span><span class="sxs-lookup"><span data-stu-id="5181e-129">When the node goes out of scope, XML Bulk Load considers the generated record complete (with data) and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="5181e-130">Por exemplo, considere o seguinte fragmento de esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="5181e-130">For example, consider the following XSD schema fragment:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Customers" >  
   <xsd:complexType>  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
     <xsd:attribute name="CompanyName" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5181e-131">O esquema especifica um **\<Customer>** elemento com os atributos **CustomerID** e **CompanyName** .</span><span class="sxs-lookup"><span data-stu-id="5181e-131">The schema specifies a **\<Customer>** element with **CustomerID** and **CompanyName** attributes.</span></span> <span data-ttu-id="5181e-132">A `sql:relation` anotação mapeia o **\<Customer>** elemento para a tabela Customers.</span><span class="sxs-lookup"><span data-stu-id="5181e-132">The `sql:relation` annotation maps the **\<Customer>** element to the Customers table.</span></span>  
  
 <span data-ttu-id="5181e-133">Considere este fragmento de um documento XML:</span><span class="sxs-lookup"><span data-stu-id="5181e-133">Consider this fragment of an XML document:</span></span>  
  
```  
<Customer CustomerID="1" CompanyName="xyz" />  
<Customer CustomerID="2" CompanyName="abc" />  
...  
```  
  
 <span data-ttu-id="5181e-134">Quando um Carregamento em massa XML é fornecido com o esquema descrito nos parágrafos anteriores e os dados XML são fornecidos como entrada, ele processa os nós (elementos e atributos) nos dados de origem, conforme indicado a seguir:</span><span class="sxs-lookup"><span data-stu-id="5181e-134">When XML Bulk Load is provided with the schema described in the preceding paragraphs and XML data as input, it processes the nodes (elements and attributes) in the source data as follows:</span></span>  
  
-   <span data-ttu-id="5181e-135">A marca de início do primeiro **\<Customer>** elemento traz esse elemento no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-135">The start tag of the first **\<Customer>** element brings that element in scope.</span></span> <span data-ttu-id="5181e-136">Este nó é mapeado para a tabela Customers.</span><span class="sxs-lookup"><span data-stu-id="5181e-136">This node maps to the Customers table.</span></span> <span data-ttu-id="5181e-137">Portanto, o Carregamento em massa XML gera um registro para a tabela Customers.</span><span class="sxs-lookup"><span data-stu-id="5181e-137">Therefore, XML Bulk Load generates a record for the Customers table.</span></span>  
  
-   <span data-ttu-id="5181e-138">No esquema, todos os atributos do **\<Customer>** elemento são mapeados para as colunas da tabela Customers.</span><span class="sxs-lookup"><span data-stu-id="5181e-138">In the schema, all attributes of the **\<Customer>** element map to columns of the Customers table.</span></span> <span data-ttu-id="5181e-139">À medida que esses atributos entram no escopo, o Carregamento em massa XML copia seus valores para o registro do cliente que já foi gerado pelo escopo pai.</span><span class="sxs-lookup"><span data-stu-id="5181e-139">As these attributes enter into scope, XML Bulk Load copies their values to the customer record that is already generated by the parent scope.</span></span>  
  
-   <span data-ttu-id="5181e-140">Quando o carregamento em massa de XML atinge a marca de fim do **\<Customer>** elemento, o elemento sai do escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-140">When XML Bulk Load reaches the end tag for the **\<Customer>** element, the element goes out of scope.</span></span> <span data-ttu-id="5181e-141">Isto faz o Carregamento em massa XML considerar o registro completo e enviá-lo ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5181e-141">This causes XML Bulk Load to consider the record complete and send it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5181e-142">O carregamento em massa de XML segue esse processo para cada **\<Customer>** elemento subsequente.</span><span class="sxs-lookup"><span data-stu-id="5181e-142">XML Bulk Load follows this process for each subsequent **\<Customer>** element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5181e-143">Nesse modelo, como um registro é inserido quando uma marca final é atingida (ou o nó fica fora do escopo), você deve definir todos os dados que estão associados ao registro dentro do escopo do nó.</span><span class="sxs-lookup"><span data-stu-id="5181e-143">In this model, because a record is inserted when the end tag is reached (or the node is out of scope), you must define all of the data that is associated with the record within the scope of the node.</span></span>  
  
## <a name="record-subset-and-the-key-ordering-rule"></a><span data-ttu-id="5181e-144">Subconjunto de registros e a regra de ordenação de chave</span><span class="sxs-lookup"><span data-stu-id="5181e-144">Record Subset and the Key Ordering Rule</span></span>  
 <span data-ttu-id="5181e-145">Quando você especifica um esquema de mapeamento que usa `<sql:relationship>`, o termo subconjunto refere-se ao conjunto dos registros que é gerado no lado externo do relacionamento.</span><span class="sxs-lookup"><span data-stu-id="5181e-145">When you specify a mapping schema that uses `<sql:relationship>`, the subset term refers to the set of records that is generated on the foreign side of the relationship.</span></span> <span data-ttu-id="5181e-146">No seguinte exemplo, os registros CustOrder estão no lado externo, `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="5181e-146">In the following example, the CustOrder records are on the foreign side, `<sql:relationship>`.</span></span>  
  
 <span data-ttu-id="5181e-147">Por exemplo, suponha que um banco de dados contenha as seguintes tabelas:</span><span class="sxs-lookup"><span data-stu-id="5181e-147">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="5181e-148">Cust (CustomerID, CompanyName, City)</span><span class="sxs-lookup"><span data-stu-id="5181e-148">Cust (CustomerID, CompanyName, City)</span></span>  
  
-   <span data-ttu-id="5181e-149">CustOrder (CustomerID, OrderID)</span><span class="sxs-lookup"><span data-stu-id="5181e-149">CustOrder (CustomerID, OrderID)</span></span>  
  
 <span data-ttu-id="5181e-150">O CustomerID na tabela CustOrder é uma chave estrangeira que faz referência à chave primária CustomerID na tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="5181e-150">The CustomerID in the CustOrder table is a foreign key that refers to the CustomerID primary key in the Cust table.</span></span>  
  
 <span data-ttu-id="5181e-151">Agora, considere a exibição XML conforme especificado no seguinte esquema XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="5181e-151">Now, consider the XML view as specified in the following annotated XSD schema.</span></span> <span data-ttu-id="5181e-152">Esse esquema usa `<sql:relationship>` para especificar a relação entre as tabelas Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="5181e-152">This schema uses `<sql:relationship>` to specify the relationship between the Cust and CustOrder tables.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5181e-153">Os dados XML de exemplo e as etapas para criar um exemplo de funcionamento são dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="5181e-153">The sample XML data and the steps to create a working sample are given below.</span></span>  
  
-   <span data-ttu-id="5181e-154">Quando um **\<Customer>** nó de elemento no arquivo de dados XML entra no escopo, o carregamento em massa de XML gera um registro para a tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="5181e-154">When a **\<Customer>** element node in the XML data file enters into scope, XML Bulk Load generates a record for the Cust table.</span></span> <span data-ttu-id="5181e-155">Em seguida, o carregamento em massa de XML copia os valores de coluna necessários (CustomerID, CompanyName e City) de **\<CustomerID>** , **\<CompanyName>** e os **\<City>** elementos filho como esses elementos entram no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-155">XML Bulk Load then copies the necessary column values (CustomerID, CompanyName, and City) from the **\<CustomerID>**, **\<CompanyName>**, and the **\<City>** child elements as these elements enter into scope.</span></span>  
  
-   <span data-ttu-id="5181e-156">Quando um **\<Order>** nó de elemento entra no escopo, o carregamento em massa de XML gera um registro para a tabela CustOrder.</span><span class="sxs-lookup"><span data-stu-id="5181e-156">When an **\<Order>** element node enters into scope, XML Bulk Load generates a record for the CustOrder table.</span></span> <span data-ttu-id="5181e-157">O carregamento em massa de XML copia o valor do atributo **OrderID** para esse registro.</span><span class="sxs-lookup"><span data-stu-id="5181e-157">XML Bulk Load copies the value of the **OrderID** attribute to this record.</span></span> <span data-ttu-id="5181e-158">O valor necessário para a coluna CustomerID é obtido do **\<CustomerID>** elemento filho do **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="5181e-158">The value required for the CustomerID column is obtained from the **\<CustomerID>** child element of the **\<Customer>** element.</span></span> <span data-ttu-id="5181e-159">O carregamento em massa de XML usa as informações especificadas em `<sql:relationship>` para obter o valor de chave estrangeira CustomerID para esse registro, a menos que o atributo **CustomerID** tenha sido especificado no **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="5181e-159">XML Bulk Load uses the information that is specified in `<sql:relationship>` to obtain the CustomerID foreign key value for this record, unless the **CustomerID** attribute was specified in the **\<Order>** element.</span></span> <span data-ttu-id="5181e-160">A regra geral é que, se o elemento filho especifica explicitamente um valor para o atributo de chave estrangeira, o Carregamento em massa XML usará esse valor e não obterá o valor do elemento pai usando o `<sql:relationship>` especificado.</span><span class="sxs-lookup"><span data-stu-id="5181e-160">The general rule is that if the child element explicitly specifies a value for the foreign key attribute, XML Bulk Load uses that value and does not obtain the value from the parent element by using the specified `<sql:relationship>`.</span></span> <span data-ttu-id="5181e-161">Como esse **\<Order>** nó de elemento sai do escopo, o carregamento em massa de XML envia o registro para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e, em seguida, processa todos os nós de elementos subsequentes da **\<Order>** mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="5181e-161">As this **\<Order>** element node goes out of scope, XML Bulk Load sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then processes all the subsequent **\<Order>** element nodes in the same manner.</span></span>  
  
-   <span data-ttu-id="5181e-162">Por fim, o **\<Customer>** nó do elemento sai do escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-162">Finally, the **\<Customer>** element node goes out of scope.</span></span> <span data-ttu-id="5181e-163">Nesse instante, o Carregamento em massa XML envia o registro do cliente ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5181e-163">At that time, XML Bulk Load sends the customer record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5181e-164">O Carregamento em massa XML segue este processo para todos os clientes subsequentes no fluxo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="5181e-164">XML Bulk Load follows this process for all the subsequent customers in the XML data stream.</span></span>  
  
 <span data-ttu-id="5181e-165">Existem duas observações sobre o esquema de mapeamento:</span><span class="sxs-lookup"><span data-stu-id="5181e-165">Here are two observations about the mapping schema:</span></span>  
  
-   <span data-ttu-id="5181e-166">Quando o esquema satisfizer a regra de "contenção" (por exemplo, todos os dados associados ao cliente e a ordem são definidos dentro do escopo dos **\<Customer>** nós associados e do **\<Order>** elemento), o carregamento em massa é bem sucedido.</span><span class="sxs-lookup"><span data-stu-id="5181e-166">When the schema satisfies the "containment" rule (for example, all data that is associated with the customer and the order is defined within the scope of the associated **\<Customer>** and **\<Order>** element nodes), the bulk load succeeds.</span></span>  
  
-   <span data-ttu-id="5181e-167">Ao descrever o **\<Customer>** elemento, seus elementos filho são especificados na ordem apropriada.</span><span class="sxs-lookup"><span data-stu-id="5181e-167">In describing the **\<Customer>** element, its child elements are specified in the appropriate order.</span></span> <span data-ttu-id="5181e-168">Nesse caso, o **\<CustomerID>** elemento filho é especificado antes do **\<Order>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="5181e-168">In this case, the **\<CustomerID>** child element is specified before the **\<Order>** child element.</span></span> <span data-ttu-id="5181e-169">Isso significa que, no arquivo de dados XML de entrada, o **\<CustomerID>** valor do elemento está disponível como o valor da chave estrangeira quando o **\<Order>** elemento entra no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-169">This means that in the input XML data file, the **\<CustomerID>** element value is available as the foreign key value when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="5181e-170">Os atributos de chave são especificados primeiro; esta é a “regra de ordenação de chaves".</span><span class="sxs-lookup"><span data-stu-id="5181e-170">The key attributes are specified first; this is the "Key Ordering Rule."</span></span>  
  
     <span data-ttu-id="5181e-171">Se você especificar o **\<CustomerID>** elemento filho após o **\<Order>** elemento filho, o valor não estará disponível quando o **\<Order>** elemento entrar no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-171">If you specify the **\<CustomerID>** child element after the **\<Order>** child element, the value is not available when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="5181e-172">Quando a **\</Order>** marca de fim é lida, o registro para a tabela CustOrder é considerado concluído e é inserido na tabela CustOrder com um valor nulo para a coluna CustomerID, que não é o resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="5181e-172">When the **\</Order>** end tag is then read, the record for CustOrder table is considered complete and is inserted in the CustOrder table with a NULL value for the CustomerID column, which is not the desired result.</span></span>  
  
#### <a name="to-create-a-working-sample"></a><span data-ttu-id="5181e-173">Para criar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="5181e-173">To create a working sample</span></span>  
  
1.  <span data-ttu-id="5181e-174">Salve o esquema fornecido neste exemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="5181e-174">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="5181e-175">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="5181e-175">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                 OrderID        int         PRIMARY KEY,  
                 CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
3.  <span data-ttu-id="5181e-176">Salve os dados de entrada XML de exemplo a seguir como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="5181e-176">Save the following sample XML input data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>   
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
        <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="5181e-177">Para executar o Carregamento em massa XML, salve e execute o seguinte exemplo do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) (BulkLoad.vbs):</span><span class="sxs-lookup"><span data-stu-id="5181e-177">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example (BulkLoad.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
## <a name="exceptions-to-the-record-generation-rule"></a><span data-ttu-id="5181e-178">Exceções à regra de geração de registros</span><span class="sxs-lookup"><span data-stu-id="5181e-178">Exceptions to the Record Generation Rule</span></span>  
 <span data-ttu-id="5181e-179">O Carregamento em massa XML não gera um registro para um nó quando ele entra no escopo, se esse nó for do tipo IDREF ou IDREFS.</span><span class="sxs-lookup"><span data-stu-id="5181e-179">XML Bulk Load does not generate a record for a node when it enters into scope if that node is either an IDREF or IDREFS type.</span></span> <span data-ttu-id="5181e-180">Você deve ter certeza de que há uma descrição completa do registro em algum lugar do esquema.</span><span class="sxs-lookup"><span data-stu-id="5181e-180">You must make sure that a complete description of the record occurs at some place in the schema.</span></span> <span data-ttu-id="5181e-181">As anotações `dt:type="nmtokens"` são ignoradas da mesma maneira que o tipo IDREFS é ignorado.</span><span class="sxs-lookup"><span data-stu-id="5181e-181">The `dt:type="nmtokens"` annotations are ignored just as the IDREFS type is ignored.</span></span>  
  
 <span data-ttu-id="5181e-182">Por exemplo, considere o seguinte esquema XSD que descreve **\<Customer>** os **\<Order>** elementos e.</span><span class="sxs-lookup"><span data-stu-id="5181e-182">For example, consider the following XSD schema that describes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="5181e-183">O **\<Customer>** elemento inclui um atributo **OrderList** do tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="5181e-183">The **\<Customer>** element includes an **OrderList** attribute of the IDREFS type.</span></span> <span data-ttu-id="5181e-184">A marca `<sql:relationship>` especifica a relação um-para-muitos entre o cliente e lista de pedidos.</span><span class="sxs-lookup"><span data-stu-id="5181e-184">The `<sql:relationship>` tag specifies the one-to-many relationship between the customer and list of orders.</span></span>  
  
 <span data-ttu-id="5181e-185">Este é o esquema:</span><span class="sxs-lookup"><span data-stu-id="5181e-185">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
                 parent="Cust"  
                 parent-key="CustomerID"  
                 child="CustOrder"  
                 child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="CompanyName" type="xsd:string" />  
    <xsd:attribute name="City" type="xsd:string" />  
    <xsd:attribute name="OrderList"   
                       type="xsd:IDREFS"   
                       sql:relation="CustOrder"   
                       sql:field="OrderID"  
                       sql:relationship="CustCustOrder" >  
    </xsd:attribute>  
  </xsd:complexType>  
 </xsd:element>  
  
  <xsd:element name="Order" sql:relation="CustOrder" >  
   <xsd:complexType>  
    <xsd:attribute name="OrderID" type="xsd:string" />  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="OrderDate" type="xsd:date" />  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5181e-186">Como o carregamento em massa ignora os nós do tipo IDREFS, não há nenhuma geração de registro quando o nó de atributo **OrderList** entra no escopo.</span><span class="sxs-lookup"><span data-stu-id="5181e-186">Because Bulk Load ignores the nodes of IDREFS type, there is no record generation when the **OrderList** attribute node enters into scope.</span></span> <span data-ttu-id="5181e-187">Portanto, se você quiser que os registros de ordem sejam adicionados à tabela Orders, deve descrever esses pedidos ordens em algum lugar no esquema.</span><span class="sxs-lookup"><span data-stu-id="5181e-187">Therefore, if you want the order records added to the Orders table, you must describe those orders somewhere in the schema.</span></span> <span data-ttu-id="5181e-188">Nesse esquema, a especificação do **\<Order>** elemento garante que o carregamento em massa de XML adicione os registros de pedidos à tabela Orders.</span><span class="sxs-lookup"><span data-stu-id="5181e-188">In this schema, specifying the **\<Order>** element ensures that XML Bulk Load adds the order records to the Orders table.</span></span> <span data-ttu-id="5181e-189">O **\<Order>** elemento descreve todos os atributos necessários para preencher o registro para a tabela CustOrder.</span><span class="sxs-lookup"><span data-stu-id="5181e-189">The **\<Order>** element describes all the attributes that are required to fill the record for the CustOrder table.</span></span>  
  
 <span data-ttu-id="5181e-190">Você deve garantir que os valores **CustomerID** e **OrderID** no **\<Customer>** elemento correspondam aos valores no **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="5181e-190">You must ensure that the **CustomerID** and **OrderID** values in the **\<Customer>** element match the values in the **\<Order>** element.</span></span> <span data-ttu-id="5181e-191">Você é responsável por manter a integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="5181e-191">You are responsible for maintaining referential integrity.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="5181e-192">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="5181e-192">To test a working sample</span></span>  
  
1.  <span data-ttu-id="5181e-193">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="5181e-193">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
                  CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
                  CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID),  
                  OrderDate      datetime DEFAULT '2000-01-01')  
    GO  
    ```  
  
2.  <span data-ttu-id="5181e-194">Salve o esquema de mapeamento fornecido neste exemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="5181e-194">Save the mapping schema provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="5181e-195">Salve os dados XML de exemplo a seguir como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="5181e-195">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai" City="NY"  
                 OrderList="Ord1 Ord2" />  
      <Customers CustomerID="1112" CompanyName="Dont Know" City="LA"  
                 OrderList="Ord3 Ord4" />  
      <Order OrderID="Ord1" CustomerID="1111" OrderDate="1999-01-01" />  
      <Order OrderID="Ord2" CustomerID="1111" OrderDate="1999-02-01" />  
      <Order OrderID="Ord3" CustomerID="1112" OrderDate="1999-03-01" />  
      <Order OrderID="Ord4" CustomerID="1112" OrderDate="1999-04-01" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="5181e-196">Para executar o Carregamento em massa XML, salve e execute esse exemplo de VBScript (SampleVB.vbs):</span><span class="sxs-lookup"><span data-stu-id="5181e-196">To execute XML Bulk Load, save and execute this VBScript example (SampleVB.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
