---
title: Criar um grupo de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fbd95869082ea0a73f3abea092163c4705e4da5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683577"
---
# <a name="create-an-attribute-group-master-data-services"></a><span data-ttu-id="feee9-102">Criar um grupo de atributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="feee9-102">Create an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="feee9-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie grupos de atributos quando você desejar exibir atributos em guias individuais na grade do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="feee9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create attribute groups when you want to display attributes on individual tabs in the **Explorer** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="feee9-104">Quando você criar um grupo de atributos, ele será ocultado automaticamente de todos os usuários, exceto daquele que o criou.</span><span class="sxs-lookup"><span data-stu-id="feee9-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="feee9-105">Para obter mais informações sobre como tornar o grupo visível, consulte [Tornar um grupo de atributos visível para os usuários &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="feee9-105">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="feee9-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="feee9-106">Prerequisites</span></span>  
 <span data-ttu-id="feee9-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="feee9-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="feee9-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="feee9-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="feee9-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="feee9-109">You must be a model administrator.</span></span> <span data-ttu-id="feee9-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="feee9-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="feee9-111">Pelo menos um atributo deve existir.</span><span class="sxs-lookup"><span data-stu-id="feee9-111">At least one attribute must exist.</span></span> <span data-ttu-id="feee9-112">Para obter mais informações, veja [Criar um atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="feee9-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-create-an-attribute-group"></a><span data-ttu-id="feee9-113">Para criar um grupo de atributo</span><span class="sxs-lookup"><span data-stu-id="feee9-113">To create an attribute group</span></span>  
  
1.  <span data-ttu-id="feee9-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="feee9-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="feee9-115">Na página **exibição de modelo** , na barra de menus, aponte para **gerenciar** e clique em **grupos de atributos**.</span><span class="sxs-lookup"><span data-stu-id="feee9-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="feee9-116">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="feee9-116">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="feee9-117">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="feee9-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="feee9-118">Clique em **Grupos de Folha**, **Grupos Consolidados**ou **Grupos de Coleção** para criar um grupo de atributos de membros folha, membros consolidados ou coleções, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="feee9-118">Click **Leaf Groups**, **Consolidated Groups**, or **Collection Groups** to create an attribute group of leaf members, consolidated members, or collections respectively.</span></span>  
  
6.  <span data-ttu-id="feee9-119">Clique em **Adicionar grupo de atributos**.</span><span class="sxs-lookup"><span data-stu-id="feee9-119">Click **Add attribute group**.</span></span>  
  
7.  <span data-ttu-id="feee9-120">Na caixa **nome do grupo folha** , digite um nome para o grupo.</span><span class="sxs-lookup"><span data-stu-id="feee9-120">In the **Leaf group name** box, type a name for the group.</span></span> <span data-ttu-id="feee9-121">Esse é o nome exibido na guia no **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="feee9-121">This is the name displayed on the tab in **Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="feee9-122">Se você selecionou **grupos consolidados** ou **grupos de coleta** na etapa 5, essa caixa será o **nome do grupo consolidado** ou o nome do grupo de **coleta**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="feee9-122">If you selected **Consolidated Groups** or **Collection Groups** in step 5, this box is **Consolidated group name** or **Collection group name**, respectively.</span></span>  
  
8.  <span data-ttu-id="feee9-123">Clique em **Salvar grupo**.</span><span class="sxs-lookup"><span data-stu-id="feee9-123">Click **Save group**.</span></span>  
  
9. <span data-ttu-id="feee9-124">Expanda a pasta para o grupo.</span><span class="sxs-lookup"><span data-stu-id="feee9-124">Expand the folder for the group.</span></span>  
  
10. <span data-ttu-id="feee9-125">Clique em **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="feee9-125">Click **Attributes**.</span></span>  
  
11. <span data-ttu-id="feee9-126">Clique em **editar item selecionado**.</span><span class="sxs-lookup"><span data-stu-id="feee9-126">Click **Edit selected item**.</span></span>  
  
12. <span data-ttu-id="feee9-127">Clique em atributos na caixa **disponível** e clique na seta **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="feee9-127">Click attributes in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="feee9-128">Para adicionar tudo, clique na seta **Adicionar Tudo** .</span><span class="sxs-lookup"><span data-stu-id="feee9-128">To add all, click the **Add All** arrow.</span></span>  
  
13. <span data-ttu-id="feee9-129">Opcionalmente, clique nas setas para **cima** e para **baixo** para alterar a ordem da esquerda para a direita dos atributos.</span><span class="sxs-lookup"><span data-stu-id="feee9-129">Optionally, click the **Up** and **Down** arrows to change the left-to-right order of the attributes.</span></span>  
  
14. <span data-ttu-id="feee9-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="feee9-130">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="feee9-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="feee9-131">Next Steps</span></span>  
  
-   [<span data-ttu-id="feee9-132">Tornar um grupo de atributos visível para os usuários &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="feee9-132">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="feee9-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="feee9-133">See Also</span></span>  
 <span data-ttu-id="feee9-134">[Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="feee9-134">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="feee9-135">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="feee9-135">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="feee9-136">[Alterar um nome de grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="feee9-136">[Change an Attribute Group Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span></span>  
 <span data-ttu-id="feee9-137">[Excluir um grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="feee9-137">[Delete an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span></span>  
 <span data-ttu-id="feee9-138">[Permissões de folha &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="feee9-138">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="feee9-139">Permissões consolidadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="feee9-139">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
