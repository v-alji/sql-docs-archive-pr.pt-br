---
title: Como exibir um relatório do supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- viewing reports
- Upgrade Advisor [SQL Server], reports
- SQL Server Upgrade Advisor, reports
- reports [Upgrade Advisor], viewing
ms.assetid: d13b38af-0ac3-4030-83cd-e7d7825dd09f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e6df35b869186a601458889c348153093ccbce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582780"
---
# <a name="how-to-view-an-upgrade-advisor-report"></a><span data-ttu-id="15ad2-102">Como fazer: Para exibir um relatório do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="15ad2-102">How to: View an Upgrade Advisor Report</span></span>
  <span data-ttu-id="15ad2-103">O Supervisor de Atualização cria relatórios para cada componente que você seleciona para analisar.</span><span class="sxs-lookup"><span data-stu-id="15ad2-103">Upgrade Advisor creates reports for each component that you select to analyze.</span></span> <span data-ttu-id="15ad2-104">Este tópico descreve como exibir esses relatórios na página inicial do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="15ad2-104">This topic describes how to view an Upgrade Advisor report from the Upgrade Advisor start page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15ad2-105">O visualizador de relatórios carrega arquivos com base em nomes de arquivo padrão.</span><span class="sxs-lookup"><span data-stu-id="15ad2-105">The report viewer loads files based on standard file names.</span></span> <span data-ttu-id="15ad2-106">Se os arquivos tiverem sido renomeados, o visualizador de relatórios não os carregará.</span><span class="sxs-lookup"><span data-stu-id="15ad2-106">If the files have been renamed, the report viewer will not load them.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="15ad2-107">Para exibir um relatório</span><span class="sxs-lookup"><span data-stu-id="15ad2-107">To view a report</span></span>  
  
1.  <span data-ttu-id="15ad2-108">Clique em **Iniciar**, em **todos os programas**, em **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]** e em \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supervisor de atualização\*\*.</span><span class="sxs-lookup"><span data-stu-id="15ad2-108">Click **Start**, click **All Programs**, click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**, and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
2.  <span data-ttu-id="15ad2-109">Na página inicial do supervisor de atualização, clique em **Iniciar Visualizador de relatórios do supervisor de atualização**.</span><span class="sxs-lookup"><span data-stu-id="15ad2-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
3.  <span data-ttu-id="15ad2-110">Para selecionar um relatório no local padrão em seu computador:</span><span class="sxs-lookup"><span data-stu-id="15ad2-110">To select a report in the default location on your computer:</span></span>  
  
    1.  <span data-ttu-id="15ad2-111">Na lista **servidor** , selecione um servidor.</span><span class="sxs-lookup"><span data-stu-id="15ad2-111">In the **Server** list, select a server.</span></span>  
  
    2.  <span data-ttu-id="15ad2-112">Na lista de **instância ou componente** , selecione uma combinação de componente ou componente/instância.</span><span class="sxs-lookup"><span data-stu-id="15ad2-112">In the **Instance or component** list, select a component or component/instance combination.</span></span>  
  
     <span data-ttu-id="15ad2-113">Para selecionar um relatório em outro local:</span><span class="sxs-lookup"><span data-stu-id="15ad2-113">To select a report at another location:</span></span>  
  
    1.  <span data-ttu-id="15ad2-114">Clique no link **abrir relatório** .</span><span class="sxs-lookup"><span data-stu-id="15ad2-114">Click the **Open Report** link.</span></span>  
  
    2.  <span data-ttu-id="15ad2-115">Navegue até o local do relatório e clique duas vezes no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="15ad2-115">Browse to the report location and then double-click the XML file.</span></span>  
  
     <span data-ttu-id="15ad2-116">O Supervisor de Atualização armazena até cinco relatórios da análise anterior como histórico.</span><span class="sxs-lookup"><span data-stu-id="15ad2-116">Upgrade Advisor stores up to five reports from previous analysis as history.</span></span> <span data-ttu-id="15ad2-117">Para exibir esses relatórios, clique na caixa de listagem suspensa **relatório** e selecione um relatório.</span><span class="sxs-lookup"><span data-stu-id="15ad2-117">To view these reports, click the **Report** drop-down list box, and select a report.</span></span> <span data-ttu-id="15ad2-118">Os relatórios são listados pelo carimbo de data/hora de quando foram gerados.</span><span class="sxs-lookup"><span data-stu-id="15ad2-118">The reports are listed by the timestamp from when they were generated.</span></span>  
  
     <span data-ttu-id="15ad2-119">O relatório contém os seguintes detalhes para todos os problemas detectados:</span><span class="sxs-lookup"><span data-stu-id="15ad2-119">The report contains the following details for all detected issues:</span></span>  
  
    -   <span data-ttu-id="15ad2-120">**Importância**, que indica quão importante é corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="15ad2-120">**Importance**, which indicates how important it is to fix the issue.</span></span>  
  
    -   <span data-ttu-id="15ad2-121">**Quando corrigir**, o que indica se você deve (ou deve) corrigir o problema antes ou depois de atualizar para [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] o, antes ou depois de migrar o aplicativo ou os dados, ou a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="15ad2-121">**When to fix**, which indicates if you should (or must) fix the issue before or after upgrading to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], before or after migrating the application or data, or anytime.</span></span>  
  
    -   <span data-ttu-id="15ad2-122">Uma descrição breve do problema.</span><span class="sxs-lookup"><span data-stu-id="15ad2-122">A brief description of the issue.</span></span>  
  
