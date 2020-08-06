---
title: Diretrizes e limitações de DiffGrams no SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f2901f02f8b4a8fc7b77dcb6c1cb166cb6af6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574605"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a><span data-ttu-id="1d46a-102">Diretrizes e limitações de DiffGrams no SQLXML</span><span class="sxs-lookup"><span data-stu-id="1d46a-102">Guidelines and Limitations of DiffGrams in SQLXML</span></span>
  <span data-ttu-id="1d46a-103">Lembre-se das recomendações a seguir ao usar DiffGrams com o SQLXML 4.0:</span><span class="sxs-lookup"><span data-stu-id="1d46a-103">Remember the following when using DiffGrams with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="1d46a-104">Os tipos BLOB (objeto grande binário) como `text/ntext` e as imagens não devem ser usados no bloco `<diffgr:before>` ao trabalhar com DiffGrams, porque assim eles serão incluídos para ser usados em controle simultâneo.</span><span class="sxs-lookup"><span data-stu-id="1d46a-104">Binary large object (BLOB) types like `text/ntext` and images should not be used in the `<diffgr:before>` block in when working with DiffGrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="1d46a-105">Isso pode causar problemas com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devido às limitações de comparação para tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="1d46a-105">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="1d46a-106">Por exemplo, a palavra-chave LIKE é usada na cláusula WHERE para comparar entre colunas do tipo de dados `text`; entretanto, as comparações falharão no caso de tipos BLOB em que o tamanho dos dados seja maior do que 8KB.</span><span class="sxs-lookup"><span data-stu-id="1d46a-106">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="1d46a-107">Caracteres especiais em dados `ntext` podem causar problemas com o SQLXML 4.0 devido às limitações de comparação para tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="1d46a-107">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="1d46a-108">Por exemplo, o uso de "[Serializable]" no bloco `<diffgr:before>` de um DiffGram quando usado na verificação simultânea de uma coluna de tipo `ntext` falhará com a descrição do erro do SQLOLEDB a seguir:</span><span class="sxs-lookup"><span data-stu-id="1d46a-108">For example, the use of "[Serializable]" in the `<diffgr:before>` block of a DiffGram when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  
