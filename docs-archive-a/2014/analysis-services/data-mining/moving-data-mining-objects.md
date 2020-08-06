---
title: Movendo objetos de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], models
- data mining editor [Analysis Services]
- mining models [Analysis Services], managing
- Data Mining Designer
- mining models [Analysis Services], modifying
ms.assetid: bc108407-2603-4387-b930-b5bb9df78069
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b10be3a79487376b173eab87059404b7f7a618e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679099"
---
# <a name="moving-data-mining-objects"></a><span data-ttu-id="76661-102">Movendo objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="76661-102">Moving Data Mining Objects</span></span>
  <span data-ttu-id="76661-103">Os cenários mais comuns para mover objetos de mineração de dados são implantar um modelo de um ambiente de teste ou análise para um ambiente de produção ou compartilhar modelos com outros usuários.</span><span class="sxs-lookup"><span data-stu-id="76661-103">The most common scenarios for moving data mining objects are to deploy a model from a testing or analysis environment to a production environment, or to share models with other users.</span></span>  
  
 <span data-ttu-id="76661-104">Este tópico descreve como você pode usar as ferramentas e as linguagens de scripts fornecidas pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], para mover objetos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="76661-104">This topic describes how you can use the tools and scripting languages provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], for moving data mining objects.</span></span>  
  
## <a name="moving-data-mining-objects-between-databases-or-servers"></a><span data-ttu-id="76661-105">Movendo objetos de mineração de dados entre bancos de dados ou servidores</span><span class="sxs-lookup"><span data-stu-id="76661-105">Moving Data Mining Objects between Databases or Servers</span></span>  
 <span data-ttu-id="76661-106">Você pode mover objetos de mineração de dados entre os bancos de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou entre instâncias do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="76661-106">You can move data mining objects between [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases or between instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="76661-107">Reimplantando a solução em um banco de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="76661-107">Re-deploying the solution to a different database.</span></span>  
  
-   <span data-ttu-id="76661-108">Criando scripts de objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="76661-108">Scripting individual objects.</span></span>  
  
-   <span data-ttu-id="76661-109">Fazendo backup e restaurando uma cópia do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="76661-109">Backing up and then restoring a copy of the database.</span></span>  
  
-   <span data-ttu-id="76661-110">Exportando e importando estruturas e modelos.</span><span class="sxs-lookup"><span data-stu-id="76661-110">Exporting and importing structures and models.</span></span>  
  
 <span data-ttu-id="76661-111">As seções a seguir explicam essas opções em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="76661-111">The following section explains these options in more detail.</span></span>  
  
### <a name="deploying"></a><span data-ttu-id="76661-112">Implantando</span><span class="sxs-lookup"><span data-stu-id="76661-112">Deploying</span></span>  
 <span data-ttu-id="76661-113">Implantar a solução em um servidor ou banco de dados diferente exige que você tenha o arquivo de solução que foi criado usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76661-113">Deploying the solution to a different server or database requires that you have the solution file that was created by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="76661-114">Para obter mais informações sobre como implantar soluções do Analysis Services, consulte [Implantar projetos do Analysis Services &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="76661-114">For more information about deploying Analysis Services solutions, see [Deploy Analysis Services Projects &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span></span>  
  
### <a name="scripting"></a><span data-ttu-id="76661-115">Scripting</span><span class="sxs-lookup"><span data-stu-id="76661-115">Scripting</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="76661-116">fornece vários idiomas que você pode usar para criar script de objetos.</span><span class="sxs-lookup"><span data-stu-id="76661-116">provides several languages that you can use to script objects.</span></span>  
  
-   <span data-ttu-id="76661-117">**XMLA**: você pode criar scripts de objetos usando o XMLA clicando com o botão direito do mouse nos objetos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76661-117">**XMLA**: You can script objects using XMLA by right-clicking objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="76661-118">Para executar o script, abra-o na janela **Consulta XMLA** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="76661-118">To execute the script, open it in an **XMLA Query** window on the target server.</span></span>  
  
-   <span data-ttu-id="76661-119">**DMX**: você pode criar scripts usando modelos ou um dos construtores de consulta fornecidos no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] e no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76661-119">**DMX**: You can create scripts by using templates or one of the query builders provided in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="76661-120">Observe, no entanto, que há diferenças nas tarefas que você pode executar com cada linguagem de scripts:</span><span class="sxs-lookup"><span data-stu-id="76661-120">Note, however, that there are differences in the tasks that you can perform with each scripting language:</span></span>  
  
-   <span data-ttu-id="76661-121">As propriedades como a descrição de objetos e as associações de dados só podem ser criadas ou alteradas usando as linguagens de DDL do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , não usando DMX.</span><span class="sxs-lookup"><span data-stu-id="76661-121">Properties such as the object description and data bindings can only by created or changed by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL languages, not by using DMX.</span></span>  
  
