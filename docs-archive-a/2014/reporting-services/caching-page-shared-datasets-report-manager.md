---
title: Página cache, conjuntos de armazenamento compartilhados (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eac372e9-d2a1-48a8-bbe5-09d101df16ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62d899964911a6f2d35e59d49d925ff80013af42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573814"
---
# <a name="caching-page-shared-datasets-report-manager"></a><span data-ttu-id="2724e-102">Página Cache, Conjuntos de Dados Compartilhados (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="2724e-102">Caching Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="2724e-103">Use a página de propriedades Cache para definir as opções de cache para um conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="2724e-103">Use the Caching properties page to set the cache options for a shared dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2724e-104">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2724e-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2724e-105">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="2724e-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="2724e-106">Navegação</span><span class="sxs-lookup"><span data-stu-id="2724e-106">Navigation</span></span>  
 <span data-ttu-id="2724e-107">Use o procedimento a seguir para navegar para esse local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="2724e-107">Use the following procedure to navigate to this location in the user interface.</span></span>  
  
### <a name="to-open-the-caching-properties-page-for-a-shared-dataset"></a><span data-ttu-id="2724e-108">Para abrir a página de propriedades Cache de um conjunto de dados compartilhado</span><span class="sxs-lookup"><span data-stu-id="2724e-108">To open the Caching properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="2724e-109">Abra o Gerenciador de Relatórios e localize o relatório cujo conjunto de dados compartilhado você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="2724e-109">Open Report Manager, and locate the report for which you want to configure shared dataset properties.</span></span>  
  
2.  <span data-ttu-id="2724e-110">Aponte para o conjunto de dados compartilhado e clique na seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="2724e-110">Point to the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2724e-111">Na lista suspensa, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="2724e-111">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="2724e-112">A página de propriedades Geral do relatório é aberta.</span><span class="sxs-lookup"><span data-stu-id="2724e-112">The General properties page for the report opens.</span></span>  
  
4.  <span data-ttu-id="2724e-113">Clique na guia **Cache** .</span><span class="sxs-lookup"><span data-stu-id="2724e-113">Click the **Caching** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2724e-114">Opções</span><span class="sxs-lookup"><span data-stu-id="2724e-114">Options</span></span>  
 <span data-ttu-id="2724e-115">**Armazenar conjunto de dados compartilhado em cache**</span><span class="sxs-lookup"><span data-stu-id="2724e-115">**Cache shared dataset**</span></span>  
 <span data-ttu-id="2724e-116">Coloca uma cópia temporária dos dados em um cache quando um usuário abre pela primeira vez um relatório que usa esse conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="2724e-116">Places a temporary copy of the data in a cache when a user first opens a report that uses this shared dataset.</span></span> <span data-ttu-id="2724e-117">Os usuários subsequentes que executarem o relatório dentro do período de cache receberão a cópia dos dados armazenada em cache.</span><span class="sxs-lookup"><span data-stu-id="2724e-117">Subsequent users who run the report within the caching period receive the cached copy of the data.</span></span> <span data-ttu-id="2724e-118">O cache normalmente melhora o desempenho porque os dados são retornados do cache, em vez de haver uma nova execução da consulta de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="2724e-118">Caching usually improves performance because the data is returned from the cache instead of running the dataset query again.</span></span>  
  
 <span data-ttu-id="2724e-119">**Expire o cache após este número de minutos**</span><span class="sxs-lookup"><span data-stu-id="2724e-119">**Expire the cache after a number of minutes**</span></span>  
 <span data-ttu-id="2724e-120">Especifique o número de minutos para salvar a cópia dos dados armazenada em cache.</span><span class="sxs-lookup"><span data-stu-id="2724e-120">Specify the number of minutes to save the cached copy of the data.</span></span> <span data-ttu-id="2724e-121">Assim que uma cópia temporária expirar, os dados não serão mais retornados do cache.</span><span class="sxs-lookup"><span data-stu-id="2724e-121">As soon as a temporary copy expires, the data is no longer returned from the cache.</span></span> <span data-ttu-id="2724e-122">Na próxima vez que um usuário abrir um relatório que use esse conjunto de dados compartilhado, a consulta de conjunto de dados será executada e o servidor de relatório colocará novamente uma cópia dos dados atualizados no cache.</span><span class="sxs-lookup"><span data-stu-id="2724e-122">The next time a user opens a report that uses this shared dataset, the dataset query runs and the report server places a copy of the refreshed data back in the cache.</span></span>  
  
 <span data-ttu-id="2724e-123">**Expire o cache na seguinte agenda**</span><span class="sxs-lookup"><span data-stu-id="2724e-123">**Expire the cache on the following schedule**</span></span>  
 <span data-ttu-id="2724e-124">Agende a hora em que os dados armazenados em cache não serão mais válidos e serão removidos do cache.</span><span class="sxs-lookup"><span data-stu-id="2724e-124">Schedule the time when the cached data is no longer valid and is removed from the cache.</span></span> <span data-ttu-id="2724e-125">A agenda pode ser uma agenda compartilhada ou uma que seja específica somente para o conjunto de dados compartilhado atual.</span><span class="sxs-lookup"><span data-stu-id="2724e-125">The schedule can be a shared schedule or one that is specific for only the current shared dataset.</span></span>  
  
 <span data-ttu-id="2724e-126">**Agenda específica de conjunto de dados**</span><span class="sxs-lookup"><span data-stu-id="2724e-126">**Dataset-specific schedule**</span></span>  
 <span data-ttu-id="2724e-127">Especifique uma agenda que seja usada somente por este conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="2724e-127">Specify a schedule that is used only by this dataset.</span></span>  
  
 <span data-ttu-id="2724e-128">**Agenda compartilhada**</span><span class="sxs-lookup"><span data-stu-id="2724e-128">**Shared schedule**</span></span>  
 <span data-ttu-id="2724e-129">Especifique uma agenda que seja compartilhada entre relatórios, assinaturas e outros conjuntos de dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="2724e-129">Specify a schedule that is shared among reports, subscriptions, and other shared datasets.</span></span>  
  
 <span data-ttu-id="2724e-130">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="2724e-130">**Apply**</span></span>  
 <span data-ttu-id="2724e-131">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="2724e-131">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2724e-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2724e-132">See Also</span></span>  
 <span data-ttu-id="2724e-133">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2724e-133">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="2724e-134">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="2724e-134">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="2724e-135">[Conjuntos de &#40;de armazenamento compartilhados do cache&#41;SSRS](report-server/cache-shared-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2724e-135">[Cache Shared Datasets &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="2724e-136">Agendas</span><span class="sxs-lookup"><span data-stu-id="2724e-136">Schedules</span></span>](subscriptions/schedules.md)  
  
  
