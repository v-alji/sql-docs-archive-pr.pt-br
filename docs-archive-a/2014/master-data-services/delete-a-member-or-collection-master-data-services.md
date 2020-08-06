---
title: Excluir um membro ou coleção (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], deleting
- leaf members [Master Data Services], deleting
- deleting members [Master Data Services]
- members [Master Data Services], deleting
- consolidated members [Master Data Services], deleting
ms.assetid: 519130a7-4226-4d71-9124-d2ee0ce7e5bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9b248750c0e755c3fc9e32d45068c754e64957b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678826"
---
# <a name="delete-a-member-or-collection-master-data-services"></a><span data-ttu-id="853f6-102">Excluir um membro ou uma coleção (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="853f6-102">Delete a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="853f6-103">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], exclua um membro ou coleção quando não precisar mais dele.</span><span class="sxs-lookup"><span data-stu-id="853f6-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], delete a member or collection when you no longer need it.</span></span> <span data-ttu-id="853f6-104">Se você quiser excluir membros em massa, use o processo de preparo.</span><span class="sxs-lookup"><span data-stu-id="853f6-104">If you want to delete members in bulk, use the staging process instead.</span></span> <span data-ttu-id="853f6-105">Para obter mais informações, consulte [desativar ou excluir membros usando o processo de preparo &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="853f6-105">For more information, see [Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="853f6-106">Você não poderá excluir um membro se ele for usado como um valor de atributo baseado em domínio de outro membro.</span><span class="sxs-lookup"><span data-stu-id="853f6-106">You cannot delete a member if it is used as a domain-based attribute value for another member.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="853f6-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="853f6-107">Prerequisites</span></span>  
 <span data-ttu-id="853f6-108">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="853f6-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="853f6-109">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="853f6-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="853f6-110">Para membros, você deve ter, no mínimo, a permissão **Atualizar** para o objeto de modelo folha do qual você está excluindo um membro.</span><span class="sxs-lookup"><span data-stu-id="853f6-110">For members, you must have a minimum of **Update** permission to the leaf model object you are deleting a member from.</span></span>  
  
-   <span data-ttu-id="853f6-111">Para coleções, você deve ter, no mínimo, a permissão de **Atualizar** para o objeto da coleção de folhas que você está excluindo.</span><span class="sxs-lookup"><span data-stu-id="853f6-111">For collections, you must have a minimum of **Update** permission to the leaf collection object you are deleting.</span></span>  
  
### <a name="to-delete-a-member-or-collection"></a><span data-ttu-id="853f6-112">Para excluir um membro ou uma coleção</span><span class="sxs-lookup"><span data-stu-id="853f6-112">To delete a member or collection</span></span>  
  
1.  <span data-ttu-id="853f6-113">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="853f6-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="853f6-114">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="853f6-114">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="853f6-115">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="853f6-115">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="853f6-116">Para excluir:</span><span class="sxs-lookup"><span data-stu-id="853f6-116">To delete:</span></span>  
  
    -   <span data-ttu-id="853f6-117">Um membro folha, na barra de menus, aponte para **Entidades** e clique no nome da entidade que contém o membro.</span><span class="sxs-lookup"><span data-stu-id="853f6-117">A leaf member, from the menu bar, point to **Entities** and click the name of the entity that contains the member.</span></span>  
  
    -   <span data-ttu-id="853f6-118">Um membro consolidado, na barra de menus, aponte para **Hierarquias** e clique no nome da hierarquia que contém o membro.</span><span class="sxs-lookup"><span data-stu-id="853f6-118">A consolidated member, from the menu bar, point to **Hierarchies** and click the name of the hierarchy that contains the member.</span></span> <span data-ttu-id="853f6-119">Em seguida, o nó na hierarquia que contém o membro.</span><span class="sxs-lookup"><span data-stu-id="853f6-119">Then click the node in the hierarchy that contains the member.</span></span>  
  
    -   <span data-ttu-id="853f6-120">Uma coleção, na barra de menus, aponte para **Coleções** e clique no nome da entidade que contém a coleção.</span><span class="sxs-lookup"><span data-stu-id="853f6-120">A collection, from the menu bar, point to **Collections** and click the name of the entity that contains the collection.</span></span>  
  
5.  <span data-ttu-id="853f6-121">Na grade, clique na linha do membro ou coleção que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="853f6-121">In the grid, click the row of the member or collection you want to delete.</span></span>  
  
6.  <span data-ttu-id="853f6-122">Clique **Excluir Membro**, **Excluir**ou **Excluir Coleção**.</span><span class="sxs-lookup"><span data-stu-id="853f6-122">Click **Delete Member**, **Delete**, or **Delete Collection**.</span></span>  
  
7.  <span data-ttu-id="853f6-123">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="853f6-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="853f6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="853f6-124">See Also</span></span>  
 <span data-ttu-id="853f6-125">[Reativar um membro ou uma coleção &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="853f6-125">[Reactivate a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="853f6-126">[Membros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="853f6-126">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="853f6-127">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="853f6-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
