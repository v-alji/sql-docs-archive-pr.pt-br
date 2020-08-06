---
title: Inicializar uma assinatura | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- snapshot replication [SQL Server], initializing subscriptions
- transactional replication, initializing subscriptions
- initializing subscriptions [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], about initializing subscriptions
- merge replication [SQL Server replication], initializing subscriptions
ms.assetid: d6013845-cb7a-4203-8e21-edce32f1d330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1f024d360fdeab477ace09970b4f140a97696c2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569884"
---
# <a name="initialize-a-subscription"></a><span data-ttu-id="651b2-102">Inicializar uma assinatura</span><span class="sxs-lookup"><span data-stu-id="651b2-102">Initialize a Subscription</span></span>
  <span data-ttu-id="651b2-103">Os assinantes em uma topologia de replicação devem ser inicializados, de modo a terem uma cópia do esquema de cada artigo na publicação que assinaram e quaisquer objetos de replicação que sejam necessários, como procedimentos armazenados, gatilhos e tabelas de metadados.</span><span class="sxs-lookup"><span data-stu-id="651b2-103">Subscribers in a replication topology must be initialized, so that they have a copy of the schema from each article in the publication they have subscribed to and any replication objects that are required, such as stored procedures, triggers, and metadata tables.</span></span> <span data-ttu-id="651b2-104">Além disso, o Assinante recebe, geralmente, um conjunto de dados inicial.</span><span class="sxs-lookup"><span data-stu-id="651b2-104">In addition, the Subscriber typically receives an initial dataset.</span></span> <span data-ttu-id="651b2-105">O método de inicialização padrão usa um instantâneo completo que inclui esquema, objetos de replicação e dados, mas as publicações também podem ser inicializadas sem um instantâneo completo.</span><span class="sxs-lookup"><span data-stu-id="651b2-105">The default initialization method uses a full snapshot that includes schema, replication objects, and data, but publications can also be initialized without a full snapshot.</span></span>  
  
 <span data-ttu-id="651b2-106">Para obter mais informações, consulte [Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) e [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="651b2-106">For more information, see [Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) and [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
  
