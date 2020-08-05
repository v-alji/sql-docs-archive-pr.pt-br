---
title: Página agendas (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ef19d96e-9f00-4434-950e-152dda9c1ced
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e31bc25473aad23ecd2654f74ee3e837e65b65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572383"
---
# <a name="schedules-page-report-manager"></a><span data-ttu-id="dea30-102">Página Agendas (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="dea30-102">Schedules Page (Report Manager)</span></span>
  <span data-ttu-id="dea30-103">Use a página Agendas para criar, modificar, excluir, pausar ou reiniciar agendas compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="dea30-103">Use the Schedules page to create, modify, delete, pause, or resume shared schedules.</span></span> <span data-ttu-id="dea30-104">Uma agenda compartilhada é uma agenda nomeada que você pode criar e gerenciar separadamente de relatórios, assinaturas e outros processos que consomem informações de agenda.</span><span class="sxs-lookup"><span data-stu-id="dea30-104">A shared schedule is a named schedule that you can create and manage separately from reports, subscriptions, and other processes that consume schedule information.</span></span> <span data-ttu-id="dea30-105">Os usuários podem selecionar agendas compartilhadas que você fornece.</span><span class="sxs-lookup"><span data-stu-id="dea30-105">Users can select shared schedules that you provide.</span></span>  
  
 <span data-ttu-id="dea30-106">Para excluir, pausar ou retomar uma agenda compartilhada, marque a caixa de seleção ao lado da agenda compartilhada que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="dea30-106">To delete, pause, or resume a shared schedule, select the check box next to the shared schedule that you want to modify.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dea30-107">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dea30-107">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dea30-108">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="dea30-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="dea30-109">Navegação</span><span class="sxs-lookup"><span data-stu-id="dea30-109">Navigation</span></span>  
 <span data-ttu-id="dea30-110">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="dea30-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-schedules-page"></a><span data-ttu-id="dea30-111">Para abrir a página Agendas</span><span class="sxs-lookup"><span data-stu-id="dea30-111">To open the Schedules page</span></span>  
  
1.  <span data-ttu-id="dea30-112">Abra o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="dea30-112">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="dea30-113">Na parte superior da página, no canto direito, clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="dea30-113">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="dea30-114">Esse procedimento abre a página Propriedades Gerais do site.</span><span class="sxs-lookup"><span data-stu-id="dea30-114">This opens the General Properties page of the site.</span></span>  
  
3.  <span data-ttu-id="dea30-115">Selecione a guia **Agendas** .</span><span class="sxs-lookup"><span data-stu-id="dea30-115">Select the **Schedules** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dea30-116">Opções</span><span class="sxs-lookup"><span data-stu-id="dea30-116">Options</span></span>  
 <span data-ttu-id="dea30-117">**Nova agenda**</span><span class="sxs-lookup"><span data-stu-id="dea30-117">**New Schedule**</span></span>  
 <span data-ttu-id="dea30-118">Clique para abrir a página Agenda que é usada para especificar informações de frequência.</span><span class="sxs-lookup"><span data-stu-id="dea30-118">Click to open the Scheduling page, which is used to specify frequency information.</span></span>  
  
 <span data-ttu-id="dea30-119">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="dea30-119">**Delete**</span></span>  
 <span data-ttu-id="dea30-120">Clique para remover uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dea30-120">Click to remove a shared schedule.</span></span>  
  
 <span data-ttu-id="dea30-121">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="dea30-121">**Pause**</span></span>  
 <span data-ttu-id="dea30-122">Clique para parar temporariamente a execução de uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dea30-122">Click to stop a shared schedule from running temporarily.</span></span> <span data-ttu-id="dea30-123">Quando uma agenda é pausada, isso impede que a assinatura e outros processos agendados sejam executados.</span><span class="sxs-lookup"><span data-stu-id="dea30-123">Pausing a schedule prevents subscriptions and other scheduled processes from running.</span></span>  
  
 <span data-ttu-id="dea30-124">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="dea30-124">**Resume**</span></span>  
 <span data-ttu-id="dea30-125">Clique para reiniciar uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dea30-125">Click to reinstate a shared schedule.</span></span> <span data-ttu-id="dea30-126">Processos interrompidos agendados para executar enquanto a agenda estava em pausa não são concluídos.</span><span class="sxs-lookup"><span data-stu-id="dea30-126">Lapsed processes that were scheduled to run while the schedule was paused are not made up.</span></span>  
  
 <span data-ttu-id="dea30-127">**Agenda**</span><span class="sxs-lookup"><span data-stu-id="dea30-127">**Schedule**</span></span>  
 <span data-ttu-id="dea30-128">Exibe as agendas compartilhadas atualmente definidas.</span><span class="sxs-lookup"><span data-stu-id="dea30-128">Shows the shared schedules that are currently defined.</span></span> <span data-ttu-id="dea30-129">Clique em uma agenda compartilhada para exibir ou editar informações de frequência.</span><span class="sxs-lookup"><span data-stu-id="dea30-129">Click a shared schedule to view or edit frequency information.</span></span>  
  
 <span data-ttu-id="dea30-130">**Criador**</span><span class="sxs-lookup"><span data-stu-id="dea30-130">**Creator**</span></span>  
 <span data-ttu-id="dea30-131">Exibe o nome do usuário que criou a agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dea30-131">Shows the name of the user who created the shared schedule.</span></span>  
  
 <span data-ttu-id="dea30-132">**Última Execução, Próxima Execução**</span><span class="sxs-lookup"><span data-stu-id="dea30-132">**Last Run, Next Run**</span></span>  
 <span data-ttu-id="dea30-133">Exibe quando a agenda compartilhada foi executada por último e quando será a próxima execução.</span><span class="sxs-lookup"><span data-stu-id="dea30-133">Shows when the shared schedule was last run and when it will run next.</span></span>  
  
 <span data-ttu-id="dea30-134">**Status**</span><span class="sxs-lookup"><span data-stu-id="dea30-134">**Status**</span></span>  
 <span data-ttu-id="dea30-135">Exibe se uma agenda compartilhada está em pausa ou ativa.</span><span class="sxs-lookup"><span data-stu-id="dea30-135">Shows whether a shared schedule is paused or active.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea30-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dea30-136">See Also</span></span>  
 <span data-ttu-id="dea30-137">[Criar, modificar e excluir agendas](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="dea30-137">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="dea30-138">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="dea30-138">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
