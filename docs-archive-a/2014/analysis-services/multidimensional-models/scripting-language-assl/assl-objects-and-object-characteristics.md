---
title: Objetos ASSL e características de objeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- reference exceptions [Analysis Services Scripting Language]
- ASSL, objects
- inheritance [Analysis Services Scripting Language]
- localized names [Analysis Services Scripting Language]
- objects [Analysis Services Scripting Language]
- names [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
- expansion [Analysis Services Scripting Language]
ms.assetid: 6e5c28b5-c0bc-4ccd-82e5-e174bbb71386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d57bb421a7f486983476a6549a5121ce88ee9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576027"
---
# <a name="assl-objects-and-object-characteristics"></a><span data-ttu-id="d7fda-102">Objetos e características de objeto ASSL</span><span class="sxs-lookup"><span data-stu-id="d7fda-102">ASSL Objects and Object Characteristics</span></span>
  <span data-ttu-id="d7fda-103">Os objetos da ASSL (Analysis Services Scripting Language) seguem diretrizes específicas a respeito de grupos de objetos, herança, nomenclatura, expansão e processamento.</span><span class="sxs-lookup"><span data-stu-id="d7fda-103">Objects in Analysis Services Scripting Language (ASSL) follow specific guidelines in regards to object groups, inheritance, naming, expansion, and processing.</span></span>  
  
## <a name="object-groups"></a><span data-ttu-id="d7fda-104">Grupos de objetos</span><span class="sxs-lookup"><span data-stu-id="d7fda-104">Object Groups</span></span>  
 <span data-ttu-id="d7fda-105">Todos os [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objetos têm uma representação XML.</span><span class="sxs-lookup"><span data-stu-id="d7fda-105">All [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects have an XML representation.</span></span> <span data-ttu-id="d7fda-106">Os objetos estão divididos em dois grupos:</span><span class="sxs-lookup"><span data-stu-id="d7fda-106">The objects are divided into two groups:</span></span>  
  
 <span data-ttu-id="d7fda-107">**Objetos principais**</span><span class="sxs-lookup"><span data-stu-id="d7fda-107">**Major objects**</span></span>  
 <span data-ttu-id="d7fda-108">Os objetos principais podem ser criados, alterados e excluídos de forma independente.</span><span class="sxs-lookup"><span data-stu-id="d7fda-108">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="d7fda-109">Entre eles, estão incluídos:</span><span class="sxs-lookup"><span data-stu-id="d7fda-109">Major objects include:</span></span>  
  
-   <span data-ttu-id="d7fda-110">Servidores</span><span class="sxs-lookup"><span data-stu-id="d7fda-110">Servers</span></span>  
  
-   <span data-ttu-id="d7fda-111">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="d7fda-111">Databases</span></span>  
  
-   <span data-ttu-id="d7fda-112">Dimensões</span><span class="sxs-lookup"><span data-stu-id="d7fda-112">Dimensions</span></span>  
  
-   <span data-ttu-id="d7fda-113">Cubes</span><span class="sxs-lookup"><span data-stu-id="d7fda-113">Cubes</span></span>  
  
-   <span data-ttu-id="d7fda-114">Grupos de medidas</span><span class="sxs-lookup"><span data-stu-id="d7fda-114">Measure groups</span></span>  
  
-   <span data-ttu-id="d7fda-115">Partições</span><span class="sxs-lookup"><span data-stu-id="d7fda-115">Partitions</span></span>  
  
-   <span data-ttu-id="d7fda-116">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="d7fda-116">Perspectives</span></span>  
  
-   <span data-ttu-id="d7fda-117">Modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="d7fda-117">Mining models</span></span>  
  
-   <span data-ttu-id="d7fda-118">Funções</span><span class="sxs-lookup"><span data-stu-id="d7fda-118">Roles</span></span>  
  
-   <span data-ttu-id="d7fda-119">Comandos associados a um servidor ou a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="d7fda-119">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="d7fda-120">Fontes de dados</span><span class="sxs-lookup"><span data-stu-id="d7fda-120">Data sources</span></span>  
  
 <span data-ttu-id="d7fda-121">Os objetos principais têm as seguintes propriedades para o rastreamento de seu histórico e de seu status.</span><span class="sxs-lookup"><span data-stu-id="d7fda-121">Major objects have the following properties to track their history and status.</span></span>  
  
-   `CreatedTimestamp`  
  
-   `LastSchemaUpdate`  
  
-   <span data-ttu-id="d7fda-122">`LastProcessed` (onde apropriado)</span><span class="sxs-lookup"><span data-stu-id="d7fda-122">`LastProcessed` (where appropriate)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7fda-123">A classificação de um objeto como um objeto principal afeta a forma como uma instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] tratará esse objeto e como ele será manipulado na linguagem de definição de objeto.</span><span class="sxs-lookup"><span data-stu-id="d7fda-123">The classification of an object as a major object affects how an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] treats that object and how that object is handled in the object definition language.</span></span> <span data-ttu-id="d7fda-124">No entanto, essa classificação não garante que as ferramentas de desenvolvimento e de gerenciamento do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] permitirão a criação, a modificação ou a exclusão independente desses objetos.</span><span class="sxs-lookup"><span data-stu-id="d7fda-124">However, this classification does not guarantee that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] management and development tools will allow the independent creation, modification, or deletion of these objects.</span></span>  
  
 <span data-ttu-id="d7fda-125">**Objetos secundários**</span><span class="sxs-lookup"><span data-stu-id="d7fda-125">**Minor objects**</span></span>  
 <span data-ttu-id="d7fda-126">Os objetos secundários só podem ser criados, alterados ou excluídos como parte da criação, da alteração ou da exclusão do objeto principal pai.</span><span class="sxs-lookup"><span data-stu-id="d7fda-126">Minor objects can only be created, altered, or deleted as part of creating, altering, or deleting the parent major object.</span></span> <span data-ttu-id="d7fda-127">Entre eles, estão incluídos:</span><span class="sxs-lookup"><span data-stu-id="d7fda-127">Minor objects include:</span></span>  
  
-   <span data-ttu-id="d7fda-128">Hierarquias e níveis</span><span class="sxs-lookup"><span data-stu-id="d7fda-128">Hierarchies and levels</span></span>  
  
-   <span data-ttu-id="d7fda-129">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7fda-129">Attributes</span></span>  
  
-   <span data-ttu-id="d7fda-130">Medidas</span><span class="sxs-lookup"><span data-stu-id="d7fda-130">Measures</span></span>  
  
-   <span data-ttu-id="d7fda-131">Colunas do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="d7fda-131">Mining model columns</span></span>  
  
-   <span data-ttu-id="d7fda-132">Comandos associados a um cubo</span><span class="sxs-lookup"><span data-stu-id="d7fda-132">Commands associated with a cube</span></span>  
  
-   <span data-ttu-id="d7fda-133">Agregações</span><span class="sxs-lookup"><span data-stu-id="d7fda-133">Aggregations</span></span>  
  
## <a name="object-expansion"></a><span data-ttu-id="d7fda-134">Expansão de objetos</span><span class="sxs-lookup"><span data-stu-id="d7fda-134">Object Expansion</span></span>  
 <span data-ttu-id="d7fda-135">A restrição `ObjectExpansion` pode ser usada para controlar o grau de expansão do XML ASSL retornado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="d7fda-135">The `ObjectExpansion` restriction can be used to control the degree of expansion of ASSL XML returned by the server.</span></span> <span data-ttu-id="d7fda-136">As opções dessa restrição estão relacionadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d7fda-136">This restriction has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d7fda-137">Valor de enumeração</span><span class="sxs-lookup"><span data-stu-id="d7fda-137">Enumeration value</span></span>|<span data-ttu-id="d7fda-138">Permitido para\<Alter></span><span class="sxs-lookup"><span data-stu-id="d7fda-138">Allowed for \<Alter></span></span>|<span data-ttu-id="d7fda-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7fda-139">Description</span></span>|  
|-----------------------|---------------------------|-----------------|  
|<span data-ttu-id="d7fda-140">*ReferenceOnly*</span><span class="sxs-lookup"><span data-stu-id="d7fda-140">*ReferenceOnly*</span></span>|<span data-ttu-id="d7fda-141">no</span><span class="sxs-lookup"><span data-stu-id="d7fda-141">no</span></span>|<span data-ttu-id="d7fda-142">Retorna somente o nome, a ID e o carimbo de data/hora do objeto solicitado e de todos os objetos principais contidos de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="d7fda-142">Returns only the name, ID, and timestamp for the requested object and for all contained major objects recursively.</span></span>|  
|<span data-ttu-id="d7fda-143">*ObjectProperties*</span><span class="sxs-lookup"><span data-stu-id="d7fda-143">*ObjectProperties*</span></span>|<span data-ttu-id="d7fda-144">sim</span><span class="sxs-lookup"><span data-stu-id="d7fda-144">yes</span></span>|<span data-ttu-id="d7fda-145">Expande o objeto solicitado e os objetos secundários contidos, mas não retorna objetos principais contidos.</span><span class="sxs-lookup"><span data-stu-id="d7fda-145">Expands the requested object and minor contained objects, but does not return major contained objects.</span></span>|  
|<span data-ttu-id="d7fda-146">*Expandobject*</span><span class="sxs-lookup"><span data-stu-id="d7fda-146">*ExpandObject*</span></span>|<span data-ttu-id="d7fda-147">no</span><span class="sxs-lookup"><span data-stu-id="d7fda-147">no</span></span>|<span data-ttu-id="d7fda-148">Igual a *ObjectProperties*, mas também retorna o nome, a ID e o carimbo de data/hora para os principais objetos contidos.</span><span class="sxs-lookup"><span data-stu-id="d7fda-148">Same as *ObjectProperties*, but also returns the name, ID, and timestamp for contained major objects.</span></span>|  
|<span data-ttu-id="d7fda-149">*ExpandFull*</span><span class="sxs-lookup"><span data-stu-id="d7fda-149">*ExpandFull*</span></span>|<span data-ttu-id="d7fda-150">sim</span><span class="sxs-lookup"><span data-stu-id="d7fda-150">yes</span></span>|<span data-ttu-id="d7fda-151">Expande completamente o objeto solicitado e todos os objetos recursivamente.</span><span class="sxs-lookup"><span data-stu-id="d7fda-151">Fully expands the requested object and all contained objects recursively.</span></span>|  
  
 <span data-ttu-id="d7fda-152">Esta seção de referência de ASSL descreve a representação *ExpandFull* .</span><span class="sxs-lookup"><span data-stu-id="d7fda-152">This ASSL reference section describes the *ExpandFull* representation.</span></span> <span data-ttu-id="d7fda-153">Todos os outros níveis de `ObjectExpansion` derivam desse nível.</span><span class="sxs-lookup"><span data-stu-id="d7fda-153">All other `ObjectExpansion` levels are derived from this level.</span></span>  
  
## <a name="object-processing"></a><span data-ttu-id="d7fda-154">Processamento de objetos</span><span class="sxs-lookup"><span data-stu-id="d7fda-154">Object Processing</span></span>  
 <span data-ttu-id="d7fda-155">A ASSL inclui elementos ou propriedades somente leitura (por exemplo, `LastProcessed`) que podem ser lidos na instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], mas que são omitidos quando os scripts de comando são enviados à instância.</span><span class="sxs-lookup"><span data-stu-id="d7fda-155">ASSL includes read-only elements or properties (for example, `LastProcessed`) that can be read from the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, but which are omitted when command scripts are submitted to the instance.</span></span> <span data-ttu-id="d7fda-156">O [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ignora valores modificados para elementos somente leitura sem aviso ou erro.</span><span class="sxs-lookup"><span data-stu-id="d7fda-156">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ignores modified values for read-only elements without warning or error.</span></span>  
  
 <span data-ttu-id="d7fda-157">O [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] também ignora propriedades impróprias ou irrelevantes sem gerar erros de validação.</span><span class="sxs-lookup"><span data-stu-id="d7fda-157">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] also ignores inappropriate or irrelevant properties without raising validation errors.</span></span> <span data-ttu-id="d7fda-158">Por exemplo, o elemento X só deve estar presente quando o elemento Y tiver um valor específico.</span><span class="sxs-lookup"><span data-stu-id="d7fda-158">For example, the X element should only be present when the Y element has a particular value.</span></span> <span data-ttu-id="d7fda-159">A instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ignora o elemento X em vez de validar aquele elemento em relação ao valor do elemento Y.</span><span class="sxs-lookup"><span data-stu-id="d7fda-159">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance ignores the X element instead of validating that element against the value of the Y element.</span></span>  
  
  
