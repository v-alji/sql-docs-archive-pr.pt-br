---
title: Validar Todas as Assinaturas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27a7a4f5e5c3c303d5a1cbe257c0a0e9b531e824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576268"
---
# <a name="validate-all-subscriptions"></a><span data-ttu-id="0f12b-102">Validar Todas as Assinaturas</span><span class="sxs-lookup"><span data-stu-id="0f12b-102">Validate All Subscriptions</span></span>
  <span data-ttu-id="0f12b-103">Use a caixa de diálogo **Validar Todas as Assinaturas** para especificar que todas as assinaturas em uma publicação de mesclagem devem ser validadas na próxima execução do Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="0f12b-103">Use the **Validate All Subscriptions** dialog box to specify that all subscriptions to a merge publication should be validated the next time the Merge Agent for each subscription runs.</span></span> <span data-ttu-id="0f12b-104">Os resultados de validação são exibidos no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="0f12b-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="0f12b-105">Para obter mais informações, consulte [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="0f12b-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="0f12b-106">Também é possível validar uma única assinatura clicando com o botão direito em uma assinatura no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e clicando em **Validar Assinatura**.</span><span class="sxs-lookup"><span data-stu-id="0f12b-106">It is also possible to validate a single subscription by right-clicking a subscription in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate Subscription**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0f12b-107">Opções</span><span class="sxs-lookup"><span data-stu-id="0f12b-107">Options</span></span>  
 <span data-ttu-id="0f12b-108">**Verificar as contagens de linhas somente**</span><span class="sxs-lookup"><span data-stu-id="0f12b-108">**Verify the row counts only**</span></span>  
 <span data-ttu-id="0f12b-109">Selecione para validar se a tabela no Assinante tem o mesmo número de linhas que a tabela no Publicador.</span><span class="sxs-lookup"><span data-stu-id="0f12b-109">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="0f12b-110">Esse método não valida que o conteúdo de correspondências de linhas.</span><span class="sxs-lookup"><span data-stu-id="0f12b-110">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="0f12b-111">A validação de número de linhas fornece uma abordagem superficial à validação que pode alertá-lo sobre problemas com seus dados.</span><span class="sxs-lookup"><span data-stu-id="0f12b-111">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="0f12b-112">**Verificar as contagens de linhas e comparar as somas de verificação para verificar os dados da linha**</span><span class="sxs-lookup"><span data-stu-id="0f12b-112">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="0f12b-113">Além de contar o número de linhas no Publicador e no Assinante, uma soma de verificação de todos os dados é calculada usando o algoritmo de soma de verificação binária.</span><span class="sxs-lookup"><span data-stu-id="0f12b-113">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="0f12b-114">Se a contagem de linhas falhar, a soma de verificação não será executada.</span><span class="sxs-lookup"><span data-stu-id="0f12b-114">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="0f12b-115">Essa opção não é válida para [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f12b-115">This option is not valid for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f12b-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f12b-116">See Also</span></span>  
 [<span data-ttu-id="0f12b-117">Validar os dados replicados</span><span class="sxs-lookup"><span data-stu-id="0f12b-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
