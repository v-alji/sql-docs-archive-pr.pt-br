---
title: Opção de configuração de servidor ft notify bandwidth | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- ft notify bandwidth opion
- small memory buffers
- memory [SQL Server], buffers
ms.assetid: 9ca284c5-f3e0-4a67-a132-fff376ff0ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dc5839f699d55edf86c5e3e3f0eb001089a0a5dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684339"
---
# <a name="ft-notify-bandwidth-server-configuration-option"></a><span data-ttu-id="b8ee6-102">Opção ft notify bandwidth de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="b8ee6-102">ft notify bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="b8ee6-103">Use a opção **ft notify bandwidth** para especificar o tamanho a que pode crescer o pool de buffers de memória pequenos.</span><span class="sxs-lookup"><span data-stu-id="b8ee6-103">Use the **ft notify bandwidth** option to specify the size to which the pool of small memory buffers can grow.</span></span> <span data-ttu-id="b8ee6-104">Buffers de memória pequenos têm 64 KB (quilobytes).</span><span class="sxs-lookup"><span data-stu-id="b8ee6-104">Small memory buffers are 64 kilobytes (KB) in size.</span></span> <span data-ttu-id="b8ee6-105">O valor do parâmetro *max* especifica o número máximo de buffers que o gerenciador de memória de texto completo deve manter em um pool de buffers pequenos.</span><span class="sxs-lookup"><span data-stu-id="b8ee6-105">The *max* parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a small buffer pool.</span></span> <span data-ttu-id="b8ee6-106">Se o `max` valor for zero, não haverá nenhum limite superior para o número de buffers que podem estar em um pool de buffers pequeno.</span><span class="sxs-lookup"><span data-stu-id="b8ee6-106">If the `max` value is zero, then there is no upper limit to the number of buffers that can be in a small buffer pool.</span></span>  
  
 <span data-ttu-id="b8ee6-107">O valor do parâmetro **min** especifica o número mínimo de buffers de memória que deve ser mantido no pool de buffers de memória pequenos.</span><span class="sxs-lookup"><span data-stu-id="b8ee6-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of small memory buffers.</span></span> <span data-ttu-id="b8ee6-108">Mediante solicitação do gerenciador de memória do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], todos os pools de buffers extras serão liberados, mas esse número mínimo de buffers será mantido.</span><span class="sxs-lookup"><span data-stu-id="b8ee6-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="b8ee6-109">Se, contudo, o valor especificado de **min** for zero, todos os buffers de memória serão liberados.</span><span class="sxs-lookup"><span data-stu-id="b8ee6-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="b8ee6-110">Sob certas circunstâncias, o número de buffers alocados atualmente é menor que o valor especificado pelo parâmetro **min** .</span><span class="sxs-lookup"><span data-stu-id="b8ee6-110">Under certain circumstances the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8ee6-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8ee6-111">See Also</span></span>  
 <span data-ttu-id="b8ee6-112">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8ee6-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b8ee6-113">[Opção de configuração de servidor ft crawl bandwidth](ft-crawl-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="b8ee6-113">[ft crawl bandwidth Server Configuration Option](ft-crawl-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="b8ee6-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b8ee6-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
