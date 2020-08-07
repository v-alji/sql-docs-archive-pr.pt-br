---
title: 'Especificando o atributo SQL: inverso em SQL: relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b0781102371b98cced72a5a0edee70c9567c372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573903"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a><span data-ttu-id="5864c-102">Especificando o atributo sql:inverse em sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5864c-102">Specifying the sql:inverse Attribute on sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="5864c-103">O atributo `sql:inverse` só é útil quando o esquema XSD é usado no carregamento em massa ou por um diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="5864c-103">The `sql:inverse` attribute is useful only when the XSD schema is used for either bulk load or by an updategram.</span></span> <span data-ttu-id="5864c-104">O `sql:inverse` atributo pode ser especificado no **\<sql:relationship>** elemento.</span><span class="sxs-lookup"><span data-stu-id="5864c-104">The `sql:inverse` attribute can be specified on the **\<sql:relationship>** element.</span></span> <span data-ttu-id="5864c-105">Em diagramas de atualização, a lógica do diagrama de atualização interpreta o esquema ao determinar as tabelas e as colunas atualizadas pela operação do diagrama.</span><span class="sxs-lookup"><span data-stu-id="5864c-105">In updategrams, the updategram logic interprets the schema in determining the tables and columns that are updated by the updategram operation.</span></span> <span data-ttu-id="5864c-106">As relações de pai/filho especificadas no esquema determinam a ordem na qual os registros são modificados (inseridos ou excluídos).</span><span class="sxs-lookup"><span data-stu-id="5864c-106">The parent-child relationships that are specified in the schema determine the order in which the records are modified (inserted or deleted).</span></span>  
  
 <span data-ttu-id="5864c-107">Se você tiver um esquema XSD no qual a relação pai/filho é especificada na ordem inversa da relação chave primária/chave estrangeira entre as colunas de banco de dados correspondentes, a operação do diagrama de atualização de inserção ou exclusão falhará por conta da violação da chave primária/chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5864c-107">If you have an XSD schema in which the parent-child relationship is specified in the inverse order of the primary-key/foreign-key relationship between the corresponding database columns, the insert or delete updategram operation will fail because of the primary-key/foreign-key violation.</span></span> <span data-ttu-id="5864c-108">Nesses casos, o `sql:inverse` atributo é especificado ( `sql:inverse="true"` ) no **\<sql:relationship>** elemento e a lógica updategram inversa sua interpretação da relação pai-filho especificada no esquema.</span><span class="sxs-lookup"><span data-stu-id="5864c-108">In such cases, the `sql:inverse` attribute is specified (`sql:inverse="true"`) in the **\<sql:relationship>** element, and the updategram logic inverses its interpretation of the parent-child relationship specified in the schema.</span></span>  
  
 <span data-ttu-id="5864c-109">O atributo `sql:inverse` usa um valor booliano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="5864c-109">The `sql:inverse` attribute takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="5864c-110">Os valores aceitáveis são 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="5864c-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="5864c-111">Para obter um exemplo funcional usando a `sql:inverse` anotação, consulte [especificando um esquema de mapeamento anotado em um updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5864c-111">For a working sample using the `sql:inverse` annotation, see [Specifying an Annotated Mapping Schema in an Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5864c-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5864c-112">See Also</span></span>  
 [<span data-ttu-id="5864c-113">Especificando relações usando SQL: relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5864c-113">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
