---
title: Conceito de parâmetros de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b740362daea83b50a62f0b4453ce818ab21ace7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679701"
---
# <a name="report-parameters-concept-report-builder-and-ssrs"></a><span data-ttu-id="de67d-102">Conceito de parâmetros de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="de67d-102">Report Parameters Concept (Report Builder and SSRS)</span></span>
  <span data-ttu-id="de67d-103">Você pode adicionar parâmetros a um relatório para vincular relatórios relacionados, controlar a aparência do relatório, filtrar dados de relatórios ou restringir o escopo de um relatório a usuários ou locais específicos.</span><span class="sxs-lookup"><span data-stu-id="de67d-103">You can add parameters to a report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="de67d-104">Os parâmetros de relatório são criados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="de67d-104">Report parameters are created in the following ways:</span></span>  
  
-   <span data-ttu-id="de67d-105">Automaticamente, quando você define a consulta de conjunto de dados que contém variáveis de consulta.</span><span class="sxs-lookup"><span data-stu-id="de67d-105">Automatically, when you define dataset query that contains query variables.</span></span> <span data-ttu-id="de67d-106">Para cada variável de consulta, são criados um parâmetro de consulta de conjunto de dados e um parâmetro de relatório correspondentes com os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="de67d-106">For each query variable, a corresponding dataset query parameter and report parameter with the same names are created.</span></span> <span data-ttu-id="de67d-107">Um parâmetro de consulta pode ser uma referência a uma variável de consulta ou a um parâmetro de entrada para um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="de67d-107">A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.</span></span>  
  
-   <span data-ttu-id="de67d-108">Automaticamente, quando você adiciona uma referência a um conjunto de dados compartilhado que contém parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="de67d-108">Automatically, when you add a reference to a shared dataset that contains query parameters.</span></span>  
  
-   <span data-ttu-id="de67d-109">Manualmente, quando você cria parâmetros de relatório no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-109">Manually, when you create report parameters in the Report Data pane.</span></span> <span data-ttu-id="de67d-110">Os parâmetros são umas das coleções internas que você pode incluir em uma expressão em um relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-110">Parameters are one of the built-in collections that you can include in an expression in a report.</span></span> <span data-ttu-id="de67d-111">Como as expressões são usadas para definir valores em uma definição de relatório, você pode usar parâmetros para controlar a aparência do relatório ou transmitir valores aos sub-relatórios ou relatórios relacionados que também usam parâmetros.</span><span class="sxs-lookup"><span data-stu-id="de67d-111">Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.</span></span>  
  
 <span data-ttu-id="de67d-112">Para obter mais informações, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="de67d-112">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
 <span data-ttu-id="de67d-113">Os parâmetros costumam ser usados para filtrar dados de relatório antes e depois que os dados são retornados ao relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-113">Parameters are frequently used to filter report data both before and after the data is returned to the report.</span></span> <span data-ttu-id="de67d-114">Para obter mais informações, consulte [Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de67d-114">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="de67d-115">Quando você cria um relatório, os parâmetros de relatório são salvos na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-115">When you design a report, report parameters are saved in the report definition.</span></span> <span data-ttu-id="de67d-116">Quando você publica um relatório, os parâmetros de relatório são salvos e gerenciados separadamente da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-116">When you publish a report, report parameters are saved and managed separately from the report definition.</span></span> <span data-ttu-id="de67d-117">Depois de salvar o relatório no servidor de relatório, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="de67d-117">After you save the report to the report server, you can do the following:</span></span>  
  
-   <span data-ttu-id="de67d-118">Altere os valores de parâmetros de relatório diretamente no servidor de relatório, de modo independente da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-118">Change report parameter values directly on the report server independently from the report definition.</span></span>  
  
-   <span data-ttu-id="de67d-119">Crie vários relatórios vinculados em que cada relatório vinculado é um link para a definição de relatório com um conjunto separado de valores de parâmetros que podem ser gerenciados independentemente no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-119">Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.</span></span>  
  
 <span data-ttu-id="de67d-120">Se você pretende criar instantâneos de relatório, históricos ou assinaturas para um relatório publicado, precisa compreender como os parâmetros de relatório afetam os requisitos de design para o relatório.</span><span class="sxs-lookup"><span data-stu-id="de67d-120">If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de67d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de67d-121">See Also</span></span>  
 <span data-ttu-id="de67d-122">[Conceitos de criação de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de67d-122">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de67d-123">[Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de67d-123">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="de67d-124">Tutorial: Adicionar um parâmetro ao relatório &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="de67d-124">Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;</span></span>](../tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
