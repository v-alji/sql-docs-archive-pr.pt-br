---
title: Notificações (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a61825f9450dd5b708aff8c3fc72f0f12732337b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583118"
---
# <a name="notifications-master-data-services"></a><span data-ttu-id="64bb5-102">Notificações (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="64bb5-102">Notifications (Master Data Services)</span></span>
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]<span data-ttu-id="64bb5-103">pode ser configurado para enviar uma notificação por email quando a validação da regra de negócio falha ou o status de uma versão do modelo é alterado.</span><span class="sxs-lookup"><span data-stu-id="64bb5-103">can be configured to send an email notification when business rule validation fails or the status of a model version changes.</span></span>  
  
## <a name="how-notifications-are-sent"></a><span data-ttu-id="64bb5-104">Como as notificações são enviadas</span><span class="sxs-lookup"><span data-stu-id="64bb5-104">How Notifications Are Sent</span></span>  
 <span data-ttu-id="64bb5-105">As notificações são configuradas no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64bb5-105">You configure notifications in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="64bb5-106">As notificações enviam mensagens de email usando Database Mail na instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] que hospeda o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="64bb5-106">Notifications send email messages by using Database Mail on the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that hosts the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="64bb5-107">Para obter mais informações sobre o Database Mail, consulte [Objetos de configuração do Database Mail](../relational-databases/database-mail/database-mail-configuration-objects.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64bb5-107">For more information about Database Mail, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="when-notifications-are-sent"></a><span data-ttu-id="64bb5-108">Quando as notificações são enviadas</span><span class="sxs-lookup"><span data-stu-id="64bb5-108">When Notifications Are Sent</span></span>  
 <span data-ttu-id="64bb5-109">Depois que as notificações são configuradas, notificações por email automatizadas podem ser enviadas nas instâncias a seguir.</span><span class="sxs-lookup"><span data-stu-id="64bb5-109">After notifications are configured, automated email notifications can be sent in the following instances.</span></span>  
  
|<span data-ttu-id="64bb5-110">Instância</span><span class="sxs-lookup"><span data-stu-id="64bb5-110">Instance</span></span>|<span data-ttu-id="64bb5-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="64bb5-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="64bb5-112">Os dados falham na validação de regras de negócio.</span><span class="sxs-lookup"><span data-stu-id="64bb5-112">Data fails business rule validation</span></span>|<span data-ttu-id="64bb5-113">Regras de negócio individuais devem ser configuradas para enviar email quando um valor de atributo é reprovado na validação da regra de negócio.</span><span class="sxs-lookup"><span data-stu-id="64bb5-113">Individual business rules must be configured to send email when an attribute value fails business rule validation.</span></span> <span data-ttu-id="64bb5-114">Para obter mais informações, consulte [Configurar regras de negócio para enviar notificações &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64bb5-114">For more information, see [Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span></span>|  
|<span data-ttu-id="64bb5-115">O status da versão do modelo é alterado</span><span class="sxs-lookup"><span data-stu-id="64bb5-115">Model version status changes</span></span>|<span data-ttu-id="64bb5-116">Cada vez que o status de uma versão de modelo muda, os usuários que são administradores de modelo recebem notificações automaticamente.</span><span class="sxs-lookup"><span data-stu-id="64bb5-116">Each time a model version's status changes, users that are model administrators receive notifications automatically.</span></span> <span data-ttu-id="64bb5-117">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64bb5-117">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>|  
  
## <a name="system-settings"></a><span data-ttu-id="64bb5-118">Configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="64bb5-118">System Settings</span></span>  
 <span data-ttu-id="64bb5-119">Existem configurações no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] que afetam as notificações.</span><span class="sxs-lookup"><span data-stu-id="64bb5-119">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="64bb5-120">Essas configurações podem ser ajustadas no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ou diretamente na tabela de Configurações do Sistema do banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64bb5-120">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="64bb5-121">Para obter mais informações, veja [Configurações do sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64bb5-121">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="64bb5-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="64bb5-122">Related Tasks</span></span>  
  
|<span data-ttu-id="64bb5-123">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="64bb5-123">Task Description</span></span>|<span data-ttu-id="64bb5-124">Tópico</span><span class="sxs-lookup"><span data-stu-id="64bb5-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="64bb5-125">Configurar o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] para enviar notificações por email.</span><span class="sxs-lookup"><span data-stu-id="64bb5-125">Configure [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email notifications.</span></span>|[<span data-ttu-id="64bb5-126">Configurar notificações por email &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64bb5-126">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)|  
|<span data-ttu-id="64bb5-127">Configurar o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para enviar notificações quando os valores dos atributos são alterados.</span><span class="sxs-lookup"><span data-stu-id="64bb5-127">Configure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to send notifications when attribute values change.</span></span>|[<span data-ttu-id="64bb5-128">Configurar regras de negócio para enviar notificações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64bb5-128">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="64bb5-129">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="64bb5-129">Related Content</span></span>  
  
-   [<span data-ttu-id="64bb5-130">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64bb5-130">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="64bb5-131">Versões &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64bb5-131">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
-   [<span data-ttu-id="64bb5-132">Solucionando problemas de notificações por email (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="64bb5-132">Troubleshooting Email Notifications (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
