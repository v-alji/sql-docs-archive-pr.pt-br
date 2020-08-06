---
title: Otimizar o desempenho da replicação de mesclagem com o controle de exclusão condicional | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conditional delete tracking [SQL Server replication]
- merge replication [SQL Server replication], conditional delete tracking
- articles [SQL Server replication], conditional delete tracking
ms.assetid: 58f120a3-ea3a-4e97-93f0-0eb4e580ecf2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46fc189d2a2e0ebf5ea44775585a69d52783a7e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568490"
---
# <a name="optimize-merge-replication-performance-with-conditional-delete-tracking"></a><span data-ttu-id="76a17-102">Otimizar o desempenho da replicação de mesclagem com o controle de exclusão condicional</span><span class="sxs-lookup"><span data-stu-id="76a17-102">Optimize Merge Replication Performance with Conditional Delete Tracking</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="76a17-103">Com a replicação de mesclagem você pode especificar que as exclusões para um ou mais artigos não devem ser controladas pelos gatilhos de replicação e pelas tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="76a17-103">With merge replication you can specify that deletes for one or more articles should not be tracked by replication triggers and system tables.</span></span> <span data-ttu-id="76a17-104">Se especificar essa opção para um artigo, as exclusões não serão controladas nem replicadas do Publicador ou de qualquer Assinante.</span><span class="sxs-lookup"><span data-stu-id="76a17-104">If you specify this option for an article, deletes are not tracked or replicated from the Publisher or any Subscribers.</span></span> <span data-ttu-id="76a17-105">Essa opção está disponível para dar suporte a vários cenários de aplicativos e para oferecer uma otimização de desempenho para os casos nos quais a replicação de exclusões não é necessária ou desejada.</span><span class="sxs-lookup"><span data-stu-id="76a17-105">This option is available to support a number of application scenarios and to provide a performance optimization for cases in which the replication of deletes is not necessary or desirable.</span></span> <span data-ttu-id="76a17-106">O desempenho é melhorado de três maneiras: os metadados para exclusões não são armazenados, as exclusões não são enumeradas durante a sincronização e as exclusões não são replicadas para nem aplicadas ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="76a17-106">Performance is enhanced in three ways: metadata for deletes is not stored; deletes are not enumerated during synchronization; deletes are not replicated to and applied at the Subscriber.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76a17-107">Para usar artigos de somente download, o nível de compatibilidade da publicação deve ser pelo menos 90RTM.</span><span class="sxs-lookup"><span data-stu-id="76a17-107">To use download-only articles, the compatibility level of the publication must be at least 90RTM.</span></span>  
  
 <span data-ttu-id="76a17-108">A opção pode ser especificada na criação de uma publicação ou pode ser alternada para ativada e desativada se um aplicativo necessitar que algumas exclusões sejam replicadas e outras não, como as exclusões de lotes.</span><span class="sxs-lookup"><span data-stu-id="76a17-108">The option can be specified when a publication is created or it can be toggled on and off if an application requires that some deletes be replicated and that others not be replicated, such as batch deletes.</span></span> <span data-ttu-id="76a17-109">Os exemplos a seguir ilustram os modos nos quais essa opção poderá ser usada em um aplicativo:</span><span class="sxs-lookup"><span data-stu-id="76a17-109">The following examples illustrate ways in which this option might be used in an application:</span></span>  
  
