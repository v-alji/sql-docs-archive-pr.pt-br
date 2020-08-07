---
title: Aplicar permissões de membros imediatamente (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e960ad06213b7c5057a6249b72ce225a6abe35e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575178"
---
# <a name="immediately-apply-member-permissions-master-data-services"></a><span data-ttu-id="ffab3-102">Aplicar permissões de membros imediatamente (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ffab3-102">Immediately Apply Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="ffab3-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], em vez de esperar que a segurança de membro seja aplicada a intervalos regulares, você pode aplicar permissões de membro imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ffab3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ffab3-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ffab3-104">Prerequisites</span></span>  
 <span data-ttu-id="ffab3-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="ffab3-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ffab3-106">Você deverá ter permissão para executar o procedimento armazenado mdm.udpSecurityMemberProcessRebuildModel no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffab3-106">You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="ffab3-107">Para obter mais informações, consulte [Segurança do objeto de banco de dados &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ffab3-107">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a><span data-ttu-id="ffab3-108">Para aplicar permissões de membro da hierarquia imediatamente</span><span class="sxs-lookup"><span data-stu-id="ffab3-108">To immediately apply hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="ffab3-109">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se à instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] de seu banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffab3-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="ffab3-110">Crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="ffab3-110">Create a new query.</span></span>  
  
3.  <span data-ttu-id="ffab3-111">Digite o seguinte texto, substituindo *database* pelo nome do banco de dados e *Model_Name* pelo nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="ffab3-111">Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.</span></span>  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  <span data-ttu-id="ffab3-112">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="ffab3-112">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffab3-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffab3-113">See Also</span></span>  
 <span data-ttu-id="ffab3-114">[Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ffab3-114">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="ffab3-115">Permissões de membro de hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ffab3-115">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
