---
title: Gerenciar todos os alertas de dados em um site do SharePoint no Gerenciador de Alertas de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 9c70b0f4-2db8-4c2e-acbf-96e2a55ddc48
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b41fdbd18a0b1b4a7a69a3ca202de1c555c070de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683443"
---
# <a name="manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager"></a><span data-ttu-id="d2054-102">Gerenciar todos os alertas de dados em um site do SharePoint no Gerenciador de Alertas de Dados</span><span class="sxs-lookup"><span data-stu-id="d2054-102">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>
  <span data-ttu-id="d2054-103">Os administradores de alerta do SharePoint podem exibir uma lista dos alertas de dados criados por qualquer usuário do site e informações sobre os alertas.</span><span class="sxs-lookup"><span data-stu-id="d2054-103">SharePoint alerting administrators can view a list of the data alerts that were created by any site user and information about the alerts.</span></span> <span data-ttu-id="d2054-104">Os administradores de alerta também podem excluir alertas.</span><span class="sxs-lookup"><span data-stu-id="d2054-104">Alerting administrators can also delete alerts.</span></span> <span data-ttu-id="d2054-105">A imagem a seguir mostra os recursos disponíveis para os administradores de alerta no Gerenciador de Alerta de Dados.</span><span class="sxs-lookup"><span data-stu-id="d2054-105">The following picture shows the features available to alerting administrators in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="d2054-106">![Gerenciador de Alertas para administradores do site do SharePoint](media/rs-alertmanagersite.gif "Gerenciador de Alertas para administradores do site do SharePoint")</span><span class="sxs-lookup"><span data-stu-id="d2054-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>  
  
### <a name="to-view-a-list-of-alerts-created-by-a-site-user"></a><span data-ttu-id="d2054-107">Para exibir uma lista dos alertas criados por um usuário de site</span><span class="sxs-lookup"><span data-stu-id="d2054-107">To view a list of alerts created by a site user</span></span>  
  
1.  <span data-ttu-id="d2054-108">Vá para o site do SharePoint onde as definições de alertas de dados são salvas.</span><span class="sxs-lookup"><span data-stu-id="d2054-108">Go to the SharePoint site where data alerts definitions are saved.</span></span>  
  
2.  <span data-ttu-id="d2054-109">Na home page, clique em **Ações do Site**.</span><span class="sxs-lookup"><span data-stu-id="d2054-109">On the Home page, click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="d2054-110">Role para a parte inferior da lista e clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="d2054-110">Scroll to the bottom of the list and click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="d2054-111">No **Reporting Services**, clique em **Gerenciar Alertas de Dados**.</span><span class="sxs-lookup"><span data-stu-id="d2054-111">Under **Reporting Services**, click **Manage Data Alerts**.</span></span>  
  
5.  <span data-ttu-id="d2054-112">Clique na seta para baixo na lista **Exibir alertas de usuário** e selecione o usuário cujos alertas você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d2054-112">Click the down arrow by the **View alerts for user** list and select the user whose alerts you want to view.</span></span>  
  
6.  <span data-ttu-id="d2054-113">Clique na seta para baixo ao lado de **Exibir alertas de relatório** e selecione um alerta específico a ser exibido ou clique em **Mostrar Tudo** para listar todos os alertas criados pelo usuário selecionado.</span><span class="sxs-lookup"><span data-stu-id="d2054-113">Click the down arrow next to the **View alerts for report** list and select a specific alert to view, or click **Show All** to list all alerts created by the selected user.</span></span>  
  
     <span data-ttu-id="d2054-114">Uma tabela lista o nome do alerta, o nome do relatório, o nome da pessoa que criou o alerta de dados, o número de vezes em que o alerta de dados foi enviado, a última vez que a definição do alerta de dados foi modificada e o status do alerta de dados.</span><span class="sxs-lookup"><span data-stu-id="d2054-114">A table lists the name, report name, name of the person who created the data alert, the number times the data alert was sent, the last time the data alert definition was modified, and the status of the data alert.</span></span> <span data-ttu-id="d2054-115">Se o alerta de dados não puder ser gerado ou enviado, a coluna de status conterá informações sobre o erro e ajudará você a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="d2054-115">If the data alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="d2054-116">Para excluir uma definição de alerta</span><span class="sxs-lookup"><span data-stu-id="d2054-116">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="d2054-117">Clique com o botão direito do mouse no alerta de dados que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d2054-117">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d2054-118">Depois que você excluir o alerta, nenhuma mensagem de alerta adicional será enviada.</span><span class="sxs-lookup"><span data-stu-id="d2054-118">After you delete the alert, no further alert messages are sent.</span></span> <span data-ttu-id="d2054-119">No entanto, se você consultar o banco de dados de alertas, talvez descubra que a definição de alerta ainda existe.</span><span class="sxs-lookup"><span data-stu-id="d2054-119">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="d2054-120">O serviço de alerta executa a limpeza de acordo com uma agenda e a definição de alerta será excluída permanentemente na próxima limpeza.</span><span class="sxs-lookup"><span data-stu-id="d2054-120">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="d2054-121">O intervalo de limpeza padrão é de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="d2054-121">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="d2054-122">Esse e outros intervalos de limpeza são configuráveis.</span><span class="sxs-lookup"><span data-stu-id="d2054-122">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="d2054-123">Para obter mais informações, consulte [Reporting Services Data Alerts](../ssms/agent/alerts.md)[Alertas de dados do Reporting Services].</span><span class="sxs-lookup"><span data-stu-id="d2054-123">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2054-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2054-124">See Also</span></span>  
 <span data-ttu-id="d2054-125">[Gerenciador de Alertas de dados para administradores de alertas](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="d2054-125">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="d2054-126">Alertas de dados do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d2054-126">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
