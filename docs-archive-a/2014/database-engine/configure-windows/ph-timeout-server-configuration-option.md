---
title: Opção de configuração de servidor PH timeout | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- time limit for protocol handler wait [SQL Server]
- timeout options [SQL Server], ph timeout option
- protocols [SQL Server], timing out
- ph timeout option
ms.assetid: ed19a07c-83fe-4582-9c9e-41b1ce571850
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 515ed74a4b92259d53770bf6d970626eba686453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679515"
---
# <a name="ph-timeout-server-configuration-option"></a><span data-ttu-id="cc21f-102">Opção de configuração de servidor PH timeout</span><span class="sxs-lookup"><span data-stu-id="cc21f-102">PH timeout Server Configuration Option</span></span>
  <span data-ttu-id="cc21f-103">Use a opção tempo limite PH para especificar o tempo, em segundos, que o manipulador de protocolo de texto completo deve aguardar para se conectar a um banco de dados antes que o tempo limite seja excedido. O valor padrão é 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="cc21f-103">Use the PH timeout option to specify the time, in seconds, that the full-text protocol handler should wait to connect to a database before timing out. The default value is 60 seconds.</span></span> <span data-ttu-id="cc21f-104">Aumente o valor tempo limite ph quando as tentativas de conexão estiverem excedendo o tempo limite devido a problemas temporários na rede.</span><span class="sxs-lookup"><span data-stu-id="cc21f-104">Increase the ph timeout value when connection attempts are timing out due to temporary network issues.</span></span>  
  
 <span data-ttu-id="cc21f-105">O manipulador de protocolo de texto completo é hospedado no host de daemon de filtro e é usado para buscar no SQL Server os dados de texto completo a serem indexados.</span><span class="sxs-lookup"><span data-stu-id="cc21f-105">The full-text protocol handler is hosted in the filter daemon host and is used to fetch from SQL Server the data to be full-text indexed.</span></span> <span data-ttu-id="cc21f-106">Para obter mais informações sobre os componentes da pesquisa de texto completo, veja [Pesquisa de Texto Completo](../../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="cc21f-106">For more information about full-text search components, see [Full-Text Search](../../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="cc21f-107">Ao tentar buscar uma linha de dados, se o manipulador de protocolo não puder se conectar ao SQL Server dentro do tempo especificado, ele informará um erro de tempo limite para aquela linha.</span><span class="sxs-lookup"><span data-stu-id="cc21f-107">When attempting to fetch a data row, if the protocol handler cannot connect to SQL Server within the specified time, it reports a time-out error for that row.</span></span> <span data-ttu-id="cc21f-108">A busca de texto completo será feita na linha mais tarde.</span><span class="sxs-lookup"><span data-stu-id="cc21f-108">The full-text gatherer will retry the row later.</span></span> <span data-ttu-id="cc21f-109">Para obter mais informações sobre o gatherer de texto completo, veja [Popular índices de texto completo](../../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="cc21f-109">For more information about the full-text gatherer, see [Populate Full-Text Indexes](../../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc21f-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc21f-110">See Also</span></span>  
 <span data-ttu-id="cc21f-111">[Pesquisa de Texto Completo](../../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="cc21f-111">[Full-Text Search](../../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="cc21f-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc21f-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cc21f-113">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cc21f-113">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cc21f-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc21f-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
