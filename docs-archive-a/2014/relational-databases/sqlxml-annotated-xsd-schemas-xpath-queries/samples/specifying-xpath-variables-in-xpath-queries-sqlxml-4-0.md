---
title: Especificando variáveis XPath em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], XPath variables
- XPath variables [SQLXML]
ms.assetid: c11ab816-11b8-4131-8b77-c03fe500fa10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5045831f627722f7dbb9a9189be5c48d830f2add
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569279"
---
# <a name="specifying-xpath-variables-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="d117f-102">Especificando variáveis XPath em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d117f-102">Specifying XPath Variables in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="d117f-103">Os exemplos a seguir mostram como as variáveis XPath são passadas em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="d117f-103">The following examples show how XPath variables are passed in XPath queries.</span></span> <span data-ttu-id="d117f-104">As consultas XPath nesses exemplos são especificadas com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="d117f-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="d117f-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d117f-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d117f-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d117f-106">Examples</span></span>  
  
### <a name="a-use-the-xpath-variables"></a><span data-ttu-id="d117f-107">a.</span><span class="sxs-lookup"><span data-stu-id="d117f-107">A.</span></span> <span data-ttu-id="d117f-108">Usar as variáveis XPath</span><span class="sxs-lookup"><span data-stu-id="d117f-108">Use the XPath variables</span></span>  
 <span data-ttu-id="d117f-109">Um modelo de exemplo consiste em duas consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="d117f-109">A sample template consists of two XPath queries.</span></span> <span data-ttu-id="d117f-110">Cada uma das consultas XPath assume um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d117f-110">Each of the XPath queries takes one parameter.</span></span> <span data-ttu-id="d117f-111">O modelo também especifica valores padrão para esses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d117f-111">The template also specifies default values for these parameters.</span></span> <span data-ttu-id="d117f-112">Serão usados os valores padrão se não forem especificados valores dos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d117f-112">The default values are used if parameter values are not specified.</span></span> <span data-ttu-id="d117f-113">Dois parâmetros com valores padrão são especificados em **\<sql:header>** .</span><span class="sxs-lookup"><span data-stu-id="d117f-113">Two parameters with default values are specified in **\<sql:header>**.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='CustomerID'>1</sql:param>  
     <sql:param name='ContactID'>1</sql:param>   
  </sql:header>  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
    Customer[@CustomerID=$CustomerID]   
  </sql:xpath-query >  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
   Contact[@ContactID=$ContactID]   
  </sql:xpath-query>  
</ROOT>  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="d117f-114">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="d117f-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="d117f-115">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d117f-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="d117f-116">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="d117f-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="d117f-117">Crie o modelo seguinte (XPathVariables.xml) e salve-o no diretório onde:</span><span class="sxs-lookup"><span data-stu-id="d117f-117">Create the following template (XPathVariables.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:header>  
         <sql:param name='CustomerID'>1</sql:param>  
         <sql:param name='ContactID'>1</sql:param>   
      </sql:header>  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[@CustomerID=$CustomerID]   
      </sql:xpath-query >  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
       Contact[@ContactID=$ContactID]   
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="d117f-118">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="d117f-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="d117f-119">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d117f-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="d117f-120">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="d117f-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="d117f-121">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d117f-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d117f-122">Neste exemplo, nenhum parâmetro é passado.</span><span class="sxs-lookup"><span data-stu-id="d117f-122">In this example, no parameters are passed.</span></span> <span data-ttu-id="d117f-123">Por isso, são usados os valores de parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="d117f-123">Therefore, the default parameter values are used.</span></span>  
  
  
