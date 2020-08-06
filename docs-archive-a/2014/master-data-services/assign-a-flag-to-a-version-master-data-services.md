---
title: Atribuir um sinalizador a uma versão (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2de0d0d8d8ea96814e13b9123fe4fcd4782d6bef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583138"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a><span data-ttu-id="db529-102">Atribuir um sinalizador a uma versão (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db529-102">Assign a Flag to a Version (Master Data Services)</span></span>
  <span data-ttu-id="db529-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], atribua um sinalizador para uma versão para indicar a versão que usuários ou sistemas de assinatura deveriam usar.</span><span class="sxs-lookup"><span data-stu-id="db529-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign a flag to a version to indicate the version that users or subscribing systems should use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db529-104">Sinalizadores de versão podem ser atribuídos a apenas uma versão de cada vez.</span><span class="sxs-lookup"><span data-stu-id="db529-104">Version flags can be assigned to only one version at a time.</span></span> <span data-ttu-id="db529-105">Se você atribuir um sinalizador que já esteja atribuído a outra versão, o sinalizador será movido para a versão selecionada.</span><span class="sxs-lookup"><span data-stu-id="db529-105">If you assign a flag that is already assigned to another version, the flag is moved to the version you selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="db529-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="db529-106">Prerequisites</span></span>  
 <span data-ttu-id="db529-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="db529-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="db529-108">Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="db529-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="db529-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="db529-109">You must be a model administrator.</span></span> <span data-ttu-id="db529-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="db529-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="db529-111">Você deveria ter criado um sinalizador de versão para atribuir.</span><span class="sxs-lookup"><span data-stu-id="db529-111">You must have created a version flag to assign.</span></span> <span data-ttu-id="db529-112">Para obter mais informações, veja [Criar um sinalizador de versão &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="db529-112">For more information, see [Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span></span>  
  
### <a name="to-assign-a-flag-to-a-version"></a><span data-ttu-id="db529-113">Para atribuir um sinalizador a uma versão</span><span class="sxs-lookup"><span data-stu-id="db529-113">To assign a flag to a version</span></span>  
  
1.  <span data-ttu-id="db529-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="db529-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="db529-115">Na página **Gerenciar Versões** , na linha da versão à qual você deseja atribuir um sinalizador, clique duas vezes na célula na coluna **Sinalizador** .</span><span class="sxs-lookup"><span data-stu-id="db529-115">On the **Manage Versions** page, in the row for the version to which you want to assign a flag, double-click the cell in the **Flag** column.</span></span>  
  
3.  <span data-ttu-id="db529-116">Selecione na lista os sinalizadores que você quer atribuir.</span><span class="sxs-lookup"><span data-stu-id="db529-116">From the list, select the flag you want to assign.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="db529-117">Se o sinalizador desejado não estiver disponível, talvez ele só esteja disponível para versões **Confirmadas** .</span><span class="sxs-lookup"><span data-stu-id="db529-117">If the flag you want is not available, the flag might be available for **Committed** versions only.</span></span> <span data-ttu-id="db529-118">Para confirmar, vá para a página **Gerenciar Sinalizadores de Versão** e exiba o campo **Somente Versões Confirmadas** do sinalizador.</span><span class="sxs-lookup"><span data-stu-id="db529-118">To confirm, go to the **Manage Version Flags** page and view the **Committed Versions Only** field for the flag.</span></span>  
  
4.  <span data-ttu-id="db529-119">Pressione ENTER para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="db529-119">Press ENTER to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db529-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db529-120">See Also</span></span>  
 <span data-ttu-id="db529-121">[Criar um sinalizador de versão &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="db529-121">[Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span></span>  
 [<span data-ttu-id="db529-122">Versões &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="db529-122">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
