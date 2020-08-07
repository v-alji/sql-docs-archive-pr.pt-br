---
title: Operações de serviço Web categorizadas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e3f346b5-7e26-481d-9821-1846e2e91289
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0f7dd682f55c16c6dcbff9f0f669593a10486da6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581443"
---
# <a name="categorized-web-service-operations-master-data-services"></a><span data-ttu-id="79ad7-102">Operações de serviço Web categorizadas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="79ad7-102">Categorized Web Service Operations (Master Data Services)</span></span>
  <span data-ttu-id="79ad7-103">O serviço Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] contém um conjunto completo de operações que permitem a você escrever código para controlar todos os recursos que o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] usa por meio de sua interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="79ad7-103">The [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service contains a complete set of operations that let you write code to control all of the features that [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] does through its user interface.</span></span> <span data-ttu-id="79ad7-104">As operações de serviço Web são definidas pela interface <xref:Microsoft.MasterDataServices.IService> e são implementadas como métodos na classe <xref:Microsoft.MasterDataServices.ServiceClient>.</span><span class="sxs-lookup"><span data-stu-id="79ad7-104">The web service operations are defined by the <xref:Microsoft.MasterDataServices.IService> interface and are implemented as methods in the <xref:Microsoft.MasterDataServices.ServiceClient> class.</span></span> <span data-ttu-id="79ad7-105">Este tópico agrupa as operações do serviço Web em categorias conceituais para ajudá-lo a entender como usar a API do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="79ad7-105">This topic groups the web service operations into conceptual categories to help you understand how to use the web service API.</span></span>  
  
## <a name="model-operations"></a><span data-ttu-id="79ad7-106">Operações de modelo</span><span class="sxs-lookup"><span data-stu-id="79ad7-106">Model Operations</span></span>  
 <span data-ttu-id="79ad7-107">Estas operações são usadas para criar, atualizar e excluir modelos, bem como operar em todos os conteúdos de um modelo, como entidades, hierarquias e versões.</span><span class="sxs-lookup"><span data-stu-id="79ad7-107">These operations are used to create, update, and delete models, as well as to operate on all the contents of a model, such as entities, hierarchies, and versions.</span></span> <span data-ttu-id="79ad7-108">Para obter mais informações, consulte [Modelos &#40;Master Data Services&#41;](../models-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-108">For more information, see [Models &#40;Master Data Services&#41;](../models-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>|  
  
## <a name="entity-operations"></a><span data-ttu-id="79ad7-109">Operações de entidade</span><span class="sxs-lookup"><span data-stu-id="79ad7-109">Entity Operations</span></span>  
 <span data-ttu-id="79ad7-110">Estas operações são usadas para criar, atualizar e excluir os membros de uma única entidade.</span><span class="sxs-lookup"><span data-stu-id="79ad7-110">These operations are used to create, update, and delete the members of a single entity.</span></span> <span data-ttu-id="79ad7-111">Para obter mais informações, consulte [Entidades &#40;Master Data Services&#41;](../entities-master-data-services.md) e [Membros &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-111">For more information, see [Entities &#40;Master Data Services&#41;](../entities-master-data-services.md) and [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberKeyLookup%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersUpdate%2A>|  
  
## <a name="member-operations"></a><span data-ttu-id="79ad7-112">Operações de membro</span><span class="sxs-lookup"><span data-stu-id="79ad7-112">Member Operations</span></span>  
 <span data-ttu-id="79ad7-113">Estas operações são usadas para obter, atualizar e excluir os membros.</span><span class="sxs-lookup"><span data-stu-id="79ad7-113">These operations are used to get, update, and delete members.</span></span> <span data-ttu-id="79ad7-114">O conjunto de membros operado pode conter membros de várias entidades.</span><span class="sxs-lookup"><span data-stu-id="79ad7-114">The set of members operated on can contain members from multiple entities.</span></span> <span data-ttu-id="79ad7-115">Para obter mais informações, consulte [Membros &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-115">For more information, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersGet%2A>|  
  
## <a name="attribute-and-hierarchy-operations"></a><span data-ttu-id="79ad7-116">Operações de atributo e hierarquia</span><span class="sxs-lookup"><span data-stu-id="79ad7-116">Attribute and Hierarchy Operations</span></span>  
 <span data-ttu-id="79ad7-117">Estas operações são usadas para obter informações sobre atributos e hierarquias.</span><span class="sxs-lookup"><span data-stu-id="79ad7-117">These operations are used to get attribute and hierarchy information.</span></span> <span data-ttu-id="79ad7-118">Atributos e hierarquias também podem ser modificados com o uso das operações de modelo, como <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span><span class="sxs-lookup"><span data-stu-id="79ad7-118">Attributes and hierarchies can also be modified by using the model operations, such as <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span></span> <span data-ttu-id="79ad7-119">Para obter mais informações, consulte [Atributos &#40;Master Data Services&#41;](../attributes-master-data-services.md) e [Hierarquias &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-119">For more information, see [Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) and [Hierarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAttributesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.HierarchyMembersGet%2A>|  
  
## <a name="business-rule-operations"></a><span data-ttu-id="79ad7-120">Operações de regra de negócio</span><span class="sxs-lookup"><span data-stu-id="79ad7-120">Business Rule Operations</span></span>  
 <span data-ttu-id="79ad7-121">Estas operações são usadas para criar, atualizar, excluir e publicar regras de negócios.</span><span class="sxs-lookup"><span data-stu-id="79ad7-121">These operations are used to create, update, delete, and publish business rules.</span></span> <span data-ttu-id="79ad7-122">Para obter mais informações, consulte [Regras de negócio &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-122">For more information, see [Business Rules &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPaletteGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPublish%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesUpdate%2A>|  
  
## <a name="annotation-operations"></a><span data-ttu-id="79ad7-123">Operações de anotação</span><span class="sxs-lookup"><span data-stu-id="79ad7-123">Annotation Operations</span></span>  
 <span data-ttu-id="79ad7-124">Estas operações são usadas para criar, atualizar e excluir anotações.</span><span class="sxs-lookup"><span data-stu-id="79ad7-124">These operations are used to create, update, and delete annotations.</span></span> <span data-ttu-id="79ad7-125">Para obter mais informações, consulte [Anotações &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-125">For more information, see [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsGet%2A>|  
  
## <a name="transaction-operations"></a><span data-ttu-id="79ad7-126">Operações de transação</span><span class="sxs-lookup"><span data-stu-id="79ad7-126">Transaction Operations</span></span>  
 <span data-ttu-id="79ad7-127">Estas operações são usadas para obter e reverter transações.</span><span class="sxs-lookup"><span data-stu-id="79ad7-127">These operations are used to get and reverse transactions.</span></span> <span data-ttu-id="79ad7-128">Para obter mais informações, consulte [Transações &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-128">For more information, see [Transactions &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsReverse%2A>|  
  
## <a name="version-and-validation-operations"></a><span data-ttu-id="79ad7-129">Operações de versão e validação</span><span class="sxs-lookup"><span data-stu-id="79ad7-129">Version and Validation Operations</span></span>  
 <span data-ttu-id="79ad7-130">Estas operações são usadas para copiar e validar versões.</span><span class="sxs-lookup"><span data-stu-id="79ad7-130">These operations are used to copy and validate versions.</span></span> <span data-ttu-id="79ad7-131">Para obter mais informações, consulte [Versões &#40;Master Data Services&#41;](../versions-master-data-services.md) e [Validação &#40;Master Data Services&#41;](../validation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-131">For more information, see [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) and [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.VersionCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationProcess%2A>|  
  
## <a name="data-quality-operations"></a><span data-ttu-id="79ad7-132">Operações de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="79ad7-132">Data Quality Operations</span></span>  
 <span data-ttu-id="79ad7-133">Estas operações são usadas para executar tarefas de qualidade de dados e examinar seus resultados.</span><span class="sxs-lookup"><span data-stu-id="79ad7-133">These operations are used to perform data quality tasks and to examine their results.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityCleansingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityMatchingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStart%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityInstalledState%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityKnowledgeBasesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationResultsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStatus%2A>|  
  
## <a name="data-import-operations"></a><span data-ttu-id="79ad7-134">Operações de importação de dados</span><span class="sxs-lookup"><span data-stu-id="79ad7-134">Data Import Operations</span></span>  
 <span data-ttu-id="79ad7-135">Estas operações são usadas para importar dados para um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79ad7-135">These operations are used to import data into a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="79ad7-136">Para obter mais informações, consulte [Importação de dados &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-136">For more information, see [Data Import &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingLoad%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingProcess%2A>|  
  
 <span data-ttu-id="79ad7-137">As operações a seguir são usadas para importar dados utilizando o processo de preparo incluído no [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79ad7-137">The following operations are used to import data by using the staging process included in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="79ad7-138">Estas operações só devem ser usadas para dar suporte aos bancos de dados existentes.</span><span class="sxs-lookup"><span data-stu-id="79ad7-138">These operations should be used only to support existing databases.</span></span> <span data-ttu-id="79ad7-139">Para um novo desenvolvimento, use as operações listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="79ad7-139">For new development, use the previously listed operations.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingNameCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingProcess%2A>|  
  
## <a name="data-export-operations"></a><span data-ttu-id="79ad7-140">Operações de exportação de dados</span><span class="sxs-lookup"><span data-stu-id="79ad7-140">Data Export Operations</span></span>  
 <span data-ttu-id="79ad7-141">Estas operações são usadas para exportar dados por meio do uso de exibições de assinatura.</span><span class="sxs-lookup"><span data-stu-id="79ad7-141">These operations are used to export data through the use of subscription views.</span></span> <span data-ttu-id="79ad7-142">Para obter mais informações, consulte [exportando dados &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-142">For more information, see [Exporting Data &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewUpdate%2A>|  
  
## <a name="security-operations"></a><span data-ttu-id="79ad7-143">Operações de segurança</span><span class="sxs-lookup"><span data-stu-id="79ad7-143">Security Operations</span></span>  
 <span data-ttu-id="79ad7-144">Estas operações são usadas para modificar as configurações de segurança que controlam o acesso ao banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79ad7-144">These operations are used to modify the security settings that control access to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="79ad7-145">Para obter mais informações, consulte [Segurança &#40;Master Data Services&#41;](../security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79ad7-145">For more information, see [Security &#40;Master Data Services&#41;](../security-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesUpdate%2A>|  
  
## <a name="system-operations"></a><span data-ttu-id="79ad7-146">Operações de sistema</span><span class="sxs-lookup"><span data-stu-id="79ad7-146">System Operations</span></span>  
 <span data-ttu-id="79ad7-147">Estas operações são usadas para obter e atualizar configurações de sistema e preferências do usuário.</span><span class="sxs-lookup"><span data-stu-id="79ad7-147">These operations are used to get and update system settings and user preferences.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceVersionGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemDomainListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemPropertiesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesUpdate%2A>|  
  
  
