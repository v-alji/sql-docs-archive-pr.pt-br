---
title: Criar uma hierarquia explícita (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating explicit hierarchies [Master Data Services]
- explicit hierarchies, creating
ms.assetid: ba768393-6990-4eda-8cb0-d58cb3cfc2e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aebf95e68f210fe5a573aed092231670c10fa188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575884"
---
# <a name="create-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="e434d-102">Criar uma hierarquia explícita (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e434d-102">Create an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="e434d-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie uma hierarquia explícita quando precisar de uma hierarquia desbalanceada em que os membros podem existir em qualquer nível.</span><span class="sxs-lookup"><span data-stu-id="e434d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an explicit hierarchy when you need a ragged hierarchy in which members can exist at any level.</span></span> <span data-ttu-id="e434d-104">As hierarquias explícitas contêm membros de uma única entidade.</span><span class="sxs-lookup"><span data-stu-id="e434d-104">Explicit hierarchies contain members from a single entity.</span></span>  
  
 <span data-ttu-id="e434d-105">Depois que você criar uma hierarquia explícita, pode adicionar os membros a ela na área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="e434d-105">After you create an explicit hierarchy, you can add members to it in the **Explorer** functional area.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e434d-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e434d-106">Prerequisites</span></span>  
 <span data-ttu-id="e434d-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="e434d-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e434d-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="e434d-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="e434d-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="e434d-109">You must be a model administrator.</span></span> <span data-ttu-id="e434d-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e434d-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e434d-111">A entidade deve estar habilitada para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="e434d-111">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="e434d-112">Para obter mais informações, consulte [habilitar uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e434d-112">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-an-explicit-hierarchy"></a><span data-ttu-id="e434d-113">Para criar uma hierarquia explícita</span><span class="sxs-lookup"><span data-stu-id="e434d-113">To create an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="e434d-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="e434d-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="e434d-115">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="e434d-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="e434d-116">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="e434d-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="e434d-117">Selecione a linha correspondente à entidade para a qual você deseja criar uma hierarquia explícita.</span><span class="sxs-lookup"><span data-stu-id="e434d-117">Select the row for the entity that you want to create an explicit hierarchy for.</span></span>  
  
5.  <span data-ttu-id="e434d-118">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="e434d-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="e434d-119">Na página **Editar entidade** , no painel **hierarquias explícitas** , clique em **Adicionar Hierarquia explícita**.</span><span class="sxs-lookup"><span data-stu-id="e434d-119">On the **Edit Entity** page, in the **Explicit hierarchies** pane, click **Add explicit hierarchy**.</span></span>  
  
7.  <span data-ttu-id="e434d-120">Na página **Adicionar Hierarquia explícita** , na caixa **nome da hierarquia explícita** , digite um nome para a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="e434d-120">On the **Add Explicit Hierarchy** page, in the **Explicit hierarchy name** box, type a name for the hierarchy.</span></span>  
  
8.  <span data-ttu-id="e434d-121">Opcionalmente, desmarque a caixa de seleção **Hierarquia obrigatória** para criar a hierarquia como não obrigatória.</span><span class="sxs-lookup"><span data-stu-id="e434d-121">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span> <span data-ttu-id="e434d-122">Para obter mais informações sobre tipos de hierarquia, consulte [Hierarquias explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e434d-122">For more information about hierarchy types, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="e434d-123">Clique em **salvar hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="e434d-123">Click **Save hierarchy**.</span></span>  
  
10. <span data-ttu-id="e434d-124">Na página **Editar entidade** , clique em **salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="e434d-124">On the **Edit Entity** page, click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e434d-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e434d-125">Next Steps</span></span>  
  
-   [<span data-ttu-id="e434d-126">Criar um membro consolidado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e434d-126">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)  
  
-   [<span data-ttu-id="e434d-127">Mover membros dentro de uma hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e434d-127">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="e434d-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e434d-128">See Also</span></span>  
 <span data-ttu-id="e434d-129">[Hierarquias explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e434d-129">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="e434d-130">[Hierarquias derivadas com limites explícitos &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e434d-130">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="e434d-131">Alterar o nome de uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e434d-131">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)  
  
  
