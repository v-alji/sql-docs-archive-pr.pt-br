---
title: Adicionar atributos a um grupo de controle de alterações (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c8a13dad3ca886668c96c1886f8cd238d9adad9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583143"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a><span data-ttu-id="c0042-102">Adicionar atributos a um grupo de controle de alterações (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c0042-102">Add Attributes to a Change Tracking Group (Master Data Services)</span></span>
  <span data-ttu-id="c0042-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], adicione atributos ao grupo de controle de alterações quando desejar controlar as alterações feitas nos valores dos atributos.</span><span class="sxs-lookup"><span data-stu-id="c0042-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add attributes to a change tracking group when you want to track changes to the attribute's values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0042-104">Depois de adicionar um atributo a um grupo de controle de alterações, quando os valores do atributo forem alterados, o atributo será sinalizado como alterado no banco de dados [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0042-104">After you add an attribute to a change tracking group, when values for the attribute change, the attribute is flagged as changed in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="c0042-105">Crie uma regra de negócio para executar uma ação com base na alteração.</span><span class="sxs-lookup"><span data-stu-id="c0042-105">Create a business rule to take action based on the change.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c0042-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c0042-106">Prerequisites</span></span>  
 <span data-ttu-id="c0042-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="c0042-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c0042-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="c0042-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c0042-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="c0042-109">You must be a model administrator.</span></span> <span data-ttu-id="c0042-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c0042-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c0042-111">Os atributos devem existir para que possam ser adicionados ao grupo de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="c0042-111">Attributes must exist to add to the change tracking group.</span></span> <span data-ttu-id="c0042-112">Para obter mais informações, veja [Criar um atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c0042-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a><span data-ttu-id="c0042-113">Para adicionar atributos a um grupo de controle de alterações</span><span class="sxs-lookup"><span data-stu-id="c0042-113">To add attributes to a change tracking group</span></span>  
  
1.  <span data-ttu-id="c0042-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="c0042-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c0042-115">Na página **Gerenciador de modelos** , na barra de menus, aponte para **gerenciar** e clique em **entidades**.</span><span class="sxs-lookup"><span data-stu-id="c0042-115">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="c0042-116">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="c0042-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c0042-117">Selecione a linha correspondente à entidade para a qual você deseja controlar os valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="c0042-117">Select the row for the entity that you want to track attribute values for.</span></span>  
  
5.  <span data-ttu-id="c0042-118">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="c0042-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="c0042-119">Na página **Editar Entidade** :</span><span class="sxs-lookup"><span data-stu-id="c0042-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="c0042-120">Se o atributo for para membros folha, no painel **atributos de folha** , selecione o atributo e clique em **Editar atributo folha**.</span><span class="sxs-lookup"><span data-stu-id="c0042-120">If the attribute is for leaf members, in the **Leaf attributes** pane, select the attribute and click **Edit leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="c0042-121">Se o atributo for para membros consolidados, no painel **atributos consolidados** , selecione o atributo e clique em **Editar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="c0042-121">If the attribute is for consolidated members, in the **Consolidated attributes** pane, select the attribute and click **Edit consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="c0042-122">Se o atributo for para coleções, no painel **atributos da coleção** , selecione o atributo e clique em **Editar atributo de coleção**.</span><span class="sxs-lookup"><span data-stu-id="c0042-122">If the attribute is for collections, in the **Collection attributes** pane, select the attribute and click **Edit collection attribute**.</span></span>  
  
7.  <span data-ttu-id="c0042-123">Marque a caixa de seleção **Habilitar controle de alterações** .</span><span class="sxs-lookup"><span data-stu-id="c0042-123">Select the **Enable change tracking** check box.</span></span>  
  
8.  <span data-ttu-id="c0042-124">Na caixa **Grupo de controle de alterações** , digite um número para o grupo.</span><span class="sxs-lookup"><span data-stu-id="c0042-124">In the **Change tracking group** box, type a number for the group.</span></span>  
  
9. <span data-ttu-id="c0042-125">Clique em **Salvar atributo**.</span><span class="sxs-lookup"><span data-stu-id="c0042-125">Click **Save attribute**.</span></span>  
  
10. <span data-ttu-id="c0042-126">Na página **Manutenção da Entidade** , clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="c0042-126">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
11. <span data-ttu-id="c0042-127">Repita esse procedimento para todos os atributos que você deseja incluir no grupo.</span><span class="sxs-lookup"><span data-stu-id="c0042-127">Repeat this procedure for all attributes you want to include in the group.</span></span> <span data-ttu-id="c0042-128">Use o mesmo número de grupo de controle de alterações para cada atributo no grupo.</span><span class="sxs-lookup"><span data-stu-id="c0042-128">Use the same change tracking group number for each attribute in the group.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c0042-129">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c0042-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="c0042-130">Iniciar ações com base em alterações no valor do atributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c0042-130">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0042-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0042-131">See Also</span></span>  
 <span data-ttu-id="c0042-132">[Criar um atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c0042-132">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="c0042-133">Criar um atributo baseado em domínio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c0042-133">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
