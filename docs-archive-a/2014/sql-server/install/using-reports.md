---
title: Usando relatórios | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- overriding reports
- Upgrade Advisor Report Viewer
- reports [Upgrade Advisor], about reports
- formatting reports
- resolved issues [Upgrade Advisor]
- distributing reports [Reporting Services]
- filtering reports [Reporting Services]
- removing report items
- viewing reports
- rerunning analysis
- information issues [Upgrade Advisor]
- deleting report items
- icons [Upgrade Advisor]
- Upgrade Advisor [SQL Server], reports
- sending reports
- blocking issues [Upgrade Advisor]
- sharing reports
- reports [Upgrade Advisor]
- SQL Server Upgrade Advisor, reports
- modifying reports
- distributing reports [Reporting Services], about report distribution
- warnings [Upgrade Advisor]
- analyzing system [Upgrade Advisor], reports
ms.assetid: 4a3cb94a-a7ac-4cec-94c7-db26fcf6d161
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f52afcfdaa7de33d83d64a049f9a350f0463b4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686024"
---
# <a name="using-reports"></a><span data-ttu-id="d1ae3-102">Usando relatórios</span><span class="sxs-lookup"><span data-stu-id="d1ae3-102">Using Reports</span></span>
  <span data-ttu-id="d1ae3-103">Um relatório único é gerado para cada componente e, se necessário, para cada instância analisada pelo Assistente para Análise do Supervisor de Atualização em um servidor.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-103">A separate report is generated for each component, and, where necessary, each instance, that the Upgrade Advisor Analysis Wizard analyzes on a server.</span></span> <span data-ttu-id="d1ae3-104">O relatório fornece detalhes sobre problemas conhecidos que podem afetar uma atualização.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-104">The report provides details about known issues that affect an upgrade.</span></span> <span data-ttu-id="d1ae3-105">Ele também fornece links para informações e ações sugeridas para resolver os problemas identificados.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-105">It also provides links to information and suggested actions for addressing the identified issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1ae3-106">Se o Visualizador de relatórios do supervisor de atualização não encontrar relatórios no diretório de relatórios padrão, você poderá carregar um relatório de um diretório diferente usando o link **abrir relatório** .</span><span class="sxs-lookup"><span data-stu-id="d1ae3-106">If the Upgrade Advisor Report Viewer does not find any reports in the default reports directory, you can load a report from a different directory by using the **Open Report** link.</span></span>  
  
## <a name="viewing-reports"></a><span data-ttu-id="d1ae3-107">Exibindo relatórios</span><span class="sxs-lookup"><span data-stu-id="d1ae3-107">Viewing Reports</span></span>  
 <span data-ttu-id="d1ae3-108">O Visualizador de Relatórios do Supervisor de Atualização é usado para exibir relatórios do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-108">You use the Upgrade Advisor Report Viewer to view Upgrade Advisor reports.</span></span> <span data-ttu-id="d1ae3-109">Para exibir relatórios, na página inicial do supervisor de atualização, clique em **Iniciar Visualizador de relatórios do supervisor de atualização**.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-109">To view reports, on the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
 <span data-ttu-id="d1ae3-110">Depois de carregar um relatório no servidor, você pode selecionar um componente para o qual deseja verificar os problemas de atualização.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-110">After you load a report for a server, you can select a component for which you want to see upgrade issues.</span></span> <span data-ttu-id="d1ae3-111">Você pode aplicar um filtro da caixa **Filtrar por** para ver o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1ae3-111">You can apply a filter from the **Filter By** box to see the following:</span></span>  
  
-   <span data-ttu-id="d1ae3-112">Todos os problemas</span><span class="sxs-lookup"><span data-stu-id="d1ae3-112">All issues</span></span>  
  
-   <span data-ttu-id="d1ae3-113">Todos os problemas de atualização</span><span class="sxs-lookup"><span data-stu-id="d1ae3-113">All upgrade issues</span></span>  
  