-   <span data-ttu-id="76661-122">Somente o DMX dá suporte à importação e exportação de objetos de mineração.</span><span class="sxs-lookup"><span data-stu-id="76661-122">Only DMX supports the import and export of mining objects.</span></span>  
  
-   <span data-ttu-id="76661-123">Somente o DMX dá suporte à geração de PMML ou importação de definições de modelo de PMML.</span><span class="sxs-lookup"><span data-stu-id="76661-123">Only DMX supports generating PMML or importing model definitions from PMML.</span></span>  
  
-   <span data-ttu-id="76661-124">Somente o DMX dá suporte ao treinamento de um modelo com dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="76661-124">Only DMX supports training a model with application data.</span></span> <span data-ttu-id="76661-125">Além disso, a instrução DMX INSERT INTO dá suporte a treinamento de um modelo sem fornecer valores para uma coluna de chave.</span><span class="sxs-lookup"><span data-stu-id="76661-125">Moreover, the DMX INSERT INTO statement supports training a model without providing values for a key column.</span></span>  
  
 <span data-ttu-id="76661-126">Para obter mais informações, consulte [Desenvolvendo com ASSL &#40;linguagem de script do Analysis Services&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="76661-126">For more information, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
### <a name="backup-and-restore"></a><span data-ttu-id="76661-127">Backup e restauração</span><span class="sxs-lookup"><span data-stu-id="76661-127">Backup and Restore</span></span>  
 <span data-ttu-id="76661-128">Backup e restauração de um banco de dados inteiro do Analysis Services é o método preferencial se a sua solução de mineração de dados utiliza objetos OLAP.</span><span class="sxs-lookup"><span data-stu-id="76661-128">Backup and restore of an entire Analysis Services database is the method of choice if your data mining solution relies on OLAP objects.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="76661-129">oferece a funcionalidade de backup e restauração que agiliza e simplifica os backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="76661-129">provides backup and restore functionality that makes database backups faster and easier.</span></span>  
  
 <span data-ttu-id="76661-130">Para obter informações sobre o backup, consulte [Backup e restauração de Bancos de Dados do Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="76661-130">For more information about backup, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
### <a name="exporting-and-importing"></a><span data-ttu-id="76661-131">Exportando e importando</span><span class="sxs-lookup"><span data-stu-id="76661-131">Exporting and Importing</span></span>  
 <span data-ttu-id="76661-132">Exportar e, em seguida, reimportar os modelos e as estruturas de mineração usando instruções DMX é a maneira mais fácil de mover ou fazer backup de objetos de mineração de dados relacionais individuais.</span><span class="sxs-lookup"><span data-stu-id="76661-132">Exporting and then re-importing mining models and structures by using DMX statements is the easiest way to move or back up individual relational data mining objects.</span></span> <span data-ttu-id="76661-133">Para obter mais informações sobre a sintaxe DMX para essas operações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="76661-133">For more information about the DMX syntax for these operations, see the following topics:</span></span>  
  
-   [<span data-ttu-id="76661-134">EXPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="76661-134">EXPORT &#40;DMX&#41;</span></span>](/sql/dmx/export-dmx)  
  
-   [<span data-ttu-id="76661-135">IMPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="76661-135">IMPORT &#40;DMX&#41;</span></span>](/sql/dmx/import-dmx)  
  
 <span data-ttu-id="76661-136">Se você especificar a opção INCLUDE DEPENDENCIES, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] também exportará a definição de qualquer exibição da fonte de dados necessária e, quando você importar o modelo ou a estrutura, ele recriará a exibição da fonte de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="76661-136">If you specify the INCLUDE DEPENDENCIES option, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will also export the definition of any required data source views, and when you import the model or structure, it will re-create the data source view on the target server.</span></span> <span data-ttu-id="76661-137">Depois que você terminar de importar o modelo, defina as permissões de mineração necessárias no objeto.</span><span class="sxs-lookup"><span data-stu-id="76661-137">After you have finished importing the model, make sure to set the necessary mining permissions on the object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76661-138">Não é possível exportar e importar modelos OLAP usando DMX.</span><span class="sxs-lookup"><span data-stu-id="76661-138">You cannot export and import OLAP models by using DMX.</span></span> <span data-ttu-id="76661-139">Se o modelo de mineração se basear em um cubo OLAP, você deverá usar a funcionalidade fornecida pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para fazer backup e restauração de um banco de dados inteiro, ou reimplantar o cubo e seus modelos.</span><span class="sxs-lookup"><span data-stu-id="76661-139">If your mining model is based on an OLAP cube, you must use the functionality provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up and restoring an entire database, or redeploy the cube and its models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76661-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76661-140">See Also</span></span>  
 [<span data-ttu-id="76661-141">Gerenciamento de soluções de mineração de dados e objetos</span><span class="sxs-lookup"><span data-stu-id="76661-141">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
