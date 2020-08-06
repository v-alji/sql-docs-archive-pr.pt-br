---
title: Habilitar uma entidade para hierarquias explícitas e coleções (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], enabling for collections
- entities [Master Data Services], enabling for explicit hierarchies
ms.assetid: 380e77e5-ad60-43d4-9605-34a84525f5dd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a8129b3f67f050603f85ffb782a9dd209cb303fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678814"
---
# <a name="enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services"></a><span data-ttu-id="f6cf1-102">Habilitar uma entidade para hierarquias explícitas e coleções (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f6cf1-102">Enable an Entity for Explicit Hierarchies and Collections (Master Data Services)</span></span>
  <span data-ttu-id="f6cf1-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], habilite uma entidade para hierarquias explícitas e coleções, de modo que você possa criar hierarquias explícitas e coleções para a entidade.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], enable an entity for explicit hierarchies and collections so that you can create explicit hierarchies and collections for the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6cf1-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f6cf1-104">Prerequisites</span></span>  
 <span data-ttu-id="f6cf1-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="f6cf1-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f6cf1-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="f6cf1-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="f6cf1-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-107">You must be a model administrator.</span></span> <span data-ttu-id="f6cf1-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6cf1-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f6cf1-109">Uma entidade deve existir.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-109">An entity must exist.</span></span> <span data-ttu-id="f6cf1-110">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6cf1-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-enable-an-entity-for-explicit-hierarchies-and-collections"></a><span data-ttu-id="f6cf1-111">Para habilitar uma entidade para hierarquias explícitas e coleções</span><span class="sxs-lookup"><span data-stu-id="f6cf1-111">To enable an entity for explicit hierarchies and collections</span></span>  
  
1.  <span data-ttu-id="f6cf1-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="f6cf1-113">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="f6cf1-114">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="f6cf1-115">Selecione a linha correspondente à entidade que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-115">Select the row for the entity that you want to update.</span></span>  
  
5.  <span data-ttu-id="f6cf1-116">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="f6cf1-117">Na lista **habilitar hierarquias explícitas e coleções** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-117">From the **Enable explicit hierarchies and collections** list, select **Yes**.</span></span>  
  
7.  <span data-ttu-id="f6cf1-118">Na caixa **nome da hierarquia explícita** , digite um nome para uma hierarquia explícita.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-118">In the **Explicit hierarchy name** box, type a name for an explicit hierarchy.</span></span>  
  
8.  <span data-ttu-id="f6cf1-119">Opcionalmente, desmarque a caixa de seleção **Hierarquia obrigatória** para criar a hierarquia como não obrigatória.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-119">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="f6cf1-120">Clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-120">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f6cf1-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f6cf1-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="f6cf1-122">Criar uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f6cf1-122">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
-   [<span data-ttu-id="f6cf1-123">Criar uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f6cf1-123">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6cf1-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6cf1-124">See Also</span></span>  
 <span data-ttu-id="f6cf1-125">[Entidades &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6cf1-125">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="f6cf1-126">[Hierarquias explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6cf1-126">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="f6cf1-127">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f6cf1-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
