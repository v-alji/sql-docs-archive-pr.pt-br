---
title: Criar um membro consolidado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating consolidated members [Master Data Services]
- members [Master Data Services], creating consolidated members
- consolidated members [Master Data Services], creating
ms.assetid: 431ab2d2-5517-4372-9980-142b05427c08
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c41673f6f3bf1f4de2a831ecd659321b273b6af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681720"
---
# <a name="create-a-consolidated-member-master-data-services"></a><span data-ttu-id="465aa-102">Criar um membro consolidado (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="465aa-102">Create a Consolidated Member (Master Data Services)</span></span>
  <span data-ttu-id="465aa-103">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], crie um membro consolidado quando você desejar um nó pai para uma hierarquia explícita.</span><span class="sxs-lookup"><span data-stu-id="465aa-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a consolidated member when you want a parent node for an explicit hierarchy.</span></span> <span data-ttu-id="465aa-104">Os membros consolidados podem ter seus próprios atributos.</span><span class="sxs-lookup"><span data-stu-id="465aa-104">Consolidated members can have their own attributes.</span></span> <span data-ttu-id="465aa-105">Eles são usados para agrupamento.</span><span class="sxs-lookup"><span data-stu-id="465aa-105">They are used for grouping.</span></span> <span data-ttu-id="465aa-106">Conforme mostrado no exemplo a seguir, os membros consolidados podem ser usados para grupos de contas que têm contas neles.</span><span class="sxs-lookup"><span data-stu-id="465aa-106">As shown in the following example, consolidated members can be used for account groups that have accounts under them.</span></span>

 <span data-ttu-id="465aa-107">![Membros consolidados do MDS](../../2014/master-data-services/media/mds-consolidated-members.png "Membros consolidados do MDS")</span><span class="sxs-lookup"><span data-stu-id="465aa-107">![MDS Consolidated Members](../../2014/master-data-services/media/mds-consolidated-members.png "MDS Consolidated Members")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="465aa-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="465aa-108">Prerequisites</span></span>
 <span data-ttu-id="465aa-109">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="465aa-109">To perform this procedure:</span></span>

-   <span data-ttu-id="465aa-110">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="465aa-110">You must have permission to access the **Explorer** functional area.</span></span>

-   <span data-ttu-id="465aa-111">Você deve ter, no mínimo, a permissão **Atualizar** para o objeto de modelo consolidado para a entidade a qual você está adicionando um membro.</span><span class="sxs-lookup"><span data-stu-id="465aa-111">You must have a minimum of **Update** permission to the consolidated model object for the entity you are adding a member to.</span></span>

### <a name="to-create-a-consolidated-member"></a><span data-ttu-id="465aa-112">Para criar um membro consolidado</span><span class="sxs-lookup"><span data-stu-id="465aa-112">To create a consolidated member</span></span>

1.  <span data-ttu-id="465aa-113">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="465aa-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>

2.  <span data-ttu-id="465aa-114">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="465aa-114">From the **Version** list, select a version.</span></span>

3.  <span data-ttu-id="465aa-115">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="465aa-115">Click **Explorer**.</span></span>

4.  <span data-ttu-id="465aa-116">Na barra de menus, aponte para **Hierarquias** e clique no nome da hierarquia à qual você deseja adicionar um membro consolidado.</span><span class="sxs-lookup"><span data-stu-id="465aa-116">From the menu bar, point to **Hierarchies** and click the name of the hierarchy you want to add a consolidated member to.</span></span>

5.  <span data-ttu-id="465aa-117">Acima da grade, selecione a opção **Membros consolidados** ou **Todos os membros consolidados da hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="465aa-117">Above the grid, select either the **Consolidated members** or the **All consolidated members in hierarchy** option.</span></span>

6.  <span data-ttu-id="465aa-118">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="465aa-118">Click **Add**.</span></span>

7.  <span data-ttu-id="465aa-119">No painel à direita, preencha os campos.</span><span class="sxs-lookup"><span data-stu-id="465aa-119">In the pane on the right, complete the fields.</span></span>

8.  <span data-ttu-id="465aa-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="465aa-120">Optional.</span></span> <span data-ttu-id="465aa-121">Na caixa **Anotações** , digite um comentário sobre por que o membro foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="465aa-121">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="465aa-122">Todos os usuários que têm acesso ao membro podem exibir a anotação.</span><span class="sxs-lookup"><span data-stu-id="465aa-122">All users who have access to the member can view the annotation.</span></span>

9. <span data-ttu-id="465aa-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="465aa-123">Click **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="465aa-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="465aa-124">Next Steps</span></span>

-   [<span data-ttu-id="465aa-125">Mover membros dentro de uma hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="465aa-125">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](move-members-within-a-hierarchy-master-data-services.md)

## <a name="see-also"></a><span data-ttu-id="465aa-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="465aa-126">See Also</span></span>
 <span data-ttu-id="465aa-127">[Crie uma hierarquia explícita &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [criar um membro folha &#40;Master Data Services](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [carregar ou atualizar Membros em&#41;usando os membros do processo de preparo](add-update-and-delete-data-master-data-services.md) [Master Data Services](../../2014/master-data-services/members-master-data-services.md) &#40;[hierarquias explícitas Master Data Services](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="465aa-127">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [Create a Leaf Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)</span></span>


