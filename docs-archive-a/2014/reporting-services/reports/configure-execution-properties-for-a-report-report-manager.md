---
title: Configurar as propriedades de execução de um relatório (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- reports [Reporting Services], properties
- reports [Reporting Services], execution options
ms.assetid: 73cc8dcc-ef80-40d7-9739-d33bba0eb28a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51cd7b5db225b39f5a061ed750b2ef5cdd265b9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584001"
---
# <a name="configure-execution-properties-for-a-report--report-manager"></a><span data-ttu-id="9a0c7-102">Configurar propriedades de execução de um relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="9a0c7-102">Configure Execution Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="9a0c7-103">Você pode definir opções de processamento de relatório para especificar quando os dados são recuperados para um relatório.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-103">You can set report processing options to specify when data is retrieved for a report.</span></span> <span data-ttu-id="9a0c7-104">É útil agendar o processamento de dados de um relatório se a fonte de dados externa for atualizada em horários específicos (por exemplo, um data warehouse que é atualizado diária ou semanalmente) e você desejar evitar a sobrecarga da recuperação dos mesmos dados sempre que um relatório for solicitado.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-104">It is useful to schedule data processing for a report if the external data source is refreshed at specific times (for example, a data warehouse that is refreshed daily or weekly) and you want to avoid the overhead of retrieving the same data each time a report is requested.</span></span> <span data-ttu-id="9a0c7-105">O agendamento do processamento de dados também é útil se você desejar controlar a carga de processamento no servidor de banco de dados externo ou quando você quiser fornecer resultados consistentes para vários usuários que devem trabalhar com conjuntos de dados idênticos.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-105">Scheduling data processing is also useful if you want to control the processing load on the external database server or when you want to provide consistent results for multiple users who must work with identical sets of data.</span></span> <span data-ttu-id="9a0c7-106">Com dados voláteis, um relatório sob demanda pode produzir resultados diferentes de um minuto para o outro.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-106">With volatile data, an on-demand report can produce different results from one minute to the next.</span></span> <span data-ttu-id="9a0c7-107">Por outro lado, um instantâneo de relatório permite fazer comparações válidas com outros relatórios ou ferramentas analíticas que contêm dados do mesmo momento.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-107">A report snapshot, by contrast, allows you to make valid comparisons against other reports or analytical tools that contain data from the same point in time.</span></span>  
  
 <span data-ttu-id="9a0c7-108">Um instantâneo de relatório é um relatório que contém instruções sobre layout e resultados de consulta que foram recuperados em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-108">A report snapshot is a report that contains layout instructions and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="9a0c7-109">Diferente dos relatórios sob demanda, que obtêm resultados de consulta atualizados quando o relatório é selecionado, os instantâneos de relatório são processados em uma agenda e salvos em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-109">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="9a0c7-110">Quando você seleciona um instantâneo de relatório para exibição, o servidor de relatório recupera o relatório armazenado do banco de dados do servidor e mostra os dados e o layout correspondentes ao momento em que o instantâneo foi criado.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-110">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
 <span data-ttu-id="9a0c7-111">Os instantâneos de relatório não são salvos em um formato de renderização específico.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-111">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="9a0c7-112">Em vez disso, os instantâneos de relatório são renderizados em um formato de exibição final (como HTML) somente quando solicitado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-112">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="9a0c7-113">A renderização adiada deixa o instantâneo portátil.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-113">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="9a0c7-114">O relatório pode ser renderizado no formato correto para a solicitação do dispositivo ou navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-114">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
### <a name="to-configure-report-processing-options"></a><span data-ttu-id="9a0c7-115">Para configurar opções de processamento de relatório</span><span class="sxs-lookup"><span data-stu-id="9a0c7-115">To configure report processing options</span></span>  
  
1.  <span data-ttu-id="9a0c7-116">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9a0c7-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="9a0c7-117">Navegue até o relatório cujas opções de processamento você deseja definir e abra-o.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-117">Navigate to and open the report for which you want to set processing options.</span></span>  
  
 <span data-ttu-id="9a0c7-118">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
1.  <span data-ttu-id="9a0c7-119">No menu suspenso, clique em **Gerenciar** e selecione a guia **Opções de Processamento** .</span><span class="sxs-lookup"><span data-stu-id="9a0c7-119">In the drop-down menu, click **Manage** and then select the **Processing Options** tab.</span></span>  
  
2.  <span data-ttu-id="9a0c7-120">Clique em **Renderizar este relatório em um instantâneo de execução de relatórios**e selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9a0c7-120">Click **Render this report from an execution snapshot, and then select one of the following options:**</span></span>  
  
    -   <span data-ttu-id="9a0c7-121">Se desejar criar um instantâneo, selecione **Use o agendamento a seguir para criar instantâneos de execução de relatórios**e defina uma agenda específica ao relatório ou selecione uma opção na lista **Agenda compartilhada** .</span><span class="sxs-lookup"><span data-stu-id="9a0c7-121">If you want to create a snapshot, select **Use the following schedule to create report execution snapshots**, and then either define a report-specific schedule or select from the **Shared schedule** list.</span></span>  
  
    -   <span data-ttu-id="9a0c7-122">Se desejar criar um instantâneo imediatamente, selecione **Criar um instantâneo de relatórios ao clicar no botão Aplicar nesta página**.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-122">If you want to create a snapshot immediately, select **Create a report snapshot when you click the Apply button on this page**.</span></span>  
  
3.  <span data-ttu-id="9a0c7-123">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9a0c7-123">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0c7-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a0c7-124">See Also</span></span>  
 <span data-ttu-id="9a0c7-125">[Definir propriedades de processamento de relatório](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9a0c7-125">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="9a0c7-126">[Abrir e fechar um relatório &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="9a0c7-126">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="9a0c7-127">[Página Conteúdo &#40;Gerenciador de Relatórios&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="9a0c7-127">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="9a0c7-128">[Gerenciamento do conteúdo do Servidor de Relatório &#40;Modo Nativo do SSRS&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="9a0c7-128">[Report Server Content Management &#40;SSRS Native Mode&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="9a0c7-129">Página de propriedades Opções de Processamento &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0c7-129">Processing Options Properties Page &#40;Report Manager&#41;</span></span>](../processing-options-properties-page-report-manager.md)  
  
  
