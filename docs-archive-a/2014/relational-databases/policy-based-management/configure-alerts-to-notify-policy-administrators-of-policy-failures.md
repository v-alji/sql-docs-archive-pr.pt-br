---
title: Configurar alertas para notificar os administradores de políticas sobre falhas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9eb84ced3bb6313dd5920deaf479925556f08fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678724"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a><span data-ttu-id="b2ee3-102">Configurar alertas para notificar os administradores de políticas sobre falhas</span><span class="sxs-lookup"><span data-stu-id="b2ee3-102">Configure Alerts to Notify Policy Administrators of Policy Failures</span></span>
  <span data-ttu-id="b2ee3-103">Quando as políticas do Gerenciamento Baseado em Políticas são executadas em um dos três modos de avaliação automatizados, se ocorrer uma violação de política, uma mensagem será gravada no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-103">When Policy-Based Management policies are executed in one of the three automated evaluation modes, if a policy violation occurs, a message is written to the event log.</span></span> <span data-ttu-id="b2ee3-104">Para ser notificado quando essa mensagem for gravada no log de eventos, você pode criar um alerta para detectar a mensagem e executar uma ação.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-104">To be notified when this message is written to the event log, you can create an alert to detect the message and perform an action.</span></span> <span data-ttu-id="b2ee3-105">O alerta deve detectar as mensagens como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-105">The alert should detect the messages as shown in the following table.</span></span>  
  
|<span data-ttu-id="b2ee3-106">Modo de execução</span><span class="sxs-lookup"><span data-stu-id="b2ee3-106">Execution mode</span></span>|<span data-ttu-id="b2ee3-107">Número da mensagem</span><span class="sxs-lookup"><span data-stu-id="b2ee3-107">Message number</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="b2ee3-108">Ao alterar: impedir</span><span class="sxs-lookup"><span data-stu-id="b2ee3-108">On change: prevent</span></span><br /><br /> <span data-ttu-id="b2ee3-109">(se automático)</span><span class="sxs-lookup"><span data-stu-id="b2ee3-109">(if automatic)</span></span>|<span data-ttu-id="b2ee3-110">34050</span><span class="sxs-lookup"><span data-stu-id="b2ee3-110">34050</span></span>|  
|<span data-ttu-id="b2ee3-111">Ao alterar: impedir</span><span class="sxs-lookup"><span data-stu-id="b2ee3-111">On change: prevent</span></span><br /><br /> <span data-ttu-id="b2ee3-112">(se por demanda)</span><span class="sxs-lookup"><span data-stu-id="b2ee3-112">(if On demand)</span></span>|<span data-ttu-id="b2ee3-113">34051</span><span class="sxs-lookup"><span data-stu-id="b2ee3-113">34051</span></span>|  
|<span data-ttu-id="b2ee3-114">Ao agendar</span><span class="sxs-lookup"><span data-stu-id="b2ee3-114">On schedule</span></span>|<span data-ttu-id="b2ee3-115">34052</span><span class="sxs-lookup"><span data-stu-id="b2ee3-115">34052</span></span>|  
|<span data-ttu-id="b2ee3-116">Ao alterar</span><span class="sxs-lookup"><span data-stu-id="b2ee3-116">On change</span></span>|<span data-ttu-id="b2ee3-117">34053</span><span class="sxs-lookup"><span data-stu-id="b2ee3-117">34053</span></span>|  
  
 <span data-ttu-id="b2ee3-118">Para configurar um alerta para responder às mensagens de erro do Gerenciamento Baseado em Políticas, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b2ee3-118">To set up an alert to respond to the Policy-Based Management error messages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b2ee3-119">Criar um operador</span><span class="sxs-lookup"><span data-stu-id="b2ee3-119">Create an Operator</span></span>](../../ssms/agent/create-an-operator.md)  
  
-   [<span data-ttu-id="b2ee3-120">Criar um alerta usando um número de erro</span><span class="sxs-lookup"><span data-stu-id="b2ee3-120">Create an Alert Using an Error Number</span></span>](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="b2ee3-121">Atribuir alertas a um operador</span><span class="sxs-lookup"><span data-stu-id="b2ee3-121">Assign Alerts to an Operator</span></span>](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a><span data-ttu-id="b2ee3-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="b2ee3-122">Permissions</span></span>  
 <span data-ttu-id="b2ee3-123">Quando as políticas são avaliadas por demanda, elas são executadas no contexto de segurança do usuário.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-123">When policies are evaluated on demand, they execute in the security context of the user.</span></span> <span data-ttu-id="b2ee3-124">Para gravar no log de erros, o usuário deve ter permissões ALTER TRACE ou ser um membro da função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-124">To write to the error log, the user must have ALTER TRACE permissions or be a member of the sysadmin fixed server role.</span></span> <span data-ttu-id="b2ee3-125">As políticas avaliadas por um usuário que tenha menos privilégios não são gravadas no log de eventos e não disparam um alerta.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-125">Policies that are evaluated by a user that has less privileges will not write to the event log, and will not fire an alert.</span></span>  
  
 <span data-ttu-id="b2ee3-126">Os modos de execução automatizados são executados como um membro da função sysadmin.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-126">The automated execution modes execute as a member of the sysadmin role.</span></span> <span data-ttu-id="b2ee3-127">Isso permite que a política grave no log de erros e gere um alerta.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-127">This allows the policy to write to the error log and raise an alert.</span></span>  
  
## <a name="additional-considerations-about-alerts"></a><span data-ttu-id="b2ee3-128">Considerações adicionais sobre alertas</span><span class="sxs-lookup"><span data-stu-id="b2ee3-128">Additional Considerations About Alerts</span></span>  
 <span data-ttu-id="b2ee3-129">Esteja atento às seguintes considerações adicionais sobre alertas:</span><span class="sxs-lookup"><span data-stu-id="b2ee3-129">Be aware of the following additional considerations about alerts:</span></span>  
  
-   <span data-ttu-id="b2ee3-130">Os alertas só são gerados para políticas que estiverem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-130">Alerts are raised only for policies that are enabled.</span></span> <span data-ttu-id="b2ee3-131">Como as políticas **Sob demanda** não podem ser habilitadas, não são gerados alertas para políticas executadas sob demanda.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-131">Because **On demand** policies cannot be enabled, alerts are not raised for policies that are executed on demand.</span></span>  
  
-   <span data-ttu-id="b2ee3-132">Se a ação que você deseja executar incluir o envio de um email, você deverá configurar uma conta de email.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-132">If the action you want to take includes sending an e-mail message, you must configure a mail account.</span></span> <span data-ttu-id="b2ee3-133">É recomendável usar o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b2ee3-133">We recommend that you use Database Mail.</span></span> <span data-ttu-id="b2ee3-134">Para obter mais informações sobre como configurar o Database Mail, veja [Criar uma conta do Database Mail](../database-mail/create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="b2ee3-134">For more information about how to set up Database Mail, see [Create a Database Mail Account](../database-mail/create-a-database-mail-account.md).</span></span>  
  
  
