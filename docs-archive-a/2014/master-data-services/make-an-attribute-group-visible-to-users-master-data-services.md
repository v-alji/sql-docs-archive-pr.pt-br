---
title: Tornar um grupo de atributos visível para os usuários (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b2f6cc27-dbc9-4f3f-961e-e81e76375248
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 309ad0392cd717d4a8a11470621144ef9e604fd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568679"
---
# <a name="make-an-attribute-group-visible-to-users-master-data-services"></a><span data-ttu-id="b2217-102">Tornar um grupo de atributos visível para os usuários (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b2217-102">Make an Attribute Group Visible to Users (Master Data Services)</span></span>
  <span data-ttu-id="b2217-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], torne um grupo de atributos visível para usuários ou grupos quando você desejar que os usuários tenham guias acima da grade na área funcional do **Explorer** .</span><span class="sxs-lookup"><span data-stu-id="b2217-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], make an attribute group visible to users or groups when you want users to have tabs above the grid in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="b2217-104">Quando você criar um grupo de atributos, ele será ocultado automaticamente de todos os usuários, exceto daquele que o criou.</span><span class="sxs-lookup"><span data-stu-id="b2217-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b2217-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b2217-105">Prerequisites</span></span>  
 <span data-ttu-id="b2217-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="b2217-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b2217-107">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="b2217-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="b2217-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="b2217-108">You must be a model administrator.</span></span> <span data-ttu-id="b2217-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b2217-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b2217-110">Pelo menos um grupo de atributos deve existir.</span><span class="sxs-lookup"><span data-stu-id="b2217-110">At least one attribute group must exist.</span></span> <span data-ttu-id="b2217-111">Para obter mais informações, veja [Criar um grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b2217-111">For more information, see [Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span></span>  
  
### <a name="to-make-an-attribute-group-visible-to-users"></a><span data-ttu-id="b2217-112">Para tornar um grupo de atributos visível para usuários</span><span class="sxs-lookup"><span data-stu-id="b2217-112">To make an attribute group visible to users</span></span>  
  
1.  <span data-ttu-id="b2217-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="b2217-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b2217-114">Na página **exibição de modelo** , na barra de menus, aponte para **gerenciar** e clique em **grupos de atributos**.</span><span class="sxs-lookup"><span data-stu-id="b2217-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="b2217-115">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="b2217-115">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="b2217-116">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="b2217-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="b2217-117">Clique no sinal de adição para expandir **grupos folha**, **grupos consolidados**ou **grupos de coleta**, dependendo do tipo de grupo que você deseja tornar visível.</span><span class="sxs-lookup"><span data-stu-id="b2217-117">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to make visible.</span></span>  
  
6.  <span data-ttu-id="b2217-118">Clique no sinal de adição para expandir o grupo que você deseja tornar visível.</span><span class="sxs-lookup"><span data-stu-id="b2217-118">Click the plus sign to expand the group you want to make visible.</span></span>  
  
7.  <span data-ttu-id="b2217-119">Clique em **usuários** ou **grupos**, dependendo se você estiver tornando o grupo visível para um usuário ou um grupo.</span><span class="sxs-lookup"><span data-stu-id="b2217-119">Click either **Users** or **Groups**, depending on whether you are making the group visible to a user or a group.</span></span>  
  
8.  <span data-ttu-id="b2217-120">Clique em **editar item selecionado**.</span><span class="sxs-lookup"><span data-stu-id="b2217-120">Click **Edit selected item**.</span></span>  
  
9. <span data-ttu-id="b2217-121">Clique em usuários ou grupos na caixa **disponível** e clique na seta **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="b2217-121">Click users or groups in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="b2217-122">Para adicionar tudo, clique na seta **Adicionar Tudo** .</span><span class="sxs-lookup"><span data-stu-id="b2217-122">To add all, click the **Add All** arrow.</span></span>  
  
10. <span data-ttu-id="b2217-123">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b2217-123">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2217-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2217-124">See Also</span></span>  
 <span data-ttu-id="b2217-125">[Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b2217-125">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="b2217-126">Criar um grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b2217-126">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
