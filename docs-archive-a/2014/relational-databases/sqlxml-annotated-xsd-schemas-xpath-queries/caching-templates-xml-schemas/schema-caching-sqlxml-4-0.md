---
title: Cache de esquema (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- schemas [SQLXML]
ms.assetid: 7e5fda21-b435-41fd-b637-8b616560a93f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e36711955fa28bafd3b0996b1a02f6cd71f3c4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582366"
---
# <a name="schema-caching-sqlxml-40"></a><span data-ttu-id="1f7b8-102">Cache de esquemas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1f7b8-102">Schema Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="1f7b8-103">Com uma instalação lado a lado do XML para Microsoft SQL Server 2000 versão da Web 1, do Microsoft SQLXML 2.0 e do SQLXML 3.0, é possível controlar explicitamente o cache de esquemas em todas as versões usando as seguintes chaves do Registro:</span><span class="sxs-lookup"><span data-stu-id="1f7b8-103">With a side-by-side installation of XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0, and SQLXML 3.0, you can explicitly control the schema caching in all versions by using the following registry keys:</span></span>  
  
 <span data-ttu-id="1f7b8-104">Versão da Web 1:</span><span class="sxs-lookup"><span data-stu-id="1f7b8-104">Web Release 1:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX\SchemaCacheSize  
```  
  
 <span data-ttu-id="1f7b8-105">SQLXML 2,0:</span><span class="sxs-lookup"><span data-stu-id="1f7b8-105">SQLXML 2.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML2\SchemaCacheSize  
```  
  
 <span data-ttu-id="1f7b8-106">SQLXML 3.0:</span><span class="sxs-lookup"><span data-stu-id="1f7b8-106">SQLXML 3.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML3\SchemaCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="1f7b8-107">Para obter mais informações sobre a instalação lado a lado, consulte [What ' s New in SQLXML 4,0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span><span class="sxs-lookup"><span data-stu-id="1f7b8-107">For more information about side-by-side installation, see [What's New in SQLXML 4.0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span></span>  
  
 <span data-ttu-id="1f7b8-108">O cache de esquemas aprimora significativamente o desempenho de uma consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-108">Schema caching significantly improves the performance of an XPath query.</span></span> <span data-ttu-id="1f7b8-109">Quando uma consulta XPath é executada em um esquema de mapeamento, o esquema é armazenado na memória e as estruturas de dados necessárias são criadas na memória.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-109">When an XPath query is executed against a mapping schema, the schema is stored in memory, and the necessary data structures are built in memory.</span></span> <span data-ttu-id="1f7b8-110">Se o cache de esquemas estiver definido, o esquema permanece na memória, aprimorando assim o desempenho de consultas XPath subsequentes.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-110">If schema caching is set, the schema remains in memory, thereby improving performance for subsequent XPath queries.</span></span>  
  
 <span data-ttu-id="1f7b8-111">Você pode definir o tamanho do cache de esquemas adicionando a chave acima ao Registro</span><span class="sxs-lookup"><span data-stu-id="1f7b8-111">You can set the schema cache size by adding the above key in the registry</span></span>  
  
 <span data-ttu-id="1f7b8-112">O tamanho do esquema é definido com base na memória disponível e no número de esquemas utilizados.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-112">The schema size is set based on the available memory and the number of schemas you are using.</span></span> <span data-ttu-id="1f7b8-113">O tamanho de **SchemaCacheSize** padrão é 31.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-113">The default **SchemaCacheSize** size is 31.</span></span> <span data-ttu-id="1f7b8-114">Se você definir **SchemaCacheSize** mais alto, mais memória será usada.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-114">If you set **SchemaCacheSize** higher, more memory is used.</span></span> <span data-ttu-id="1f7b8-115">Portando, você pode aumentar o tamanho do cache se o acesso ao esquema parecer lento ou diminuir o tamanho do cache se houver pouca memória.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-115">Therefore, you can increase the cache size if schema access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="1f7b8-116">Por motivos de desempenho, é recomendável que você defina **SchemaCacheSize** maior do que o número de esquemas de mapeamento que você geralmente usa.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-116">For performance reasons, it is recommended that you set **SchemaCacheSize** higher than the number of mapping schemas you usually use.</span></span> <span data-ttu-id="1f7b8-117">Conforme aumenta o número de esquemas, se **SchemaCacheSize** for menor que o número de esquemas que você tem, o desempenho degradará.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-117">As the number of schemas increase, if **SchemaCacheSize** is less than the number of schemas you have, the performance degrades.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f7b8-118">Durante o desenvolvimento, é recomendável não armazenar os esquemas em cache, pois as alterações dos esquemas não se refletem no cache por aproximadamente dois minutos.</span><span class="sxs-lookup"><span data-stu-id="1f7b8-118">During development, it is recommended that you do not cache the schemas, because the changes to the schemas are not reflected in the cache for about two minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7b8-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f7b8-119">See Also</span></span>  
 <span data-ttu-id="1f7b8-120">[Cache de modelos &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="1f7b8-120">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="1f7b8-121">Cache XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1f7b8-121">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