4.  <span data-ttu-id="15ad2-123">Se o relatório tiver mais de 20 itens, clique na seta verde para frente, na parte superior ou inferior do relatório, para exibir o próximo conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="15ad2-123">If the report contains more than 20 items, click the green forward arrow at the top or bottom of the report to view the next set of items.</span></span> <span data-ttu-id="15ad2-124">Clique na seta verde para trás para exibir os 20 itens anteriores.</span><span class="sxs-lookup"><span data-stu-id="15ad2-124">Click the green back button to view the previous 20 items.</span></span>  
  
5.  <span data-ttu-id="15ad2-125">Para classificar o relatório, clique em um título de coluna.</span><span class="sxs-lookup"><span data-stu-id="15ad2-125">To sort the report, click a column heading.</span></span>  
  
6.  <span data-ttu-id="15ad2-126">Para exibir detalhes para um item específico, clique no item.</span><span class="sxs-lookup"><span data-stu-id="15ad2-126">To view details for a specific item, click the item.</span></span> <span data-ttu-id="15ad2-127">Aparecerá uma descrição do problema, juntamente com opções adicionais:</span><span class="sxs-lookup"><span data-stu-id="15ad2-127">A description of the issue appears, along with additional options:</span></span>  
  
    -   <span data-ttu-id="15ad2-128">Para exibir os objetos em que esse problema foi encontrado, clique em **Mostrar objetos afetados**.</span><span class="sxs-lookup"><span data-stu-id="15ad2-128">To view the objects where this issue was found, click **Show affected objects**.</span></span>  
  
    -   <span data-ttu-id="15ad2-129">Para exibir a ajuda do problema, clique em **mais informações sobre esse problema e como resolvê-lo**.</span><span class="sxs-lookup"><span data-stu-id="15ad2-129">To view help for the issue, click **Tell me more about this issue and how to resolve it**.</span></span>  
  
    -   <span data-ttu-id="15ad2-130">Para marcar o problema como resolvido, que oculta o problema quando você exibe o relatório novamente, selecione **esse problema foi resolvido**.</span><span class="sxs-lookup"><span data-stu-id="15ad2-130">To mark the issue as resolved, which hides the issue when you view the report again, select **This issue has been resolved**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15ad2-131">O relatório pode conter um item para problemas indetectáveis.</span><span class="sxs-lookup"><span data-stu-id="15ad2-131">The report may contain an item for undetectable issues.</span></span> <span data-ttu-id="15ad2-132">Esses são os problemas que não podem ser detectados ou os que gerariam muitos resultados de falso positivo.</span><span class="sxs-lookup"><span data-stu-id="15ad2-132">These are issues that cannot be detected or that would generate too many false-positive results.</span></span> <span data-ttu-id="15ad2-133">Clique no link **mais informações sobre esse problema e como resolvê-lo** para ver uma lista de problemas não detectáveis do componente.</span><span class="sxs-lookup"><span data-stu-id="15ad2-133">Click the **Tell me more about this issue and how to resolve it** link to see a list of undetectable issues for the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ad2-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15ad2-134">See Also</span></span>  
 <span data-ttu-id="15ad2-135">[Como: exportar relatórios](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="15ad2-135">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="15ad2-136">[Como executar o assistente de análise do supervisor de atualização](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="15ad2-136">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="15ad2-137">[Resolvendo problemas de atualização](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="15ad2-137">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="15ad2-138">[Tópicos de instruções do supervisor de atualização](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="15ad2-138">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="15ad2-139">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="15ad2-139">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
