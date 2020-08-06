---
title: Especificar um tipo de assinatura de mesclagem e prioridade de resolução de conflitos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686250"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a><span data-ttu-id="24faf-102">Especificar um tipo de assinatura de mesclagem e prioridade de resolução de conflitos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="24faf-102">Specify a Merge Subscription Type and Conflict Resolution Priority (SQL Server Management Studio)</span></span>
  <span data-ttu-id="24faf-103">Especifique um tipo de assinatura de mesclagem e prioridade de resolução de conflito na página **Tipo da Assinatura** do Assistente para Novas Assinaturas.</span><span class="sxs-lookup"><span data-stu-id="24faf-103">Specify a merge subscription type and conflict resolution priority on the **Subscription Type** page of the New Subscription Wizard.</span></span> <span data-ttu-id="24faf-104">Para mais informações sobre como usar esse assistente, consulte [Create a Pull Subscription](create-a-pull-subscription.md) e [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="24faf-104">For more information about using this wizard, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="24faf-105">O tipo de assinatura não pode ser modificado após a assinatura ser criada, mas a prioridade pode ser modificada para o tipo de assinatura do servidor na caixa de diálogo **Propriedades da Assinatura – \<Publisher>: \<PublicationDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="24faf-105">Subscription type cannot be modified after a subscription is created, but priority can be modified for the server subscription type in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box.</span></span> <span data-ttu-id="24faf-106">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) e [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="24faf-106">For more information about accessing this dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a><span data-ttu-id="24faf-107">Para especificar um tipo de assinatura de mesclagem e prioridade de resolução de conflito</span><span class="sxs-lookup"><span data-stu-id="24faf-107">To specify a merge subscription type and conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="24faf-108">Na página **Tipo da Assinatura** do Assistente para Novas Assinaturas, selecione **Cliente** ou **Servidor** para a opção **Tipo da Assinatura** .</span><span class="sxs-lookup"><span data-stu-id="24faf-108">On the **Subscription Type** page of the New Subscription Wizard, select **Client** or **Server** for the **Subscription Type** option.</span></span>  
  
2.  <span data-ttu-id="24faf-109">Se você selecionar um tipo de assinatura no **Servidor**, digite também um valor (0.00 até 99.99) para a opção **Prioridade para a Resolução de Conflitos** .</span><span class="sxs-lookup"><span data-stu-id="24faf-109">If you select a subscription type of **Server**, also enter a value (0.00 to 99.99) for the **Priority for Conflict Resolution** option.</span></span>  
  
### <a name="to-modify-the-conflict-resolution-priority"></a><span data-ttu-id="24faf-110">Para modificar a prioridade para a resolução de conflitos</span><span class="sxs-lookup"><span data-stu-id="24faf-110">To modify the conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="24faf-111">Em **Propriedades da Assinatura –\<Publisher>: \<PublicationDatabase>** no Editor, digite um valor (0,00 até 99,99) para a opção **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="24faf-111">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** at the Publisher, enter a value (0.00 to 99.99) for the **Priority** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24faf-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24faf-112">See Also</span></span>  
 <span data-ttu-id="24faf-113">[Detecção e resolução de conflito de replicação de mesclagem avançada](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="24faf-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="24faf-114">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="24faf-114">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
