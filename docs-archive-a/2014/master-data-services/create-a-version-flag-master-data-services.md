---
title: Criar um sinalizador de versão (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f04c93f8315ccd5b53e07db169783da53afe0156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575892"
---
# <a name="create-a-version-flag-master-data-services"></a><span data-ttu-id="cc355-102">Criar um sinalizador de versão (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="cc355-102">Create a Version Flag (Master Data Services)</span></span>
  <span data-ttu-id="cc355-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie um sinalizador de versão a ser atribuído a uma versão.</span><span class="sxs-lookup"><span data-stu-id="cc355-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a version flag to assign to a version.</span></span> <span data-ttu-id="cc355-104">O sinalizador pode indicar a versão que os usuários ou sistemas de assinatura devem usar.</span><span class="sxs-lookup"><span data-stu-id="cc355-104">The flag can indicate the version that users or subscribing systems should use.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cc355-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cc355-105">Prerequisites</span></span>  
 <span data-ttu-id="cc355-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="cc355-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cc355-107">Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="cc355-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="cc355-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="cc355-108">You must be a model administrator.</span></span> <span data-ttu-id="cc355-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cc355-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-version-flag"></a><span data-ttu-id="cc355-110">Para criar um sinalizador de versão</span><span class="sxs-lookup"><span data-stu-id="cc355-110">To create a version flag</span></span>  
  
1.  <span data-ttu-id="cc355-111">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="cc355-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="cc355-112">Na página **Gerenciar Versões** , na barra de menus, aponte para **Gerenciar** e clique em **Sinalizadores**.</span><span class="sxs-lookup"><span data-stu-id="cc355-112">On the **Manage Versions** page, from the menu bar, point to **Manage** and then click **Flags**.</span></span>  
  
3.  <span data-ttu-id="cc355-113">Na página **Gerenciar Sinalizadores de Versão** , no campo **Modelo** , selecione o modelo para o qual você deseja criar um sinalizador.</span><span class="sxs-lookup"><span data-stu-id="cc355-113">On the **Manage Version Flags** page, from the **Model** field, select the model for which you want to create a flag.</span></span>  
  
4.  <span data-ttu-id="cc355-114">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc355-114">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="cc355-115">Na caixa **Nome** , digite um nome.</span><span class="sxs-lookup"><span data-stu-id="cc355-115">In the **Name** box, type a name.</span></span>  
  
6.  <span data-ttu-id="cc355-116">Na caixa **Descrição** , digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="cc355-116">In the **Description** box, type a description.</span></span>  
  
7.  <span data-ttu-id="cc355-117">No campo **Somente Versões Confirmadas** , selecione **True** para indicar que o sinalizador pode ser atribuído a versões apenas com um status de **Confirmado** .</span><span class="sxs-lookup"><span data-stu-id="cc355-117">In the **Committed Versions Only** field, select **True** to indicate that the flag can be assigned to versions with a status of **Committed** only.</span></span> <span data-ttu-id="cc355-118">Selecione **False** para indicar que o sinalizador pode ser atribuído a versões com qualquer status.</span><span class="sxs-lookup"><span data-stu-id="cc355-118">Select **False** to indicate that the flag can be assigned to versions with any status.</span></span>  
  
8.  <span data-ttu-id="cc355-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc355-119">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cc355-120">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cc355-120">Next Steps</span></span>  
  
-   [<span data-ttu-id="cc355-121">Atribuir um sinalizador a uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc355-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc355-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc355-122">See Also</span></span>  
 <span data-ttu-id="cc355-123">[Versões &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cc355-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="cc355-124">Alterar o nome de um sinalizador de versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc355-124">Change a Version Flag Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  
