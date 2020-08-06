---
title: Habilitar a inicialização com um backup para publicações transacionais (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: 9df00514-aa9d-4ac6-9766-d226c9958175
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e22614c8c4f5250db3966e747b686091512774
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569909"
---
# <a name="enable-initialization-with-a-backup-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="b9e12-102">Habilitar a inicialização com um backup para publicações transacionais (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b9e12-102">Enable Initialization with a Backup for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b9e12-103">Para inicializar uma assinatura de uma publicação transacional a partir de um backup, habilite a publicação para permitir a inicialização a partir de um backup e então especifique informações de backup ao criar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="b9e12-103">To initialize a subscription to a transactional publication from a backup, enable the publication to allow initialization from a backup, and then specify backup information when creating the subscription:</span></span>  
  
-   <span data-ttu-id="b9e12-104">Habilite a publicação na página **Opções de Assinatura** da caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="b9e12-104">Enable the publication on the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="b9e12-105">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b9e12-105">For more information about accessing this dialog box, see [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="b9e12-106">Especifique informações de backup com o procedimento armazenado [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9e12-106">Specify backup information with the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="b9e12-107">Para mais informações sobre os parâmetros exigidos por **sp_addsubscription**, consulte [Inicializar uma assinatura transacional de um Backup &#40;programação de Transact-SQL de replicação&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b9e12-107">For more information about the parameters required by **sp_addsubscription**, see [Initialize a Transactional Subscription from a Backup &#40;Replication Transact-SQL Programming&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span></span>  
  
### <a name="to-enable-initialization-with-a-backup"></a><span data-ttu-id="b9e12-108">Para habilitar a inicialização com um backup</span><span class="sxs-lookup"><span data-stu-id="b9e12-108">To enable initialization with a backup</span></span>  
  
1.  <span data-ttu-id="b9e12-109">Na página **Opções de Assinatura** da caixa de diálogo **Propriedades de Publicação – \<Publication>** , selecione um valor **Verdadeiro** para a opção **Permitir inicialização dos arquivos de backup**.</span><span class="sxs-lookup"><span data-stu-id="b9e12-109">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, select a value of **True** for the **Allow initialization from backup files** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e12-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9e12-110">See Also</span></span>  
 [<span data-ttu-id="b9e12-111">Inicializar uma assinatura transacional sem um instantâneo</span><span class="sxs-lookup"><span data-stu-id="b9e12-111">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
