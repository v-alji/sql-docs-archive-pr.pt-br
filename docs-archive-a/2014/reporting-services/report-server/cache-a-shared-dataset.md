---
title: Armazenar em cache um conjunto de dados compartilhado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d4757d82425368efcb6a0a555c6cfe1deacf48c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575612"
---
# <a name="cache-a-shared-dataset"></a><span data-ttu-id="071d1-102">Armazenar em cache um conjunto de dados compartilhado</span><span class="sxs-lookup"><span data-stu-id="071d1-102">Cache a Shared Dataset</span></span>
  <span data-ttu-id="071d1-103">Um modo de melhorar o desempenho é configurar propriedades de cache para um conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="071d1-103">One way to improve performance is to configure caching properties for a shared dataset.</span></span> <span data-ttu-id="071d1-104">Quando um conjunto de dados compartilhado é armazenado em cache, uma cópia dos resultados da consulta é salva por um período de tempo específico.</span><span class="sxs-lookup"><span data-stu-id="071d1-104">When a shared dataset is cached, a copy of the query results is saved for a specified period of time.</span></span> <span data-ttu-id="071d1-105">O primeiro usuário que solicita um relatório que usa o conjunto de dados compartilhado deve aguardar os resultados da consulta e a conclusão de todo o processamento antes de exibir o relatório.</span><span class="sxs-lookup"><span data-stu-id="071d1-105">The first user who requests a report that uses the shared dataset must wait for the query results and all processing to complete before viewing the report.</span></span> <span data-ttu-id="071d1-106">Os usuários subsequentes que solicitarem o relatório dentro do período de cache terão um desempenho melhor porque a consulta e o processamento já ocorreram.</span><span class="sxs-lookup"><span data-stu-id="071d1-106">Subsequent users who request the report within the caching period will experience improved performance because the query and processing has already occurred.</span></span> <span data-ttu-id="071d1-107">Também é possível especificar um plano de atualização de cache para executar a consulta e armazenar os resultados em cache até a expiração de cache especificada.</span><span class="sxs-lookup"><span data-stu-id="071d1-107">You can also specify a cache refresh plan to run the query and cache the results until the specified cache expiration.</span></span>  
  
 <span data-ttu-id="071d1-108">Os usuários que estiverem executando relatórios com base em um conjunto de dados compartilhado ou em planos de atualização de cache criam o cache de consultas e, em ambos os casos, o cache permanece disponível com base nas opções de expiração de cache.</span><span class="sxs-lookup"><span data-stu-id="071d1-108">Users running reports based on a shared dataset or cache refresh plans create the query cache and in both cases, the cache is available based on the cache expiration options.</span></span>  
  
 <span data-ttu-id="071d1-109">Há restrições quanto aos tipos de conjuntos de dados compartilhados que podem ser armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="071d1-109">There are restrictions on the types of shared datasets that you can cache.</span></span> <span data-ttu-id="071d1-110">Por exemplo, os resultados da consulta não podem ser armazenados em cache se os dados variam de acordo com a identidade do usuário ou se os dados forem recuperados com o token de segurança do usuário que solicita o relatório.</span><span class="sxs-lookup"><span data-stu-id="071d1-110">For example, the query results cannot be cached if the data varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="071d1-111">Para obter mais informações, consulte [Armazenar conjuntos de dados compartilhados em cache &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) e [Armazenando relatórios em cache &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="071d1-111">For more information, see [Cache Shared Datasets &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) and [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="071d1-112">Para agendar a validade de um relatório armazenado em cache</span><span class="sxs-lookup"><span data-stu-id="071d1-112">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="071d1-113">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="071d1-113">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="071d1-114">No Gerenciador de Relatórios, navegue até o conjunto de dados compartilhado para o qual deseja definir propriedades de armazenamento em cache, passe o mouse sobre o item e clique na seta suspensa.</span><span class="sxs-lookup"><span data-stu-id="071d1-114">In Report Manager, navigate to the shared dataset for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="071d1-115">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="071d1-115">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="071d1-116">No quadro esquerdo, clique em **Cache**.</span><span class="sxs-lookup"><span data-stu-id="071d1-116">In the left frame, click **Caching**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="071d1-117">Caso veja o erro **As credenciais usadas para executar o conjunto de dados compartilhado não estão armazenadas**, a opção de conjunto de dados compartilhado em cache será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="071d1-117">If you see the error **Credentials used to run the shared dataset are not stored**, the cache shared dataset option will be disabled.</span></span> <span data-ttu-id="071d1-118">É preciso modificar a fonte de dados para armazenar as credenciais ou modificar o conjunto de dados compartilhado para usar uma fonte de dados diferente que não armazena credenciais.</span><span class="sxs-lookup"><span data-stu-id="071d1-118">You need modify the data source to store credentials or modify the shared dataset to use a different data source that does store credentials.</span></span>  
  
5.  <span data-ttu-id="071d1-119">Selecione **Conjunto de dados de compartilhamento em cache**.</span><span class="sxs-lookup"><span data-stu-id="071d1-119">Select **Cache share dataset**.</span></span>  
  
6.  <span data-ttu-id="071d1-120">Selecione a opção para expirar o cache depois de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="071d1-120">Select the option to expire the cache after 30 minutes.</span></span> <span data-ttu-id="071d1-121">Você também pode optar pela expiração do cache em uma agenda especificada.</span><span class="sxs-lookup"><span data-stu-id="071d1-121">You can also choose for the cache to expire on a specified schedule.</span></span>  
  
7.  <span data-ttu-id="071d1-122">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="071d1-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071d1-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="071d1-123">See Also</span></span>  
 [<span data-ttu-id="071d1-124">Gerenciar conjuntos de dados compartilhados</span><span class="sxs-lookup"><span data-stu-id="071d1-124">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
