---
title: Construtor de Consultas (Assistente de relatório) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.dataview.vdtquerydesigner.f1
- sql12.rtp.rptwizard.querybuilder.f1
helpviewer_keywords:
- Query Builder [Reporting Services]
ms.assetid: 1b0904ea-28c1-448e-b56c-c0fdfbc8b222
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 34369bc72fadae75afbc93eb03c0e40509dd27a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569172"
---
# <a name="query-builder-report-wizard"></a><span data-ttu-id="0774d-102">Construtor de Consultas (Assistente de Relatório)</span><span class="sxs-lookup"><span data-stu-id="0774d-102">Query Builder (Report Wizard)</span></span>
  <span data-ttu-id="0774d-103">Use o Construtor de Consultas para especificar uma consulta que recupera um conjunto de resultados para usar em um relatório.</span><span class="sxs-lookup"><span data-stu-id="0774d-103">Use the Query Builder to specify a query that retrieves a result set to use in a report.</span></span> <span data-ttu-id="0774d-104">Você pode escolher entre dois construtores de consulta:</span><span class="sxs-lookup"><span data-stu-id="0774d-104">You can choose between two query builders:</span></span>  
  
-   <span data-ttu-id="0774d-105">O construtor de consultas baseado em texto (padrão) fornece um workspace simples para especificar uma consulta e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="0774d-105">The text-based query builder (default) provides a simple workspace for specifying a query and viewing the results.</span></span> <span data-ttu-id="0774d-106">Você pode especificar várias instruções do [!INCLUDE[tsql](../includes/tsql-md.md)] , consulta ou sintaxe de comando para as extensões de processamento de dados e consultas que são especificadas como expressões.</span><span class="sxs-lookup"><span data-stu-id="0774d-106">You can specify multiple [!INCLUDE[tsql](../includes/tsql-md.md)] statements, query or command syntax for custom data processing extensions, and queries that are specified as expressions.</span></span> <span data-ttu-id="0774d-107">Como o construtor de consulta genérico não processa previamente a consulta e pode acomodar qualquer tipo de sintaxe de consulta, esta é a ferramenta de construção de consulta padrão para o Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="0774d-107">Because the generic query builder does not preprocess the query and can accommodate any kind of query syntax, it is the default query builder tool for Report Designer.</span></span>  
  
-   <span data-ttu-id="0774d-108">O construtor de consultas gráfico fornece uma experiência visual mais rica.</span><span class="sxs-lookup"><span data-stu-id="0774d-108">The graphical query builder provides a richer visual experience.</span></span> <span data-ttu-id="0774d-109">É usado no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] e em outras partes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0774d-109">It is used in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] and in other parts of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0774d-110">Você poderá usar o construtor de consultas gráfico se não estiver criando expressões ou instruções SQL de várias partes.</span><span class="sxs-lookup"><span data-stu-id="0774d-110">You can use the graphical query builder if you are not creating expressions or multi-part SQL statements.</span></span>  
  
     <span data-ttu-id="0774d-111">Para mudar para o construtor de consultas gráfico, ative/desative o botão **Editar como Texto** , no canto superior esquerdo da janela.</span><span class="sxs-lookup"><span data-stu-id="0774d-111">To switch to the graphical query builder, toggle the **Edit As Text** button in the top left corner of the window.</span></span>  
  
 <span data-ttu-id="0774d-112">Você também pode importar uma consulta de outro relatório.</span><span class="sxs-lookup"><span data-stu-id="0774d-112">You can also import a query from another report.</span></span>  
  
## <a name="query-builder-options"></a><span data-ttu-id="0774d-113">Opções do Construtor de Consultas</span><span class="sxs-lookup"><span data-stu-id="0774d-113">Query Builder Options</span></span>  
 <span data-ttu-id="0774d-114">**Editar como Texto**</span><span class="sxs-lookup"><span data-stu-id="0774d-114">**Edit As Text**</span></span>  
 <span data-ttu-id="0774d-115">Alterna entre os designers de consultas gráficas e baseados em texto, se ambos funcionarem para a consulta.</span><span class="sxs-lookup"><span data-stu-id="0774d-115">Toggles between the text-based and graphical query designers, if both will work for the query.</span></span>  
  
 <span data-ttu-id="0774d-116">**Importaçãoação**</span><span class="sxs-lookup"><span data-stu-id="0774d-116">**Import**</span></span>  
 <span data-ttu-id="0774d-117">Abre a caixa de diálogo **Importar Consulta** e exibe arquivos .rdl e .sql de qualquer relatório disponível.</span><span class="sxs-lookup"><span data-stu-id="0774d-117">Opens the **Import Query** dialog box and displays .rdl and .sql files for any available report.</span></span> <span data-ttu-id="0774d-118">Você pode usar a consulta importada como ela está ou pode modificá-la no construtor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0774d-118">You can use the imported query as it is, or you can modify it in the query builder.</span></span>  
  
 <span data-ttu-id="0774d-119">**! (Executar)**</span><span class="sxs-lookup"><span data-stu-id="0774d-119">**! (Run)**</span></span>  
 <span data-ttu-id="0774d-120">Executa a consulta e retorna um conjunto de resultados se a consulta for válida.</span><span class="sxs-lookup"><span data-stu-id="0774d-120">Runs the query and returns a result set if the query is valid.</span></span> <span data-ttu-id="0774d-121">Observe que você não poderá executar a consulta se ela for uma expressão.</span><span class="sxs-lookup"><span data-stu-id="0774d-121">Note that you cannot execute the query if it is an expression.</span></span> <span data-ttu-id="0774d-122">Para verificar uma consulta baseada em expressão, você deve visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="0774d-122">To verify an expression-based query, you must preview the report.</span></span>  
  
 <span data-ttu-id="0774d-123">**Tipo de comando**</span><span class="sxs-lookup"><span data-stu-id="0774d-123">**Command type**</span></span>  
 <span data-ttu-id="0774d-124">Especifica o direcionamento de texto, o procedimento armazenado ou a tabela.</span><span class="sxs-lookup"><span data-stu-id="0774d-124">Specifies text, stored procedure, or table direct.</span></span> <span data-ttu-id="0774d-125">A disponibilidade de um tipo de comando depende da extensão de processamento de dados que você especificou.</span><span class="sxs-lookup"><span data-stu-id="0774d-125">Availability of a command type depends on the data processing extension you specified.</span></span>  
  
 <span data-ttu-id="0774d-126">**Painel de consulta**</span><span class="sxs-lookup"><span data-stu-id="0774d-126">**Query pane**</span></span>  
 <span data-ttu-id="0774d-127">Digite a consulta.</span><span class="sxs-lookup"><span data-stu-id="0774d-127">Type the query.</span></span>  
  
 <span data-ttu-id="0774d-128">**Painel de resultados**</span><span class="sxs-lookup"><span data-stu-id="0774d-128">**Result pane**</span></span>  
 <span data-ttu-id="0774d-129">Mostra o conjunto de resultados retornado da consulta.</span><span class="sxs-lookup"><span data-stu-id="0774d-129">Shows the result set returned from the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0774d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0774d-130">See Also</span></span>  
 <span data-ttu-id="0774d-131">[Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0774d-131">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0774d-132">Ajuda do Assistente de Relatório</span><span class="sxs-lookup"><span data-stu-id="0774d-132">Report Wizard Help</span></span>](../../2014/reporting-services/report-wizard-help.md)  
  
  
