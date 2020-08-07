---
title: Diretrizes e limitações de Updategrams XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updategrams [SQLXML], about updategrams
ms.assetid: b5231859-14e2-4276-bc17-db2817b6f235
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e01e366edc2889691862de639f69220ac4bb439
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680844"
---
# <a name="guidelines-and-limitations-of-xml-updategrams-sqlxml-40"></a><span data-ttu-id="90af8-102">Diretrizes e limitações dos diagramas de atualização XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="90af8-102">Guidelines and Limitations of XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="90af8-103">Lembre-se das recomendações a seguir ao usar diagramas de atualização XML:</span><span class="sxs-lookup"><span data-stu-id="90af8-103">Remember the following when using XML updategrams:</span></span>  
  
-   <span data-ttu-id="90af8-104">Se você estiver usando um updategram para uma operação de inserção com apenas um único par **\<before>** de **\<after>** blocos e, o **\<before>** bloco poderá ser omitido.</span><span class="sxs-lookup"><span data-stu-id="90af8-104">If you are using an updategram for an insert operation with only a single pair of **\<before>** and **\<after>** blocks, the **\<before>** block can be omitted.</span></span> <span data-ttu-id="90af8-105">Por outro lado, no caso de uma operação de exclusão, o **\<after>** bloco pode ser omitido.</span><span class="sxs-lookup"><span data-stu-id="90af8-105">Conversely, in case of a delete operation, the **\<after>** block can be omitted.</span></span>  
  
-   <span data-ttu-id="90af8-106">Se você estiver usando um updategram com vários **\<before>** **\<after>** blocos e na **\<sync>** marca, os **\<before>** blocos e blocos **\<after>** deverão ser especificados para formar **\<before>** e **\<after>** emparelhar.</span><span class="sxs-lookup"><span data-stu-id="90af8-106">If you are using an updategram with multiple **\<before>** and **\<after>** blocks in the **\<sync>** tag, both **\<before>** blocks and **\<after>** blocks must be specified to form **\<before>** and **\<after>** pairs.</span></span>  
  
-   <span data-ttu-id="90af8-107">As atualizações em um diagrama de atualização são aplicadas à exibição XML fornecida pelo esquema XML.</span><span class="sxs-lookup"><span data-stu-id="90af8-107">The updates in an updategram are applied to the XML view that is provided by the XML schema.</span></span> <span data-ttu-id="90af8-108">Portanto, para o mapeamento padrão obter êxito em qualquer uma das situações, você precisará especificar o nome do arquivo de esquema no diagrama de atualização ou, se o nome do arquivo não for fornecido, os nomes de elemento e atributo precisarão corresponder aos nomes de tabela e coluna no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90af8-108">Therefore, for the default mapping to succeed either you must specify the schema file name in the updategram or, if the file name is not provided, the element and attribute names must match the table and column names in the database.</span></span>  
  
