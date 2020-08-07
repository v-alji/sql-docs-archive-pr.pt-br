---
title: Configurar regras de negócio para enviar notificações (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cb1a12167dffe123e55760f031e21499fe22a945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584188"
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a><span data-ttu-id="dcaed-102">Configurar regras de negócio para enviar notificações (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dcaed-102">Configure Business Rules to Send Notifications (Master Data Services)</span></span>
  <span data-ttu-id="dcaed-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure regras de negócios para enviar notificações quando você desejar notificar os usuários sobre alterações de valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="dcaed-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure business rules to send notifications when you want to notify users about attribute value changes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dcaed-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="dcaed-104">Prerequisites</span></span>  
 <span data-ttu-id="dcaed-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="dcaed-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dcaed-106">Você deve ter permissão para acessar as áreas funcionais **Administração do Sistema** e **Permissões de Usuário e de Grupo** .</span><span class="sxs-lookup"><span data-stu-id="dcaed-106">You must have permission to access the **System Administration** and **User and Group Permissions** functional areas.</span></span> <span data-ttu-id="dcaed-107">Se você não tiver permissão para a área funcional **Permissões de Usuário e de Grupo** , não poderá exibir a lista de usuários e grupos para a qual enviar notificações.</span><span class="sxs-lookup"><span data-stu-id="dcaed-107">If you do not have permission to the **User and Group Permissions** functional area, you cannot view the list of users and groups to send notifications to.</span></span>  
  
-   <span data-ttu-id="dcaed-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="dcaed-108">You must be a model administrator.</span></span> <span data-ttu-id="dcaed-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dcaed-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="dcaed-110">Uma regra de negócios que usa uma ação de validação já deve existir.</span><span class="sxs-lookup"><span data-stu-id="dcaed-110">A business rule that uses a validation action must already exist.</span></span> <span data-ttu-id="dcaed-111">Para obter mais informações, consulte [Criar e publicar uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dcaed-111">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="dcaed-112">O usuário ou grupo que recebe a notificação deve ter, no mínimo, a permissão **Somente leitura** no atributo que falhar na validação.</span><span class="sxs-lookup"><span data-stu-id="dcaed-112">The user or group that receives the notification must have at least **Read-only** permission to the attribute that fails validation.</span></span> <span data-ttu-id="dcaed-113">Os usuários ou grupos que tiverem a permissão para o atributo negada de forma explícita ou implícita receberão o email, mas não poderão acessar o atributo no [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcaed-113">Users or groups that are explicitly or implicitly denied permission to the attribute will receive the email but will not be able to access the attribute in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="dcaed-114">Se o email for enviado a um grupo, somente os membros do grupo que tiverem acessado o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] receberão o email.</span><span class="sxs-lookup"><span data-stu-id="dcaed-114">If mail is sent to a group, only members of the group that have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] will get the email.</span></span>  
  
### <a name="to-configure-business-rules-to-send-notifications"></a><span data-ttu-id="dcaed-115">Para configurar regras de negócios para enviar notificações</span><span class="sxs-lookup"><span data-stu-id="dcaed-115">To configure business rules to send notifications</span></span>  
  
1.  <span data-ttu-id="dcaed-116">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="dcaed-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="dcaed-117">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="dcaed-117">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="dcaed-118">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="dcaed-118">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="dcaed-119">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="dcaed-119">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="dcaed-120">Na lista **tipo de membro** , selecione um tipo de membro.</span><span class="sxs-lookup"><span data-stu-id="dcaed-120">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="dcaed-121">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="dcaed-121">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="dcaed-122">Na grade, na linha da regra de negócio, clique duas vezes no campo de **notificação** .</span><span class="sxs-lookup"><span data-stu-id="dcaed-122">In the grid, in the row for the business rule, double-click the **Notification** field.</span></span>  
  
8.  <span data-ttu-id="dcaed-123">No submenu, clique em um usuário ou grupo para o qual enviar a notificação por email.</span><span class="sxs-lookup"><span data-stu-id="dcaed-123">From the sub-menu, click a user or group to send the email notification to.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dcaed-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dcaed-124">Next Steps</span></span>  
  
-   <span data-ttu-id="dcaed-125">Aplique regras de negócio a dados seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="dcaed-125">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="dcaed-126">Validar membros específicos em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcaed-126">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="dcaed-127">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcaed-127">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   <span data-ttu-id="dcaed-128">Configure o protocolo de email da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dcaed-128">Configure the email protocol as follows:</span></span>  
  
    -   [<span data-ttu-id="dcaed-129">Configurar notificações por email &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcaed-129">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="dcaed-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dcaed-130">See Also</span></span>  
 <span data-ttu-id="dcaed-131">[Master Data Services de notificações &#40;&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dcaed-131">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 [<span data-ttu-id="dcaed-132">Configurar notificações por email &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcaed-132">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
  
