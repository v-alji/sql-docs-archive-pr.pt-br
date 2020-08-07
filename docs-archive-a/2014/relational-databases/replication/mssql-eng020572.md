---
title: MSSQL_ENG020572 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583533"
---
# <a name="mssql_eng020572"></a><span data-ttu-id="1979a-102">MSSQL_ENG020572</span><span class="sxs-lookup"><span data-stu-id="1979a-102">MSSQL_ENG020572</span></span>
    
## <a name="message-details"></a><span data-ttu-id="1979a-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="1979a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1979a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="1979a-104">Product Name</span></span>|<span data-ttu-id="1979a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1979a-105">SQL Server</span></span>|  
|<span data-ttu-id="1979a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="1979a-106">Event ID</span></span>|<span data-ttu-id="1979a-107">20572</span><span class="sxs-lookup"><span data-stu-id="1979a-107">20572</span></span>|  
|<span data-ttu-id="1979a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="1979a-108">Event Source</span></span>|<span data-ttu-id="1979a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1979a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1979a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1979a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="1979a-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="1979a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="1979a-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="1979a-112">Message Text</span></span>|<span data-ttu-id="1979a-113">A assinatura do assinante '%s' para o artigo '%s' na publicação '%s' foi reiniciada após uma falha na validação.</span><span class="sxs-lookup"><span data-stu-id="1979a-113">Subscriber '%s' subscription to article '%s' in publication '%s' has been reinitialized after a validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1979a-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="1979a-114">Explanation</span></span>  
 <span data-ttu-id="1979a-115">Os dados no Assinante foram validados de acordo com os dados no Publicador, e os dados não corresponderam, portanto, houve falha na validação.</span><span class="sxs-lookup"><span data-stu-id="1979a-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="1979a-116">Quando você especificou que a validação deveria ser realizada, selecionou a opção de reinicialização da assinatura no caso de falha de validação.</span><span class="sxs-lookup"><span data-stu-id="1979a-116">When you specified that validation should be performed, you selected the option that a subscription should be reinitialized if validation failed.</span></span> <span data-ttu-id="1979a-117">Reinicializar uma assinatura envolve a aplicação de um novo instantâneo no Assinante.</span><span class="sxs-lookup"><span data-stu-id="1979a-117">Reinitializing a subscription involves applying a new snapshot at the Subscriber.</span></span> <span data-ttu-id="1979a-118">Para obter mais informações sobre validação, consulte [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="1979a-118">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1979a-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="1979a-119">User Action</span></span>  
 <span data-ttu-id="1979a-120">Dados no Publicador e no Assinante serão correspondentes após a aplicação de um novo instantâneo no Assinante.</span><span class="sxs-lookup"><span data-stu-id="1979a-120">Data at the Publisher and Subscriber will match after the new snapshot is applied at the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1979a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1979a-121">See Also</span></span>  
 [<span data-ttu-id="1979a-122">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="1979a-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
