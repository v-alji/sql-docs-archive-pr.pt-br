---
title: Criar, alterar e remover índices XML seletivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: c398f396-f630-4a2d-a264-f243c5346de1
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4123a46cc13359c936e6f9cfc0db3dcfdaa175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679740"
---
# <a name="create-alter-and-drop-selective-xml-indexes"></a><span data-ttu-id="4b0fc-102">Criar, alterar e remover índices XML seletivos</span><span class="sxs-lookup"><span data-stu-id="4b0fc-102">Create, Alter, and Drop Selective XML Indexes</span></span>
  <span data-ttu-id="4b0fc-103">Descreve como criar um novo índice XML seletivo ou alterar ou remover um índice XML seletivo existente.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-103">Describes how to create a new selective XML index, or alter or drop an existing selective XML index.</span></span>  
  
 <span data-ttu-id="4b0fc-104">Para obter mais informações sobre índices XML seletivos, veja [Índices XML Seletivos &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="4b0fc-104">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="creating-a-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="4b0fc-105">Criando um índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="4b0fc-105">Creating a Selective XML Index</span></span>  
  
### <a name="how-to-create-a-selective-xml-index"></a><span data-ttu-id="4b0fc-106">Como fazer: Criar um índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="4b0fc-106">How to: Create a Selective XML Index</span></span>  
 <span data-ttu-id="4b0fc-107">**Criar um índice XML seletivo usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4b0fc-107">**Create a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="4b0fc-108">Crie um índice XML seletivo chamando a instrução CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-108">Create a selective XML index by calling the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="4b0fc-109">Para obter mais informações, veja [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b0fc-109">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
 <span data-ttu-id="4b0fc-110">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="4b0fc-110">**Example**</span></span>  
  
 <span data-ttu-id="4b0fc-111">O exemplo a seguir mostra a sintaxe para criar um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-111">The following example shows the syntax for creating a selective XML index.</span></span> <span data-ttu-id="4b0fc-112">Ele também mostra variações da sintaxe para descrever os caminhos a serem indexados, com dicas de otimização opcionais.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-112">It also shows several variations of the syntax for describing the paths to be indexed, with optional optimization hints.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()'  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
)  
```  
  
  
  
##  <a name="altering-a-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="4b0fc-113">Alterando um índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="4b0fc-113">Altering a Selective XML Index</span></span>  
  
### <a name="how-to-alter-a-selective-xml-index"></a><span data-ttu-id="4b0fc-114">Como fazer: Alterar um índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="4b0fc-114">How to: Alter a Selective XML Index</span></span>  
 <span data-ttu-id="4b0fc-115">**Alterar um índice XML seletivo usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4b0fc-115">**Alter a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="4b0fc-116">Altere um índice XML seletivo existente chamando a instrução ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-116">Alter an existing selective XML index by calling the ALTER INDEX statement.</span></span> <span data-ttu-id="4b0fc-117">Para obter mais informações, veja [ALTER INDEX &#40;Índices XML Seletivos&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4b0fc-117">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="4b0fc-118">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="4b0fc-118">**Example**</span></span>  
  
 <span data-ttu-id="4b0fc-119">O exemplo a seguir mostra uma instrução ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-119">The following example shows an ALTER INDEX statement.</span></span> <span data-ttu-id="4b0fc-120">Essa instrução adiciona o caminho `'/a/b/m'` à parte XQuery do índice e exclui o caminho `'/a/b/e'` da parte SQL do índice criado no exemplo no tópico [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b0fc-120">This statement adds the path `'/a/b/m'` to the XQuery part of the index and deletes the path `'/a/b/e'` from the SQL part of the index created in the example in the topic [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span> <span data-ttu-id="4b0fc-121">O caminho a ser excluído é identificado pelo nome atribuído a ele quando foi criado.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-121">The path to delete is identified by the name that was given to it when it was created.</span></span>  
  
```sql  
ALTER INDEX sxi_index  
ON Tbl  
FOR   
(  
    ADD pathm = '/a/b/m' as XQUERY 'node()' ,  
    REMOVE pathabe  
)  
```  
  
  
  
##  <a name="dropping-a-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="4b0fc-122">Removendo um índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="4b0fc-122">Dropping a Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-selective-xml-index"></a><span data-ttu-id="4b0fc-123">Como fazer: Remover um índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="4b0fc-123">How to: Drop a Selective XML Index</span></span>  
 <span data-ttu-id="4b0fc-124">**Remover um índice XML seletivo usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4b0fc-124">**Drop a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="4b0fc-125">Remova um índice XML seletivo chamando a instrução DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-125">Drop a selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="4b0fc-126">Para obter mais informações, veja [DROP INDEX &#40;Índices XML Seletivos&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span><span class="sxs-lookup"><span data-stu-id="4b0fc-126">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span></span>  
  
 <span data-ttu-id="4b0fc-127">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="4b0fc-127">**Example**</span></span>  
  
 <span data-ttu-id="4b0fc-128">O exemplo a seguir mostra uma instrução DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="4b0fc-128">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX sxi_index ON tbl  
```  
  
 
  
  
