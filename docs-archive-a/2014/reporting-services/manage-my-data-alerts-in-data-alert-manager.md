---
title: Gerenciar Meus Alertas de Dados no Gerenciador de Alertas de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 371c62c2f97334e20280a659c8039ab20852ccfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683444"
---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a><span data-ttu-id="20db1-102">Gerenciar meus alertas de dados no Gerenciador de Alertas de Dados</span><span class="sxs-lookup"><span data-stu-id="20db1-102">Manage My Data Alerts in Data Alert Manager</span></span>
  <span data-ttu-id="20db1-103">Os usuários do SharePoint podem exibir uma lista dos alertas de dados que criaram e informações sobre os alertas.</span><span class="sxs-lookup"><span data-stu-id="20db1-103">SharePoint users can view a list of the data alerts that they created and information about the alerts.</span></span> <span data-ttu-id="20db1-104">Os usuários também podem excluir seus alertas, abrir definições de alerta para edição no Designer de Alertas de Dados e executar seus alertas.</span><span class="sxs-lookup"><span data-stu-id="20db1-104">Users can also delete their alerts, open alert definitions for edit in Data Alert Designer, and run their alerts.</span></span> <span data-ttu-id="20db1-105">A imagem a seguir mostra os recursos disponíveis para os usuários no Gerenciador de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="20db1-105">The following picture shows the features available to users in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="20db1-106">![Recursos do Gerenciador de Alertas para usuários do SharePoint](media/rs-alertmanageriw.gif "Recursos do Gerenciador de Alertas para usuários do SharePoint")</span><span class="sxs-lookup"><span data-stu-id="20db1-106">![Alert Manager features for SharePoint users](media/rs-alertmanageriw.gif "Alert Manager features for SharePoint users")</span></span>  
  
### <a name="to-view-a-list-of-your-alerts"></a><span data-ttu-id="20db1-107">Para exibir uma lista dos seus alertas</span><span class="sxs-lookup"><span data-stu-id="20db1-107">To view a list of your alerts</span></span>  
  
1.  <span data-ttu-id="20db1-108">Vá para a biblioteca do SharePoint onde você salvou os relatórios em que criou os alertas de dados.</span><span class="sxs-lookup"><span data-stu-id="20db1-108">Go to the SharePoint library where you saved the reports on which you created data alerts.</span></span>  
  
2.  <span data-ttu-id="20db1-109">Clique no ícone para expandir o menu suspenso em um relatório e clique em **Gerenciar Alertas de Dados**.</span><span class="sxs-lookup"><span data-stu-id="20db1-109">Click the icon for the expand drop-down menu on a report and click **Manage Data Alerts**.</span></span> <span data-ttu-id="20db1-110">A imagem a seguir mostra o menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="20db1-110">The following picture shows the drop-down menu.</span></span>  
  
     <span data-ttu-id="20db1-111">![Abrir o Gerenciador de Alertas no menu de contexto de relatório](media/rs-openalertmanager.gif "Abrir o Gerenciador de Alertas no menu de contexto de relatório")</span><span class="sxs-lookup"><span data-stu-id="20db1-111">![Open Alert Manager from report context menu](media/rs-openalertmanager.gif "Open Alert Manager from report context menu")</span></span>  
  
     <span data-ttu-id="20db1-112">O Gerenciador de Alertas de Dados é aberto.</span><span class="sxs-lookup"><span data-stu-id="20db1-112">Data Alert Manager opens.</span></span> <span data-ttu-id="20db1-113">Por padrão, ele lista os alertas para o relatório que você selecionou na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="20db1-113">By default, it lists the alerts for the report that you selected in the library.</span></span>  
  
3.  <span data-ttu-id="20db1-114">Clique na seta para baixo ao lado de **Exibir alertas para o relatório** e selecione um relatório para exibir seus alertas ou clique em **Mostrar Tudo** para listar todos os alertas.</span><span class="sxs-lookup"><span data-stu-id="20db1-114">Click the down arrow next to the **View alerts for report** list and select a report to view its alerts, or click **Show All** to list all alerts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20db1-115">Se o relatório que você selecionou não tiver nenhum alerta, você não precisará voltar à biblioteca do SharePoint para localizar e selecionar um relatório que tenha alertas.</span><span class="sxs-lookup"><span data-stu-id="20db1-115">If the report that you selected does not have any alerts, you do not have to return to the SharePoint library to locate and select a report that hasalerts.</span></span> <span data-ttu-id="20db1-116">Em vez disso, clique em **Mostrar Tudo** para consultar uma lista com todos os alertas.</span><span class="sxs-lookup"><span data-stu-id="20db1-116">Instead, click **Show All** to see a list of all your alerts.</span></span>  
  
     <span data-ttu-id="20db1-117">Uma tabela lista o nome do alerta, o nome do relatório, seu nome como criador do alerta, o número com o qual o alerta foi enviado, a última vez que a definição de alerta foi modificada e o status do alerta.</span><span class="sxs-lookup"><span data-stu-id="20db1-117">A table lists the alert name, report name, your name as the creator of the alert, the number the alert was sent, the last time the alert definition was modified, and the status of the alert.</span></span> <span data-ttu-id="20db1-118">Se o alerta não puder ser gerado ou enviado, a coluna de status conterá informações sobre o erro e ajudará a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="20db1-118">If the alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-edit-an-alert-definition"></a><span data-ttu-id="20db1-119">Para editar uma definição de alerta</span><span class="sxs-lookup"><span data-stu-id="20db1-119">To edit an alert definition</span></span>  
  
