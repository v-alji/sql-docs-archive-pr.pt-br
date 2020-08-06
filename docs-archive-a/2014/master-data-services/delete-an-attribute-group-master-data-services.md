---
title: Excluir um grupo de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting attribute groups [Master Data Services]
- attribute groups [Master Data Services], deleting
ms.assetid: f915e89b-629d-4725-aea6-a7f051978244
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 833c5cf327034b25d68af123a1fc134372bd6f10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583132"
---
# <a name="delete-an-attribute-group-master-data-services"></a><span data-ttu-id="eff4d-102">Excluir um grupo de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="eff4d-102">Delete an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="eff4d-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua um grupo de atributos quando você não precisar mais da guia para exibir a área funcional **Explorer** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eff4d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute group when you no longer need the tab to display in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="eff4d-104">**Observação** Quando existem grupos de atributos, os atributos que não pertencem a um grupo de atributos não são exibidos no **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="eff4d-104">**Note** When attribute groups exist, attributes that do not belong to an attribute group are not displayed in **Explorer**.</span></span> <span data-ttu-id="eff4d-105">Quando não existem grupos de atributos, todos os atributos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="eff4d-105">When no attribute groups exist, all attributes are displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eff4d-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="eff4d-106">Prerequisites</span></span>  
 <span data-ttu-id="eff4d-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="eff4d-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="eff4d-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="eff4d-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="eff4d-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="eff4d-109">You must be a model administrator.</span></span> <span data-ttu-id="eff4d-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="eff4d-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute-group"></a><span data-ttu-id="eff4d-111">Para excluir um grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="eff4d-111">To delete an attribute group</span></span>  
  
1.  <span data-ttu-id="eff4d-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="eff4d-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="eff4d-113">Na página **exibição de modelo** , na barra de menus, aponte para **gerenciar** e clique em **grupos de atributos**.</span><span class="sxs-lookup"><span data-stu-id="eff4d-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="eff4d-114">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="eff4d-114">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="eff4d-115">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="eff4d-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="eff4d-116">Clique no sinal de adição para expandir **grupos folha**, **grupos consolidados**ou **grupos de coleta**, dependendo do tipo de grupo que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="eff4d-116">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to delete.</span></span>  
  
6.  <span data-ttu-id="eff4d-117">Clique no grupo de atributos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="eff4d-117">Click the attribute group you want to delete.</span></span>  
  
7.  <span data-ttu-id="eff4d-118">Clique em **excluir grupo selecionado**.</span><span class="sxs-lookup"><span data-stu-id="eff4d-118">Click **Delete selected group**.</span></span>  
  
8.  <span data-ttu-id="eff4d-119">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eff4d-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="eff4d-120">Na caixa de diálogo de confirmação adicional, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eff4d-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff4d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eff4d-121">See Also</span></span>  
 <span data-ttu-id="eff4d-122">[Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="eff4d-122">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="eff4d-123">Criar um grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eff4d-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
