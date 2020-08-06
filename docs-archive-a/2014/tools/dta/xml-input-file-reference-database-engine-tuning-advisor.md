---
title: Referência do arquivo de entrada XML (Orientador de Otimização do Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], XML input files
- input file reference [Database Engine Tuning Advisor]
- XML input files [Database Engine Tuning Advisor]
ms.assetid: 05e5e5f0-d6df-4336-b18e-e9bc2835a766
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3bbd38299e4921db33cbaf318883c2f0a9041d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685394"
---
# <a name="xml-input-file-reference-database-engine-tuning-advisor"></a><span data-ttu-id="4d394-102">Referência do arquivo de entrada XML (Orientador de Otimização do Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="4d394-102">XML Input File Reference (Database Engine Tuning Advisor)</span></span>
  [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="4d394-103">pode usar um arquivo de entrada XML para ajustar o banco de dados</span><span class="sxs-lookup"><span data-stu-id="4d394-103">Tuning Advisor can use an XML input file to tune a database.</span></span> <span data-ttu-id="4d394-104">Este arquivo XML define os bancos de dados, tabelas, arquivos ou tabelas da carga de trabalho e as opções a serem usadas na sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="4d394-104">This XML file designates which databases, tables, workload files or tables, and tuning options to use for the tuning session.</span></span> <span data-ttu-id="4d394-105">Você também pode usar este arquivo para indicar uma configuração específica de usuário a fim de realizar uma análise hipotética.</span><span class="sxs-lookup"><span data-stu-id="4d394-105">You can also use this file to specify a user-specified configuration to perform "what-if" analysis.</span></span>  
  
 <span data-ttu-id="4d394-106">O arquivo de entrada do Orientador de Otimização do [!INCLUDE[ssDE](../../includes/ssde-md.md)] contém uma hierarquia de elementos XML, cada qual contendo um texto ou outros elementos que especificam os parâmetros da sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="4d394-106">A [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file contains a hierarchy of XML elements, each containing text or other elements that specify the tuning session settings.</span></span> <span data-ttu-id="4d394-107">O arquivo de entrada XML do Orientador de Otimização do [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve seguir os padrões do XML bem formado para que todos os nomes dos elementos diferenciem letras maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4d394-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file must conform to the standards for well-formed XML, so all element names are case sensitive.</span></span> <span data-ttu-id="4d394-108">Os elementos são especificados usando a caixa Pascal, o que significa que o primeiro caractere está em maiúscula e a primeira letra de qualquer palavra concatenada subsequente está em maiúscula.</span><span class="sxs-lookup"><span data-stu-id="4d394-108">Elements are specified using Pascal case, which means that the first character is uppercase and the first letter of any subsequent concatenated word is uppercase.</span></span>  
  
 <span data-ttu-id="4d394-109">Todos os valores de elementos devem seguir as convenções de nomenclatura XML.</span><span class="sxs-lookup"><span data-stu-id="4d394-109">All element values must conform to XML naming conventions.</span></span> <span data-ttu-id="4d394-110">Para obter mais informações sobre essas convenções, consulte o [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) na MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="4d394-110">For more information about these conventions, see [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="4d394-111">Observe que esta referência não é abrangente.</span><span class="sxs-lookup"><span data-stu-id="4d394-111">Note that this reference is not comprehensive.</span></span> <span data-ttu-id="4d394-112">Para obter informações sobre todos os elementos que você pode usar para definir a entrada XML, consulte DTASchema.xds, o esquema XML do Orientador de Otimização do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d394-112">For information about all the elements you can use to define XML input, refer to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML schema, DTASchema.xsd.</span></span>  
  
## <a name="xml-declaration"></a><span data-ttu-id="4d394-113">Declaração XML</span><span class="sxs-lookup"><span data-stu-id="4d394-113">XML Declaration</span></span>  
  
-   [<span data-ttu-id="4d394-114">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-114">XML Data &#40;SQL Server&#41;</span></span>](../../relational-databases/xml/xml-data-sql-server.md)  
  
## <a name="dtaxml-root-element"></a><span data-ttu-id="4d394-115">Elemento raiz DTAXML</span><span class="sxs-lookup"><span data-stu-id="4d394-115">DTAXML Root Element</span></span>  
  
-   [<span data-ttu-id="4d394-116">Elemento DTAXML &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-116">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)  
  
## <a name="dtainput-elements"></a><span data-ttu-id="4d394-117">Elementos DTAInput</span><span class="sxs-lookup"><span data-stu-id="4d394-117">DTAInput Elements</span></span>  
  
-   [<span data-ttu-id="4d394-118">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)  
  
-   [<span data-ttu-id="4d394-119">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-119">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)  
  
-   [<span data-ttu-id="4d394-120">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)  
  
-   [<span data-ttu-id="4d394-121">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-121">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)  
  
-   [<span data-ttu-id="4d394-122">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-122">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)  
  
## <a name="server-elements"></a><span data-ttu-id="4d394-123">Elementos de servidor</span><span class="sxs-lookup"><span data-stu-id="4d394-123">Server Elements</span></span>  
  
-   [<span data-ttu-id="4d394-124">Elemento Name para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-124">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)  
  
-   [<span data-ttu-id="4d394-125">Elemento Database para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-125">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)  
  
## <a name="workload-elements"></a><span data-ttu-id="4d394-126">Elementos de Carga de Trabalho</span><span class="sxs-lookup"><span data-stu-id="4d394-126">Workload Elements</span></span>  
  
-   [<span data-ttu-id="4d394-127">Elemento File &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-127">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)  
  
-   [<span data-ttu-id="4d394-128">Elemento Database para Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-128">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)  
  
-   [<span data-ttu-id="4d394-129">Elemento EventString &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-129">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)  
  
## <a name="tuning-options-elements"></a><span data-ttu-id="4d394-130">Elementos de opções de ajuste</span><span class="sxs-lookup"><span data-stu-id="4d394-130">Tuning Options Elements</span></span>  
  
-   [<span data-ttu-id="4d394-131">Elemento TuningTimeInMin &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-131">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)  
  
-   [<span data-ttu-id="4d394-132">Elemento StorageBoundInMB &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-132">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)  
  
-   [<span data-ttu-id="4d394-133">Elemento TestServer &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-133">TestServer Element &#40;DTA&#41;</span></span>](testserver-element-dta.md)  
  
-   [<span data-ttu-id="4d394-134">Elemento FeatureSet &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-134">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)  
  
-   [<span data-ttu-id="4d394-135">Elemento Partitioning &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-135">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)  
  
-   [<span data-ttu-id="4d394-136">Elemento DropOnlyMode &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-136">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)  
  
-   [<span data-ttu-id="4d394-137">Elemento KeepExisting &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-137">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)  
  
-   [<span data-ttu-id="4d394-138">Elemento OnlineIndexOperation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-138">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)  
  
-   [<span data-ttu-id="4d394-139">Elemento DatabaseToConnect &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-139">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)  
  
## <a name="configuration-elements"></a><span data-ttu-id="4d394-140">Elementos de configuração</span><span class="sxs-lookup"><span data-stu-id="4d394-140">Configuration Elements</span></span>  
  
-   [<span data-ttu-id="4d394-141">Elemento Server para Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-141">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="4d394-142">Elemento Database para Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-142">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="4d394-143">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-143">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)  
  
-   [<span data-ttu-id="4d394-144">Elemento Create &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-144">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)  
  
-   [<span data-ttu-id="4d394-145">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-145">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)  
  
-   [<span data-ttu-id="4d394-146">Elemento Name para o índice &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-146">Name Element for Index &#40;DTA&#41;</span></span>](name-element-for-index-dta.md)  
  
-   [<span data-ttu-id="4d394-147">Elemento Column para Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-147">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)  
  
-   [<span data-ttu-id="4d394-148">Elemento Name para coluna &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-148">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)  
  
-   [<span data-ttu-id="4d394-149">Elemento Filegroup para o índice &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-149">Filegroup Element for Index &#40;DTA&#41;</span></span>](filegroup-element-for-index-dta.md)  
  
## <a name="database-elements"></a><span data-ttu-id="4d394-150">Elementos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="4d394-150">Database Elements</span></span>  
  
-   [<span data-ttu-id="4d394-151">Elemento Name para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-151">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)  
  
-   [<span data-ttu-id="4d394-152">Elemento Schema para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-152">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)  
  
-   [<span data-ttu-id="4d394-153">Elemento Name para Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-153">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="4d394-154">Elemento Table para Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-154">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="4d394-155">Elemento Name para Table &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-155">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d394-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d394-156">See Also</span></span>  
 [<span data-ttu-id="4d394-157">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="4d394-157">Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
