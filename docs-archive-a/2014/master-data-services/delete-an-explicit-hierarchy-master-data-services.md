---
title: Excluir uma hierarquia explícita (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, deleting
- deleting explicit hierarchies [Master Data Services]
ms.assetid: 4ce177b0-9884-47a2-9cea-212e845dd762
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 744f96a2705a3abbc2318ecd3c9b0c7fffb7605e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584180"
---
# <a name="delete-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="8e958-102">Excluir uma hierarquia explícita (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8e958-102">Delete an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="8e958-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua uma hierarquia explícita quando você já não precisar mais dela.</span><span class="sxs-lookup"><span data-stu-id="8e958-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an explicit hierarchy when you no longer need it.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8e958-104">Quando você excluir uma hierarquia explícita, todos os membros consolidados na hierarquia também serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="8e958-104">When you delete an explicit hierarchy, all consolidated members in the hierarchy are deleted also.</span></span> <span data-ttu-id="8e958-105">Se você excluir todas as hierarquias explícitas de uma entidade, serão excluídas também todas as coleções na entidade, que deixará de estar habilitada para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="8e958-105">If you delete all explicit hierarchies for an entity, all collections for the entity are also deleted and the entity is no longer enabled for explicit hierarchies and collections.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e958-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8e958-106">Prerequisites</span></span>  
 <span data-ttu-id="8e958-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="8e958-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8e958-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="8e958-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="8e958-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="8e958-109">You must be a model administrator.</span></span> <span data-ttu-id="8e958-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8e958-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-explicit-hierarchy"></a><span data-ttu-id="8e958-111">Para excluir uma hierarquia explícita</span><span class="sxs-lookup"><span data-stu-id="8e958-111">To delete an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="8e958-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="8e958-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="8e958-113">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="8e958-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="8e958-114">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="8e958-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="8e958-115">Selecione a linha da entidade que contém a hierarquia explícita que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="8e958-115">Select the row for the entity that contains the explicit hierarchy you want to delete.</span></span>  
  
5.  <span data-ttu-id="8e958-116">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="8e958-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="8e958-117">Na página **Editar entidade** , no painel **hierarquias explícitas** , clique na hierarquia explícita que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="8e958-117">On the **Edit Entity** page, in the **Explicit Hierarchies** pane, click the explicit hierarchy you want to delete.</span></span>  
  
7.  <span data-ttu-id="8e958-118">Clique em **excluir hierarquia selecionada**.</span><span class="sxs-lookup"><span data-stu-id="8e958-118">Click **Delete selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="8e958-119">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e958-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="8e958-120">Na caixa de diálogo de confirmação adicional, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e958-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e958-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e958-121">See Also</span></span>  
 <span data-ttu-id="8e958-122">[Criar uma hierarquia explícita &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8e958-122">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="8e958-123">Hierarquias explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8e958-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