-   <span data-ttu-id="76a17-110">O aplicativo para uma força de vendas móvel tem normalmente tabelas como **SalesOrderHeader**, **SalesOrderDetail** e **Produto**.</span><span class="sxs-lookup"><span data-stu-id="76a17-110">An application for a mobile sales force typically has tables such as **SalesOrderHeader**, **SalesOrderDetail** and **Product**.</span></span> <span data-ttu-id="76a17-111">Os pedidos são inseridos no Assinante e replicados para o Publicador, que, muitas vezes, fornece dados a um sistema de efetivação de pedidos.</span><span class="sxs-lookup"><span data-stu-id="76a17-111">Orders are entered at the Subscriber and then replicated to the Publisher, which often supplies data to an order fulfillment system.</span></span> <span data-ttu-id="76a17-112">Vários trabalhadores externos usam dispositivos portáteis que têm um armazenamento limitado: após o pedido ser recebido no Publicador, ele pode ser excluído do Assinante.</span><span class="sxs-lookup"><span data-stu-id="76a17-112">Many mobile workers use handheld devices which have limited storage: after the order is received at the Publisher, it can be deleted at the Subscriber.</span></span> <span data-ttu-id="76a17-113">A exclusão não é propagada ao Publicador, pois o pedido continua ativo no sistema.</span><span class="sxs-lookup"><span data-stu-id="76a17-113">The delete is not propagated to the Publisher, because the order is still active in the system.</span></span>  
  
     <span data-ttu-id="76a17-114">Nesse cenário, as exclusões não serão controladas para as tabelas **SalesOrderHeader** e **SalesOrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="76a17-114">In this scenario, deletes would not be tracked for the **SalesOrderHeader** and **SalesOrderDetail** tables.</span></span> <span data-ttu-id="76a17-115">As exclusões serão controladas na tabela **Produto** , pois se um produto for excluído no Publicador, a exclusão deverá ser enviada ao Assinante para manter a lista de produtos atualizada.</span><span class="sxs-lookup"><span data-stu-id="76a17-115">Deletes would be tracked for the **Product** table, because if a product is deleted at the Publisher, the delete should be sent to the Subscriber to keep the product list up to date.</span></span>  
  
-   <span data-ttu-id="76a17-116">Um aplicativo armazena os dados históricos em uma tabela como a **TransactionHistory**, que é limpa periodicamente para remover registros antigos com mais de um ano.</span><span class="sxs-lookup"><span data-stu-id="76a17-116">An application could store historical data in a table such as **TransactionHistory**, which is periodically purged of records older than a year.</span></span> <span data-ttu-id="76a17-117">A tabela pode ser filtrada de modo que os Assinantes recebam dados sobre transações dentro do mês atual.</span><span class="sxs-lookup"><span data-stu-id="76a17-117">The table could be filtered such that Subscribers only receive data on transactions within the current month.</span></span> <span data-ttu-id="76a17-118">Exclusões mensais de lotes no Publicador que remove dados mais antigos não são relevantes para os Assinantes, mas poderão ser controladas e enumeradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="76a17-118">Monthly batch deletes at the Publisher that purge older data are not relevant to Subscribers, but they would still be tracked and enumerated by default.</span></span>  
  
     <span data-ttu-id="76a17-119">Nesse cenário, antes de o processamento do lote ocorrer, a atividade pode ser interrompida no sistema e o aplicativo irá desabilitar o controle das exclusões.</span><span class="sxs-lookup"><span data-stu-id="76a17-119">In this scenario, before the batch processing occurred, activity could be stopped on the system, and the application could disable the tracking of deletes.</span></span> <span data-ttu-id="76a17-120">Após a conclusão do processamento, o controle poderá ser habilitado novamente.</span><span class="sxs-lookup"><span data-stu-id="76a17-120">After the processing has finished, tracking could again be enabled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="76a17-121">Se uma outra atividade continuar no Publicador, você deverá garantir que as exclusões que deveriam ser propagadas para o Assinante não ocorram enquanto o controle das exclusões estiver desabilitado.</span><span class="sxs-lookup"><span data-stu-id="76a17-121">If other activity continues at the Publisher, you must ensure that deletes that should be propagated to Subscribers do not occur while delete tracking is disabled.</span></span>  
  
 <span data-ttu-id="76a17-122">**Para especificar que as exclusões não devem ser controladas**</span><span class="sxs-lookup"><span data-stu-id="76a17-122">**To specify that deletes should not be tracked**</span></span>  
  
-   <span data-ttu-id="76a17-123">Programação [!INCLUDE[tsql](../../../includes/tsql-md.md)] de replicação: [Especificar que as exclusões não devem ser controladas para artigos de mesclagem &#40;programação Transact-SQL de replicação&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span><span class="sxs-lookup"><span data-stu-id="76a17-123">Replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] programming: [Specify That Deletes Should Not Be Tracked For Merge Articles &#40;Replication Transact-SQL Programming&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a17-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76a17-124">See Also</span></span>  
 <span data-ttu-id="76a17-125">[Opções de artigo para replicação de mesclagem](article-options-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="76a17-125">[Article Options for Merge Replication](article-options-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="76a17-126">Otimizar o desempenho da replicação de mesclagem com artigos de somente download</span><span class="sxs-lookup"><span data-stu-id="76a17-126">Optimize Merge Replication Performance with Download-Only Articles</span></span>](optimize-merge-replication-performance-with-download-only-articles.md)  
  
  
