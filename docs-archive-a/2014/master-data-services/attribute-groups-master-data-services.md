---
title: Grupos de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services]
- attribute groups [Master Data Services], about attribute groups
ms.assetid: 648b3d0b-e15a-45f9-8292-3a54a072e62c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 390b402489799639e66a44992da1e20b0d0c1bbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574766"
---
# <a name="attribute-groups-master-data-services"></a><span data-ttu-id="d2449-102">Grupos de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d2449-102">Attribute Groups (Master Data Services)</span></span>
  <span data-ttu-id="d2449-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], os grupos de atributos ajudam organizar atributos em uma entidade.</span><span class="sxs-lookup"><span data-stu-id="d2449-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], attribute groups help organize attributes in an entity.</span></span> <span data-ttu-id="d2449-104">Quando uma entidade tem muitos atributos, os grupos de atributos melhoram a maneira como uma entidade é exibida no aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2449-104">When an entity has lots of attributes, attribute groups improve the way an entity is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
## <a name="how-attribute-groups-change-the-display"></a><span data-ttu-id="d2449-105">Como os grupos de atributos alteram a exibição</span><span class="sxs-lookup"><span data-stu-id="d2449-105">How Attribute Groups Change the Display</span></span>  
 <span data-ttu-id="d2449-106">Os grupos de atributos são exibidos como guias acima da grade na área funcional **Gerenciador** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2449-106">Attribute groups are displayed as tabs above the grid in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="d2449-107">Quando uma entidade com um grande número de atributos é exibida em uma grade no **Gerenciador**, é necessário rolar para a direita para exibir todos os atributos.</span><span class="sxs-lookup"><span data-stu-id="d2449-107">When an entity has a large number of attributes and you view that entity in a grid in **Explorer**, you must scroll to the right to view all of the attributes.</span></span> <span data-ttu-id="d2449-108">Para impedir esse deslocamento, você pode criar grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="d2449-108">To prevent this scrolling, you can create attribute groups.</span></span>  
  
-   <span data-ttu-id="d2449-109">Os grupos de atributos sempre incluem os atributos Name e Code.</span><span class="sxs-lookup"><span data-stu-id="d2449-109">Attribute groups always include the Name and Code attributes.</span></span>  
  
-   <span data-ttu-id="d2449-110">Cada atributo de uma entidade pode pertencer a um ou mais grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="d2449-110">Each attribute for an entity can belong to one or more attribute groups.</span></span>  
  
-   <span data-ttu-id="d2449-111">Todos os atributos são incluídos automaticamente na guia **Todos os Atributos** no **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="d2449-111">All attributes are automatically included on the **All Attributes** tab in **Explorer**.</span></span>  
  
-   <span data-ttu-id="d2449-112">Não é possível ocultar a guia **Todos os Atributos** .</span><span class="sxs-lookup"><span data-stu-id="d2449-112">There is no way to hide the **All Attributes** tab.</span></span>  
  
 <span data-ttu-id="d2449-113">Os grupos de atributos são adminitrados na área funcional **Administração do Sistema** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2449-113">Attribute groups are administered in the **System Administration** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="show-or-hide-attribute-groups"></a><span data-ttu-id="d2449-114">Mostrar ou ocultar grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="d2449-114">Show or Hide Attribute Groups</span></span>  
 <span data-ttu-id="d2449-115">Quando você criar um grupo de atributos, ele será ocultado automaticamente de todos os usuários, exceto daquele que o criou.</span><span class="sxs-lookup"><span data-stu-id="d2449-115">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="d2449-116">Para obter mais informações sobre como tornar o grupo visível, consulte [Tornar um grupo de atributos visível para os usuários &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d2449-116">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
 <span data-ttu-id="d2449-117">Se você desejar ocultar um atributo específico em um grupo, poderá atribuir a permissão **Negar** ao atributo.</span><span class="sxs-lookup"><span data-stu-id="d2449-117">If you want to hide a specific attribute within a group, you can assign **Deny** permission to the attribute.</span></span> <span data-ttu-id="d2449-118">Para obter mais informações, consulte [Permissões de folha &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) ou [Permissões consolidadas &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d2449-118">For more information, see [Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) or [Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d2449-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d2449-119">Related Tasks</span></span>  
  
|<span data-ttu-id="d2449-120">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="d2449-120">Task Description</span></span>|<span data-ttu-id="d2449-121">Tópico</span><span class="sxs-lookup"><span data-stu-id="d2449-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="d2449-122">Criar um novo grupo de atributos e adicionar atributos a ele.</span><span class="sxs-lookup"><span data-stu-id="d2449-122">Create a new attribute group and add attributes to it.</span></span>|[<span data-ttu-id="d2449-123">Criar um grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2449-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)|  
|<span data-ttu-id="d2449-124">Tornar um grupo de atributos visível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="d2449-124">Make an attribute group visible to users.</span></span>|[<span data-ttu-id="d2449-125">Tornar um grupo de atributos visível para os usuários &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2449-125">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)|  
|<span data-ttu-id="d2449-126">Alterar o nome de um grupo de atributos existente.</span><span class="sxs-lookup"><span data-stu-id="d2449-126">Change the name of an existing attribute group.</span></span>|[<span data-ttu-id="d2449-127">Alterar o nome de um grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2449-127">Change an Attribute Group Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)|  
|<span data-ttu-id="d2449-128">Excluir um grupo de atributos existente.</span><span class="sxs-lookup"><span data-stu-id="d2449-128">Delete an existing attribute group.</span></span>|[<span data-ttu-id="d2449-129">Excluir um grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2449-129">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="d2449-130">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="d2449-130">Related Content</span></span>  
  
-   [<span data-ttu-id="d2449-131">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2449-131">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
