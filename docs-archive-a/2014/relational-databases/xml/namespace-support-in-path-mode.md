---
title: Suporte a namespace no modo PATH | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679192"
---
# <a name="namespace-support-in-path-mode"></a><span data-ttu-id="0c994-102">Suporte a namespace em modo PATH</span><span class="sxs-lookup"><span data-stu-id="0c994-102">Namespace Support in PATH Mode</span></span>
  <span data-ttu-id="0c994-103">O suporte a namespace em modo PATH é fornecido usando WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="0c994-103">Namespace support in the PATH mode is provided by using WITH NAMESPACES.</span></span> <span data-ttu-id="0c994-104">Por exemplo, a consulta a seguir demonstra a sintaxe de WITH NAMESPACES para declarar um namespace ("a:") que pode , em seguida, ser usado na instrução SELECT subsequente.</span><span class="sxs-lookup"><span data-stu-id="0c994-104">For example, the following query demonstrates the WITH NAMESPACES syntax to declare a namespace ("a:") that can then be used in the subsequent SELECT statement:</span></span>  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a><span data-ttu-id="0c994-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0c994-105">Examples</span></span>  
 <span data-ttu-id="0c994-106">Esses exemplos ilustram o uso do modo PATH para gerar XML de uma consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="0c994-106">These samples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="0c994-107">Muitas dessas consultas são especificadas em relação a documentos XML de instruções da fabricação de bicicletas que são armazenados na coluna Instructions da tabela ProductModel.</span><span class="sxs-lookup"><span data-stu-id="0c994-107">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c994-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c994-108">See Also</span></span>  
 [<span data-ttu-id="0c994-109">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="0c994-109">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
