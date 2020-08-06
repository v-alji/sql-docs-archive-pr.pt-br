---
title: Exibição de visualização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.previewview.f1
helpviewer_keywords:
- Preview view [Reporting Services]
ms.assetid: 108255d1-5be8-47c1-80f3-1f2a055e4d02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1ff7c59c3ac5143d4f4103edea1a5ee309046547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680786"
---
# <a name="preview-view"></a><span data-ttu-id="29d18-102">Modo Visualizar</span><span class="sxs-lookup"><span data-stu-id="29d18-102">Preview View</span></span>
  <span data-ttu-id="29d18-103">Use o modo **Visualizar** para exibir o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="29d18-103">Use **Preview** view to display the rendered report.</span></span> <span data-ttu-id="29d18-104">Quando um relatório é visualizado, o Designer de Relatórios o executa localmente e o exibe no modo Visualizar.</span><span class="sxs-lookup"><span data-stu-id="29d18-104">When a report is previewed, Report Designer runs the report locally and displays it in the Preview view.</span></span> <span data-ttu-id="29d18-105">Nesse modo de exibição, o relatório é processado por completo.</span><span class="sxs-lookup"><span data-stu-id="29d18-105">In preview mode, the report is processed in full.</span></span> <span data-ttu-id="29d18-106">Se o relatório tiver uma consulta complexa ou se contiver muitos dados, a visualização poderá demorar vários minutos para ser concluída na primeira vez.</span><span class="sxs-lookup"><span data-stu-id="29d18-106">If the report has a complex query or has a large amount of data, preview might take several minutes to complete the first time you view it.</span></span> <span data-ttu-id="29d18-107">Nas alterações subsequentes que afetam apenas o formato do relatório, a visualização usa dados armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="29d18-107">For subsequent changes that affect only the format of the report, preview uses cached data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="29d18-108">Quando o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for executado como um RemoteApp, os relatórios não poderão ser exibidos no modo **Visualizar** do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29d18-108">When [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] is run as a RemoteApp, reports cannot be displayed in **Preview** view in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="29d18-109">Os programas RemoteApp são acessados remotamente através dos Serviços da área de trabalho remota.</span><span class="sxs-lookup"><span data-stu-id="29d18-109">RemoteApp programs are programs that are accessed remotely through Remote Desktop Services.</span></span> <span data-ttu-id="29d18-110">Para obter mais informações, consulte [Guia passo a passo do TS RemoteApp](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="29d18-110">For more information, see [TS RemoteApp Step-by-Step Guide](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span></span>  
  
