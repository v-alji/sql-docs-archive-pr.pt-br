---
title: Usar minhas assinaturas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3378a65637ad04151cc517fd9047363af954c31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684452"
---
# <a name="use-my-subscriptions"></a><span data-ttu-id="e92cf-102">Usar Minhas Assinaturas</span><span class="sxs-lookup"><span data-stu-id="e92cf-102">Use My Subscriptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]<span data-ttu-id="e92cf-103">Report Manager inclui uma página **minhas assinaturas** que organiza todas as suas assinaturas em um único lugar.</span><span class="sxs-lookup"><span data-stu-id="e92cf-103">Report Manager includes a **My Subscriptions** page that organizes all of your subscriptions into one place.</span></span> <span data-ttu-id="e92cf-104">É possível usar Minhas Assinaturas para exibir, modificar e excluir assinaturas existentes.</span><span class="sxs-lookup"><span data-stu-id="e92cf-104">You can use My Subscriptions to view, modify, and delete existing subscriptions.</span></span> <span data-ttu-id="e92cf-105">Entretanto, você não pode usar Minhas Assinaturas para criar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="e92cf-105">However, you cannot use it to create subscriptions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="e92cf-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Modo nativo</span><span class="sxs-lookup"><span data-stu-id="e92cf-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 <span data-ttu-id="e92cf-107">Em Minhas Assinaturas, você pode classificar assinaturas por pasta, relatório, descrição, gatilho, data da última execução ou status.</span><span class="sxs-lookup"><span data-stu-id="e92cf-107">Within My Subscriptions, you can sort subscriptions by folder, report, description, trigger, last run, or status.</span></span> <span data-ttu-id="e92cf-108">Todos os valores são classificados por ordem alfabética, exceto Data da Última Execução, que está em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="e92cf-108">All values are sorted alphabetically except for Last Run, which is in chronological order.</span></span>  
  
 <span data-ttu-id="e92cf-109">Minhas Assinaturas exibe somente as assinaturas criadas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="e92cf-109">My Subscriptions shows only the subscriptions that you create.</span></span> <span data-ttu-id="e92cf-110">Minhas Assinaturas não relaciona assinaturas de propriedade de outros usuários, ainda que você tenha sido adicionado como assinante dessas assinaturas, tampouco exibe assinaturas controladas por dados.</span><span class="sxs-lookup"><span data-stu-id="e92cf-110">It does not list subscriptions that are owned by other users, even if you are added as a subscriber to those subscriptions, nor does it show data-driven subscriptions.</span></span>  
  
 <span data-ttu-id="e92cf-111">Não é possível procurar assinaturas por nome, nem procurar uma assinatura com base em informações de gatilho, informações de status, etc.</span><span class="sxs-lookup"><span data-stu-id="e92cf-111">You cannot search for subscriptions by name, nor can you search for subscriptions based on trigger information, status information, and so forth.</span></span> <span data-ttu-id="e92cf-112">Para obter mais informações, consulte [criar, modificar e excluir assinaturas padrão &#40;Reporting Services no modo nativo&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e92cf-112">For more information, see [Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span></span>  
  
## <a name="how-to-use-my-subscriptions"></a><span data-ttu-id="e92cf-113">Como usar Minhas Assinaturas</span><span class="sxs-lookup"><span data-stu-id="e92cf-113">How to Use My Subscriptions</span></span>  
 <span data-ttu-id="e92cf-114">Minhas Assinaturas está disponível através do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="e92cf-114">My Subscriptions is available through Report Manager.</span></span> <span data-ttu-id="e92cf-115">Para acessar Minhas Assinaturas, clique em **Minhas Assinaturas** na barra de ferramentas global do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="e92cf-115">To access My Subscriptions, click **My Subscriptions** on the Report Manager global toolbar.</span></span>  
  
## <a name="use-windows-powershell-to-list-mysubscriptions"></a><span data-ttu-id="e92cf-116">Usar o Windows PowerShell para listar MySubscriptions</span><span class="sxs-lookup"><span data-stu-id="e92cf-116">Use Windows PowerShell to list MySubscriptions</span></span>  
 <span data-ttu-id="e92cf-117">![Conteúdo relacionado ao PowerShell](../media/rs-powershellicon.jpg "Conteúdo relacionado ao PowerShell")</span><span class="sxs-lookup"><span data-stu-id="e92cf-117">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>  
  
 <span data-ttu-id="e92cf-118">O seguinte script do PowerShell retornará a lista de assinaturas e as propriedades de assinatura do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="e92cf-118">The following PowerShell script will return the list of subscriptions and subscription properties for the current user.</span></span> <span data-ttu-id="e92cf-119">Para obter mais informações, consulte [Método ReportingService2010.ListMySubscriptions](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span><span class="sxs-lookup"><span data-stu-id="e92cf-119">For more information, see [ReportingService2010.ListMySubscriptions Method](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span></span>  
  
```powershell
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions
```  
  
## <a name="see-also"></a><span data-ttu-id="e92cf-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e92cf-120">See Also</span></span>  
 <span data-ttu-id="e92cf-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="e92cf-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="e92cf-122">[Assinaturas e entrega &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e92cf-122">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="e92cf-123">Criar e gerenciar assinaturas de servidores de relatório no modo Nativo</span><span class="sxs-lookup"><span data-stu-id="e92cf-123">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../create-manage-subscriptions-native-mode-report-servers.md)  
