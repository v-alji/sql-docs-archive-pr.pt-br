---
title: Adicionar um instantâneo ao histórico de relatórios (Gerenciador de Relatórios) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
helpviewer_keywords:
- report history [Reporting Services], adding snapshots
- historical data [Reporting Services]
- snapshots [Reporting Services], adding report snapshots
- adding snapshots to report history
- report snapshots [Reporting Services], adding
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 84d4c264ab0b82fca2a34e6356b53113d63e6994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575630"
---
# <a name="add-a-snapshot-to-report-history-report-manager"></a><span data-ttu-id="79481-102">Adicionar um instantâneo ao histórico de relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="79481-102">Add a Snapshot to Report History (Report Manager)</span></span>

<span data-ttu-id="79481-103">O histórico de relatórios é uma coleção de instantâneos de relatórios que você cria.</span><span class="sxs-lookup"><span data-stu-id="79481-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="79481-104">Um instantâneo de relatório é um relatório que contém informações sobre layout e resultados de consulta que foram recuperados em um momento determinado.</span><span class="sxs-lookup"><span data-stu-id="79481-104">A report snapshot is a report that contains layout information and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="79481-105">Diferente dos relatórios sob demanda, que obtêm resultados de consulta atualizados quando o relatório é selecionado, os instantâneos de relatório são processados em uma agenda e salvos em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="79481-105">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="79481-106">Quando você seleciona um instantâneo de relatório para exibição, o servidor de relatório recupera o relatório armazenado do banco de dados do servidor e mostra os dados e o layout correspondentes ao momento em que o instantâneo foi criado.</span><span class="sxs-lookup"><span data-stu-id="79481-106">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
<span data-ttu-id="79481-107">Os instantâneos de relatório não são salvos em um formato de renderização específico.</span><span class="sxs-lookup"><span data-stu-id="79481-107">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="79481-108">Em vez disso, os instantâneos de relatório são renderizados em um formato de exibição final (como HTML) somente quando solicitado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="79481-108">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="79481-109">A renderização adiada deixa o instantâneo portátil.</span><span class="sxs-lookup"><span data-stu-id="79481-109">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="79481-110">O relatório pode ser renderizado no formato correto para a solicitação do dispositivo ou navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="79481-110">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
## <a name="to-manually-add-snapshots-to-report-history"></a><span data-ttu-id="79481-111">Para adicionar manualmente instantâneos ao histórico de relatórios</span><span class="sxs-lookup"><span data-stu-id="79481-111">To manually add snapshots to report history</span></span>

1. <span data-ttu-id="79481-112">No Gerenciador de Relatórios, navegue até a página **Conteúdo** , focalize o item cujo histórico você quer exibir e clique na seta suspensa.</span><span class="sxs-lookup"><span data-stu-id="79481-112">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>
  
2. <span data-ttu-id="79481-113">No menu suspenso, clique em **Exibir Histórico de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="79481-113">In the drop-down menu, click **View Report History**.</span></span>  
  
