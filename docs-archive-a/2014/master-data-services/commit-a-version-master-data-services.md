---
title: Confirmar uma versão (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cec3244d4ddaa78d9168e3ede503fa16756633a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680545"
---
# <a name="commit-a-version-master-data-services"></a><span data-ttu-id="ecd88-102">Confirmar uma versão (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ecd88-102">Commit a Version (Master Data Services)</span></span>
  <span data-ttu-id="ecd88-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], confirme uma versão de um modelo para evitar alterações para os membros do modelo e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="ecd88-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], commit a version of a model to prevent changes to the model's members and their attributes.</span></span> <span data-ttu-id="ecd88-104">As versões confirmadas não podem ser desbloqueadas.</span><span class="sxs-lookup"><span data-stu-id="ecd88-104">Committed versions cannot be unlocked.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecd88-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ecd88-105">Prerequisites</span></span>  
 <span data-ttu-id="ecd88-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="ecd88-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ecd88-107">Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="ecd88-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="ecd88-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="ecd88-108">You must be a model administrator.</span></span> <span data-ttu-id="ecd88-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecd88-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ecd88-110">O status da versão deverá ser **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="ecd88-110">The version's status must be **Locked**.</span></span> <span data-ttu-id="ecd88-111">Para obter mais informações, veja [Bloquear uma versão &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecd88-111">For more information, see [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ecd88-112">Todos os membros devem ter validado com êxito.</span><span class="sxs-lookup"><span data-stu-id="ecd88-112">All members must have validated successfully.</span></span>  
  
### <a name="to-commit-a-version"></a><span data-ttu-id="ecd88-113">Para confirmar uma versão</span><span class="sxs-lookup"><span data-stu-id="ecd88-113">To commit a version</span></span>  
  
1.  <span data-ttu-id="ecd88-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="ecd88-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="ecd88-115">Na página **Gerenciar Versões** , na barra de menus, clique em **Validar Versão**.</span><span class="sxs-lookup"><span data-stu-id="ecd88-115">On the **Manage Versions** page, on the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="ecd88-116">Na página **Validar Versão** , selecione o modelo e a versão que deseja confirmar.</span><span class="sxs-lookup"><span data-stu-id="ecd88-116">On the **Validate Version** page, select the model and version you want to commit.</span></span>  
  
4.  <span data-ttu-id="ecd88-117">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ecd88-117">Click **Commit**.</span></span>  
  
5.  <span data-ttu-id="ecd88-118">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecd88-118">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ecd88-119">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ecd88-119">Next Steps</span></span>  
  
-   [<span data-ttu-id="ecd88-120">Criar um sinalizador de versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ecd88-120">Create a Version Flag &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [<span data-ttu-id="ecd88-121">Atribuir um sinalizador a uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ecd88-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [<span data-ttu-id="ecd88-122">Copiar uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ecd88-122">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ecd88-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ecd88-123">See Also</span></span>  
 [<span data-ttu-id="ecd88-124">Versões &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ecd88-124">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
