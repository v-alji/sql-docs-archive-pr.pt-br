---
title: Cache de modelos (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- templates [SQLXML], caching
ms.assetid: 73e151c6-b24e-4422-a116-51e0846bc6f5
author: rothja
ms.author: jroth
ms.openlocfilehash: b2ea8a539086ada1b15abbb9cff4f838af45818c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573883"
---
# <a name="template-caching-sqlxml-40"></a><span data-ttu-id="3ce06-102">Cache de modelos (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3ce06-102">Template Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="3ce06-103">O armazenamento de modelos em cache aprimora o desempenho significativamente.</span><span class="sxs-lookup"><span data-stu-id="3ce06-103">Template caching significantly improves performance.</span></span> <span data-ttu-id="3ce06-104">Se o armazenamento de modelos em cache estiver definido, o modelo permanecerá na memória até sua primeira execução.</span><span class="sxs-lookup"><span data-stu-id="3ce06-104">If template caching is set, the template remains in memory upon its first execution.</span></span> <span data-ttu-id="3ce06-105">Isto melhora o desempenho das execuções subsequentes do modelo.</span><span class="sxs-lookup"><span data-stu-id="3ce06-105">This improves the performance for the subsequent execution of the template.</span></span>  
  
 <span data-ttu-id="3ce06-106">Você pode definir o tamanho do cache do modelo adicionando a seguinte chave no Registro:</span><span class="sxs-lookup"><span data-stu-id="3ce06-106">You can set the template cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\TemplateCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="3ce06-107">O tamanho do modelo deve ser definido com base na memória disponível e no número de modelos que estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="3ce06-107">The template size should be set on the basis of the available memory and the number of templates you are using.</span></span> <span data-ttu-id="3ce06-108">O padrão de tamanho de **TemplateCacheSize** é 31.</span><span class="sxs-lookup"><span data-stu-id="3ce06-108">The default of **TemplateCacheSize** size is 31.</span></span> <span data-ttu-id="3ce06-109">Você pode aumentar o tamanho do cache se o acesso ao modelo parecer lento ou diminuir o tamanho do cache se houver pouca memória.</span><span class="sxs-lookup"><span data-stu-id="3ce06-109">You can increase the cache size if template access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="3ce06-110">Para obter um melhor desempenho, é recomendável que você defina **TemplateCacheSize** maior do que o número de modelos que geralmente usa.</span><span class="sxs-lookup"><span data-stu-id="3ce06-110">For better performance, it is recommended that you set **TemplateCacheSize** higher than the number of templates you usually use.</span></span> <span data-ttu-id="3ce06-111">Se **TemlateCacheSize** for menor que o número de modelos que você tem, o desempenho degradará conforme o número de modelos aumentar.</span><span class="sxs-lookup"><span data-stu-id="3ce06-111">If **TemlateCacheSize** is less than the number of templates you have, performance degrades as the number of templates increase.</span></span> <span data-ttu-id="3ce06-112">O **TemplateCacheSize** pode ser definido como um máximo de 128.</span><span class="sxs-lookup"><span data-stu-id="3ce06-112">The **TemplateCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="3ce06-113">Sempre que um modelo em cache for usado, a hora da modificação do arquivo de modelo será verificada para ver se é necessário atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="3ce06-113">Every time a cached template is used, the modification time of the template file is checked to see whether it needs to be refreshed.</span></span> <span data-ttu-id="3ce06-114">Isso ocorre porque a cópia em disco é mais recente do que a cópia em cache.</span><span class="sxs-lookup"><span data-stu-id="3ce06-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ce06-115">As propriedades de comandos e parâmetros do modelo não são armazenadas em cache.</span><span class="sxs-lookup"><span data-stu-id="3ce06-115">Template parameters and command properties are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce06-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ce06-116">See Also</span></span>  
 <span data-ttu-id="3ce06-117">[Cache de esquema &#40;SQLXML 4,0&#41;](schema-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="3ce06-117">[Schema Caching &#40;SQLXML 4.0&#41;](schema-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="3ce06-118">Cache XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3ce06-118">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