## <a name="options"></a><span data-ttu-id="29d18-111">Opções</span><span class="sxs-lookup"><span data-stu-id="29d18-111">Options</span></span>  
 <span data-ttu-id="29d18-112">Use a barra de ferramentas para gerenciar as funções de visualização.</span><span class="sxs-lookup"><span data-stu-id="29d18-112">Use the toolbar to manage preview functions.</span></span>  
  
 <span data-ttu-id="29d18-113">**Mostrar ou Ocultar Mapa do Documento**</span><span class="sxs-lookup"><span data-stu-id="29d18-113">**Show or Hide Document Map**</span></span>  
 <span data-ttu-id="29d18-114">Escolha essa opção para mostrar ou ocultar o mapa do documento, se houver.</span><span class="sxs-lookup"><span data-stu-id="29d18-114">Choose this option to show or hide the document map if one exists.</span></span>  
  
 <span data-ttu-id="29d18-115">**Mostrar ou Ocultar Área de Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="29d18-115">**Show or Hide Parameter Area**</span></span>  
 <span data-ttu-id="29d18-116">Escolha essa opção para mostrar ou ocultar as caixas de parâmetros dos relatórios com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="29d18-116">Choose this option to show or hide the parameters boxes for reports with parameters.</span></span>  
  
 <span data-ttu-id="29d18-117">**Primeira Página**</span><span class="sxs-lookup"><span data-stu-id="29d18-117">**First Page**</span></span>  
 <span data-ttu-id="29d18-118">Escolha essa opção para ir para a primeira página do relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-118">Choose this option to go to the first page of the report.</span></span>  
  
 <span data-ttu-id="29d18-119">**Página anterior**</span><span class="sxs-lookup"><span data-stu-id="29d18-119">**Previous Page**</span></span>  
 <span data-ttu-id="29d18-120">Escolha essa opção para ir para a página anterior do relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-120">Choose this option to go to the previous page of the report.</span></span>  
  
 <span data-ttu-id="29d18-121">**Página atual**</span><span class="sxs-lookup"><span data-stu-id="29d18-121">**Current Page**</span></span>  
 <span data-ttu-id="29d18-122">Exibe a página atual do relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-122">Displays the current page of the report.</span></span>  
  
 <span data-ttu-id="29d18-123">**Total de Páginas**</span><span class="sxs-lookup"><span data-stu-id="29d18-123">**Total Pages**</span></span>  
 <span data-ttu-id="29d18-124">Exibe o total de páginas do relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-124">Displays the total number of pages in the report.</span></span>  
  
 <span data-ttu-id="29d18-125">**Próxima página**</span><span class="sxs-lookup"><span data-stu-id="29d18-125">**Next Page**</span></span>  
 <span data-ttu-id="29d18-126">Escolha essa opção para ir para a próxima página do relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-126">Choose this option to go to the next page of the report.</span></span>  
  
 <span data-ttu-id="29d18-127">**Última Página**</span><span class="sxs-lookup"><span data-stu-id="29d18-127">**Last Page**</span></span>  
 <span data-ttu-id="29d18-128">Escolha essa opção para ir para a última página do relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-128">Choose this option to go to the last page of the report.</span></span>  
  
 <span data-ttu-id="29d18-129">**Voltar para o Relatório Pai**</span><span class="sxs-lookup"><span data-stu-id="29d18-129">**Back to Parent Report**</span></span>  
 <span data-ttu-id="29d18-130">Escolha essa opção para ir para o relatório pai.</span><span class="sxs-lookup"><span data-stu-id="29d18-130">Choose this option to go to the parent report.</span></span> <span data-ttu-id="29d18-131">Essa opção é usada para navegar e extrair relatórios detalhados.</span><span class="sxs-lookup"><span data-stu-id="29d18-131">This option is used to navigate drillthrough reports.</span></span>  
  
 <span data-ttu-id="29d18-132">**Parar Renderização**</span><span class="sxs-lookup"><span data-stu-id="29d18-132">**Stop Rendering**</span></span>  
 <span data-ttu-id="29d18-133">Escolha essa opção para parar o processo de renderização.</span><span class="sxs-lookup"><span data-stu-id="29d18-133">Choose this option to stop the rendering process.</span></span>  
  
 <span data-ttu-id="29d18-134">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="29d18-134">**Refresh**</span></span>  
 <span data-ttu-id="29d18-135">Escolha essa opção para atualizar o cache de dados e executar o relatório novamente.</span><span class="sxs-lookup"><span data-stu-id="29d18-135">Choose this option to refresh the data cache and run the report again.</span></span>  
  
 <span data-ttu-id="29d18-136">**Imprimir**</span><span class="sxs-lookup"><span data-stu-id="29d18-136">**Print**</span></span>  
 <span data-ttu-id="29d18-137">Escolha essa opção para imprimir o relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-137">Choose this option to print the report.</span></span>  
  
 <span data-ttu-id="29d18-138">**Layout de Impressão**</span><span class="sxs-lookup"><span data-stu-id="29d18-138">**Print Layout**</span></span>  
 <span data-ttu-id="29d18-139">Escolha essa opção para alternar entre a visualização de um relatório e como ele será exibido na página impressa.</span><span class="sxs-lookup"><span data-stu-id="29d18-139">Choose this option to toggle between the preview report and the view of the report as it will appear on the printed page.</span></span>  
  
 <span data-ttu-id="29d18-140">**Configurar Página**</span><span class="sxs-lookup"><span data-stu-id="29d18-140">**Page Setup**</span></span>  
 <span data-ttu-id="29d18-141">Escolha essa opção para alterar as propriedades de páginas e de impressão.</span><span class="sxs-lookup"><span data-stu-id="29d18-141">Choose this option to conveniently change page and print properties.</span></span> <span data-ttu-id="29d18-142">Use Layout de Impressão para exibir as alterações antes de imprimir.</span><span class="sxs-lookup"><span data-stu-id="29d18-142">Use Print Layout to view changes before printing.</span></span>  
  
 <span data-ttu-id="29d18-143">**Exportar**</span><span class="sxs-lookup"><span data-stu-id="29d18-143">**Export**</span></span>  
 <span data-ttu-id="29d18-144">Escolha essa opção para exportar o relatório renderizado em um formato específico.</span><span class="sxs-lookup"><span data-stu-id="29d18-144">Choose this option to export the rendered report in a specific format.</span></span>  
  
 <span data-ttu-id="29d18-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="29d18-145">**Zoom**</span></span>  
 <span data-ttu-id="29d18-146">Selecione um fator de zoom para ampliar ou reduzir o relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-146">Select a zoom factor to zoom in or out on the report.</span></span>  
  
 <span data-ttu-id="29d18-147">**Pesquisar texto**</span><span class="sxs-lookup"><span data-stu-id="29d18-147">**Search Text**</span></span>  
 <span data-ttu-id="29d18-148">Digite o texto para procurar uma correspondência no relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-148">Type text to search for a match within the report.</span></span> <span data-ttu-id="29d18-149">Não é possível usar operadores de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29d18-149">You cannot use search operators.</span></span> <span data-ttu-id="29d18-150">Clique em **Localizar** para procurar a primeira instância.</span><span class="sxs-lookup"><span data-stu-id="29d18-150">Click **Find** to search for the first instance.</span></span>  
  
 <span data-ttu-id="29d18-151">**Considerar**</span><span class="sxs-lookup"><span data-stu-id="29d18-151">**Find**</span></span>  
 <span data-ttu-id="29d18-152">Escolha essa opção para começar a procurar o texto de pesquisa no relatório.</span><span class="sxs-lookup"><span data-stu-id="29d18-152">Choose this option to begin searching the report for the search text.</span></span>  
  
 <span data-ttu-id="29d18-153">**Localizar Próximo**</span><span class="sxs-lookup"><span data-stu-id="29d18-153">**Find Next**</span></span>  
 <span data-ttu-id="29d18-154">Escolha essa opção para procurar a próxima instância do texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29d18-154">Choose this option to search for the next instance of the search text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d18-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29d18-155">See Also</span></span>  
 <span data-ttu-id="29d18-156">[Visualizando relatórios](../reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="29d18-156">[Previewing Reports](../reports/previewing-reports.md) </span></span>  
 [<span data-ttu-id="29d18-157">Ajuda F1 do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="29d18-157">Report Designer F1 Help</span></span>](report-designer-f1-help.md)  
  
  