-   <span data-ttu-id="d1ae3-114">Problemas de pré-atualização</span><span class="sxs-lookup"><span data-stu-id="d1ae3-114">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="d1ae3-115">Todos os problemas de migração</span><span class="sxs-lookup"><span data-stu-id="d1ae3-115">All migration issues</span></span>  
  
-   <span data-ttu-id="d1ae3-116">Problemas resolvidos</span><span class="sxs-lookup"><span data-stu-id="d1ae3-116">Resolved issues</span></span>  
  
-   <span data-ttu-id="d1ae3-117">Problemas não resolvidos</span><span class="sxs-lookup"><span data-stu-id="d1ae3-117">Unresolved issues</span></span>  
  
 <span data-ttu-id="d1ae3-118">Se o relatório tiver mais de 20 problemas, você poderá ir para o grupo de problemas seguinte ou anterior clicando em **avançar 20** ou **20** na parte superior ou inferior da lista de problemas.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-118">If your report has more than 20 issues, you can move to the next or previous group of issues by clicking **Next 20** or **Previous 20** at the top or bottom of the issues list.</span></span>  
  
 <span data-ttu-id="d1ae3-119">Você pode exibir até cinco relatórios salvos selecionando os relatórios na caixa de listagem suspensa **relatório** .</span><span class="sxs-lookup"><span data-stu-id="d1ae3-119">You can view up to five saved reports by selecting the reports from the **Report** drop-down list box.</span></span> <span data-ttu-id="d1ae3-120">Os relatórios são listados pelo carimbo de data/hora de quando foram gerados.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-120">The reports are listed by the timestamp from when they were generated.</span></span>  
  
## <a name="report-format"></a><span data-ttu-id="d1ae3-121">Formato de relatório</span><span class="sxs-lookup"><span data-stu-id="d1ae3-121">Report Format</span></span>  
 <span data-ttu-id="d1ae3-122">O visualizador de relatórios exibe os problemas em três colunas.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-122">The report viewer displays report issues in three columns.</span></span> <span data-ttu-id="d1ae3-123">Cada problema pode ser recolhido para que você possa ocultar a descrição ou exibir apenas informações fundamentais.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-123">Each issue is collapsible so that you can hide the description and view only the key information.</span></span>  
  
 <span data-ttu-id="d1ae3-124">A primeira coluna é a coluna **importância** .</span><span class="sxs-lookup"><span data-stu-id="d1ae3-124">The first column is the **Importance** column.</span></span> <span data-ttu-id="d1ae3-125">Os ícones indicam a importância de cada problema. Um círculo vermelho com um X indica problemas importantes ou que podem impedir a atualização; um triângulo amarelo com um ponto de exclamação indica problemas com avisos ou informações.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-125">Icons indicate the importance for each issue by displaying either a red circle with an X for blocking or important issues or a yellow triangle with an exclamation mark for Warning and Information issues.</span></span> <span data-ttu-id="d1ae3-126">A segunda coluna, **quando corrigir**, indica quando você deve resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-126">The second column, **When to fix**, indicates when you must resolve the issue.</span></span> <span data-ttu-id="d1ae3-127">Você pode classificar o relatório sobre a coluna **importância** ou **quando corrigir** .</span><span class="sxs-lookup"><span data-stu-id="d1ae3-127">You can sort the report on either the **Importance** or **When to fix** column.</span></span> <span data-ttu-id="d1ae3-128">A terceira coluna, **Descrição**, lista o título do problema.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-128">The third column, **Description**, lists the title of the issue.</span></span>  
  
 <span data-ttu-id="d1ae3-129">É possível expandir um problema para exibir informações adicionais, um link para informações detalhadas sobre como solucionar o problema e um link para exibir detalhes do problema.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-129">You can expand an issue to display additional information, a link to detailed information about resolving the issue, and a link to show issue details.</span></span> <span data-ttu-id="d1ae3-130">Ao clicar no link para acessar informações detalhadas do problema, o tópico da Ajuda com informações sobre o problema e instruções para solucioná-lo é exibido.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-130">When you click the link to get detailed information for the issue, a Help topic with information about the issue and instructions for addressing the issue is displayed.</span></span> <span data-ttu-id="d1ae3-131">Depois de corrigir um problema, ou de gerenciar seus itens de ação, você pode marcar problemas como concluídos marcando a caixa de seleção **este problema foi resolvido** .</span><span class="sxs-lookup"><span data-stu-id="d1ae3-131">After you have fixed an issue, or to manage your action items, you can mark issues as complete by selecting the **This issue has been resolved** check box.</span></span> <span data-ttu-id="d1ae3-132">Se você quiser remover os problemas resolvidos da lista de problemas de atualização, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-132">If you want to remove the resolved issues from the list of upgrade issues, click **Refresh**.</span></span> <span data-ttu-id="d1ae3-133">O problema não é exibido novamente até que você execute o assistente de análise do supervisor de atualização no mesmo componente ou aplique o filtro **problemas resolvidos** da opção **Filtrar por** .</span><span class="sxs-lookup"><span data-stu-id="d1ae3-133">The issue is not displayed again until you either run the Upgrade Advisor Analysis Wizard against the same component or apply the **Resolved Issues** filter from the **Filter By** option.</span></span>  
  
