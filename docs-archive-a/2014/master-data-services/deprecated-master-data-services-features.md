---
title: Recursos de Master Data Services preteridos no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d8506bda-66dd-45a4-bfc9-3a10fa665acc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce532e9f407ec475f7e59c0d79659265a9e0bf3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678820"
---
# <a name="deprecated-master-data-services-features-in-sql-server-2014"></a><span data-ttu-id="0ddeb-102">Recursos do Master Data Services substituídos no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0ddeb-102">Deprecated Master Data Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="0ddeb-103">Este tópico descreve os recursos substituídos do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] que ainda estão disponíveis no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ddeb-103">This topic describes the deprecated [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="0ddeb-104">Esses recursos estão programados para serem removidos em uma versão futura do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ddeb-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ddeb-105">Recursos preteridos não devem ser usados em aplicativos novos.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="staging-process"></a><span data-ttu-id="0ddeb-106">Processo de preparo</span><span class="sxs-lookup"><span data-stu-id="0ddeb-106">Staging Process</span></span>  
 <span data-ttu-id="0ddeb-107">O processo de preparo que era usado no [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] não está mais disponível no aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] . No entanto, ele ainda está disponível no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ddeb-107">The staging process that was used in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] is no longer available in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application; however it is still available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0ddeb-108">Erros de preparo do processo de preparo do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] não são mais exibidos na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-108">Staging errors from the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging process are no longer displayed in the UI.</span></span> <span data-ttu-id="0ddeb-109">Os códigos de erro que são preenchidos durante o processo de preparo ainda estão disponíveis nas tabelas de preparo e podem ser encontrados aqui: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0ddeb-109">Error codes that are populated during the staging process are still available in the staging tables, and can be found here: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx).</span></span>  
  
 <span data-ttu-id="0ddeb-110">As tabelas de preparo (tblStgMember, tblStgMemberAttribute e tblStgRelationship) ainda estão disponíveis no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-110">The staging tables (tblStgMember, tblStgMemberAttribute, and tblStgRelationship) are still available in the database.</span></span> <span data-ttu-id="0ddeb-111">O procedimento armazenado usado para iniciar o processo de preparo (mdm.udpStagingSweep) ainda está disponível no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-111">The stored procedure used to initiate the staging process (mdm.udpStagingSweep) is still available in the database.</span></span>  
  
 <span data-ttu-id="0ddeb-112">Os métodos de serviço Web que chamam o processo de preparo ainda estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-112">The web service methods that call the staging process are still available.</span></span>  
  
 <span data-ttu-id="0ddeb-113">O intervalo de preparo definido no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] aplica-se ao processo de preparo no [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] e no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ddeb-113">The staging interval set in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] applies to the staging process in both [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] and [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="0ddeb-114">Um novo processo de preparação de maior desempenho foi implementado no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ddeb-114">A new, higher performance staging process has been implemented in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="0ddeb-115">Para obter mais informações, consulte [Importação de dados &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0ddeb-115">For more information, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="0ddeb-116">Metadados</span><span class="sxs-lookup"><span data-stu-id="0ddeb-116">Metadata</span></span>  
 <span data-ttu-id="0ddeb-117">Embora o modelo de metadados ainda seja exibido no aplicativo Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , ele não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-117">Though the Metadata model is still displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, it should not be used.</span></span> <span data-ttu-id="0ddeb-118">Ela será removida em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-118">It will be removed in a future release.</span></span> <span data-ttu-id="0ddeb-119">Os usuários também não podem mais exibir metadados na área funcional do **Gerenciador** e você não pode mais criar versões do modelo de Metadados.</span><span class="sxs-lookup"><span data-stu-id="0ddeb-119">Users can also no longer view metadata in the **Explorer** functional area, and you can no longer create versions of the Metadata model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddeb-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ddeb-120">See Also</span></span>  
 [<span data-ttu-id="0ddeb-121">Recursos do Master Data Services descontinuados no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0ddeb-121">Discontinued Master Data Services Features in SQL Server 2014</span></span>](discontinued-master-data-services-features.md)  
  
  