3. <span data-ttu-id="79481-114">Clique em **Novo Instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="79481-114">Click **New Snapshot**.</span></span> <span data-ttu-id="79481-115">Um novo instantâneo é criado na coluna **Quando Executado** .</span><span class="sxs-lookup"><span data-stu-id="79481-115">A new snapshot is created in the **When Run** column.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="79481-116">Para fazer isso, o histórico de relatório deve ser configurado pelo administrador como **Permitir que o histórico seja criado manualmente**.</span><span class="sxs-lookup"><span data-stu-id="79481-116">In order to do this, the report history must be configured by the administrator to **Allow history to be created manually**.</span></span> <span data-ttu-id="79481-117">Para obter mais informações, consulte [Limitar o histórico de relatório &#40;Gerenciador de Relatórios&#41;](../reports/limit-report-history-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="79481-117">For more information, see [Limit Report History &#40;Report Manager&#41;](../reports/limit-report-history-report-manager.md).</span></span>

4. <span data-ttu-id="79481-118">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="79481-118">Click **Apply**.</span></span>

## <a name="to-automatically-add-all-snapshots-to-report-history"></a><span data-ttu-id="79481-119">Para adicionar automaticamente todos os instantâneos ao histórico de relatórios</span><span class="sxs-lookup"><span data-stu-id="79481-119">To automatically add all snapshots to report history</span></span>  
  
1. <span data-ttu-id="79481-120">Para um relatório que já foi configurado para ser executado como um instantâneo de execução de relatório, é possível definir propriedades adicionais para salvar uma cópia do instantâneo no histórico de relatórios sempre que o instantâneo for atualizado.</span><span class="sxs-lookup"><span data-stu-id="79481-120">For a report that is already configured to run as a report execution snapshot, you can set additional properties to save a copy of the snapshot to report history each time the snapshot is refreshed.</span></span>  
  
2. <span data-ttu-id="79481-121">No Gerenciador de Relatórios, navegue até a página **Conteúdo** , focalize o item cujo histórico você quer exibir e clique na seta suspensa.</span><span class="sxs-lookup"><span data-stu-id="79481-121">In Report Manager, navigate to the **Contents** page, hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
3. <span data-ttu-id="79481-122">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="79481-122">In the drop-down menu, click **Manage**.</span></span>  
  
4. <span data-ttu-id="79481-123">Clique em **Opções de Instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="79481-123">Click **Snapshot Options**.</span></span>  
  
5. <span data-ttu-id="79481-124">Marque a caixa de seleção **Armazenar todos os instantâneos de execução de relatórios no histórico**.</span><span class="sxs-lookup"><span data-stu-id="79481-124">Select the check box for **Store all report execution snapshots in history**.</span></span>  
  
6. <span data-ttu-id="79481-125">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="79481-125">Click **Apply**.</span></span>  
  
### <a name="to-automatically-add-snapshots-to-report-history-based-on-a-schedule"></a><span data-ttu-id="79481-126">Para adicionar automaticamente instantâneos ao histórico de relatórios com base em um agendamento</span><span class="sxs-lookup"><span data-stu-id="79481-126">To automatically add snapshots to report history based on a schedule</span></span>  
  
1. <span data-ttu-id="79481-127">No Gerenciador de Relatórios, navegue até a página **Conteúdo** , focalize o item cujo histórico você quer exibir e clique na seta suspensa.</span><span class="sxs-lookup"><span data-stu-id="79481-127">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
2. <span data-ttu-id="79481-128">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="79481-128">In the drop-down menu, click **Manage**.</span></span>  
  
3. <span data-ttu-id="79481-129">Clique em **Opções de Instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="79481-129">Click **Snapshot Options**.</span></span>  
  
4. <span data-ttu-id="79481-130">Marque a caixa de seleção para **Usar o agendamento a seguir para adicionar instantâneos ao histórico de relatório**.</span><span class="sxs-lookup"><span data-stu-id="79481-130">Select the check box for **Use the following schedule to add snapshots to report history**.</span></span> <span data-ttu-id="79481-131">Execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="79481-131">Perform one of the following:</span></span>  
  
    - <span data-ttu-id="79481-132">Selecione **Agendamento específico do relatório**.</span><span class="sxs-lookup"><span data-stu-id="79481-132">Select **Report-specific schedule**.</span></span> <span data-ttu-id="79481-133">Preencha os detalhes do agendamento, selecione as datas de início e término e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79481-133">Fill in the schedule details, select the start and end dates for the schedule, and then click **OK**.</span></span>  
  
    - <span data-ttu-id="79481-134">Selecione **Agendamento compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="79481-134">Select **Shared schedule**.</span></span> <span data-ttu-id="79481-135">Na lista, selecione a agenda desejada.</span><span class="sxs-lookup"><span data-stu-id="79481-135">From the list, select the preferred schedule.</span></span>  
  
5. <span data-ttu-id="79481-136">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="79481-136">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79481-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79481-137">See Also</span></span>

- [<span data-ttu-id="79481-138">Configurar propriedades de execução de um relatório &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="79481-138">Configure Execution Properties for a Report  &#40;Report Manager&#41;</span></span>](../reports/configure-execution-properties-for-a-report-report-manager.md)
- [<span data-ttu-id="79481-139">Abrir e fechar um relatório &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="79481-139">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)
- [<span data-ttu-id="79481-140">Limitar o histórico de relatórios &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="79481-140">Limit Report History &#40;Report Manager&#41;</span></span>](../reports/limit-report-history-report-manager.md)
- [<span data-ttu-id="79481-141">Agendas</span><span class="sxs-lookup"><span data-stu-id="79481-141">Schedules</span></span>](../subscriptions/schedules.md)   
- [<span data-ttu-id="79481-142">Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79481-142">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)