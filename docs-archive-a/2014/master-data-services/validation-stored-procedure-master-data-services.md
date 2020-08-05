---
title: Procedimento armazenado de validação (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8fa6b01d950c87768d10b0252c1ccbab2b932fe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574069"
---
# <a name="validation-stored-procedure-master-data-services"></a><span data-ttu-id="39c86-102">Procedimento armazenado de validação (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="39c86-102">Validation Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="39c86-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], valide uma versão para aplicar regras de negócio a todos os membros da versão do modelo.</span><span class="sxs-lookup"><span data-stu-id="39c86-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="39c86-104">Este tópico explica como usar o procedimento armazenado **mdm.udpValidateModel** para validar dados.</span><span class="sxs-lookup"><span data-stu-id="39c86-104">This topic explains how to use the **mdm.udpValidateModel** stored procedure to validate data.</span></span> <span data-ttu-id="39c86-105">Se você for um administrador no aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , poderá fazer validação na interface do usuário em vez disso.</span><span class="sxs-lookup"><span data-stu-id="39c86-105">If you are an administrator in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you can do validation in the UI instead.</span></span> <span data-ttu-id="39c86-106">Para obter mais informações, consulte [Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="39c86-106">For more information, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39c86-107">Se você invocar a validação antes de o processo de preparo ser concluído, os membros que não concluíram o preparo não serão validados.</span><span class="sxs-lookup"><span data-stu-id="39c86-107">If you invoke validation before the staging process is complete, members that have not finished staging will not be validated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c86-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="39c86-108">Example</span></span>  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a><span data-ttu-id="39c86-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="39c86-109">Parameters</span></span>  
 <span data-ttu-id="39c86-110">Os parâmetros desse procedimento são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="39c86-110">The parameters of this procedure are as follows:</span></span>  
  
|<span data-ttu-id="39c86-111">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="39c86-111">Parameter</span></span>|<span data-ttu-id="39c86-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="39c86-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39c86-113">UserID</span><span class="sxs-lookup"><span data-stu-id="39c86-113">UserID</span></span>|<span data-ttu-id="39c86-114">A ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="39c86-114">The user ID.</span></span>|  
|<span data-ttu-id="39c86-115">Model_ID</span><span class="sxs-lookup"><span data-stu-id="39c86-115">Model_ID</span></span>|<span data-ttu-id="39c86-116">A ID do modelo.</span><span class="sxs-lookup"><span data-stu-id="39c86-116">The model ID.</span></span>|  
|<span data-ttu-id="39c86-117">Version_ID</span><span class="sxs-lookup"><span data-stu-id="39c86-117">Version_ID</span></span>|<span data-ttu-id="39c86-118">A ID da versão.</span><span class="sxs-lookup"><span data-stu-id="39c86-118">The version ID.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39c86-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39c86-119">See Also</span></span>  
 <span data-ttu-id="39c86-120">[Master Data Services de importação de dados &#40;&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="39c86-120">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="39c86-121">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="39c86-121">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](validate-a-version-against-business-rules-master-data-services.md)  
  
  