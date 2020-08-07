---
title: Atribuir permissões de membro de hierarquia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4a1602f9fe351f826b63d4447f90dcf02a10f49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574783"
---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="bb05d-102">Atribuir permissões de membro de hierarquia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bb05d-102">Assign Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="bb05d-103">Atribua permissões a membros de hierarquia para conceder aos usuários ou grupos o acesso para exibir dados na área funcional **Explorer** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb05d-103">Assign permissions to hierarchy members to give users or groups access to view data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="bb05d-104">As permissões de membro de hierarquia são opcionais.</span><span class="sxs-lookup"><span data-stu-id="bb05d-104">Hierarchy member permissions are optional.</span></span> <span data-ttu-id="bb05d-105">Elas fornecem granularidade adicional às permissões de objeto de modelo, que são obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="bb05d-105">They provide added granularity to model object permissions, which are required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bb05d-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bb05d-106">Prerequisites</span></span>  
 <span data-ttu-id="bb05d-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="bb05d-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bb05d-108">Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .</span><span class="sxs-lookup"><span data-stu-id="bb05d-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="bb05d-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="bb05d-109">You must be a model administrator.</span></span> <span data-ttu-id="bb05d-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bb05d-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-hierarchy-member-permissions"></a><span data-ttu-id="bb05d-111">Para atribuir permissões de membro de hierarquia</span><span class="sxs-lookup"><span data-stu-id="bb05d-111">To assign hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="bb05d-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.</span><span class="sxs-lookup"><span data-stu-id="bb05d-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="bb05d-113">Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="bb05d-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="bb05d-114">Clique em **Editar usuário selecionado**.</span><span class="sxs-lookup"><span data-stu-id="bb05d-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="bb05d-115">Clique na guia **Membros da Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="bb05d-115">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="bb05d-116">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="bb05d-116">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="bb05d-117">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="bb05d-117">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="bb05d-118">Na lista **Hierarquia** , selecione uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="bb05d-118">From the **Hierarchy** list, select a hierarchy.</span></span>  
  
8.  <span data-ttu-id="bb05d-119">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb05d-119">Click **Edit**.</span></span>  
  
9. <span data-ttu-id="bb05d-120">Expanda a árvore e clique no nó de hierarquia ao qual deseja atribuir permissões.</span><span class="sxs-lookup"><span data-stu-id="bb05d-120">Expand the tree, and click the hierarchy node you want to assign permissions to.</span></span>  
  
10. <span data-ttu-id="bb05d-121">No menu, selecione **somente leitura**, **Atualizar**ou **negar**.</span><span class="sxs-lookup"><span data-stu-id="bb05d-121">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
11. <span data-ttu-id="bb05d-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bb05d-122">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb05d-123">As permissões de membro de hierarquia não entram em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="bb05d-123">Hierarchy member permissions do not take effect immediately.</span></span> <span data-ttu-id="bb05d-124">Consulte [Aplicar permissões de membros imediatamente &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb05d-124">See [Immediately Apply Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb05d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb05d-125">See Also</span></span>  
 <span data-ttu-id="bb05d-126">[Excluir permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb05d-126">[Delete Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="bb05d-127">[Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb05d-127">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="bb05d-128">Permissões de membro de hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bb05d-128">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
