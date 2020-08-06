---
title: Página progresso (assistentes do grupo de disponibilidade AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.progress.f1
- sql12.swb.newagwizard.progress.f1
- sql11.swb.failoverwizard.progress.f1
- sql11.swb.adddatabasewizard.progress.f1
- sql11.swb.addreplicawizard.progress.f1
- sql11.swb.newagwizard.progress.f1
- sql12.swb.adddatabasewizard.progress.f1
- sql12.swb.failoverwixard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7de8df6906d930215d71a0adc562bd7cef961ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684918"
---
# <a name="progress-page-alwayson-availability-group-wizards"></a><span data-ttu-id="e2ce6-102">Página de Progresso (Assistentes de Grupo de Disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="e2ce6-102">Progress Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="e2ce6-103">Use esta caixa de diálogo para exibir o progresso de um assistente do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] que você está executando no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2ce6-103">Use this dialog box to view the progress of a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard that you are running in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e2ce6-104">A barra de progresso indica o progresso relativo das etapas que o assistente está executando.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-104">The progress bar indicates the relative progress of the steps that the wizard is performing.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e2ce6-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="e2ce6-105">UI element list</span></span>  
 <span data-ttu-id="e2ce6-106">**Mais detalhes**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-106">**More details**</span></span>  
 <span data-ttu-id="e2ce6-107">Clique na seta para baixo para exibir uma grade de progresso que lista todas as etapas concluídas, em ordem, seguidas pela operação em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-107">Click the down arrow to display a progress grid that lists any completed steps, in order, followed by the current in-progress operation.</span></span> <span data-ttu-id="e2ce6-108">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="e2ce6-108">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="e2ce6-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-109">**Name**</span></span>  
 <span data-ttu-id="e2ce6-110">Exibe uma frase que descreve uma etapa específica.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-110">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="e2ce6-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-111">**Status**</span></span>  
 <span data-ttu-id="e2ce6-112">Indica o resultado das etapas concluídas e o percentual de conclusão da etapa atual, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e2ce6-112">Indicates the outcome of completed steps and the percentage of completion of the current step, as follows:</span></span>  
  
|<span data-ttu-id="e2ce6-113">Result</span><span class="sxs-lookup"><span data-stu-id="e2ce6-113">Result</span></span>|<span data-ttu-id="e2ce6-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e2ce6-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e2ce6-115">**Erro**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-115">**Error**</span></span>|<span data-ttu-id="e2ce6-116">Indica que a operação desta etapa experimentou um erro.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-116">Indicates the operation for this step experienced an error.</span></span> <span data-ttu-id="e2ce6-117">Clique no link para exibir uma caixa de diálogo de mensagem que descreve o erro.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-117">Click the link to display a message dialog box that describes the error.</span></span>|  
|<span data-ttu-id="e2ce6-118">**Em andamento (** *percentual concluído* **)**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-118">**In Progress (** *percentage-completed* **)**</span></span>|<span data-ttu-id="e2ce6-119">Indica que a operação está ocorrendo agora e estima o percentual desta etapa que foi concluída.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-119">Indicates that the operation is occurring now and estimates the percentage of this step that has completed.</span></span>|  
|<span data-ttu-id="e2ce6-120">**Êxito**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-120">**Success**</span></span>|<span data-ttu-id="e2ce6-121">Indica que a operação desta etapa foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-121">Indicates the operation for this step completed successfully.</span></span>|  
  
 <span data-ttu-id="e2ce6-122">**Menos Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-122">**Fewer Details**</span></span>  
 <span data-ttu-id="e2ce6-123">Clique para ocultar a grade de progresso.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-123">Click to hide the progress grid.</span></span>  
  
 <span data-ttu-id="e2ce6-124">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="e2ce6-124">**Cancel**</span></span>  
 <span data-ttu-id="e2ce6-125">Clique para ignorar todas as operações restantes e sair do assistente.</span><span class="sxs-lookup"><span data-stu-id="e2ce6-125">Click to skip any remaining operations and then exit the wizard.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e2ce6-126">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e2ce6-126">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e2ce6-127">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ce6-127">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e2ce6-128">Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ce6-128">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e2ce6-129">Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ce6-129">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="e2ce6-130">Usar o Assistente de Grupo de Disponibilidade de Failover &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ce6-130">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2ce6-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2ce6-131">See Also</span></span>  
 [<span data-ttu-id="e2ce6-132">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ce6-132">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
