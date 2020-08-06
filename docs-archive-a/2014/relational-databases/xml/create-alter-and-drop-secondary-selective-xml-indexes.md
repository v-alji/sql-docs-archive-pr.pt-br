---
title: Criar, alterar e remover índices XML seletivos secundários | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 45128105-833b-40a9-9cc9-1ae03ac0b52b
author: rothja
ms.author: jroth
ms.openlocfilehash: e6f7296896b6421db5329565403cdcbaf10b26a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679741"
---
# <a name="create-alter-and-drop-secondary-selective-xml-indexes"></a><span data-ttu-id="4ed1f-102">Criar, alterar e remover índices XML seletivos secundários</span><span class="sxs-lookup"><span data-stu-id="4ed1f-102">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>
  <span data-ttu-id="4ed1f-103">Descreve como criar um novo índice XML seletivo secundário, ou como alterar ou remover um índice XML seletivo secundário.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-103">Describes how to create a new secondary selective XML index, or alter or drop an existing secondary selective XML index.</span></span>  
  
##  <a name="creating-a-secondary-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="4ed1f-104">Criando um índice XML seletivo secundário</span><span class="sxs-lookup"><span data-stu-id="4ed1f-104">Creating a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-create-a-secondary-selective-xml-index"></a><span data-ttu-id="4ed1f-105">Como fazer: Criar um índice XML seletivo secundário</span><span class="sxs-lookup"><span data-stu-id="4ed1f-105">How to: Create a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="4ed1f-106">**Criar um índice XML seletivo secundário usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4ed1f-106">**Create a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="4ed1f-107">Crie um índice XML seletivo secundário chamando a instrução CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-107">Create a secondary selective XML index by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="4ed1f-108">Para obter mais informações, consulte [criar índice XML &#40;índices XML seletivos&#41;] (~/t-SQL/Statements/CREATE-XML-index-Selective-XML-indexes.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-108">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="4ed1f-109">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="4ed1f-109">**Example**</span></span>  
  
 <span data-ttu-id="4ed1f-110">O exemplo a seguir cria um índice XML seletivo secundário no caminho `'pathabc'`.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-110">The following example creates a secondary selective XML index on the path `'pathabc'`.</span></span> <span data-ttu-id="4ed1f-111">O caminho para o índice é identificado pelo nome atribuído a ele quando ele foi criado com a instrução CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-111">The path to index is identified by the name that was given to it when it was created with the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="4ed1f-112">Para obter mais informações, veja [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ed1f-112">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
```sql  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="altering-a-secondary-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="4ed1f-113">Alterando um índice XML seletivo secundário</span><span class="sxs-lookup"><span data-stu-id="4ed1f-113">Altering a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="4ed1f-114">A instrução ALTER não oferece suporte a índices XML secundários seletivos.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-114">The ALTER statement is not supported for secondary selective XML indexes.</span></span> <span data-ttu-id="4ed1f-115">Para alterar um índice XML secundário, remova o índice existente e recrie-o.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-115">To change a secondary selective XML index, drop the existing index and recreate it.</span></span>  
  
### <a name="how-to-alter-a-secondary-selective-xml-index"></a><span data-ttu-id="4ed1f-116">Como fazer: Alterar um índice XML seletivo secundário</span><span class="sxs-lookup"><span data-stu-id="4ed1f-116">How to: Alter a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="4ed1f-117">**Alterar um índice XML seletivo secundário usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4ed1f-117">**Alter a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 1.  <span data-ttu-id="4ed1f-118">Remova o índice XML seletivo secundário existente chamando a instrução DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-118">Drop the existing secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="4ed1f-119">Para obter mais informações, veja [DROP INDEX &#40;Índices XML Seletivos&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4ed1f-119">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
2.  <span data-ttu-id="4ed1f-120">Recrie o índice com as opções desejadas chamando a instrução CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-120">Recreate the index with the desired options by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="4ed1f-121">Para obter mais informações, consulte [criar índice XML &#40;índices XML seletivos&#41;] (~/t-SQL/Statements/CREATE-XML-index-Selective-XML-indexes.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-121">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="4ed1f-122">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="4ed1f-122">**Example**</span></span>  
  
 <span data-ttu-id="4ed1f-123">O exemplo a seguir altera um índice XML seletivo secundário removendo-o e recriando-o.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-123">The following example changes a secondary selective XML index by dropping it and recreating it.</span></span>  
  
```sql  
DROP INDEX filt_sxi_index_c  
  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="dropping-a-secondary-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="4ed1f-124">Removendo um índice XML seletivo secundário</span><span class="sxs-lookup"><span data-stu-id="4ed1f-124">Dropping a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-secondary-selective-xml-index"></a><span data-ttu-id="4ed1f-125">Como fazer: Remover um índice XML seletivo secundário</span><span class="sxs-lookup"><span data-stu-id="4ed1f-125">How to: Drop a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="4ed1f-126">**Remover um índice XML seletivo secundário usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4ed1f-126">**Drop a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="4ed1f-127">Remova um índice XML seletivo secundário chamando a instrução DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-127">Drop a secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="4ed1f-128">Para obter mais informações, veja [DROP INDEX &#40;Índices XML Seletivos&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4ed1f-128">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="4ed1f-129">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="4ed1f-129">**Example**</span></span>  
  
 <span data-ttu-id="4ed1f-130">O exemplo a seguir mostra uma instrução DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-130">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX ssxi_index  
ON tbl  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="4ed1f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ed1f-131">See Also</span></span>  
 [<span data-ttu-id="4ed1f-132">Índices XML Seletivos &#40;SXI&#41;</span><span class="sxs-lookup"><span data-stu-id="4ed1f-132">Selective XML Indexes &#40;SXI&#41;</span></span>](selective-xml-indexes-sxi.md)  
  
  
