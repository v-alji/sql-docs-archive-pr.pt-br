---
title: Criar uma coleção (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f76171b4fd9b07f751d4f919011a443253fbe31b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681725"
---
# <a name="create-a-collection-master-data-services"></a><span data-ttu-id="8bf95-102">Criar uma coleção (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8bf95-102">Create a Collection (Master Data Services)</span></span>
  <span data-ttu-id="8bf95-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie uma coleção quando desejar criar listas simples de membros folha e consolidados.</span><span class="sxs-lookup"><span data-stu-id="8bf95-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a collection when you want to create flat lists of leaf and consolidated members.</span></span> <span data-ttu-id="8bf95-104">Coleções não precisam incluir todos os membros da entidade.</span><span class="sxs-lookup"><span data-stu-id="8bf95-104">Collections do not need to include all members from the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8bf95-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8bf95-105">Prerequisites</span></span>  
 <span data-ttu-id="8bf95-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="8bf95-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8bf95-107">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="8bf95-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="8bf95-108">Você deve ter, no mínimo, a permissão **Atualizar** no objeto do modelo de coleção da entidade.</span><span class="sxs-lookup"><span data-stu-id="8bf95-108">You must have a minimum of **Update** permission to the collection model object for the entity.</span></span>  
  
-   <span data-ttu-id="8bf95-109">A entidade deve estar habilitada para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="8bf95-109">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="8bf95-110">Para obter mais informações, consulte [habilitar uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8bf95-110">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-a-collection"></a><span data-ttu-id="8bf95-111">Para criar uma coleção</span><span class="sxs-lookup"><span data-stu-id="8bf95-111">To create a collection</span></span>  
  
1.  <span data-ttu-id="8bf95-112">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="8bf95-112">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="8bf95-113">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="8bf95-113">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="8bf95-114">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="8bf95-114">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="8bf95-115">Na barra de menus, aponte para **Coleções** e clique em *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="8bf95-115">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="8bf95-116">Clique em **Adicionar coleção**.</span><span class="sxs-lookup"><span data-stu-id="8bf95-116">Click **Add collection**.</span></span>  
  
6.  <span data-ttu-id="8bf95-117">Na guia **Detalhes** , na caixa **Nome** , digite um nome para a coleção.</span><span class="sxs-lookup"><span data-stu-id="8bf95-117">On the **Details** tab, in the **Name** box, type a name for the collection.</span></span>  
  
7.  <span data-ttu-id="8bf95-118">Na caixa **Código** , digite um código exclusivo para a coleção.</span><span class="sxs-lookup"><span data-stu-id="8bf95-118">In the **Code** box, type a unique code for the collection.</span></span>  
  
8.  <span data-ttu-id="8bf95-119">Opcionalmente, na caixa **Descrição** , digite uma descrição para a coleção.</span><span class="sxs-lookup"><span data-stu-id="8bf95-119">Optionally, in the **Description** box, type a description for the collection.</span></span>  
  
9. <span data-ttu-id="8bf95-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8bf95-120">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8bf95-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8bf95-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="8bf95-122">Adicionar membros a uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8bf95-122">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="8bf95-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8bf95-123">See Also</span></span>  
 <span data-ttu-id="8bf95-124">[Coleções &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8bf95-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 <span data-ttu-id="8bf95-125">[Excluir um membro ou uma coleção &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8bf95-125">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 [<span data-ttu-id="8bf95-126">Criar uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8bf95-126">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
