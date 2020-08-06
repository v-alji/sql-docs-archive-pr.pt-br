---
title: Usando o carregamento em massa do SQLXML no ambiente .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- XML Bulk Load [SQLXML], .NET environment
- .NET Framework [SQLXML], XML Bulk Load
- bulk load [SQLXML], .NET environment
ms.assetid: b85df83b-ba56-43bf-bcdf-b2a6fca43276
author: rothja
ms.author: jroth
ms.openlocfilehash: 6bd1c44a8b56bc5129aeb9843ed9ba814d45742a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684145"
---
# <a name="using-sqlxml-bulk-load-in-the-net-environment"></a><span data-ttu-id="4c677-102">Usando o Carregamento em Massa de SQLXML no ambiente .NET</span><span class="sxs-lookup"><span data-stu-id="4c677-102">Using SQLXML Bulk Load in the .NET Environment</span></span>
  <span data-ttu-id="4c677-103">Este tópico explica como a funcionalidade de Carregamento em Massa de XML pode ser usada no ambiente .NET.</span><span class="sxs-lookup"><span data-stu-id="4c677-103">This topic explains how the XML Bulk Load functionality can be used in the .NET environment.</span></span> <span data-ttu-id="4c677-104">Para obter informações detalhadas sobre o carregamento em massa de XML, consulte [executando o carregamento em massa de dados XML &#40;SQLXML 4,0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4c677-104">For detailed information about XML Bulk Load, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="4c677-105">Para usar o objeto COM do Carregamento em Massa de SQLXML de um ambiente gerenciado, você precisa adicionar uma referência de projeto a esse objeto.</span><span class="sxs-lookup"><span data-stu-id="4c677-105">To use the SQLXML Bulk Load COM object from a managed environment, you need to add a project reference to this object.</span></span> <span data-ttu-id="4c677-106">Isso gera uma interface de wrapper gerenciado em torno do objeto COM do Carregamento em Massa.</span><span class="sxs-lookup"><span data-stu-id="4c677-106">This generates a managed wrapper interface around the Bulk Load COM object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c677-107">O Carregamento em Massa de XML gerenciado não funciona com fluxos gerenciados e exige um wrapper em torno dos fluxos nativos.</span><span class="sxs-lookup"><span data-stu-id="4c677-107">Managed XML Bulk load does not work with managed streams and requires a wrapper around native streams.</span></span> <span data-ttu-id="4c677-108">O componente de Carregamento em Massa de SQLXML não será executado em um ambiente multithread (atributo '[MTAThread]').</span><span class="sxs-lookup"><span data-stu-id="4c677-108">The SQLXML Bulk Load component will not run in a multi-threaded environment ('[MTAThread]' attribute).</span></span> <span data-ttu-id="4c677-109">Se você tentar executar o componente de carregamento em massa em um ambiente de vários threads, obterá uma exceção InvalidCastException com as seguintes informações adicionais: "QueryInterface para a interface SQLXMLBULKLOADLib. ISQLXMLBulkLoad falhou."</span><span class="sxs-lookup"><span data-stu-id="4c677-109">If you attempt to run the Bulk Load component in a multi-thread environment, you get an InvalidCastException exception with the following additional information: "QueryInterface for interface SQLXMLBULKLOADLib.ISQLXMLBulkLoad failed."</span></span> <span data-ttu-id="4c677-110">A solução alternativa é tornar o objeto que contém o objeto de carregamento em massa acessível por thread único (por exemplo, usando o atributo **[STAThread]** , como mostrado no exemplo).</span><span class="sxs-lookup"><span data-stu-id="4c677-110">The workaround is to make the object that contains the Bulk Load object single-thread accessible (for example, by using the **[STAThread]** attribute as shown in the sample).</span></span>  
  
 <span data-ttu-id="4c677-111">Este tópico fornece um exemplo de aplicativo C# funcional para carregamento em massa de dados XML no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4c677-111">This topic provides a working C# sample application to bulk load XML data in the database.</span></span> <span data-ttu-id="4c677-112">Para criar um exemplo funcional, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4c677-112">To create a working sample, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4c677-113">Crie as tabelas a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c677-113">Create the following tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5))  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20))  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID))  
    GO  
    ```  
  
2.  <span data-ttu-id="4c677-114">Salve o seguinte esquema em um arquivo (schema.xml):</span><span class="sxs-lookup"><span data-stu-id="4c677-114">Save the following schema in a file (schema.xml):</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="4c677-115">Salve o seguinte exemplo de documento XML em um arquivo (data.xml):</span><span class="sxs-lookup"><span data-stu-id="4c677-115">Save the following sample XML document in a file (data.xml):</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="4c677-116">Inicie o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4c677-116">Start Visual Studio.</span></span>  
  
5.  <span data-ttu-id="4c677-117">Crie um aplicativo de console C#.</span><span class="sxs-lookup"><span data-stu-id="4c677-117">Create a C# console application.</span></span>  
  
6.  <span data-ttu-id="4c677-118">No menu **projeto** , selecione **Adicionar referência**.</span><span class="sxs-lookup"><span data-stu-id="4c677-118">From the **Project** menu, select **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="4c677-119">Na guia **com** , selecione **biblioteca de tipos do Microsoft SQLXML carregamento em massa 4,0** (xblkld4.dll) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c677-119">In the **COM** tab, select **Microsoft SQLXML Bulkload 4.0 Type Library** (xblkld4.dll) and click **OK**.</span></span> <span data-ttu-id="4c677-120">Você verá o assembly **Interop. SQLXMLBULKLOADLib** criado no projeto.</span><span class="sxs-lookup"><span data-stu-id="4c677-120">You will see the **Interop.SQLXMLBULKLOADLib** assembly created in the project.</span></span>  
  
8.  <span data-ttu-id="4c677-121">Substitua o método Main() pelo código a seguir.</span><span class="sxs-lookup"><span data-stu-id="4c677-121">Replace the Main() method with the following code.</span></span> <span data-ttu-id="4c677-122">Atualize a propriedade **ConnectionString** e o caminho do arquivo para o esquema e os arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="4c677-122">Update the **ConnectionString** property and the file path to the schema and data files.</span></span>  
  
    ```  
    [STAThread]  
       static void Main(string[] args)  
       {     
             try  
             {  
                SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class objBL = new SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class();  
                objBL.ConnectionString = "Provider=sqloledb;server=server;database=databaseName;integrated security=SSPI";  
                objBL.ErrorLogFile = "error.xml";  
                objBL.KeepIdentity = false;  
                objBL.Execute ("schema.xml","data.xml");  
             }  
             catch(Exception e)  
             {  
             Console.WriteLine(e.ToString());  
             }  
       }  
    ```  
  
9. <span data-ttu-id="4c677-123">Para carregar o XML na tabela que você criou, compile e execute o projeto.</span><span class="sxs-lookup"><span data-stu-id="4c677-123">To load the XML in the table you created, build and run the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c677-124">A referência para o componente de Carregamento em Massa (xblkld4.dll) também pode ser acionada usando a ferramenta tlbimp.exe, que está disponível como parte da estrutura .NET.</span><span class="sxs-lookup"><span data-stu-id="4c677-124">The reference to the Bulk Load component (xblkld4.dll) can also be added using the tlbimp.exe tool, which is available as part of .NET framework.</span></span> <span data-ttu-id="4c677-125">Essa ferramenta cria um wrapper gerenciado para a DLL nativa (xblkld4.dll) que pode ser usada em qualquer projeto do .NET.</span><span class="sxs-lookup"><span data-stu-id="4c677-125">This tool creates a managed wrapper for the native DLL (xblkld4.dll), which can then be used in any .NET project.</span></span> <span data-ttu-id="4c677-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4c677-126">For example:</span></span>  
  
    ```  
    c:\>tlbimp xblkld4.dll  
    ```  
  
     <span data-ttu-id="4c677-127">Isso cria a DLL do wrapper gerenciado (SQLXMLBULKLOADLib.dll) que você pode usar no projeto do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c677-127">This creates the managed wrapper DLL (SQLXMLBULKLOADLib.dll) that you can use in the .NET Framework project.</span></span> <span data-ttu-id="4c677-128">No .NET Framework, você adiciona referência de projeto à DLL recém-criada.</span><span class="sxs-lookup"><span data-stu-id="4c677-128">In the .NET Framework, you add project reference to the newly created DLL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c677-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c677-129">See Also</span></span>  
 [<span data-ttu-id="4c677-130">Como executar o carregamento em massa de dados XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="4c677-130">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  
