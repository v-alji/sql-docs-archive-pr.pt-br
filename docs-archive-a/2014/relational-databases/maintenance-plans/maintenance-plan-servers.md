---
title: Plano de manutenção (servidores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.server.f1
- sql12.swb.maint.servers.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c971edc9b641846068313f47ca410715ec552014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572529"
---
# <a name="maintenance-plan-servers"></a><span data-ttu-id="134de-102">Plano de manutenção (Servidores)</span><span class="sxs-lookup"><span data-stu-id="134de-102">Maintenance Plan (Servers)</span></span>
  <span data-ttu-id="134de-103">Use a caixa de diálogo **Servidores** para selecionar os servidores em que você quer executar o plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="134de-103">Use the **Servers** dialog box to select the servers where you want to run the maintenance plan.</span></span>  
  
 <span data-ttu-id="134de-104">É necessário configurar um ambiente multisservidor contendo um servidor mestre e um ou mais servidores de destino para criar um plano de manutenção multisservidor.</span><span class="sxs-lookup"><span data-stu-id="134de-104">A multiserver environment containing one master server and one or more target servers must be configured to create a multiserver maintenance plan.</span></span> <span data-ttu-id="134de-105">Para planos de manutenção multisservidor, o servidor local deve ser configurado como um servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="134de-105">For multiserver maintenance plans, the local server should be configured as a master server.</span></span> <span data-ttu-id="134de-106">Em ambientes multisservidor, essa caixa de diálogo exibe o servidor mestre **(local)** e todos os servidores de destino correspondentes.</span><span class="sxs-lookup"><span data-stu-id="134de-106">In multiserver environments, this dialog box displays the **(local)** master server and all corresponding target servers.</span></span> <span data-ttu-id="134de-107">Um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é criado para o servidor local.</span><span class="sxs-lookup"><span data-stu-id="134de-107">One [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created for the local server.</span></span> <span data-ttu-id="134de-108">Ele está habilitado ou desabilitado dependendo se o servidor **(local)** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="134de-108">It is enabled or disabled depending on whether you select the **(local)** server.</span></span> <span data-ttu-id="134de-109">Se os servidores de destino estiverem selecionados, um trabalho multisservidor será criado e baixado para cada um dos servidores de destino selecionados.</span><span class="sxs-lookup"><span data-stu-id="134de-109">If target servers are selected, a multiserver job is created and downloaded to each of the selected target servers.</span></span> <span data-ttu-id="134de-110">Se nenhum servidor de destino estiver selecionado, o trabalho multisservidor será excluído.</span><span class="sxs-lookup"><span data-stu-id="134de-110">If no target servers are selected, the multiserver job is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134de-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="134de-111">See Also</span></span>  
 <span data-ttu-id="134de-112">[Planos de manutenção](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="134de-112">[Maintenance Plans](maintenance-plans.md) </span></span>  
 <span data-ttu-id="134de-113">[Criar um ambiente multisservidor](../../ssms/agent/create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="134de-113">[Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="134de-114">[Criar um servidor mestre](../../ssms/agent/make-a-master-server.md) </span><span class="sxs-lookup"><span data-stu-id="134de-114">[Make a Master Server](../../ssms/agent/make-a-master-server.md) </span></span>  
 [<span data-ttu-id="134de-115">Criar um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="134de-115">Make a Target Server</span></span>](../../ssms/agent/make-a-target-server.md)  
  
  
