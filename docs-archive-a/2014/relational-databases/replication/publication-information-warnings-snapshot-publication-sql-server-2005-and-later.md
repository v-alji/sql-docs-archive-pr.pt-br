---
title: Informações da publicação, avisos (publicação de instantâneo, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.snapshot.f1
ms.assetid: 7aa2eb52-b6b7-4dd3-8483-8ef00d9f0435
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3ae662a339e1e211ce4f46a588f4d7de65bf5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681572"
---
# <a name="publication-information-warnings-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="c9422-102">Informações da Publicação, Avisos (publicação de instantâneo, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="c9422-102">Publication Information, Warnings (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="c9422-103">A guia **Avisos** está disponível para Distribuidores que estão executando [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="c9422-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="c9422-104">A guia **Avisos** permite executar as seguintes tarefas para a publicação selecionada:</span><span class="sxs-lookup"><span data-stu-id="c9422-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="c9422-105">Habilitar avisos.</span><span class="sxs-lookup"><span data-stu-id="c9422-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="c9422-106">Especificar limites associados a avisos.</span><span class="sxs-lookup"><span data-stu-id="c9422-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="c9422-107">Definir alertas associados a avisos.</span><span class="sxs-lookup"><span data-stu-id="c9422-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="c9422-108">Avisos, limites e alertas</span><span class="sxs-lookup"><span data-stu-id="c9422-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="c9422-109">Por padrão, o Replication Monitor exibe avisos para assinaturas não inicializadas: um status **Assinatura não inicializada** é exibido como um aviso na coluna **Status** de páginas que incluem informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="c9422-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="c9422-110">Para publicações de instantâneo, você também pode especificar que a expiração iminente da assinatura resulte em um aviso, com a definição da opção **Avisar se uma assinatura for expirar dentro do limite**.</span><span class="sxs-lookup"><span data-stu-id="c9422-110">For snapshot publications, you can also specify that imminent subscription expiration results in a warning by setting the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="c9422-111">Se o limite especificado for alcançado ou ultrapassado, o status da assinatura será exibido como **Expirando em breve/Expirado** (a menos que um problema com prioridade mais alta precise ser exibido).</span><span class="sxs-lookup"><span data-stu-id="c9422-111">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="c9422-112">Além de exibir de um aviso no Replication Monitor, atingir um limite também pode disparar um alerta.</span><span class="sxs-lookup"><span data-stu-id="c9422-112">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="c9422-113">Os alertas são definidos clicando em **Configurar Alertas** e fornecendo informações na caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="c9422-113">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9422-114">Opções</span><span class="sxs-lookup"><span data-stu-id="c9422-114">Options</span></span>  
 <span data-ttu-id="c9422-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="c9422-115">**Enabled**</span></span>  
 <span data-ttu-id="c9422-116">Selecione para habilitar um aviso e especificar um limite.</span><span class="sxs-lookup"><span data-stu-id="c9422-116">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="c9422-117">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="c9422-117">**Warning**</span></span>  
 <span data-ttu-id="c9422-118">Uma descrição do aviso associada a um limite.</span><span class="sxs-lookup"><span data-stu-id="c9422-118">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="c9422-119">**Limite**</span><span class="sxs-lookup"><span data-stu-id="c9422-119">**Threshold**</span></span>  
 <span data-ttu-id="c9422-120">Especifique um valor para o limite.</span><span class="sxs-lookup"><span data-stu-id="c9422-120">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="c9422-121">**Configurar Alertas**</span><span class="sxs-lookup"><span data-stu-id="c9422-121">**Configure Alerts**</span></span>  
 <span data-ttu-id="c9422-122">Selecione uma linha na grade **Avisos** e clique em **Configurar Alertas** para iniciar a caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="c9422-122">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="c9422-123">A caixa de diálogo permite definir um alerta associado ao limite selecionado e ao aviso.</span><span class="sxs-lookup"><span data-stu-id="c9422-123">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="c9422-124">**Descartar Alterações**</span><span class="sxs-lookup"><span data-stu-id="c9422-124">**Discard Changes**</span></span>  
 <span data-ttu-id="c9422-125">Clique para descartar qualquer alteração em avisos e limites.</span><span class="sxs-lookup"><span data-stu-id="c9422-125">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9422-126">Clicar em **Descartar Alterações** não afeta alertas definidos na caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="c9422-126">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="c9422-127">**Salvar alterações**</span><span class="sxs-lookup"><span data-stu-id="c9422-127">**Save Changes**</span></span>  
 <span data-ttu-id="c9422-128">Clique para salvar qualquer alteração em avisos e limites.</span><span class="sxs-lookup"><span data-stu-id="c9422-128">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9422-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9422-129">See Also</span></span>  
 <span data-ttu-id="c9422-130">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c9422-130">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="c9422-131">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c9422-131">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="c9422-132">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="c9422-132">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
