---
title: Resolvedor Interativo de Conflitos de Replicação da Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.interactiveresolver.f1
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8cbd2231ab1ab357321f9887bced986e182e608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685568"
---
# <a name="microsoft-replication-interactive-conflict-resolver"></a><span data-ttu-id="31869-102">Resolvedor Interativo de Conflitos de Replicação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="31869-102">Microsoft Replication Interactive Conflict Resolver</span></span>
  <span data-ttu-id="31869-103">O Resolvedor Interativo de Conflitos de Replicação pode ser usado para assinaturas de mesclagem sincronizadas usando o Gerenciador de Sincronização do Windows.</span><span class="sxs-lookup"><span data-stu-id="31869-103">The Interactive Conflict Resolver can be used for merge subscriptions that are synchronized using Windows Synchronization Manager.</span></span> <span data-ttu-id="31869-104">Ele permite exibir, comparar, editar e selecionar o resultado dos conflitos de dados.</span><span class="sxs-lookup"><span data-stu-id="31869-104">It allows you to view, compare, edit, and select the outcome for data conflicts.</span></span> <span data-ttu-id="31869-105">A replicação também inclui o Visualizador de Conflitos, que permite exibir e modificar resultados de conflitos depois de terem sido confirmados.</span><span class="sxs-lookup"><span data-stu-id="31869-105">Replication also includes the Conflict Viewer, which allows you to view and modify conflict outcomes after they have been committed.</span></span> <span data-ttu-id="31869-106">O Resolvedor Interativo de Conflitos permite selecionar o resultado durante a sincronização.</span><span class="sxs-lookup"><span data-stu-id="31869-106">The Interactive Conflict Resolver allows you to select the outcome during synchronization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31869-107">Os conflitos que envolvem registros lógicos não são exibidos no Resolvedor Interativo.</span><span class="sxs-lookup"><span data-stu-id="31869-107">Conflicts that involve logical records are not displayed in the Interactive Resolver.</span></span> <span data-ttu-id="31869-108">Para exibir informações sobre esses conflitos, use procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="31869-108">To view information about these conflicts, use replication stored procedures.</span></span> <span data-ttu-id="31869-109">Para obter mais informações, consulte [Exibir informações sobre conflitos em publicações de mesclagem &#40;Programação Transact-SQL de replicação&#41;](view-conflict-information-for-merge-publications.md).</span><span class="sxs-lookup"><span data-stu-id="31869-109">For more information, see [View Conflict Information for Merge Publications &#40;Replication Transact-SQL Programming&#41;](view-conflict-information-for-merge-publications.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="31869-110">Opções</span><span class="sxs-lookup"><span data-stu-id="31869-110">Options</span></span>  
 <span data-ttu-id="31869-111">**Nome da coluna**</span><span class="sxs-lookup"><span data-stu-id="31869-111">**Column name**</span></span>  
 <span data-ttu-id="31869-112">O nome de todas as colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="31869-112">The name of all columns in the table.</span></span> <span data-ttu-id="31869-113">Uma ou mais colunas podem ter dados conflitantes.</span><span class="sxs-lookup"><span data-stu-id="31869-113">One or more columns might have conflicting data.</span></span> <span data-ttu-id="31869-114">Independentemente de quais colunas estejam em conflito, toda a linha vencedora substituirá toda a linha perdedora.</span><span class="sxs-lookup"><span data-stu-id="31869-114">Regardless of which columns conflict, the entire winning row will overwrite the entire losing row.</span></span>  
  
 <span data-ttu-id="31869-115">**Resolução Sugerida**</span><span class="sxs-lookup"><span data-stu-id="31869-115">**Suggested Resolution**</span></span>  
 <span data-ttu-id="31869-116">A resolução sugerida fornecida pelo resolvedor de conflitos para o artigo.</span><span class="sxs-lookup"><span data-stu-id="31869-116">The suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="31869-117">**Publicador**</span><span class="sxs-lookup"><span data-stu-id="31869-117">**Publisher**</span></span>  
 <span data-ttu-id="31869-118">O valor dos dados no Publicador.</span><span class="sxs-lookup"><span data-stu-id="31869-118">The data value at the Publisher.</span></span>  
  
 <span data-ttu-id="31869-119">**Assinante**</span><span class="sxs-lookup"><span data-stu-id="31869-119">**Subscriber**</span></span>  
 <span data-ttu-id="31869-120">O valor dos dados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="31869-120">The data value at the Subscriber.</span></span>  
  
 <span data-ttu-id="31869-121">**Aceitar Sugestão**, **Aceitar Publicador**e **Aceitar Assinante**</span><span class="sxs-lookup"><span data-stu-id="31869-121">**Accept Suggested**, **Accept Publisher**, and **Accept Subscriber**</span></span>  
 <span data-ttu-id="31869-122">Clique para aceitar a linha que será aplicada no Publicador ou no Assinante, dependendo de quem perderá o conflito.</span><span class="sxs-lookup"><span data-stu-id="31869-122">Click to accept the row that will be applied at either the Publisher or the Subscriber, depending on which one lost the conflict.</span></span> <span data-ttu-id="31869-123">Se o Publicador perder o conflito, todos os outros Assinantes receberão a linha vencedora da próxima vez em que sincronizarem com o Publicador.</span><span class="sxs-lookup"><span data-stu-id="31869-123">If the Publisher lost the conflict, all other Subscribers will receive the winning row the next time they synchronize with the Publisher.</span></span>  
  
 <span data-ttu-id="31869-124">**Resolver conflitos restantes automaticamente**</span><span class="sxs-lookup"><span data-stu-id="31869-124">**Resolve remaining conflicts automatically**</span></span>  
 <span data-ttu-id="31869-125">Resolva todos os conflitos restantes usando a resolução sugerida fornecida pelo resolvedor de conflitos para o artigo.</span><span class="sxs-lookup"><span data-stu-id="31869-125">Resolve all remaining conflicts using the suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="31869-126">**Registrar em log os detalhes do conflito para referência futura**</span><span class="sxs-lookup"><span data-stu-id="31869-126">**Log the details of the conflict for later reference**</span></span>  
 <span data-ttu-id="31869-127">Registra os detalhes do conflito em tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="31869-127">Logs the details of the conflict in system tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31869-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31869-128">See Also</span></span>  
 <span data-ttu-id="31869-129">[Resolução interativa de conflitos](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="31869-129">[Interactive Conflict Resolution](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span></span>  
 <span data-ttu-id="31869-130">[Exibir e resolver conflitos de dados em publicações de mesclagem &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span><span class="sxs-lookup"><span data-stu-id="31869-130">[View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span></span>  
 <span data-ttu-id="31869-131">[Sincronizar uma assinatura usando o Gerenciador de Sincronização do Windows &#40;Gerenciador de Sincronização do Windows&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span><span class="sxs-lookup"><span data-stu-id="31869-131">[Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span></span>  
 [<span data-ttu-id="31869-132">Advanced Merge Replication Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="31869-132">Advanced Merge Replication Conflict Detection and Resolution</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
