---
title: Adicionar assinante não SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e36d048b11fcc71b27ab0ab2ee815b0284187c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574669"
---
# <a name="add-non-sql-server-subscriber"></a><span data-ttu-id="de75b-102">Adicionar Assinante não SQL Server</span><span class="sxs-lookup"><span data-stu-id="de75b-102">Add Non-SQL Server Subscriber</span></span>
  <span data-ttu-id="de75b-103">A replicação oferece suporte à criação de assinaturas push para publicações de instantâneo e transacionais para Assinantes Oracle e IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="de75b-103">Replication supports creating push subscriptions to snapshot and transactional publications for Oracle and IBM DB2 Subscribers.</span></span>  
  
## <a name="options"></a><span data-ttu-id="de75b-104">Opções</span><span class="sxs-lookup"><span data-stu-id="de75b-104">Options</span></span>  
 <span data-ttu-id="de75b-105">**Tipo de Assinante a adicionar**</span><span class="sxs-lookup"><span data-stu-id="de75b-105">**Type of Subscriber to add**</span></span>  
 <span data-ttu-id="de75b-106">Selecione um Assinante Oracle ou um Assinante IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="de75b-106">Select an Oracle Subscriber or IBM DB2 Subscriber.</span></span> <span data-ttu-id="de75b-107">Para obter mais informações sobre o suporte para esses Assinantes, consulte [Assinantes não SQL Server](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="de75b-107">For more information about support for these Subscribers, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
 <span data-ttu-id="de75b-108">**Nome da fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="de75b-108">**Data source name**</span></span>  
 <span data-ttu-id="de75b-109">O nome usado para localizar o banco de dados em uma rede.</span><span class="sxs-lookup"><span data-stu-id="de75b-109">The name used to locate the database on a network.</span></span> <span data-ttu-id="de75b-110">A replicação produz uma sequência de conexão para o banco de dados usando o nome da fonte de dados, combinando com o logon, senha e qualquer opção de conexão especificada na página **Segurança do Agente de Distribuição** neste assistente.</span><span class="sxs-lookup"><span data-stu-id="de75b-110">Replication produces a connection string for the database using the data source name, combined with the login, password, and any connection options you specify in the **Distribution Agent Security** page in this wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de75b-111">O nome da fonte de dados e a cadeia de conexão não são validados pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] até que o Agente de Distribuição tente inicializar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="de75b-111">The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de75b-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de75b-112">See Also</span></span>  
 <span data-ttu-id="de75b-113">[Criar uma assinatura para um assinante não SQL Server](create-a-subscription-for-a-non-sql-server-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="de75b-113">[Create a Subscription for a Non-SQL Server Subscriber](create-a-subscription-for-a-non-sql-server-subscriber.md) </span></span>  
 <span data-ttu-id="de75b-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="de75b-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="de75b-115">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="de75b-115">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
