---
title: Executando consultas XPath com namespaces (provedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- namespaces property
- queries [SQLXML], SQLXMLOLEDB Provider
- XPath queries [SQLXML], namespaces
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- namespaces [SQLXML], XPath queries
ms.assetid: 024a4b7d-435d-47ba-9e80-2c2f640108f5
author: rothja
ms.author: jroth
ms.openlocfilehash: ff692b49a4c32c14655af3a9eb07071dc60ba2a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680851"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxmloledb-provider"></a><span data-ttu-id="7cc84-102">Executando consultas XPath com namespaces (provedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="7cc84-102">Executing XPath Queries with Namespaces (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="7cc84-103">As consultas XPath podem incluir namespaces.</span><span class="sxs-lookup"><span data-stu-id="7cc84-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="7cc84-104">Se os elementos de esquema forem qualificados por namespace (ou seja, se incluírem um namespace de destino), as consultas XPath com relação ao esquema precisarão especificar esse namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-104">If the schema elements are namespace qualified (that is, if they include a target namespace), XPath queries against the schema must specify this namespace.</span></span>  
  
 <span data-ttu-id="7cc84-105">Como não há suporte ao uso do caractere curinga (\*) no SQLXML 4.0, você precisa especificar a consulta XPath usando um prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-105">Because using the wildcard character (\*) is not supported in SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="7cc84-106">Para resolver esse prefixo, use a propriedade namespaces para especificar a associação de namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-106">To resolve this prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="7cc84-107">No exemplo a seguir, a consulta XPath especifica namespaces usando o caractere curinga ( \* ) e as funções XPath de nome local () e namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="7cc84-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="7cc84-108">Essa consulta XPath retorna todos os elementos em que o nome local é `Contact` e o URI de namespace é `urn:myschema:Contacts`.</span><span class="sxs-lookup"><span data-stu-id="7cc84-108">This XPath query returns all the elements where the local name is `Contact` and the namespace URI is `urn:myschema:Contacts`.</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="7cc84-109">No SQLXML 4.0, essa consulta XPath deve ser especificada com um prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-109">In SQLXML 4.0, this XPath query must be specified with a namespace prefix.</span></span> <span data-ttu-id="7cc84-110">Um exemplo é `x:Contact`, em que `x` é o prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="7cc84-111">Considere o esquema XSD a seguir:</span><span class="sxs-lookup"><span data-stu-id="7cc84-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="7cc84-112">Como esse esquema define o namespace de destino, uma consulta XPath (como "Employee") com relação ao esquema precisa incluir o namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against the schema must include the namespace.</span></span>  
  
 <span data-ttu-id="7cc84-113">Este é um aplicativo de exemplo do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic que executa uma consulta XPath (x:Employee) no esquema XSD anterior.</span><span class="sxs-lookup"><span data-stu-id="7cc84-113">This is a sample [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application that executes an XPath query (x:Employee) against the preceding XSD schema.</span></span> <span data-ttu-id="7cc84-114">Para resolver o prefixo, a associação de namespace é especificada usando a propriedade namespaces.</span><span class="sxs-lookup"><span data-stu-id="7cc84-114">To resolve the prefix, the namespace binding is specified by using the namespaces property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7cc84-115">No código, é necessário fornecer o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="7cc84-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="7cc84-116">Este exemplo também especifica o uso do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para o provedor de dados, o que requer a instalação adicional do software cliente da rede.</span><span class="sxs-lookup"><span data-stu-id="7cc84-116">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="7cc84-117">Para obter mais informações, consulte [requisitos do sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="7cc84-117">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Private Sub Form_Load()  
    Dim con As New ADODB.Connection  
    Dim cmd As New ADODB.Command  
    Dim stm As New ADODB.Stream  
    con.Open "provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
    Set cmd.ActiveConnection = con  
    stm.Open  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    cmd.Properties("Mapping schema") = "C:\DirectoryPath\con-ex.xml"  
    cmd.Properties("namespaces") = "xmlns:x='urn:myschema:Contacts'"  
    '  Debug.Print "Set Command Dialect to DBGUID_XPATH"  
    cmd.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
    cmd.CommandText = "x:Contact"  
    cmd.Execute , , adExecuteStream   
    stm.Position = 0  
    Debug.Print stm.ReadText(adReadAll)  
End Sub  
```  
  
### <a name="to-test-this-application"></a><span data-ttu-id="7cc84-118">Para testar esse aplicativo</span><span class="sxs-lookup"><span data-stu-id="7cc84-118">To test this application</span></span>  
  
1.  <span data-ttu-id="7cc84-119">Salve o esquema XSD do exemplo em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="7cc84-119">Save the sample XSD schema in a folder.</span></span>  
  
2.  <span data-ttu-id="7cc84-120">Crie um projeto executável do Visual Basic e copie o código nele.</span><span class="sxs-lookup"><span data-stu-id="7cc84-120">Create a Visual Basic executable project, and copy the code into it.</span></span> <span data-ttu-id="7cc84-121">Altere o caminho de diretório especificado conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="7cc84-121">Change the specified directory path as appropriate.</span></span>  
  
3.  <span data-ttu-id="7cc84-122">Adicione a seguinte referência de projeto:</span><span class="sxs-lookup"><span data-stu-id="7cc84-122">Add the following project reference:</span></span>  
  
    ```  
    "Microsoft ActiveX Data Objects 2.8 Library"  
    ```  
  
4.  <span data-ttu-id="7cc84-123">Execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7cc84-123">Execute the application.</span></span>  
  
 <span data-ttu-id="7cc84-124">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="7cc84-124">This is the partial result:</span></span>  
  
```  
<y0:Employee xmlns:y0="urn:myschema:Contacts"   
             LName="Achong" CID="1" FName="Gustavo"/>  
<y0:Employee xmlns:y0="urn:myschema:Employees"   
             LName="Abel" CID="2" FName="Catherine"/>  
```  
  
 <span data-ttu-id="7cc84-125">Os prefixos gerados no documento XML são arbitrários, mas são mapeados para o mesmo namespace.</span><span class="sxs-lookup"><span data-stu-id="7cc84-125">The prefixes that are generated in the XML document are arbitrary, but they map to the same namespace.</span></span>  
  
  
