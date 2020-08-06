---
title: Opção de configuração de servidor max full-text crawl range | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- crawls [full-text search]
- max full-text crawl range option
ms.assetid: a49de86b-0891-4dcd-89c0-ead30aab00e0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1dbd9e44518b6e849a06a76e21fc605172fd2ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678960"
---
# <a name="max-full-text-crawl-range-server-configuration-option"></a><span data-ttu-id="acbbb-102">Opção max full-text crawl range de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="acbbb-102">max full-text crawl range Server Configuration Option</span></span>
  <span data-ttu-id="acbbb-103">Use a opção **max full-text crawl range** para otimizar a utilização de CPU, o que melhora o desempenho durante um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="acbbb-103">Use the **max full-text crawl range** option to optimize CPU utilization, which improves crawl performance during a full crawl.</span></span> <span data-ttu-id="acbbb-104">Usando esta opção, você pode especificar o número de partições que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deverá usar durante um rastreamento de índice completo.</span><span class="sxs-lookup"><span data-stu-id="acbbb-104">Using this option, you can specify the number of partitions that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should use during a full index crawl.</span></span> <span data-ttu-id="acbbb-105">Por exemplo, se houver muitas CPUs e sua utilização não for a ideal, você pode aumentar o valor máximo dessa opção.</span><span class="sxs-lookup"><span data-stu-id="acbbb-105">For example, if there are many CPUs and their utilization is not optimal, you can increase the maximum value of this option.</span></span> <span data-ttu-id="acbbb-106">Além dessa opção, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa vários outros fatores, como o número de linhas na tabela e o número de CPUs, para determinar o número real de partições usadas.</span><span class="sxs-lookup"><span data-stu-id="acbbb-106">In addition to this option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses a number of other factors, such as the number of rows in the table and the number of CPUs, to determine the actual number of partitions used.</span></span>  
  
 <span data-ttu-id="acbbb-107">O valor padrão desta opção é 4; o valor mínimo é 1 e o valor máximo, 256.</span><span class="sxs-lookup"><span data-stu-id="acbbb-107">The default value of this option is 4; the minimum value is 1, and the maximum value is 256.</span></span> <span data-ttu-id="acbbb-108">As alterações feitas nesta opção afetam somente os rastreamentos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="acbbb-108">Changes made to this option affect only subsequent crawls.</span></span> <span data-ttu-id="acbbb-109">Os rastreamentos em andamento não serão afetados por alterações na configuração desta opção.</span><span class="sxs-lookup"><span data-stu-id="acbbb-109">Crawls in process will not be affected by a change in this option setting.</span></span>  
  
 <span data-ttu-id="acbbb-110">A opção **max full-text crawl range** é uma opção avançada.</span><span class="sxs-lookup"><span data-stu-id="acbbb-110">The **max full-text crawl range** option is an advanced option.</span></span> <span data-ttu-id="acbbb-111">Se você estiver usando o procedimento armazenado do sistema **sp_configure** para alterar a configuração, só será possível alterar **max full-text crawl range** quando **show advanced options** for definido como 1.</span><span class="sxs-lookup"><span data-stu-id="acbbb-111">If you are using the **sp_configure** system stored procedure to change the setting, you can change **max full-text crawl range** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="acbbb-112">A configuração entra em vigor imediatamente sem a reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="acbbb-112">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acbbb-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="acbbb-113">See Also</span></span>  
 <span data-ttu-id="acbbb-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="acbbb-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="acbbb-115">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="acbbb-115">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="acbbb-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="acbbb-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
