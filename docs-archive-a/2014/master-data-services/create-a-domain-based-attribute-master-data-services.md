---
title: Criar um atributo baseado em domínio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], creating
- creating domain-based attributes [Master Data Services]
- attributes [Master Data Services], creating domain-based attributes
ms.assetid: 11c31c9f-e6cc-47b7-b76a-d691f84c93c6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 51c0f44bb76ae2ad4c25987ed5e5ee144a18c739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570737"
---
# <a name="create-a-domain-based-attribute-master-data-services"></a><span data-ttu-id="f21bc-102">Criar um atributo baseado em domínio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f21bc-102">Create a Domain-Based Attribute (Master Data Services)</span></span>
  <span data-ttu-id="f21bc-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie um atributo baseado em domínio para popular os valores de um atributo com membros de uma entidade.</span><span class="sxs-lookup"><span data-stu-id="f21bc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a domain-based attribute to populate an attribute's values with members from an entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f21bc-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f21bc-104">Prerequisites</span></span>  
 <span data-ttu-id="f21bc-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="f21bc-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f21bc-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="f21bc-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="f21bc-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-107">You must be a model administrator.</span></span> <span data-ttu-id="f21bc-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f21bc-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f21bc-109">Uma entidade deve existir para ser usada como a origem dos valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-109">An entity must exist to use as the source of the attribute values.</span></span> <span data-ttu-id="f21bc-110">Por exemplo, para criar um atributo baseado em domínio com base na entidade Color, você deve primeiro criar a entidade Color.</span><span class="sxs-lookup"><span data-stu-id="f21bc-110">For example, to create a domain-based attribute based on the Color entity, you must first create the Color entity.</span></span> <span data-ttu-id="f21bc-111">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f21bc-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f21bc-112">Uma entidade deve existir para que se possa criar o atributo para ela.</span><span class="sxs-lookup"><span data-stu-id="f21bc-112">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="f21bc-113">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f21bc-113">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-domain-based-attribute"></a><span data-ttu-id="f21bc-114">Para criar um atributo baseado em domínio</span><span class="sxs-lookup"><span data-stu-id="f21bc-114">To create a domain-based attribute</span></span>  
  
1.  <span data-ttu-id="f21bc-115">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="f21bc-116">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-116">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="f21bc-117">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-117">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="f21bc-118">Selecione a linha correspondente à entidade para a qual você deseja criar um atributo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-118">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="f21bc-119">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-119">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="f21bc-120">Na página **Editar Entidade** :</span><span class="sxs-lookup"><span data-stu-id="f21bc-120">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="f21bc-121">Se o atributo for para membros folha, no painel **Atributos de membro folha** , clique em **Adicionar atributo folha**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-121">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="f21bc-122">Se o atributo for para membros consolidados, no painel **Atributo de membro consolidado** , clique em **Adicionar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-122">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="f21bc-123">Se o atributo for para coleções, no painel **Atributos da coleção** , clique em **Adicionar atributo de coleção**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-123">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="f21bc-124">Na página **Adicionar atributo** , selecione a opção **baseado em domínio** .</span><span class="sxs-lookup"><span data-stu-id="f21bc-124">On the **Add Attribute** page, select the **Domain-based** option.</span></span>  
  
8.  <span data-ttu-id="f21bc-125">Na caixa **Nome** , digite um nome para o atributo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-125">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="f21bc-126">Ele não precisa ser o mesmo nome da entidade que você usa para a origem dos valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-126">It does not have to be the same name as the entity that you use for the source of the attribute values.</span></span>  
  
9. <span data-ttu-id="f21bc-127">Na caixa **Exibir largura em pixels** , digite a largura da coluna de atributo a ser exibida na grade do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="f21bc-127">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="f21bc-128">Na lista **entidade** , escolha a entidade a ser usada para popular os valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="f21bc-128">From the **Entity** list, choose the entity to be used to populate the attribute values.</span></span>  
  
11. <span data-ttu-id="f21bc-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f21bc-129">Optional.</span></span> <span data-ttu-id="f21bc-130">Selecione **Enable change tracking** para acompanhar as alterações feitas em grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="f21bc-130">Select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="f21bc-131">Para obter mais informações, consulte [Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f21bc-131">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="f21bc-132">Clique em **Salvar atributo**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-132">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="f21bc-133">Na página **Manutenção da Entidade** , clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="f21bc-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21bc-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f21bc-134">See Also</span></span>  
 <span data-ttu-id="f21bc-135">[Atributos baseados em domínio &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f21bc-135">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="f21bc-136">[Criar uma hierarquia derivada &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f21bc-136">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 <span data-ttu-id="f21bc-137">[Alterar um nome de atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f21bc-137">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 [<span data-ttu-id="f21bc-138">Excluir um atributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f21bc-138">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)  
  
  