-   <span data-ttu-id="20db1-120">Clique com o botão direito do mouse no alerta de dados para o qual você deseja editar a definição de alerta e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="20db1-120">Right-click the data alert for which you want to edit the alert definition and click **Edit**.</span></span>  
  
     <span data-ttu-id="20db1-121">A definição de alerta é aberta no Designer de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="20db1-121">The alert definition opens in Data Alert Designer.</span></span> <span data-ttu-id="20db1-122">Para obter mais informações, consulte [Editar um Alerta de Dados no Designer de Alertas](edit-a-data-alert-in-alert-designer.md) e [Designer de Alertas de Dados](../../2014/reporting-services/data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="20db1-122">For more information, see [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md) and [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20db1-123">Apenas o usuário que criou a definição de alerta de dados pode editá-la.</span><span class="sxs-lookup"><span data-stu-id="20db1-123">Only the user that created the data alert definition can edit it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20db1-124">Se o relatório tiver sido alterado e os feeds de dados gerados no relatório tiverem sido alterados, a definição de alerta talvez não seja mais válida.</span><span class="sxs-lookup"><span data-stu-id="20db1-124">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="20db1-125">Isso ocorre quando uma coluna referenciada pelo alerta nas regras é excluída do relatório, altera o tipo de dados ou é incluída em outro feed de dados, ou quando o relatório é excluído ou movido.</span><span class="sxs-lookup"><span data-stu-id="20db1-125">This occurs when a column that the alert references in its rules is deleted from the report, changes data type, or is included in a different data feed or the report is deleted or moved.</span></span> <span data-ttu-id="20db1-126">Você pode abrir uma definição de alerta que não é válida, mas só pode salvá-la novamente depois que ela estiver válida com base na versão atual do feed de dados de relatório do qual ela depende.</span><span class="sxs-lookup"><span data-stu-id="20db1-126">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="20db1-127">Para saber mais sobre como os feeds de dados são gerados com base em relatórios, consulte [Gerando feeds de dados com base em relatórios &#40;Construtor de Relatórios e SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="20db1-127">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="20db1-128">Para excluir uma definição de alerta</span><span class="sxs-lookup"><span data-stu-id="20db1-128">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="20db1-129">Clique com o botão direito do mouse no alerta de dados que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="20db1-129">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
     <span data-ttu-id="20db1-130">Quando você excluir o alerta, nenhuma mensagem de alerta adicional será enviada.</span><span class="sxs-lookup"><span data-stu-id="20db1-130">When you delete the alert, no further alert messages are sent.</span></span>  
  
### <a name="to-run-an-alert"></a><span data-ttu-id="20db1-131">Para executar um alerta</span><span class="sxs-lookup"><span data-stu-id="20db1-131">To run an alert</span></span>  
  
-   <span data-ttu-id="20db1-132">Clique com o botão direito do mouse no alerta de dados que você deseja executar e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="20db1-132">Right-click the data alert that you want to run and click **Run**.</span></span>  
  
     <span data-ttu-id="20db1-133">A instância do alerta é criada e a mensagem de alerta de dados é enviada imediatamente, independentemente das opções de agenda especificadas no Designer de Alerta de Dados.</span><span class="sxs-lookup"><span data-stu-id="20db1-133">The alert instance is created and the data alert message is immediately sent, regardless of the schedule options you specified in Data Alert Designer.</span></span> <span data-ttu-id="20db1-134">Por exemplo, um alerta configurado para ser enviado semanalmente e, depois, somente se a alteração de resultados for enviada.</span><span class="sxs-lookup"><span data-stu-id="20db1-134">For example, an alert configured to be sent weekly and then only if the results change is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20db1-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="20db1-135">See Also</span></span>  
 <span data-ttu-id="20db1-136">[Gerenciador de Alertas de dados para administradores de alertas](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="20db1-136">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="20db1-137">Alertas de dados do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="20db1-137">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
