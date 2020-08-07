---
title: Administradores (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], about administrators
- administrators [Master Data Services]
- models [Master Data Services], administrators
ms.assetid: d330aa4e-6ade-4b09-b376-1b15d6c78f7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 52e16d4e77acc0a6b50b87e00184918cb9ce64b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681736"
---
# <a name="administrators-master-data-services"></a><span data-ttu-id="0e8d4-102">Administradores (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0e8d4-102">Administrators (Master Data Services)</span></span>
  <span data-ttu-id="0e8d4-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], há dois tipos de administradores: administradores de modelo e o administrador do sistema do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e8d4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], there are two types of administrators: model administrators, and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
## <a name="model-administrators"></a><span data-ttu-id="0e8d4-104">Administradores de modelo</span><span class="sxs-lookup"><span data-stu-id="0e8d4-104">Model Administrators</span></span>  
 <span data-ttu-id="0e8d4-105">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , um administrador de modelo é um usuário que tem a permissão **Atualizar** atribuída ao objeto de modelo de nível superior na guia **objetos de modelo** e nenhuma outra permissão atribuída.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-105">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a model administrator is a user who has **Update** permission assigned to the top-level model object on the **Model Objects** tab and no other assigned permissions.</span></span>  
  
-   <span data-ttu-id="0e8d4-106">Se o usuário tiver acesso à área funcional **Gerenciador** , ele poderá adicionar, excluir e atualizar todos os dados mestre nessa área.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-106">If the user has access to the **Explorer** functional area, the user can add, delete, and update all master data in this area.</span></span>  
  
-   <span data-ttu-id="0e8d4-107">Se o usuário tiver acesso a outras áreas funcionais, o usuário poderá executar todas as tarefas administrativas disponíveis na área funcional.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-107">If the user has access to other functional areas, the user can perform all administrative tasks available in the functional area.</span></span>  
  
 <span data-ttu-id="0e8d4-108">Cada modelo pode ter vários administradores.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-108">Each model can have multiple administrators.</span></span> <span data-ttu-id="0e8d4-109">Cada usuário pode ser um administrador de modelo para um, vários ou todos os modelos na implantação do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e8d4-109">Each user can be a model administrator for one, several, or all models in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span>  
  
 <span data-ttu-id="0e8d4-110">Um usuário ou pode ser configurado como um administrador de modelo no [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-110">A user can be configured as a model administrator either in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] or programmatically.</span></span> <span data-ttu-id="0e8d4-111">Para obter mais informações, consulte [Criar um administrador de modelo &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d4-111">For more information, see [Create a Model Administrator &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md).</span></span>  
  
## <a name="master-data-services-system-administrator"></a><span data-ttu-id="0e8d4-112">Administrador do sistema do Master Data Services</span><span class="sxs-lookup"><span data-stu-id="0e8d4-112">Master Data Services System Administrator</span></span>  
 <span data-ttu-id="0e8d4-113">Há somente um administrador do sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e8d4-113">There is only one [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span> <span data-ttu-id="0e8d4-114">O administrador do sistema é o usuário especificado para a **conta de administrador** quando você cria o banco de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] dados.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-114">The system administrator is the user specified for the **Administrator Account** when you create the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
 <span data-ttu-id="0e8d4-115">O administrador do sistema do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0e8d4-115">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator:</span></span>  
  
-   <span data-ttu-id="0e8d4-116">Tem acesso automaticamente a todas as áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-116">Automatically has access to all functional areas.</span></span>  
  
-   <span data-ttu-id="0e8d4-117">Pode adicionar, excluir e atualizar todos os dados mestre de todos os modelos na área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="0e8d4-117">Can add, delete, and update all master data for all models in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="0e8d4-118">Você pode alterar o usuário designado como administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-118">You can change the user who is assigned as the system administrator.</span></span> <span data-ttu-id="0e8d4-119">Para obter mais informações, consulte [alterar a conta de administrador do sistema &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d4-119">For more information, see [Change the System Administrator Account &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md).</span></span>  
  
## <a name="comparing-administrator-types"></a><span data-ttu-id="0e8d4-120">Comparando tipos de administrador</span><span class="sxs-lookup"><span data-stu-id="0e8d4-120">Comparing Administrator Types</span></span>  
  
|<span data-ttu-id="0e8d4-121">Tipo de administrador</span><span class="sxs-lookup"><span data-stu-id="0e8d4-121">Administrator Type</span></span>|<span data-ttu-id="0e8d4-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="0e8d4-122">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="0e8d4-123">Administrador do sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e8d4-123">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator</span></span>|<span data-ttu-id="0e8d4-124">As permissões atribuídas no [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] não têm nenhum efeito sobre o acesso do administrador.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-124">Permissions assigned in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] have no effect on the administrator's access.</span></span><br /><br /> <span data-ttu-id="0e8d4-125">Tem automaticamente a permissão **Atualizar** para todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-125">Automatically has **Update** permission to all models.</span></span><br /><br /> <span data-ttu-id="0e8d4-126">Tem acesso automaticamente a todas as áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-126">Automatically has access to all functional areas.</span></span><br /><br /> <span data-ttu-id="0e8d4-127">No MDM. tblUser, o valor na coluna **ID** é **1**.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-127">In mdm.tblUser, the value in the **ID** column is **1**.</span></span>|  
|<span data-ttu-id="0e8d4-128">Administrador de modelo</span><span class="sxs-lookup"><span data-stu-id="0e8d4-128">Model administrator</span></span>|<span data-ttu-id="0e8d4-129">As permissões atribuídas no [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] determinam se o usuário é um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-129">Permissions assigned in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] determine whether or not the user is a model administrator.</span></span><br /><br /> <span data-ttu-id="0e8d4-130">Pode ser um administrador de modelo com base nas permissões atribuídas explicitamente ou nas permissões herdadas de um grupo.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-130">Can be a model administrator based on permissions assigned explicitly or permissions inherited from a group.</span></span><br /><br /> <span data-ttu-id="0e8d4-131">É um administrador somente para modelos que têm permissão de **atualização** atribuída ao objeto de modelo de nível superior e nenhuma outra permissão.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-131">Is an administrator only for models that have **Update** permission assigned to top-level model object, and no other permissions.</span></span><br /><br /> <span data-ttu-id="0e8d4-132">Tem acesso somente a áreas funcionais às quais esse acesso é concedido.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-132">Has access only to functional areas that access is granted to.</span></span><br /><br /> <span data-ttu-id="0e8d4-133">No MDM. tblUser, o valor na coluna **ID** não é **1**.</span><span class="sxs-lookup"><span data-stu-id="0e8d4-133">In mdm.tblUser, the value in the **ID** column is not **1**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e8d4-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e8d4-134">See Also</span></span>  
 <span data-ttu-id="0e8d4-135">[Criar um administrador de modelo &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0e8d4-135">[Create a Model Administrator &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md) </span></span>  
 <span data-ttu-id="0e8d4-136">[Altere a conta de administrador do sistema &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0e8d4-136">[Change the System Administrator Account &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md) </span></span>  
 <span data-ttu-id="0e8d4-137">[Criar um banco de dados Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="0e8d4-137">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 [<span data-ttu-id="0e8d4-138">Notificações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0e8d4-138">Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/notifications-master-data-services.md)  
  
  
