---
title: Exibir erros que ocorrem durante o processo de preparo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], viewing errors
ms.assetid: 6d2bff84-624b-47fc-a4a5-d9ea01d13412
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3b39d039b29090f3021c764126ebb782ce25cbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680512"
---
# <a name="view-errors-that-occur-during-the-staging-process-master-data-services"></a><span data-ttu-id="5a319-102">Exibir os erros ocorridos durante o processo de preparo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5a319-102">View Errors that Occur During the Staging Process (Master Data Services)</span></span>
  <span data-ttu-id="5a319-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode exibir os erros ocorridos durante o processo de preparo.</span><span class="sxs-lookup"><span data-stu-id="5a319-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can view errors that occur during the staging process.</span></span> <span data-ttu-id="5a319-104">No banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , há duas exibições que mostram erros:</span><span class="sxs-lookup"><span data-stu-id="5a319-104">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, there are two views that show errors:</span></span>  
  
-   <span data-ttu-id="5a319-105">stg.viw_name_MemberErrorDetails para atualizações de membro folha ou consolidado.</span><span class="sxs-lookup"><span data-stu-id="5a319-105">stg.viw_name_MemberErrorDetails for leaf or consolidated member updates.</span></span>  
  
-   <span data-ttu-id="5a319-106">stg.viw_name_RelationshipErrorDetails para atualizações de relação de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="5a319-106">stg.viw_name_RelationshipErrorDetails for hierarchy relationship updates.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a319-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5a319-107">Prerequisites</span></span>  
 <span data-ttu-id="5a319-108">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="5a319-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5a319-109">No banco de dados [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , você deve ter permissões SELECT para a exibição stg.viw_name_MemberErrorDetails ou stg.viw_name_RelationshipErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="5a319-109">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, you must have SELECT permissions to either the stg.viw_name_MemberErrorDetails or stg.viw_name_RelationshipErrorDetails view.</span></span>  
  
-   <span data-ttu-id="5a319-110">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5a319-110">You must be a model administrator.</span></span> <span data-ttu-id="5a319-111">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5a319-111">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-view-staging-errors"></a><span data-ttu-id="5a319-112">Para exibir erros de preparo</span><span class="sxs-lookup"><span data-stu-id="5a319-112">To view staging errors</span></span>  
  
1.  <span data-ttu-id="5a319-113">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se à instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] de seu banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a319-113">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="5a319-114">Abra uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="5a319-114">Open a new query.</span></span>  
  
3.  <span data-ttu-id="5a319-115">Digite o texto a seguir, substituindo name pelo nome de sua tabela de preparo, por exemplo, viw_Product_MemberErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="5a319-115">Type the following text, replacing name with the name of your staging table, for example, viw_Product_MemberErrorDetails.</span></span>  
  
     `SELECT * FROM stg.viw_name_MemberErrorDetails`  
  
4.  <span data-ttu-id="5a319-116">Execute a consulta.</span><span class="sxs-lookup"><span data-stu-id="5a319-116">Excecute the query.</span></span> <span data-ttu-id="5a319-117">Os detalhes do erro são exibidos no campo **ErrorDescription** .</span><span class="sxs-lookup"><span data-stu-id="5a319-117">Error details are displayed in the **ErrorDescription** field.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5a319-118">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5a319-118">Next Steps</span></span>  
 <span data-ttu-id="5a319-119">Para obter mais detalhes sobre mensagens de erro, consulte [Erros de processo de preparo &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5a319-119">For more details on error messages, see [Staging Process Errors &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a319-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a319-120">See Also</span></span>  
 <span data-ttu-id="5a319-121">[Master Data Services de importação de dados &#40;&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5a319-121">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="5a319-122">Solucionando problemas do processo de preparo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5a319-122">Troubleshooting the Staging Process (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-the-staging-process-master-data-services.aspx)  
  
  
