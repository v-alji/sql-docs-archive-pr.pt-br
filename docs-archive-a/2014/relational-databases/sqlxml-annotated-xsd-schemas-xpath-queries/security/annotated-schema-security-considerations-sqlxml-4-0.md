---
title: Considerações de segurança de esquema anotado (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping schema [SQLXML], security
- annotated XDR schemas, security
- XDR schemas [SQLXML], security
- annotations [SQLXML]
- annotated XSD schemas, security
- SQLXML, annotated XSD schemas
- SQLXML, annotated XDR schemas
- security [SQLXML], annotated schemas
- XSD schemas [SQLXML], security
ms.assetid: 7d7e44dc-b6d3-4e0f-95c7-8f99930c94f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 098f554410a846ed0223d17117b51025dfcf7897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569276"
---
# <a name="annotated-schema-security-considerations-sqlxml-40"></a><span data-ttu-id="81aed-102">Considerações sobre a segurança de esquemas anotados (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="81aed-102">Annotated Schema Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="81aed-103">Seguem diretrizes de segurança para o uso de esquemas anotados:</span><span class="sxs-lookup"><span data-stu-id="81aed-103">The following are security guidelines for using annotated schemas:</span></span>  
  
-   <span data-ttu-id="81aed-104">Evite usar o mapeamento padrão nos esquemas de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="81aed-104">Avoid using default mapping in the mapping schemas.</span></span> <span data-ttu-id="81aed-105">O mapeamento padrão expõe as informações do banco de dados (nomes de colunas e tabelas) no documento XML resultante porque, por padrão, os nomes de elementos são mapeados para nomes de tabelas e os nomes de atributos são mapeados para nomes de colunas.</span><span class="sxs-lookup"><span data-stu-id="81aed-105">The default mapping exposes the database information (table and column names) in the resulting XML document because, by default, the element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="81aed-106">Assim, qualquer usuário que vê o documento XML tem acesso às informações de coluna e tabela do banco de dados, o que representa um possível risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="81aed-106">Therefore, any user who sees the XML document has access to the table and column information in the database, presenting a potential security risk.</span></span> <span data-ttu-id="81aed-107">Para evitar esse risco, especifique nomes de elementos e atributos arbitrários no esquema e use anotações para mapeá-los explicitamente para as tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="81aed-107">To avoid this risk, specify arbitrary element and attribute names in the schema and use annotations to explicitly map them to the tables and columns.</span></span> <span data-ttu-id="81aed-108">Para obter mais informações sobre como usar o mapeamento padrão ao criar esquemas XSD, consulte [mapeamento padrão de elementos e atributos XSD para tabelas e colunas &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="81aed-108">For more information about using default mapping when you create XSD schemas, see [Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="81aed-109">O mapeamento explícito especificado usando as anotações expõe as informações do banco de dados (como nomes de tabelas e nomes de colunas).</span><span class="sxs-lookup"><span data-stu-id="81aed-109">The explicit mapping specified using the annotations exposes the database information (such as table names and column names).</span></span> <span data-ttu-id="81aed-110">Assim, talvez você não queira disponibilizar esses esquemas publicamente.</span><span class="sxs-lookup"><span data-stu-id="81aed-110">Therefore, you may not want to make these schemas available publicly.</span></span>  
  
-   <span data-ttu-id="81aed-111">Determinadas consultas, como as especificadas com relação ao esquema de mapeamento com recursão (especificada usando a anotação `max-depth` definida com um valor superior), podem levar mais tempo para serem executadas.</span><span class="sxs-lookup"><span data-stu-id="81aed-111">Certain queries such as those specified against mapping schema with recursion (specified using `max-depth` annotation set to a higher value) may take longer to execute.</span></span> <span data-ttu-id="81aed-112">Opcionalmente, você pode especificar um limite de tempo limite definindo a propriedade de tempo limite do comando (em segundos).</span><span class="sxs-lookup"><span data-stu-id="81aed-112">You can optionally specify a time-out limit by setting the Command Time Out property (in seconds).</span></span> <span data-ttu-id="81aed-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="81aed-113">For example:</span></span>  
  
    ```  
    cn.Open "Provider=SQLOLEDB;Server=localhost;Database=tempdb;Integrated Security=SSPI;Command Properties='Command Time Out=50';"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="81aed-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81aed-114">See Also</span></span>  
 [<span data-ttu-id="81aed-115">Esquemas XSD anotados em SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="81aed-115">Annotated XSD Schemas in SQLXML 4.0</span></span>](../../sqlxml/annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
  
  