## <a name="report-files"></a><span data-ttu-id="d1ae3-134">Arquivos de relatório</span><span class="sxs-lookup"><span data-stu-id="d1ae3-134">Report Files</span></span>  
 <span data-ttu-id="d1ae3-135">O assistente de análise do supervisor de atualização cria relatórios no diretório meus documentos \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade Advisor\110\Reports e cria um subdiretório para cada servidor que você analisa.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-135">The Upgrade Advisor Analysis Wizard creates reports in the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports directory and creates a subdirectory for each server that you analyze.</span></span> <span data-ttu-id="d1ae3-136">Os arquivos de relatório estão no formato XML e seguem uma convenção de nomenclatura específica.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-136">The report files are XML files that follow a specific naming convention.</span></span> <span data-ttu-id="d1ae3-137">Quando você inicia o Visualizador de Relatórios do Supervisor de Atualização, os arquivos de relatório do diretório padrão são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-137">When you launch the Upgrade Advisor Report Viewer, the report files in the default directory are displayed.</span></span> <span data-ttu-id="d1ae3-138">Se você copiar arquivos de relatório para essa pasta, eles deverão seguir a mesma convenção de nomenclatura ou o visualizador de relatórios não irá exibi-los automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-138">If you copy report files into this folder, they must adhere to the naming convention or the report viewer will not display them automatically.</span></span>  
  
 <span data-ttu-id="d1ae3-139">Se você quiser compartilhar a informações com outras pessoas, poderá enviar-lhes o relatório XML.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-139">If you want to share the information with other people, you can send them the XML report.</span></span> <span data-ttu-id="d1ae3-140">Se preferir usar outro aplicativo, basta exportar o relatório para um arquivo CSV que pode ser usado para criar uma planilha, um arquivo de texto ou uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="d1ae3-140">Or, if you want to use another application, you can export the report into a comma-separated value file that you can use to create a spreadsheet, text file, or e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ae3-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1ae3-141">See Also</span></span>  
 <span data-ttu-id="d1ae3-142">[Como exibir um relatório do supervisor de atualização](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span><span class="sxs-lookup"><span data-stu-id="d1ae3-142">[How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span></span>  
 <span data-ttu-id="d1ae3-143">[Como: exportar relatórios](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="d1ae3-143">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="d1ae3-144">[Como filtrar relatórios](../../../2014/sql-server/install/how-to-filter-reports.md) </span><span class="sxs-lookup"><span data-stu-id="d1ae3-144">[How to: Filter Reports](../../../2014/sql-server/install/how-to-filter-reports.md) </span></span>  
 <span data-ttu-id="d1ae3-145">[Resolvendo problemas de atualização](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d1ae3-145">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d1ae3-146">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="d1ae3-146">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
