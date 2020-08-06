---
title: Cache XSL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- XSL caching [SQLXML]
ms.assetid: 91994142-32f0-4d8d-a8cf-eb0d8b1f1999
author: rothja
ms.author: jroth
ms.openlocfilehash: e41f247c34c1b40bedfdf6924a45afe5f63735b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680858"
---
# <a name="xsl-caching-sqlxml-40"></a><span data-ttu-id="161be-102">Cache de XSL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="161be-102">XSL Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="161be-103">O armazenamento em cache de folhas de estilo XSL melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="161be-103">Caching XSL style sheets improves performance.</span></span> <span data-ttu-id="161be-104">Em sua primeira execução, uma folha de estilo XSL permanecerá na memória se o cache de XSL for definido como ON; isto melhora o desempenho para processamento subsequente.</span><span class="sxs-lookup"><span data-stu-id="161be-104">Upon its first execution, an XSL style sheet remains in memory if XSL caching is set to ON; this improves performance for subsequent processing.</span></span> <span data-ttu-id="161be-105">A configuração padrão é ON.</span><span class="sxs-lookup"><span data-stu-id="161be-105">The default setting is ON.</span></span>  
  
 <span data-ttu-id="161be-106">Você pode definir o tamanho do cache XSL adicionando a seguinte chave no Registro:</span><span class="sxs-lookup"><span data-stu-id="161be-106">You can set the XSL cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\XSLCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="161be-107">O tamanho de cache XSL deve ser definido com base na memória disponível e no número de folhas de estilo XSL que você está usando.</span><span class="sxs-lookup"><span data-stu-id="161be-107">The XSL cache size should be set on the basis of the available memory and the number of XSL style sheets you are using.</span></span> <span data-ttu-id="161be-108">O padrão de tamanho de **XSLCacheSize** é 31.</span><span class="sxs-lookup"><span data-stu-id="161be-108">The default of **XSLCacheSize** size is 31.</span></span> <span data-ttu-id="161be-109">Você poderá aumentar o tamanho do cache se o acesso de XSL parecer lento, ou diminuir o tamanho do cache se a memória for pouca.</span><span class="sxs-lookup"><span data-stu-id="161be-109">You can increase the cache size if XSL access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="161be-110">Para obter melhor desempenho, é recomendado que você defina **XSLCacheSize** mais alto que o número de folhas de estilo XSL geralmente usado.</span><span class="sxs-lookup"><span data-stu-id="161be-110">For better performance, it is recommended that you set **XSLCacheSize** higher than the number of XSL style sheets you usually use.</span></span> <span data-ttu-id="161be-111">Se **XSLCacheSize** for menor que o número de folhas de estilo XSL que você terá, o desempenho degradará à medida que o número de folhas de estilo XSL aumentar.</span><span class="sxs-lookup"><span data-stu-id="161be-111">If **XSLCacheSize** is less than the number of XSL style sheets you have, the performance degrades as the number of XSL style sheets increases.</span></span> <span data-ttu-id="161be-112">O **XSLCacheSize** pode ser definido como 128, no máximo.</span><span class="sxs-lookup"><span data-stu-id="161be-112">The **XSLCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="161be-113">Sempre que a folha de estilo XSL armazenada em cache é usada, a hora de modificação do arquivo XSL é verificada para determinar se ele precisa ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="161be-113">Every time the cached XSL style sheet is used, the modification time of the XSL file is checked to determine whether it needs to be refreshed.</span></span> <span data-ttu-id="161be-114">Isso ocorre porque a cópia em disco é mais recente do que a cópia em cache.</span><span class="sxs-lookup"><span data-stu-id="161be-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161be-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="161be-115">See Also</span></span>  
 <span data-ttu-id="161be-116">[Cache de modelos &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="161be-116">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="161be-117">Cache de esquema &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="161be-117">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
  
  
