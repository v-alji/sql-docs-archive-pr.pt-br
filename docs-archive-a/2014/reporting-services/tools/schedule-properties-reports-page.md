---
title: Propriedades do Agendamento (página Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572366"
---
# <a name="schedule-properties-reports-page"></a><span data-ttu-id="24c61-102">Propriedades da Agenda (página Relatórios)</span><span class="sxs-lookup"><span data-stu-id="24c61-102">Schedule Properties (Reports Page)</span></span>
  <span data-ttu-id="24c61-103">Use essa página para exibir uma lista de todos os relatórios que usam agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="24c61-103">Use this page to view a list of all reports that use this shared schedule.</span></span> <span data-ttu-id="24c61-104">As agendas podem ser usadas para atualizar instantâneos de relatório, gerar histórico de relatório, engatilhar uma assinatura ou terminar uma cópia armazenada em cache do relatório.</span><span class="sxs-lookup"><span data-stu-id="24c61-104">Schedules can be used to refresh report snapshots, generate report history, trigger a subscription, or expire a cached copy of the report.</span></span> <span data-ttu-id="24c61-105">Para descobrir como a agenda é usada, exiba a propriedade e as informações de assinatura do relatório.</span><span class="sxs-lookup"><span data-stu-id="24c61-105">To find out how the schedule is used, view the property and subscription information of the report.</span></span>  
  
 <span data-ttu-id="24c61-106">Embora essa página exiba cada relatório que usa a agenda compartilhada, ele não indica quantas vezes uma agenda compartilhada é usada naquele único relatório.</span><span class="sxs-lookup"><span data-stu-id="24c61-106">Although this page shows each report that uses the shared schedule, it does not indicate how many times the shared schedule is used within that single report.</span></span> <span data-ttu-id="24c61-107">Por exemplo, suponhamos que 20 assinantes diferentes do relatório Vendas da Empresa usem a mesma agenda compartilhada para engatilhar processamento de assinatura.</span><span class="sxs-lookup"><span data-stu-id="24c61-107">For example, suppose 20 different subscribers to the Company Sales report all use the same shared schedule to trigger subscription processing.</span></span> <span data-ttu-id="24c61-108">Nesse caso, o relatório Vendas da Empresa só aparecerá uma vez nessa lista, embora o relatório tenha 20 referências à agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="24c61-108">In this case, the Company Sales report will only appear once in this list, even though the report has 20 references to the shared schedule.</span></span>  
  
 <span data-ttu-id="24c61-109">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a um servidor de relatórios, abra a pasta **Agendas Compartilhadas** , clique com o botão direito do mouse em uma agenda compartilhada, selecione **Propriedades**e clique em **Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="24c61-109">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, select **Properties**, and then click **Reports**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24c61-110">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24c61-110">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="24c61-111">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [recursos com suporte nas edições do SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="24c61-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="24c61-112">Opções</span><span class="sxs-lookup"><span data-stu-id="24c61-112">Options</span></span>  
 <span data-ttu-id="24c61-113">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="24c61-113">**Folder**</span></span>  
 <span data-ttu-id="24c61-114">Especifica o caminho do relatório.</span><span class="sxs-lookup"><span data-stu-id="24c61-114">Specifies the path of the report.</span></span>  
  
 <span data-ttu-id="24c61-115">**Report**</span><span class="sxs-lookup"><span data-stu-id="24c61-115">**Report**</span></span>  
 <span data-ttu-id="24c61-116">Especifica o nome do relatório que usa a agenda.</span><span class="sxs-lookup"><span data-stu-id="24c61-116">Specifies the name of the report that uses the schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c61-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24c61-117">See Also</span></span>  
 <span data-ttu-id="24c61-118">[Criar, modificar e excluir agendas](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="24c61-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="24c61-119">[Agendas](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="24c61-119">[Schedules](../subscriptions/schedules.md) </span></span>  
 <span data-ttu-id="24c61-120">[Servidor de relatório na ajuda Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="24c61-120">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="24c61-121">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="24c61-121">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="24c61-122">Configurar propriedades gerais para um relatório &#40;Report Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="24c61-122">Configure General Properties for a Report &#40;Report Manager&#41;</span></span>](../configure-general-properties-for-a-report-report-manager.md)  
  
  
