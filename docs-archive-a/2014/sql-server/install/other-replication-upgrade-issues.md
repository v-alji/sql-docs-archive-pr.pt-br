---
title: Outros problemas de atualização de replicação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system tables [SQL Server], replication
- passwords [SQL Server replication]
- versions [SQL Server replication]
- connections [SQL Server replication]
- scripts [SQL Server replication]
- ActiveX controls [SQL Server replication]
ms.assetid: 8a5e74be-4992-4f17-b20c-c3dce8f49329
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e8ce3f35ead9d3322c636462f682ef391703cfe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582269"
---
# <a name="other-replication-upgrade-issues"></a><span data-ttu-id="3c481-102">Outros problemas de atualização da replicação</span><span class="sxs-lookup"><span data-stu-id="3c481-102">Other Replication Upgrade Issues</span></span>
  <span data-ttu-id="3c481-103">Este tópico aborda uma série de problemas de atualização que não são relatados pelo Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="3c481-103">This topic covers a number of upgrade issues that are not reported by Upgrade Advisor.</span></span>  
  
## <a name="versions-supported"></a><span data-ttu-id="3c481-104">Versões com suporte</span><span class="sxs-lookup"><span data-stu-id="3c481-104">Versions Supported</span></span>  
 <span data-ttu-id="3c481-105">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oferece suporte a atualizações de bancos de dados replicados de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c481-105">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supports upgrading replicated databases from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3c481-106">Você não precisa interromper a atividade de outros nós enquanto um nó está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="3c481-106">You do not have to stop activity at other nodes while a node is being upgraded.</span></span> <span data-ttu-id="3c481-107">Verifique se você está de acordo com as regras relacionadas a versões que têm suporte em uma topologia.</span><span class="sxs-lookup"><span data-stu-id="3c481-107">Ensure that you adhere to the rules regarding which versions are supported in a topology.</span></span>  
  
 <span data-ttu-id="3c481-108">Normalmente, ao fazer a replicação entre diferentes versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você ficará limitado à funcionalidade da versão anterior que está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="3c481-108">When you replicate between or among different versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you are usually limited to the functionality of the earliest version that is being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c481-109">Como o formato de armazenamento em disco do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é o mesmo em ambientes de 64 e 32 bits, a topologia de replicação pode combinar instâncias de servidor executadas em um ambiente de 32 bits e instâncias de servidor executadas em um ambiente de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3c481-109">Because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on-disk storage format is the same in the 64-bit and 32-bit environments, a replication topology can combine server instances that run in a 32-bit environment and server instances that run in a 64-bit environment.</span></span>  
  
 <span data-ttu-id="3c481-110">Para todos os tipos de replicação, a versão do Distribuidor não pode ser anterior à versão do Publicador.</span><span class="sxs-lookup"><span data-stu-id="3c481-110">For all types of replication, the Distributor version must be no earlier than the Publisher version.</span></span> <span data-ttu-id="3c481-111">(Normalmente, o Distribuidor faz parte da mesma instância que o Publicador.)</span><span class="sxs-lookup"><span data-stu-id="3c481-111">(Frequently, the Distributor is the same instance as the Publisher.)</span></span>  
  
 <span data-ttu-id="3c481-112">Para a replicação transacional, um Assinante de uma publicação transacional pode ser de qualquer uma das duas versões do Publicador.</span><span class="sxs-lookup"><span data-stu-id="3c481-112">For transactional replication, a Subscriber to a transactional publication can be any version within two versions of the Publisher version.</span></span>  
  
 <span data-ttu-id="3c481-113">Para replicação de mesclagem, um Assinante de uma publicação de mesclagem pode ser de qualquer versão anterior à versão do publicador.</span><span class="sxs-lookup"><span data-stu-id="3c481-113">For merge replication, a Subscriber to a merge publication can be any version no later than the Publisher version.</span></span>  
  
## <a name="merge-replication-batches-changes"></a><span data-ttu-id="3c481-114">Alterações em lotes da replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="3c481-114">Merge Replication Batches Changes</span></span>  
 <span data-ttu-id="3c481-115">As alterações que são feitas pelo Agente de Mesclagem são divididas em lotes para aprimorar o desempenho; assim, mais de uma linha pode ser inserida, atualizada ou excluída em uma única instrução.</span><span class="sxs-lookup"><span data-stu-id="3c481-115">Changes that are made by the Merge Agent are batched to improve performance; therefore, more than one row can be inserted, updated, or deleted within a single statement.</span></span> <span data-ttu-id="3c481-116">Se alguma tabela publicada nos bancos de dados de publicação ou de assinatura tiver gatilhos, verifique se os gatilhos conseguem lidar com inserções, atualizações e exclusões multilinha.</span><span class="sxs-lookup"><span data-stu-id="3c481-116">If any published tables in the publication or subscription databases have triggers, ensure that the triggers can handle multirow inserts, updates, and deletes.</span></span> <span data-ttu-id="3c481-117">Para obter mais informações, consulte "Considerações multilinha para gatilhos DML" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c481-117">For more information, see "Multirow Considerations for DML Triggers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="activex-control-changes"></a><span data-ttu-id="3c481-118">Alterações do controle ActiveX</span><span class="sxs-lookup"><span data-stu-id="3c481-118">ActiveX Control Changes</span></span>  
 <span data-ttu-id="3c481-119">As seguintes alterações foram feitas para controles ActiveX de replicação:</span><span class="sxs-lookup"><span data-stu-id="3c481-119">The following changes have been made for replication ActiveX controls:</span></span>  
  
-   <span data-ttu-id="3c481-120">Todos os controles ActiveX são marcados como inseguros para gerar script e para inicialização.</span><span class="sxs-lookup"><span data-stu-id="3c481-120">All ActiveX controls are marked as unsafe for scripting and initialization.</span></span>  
  
-   <span data-ttu-id="3c481-121">O controle ActiveX de Instantâneo foi descartado.</span><span class="sxs-lookup"><span data-stu-id="3c481-121">The Snapshot ActiveX control has been dropped.</span></span> <span data-ttu-id="3c481-122">Você pode criar e gerenciar instantâneos usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou programaticamente usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="3c481-122">You can create and manage snapshots by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or programmatically by using replication stored procedures.</span></span> <span data-ttu-id="3c481-123">Para obter mais informações, consulte os tópicos "Como criar e aplicar o instantâneo inicial ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" e "Como criar o instantâneo inicial (Programação Transact-SQL de replicação)" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c481-123">For more information, see the topics "How to: Create and Apply the Initial Snapshot ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" and "How to: Create the Initial Snapshot (Replication Transact-SQL Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="3c481-124">O controle ActiveX de Distribuição e o controle ActiveX de Mesclagem foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="3c481-124">The Distribution ActiveX control and Merge ActiveX control have been deprecated.</span></span> <span data-ttu-id="3c481-125">Uma funcionalidade semelhante é fornecida por aplicativos de código gerenciado que usam RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="3c481-125">Similar functionality is provided for managed code applications using Replication Management Objects (RMO).</span></span> <span data-ttu-id="3c481-126">Para obter mais informações, consulte "Sincronizando assinaturas (Programação RMO)" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c481-126">For more information, see "Synchronizing Subscriptions (RMO Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c481-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c481-127">See Also</span></span>  
 [<span data-ttu-id="3c481-128">Problemas na atualização da replicação</span><span class="sxs-lookup"><span data-stu-id="3c481-128">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
