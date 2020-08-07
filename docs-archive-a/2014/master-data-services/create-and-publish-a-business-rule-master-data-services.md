---
title: Criar e publicar uma regra de negócios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], creating
- creating business rules [Master Data Services]
ms.assetid: 6961d636-4d69-468e-81f7-8d0be6a4a039
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4dfca5613a1f328e02b3fd2c7337885a23889207
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581987"
---
# <a name="create-and-publish-a-business-rule-master-data-services"></a><span data-ttu-id="84deb-102">Criar e publicar uma regra de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="84deb-102">Create and Publish a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="84deb-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie uma regra de negócio para garantir a exatidão de seus dados mestres.</span><span class="sxs-lookup"><span data-stu-id="84deb-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to ensure the accuracy of your master data.</span></span> <span data-ttu-id="84deb-104">Depois de ser criada, uma regra deve ser publicada para poder ser aplicada aos dados.</span><span class="sxs-lookup"><span data-stu-id="84deb-104">After you create a rule, you must publish it before you can apply it to data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84deb-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="84deb-105">Prerequisites</span></span>  
 <span data-ttu-id="84deb-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="84deb-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="84deb-107">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="84deb-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="84deb-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="84deb-108">You must be a model administrator.</span></span> <span data-ttu-id="84deb-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84deb-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-and-publish-a-business-rule"></a><span data-ttu-id="84deb-110">Para criar e publicar uma regra de negócio</span><span class="sxs-lookup"><span data-stu-id="84deb-110">To create and publish a business rule</span></span>  
  
1.  <span data-ttu-id="84deb-111">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="84deb-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="84deb-112">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="84deb-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="84deb-113">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="84deb-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="84deb-114">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="84deb-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="84deb-115">Na lista **Tipo de Membro** , selecione um tipo de membro ao qual a regra de negócio será aplicada.</span><span class="sxs-lookup"><span data-stu-id="84deb-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="84deb-116">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="84deb-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="84deb-117">Clique em **Adicionar regra de negócio**.</span><span class="sxs-lookup"><span data-stu-id="84deb-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="84deb-118">Clique em **Editar regra de negócio selecionada**.</span><span class="sxs-lookup"><span data-stu-id="84deb-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="84deb-119">No painel **Componentes** , expanda o nó **Condições** .</span><span class="sxs-lookup"><span data-stu-id="84deb-119">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="84deb-120">Clique em uma condição e arraste-a para o rótulo de **condições** do painel de **If** .</span><span class="sxs-lookup"><span data-stu-id="84deb-120">Click a condition and drag it to the **IF** pane's **Conditions** label.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="84deb-121">Você pode excluir itens de sua regra de negócio clicando com o botão direito do mouse e escolhendo **excluir**.</span><span class="sxs-lookup"><span data-stu-id="84deb-121">You can delete items from your business rule by right-clicking and choosing **Delete**.</span></span>  
  
11. <span data-ttu-id="84deb-122">No painel **atributos** , clique em um atributo e arraste-o para o rótulo de **atributo selecionar** do painel de **condição de edição** .</span><span class="sxs-lookup"><span data-stu-id="84deb-122">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="84deb-123">No painel **Editar condição** , preencha todos os campos obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="84deb-123">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
13. <span data-ttu-id="84deb-124">No painel **Editar Condição** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="84deb-124">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="84deb-125">No painel **Componentes** , expanda o nó **Ações** .</span><span class="sxs-lookup"><span data-stu-id="84deb-125">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="84deb-126">Clique em uma ação e arraste-a até o rótulo **Ação** do painel **THEN** .</span><span class="sxs-lookup"><span data-stu-id="84deb-126">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="84deb-127">No painel **Atributos** , clique em um atributo e arraste-o até o rótulo **Selecionar atributo** do painel **Editar Ação** .</span><span class="sxs-lookup"><span data-stu-id="84deb-127">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="84deb-128">No painel **Editar Ação** , preencha os campos necessários.</span><span class="sxs-lookup"><span data-stu-id="84deb-128">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="84deb-129">No painel **Editar Ação** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="84deb-129">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="84deb-130">Opcionalmente, adicione várias condições à regra.</span><span class="sxs-lookup"><span data-stu-id="84deb-130">Optionally, add multiple conditions to the rule.</span></span> <span data-ttu-id="84deb-131">Para obter mais informações, veja [Adicionar várias condições a uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84deb-131">For more information, see [Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span></span>  
  
20. <span data-ttu-id="84deb-132">Clique em **Voltar**.</span><span class="sxs-lookup"><span data-stu-id="84deb-132">Click **Back**.</span></span>  
  
21. <span data-ttu-id="84deb-133">Opcionalmente, na página **Manutenção de Regra de Negócio** , na linha que contém sua regra de negócio, clique duas vezes em uma célula da coluna **Nome**, **Descrição**ou **Notificação** para atualizar o valor.</span><span class="sxs-lookup"><span data-stu-id="84deb-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84deb-134">Notificações são enviadas somente para regras que incluem uma ação de validação.</span><span class="sxs-lookup"><span data-stu-id="84deb-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
22. <span data-ttu-id="84deb-135">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="84deb-135">Click **Publish business rules**.</span></span>  
  
23. <span data-ttu-id="84deb-136">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="84deb-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="84deb-137">O status da regra mudará para **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="84deb-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="84deb-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="84deb-138">Next Steps</span></span>  
  
-   <span data-ttu-id="84deb-139">Aplique regras de negócio a dados seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="84deb-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="84deb-140">Validar membros específicos em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="84deb-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="84deb-141">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="84deb-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="84deb-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84deb-142">See Also</span></span>  
 <span data-ttu-id="84deb-143">[Configurar regras de negócio para enviar notificações &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="84deb-143">[Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="84deb-144">[Alterar o nome de uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="84deb-144">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="84deb-145">Adicionar várias condições a uma regra de negócios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="84deb-145">Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md)  
  
  