-   <span data-ttu-id="90af8-109">O SQLXML 4.0 exige que todos os valores de coluna de um diagrama de atualização sejam mapeados explicitamente no esquema (XDR ou XSD) fornecido para compor a exibição XML de seus elementos filho.</span><span class="sxs-lookup"><span data-stu-id="90af8-109">SQLXML 4.0 requires that all column values in an updategram must be explicitly mapped in the schema (either XDR or XSD) provided to compose the XML view for its child elements.</span></span> <span data-ttu-id="90af8-110">Esse comportamento é diferente daquele das versões anteriores do SQLXML, que permitiam um valor para uma coluna não mapeada no esquema se fosse sugerido como parte da Chave estrangeira em uma anotação `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="90af8-110">This behavior differs from earlier versions of SQLXML, which allowed a value for a column not mapped in the schema if it was implied as part of the foreign Key in a `sql:relationship` annotation.</span></span> <span data-ttu-id="90af8-111">(Observe que essa alteração não influencia na propagação dos valores de chave primária para os elementos filho, que ainda ocorrerá para o SQLXML 4.0 se nenhum valor for especificado explicitamente para o elemento filho.</span><span class="sxs-lookup"><span data-stu-id="90af8-111">(Note that this change does not affect propagation of primary key values to child elements, which still occurs for SQLXML 4.0 if no value is explicitly specified for the child element.</span></span>  
  
-   <span data-ttu-id="90af8-112">Se você estiver usando um updategram para modificar dados em uma coluna binária (como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `image` tipo de dados), deverá fornecer um esquema de mapeamento no qual o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipo de dados (por exemplo, `sql:datatype="image"` ) e o tipo de dados XML (por exemplo, `dt:type="binhex"` ou `dt:type="binbase64` ) devem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="90af8-112">If you are using an updategram to modify data in a binary column (such as the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `image` data type), you must provide a mapping schema in which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (for example, `sql:datatype="image"`) and the XML data type (for example, `dt:type="binhex"` or `dt:type="binbase64`) must be specified.</span></span> <span data-ttu-id="90af8-113">Os dados da coluna binária precisam ser especificados no diagrama de atualização; a anotação `sql:url-encode` especificada no esquema de mapeamento é ignorada pelo diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="90af8-113">The data for the binary column must be specified in the updategram; the `sql:url-encode` annotation that is specified in the mapping schema is ignored by the updategram.</span></span>  
  
-   <span data-ttu-id="90af8-114">Quando você está escrevendo um esquema XSD, se o valor especificado para a anotação `sql:relation` ou `sql:field` incluir um caractere especial, como um caractere de espaço (por exemplo, no nome de tabela "Order Details"), esse valor precisará ser colocado entre colchetes (por exemplo, "[Order Details]").</span><span class="sxs-lookup"><span data-stu-id="90af8-114">When you are writing an XSD schema, if the value you specify for the `sql:relation` or `sql:field` annotation includes a special character, such as a space character (for example, in the "Order Details" table name), this value must be enclosed in brackets (for example, "[Order Details]").</span></span>  
  
-   <span data-ttu-id="90af8-115">Ao usar diagramas de atualização, não são suportadas relações de cadeia.</span><span class="sxs-lookup"><span data-stu-id="90af8-115">When using updategrams, chain relationships are not supported.</span></span> <span data-ttu-id="90af8-116">Por exemplo, se as tabelas A e C tiverem uma relação de cadeia que use a tabela B, ocorrerá o erro a seguir ao tentar executar o diagrama de atualização:</span><span class="sxs-lookup"><span data-stu-id="90af8-116">For example, if tables A and C are related through a chain relationship that uses table B, the following error will occur when attempting to run and execute the updategram:</span></span>  
  
    ```  
    There is an inconsistency in the schema provided.  
    ```  
  
     <span data-ttu-id="90af8-117">Mesmo se o esquema e o diagrama de atualização estiverem corretos e devidamente formados, esse erro ocorrerá se houver uma relação de cadeia.</span><span class="sxs-lookup"><span data-stu-id="90af8-117">Even if both schema and updategram are otherwise correct and validly formed, this error will occur if a chain relationship is present.</span></span>  
  
-   <span data-ttu-id="90af8-118">Os diagramas de atualização não permitem a passagem de dados de tipo `image` como parâmetros durante as atualizações.</span><span class="sxs-lookup"><span data-stu-id="90af8-118">Updategrams do not permit the passing of `image` type data as parameters during updates.</span></span>  
  
-   <span data-ttu-id="90af8-119">Tipos de objeto binário grande (BLOB) como `text/ntext` e imagens não devem ser usados no **\<before>** bloco em ao trabalhar com Updategrams, pois isso os incluirá para uso no controle de simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="90af8-119">Binary large object (BLOB) types like `text/ntext` and images should not be used in the **\<before>** block in when working with updategrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="90af8-120">Isso pode causar problemas com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devido às limitações de comparação para tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="90af8-120">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="90af8-121">Por exemplo, a palavra-chave LIKE é usada na cláusula WHERE para comparar entre colunas do tipo de dados `text`; entretanto, as comparações falharão no caso de tipos BLOB em que o tamanho dos dados seja maior do que 8KB.</span><span class="sxs-lookup"><span data-stu-id="90af8-121">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="90af8-122">Caracteres especiais em dados `ntext` podem causar problemas com o SQLXML 4.0 devido às limitações de comparação para tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="90af8-122">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="90af8-123">Por exemplo, o uso de "[Serializable]" no **\<before>** bloco de Updategrams quando usado na verificação de simultaneidade de uma coluna do `ntext` tipo falhará com a seguinte descrição de erro SQLOLEDB:</span><span class="sxs-lookup"><span data-stu-id="90af8-123">For example, the use of "[Serializable]" in the **\<before>** block of an updategrams when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90af8-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90af8-124">See Also</span></span>  
 [<span data-ttu-id="90af8-125">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="90af8-125">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
