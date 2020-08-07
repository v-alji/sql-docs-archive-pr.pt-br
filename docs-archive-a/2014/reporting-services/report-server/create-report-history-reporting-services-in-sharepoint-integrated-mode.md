---
title: Criar histórico de relatórios (Reporting Services no modo integrado do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], SharePoint
ms.assetid: e57ec746-05ae-4ff6-8e39-6cde87310daa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 996202580bbacc24080460c2c43218db27294d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575584"
---
# <a name="create-report-history-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="9caff-102">Criar histórico de relatório (Reporting Services no modo integrado do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="9caff-102">Create Report History (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="9caff-103">O histórico de relatórios é uma coleção de instantâneos de relatórios que você cria.</span><span class="sxs-lookup"><span data-stu-id="9caff-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="9caff-104">Cada instantâneo é uma cópia do relatório como existia quando criado.</span><span class="sxs-lookup"><span data-stu-id="9caff-104">Each snapshot is a copy of the report as it existed when it was created.</span></span> <span data-ttu-id="9caff-105">Ele inclui o layout e os dados que eram atuais para o relatório quando o instantâneo foi criado.</span><span class="sxs-lookup"><span data-stu-id="9caff-105">It includes the layout and data that was current for the report when the snapshot was created.</span></span> <span data-ttu-id="9caff-106">Informações de renderização não são armazenadas com o instantâneo.</span><span class="sxs-lookup"><span data-stu-id="9caff-106">Rendering information is not stored with the snapshot.</span></span> <span data-ttu-id="9caff-107">Ao abrir um instantâneo no histórico de relatórios, ele é aberto em um novo HTML na Web Part do Visualizador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="9caff-107">When you open a snapshot in report history, it opens in HTML in the Report Viewer Web Part.</span></span> <span data-ttu-id="9caff-108">Depois de processado, você pode exportá-lo para outros formatos de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9caff-108">After it is rendered, you can export it to other application formats.</span></span>  
  
 <span data-ttu-id="9caff-109">Para criar um histórico de relatórios, é necessário que o relatório seja executado como autônomo (ou seja, o servidor de relatório deve ser capaz de executar o relatório sem interação do usuário).</span><span class="sxs-lookup"><span data-stu-id="9caff-109">To create report history, the report must be able to run unattended (that is, the report server must be able to run the report without user interaction).</span></span> <span data-ttu-id="9caff-110">É necessário ter a permissão Editar Itens na biblioteca que contém o relatório.</span><span class="sxs-lookup"><span data-stu-id="9caff-110">You must have Edit Items permission on the library that contains the report.</span></span> <span data-ttu-id="9caff-111">Para exibir ou excluir o histórico de relatórios, é necessário ter a permissão Exibir Versões ou a permissão Excluir Versões.</span><span class="sxs-lookup"><span data-stu-id="9caff-111">To view or delete report history, you must have View Versions or Delete Versions permissions.</span></span>  
  
### <a name="to-create-a-snapshot-or-report-history-on-demand"></a><span data-ttu-id="9caff-112">Para criar um instantâneo ou um histórico de relatórios sob demanda</span><span class="sxs-lookup"><span data-stu-id="9caff-112">To create a snapshot or report history on demand</span></span>  
  
1.  <span data-ttu-id="9caff-113">Aponte para o relatório.</span><span class="sxs-lookup"><span data-stu-id="9caff-113">Point to the report.</span></span>  
  
2.  <span data-ttu-id="9caff-114">Clique para exibir a seta para baixo e selecione **Exibir Histórico de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="9caff-114">Click to display the down arrow, and then select **View Report History**.</span></span>  
  
3.  <span data-ttu-id="9caff-115">Clique em **Novo Instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="9caff-115">Click **New Snapshot**.</span></span> <span data-ttu-id="9caff-116">Se o botão não estiver visível, pode ser porque você não tem permissão para criar instantâneos do histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9caff-116">If the button is not visible, it is because you do not have permission to create snapshots in report history.</span></span>  
  
4.  <span data-ttu-id="9caff-117">Para exibir o instantâneo recém-criado, selecione-o na lista.</span><span class="sxs-lookup"><span data-stu-id="9caff-117">To view the snapshot you just created, select it from the list.</span></span> <span data-ttu-id="9caff-118">Cada instantâneo é identificado por um carimbo de data/hora que mostra quando ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="9caff-118">Each snapshot is identified by a timestamp that shows when the snapshot was created.</span></span> <span data-ttu-id="9caff-119">Você não pode renomear o instantâneo, movê-lo para outro local ou modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="9caff-119">You cannot rename the snapshot, move it to another location, or modify it.</span></span>  
  
### <a name="to-schedule-report-history"></a><span data-ttu-id="9caff-120">Para agendar o histórico de relatórios</span><span class="sxs-lookup"><span data-stu-id="9caff-120">To schedule report history</span></span>  
  
1.  <span data-ttu-id="9caff-121">Aponte para o relatório.</span><span class="sxs-lookup"><span data-stu-id="9caff-121">Point to the report.</span></span>  
  
2.  <span data-ttu-id="9caff-122">Clique na seta para baixo e selecione **Gerenciar Opções de Processamento**.</span><span class="sxs-lookup"><span data-stu-id="9caff-122">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="9caff-123">Em **Opções de Instantâneo de Histórico**, clique em **Criar instantâneos de histórico de relatórios em um agendamento**.</span><span class="sxs-lookup"><span data-stu-id="9caff-123">In **History Snapshot Options**, click **Create report history snapshots on a schedule**.</span></span>  
  
4.  <span data-ttu-id="9caff-124">Se você tiver uma agenda compartilhada que contenha as informações de agendamento que deseja usar, clique em **Em uma agenda compartilhada** e selecione a agenda que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="9caff-124">If you have a shared schedule that contains the schedule information you want to use, click **On a shared schedule** and select the schedule you want to use.</span></span> <span data-ttu-id="9caff-125">Caso contrário, clique em **Em uma agenda personalizada**e em **Configurar** para especificar as opções para criar o histórico de relatórios de acordo com uma agenda recorrente.</span><span class="sxs-lookup"><span data-stu-id="9caff-125">Otherwise, click **On a custom schedule**, and then click **Configure** to specify options to create report history on a recurring schedule.</span></span>  
  
### <a name="to-create-report-history-when-data-is-refreshed-in-a-report"></a><span data-ttu-id="9caff-126">Para criar histórico de relatório quando dados são atualizados em um relatório</span><span class="sxs-lookup"><span data-stu-id="9caff-126">To create report history when data is refreshed in a report</span></span>  
  
1.  <span data-ttu-id="9caff-127">Aponte para o relatório.</span><span class="sxs-lookup"><span data-stu-id="9caff-127">Point to the report.</span></span>  
  
2.  <span data-ttu-id="9caff-128">Clique na seta para baixo e selecione **Gerenciar Opções de Processamento**.</span><span class="sxs-lookup"><span data-stu-id="9caff-128">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="9caff-129">Em **Opções de Instantâneo de Histórico**, clique em **Armazenar todos os instantâneos de dados de relatório no histórico de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="9caff-129">In **History Snapshot Options**, click **Store all report data snapshots in report history**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9caff-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9caff-130">See Also</span></span>  
 [<span data-ttu-id="9caff-131">Definir opções de processamento &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="9caff-131">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
  
