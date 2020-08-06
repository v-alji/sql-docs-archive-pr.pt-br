---
title: Excluir uma versão (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f83a3bc396b2a13ac7ac03ef653b16a0d556189a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583134"
---
# <a name="delete-a-version-master-data-services"></a><span data-ttu-id="d6b3c-102">Excluir uma versão (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d6b3c-102">Delete a Version (Master Data Services)</span></span>
  <span data-ttu-id="d6b3c-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua uma versão quando tiver certeza de que já não precisa dos dados mestres associados à versão.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a version when you are sure you no longer need the master data associated with the version.</span></span> <span data-ttu-id="d6b3c-104">Depois de excluir uma versão, você não poderá recuperar os dados mestres associados.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-104">After you delete a version, you cannot retrieve the associated master data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d6b3c-105">Se um modelo tiver somente uma versão e você a excluir, ele se tornará inutilizável.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-105">If a model has only one version and you delete it, the model becomes unusable.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6b3c-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d6b3c-106">Prerequisites</span></span>  
 <span data-ttu-id="d6b3c-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="d6b3c-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d6b3c-108">Você deve ter permissão para ver a exibição mdm.viw_SYSTEM_SCHEMA_VERSION e executar o procedimento armazenado mds.udpVersionDelete no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6b3c-108">You must have permission to view the mdm.viw_SYSTEM_SCHEMA_VERSION view and to execute the mds.udpVersionDelete stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="d6b3c-109">Para obter mais informações, consulte [Segurança do objeto de banco de dados &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6b3c-109">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-version"></a><span data-ttu-id="d6b3c-110">Para excluir uma versão</span><span class="sxs-lookup"><span data-stu-id="d6b3c-110">To delete a version</span></span>  
  
1.  <span data-ttu-id="d6b3c-111">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se à instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] de seu banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6b3c-111">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="d6b3c-112">Abra a exibição mdm.viw_SYSTEM_SCHEMA_VERSION.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-112">Open the mdm.viw_SYSTEM_SCHEMA_VERSION view.</span></span>  
  
3.  <span data-ttu-id="d6b3c-113">Localize a versão do modelo que você deseja excluir e copie o valor no campo **ID** .</span><span class="sxs-lookup"><span data-stu-id="d6b3c-113">Find the version of the model you want to delete and copy the value in the **ID** field.</span></span>  
  
4.  <span data-ttu-id="d6b3c-114">Crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-114">Create a new query.</span></span>  
  
5.  <span data-ttu-id="d6b3c-115">Digite o texto a seguir, substituindo *version_ID* pelo valor copiado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-115">Type the following text, replacing *version_ID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  <span data-ttu-id="d6b3c-116">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-116">Run the query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6b3c-117">Talvez seja necessário aguardar alguns minutos para que o aplicativo Web reflita a alteração.</span><span class="sxs-lookup"><span data-stu-id="d6b3c-117">You may have to wait a few minutes before the Web application reflects the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b3c-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d6b3c-118">See Also</span></span>  
 <span data-ttu-id="d6b3c-119">[Versões &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d6b3c-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="d6b3c-120">Copiar uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d6b3c-120">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
  
