---
title: 'Lição 3: Sincronizando a assinatura com a publicação de mesclagem | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: rothja
ms.author: jroth
ms.openlocfilehash: bf0256c69d69d1236869fa83285bf4dbf5c462da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684653"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a><span data-ttu-id="f5b1c-102">Lição 3: Sincronizando a assinatura com a publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="f5b1c-102">Lesson 3: Synchronizing the Subscription to the Merge Publication</span></span>
  <span data-ttu-id="f5b1c-103">Nesta lição, você iniciará o Merge Agent para inicializar a assinatura, usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5b1c-103">In this lesson, you will start the Merge Agent to initialize the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f5b1c-104">Você também usa este procedimento para sincronizar-se com o Publicador.</span><span class="sxs-lookup"><span data-stu-id="f5b1c-104">You also use this procedure to synchronize with the Publisher.</span></span> <span data-ttu-id="f5b1c-105">Esta lição exige que você tenha concluído a lição anterior, [Lição 2: Criando uma assinatura na publicação de mesclagem](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="f5b1c-105">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a><span data-ttu-id="f5b1c-106">Para iniciar a sincronização e inicializar a assinatura</span><span class="sxs-lookup"><span data-stu-id="f5b1c-106">To start synchronization and initialize the subscription</span></span>  
  
1.  <span data-ttu-id="f5b1c-107">Conecte-se ao Assinante no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o nó de servidor, e em seguida, expanda a pasta **Replicação** .</span><span class="sxs-lookup"><span data-stu-id="f5b1c-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="f5b1c-108">Na pasta **Assinaturas Locais** , clique com o botão direito do mouse na assinatura no banco de dados **SalesOrdersReplica** e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="f5b1c-108">In the **Local Subscriptions** folder, right-click the subscription in the **SalesOrdersReplica** database, and then click **View Synchronization Status**.</span></span>  
  
3.  <span data-ttu-id="f5b1c-109">Clique em **Iniciar** para inicializar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="f5b1c-109">Click **Start** to initialize the subscription.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f5b1c-110">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f5b1c-110">Next Steps</span></span>  
 <span data-ttu-id="f5b1c-111">Você executou com sucesso o Merge Agente para iniciar a sincronização e inicializar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="f5b1c-111">You have successfully run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="f5b1c-112">Você também pode inserir, atualizar ou excluir dados nas tabelas **SalesOrderHeader** ou **SalesOrderDetail** no Publicador ou Assinante, repita esse procedimento quando a conectividade da rede estiver disponível para sincronizar dados entre o Publicador e o Assinante e, em seguida, consulte as tabelas **SalesOrderHeader** ou **SalesOrderDetail** no outro servidor para visualizar as alterações replicadas.</span><span class="sxs-lookup"><span data-stu-id="f5b1c-112">You can also insert, update, or delete data in the **SalesOrderHeader** or **SalesOrderDetail** tables at the Publisher or Subscriber, repeat this procedure when network connectivity is available to synchronize data between the Publisher and the Subscriber, and then query the **SalesOrderHeader** or **SalesOrderDetail** tables at the other server to view the replicated changes.</span></span>  
  
 <span data-ttu-id="f5b1c-113">Isso completa o tutorial Replicando Dados com Clientes Móveis.</span><span class="sxs-lookup"><span data-stu-id="f5b1c-113">This completes the Replicating Data with Mobile Clients tutorial.</span></span> <span data-ttu-id="f5b1c-114">Para um tutorial semelhante que use replicação transacional, consulte [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span><span class="sxs-lookup"><span data-stu-id="f5b1c-114">For a similar tutorial that uses transactional replication, see [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b1c-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5b1c-115">See Also</span></span>  
 <span data-ttu-id="f5b1c-116">[Inicializar uma assinatura com um instantâneo](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="f5b1c-116">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="f5b1c-117">[Sincronizar dados](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="f5b1c-117">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="f5b1c-118">Sincronizar uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="f5b1c-118">Synchronize a Pull Subscription</span></span>](synchronize-a-pull-subscription.md)  
  
  
