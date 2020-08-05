---
title: Mover membros dentro de uma hierarquia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], moving members
- explicit hierarchies, moving members
- derived hierarchies, moving members
- members [Master Data Services], moving
ms.assetid: 049c9a15-89c1-478c-8438-028fffc9e187
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 37167f76b965197dbf8e37e365778395ec640d38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572593"
---
# <a name="move-members-within-a-hierarchy-master-data-services"></a><span data-ttu-id="44335-102">Mover membros dentro de uma hierarquia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="44335-102">Move Members within a Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="44335-103">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], mova os membros dentro de uma hierarquia para alterar seu local ou atribuição pai.</span><span class="sxs-lookup"><span data-stu-id="44335-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], move members within a hierarchy to change their location or parent assignment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44335-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="44335-104">Prerequisites</span></span>  
 <span data-ttu-id="44335-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="44335-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="44335-106">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="44335-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="44335-107">Para hierarquias explícitas, você deve ter, no mínimo, a permissão **Atualizar** para a entidade.</span><span class="sxs-lookup"><span data-stu-id="44335-107">For explicit hierarchies, you must have a minimum of **Update** permission to the entity.</span></span>  
  
-   <span data-ttu-id="44335-108">Para hierarquias derivadas, você deve ter um mínimo de **atualização** para o modelo e para qualquer atributo baseado em domínio usado na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="44335-108">For derived hierarchies, you must have a minimum of **Update** to the model and to any domain-based attributes used in the hierarchy.</span></span>  
  
### <a name="to-move-members-within-a-hierarchy"></a><span data-ttu-id="44335-109">Para mover membros dentro de uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="44335-109">To move members within a hierarchy</span></span>  
  
1.  <span data-ttu-id="44335-110">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="44335-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="44335-111">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="44335-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="44335-112">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="44335-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="44335-113">Na barra de menus, aponte para **hierarquias** e clique em *hierarchy_name*.</span><span class="sxs-lookup"><span data-stu-id="44335-113">From the menu bar, point to **Hierarchies** and click *hierarchy_name*.</span></span>  
  
5.  <span data-ttu-id="44335-114">No painel **hierarquia** , em que a hierarquia é exibida em uma estrutura de árvore, clique na caixa de seleção de cada membro que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="44335-114">In the **Hierarchy** pane, where the hierarchy is displayed in a tree structure, click the check box for each member you want to move.</span></span>  
  
6.  <span data-ttu-id="44335-115">Na parte superior do painel **hierarquia** , clique em **recortar**.</span><span class="sxs-lookup"><span data-stu-id="44335-115">At the top of the **Hierarchy** pane, click **Cut**.</span></span>  
  
7.  <span data-ttu-id="44335-116">No painel **hierarquia** , clique na caixa de seleção do membro para o qual você deseja mover os membros.</span><span class="sxs-lookup"><span data-stu-id="44335-116">In the **Hierarchy** pane, click the check box for the member you want to move the members to.</span></span>  
  
8.  <span data-ttu-id="44335-117">Clique em **colar**.</span><span class="sxs-lookup"><span data-stu-id="44335-117">Click **Paste**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44335-118">Em hierarquias derivadas, você somente pode mover os membros para o mesmo nível.</span><span class="sxs-lookup"><span data-stu-id="44335-118">In derived hierarchies, you can move members to the same level only.</span></span> <span data-ttu-id="44335-119">Além disso, não pode alterar a ordem de classificação dos membros.</span><span class="sxs-lookup"><span data-stu-id="44335-119">Also, you cannot change the sort order of members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44335-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44335-120">See Also</span></span>  
 <span data-ttu-id="44335-121">[Mover membros de hierarquia explícitos usando o processo de preparo &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="44335-121">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="44335-122">[Hierarquias derivadas &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="44335-122">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="44335-123">Hierarquias explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="44335-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
