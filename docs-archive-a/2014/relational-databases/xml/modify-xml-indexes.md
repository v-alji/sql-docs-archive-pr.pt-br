---
title: Modificar índices XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML indexes [SQL Server], modifying
- modifying indexes
ms.assetid: 24d50fe1-c6ec-49e6-91a3-9791851ba53d
author: rothja
ms.author: jroth
ms.openlocfilehash: c5c67470fc9aaaeefe49e5ccb1a8602e082c4054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679193"
---
# <a name="modify-xml-indexes"></a><span data-ttu-id="094f3-102">Modificar índices XML</span><span class="sxs-lookup"><span data-stu-id="094f3-102">Modify XML Indexes</span></span>
  <span data-ttu-id="094f3-103">A instrução DDL [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] pode ser usada para modificar o XML existente e índices não XML.</span><span class="sxs-lookup"><span data-stu-id="094f3-103">The [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement can be used to modify existing XML and non-XML indexes.</span></span> <span data-ttu-id="094f3-104">Porém, nem todas as opções de ALTER INDEX estão disponíveis para índices XML.</span><span class="sxs-lookup"><span data-stu-id="094f3-104">However, not all the ALTER INDEX options are available to XML indexes.</span></span> <span data-ttu-id="094f3-105">As opções a seguir não são válidas ao modificar índices XML:</span><span class="sxs-lookup"><span data-stu-id="094f3-105">The following options are not valid when modifying XML indexes:</span></span>  
  
-   <span data-ttu-id="094f3-106">A opção de recriação e definição IGNORE_DUP_KEY não é válida para índices XML.</span><span class="sxs-lookup"><span data-stu-id="094f3-106">The rebuild and set option IGNORE_DUP_KEY is not valid for XML indexes.</span></span> <span data-ttu-id="094f3-107">O opção de reconstrução ONLINE deve ser definida como OFF para índices XML secundários.</span><span class="sxs-lookup"><span data-stu-id="094f3-107">The rebuild option ONLINE must be set to OFF for secondary XML indexes.</span></span> <span data-ttu-id="094f3-108">O opção DROP_EXISTING não é permitida na instrução ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="094f3-108">The option DROP_EXISTING is not permitted in the ALTER INDEX statement.</span></span>  
  
-   <span data-ttu-id="094f3-109">As modificações de restrição de chave primária na tabela do usuário não são propagadas automaticamente para índices XML.</span><span class="sxs-lookup"><span data-stu-id="094f3-109">The modifications of the primary key constraint in the user table are not automatically propagated to XML indexes.</span></span> <span data-ttu-id="094f3-110">O usuário deve descartar os índices XML primeiro e recriá-los.</span><span class="sxs-lookup"><span data-stu-id="094f3-110">The user must drop the XML indexes first and then re-create them.</span></span>  
  
-   <span data-ttu-id="094f3-111">Se ALTER INDEX ALL for especificado, ele se aplicará a índices XML e não XML.</span><span class="sxs-lookup"><span data-stu-id="094f3-111">If ALTER INDEX ALL is specified, it applies to both non-XML and XML indexes.</span></span> <span data-ttu-id="094f3-112">Podem ser especificadas opções de indexação que não são válidas para os dois tipos de índices.</span><span class="sxs-lookup"><span data-stu-id="094f3-112">Indexing options may be specified that are not valid for both types of indexes.</span></span> <span data-ttu-id="094f3-113">Nesse caso, há falha em toda a instrução.</span><span class="sxs-lookup"><span data-stu-id="094f3-113">In this case, the whole statement fails.</span></span>  
  
## <a name="example-modifying-an-xml-index"></a><span data-ttu-id="094f3-114">Exemplo: Modificando um índice XML</span><span class="sxs-lookup"><span data-stu-id="094f3-114">Example: Modifying an XML Index</span></span>  
 <span data-ttu-id="094f3-115">No exemplo a seguir, um índice XML é criado e, em seguida, modificado definindo a opção `ALLOW_ROW_LOCKS` como `OFF`.</span><span class="sxs-lookup"><span data-stu-id="094f3-115">In the following example, an XML index is created and then modified by setting the option `ALLOW_ROW_LOCKS` to `OFF`.</span></span> <span data-ttu-id="094f3-116">Quando `ALLOW_ROW_LOCKS` está `OFF`, as linhas não são bloqueadas e o acesso aos índices especificados é obtido usando bloqueios em nível de página e de tabela.</span><span class="sxs-lookup"><span data-stu-id="094f3-116">When `ALLOW_ROW_LOCKS` is `OFF`, rows are not locked and access to the specified indexes is obtained by using page-and table-level locks.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create primary XML index.   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
  
-- Modify and set an index option.  
ALTER INDEX PIdx_T_XmlCol on T   
SET (ALLOW_ROW_LOCKS = OFF)  
```  
  
## <a name="example-disabling-and-enabling-an-xml-index"></a><span data-ttu-id="094f3-117">Exemplo: Desabilitando e habilitando um índice XML</span><span class="sxs-lookup"><span data-stu-id="094f3-117">Example: Disabling and Enabling an XML Index</span></span>  
 <span data-ttu-id="094f3-118">Por padrão, um índice XML está habilitado.</span><span class="sxs-lookup"><span data-stu-id="094f3-118">By default, an XML index is enabled.</span></span> <span data-ttu-id="094f3-119">Se um índice XML for desabilitado, as consultas executadas na coluna XML não usarão o índice XML.</span><span class="sxs-lookup"><span data-stu-id="094f3-119">If an XML index is disabled, the queries running against the XML column do not use the XML index.</span></span> <span data-ttu-id="094f3-120">Para habilitar um índice XML, use `ALTER INDEX` com a opção `REBUILD` .</span><span class="sxs-lookup"><span data-stu-id="094f3-120">To enable an XML index, use `ALTER INDEX` with the `REBUILD` option.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol ON T(XmlCol)  
GO  
ALTER INDEX PIdx_T_XmlCol on T DISABLE  
Go  
-- Verify index is disabled.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
-- Rebuild the index.  
ALTER INDEX PIdx_T_XmlCol on T REBUILD  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="094f3-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="094f3-121">See Also</span></span>  
 [<span data-ttu-id="094f3-122">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="094f3-122">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
