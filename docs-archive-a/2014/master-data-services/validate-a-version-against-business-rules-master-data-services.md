---
title: Validar uma versão em relação a regras de negócio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- validating versions [Master Data Services]
- validating versions [Master Data Services], about validating versions
- versions [Master Data Services], validating
- business rules [Master Data Services], applying to all members
ms.assetid: 5aee7901-6d05-41d4-8bbb-c6f26791d1df
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 085fa071ca511c9d838c140547419bf87fb857bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573162"
---
# <a name="validate-a-version-against-business-rules-master-data-services"></a><span data-ttu-id="fef83-102">Validar uma versão em relação a regras de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fef83-102">Validate a Version against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="fef83-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], valide uma versão para aplicar regras de negócio a todos os membros da versão do modelo.</span><span class="sxs-lookup"><span data-stu-id="fef83-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="fef83-104">Este procedimento explica como usar o aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para validar dados.</span><span class="sxs-lookup"><span data-stu-id="fef83-104">This procedure explains how to use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application to validate data.</span></span> <span data-ttu-id="fef83-105">Se você tiver permissão no banco de dados MDS, poderá usar um procedimento armazenado no lugar.</span><span class="sxs-lookup"><span data-stu-id="fef83-105">If you have permission in the MDS database, you can use a stored procedure instead.</span></span> <span data-ttu-id="fef83-106">Para obter mais informações, consulte [Procedimento armazenado de validação &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fef83-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fef83-107">Todos os membros deverão ser validados antes que uma versão possa ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="fef83-107">All members must pass validation before a version can be committed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fef83-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fef83-108">Prerequisites</span></span>  
 <span data-ttu-id="fef83-109">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="fef83-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="fef83-110">Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="fef83-110">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="fef83-111">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="fef83-111">You must be a model administrator.</span></span> <span data-ttu-id="fef83-112">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fef83-112">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="fef83-113">O status da versão deve ser **Aberto** ou **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="fef83-113">The version's status must be **Open** or **Locked**.</span></span>  
  
-   <span data-ttu-id="fef83-114">Na página **Validar Versões** , os membros devem existir com um status diferente de **Validação bem-sucedida**.</span><span class="sxs-lookup"><span data-stu-id="fef83-114">On the **Validate Versions** page, members must exist with a status other than **Validation succeeded**.</span></span>  
  
### <a name="to-validate-a-version"></a><span data-ttu-id="fef83-115">Para validar uma versão</span><span class="sxs-lookup"><span data-stu-id="fef83-115">To validate a version</span></span>  
  
1.  <span data-ttu-id="fef83-116">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="fef83-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="fef83-117">Na página **Gerenciar Versões** , na barra de menus, clique em **Validar Versão**.</span><span class="sxs-lookup"><span data-stu-id="fef83-117">On the **Manage Versions** page, from the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="fef83-118">Na página **Validar Versões** , selecione o modelo e a versão que você deseja validar.</span><span class="sxs-lookup"><span data-stu-id="fef83-118">On the **Validate Versions** page, select the model and version you want to validate.</span></span>  
  
4.  <span data-ttu-id="fef83-119">Clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="fef83-119">Click **Validate**.</span></span>  
  
5.  <span data-ttu-id="fef83-120">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fef83-120">In the confirmation dialog box, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fef83-121">Quando o indicador de progresso já não for exibido, isso significará que a versão concluiu a validação.</span><span class="sxs-lookup"><span data-stu-id="fef83-121">When the progress indicator is no longer displayed, the version has finished validation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fef83-122">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fef83-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="fef83-123">Bloquear uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fef83-123">Lock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/lock-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="fef83-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fef83-124">See Also</span></span>  
 <span data-ttu-id="fef83-125">[Status de validação &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fef83-125">[Validation Statuses &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span></span>  
 <span data-ttu-id="fef83-126">[Procedimento armazenado de validação &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fef83-126">[Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="fef83-127">[Versões &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fef83-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 <span data-ttu-id="fef83-128">[Regras de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fef83-128">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="fef83-129">Validar membros específicos em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fef83-129">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
  
