---
title: Editar um alerta de dados no Designer de Alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- editing, data alerts
- updating, data alerts
- editing, alerts
- updating, alerts
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9906b33ae50d51733eaec1bf5c201c9f5b5d120e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682151"
---
# <a name="edit-a-data-alert-in-alert-designer"></a><span data-ttu-id="c34ca-102">Editar um alerta de dados no Designer de Alertas</span><span class="sxs-lookup"><span data-stu-id="c34ca-102">Edit a Data Alert in Alert Designer</span></span>
  <span data-ttu-id="c34ca-103">Você abre a definição de alerta de dados que deseja editar no Gerenciador de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c34ca-103">You open the data alert definition that you want to edit from Data Alert Manager.</span></span> <span data-ttu-id="c34ca-104">Apenas o usuário que criou a definição de alerta pode editá-la.</span><span class="sxs-lookup"><span data-stu-id="c34ca-104">Only the user that created the alert definition can edit it.</span></span> <span data-ttu-id="c34ca-105">Para obter mais informações sobre como abrir o Gerenciador de Alertas de Dados, consulte [Gerenciar meus alertas de dados no Gerenciador de Alertas de Dados](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c34ca-105">For more information about opening Data Alert Manager, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="c34ca-106">A imagem a seguir mostra o menu de contexto em um alerta de dados no Gerenciador de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c34ca-106">The following picture shows you the context menu on a data alert in Data Alert Manager.</span></span>

 <span data-ttu-id="c34ca-107">![Abrir o Designer de Alertas de Dados clicando em Editar](media/rs-alertmanageriwopendesigner.gif "Abrir o Designer de Alertas de Dados clicando em Editar")</span><span class="sxs-lookup"><span data-stu-id="c34ca-107">![Open Data Alert Designer by clicking Edit](media/rs-alertmanageriwopendesigner.gif "Open Data Alert Designer by clicking Edit")</span></span>

 <span data-ttu-id="c34ca-108">O procedimento a seguir inclui as etapas para abrir a definição de alerta para edição no Designer de Alertas de Dados no Gerenciador de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c34ca-108">The following procedure includes the steps to open the alert definition for editing in Data Alert Designer from Data Alert Manager.</span></span>

### <a name="to-edit-a-data-alert-definition-in-data-alert-designer"></a><span data-ttu-id="c34ca-109">Para editar uma definição de alerta de dados no Designer de Alertas de Dados</span><span class="sxs-lookup"><span data-stu-id="c34ca-109">To edit a data alert definition in Data Alert Designer</span></span>

1.  <span data-ttu-id="c34ca-110">No Gerenciador de Alertas de Dados, clique com o botão direito do mouse na definição de alerta de dados que você deseja editar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c34ca-110">In Data Alert Manager, right-click the data alert definition that you want to edit and click **Edit**.</span></span>

     <span data-ttu-id="c34ca-111">A definição de alerta é aberta no Designer de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c34ca-111">The alert definition opens in Data Alert Designer.</span></span>

2.  <span data-ttu-id="c34ca-112">Atualize as regras, as configurações de agenda e as configurações de email.</span><span class="sxs-lookup"><span data-stu-id="c34ca-112">Update the rules, schedule settings, and email settings.</span></span> <span data-ttu-id="c34ca-113">Para obter mais informações, consulte [Designer de Alertas de Dados](../../2014/reporting-services/data-alert-designer.md) e [Criar um Alerta de Dados no Designer de Alertas de Dados](create-a-data-alert-in-data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c34ca-113">For more information, see [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) and [Create a Data Alert in Data Alert Designer](create-a-data-alert-in-data-alert-designer.md).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c34ca-114">Você não pode escolher um feed de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="c34ca-114">You cannot choose a different data feed.</span></span> <span data-ttu-id="c34ca-115">Para usar um feed de dados diferente, você deve criar uma nova definição de alerta de dados.</span><span class="sxs-lookup"><span data-stu-id="c34ca-115">To use a different data feed, you must create a new data alert definition.</span></span>

3.  <span data-ttu-id="c34ca-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c34ca-116">Click **Save**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c34ca-117">Se o relatório tiver sido alterado e os feeds de dados gerados no relatório tiverem sido alterados, a definição de alerta talvez não seja mais válida.</span><span class="sxs-lookup"><span data-stu-id="c34ca-117">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="c34ca-118">Isso ocorre quando uma coluna referenciada pela definição de alerta nas regras é excluída do relatório ou altera o tipo de dados, ou quando o relatório é excluído ou movido.</span><span class="sxs-lookup"><span data-stu-id="c34ca-118">This occurs when a column that the alert definition references in its rules is deleted from the report or changes data type or the report is deleted or moved.</span></span> <span data-ttu-id="c34ca-119">Você pode abrir uma definição de alerta que não é válida, mas só pode salvá-la novamente depois que ela estiver válida com base na versão atual do feed de dados de relatório do qual ela depende.</span><span class="sxs-lookup"><span data-stu-id="c34ca-119">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="c34ca-120">Para saber mais sobre como os feeds de dados são gerados com base em relatórios, consulte [Gerando feeds de dados com base em relatórios &#40;Construtor de Relatórios e SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c34ca-120">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c34ca-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c34ca-121">See Also</span></span>
 <span data-ttu-id="c34ca-122">[Gerenciador de alertas de dados para administradores de alerta](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services alertas de dados](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c34ca-122">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


