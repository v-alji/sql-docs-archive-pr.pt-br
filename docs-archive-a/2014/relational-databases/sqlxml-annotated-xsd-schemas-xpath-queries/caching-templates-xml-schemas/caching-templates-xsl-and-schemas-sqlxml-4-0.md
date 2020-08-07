---
title: Caching de modelos, XSL e esquemas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: rothja
ms.author: jroth
ms.openlocfilehash: 4df25909cf156957908abf0691964fd66a76343a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575041"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a><span data-ttu-id="fa3b9-102">Armazenando modelos, XSL e esquemas em cache (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fa3b9-102">Caching Templates, XSL, and Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="fa3b9-103">Para melhorar o desempenho, o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 dá suporte ao cache de modelos, XSL e esquemas.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-103">To improve performance, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supports caching templates, XSL, and schemas.</span></span>  
  
 <span data-ttu-id="fa3b9-104">Todos os esquemas, modelos e arquivos XSL (exceto os arquivos de um local http:// ou ftp://) são armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-104">All schemas, templates, and XSL files (except the files from an http:// or ftp:// location) are cached.</span></span> <span data-ttu-id="fa3b9-105">Os arquivos armazenados em cache permanecem na memória enquanto o processo está em execução.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-105">The cached files remain in memory while the process is running.</span></span> <span data-ttu-id="fa3b9-106">Quando o processo é encerrado, todo o cache é perdido.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-106">As the process exits, all the cache is lost.</span></span> <span data-ttu-id="fa3b9-107">Assim, se você executar um processo por consulta, talvez a vantagem do cache não seja notável.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-107">Therefore, if you run one process per query, the caching benefit may not be noticeable.</span></span>  
  
 <span data-ttu-id="fa3b9-108">Os tópicos nesta seção fornecem mais informações sobre o cache.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-108">The topics in this section provide more information about caching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa3b9-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fa3b9-109">In This Section</span></span>  
 [<span data-ttu-id="fa3b9-110">Cache de modelos &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fa3b9-110">Template Caching &#40;SQLXML 4.0&#41;</span></span>](template-caching-sqlxml-4-0.md)  
 <span data-ttu-id="fa3b9-111">Descreve e fornece uma chave do Registro o cache de modelos.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-111">Describes and provides a registry key for template caching.</span></span>  
  
 [<span data-ttu-id="fa3b9-112">Cache XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fa3b9-112">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
 <span data-ttu-id="fa3b9-113">Descreve e fornece uma chave do Registro o cache de XSL.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-113">Describes and provides a registry key for XSL caching.</span></span>  
  
 [<span data-ttu-id="fa3b9-114">Cache de esquema &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fa3b9-114">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
 <span data-ttu-id="fa3b9-115">Discute problemas de instalação lado a lado do SQLXML relacionados ao cache de esquemas e fornece chaves do Registro para o cache de esquemas.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-115">Discusses SQLXML side-by-side installation issues related to schema caching, and provides registry keys for schema caching.</span></span>  
  
  
