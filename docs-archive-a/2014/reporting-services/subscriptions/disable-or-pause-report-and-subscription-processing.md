---
title: Pausar o processamento de relatório e assinatura | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683387"
---
# <a name="pause-report-and-subscription-processing"></a><span data-ttu-id="cecf6-102">Pausar o processamento de relatório e assinatura</span><span class="sxs-lookup"><span data-stu-id="cecf6-102">Pause Report and Subscription Processing</span></span>
  <span data-ttu-id="cecf6-103">Você não pode pausar um relatório ou assinatura diretamente.</span><span class="sxs-lookup"><span data-stu-id="cecf6-103">You cannot pause a report or subscription directly.</span></span> <span data-ttu-id="cecf6-104">No entanto, é possível interromper o processamento de relatório e assinatura antes do início do processamento ou quando uma conexão de fonte de dados for feita.</span><span class="sxs-lookup"><span data-stu-id="cecf6-104">However, you can interrupt report and subscription processing prior to the process starting or when a data source connection is made.</span></span> <span data-ttu-id="cecf6-105">Você também pode impedir o processamento de um relatório ou assinatura deixando-o inacessível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="cecf6-105">You can also prevent a report or subscription from processing by making it inaccessible to users.</span></span>  
  
 <span data-ttu-id="cecf6-106">As estratégias a seguir podem ser usadas para impedir o processamento temporariamente.</span><span class="sxs-lookup"><span data-stu-id="cecf6-106">The following strategies can be used to temporarily prevent a process from occurring.</span></span>  
  
## <a name="modify-role-assignments-to-prevent-access"></a><span data-ttu-id="cecf6-107">Modificar atribuições de função para impedir o acesso</span><span class="sxs-lookup"><span data-stu-id="cecf6-107">Modify Role Assignments to Prevent Access</span></span>  
 <span data-ttu-id="cecf6-108">A melhor maneira de deixar um relatório indisponível é remover temporariamente a atribuição de função que fornece acesso ao relatório.</span><span class="sxs-lookup"><span data-stu-id="cecf6-108">The best way to make a report unavailable is to temporarily remove the role assignment that provides access to the report.</span></span> <span data-ttu-id="cecf6-109">Esta abordagem pode ser usada em todos os relatórios, independentemente de como a conexão de fonte de dados seja feita.</span><span class="sxs-lookup"><span data-stu-id="cecf6-109">This approach can be used on all reports regardless of how the data source connection is made.</span></span> <span data-ttu-id="cecf6-110">Esta abordagem visa apenas o relatório, sem afetar a operação de outros relatórios ou itens.</span><span class="sxs-lookup"><span data-stu-id="cecf6-110">This approach targets only the report, without affecting the operation of other reports or items.</span></span>  
  
 <span data-ttu-id="cecf6-111">Para remover a atribuição de função, abra a página Propriedades de Segurança do relatório no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="cecf6-111">To remove the role assignment, open the Security Properties page of the report in Report Manager.</span></span> <span data-ttu-id="cecf6-112">Se o relatório herda a segurança de um pai, clique em **Editar Segurança de Item** para criar uma política de segurança restritiva que omite as atribuições de função que fornecem amplo acesso (por exemplo, você pode remover uma atribuição de função que fornece acesso a Todos e manter a atribuição de função que fornece acesso a um pequeno grupo de usuários, como Administradores).</span><span class="sxs-lookup"><span data-stu-id="cecf6-112">If the report inherits security from a parent, you can click **Edit Item Security** to create a restrictive security policy that omits role assignments that provide widespread access (for example, you can remove a role assignment that provides access to Everyone, and keep the role assignment that provides access to a small group of users, such as Administrators).</span></span>  
  
## <a name="disable-a-shared-data-source"></a><span data-ttu-id="cecf6-113">Desabilitar uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="cecf6-113">Disable a Shared Data Source</span></span>  
 <span data-ttu-id="cecf6-114">Uma vantagem de usar fontes de dados compartilhadas é poder desabilitá-las para impedir a execução de um relatório ou assinatura controlada por dados.</span><span class="sxs-lookup"><span data-stu-id="cecf6-114">One advantage to using shared data sources is that you can disable it to prevent a report or data-driven subscription from running.</span></span> <span data-ttu-id="cecf6-115">Desabilitar uma fonte de dados compartilhada desconecta o relatório de sua fonte externa.</span><span class="sxs-lookup"><span data-stu-id="cecf6-115">Disabling a shared data source disconnects the report from its external source.</span></span> <span data-ttu-id="cecf6-116">Enquanto está desabilitada, a fonte de dados fica indisponível para todos os relatórios e assinaturas que a utilizam.</span><span class="sxs-lookup"><span data-stu-id="cecf6-116">While it is disabled, the data source is unavailable to all reports and subscriptions that use it.</span></span> <span data-ttu-id="cecf6-117">Para desabilitar uma fonte de dados compartilhada, abra a fonte de dados no Gerenciador de Relatórios e desmarque a caixa de seleção **Habilitar esta fonte de dados** .</span><span class="sxs-lookup"><span data-stu-id="cecf6-117">To disable a shared data source, open the data source in Report Manager and clear the **Enable this data source** check box.</span></span>  
  
 <span data-ttu-id="cecf6-118">Observe que o relatório ainda é carregado mesmo que a fonte de dados não esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="cecf6-118">Note that the report still loads even if the data source is unavailable.</span></span> <span data-ttu-id="cecf6-119">O relatório não contém dados, mas os usuários com as permissões adequadas podem acessar as páginas de propriedade, as configurações de segurança, o histórico de relatórios e as informações de assinatura associadas ao relatório.</span><span class="sxs-lookup"><span data-stu-id="cecf6-119">The report does not contain data, but users with appropriate permissions can access the property pages, security settings, report history, and subscription information associated with the report.</span></span>  
  
## <a name="pause-a-shared-schedule"></a><span data-ttu-id="cecf6-120">Pausar uma agenda compartilhada</span><span class="sxs-lookup"><span data-stu-id="cecf6-120">Pause a Shared Schedule</span></span>  
 <span data-ttu-id="cecf6-121">Se um relatório ou assinatura for executado a partir de uma agenda compartilhada, você pode pausar a agenda para impedir o processamento.</span><span class="sxs-lookup"><span data-stu-id="cecf6-121">If a report or subscription runs from a shared schedule, you can pause the schedule to prevent processing.</span></span> <span data-ttu-id="cecf6-122">Todos os processamentos de relatório e assinatura que são controlados pelo agendamento serão adiados até o agendamento ser retomado.</span><span class="sxs-lookup"><span data-stu-id="cecf6-122">All report and subscription processing that is driven by the schedule is deferred until the schedule is resumed.</span></span> <span data-ttu-id="cecf6-123">Para obter mais informações, consulte [pausar e retomar agendas compartilhadas](schedules.md).</span><span class="sxs-lookup"><span data-stu-id="cecf6-123">For more information, see [Pause and Resume Shared Schedules](schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecf6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cecf6-124">See Also</span></span>  
 <span data-ttu-id="cecf6-125">[Servidor de relatório do Reporting Services &#40;Modo Nativo&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="cecf6-125">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="cecf6-126">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="cecf6-126">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="cecf6-127">Página Propriedades de Segurança, Itens &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="cecf6-127">Security Properties Page, Items &#40;Report Manager&#41;</span></span>](../security-properties-page-items-report-manager.md)  
  
  
