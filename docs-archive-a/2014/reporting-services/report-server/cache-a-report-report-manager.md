---
title: Armazenar um relatório em cache (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- cache [Reporting Services]
- cached reports [Reporting Services]
- schedules [Reporting Services], report expiration
- expiration [Reporting Services]
ms.assetid: 723d1cb0-c2e7-4763-8690-a6a7a8bbbb90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e359e6c7a40b267979137ef2b3a285667a6fdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575613"
---
# <a name="cache-a-report-report-manager"></a><span data-ttu-id="c419a-102">Armazenar um relatório em cache (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="c419a-102">Cache a Report (Report Manager)</span></span>
  <span data-ttu-id="c419a-103">Um modo de melhorar o desempenho é configurar propriedades de cache para um relatório.</span><span class="sxs-lookup"><span data-stu-id="c419a-103">One way to improve performance is to configure caching properties for a report.</span></span> <span data-ttu-id="c419a-104">Quando um relatório é armazenado em cache, uma cópia do relatório renderizado é salva por um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="c419a-104">When a report is cached, a copy of the rendered report is saved for a short period of time.</span></span> <span data-ttu-id="c419a-105">O primeiro usuário que solicita o relatório deve aguardar a conclusão do processamento antes de exibir o relatório.</span><span class="sxs-lookup"><span data-stu-id="c419a-105">The first user who requests the report must wait for all processing to complete before viewing the report.</span></span> <span data-ttu-id="c419a-106">Usuários subsequentes que solicitam o relatório dentro do período de cache podem exibi-lo imediatamente porque o processamento já ocorreu.</span><span class="sxs-lookup"><span data-stu-id="c419a-106">Subsequent users who request the report within the caching period can view it right away because processing has already occurred.</span></span>  
  
 <span data-ttu-id="c419a-107">Há restrições quanto aos tipos de relatórios que podem ser armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="c419a-107">There are restrictions on the types of reports that you can cache.</span></span> <span data-ttu-id="c419a-108">Por exemplo, um relatório não pode ser armazenado em cache se suas saídas forem diferentes dependendo da identidade do usuário ou se os dados forem recuperados com o token de segurança do usuário que solicita o relatório.</span><span class="sxs-lookup"><span data-stu-id="c419a-108">For example, a report cannot be cached if report output varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="c419a-109">Para obter mais informações, consulte [Armazenando relatórios em cache &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c419a-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="c419a-110">Para agendar a validade de um relatório armazenado em cache</span><span class="sxs-lookup"><span data-stu-id="c419a-110">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="c419a-111">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c419a-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c419a-112">No Gerenciador de Relatórios, navegue até a página **Conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="c419a-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="c419a-113">Navegue até o relatório cujas propriedades de cache você deseja definir, passe o mouse sobre o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="c419a-113">Navigate to the report for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c419a-114">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c419a-114">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="c419a-115">No quadro esquerdo, clique em **Opções de Processamento**.</span><span class="sxs-lookup"><span data-stu-id="c419a-115">In the left frame, click the **Processing Options**.</span></span>  
  
5.  <span data-ttu-id="c419a-116">Na página, selecione **Sempre executar este relatório com a data mais recente**.</span><span class="sxs-lookup"><span data-stu-id="c419a-116">On the page, select **Always run this report with the most recent data**.</span></span>  
  
6.  <span data-ttu-id="c419a-117">Selecione um das duas opções de cache a seguir e configure a validade do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="c419a-117">Select one of the following two cache options and configure expiration as follows:</span></span>  
  
    -   <span data-ttu-id="c419a-118">Para configurar uma cópia armazenada em cache para expirar depois de um período de tempo específico, clique em **Armazenar uma cópia temporária do relatório em cache. Expirar cópia de relatório após alguns minutos**.</span><span class="sxs-lookup"><span data-stu-id="c419a-118">To configure a cached copy to expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes**.</span></span> <span data-ttu-id="c419a-119">Digite o número de minutos para a validade do relatório.</span><span class="sxs-lookup"><span data-stu-id="c419a-119">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="c419a-120">Para configurar uma cópia armazenada em cache para expirar em uma agenda, clique em **Armazenar uma cópia temporária do relatório em cache. Expirar cópia de relatório no seguinte agendamento.**</span><span class="sxs-lookup"><span data-stu-id="c419a-120">To configure a cached copy to expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="c419a-121">Clique em **Configurar**ou selecione uma agenda compartilhada para controlar a validade do relatório</span><span class="sxs-lookup"><span data-stu-id="c419a-121">Click **Configure**, or select a shared schedule to control report expiration</span></span>  
  
7.  <span data-ttu-id="c419a-122">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c419a-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c419a-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c419a-123">See Also</span></span>  
 <span data-ttu-id="c419a-124">[Definir as propriedades do processamento de relatórios](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c419a-124">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="c419a-125">Armazenando relatórios em cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c419a-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
