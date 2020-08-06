---
title: MSSQL_ENG021330 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4338756a641b23bfc6f52da6b3de296bb6415756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679867"
---
# <a name="mssql_eng021330"></a><span data-ttu-id="d8a65-102">MSSQL_ENG021330</span><span class="sxs-lookup"><span data-stu-id="d8a65-102">MSSQL_ENG021330</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d8a65-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="d8a65-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8a65-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d8a65-104">Product Name</span></span>|<span data-ttu-id="d8a65-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8a65-105">SQL Server</span></span>|  
|<span data-ttu-id="d8a65-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d8a65-106">Event ID</span></span>|<span data-ttu-id="d8a65-107">21330</span><span class="sxs-lookup"><span data-stu-id="d8a65-107">21330</span></span>|  
|<span data-ttu-id="d8a65-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d8a65-108">Event Source</span></span>|<span data-ttu-id="d8a65-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8a65-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8a65-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d8a65-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d8a65-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d8a65-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d8a65-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d8a65-112">Message Text</span></span>|<span data-ttu-id="d8a65-113">Falha ao criar um subdiretório no diretório de trabalho da replicação.(% ls)</span><span class="sxs-lookup"><span data-stu-id="d8a65-113">Failed to create a sub-directory under the replication working directory.(%ls)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8a65-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="d8a65-114">Explanation</span></span>  
 <span data-ttu-id="d8a65-115">Esse erro pode ocorrer quando uma assinatura é inicializada manualmente e ocorre um problema ao criar o diretório em que os scripts de replicação são armazenados.</span><span class="sxs-lookup"><span data-stu-id="d8a65-115">This error can occur when a subscription is initialized manually, and there is a problem creating the directory in which replication scripts are stored.</span></span> <span data-ttu-id="d8a65-116">O erro pode ser causado por um problema de permissão: quando uma assinatura é inicializada sem o uso de um instantâneo, a conta na qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado no Publicador deve ter permissões de gravação na pasta do instantâneo no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d8a65-116">The error can be caused by a permissions issue: when a subscription is initialized without using a snapshot, the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher must have write permissions on the snapshot folder at the Distributor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8a65-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d8a65-117">User Action</span></span>  
 <span data-ttu-id="d8a65-118">Certifique-se de que o caminho correto foi especificado para a pasta do instantâneo e que a conta em que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado no Publicador tem permissões adequadas.</span><span class="sxs-lookup"><span data-stu-id="d8a65-118">Ensure that the correct path has been specified for the snapshot folder and that the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher has sufficient permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a65-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8a65-119">See Also</span></span>  
 <span data-ttu-id="d8a65-120">[Especificar o local do instantâneo padrão](snapshot-options.md#snapshot-folder-locations) </span><span class="sxs-lookup"><span data-stu-id="d8a65-120">[Specify the Default Snapshot Location](snapshot-options.md#snapshot-folder-locations) </span></span>  
 <span data-ttu-id="d8a65-121">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d8a65-121">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="d8a65-122">Inicializar uma assinatura transacional sem um instantâneo</span><span class="sxs-lookup"><span data-stu-id="d8a65-122">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
