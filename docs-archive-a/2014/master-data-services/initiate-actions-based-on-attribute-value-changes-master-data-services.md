---
title: Iniciar ações com base em alterações no valor do atributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], tracking attribute changes
- change tracking groups [Master Data Services], initiating actions
ms.assetid: 5e4402ce-31db-4774-a2a1-552335f87693
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 50931b9f9c4bd5d08596d485ba695143b9c6594e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679392"
---
# <a name="initiate-actions-based-on-attribute-value-changes-master-data-services"></a><span data-ttu-id="b1abe-102">Iniciar ações com base em alterações no valor do atributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b1abe-102">Initiate Actions Based on Attribute Value Changes (Master Data Services)</span></span>
  <span data-ttu-id="b1abe-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie uma regra de negócio para iniciar ações com base em alterações para atribuir valores.</span><span class="sxs-lookup"><span data-stu-id="b1abe-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to initiate actions based on changes to attribute values.</span></span> <span data-ttu-id="b1abe-104">Por exemplo, quando uma valor de atributo específico for alterado, você pode querer alterar um valor, enviar uma notificação ou iniciar um fluxo de trabalho externo.</span><span class="sxs-lookup"><span data-stu-id="b1abe-104">For example, when a specific attribute value changes, you may want to change a value, send a notification, or start an external workflow.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b1abe-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b1abe-105">Prerequisites</span></span>  
 <span data-ttu-id="b1abe-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="b1abe-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b1abe-107">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="b1abe-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="b1abe-108">You must be a model administrator.</span></span> <span data-ttu-id="b1abe-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b1abe-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b1abe-110">Seus atributos devem estar em um grupo de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="b1abe-110">Your attributes must be in a change tracking group.</span></span> <span data-ttu-id="b1abe-111">Consulte [Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b1abe-111">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
### <a name="to-create-a-business-rule-to-initiate-actions-based-on-attribute-value-changes"></a><span data-ttu-id="b1abe-112">Criar uma regra de negócios para iniciar ações com base em alterações de valores</span><span class="sxs-lookup"><span data-stu-id="b1abe-112">To create a business rule to initiate actions based on attribute value changes</span></span>  
  
1.  <span data-ttu-id="b1abe-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b1abe-114">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-114">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="b1abe-115">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="b1abe-115">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="b1abe-116">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="b1abe-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="b1abe-117">Na lista **Tipo de Membro** , selecione um tipo de membro ao qual a regra de negócio será aplicada.</span><span class="sxs-lookup"><span data-stu-id="b1abe-117">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="b1abe-118">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-118">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="b1abe-119">Clique em **Adicionar regra de negócio**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-119">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="b1abe-120">Clique em **Editar regra de negócio selecionada**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-120">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="b1abe-121">No painel **Componentes** , expanda o nó **Condições** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-121">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="b1abe-122">No nó **Comparação de valores** , arraste **foi alterado** para o rótulo **Condições** do painel **IF** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-122">Under the **Value comparison** node, drag **has changed** to the **IF** pane's **Conditions** label.</span></span>  
  
11. <span data-ttu-id="b1abe-123">No painel **atributos** , clique em um atributo e arraste-o para o rótulo de **atributo selecionar** do painel de **condição de edição** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-123">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span> <span data-ttu-id="b1abe-124">Este atributo não tem nenhum efeito na regra; portanto, selecione qualquer atributo disponível.</span><span class="sxs-lookup"><span data-stu-id="b1abe-124">This attribute has no effect on the rule, so select any available attribute.</span></span>  
  
12. <span data-ttu-id="b1abe-125">No painel **Editar Condição** , na caixa **Grupo de controle de alterações** , digite o número do grupo de controle de alterações que você atribuiu como parte dos pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="b1abe-125">In the **Edit Condition** pane, in the **Change tracking group** box, type the number of the change tracking group that you assigned as part of the prerequisites.</span></span>  
  
13. <span data-ttu-id="b1abe-126">No painel **Editar Condição** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-126">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="b1abe-127">No painel **Componentes** , expanda o nó **Ações** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-127">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="b1abe-128">Clique em uma ação e arraste-a até o rótulo **Ação** do painel **THEN** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-128">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="b1abe-129">No painel **Atributos** , clique em um atributo e arraste-o até o rótulo **Selecionar atributo** do painel **Editar Ação** .</span><span class="sxs-lookup"><span data-stu-id="b1abe-129">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="b1abe-130">No painel **Editar Ação** , preencha os campos necessários.</span><span class="sxs-lookup"><span data-stu-id="b1abe-130">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="b1abe-131">No painel **Editar Ação** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-131">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="b1abe-132">Clique em **Voltar**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-132">Click **Back**.</span></span>  
  
20. <span data-ttu-id="b1abe-133">Opcionalmente, na página **Manutenção de Regra de Negócio** , na linha que contém sua regra de negócio, clique duas vezes em uma célula da coluna **Nome**, **Descrição**ou **Notificação** para atualizar o valor.</span><span class="sxs-lookup"><span data-stu-id="b1abe-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1abe-134">Notificações são enviadas somente para regras que incluem uma ação de validação.</span><span class="sxs-lookup"><span data-stu-id="b1abe-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
21. <span data-ttu-id="b1abe-135">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-135">Click **Publish business rules**.</span></span>  
  
22. <span data-ttu-id="b1abe-136">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="b1abe-137">O status da regra mudará para **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="b1abe-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b1abe-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b1abe-138">Next Steps</span></span>  
  
-   <span data-ttu-id="b1abe-139">Aplique regras de negócio a dados seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b1abe-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="b1abe-140">Validar membros específicos em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b1abe-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="b1abe-141">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b1abe-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1abe-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1abe-142">See Also</span></span>  
 <span data-ttu-id="b1abe-143">[Adicionar atributos a um grupo de Controle de Alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b1abe-143">[Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span></span>  
 [<span data-ttu-id="b1abe-144">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b1abe-144">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
