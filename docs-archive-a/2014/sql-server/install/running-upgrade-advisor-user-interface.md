---
title: Executando o supervisor de atualização (interface do usuário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Report Viewer
- Upgrade Advisor [SQL Server], running
- launching Upgrade Advisor
- Upgrade Advisor Analysis Wizard
- starting Upgrade Advisor
- SQL Server Upgrade Advisor, running
ms.assetid: 7f47c9b3-88d3-43d6-837e-f157b49a55ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a5e47ef2b8183823dff884e114adc420e371adf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583333"
---
# <a name="running-upgrade-advisor-user-interface"></a><span data-ttu-id="145b3-102">Executando o Supervisor de Atualização (Interface do usuário)</span><span class="sxs-lookup"><span data-stu-id="145b3-102">Running Upgrade Advisor (User Interface)</span></span>
  <span data-ttu-id="145b3-103">Você pode executar o Supervisor de Atualização para analisar componentes locais ou remotos durante o planejamento da atualização.</span><span class="sxs-lookup"><span data-stu-id="145b3-103">You can run Upgrade Advisor to analyze local or remote components during upgrade planning.</span></span> <span data-ttu-id="145b3-104">O Supervisor de Atualização gera um relatório para cada componente e instância que é analisado.</span><span class="sxs-lookup"><span data-stu-id="145b3-104">Upgrade Advisor produces a report for each component and instance that is analyzed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="145b3-105">Ele não analisa instâncias remotas do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="145b3-105">Upgrade Advisor does not analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="145b3-106">Para analisar uma instância do [!INCLUDE[ssRS](../../includes/ssrs.md)], o Supervisor de Atualização deve estar instalado no computador em que o [!INCLUDE[ssRS](../../includes/ssrs.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="145b3-106">To analyze an instance of [!INCLUDE[ssRS](../../includes/ssrs.md)], Upgrade Advisor must be installed on the computer where [!INCLUDE[ssRS](../../includes/ssrs.md)] is installed.</span></span>  
>   
>  <span data-ttu-id="145b3-107">Para analisar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, você deve ter o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalado e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="145b3-107">To analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, you must have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] installed and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed on the same computer.</span></span>  
  
## <a name="running-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="145b3-108">Executando o assistente de análise do supervisor de atualização</span><span class="sxs-lookup"><span data-stu-id="145b3-108">Running the Upgrade Advisor Analysis Wizard</span></span>  
 <span data-ttu-id="145b3-109">A execução do assistente de análise do supervisor de atualização tem seis etapas:</span><span class="sxs-lookup"><span data-stu-id="145b3-109">Running the Upgrade Advisor Analysis Wizard has six steps:</span></span>  
  
1.  <span data-ttu-id="145b3-110">Iniciar o assistente na página inicial do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="145b3-110">Launch the wizard from the Upgrade Advisor start page.</span></span>  
  
2.  <span data-ttu-id="145b3-111">Identificar o servidor e os componentes que serão analisados.</span><span class="sxs-lookup"><span data-stu-id="145b3-111">Identify server and components to analyze.</span></span>  
  
3.  <span data-ttu-id="145b3-112">Reunir informações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="145b3-112">Gather authentication information.</span></span>  
  
4.  <span data-ttu-id="145b3-113">Reunir outros parâmetros com base no tipo de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="145b3-113">Gather additional parameters based on component type.</span></span>  
  
5.  <span data-ttu-id="145b3-114">Analisar os componentes selecionados.</span><span class="sxs-lookup"><span data-stu-id="145b3-114">Analyze selected components.</span></span>  
  
6.  <span data-ttu-id="145b3-115">Gerar o relatório dos problemas de atualização.</span><span class="sxs-lookup"><span data-stu-id="145b3-115">Generate report of upgrade issues.</span></span>  
  
 <span data-ttu-id="145b3-116">Para obter mais informações sobre o assistente de análise do supervisor de atualização, consulte [como executar o assistente de análise do supervisor de atualização](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="145b3-116">For more information about the Upgrade Advisor Analysis Wizard, see [How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span></span>  
  
 <span data-ttu-id="145b3-117">Para obter informações específicas necessárias para cada etapa, consulte [referência da interface do usuário do supervisor de atualização](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="145b3-117">For specific information that is required for each step, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
## <a name="running-the-upgrade-advisor-report-viewer"></a><span data-ttu-id="145b3-118">Executando o Visualizador de relatórios do supervisor de atualização</span><span class="sxs-lookup"><span data-stu-id="145b3-118">Running the Upgrade Advisor Report Viewer</span></span>  
 <span data-ttu-id="145b3-119">Você usa o Visualizador de Relatórios do Supervisor de Atualização para exibir relatórios gerados pelo Assistente para Análise do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="145b3-119">You use the Upgrade Advisor Report Viewer to view reports generated by the Upgrade Advisor Analysis Wizard.</span></span> <span data-ttu-id="145b3-120">Quando os relatórios são carregados, você pode filtrar seus componentes pelos seguintes fatores:</span><span class="sxs-lookup"><span data-stu-id="145b3-120">When the report is loaded, you can filter the components of the report by the following factors:</span></span>  
  
-   <span data-ttu-id="145b3-121">Todos os problemas</span><span class="sxs-lookup"><span data-stu-id="145b3-121">All issues</span></span>  
  
-   <span data-ttu-id="145b3-122">Todos os problemas de atualização</span><span class="sxs-lookup"><span data-stu-id="145b3-122">All upgrade issues</span></span>  
  
-   <span data-ttu-id="145b3-123">Problemas de pré-atualização</span><span class="sxs-lookup"><span data-stu-id="145b3-123">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="145b3-124">Todos os problemas de migração</span><span class="sxs-lookup"><span data-stu-id="145b3-124">All migration issues</span></span>  
  
-   <span data-ttu-id="145b3-125">Problemas resolvidos</span><span class="sxs-lookup"><span data-stu-id="145b3-125">Resolved issues</span></span>  
  
-   <span data-ttu-id="145b3-126">Problemas não resolvidos</span><span class="sxs-lookup"><span data-stu-id="145b3-126">Unresolved issues</span></span>  
  
 <span data-ttu-id="145b3-127">Para verificar as instruções passo a passo de como usar o Visualizador de Relatórios, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="145b3-127">For step-by-step instructions for using the report viewer, see the following topics:</span></span>  
  
-   [<span data-ttu-id="145b3-128">Como fazer: Para exibir um relatório do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="145b3-128">How to: View an Upgrade Advisor Report</span></span>](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md)  
  
-   [<span data-ttu-id="145b3-129">Como fazer: Para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="145b3-129">How to: Filter Reports</span></span>](../../../2014/sql-server/install/how-to-filter-reports.md)  
  
-   [<span data-ttu-id="145b3-130">Como fazer: Exportar relatórios</span><span class="sxs-lookup"><span data-stu-id="145b3-130">How to: Export Reports</span></span>](../../../2014/sql-server/install/how-to-export-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="145b3-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="145b3-131">See Also</span></span>  
 <span data-ttu-id="145b3-132">[Como executar o assistente de análise do supervisor de atualização](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="145b3-132">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="145b3-133">[Referência da interface do usuário do supervisor de atualização](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="145b3-133">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 <span data-ttu-id="145b3-134">[Resolvendo problemas de atualização](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="145b3-134">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="145b3-135">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="145b3-135">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
