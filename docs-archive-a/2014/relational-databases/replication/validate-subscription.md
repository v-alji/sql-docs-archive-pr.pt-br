---
title: Validar Assinatura | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 010b5b2e9778ccf37133b0a84796373c012290f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571922"
---
# <a name="validate-subscription"></a><span data-ttu-id="c6135-102">Validar Assinatura</span><span class="sxs-lookup"><span data-stu-id="c6135-102">Validate Subscription</span></span>
  <span data-ttu-id="c6135-103">Use a caixa de diálogo **Validar Assinatura** para especificar que uma assinatura em uma publicação de mesclagem deve ser validada na próxima execução de assinatura do Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="c6135-103">Use the **Validate Subscription** dialog box to specify that a subscription to a merge publication should be validated the next time the Merge Agent for the subscription runs.</span></span> <span data-ttu-id="c6135-104">Os resultados de validação são exibidos no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="c6135-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="c6135-105">Para obter mais informações, consulte [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="c6135-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="c6135-106">Também é possível validar todas as assinaturas para uma publicação de mesclagem clicando com o botão direito do mouse em uma publicação no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e clicando em **Validar Todas as Assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="c6135-106">It is also possible to validate all subscriptions to a merge publication by right-clicking a publication in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate All Subscriptions**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6135-107">Opções</span><span class="sxs-lookup"><span data-stu-id="c6135-107">Options</span></span>  
 <span data-ttu-id="c6135-108">**Data da última tentativa de validação**</span><span class="sxs-lookup"><span data-stu-id="c6135-108">**Date of the last attempted validation**</span></span>  
 <span data-ttu-id="c6135-109">A data da última sessão do Merge Agent que incluiu validação de assinatura, independentemente de a validação ter tido êxito.</span><span class="sxs-lookup"><span data-stu-id="c6135-109">The date of the last Merge Agent session that included subscription validation, whether or not that validation was successful.</span></span>  
  
 <span data-ttu-id="c6135-110">**Data da última validação bem-sucedida**</span><span class="sxs-lookup"><span data-stu-id="c6135-110">**Date of the last successful validation**</span></span>  
 <span data-ttu-id="c6135-111">A data da última sessão do Merge Agent que incluiu uma validação de assinatura bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c6135-111">The date of the last Merge Agent session that included a successful subscription validation.</span></span>  
  
 <span data-ttu-id="c6135-112">**Validar esta assinatura**</span><span class="sxs-lookup"><span data-stu-id="c6135-112">**Validate this subscription**</span></span>  
 <span data-ttu-id="c6135-113">Selecione para validar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="c6135-113">Select to validate the subscription.</span></span>  
  
 <span data-ttu-id="c6135-114">**Opções**</span><span class="sxs-lookup"><span data-stu-id="c6135-114">**Options**</span></span>  
 <span data-ttu-id="c6135-115">Clique para acessar a caixa de diálogo **Opções de Validação de Assinatura** , que permite especificar se deve ser usada a validação de contagem de linhas ou validação de soma de verificação binária.</span><span class="sxs-lookup"><span data-stu-id="c6135-115">Click to access the **Subscription Validation Options** dialog box, which allows you to specify whether to use row count validation or binary checksum validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6135-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6135-116">See Also</span></span>  
 [<span data-ttu-id="c6135-117">Validar os dados replicados</span><span class="sxs-lookup"><span data-stu-id="c6135-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
