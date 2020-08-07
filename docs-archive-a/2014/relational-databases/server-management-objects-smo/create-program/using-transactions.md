---
title: Usando transações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, transactions
- transactions [SMO]
- SMO [SQL Server], transactions
ms.assetid: 399aded8-bee3-4cfb-a671-1877c7d0de9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a075719c8ed31ffcc1c34f2d013a8beb0ae40dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575067"
---
# <a name="using-transactions"></a><span data-ttu-id="f499f-102">Usando transações</span><span class="sxs-lookup"><span data-stu-id="f499f-102">Using Transactions</span></span>
  <span data-ttu-id="f499f-103">No SMO ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects), o processamento de transações é feito por meio da conexão com a instância de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="f499f-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), transaction processing is achieved through the connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="f499f-104">O <xref:Microsoft.SqlServer.Management.Common.ServerConnection> objeto é referenciado pela <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> Propriedade do <xref:Microsoft.SqlServer.Management.Smo.Server> objeto quando a conexão é estabelecida.</span><span class="sxs-lookup"><span data-stu-id="f499f-104">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object is referenced by the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object when the connection is established.</span></span> <span data-ttu-id="f499f-105">Métodos como <xref:Microsoft.SqlServer.Management.Common.DataTransferProgressEventType.StartTransaction>, <xref:Microsoft.SqlServer.Management.Common.ServerConnection.RollBackTransaction%2A>e <xref:Microsoft.SqlServer.Management.Common.ServerConnection.CommitTransaction%2A> pertencem à propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="f499f-105">Methods such as <xref:Microsoft.SqlServer.Management.Common.DataTransferProgressEventType.StartTransaction>, <xref:Microsoft.SqlServer.Management.Common.ServerConnection.RollBackTransaction%2A>, and <xref:Microsoft.SqlServer.Management.Common.ServerConnection.CommitTransaction%2A> belong to the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f499f-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f499f-106">See Also</span></span>  
 [<span data-ttu-id="f499f-107">Criando programas SMO</span><span class="sxs-lookup"><span data-stu-id="f499f-107">Creating SMO Programs</span></span>](creating-smo-programs.md)  
  
  
