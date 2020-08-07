---
title: Criar um administrador de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 24efc3961e6ed5b9f41b2321dfcc4fbf16632270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583701"
---
# <a name="create-a-model-administrator-master-data-services"></a><span data-ttu-id="9a769-102">Criar um administrador de modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9a769-102">Create a Model Administrator (Master Data Services)</span></span>
  <span data-ttu-id="9a769-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , crie um administrador de modelo quando desejar que um grupo ou usuário tenha a permissão **Atualizar** para todos os objetos em um ou mais modelos.</span><span class="sxs-lookup"><span data-stu-id="9a769-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model administrator when you want a group or user to have **Update** permission to all objects in one or more models.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9a769-104">Para simplificar a administração, crie um grupo local ou do Windows e configure-o como um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="9a769-104">To simplify administration, create a Windows or local group and configure it as a model administrator.</span></span> <span data-ttu-id="9a769-105">Isso lhe permitirá adicionar e remover usuários do grupo sem acessar o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a769-105">You can then add and remove users from the group without accessing [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a769-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9a769-106">Prerequisites</span></span>  
 <span data-ttu-id="9a769-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="9a769-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9a769-108">Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .</span><span class="sxs-lookup"><span data-stu-id="9a769-108">You must have permission to access the **User and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="9a769-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="9a769-109">You must be a model administrator.</span></span> <span data-ttu-id="9a769-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a769-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-administrator"></a><span data-ttu-id="9a769-111">Para criar um administrador de modelo</span><span class="sxs-lookup"><span data-stu-id="9a769-111">To create a model administrator</span></span>  
  
1.  <span data-ttu-id="9a769-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.</span><span class="sxs-lookup"><span data-stu-id="9a769-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="9a769-113">Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="9a769-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="9a769-114">Clique em **Editar usuário selecionado**.</span><span class="sxs-lookup"><span data-stu-id="9a769-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="9a769-115">Clique na guia **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="9a769-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="9a769-116">Opcionalmente, selecione um modelo na lista **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="9a769-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="9a769-117">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a769-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="9a769-118">Clique no modelo ao qual você deseja atribuir permissão.</span><span class="sxs-lookup"><span data-stu-id="9a769-118">Click the model you want to grant permission to.</span></span>  
  
8.  <span data-ttu-id="9a769-119">No menu, selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="9a769-119">From the menu, select **Update**.</span></span>  
  
9. <span data-ttu-id="9a769-120">Conclua as etapas 7 e 8 para cada modelo do qual o grupo ou usuário deverá ser administrador.</span><span class="sxs-lookup"><span data-stu-id="9a769-120">Complete steps 7 and 8 for each model you want the group or user to be an administrator for.</span></span>  
  
10. <span data-ttu-id="9a769-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9a769-121">Click **Save**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a769-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="9a769-122">Remarks</span></span>  
 <span data-ttu-id="9a769-123">Não atribua qualquer outra permissão a objetos de modelo ou membros de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="9a769-123">Do not assign any other permissions to model objects or hierarchy members.</span></span> <span data-ttu-id="9a769-124">Se você fizer isso, o usuário não será mais um administrador e não poderá exibir o modelo em nenhuma área funcional que não seja o **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9a769-124">If you do, the user is no longer an administrator and cannot view the model in any functional area other than **Explorer**.</span></span>  
  
 <span data-ttu-id="9a769-125">Há uma exceção: se o usuário tiver a permissão **Atualizar** atribuída a uma **raiz** de hierarquia na guia **membros da hierarquia** , o usuário ainda será considerado um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="9a769-125">There is one exception: if the user has **Update** permission assigned to a hierarchy **Root** on the **Hierarchy Members** tab, the user is still considered a model administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a769-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a769-126">See Also</span></span>  
 <span data-ttu-id="9a769-127">[Administradores &#40;Master Data Services&#41;](administrators-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a769-127">[Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md) </span></span>  
 <span data-ttu-id="9a769-128">[Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a769-128">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9a769-129">[Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a769-129">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9a769-130">[Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a769-130">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="9a769-131">Permissões de membro de hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a769-131">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
