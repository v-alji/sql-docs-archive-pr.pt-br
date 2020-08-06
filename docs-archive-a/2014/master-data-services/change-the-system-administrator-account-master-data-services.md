---
title: Alterar a conta de administrador do sistema (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], changing
ms.assetid: cf30312e-4338-49a7-90f0-6e4f7b431ff8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d13cdc19c70c9e16c92dfd290393739d7e4f5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681727"
---
# <a name="change-the-system-administrator-account-master-data-services"></a><span data-ttu-id="9eaea-102">Alterar a conta de administrador do sistema (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9eaea-102">Change the System Administrator Account (Master Data Services)</span></span>
  <span data-ttu-id="9eaea-103">Você pode alterar a conta de usuário designada como o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="9eaea-103">You can change the user account that is designated as the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9eaea-104">Quando esse procedimento for concluído, a conta de usuário de administrador do sistema anterior será excluída.</span><span class="sxs-lookup"><span data-stu-id="9eaea-104">When you complete this procedure, the former system administrator user account is deleted.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9eaea-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9eaea-105">Prerequisites</span></span>  
 <span data-ttu-id="9eaea-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="9eaea-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9eaea-107">Você deve adicionar o nome de usuário do novo administrador à lista Usuários do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eaea-107">You must add the new administrator's user name to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Users list.</span></span> <span data-ttu-id="9eaea-108">Para obter mais informações, consulte [Adicionar um usuário &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9eaea-108">For more information, see [Add a User &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9eaea-109">Você deve ter permissão para exibir mdm.tblUser e para executar o procedimento armazenado mdm.udpSecurityMemberProcessRebuildModel no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eaea-109">You must have permission to view mdm.tblUser and to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="9eaea-110">Para obter mais informações, consulte [Segurança do objeto de banco de dados &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9eaea-110">For more information, see [Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-change-the-administrator-account"></a><span data-ttu-id="9eaea-111">Para alterar a conta de administrador</span><span class="sxs-lookup"><span data-stu-id="9eaea-111">To change the administrator account</span></span>  
  
1.  <span data-ttu-id="9eaea-112">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se à instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] de seu banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9eaea-112">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="9eaea-113">Em MDM. tblUser, localize o usuário que será o novo administrador e copie o valor na `SID` coluna.</span><span class="sxs-lookup"><span data-stu-id="9eaea-113">In mdm.tblUser, find the user that will be the new administrator and copy the value in the `SID` column.</span></span>  
  
3.  <span data-ttu-id="9eaea-114">Crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="9eaea-114">Create a new query.</span></span>  
  
4.  <span data-ttu-id="9eaea-115">Digite o seguinte texto, substituindo *domínio \ user_name* pelo nome de usuário do novo administrador e pelo *Sid* pelo valor que você copiou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="9eaea-115">Type the following text, replacing *DOMAIN\user_name* with the new administrator's user name and *SID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  <span data-ttu-id="9eaea-116">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="9eaea-116">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eaea-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9eaea-117">See Also</span></span>  
 [<span data-ttu-id="9eaea-118">Administradores &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9eaea-118">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
