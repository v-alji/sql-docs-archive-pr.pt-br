---
title: Salvar eventos de perfil de estatísticas do Plano de Execução XML separadamente (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML events
- saving Showplan XML events
- events [SQL Server], Showplan XML
ms.assetid: df393f13-d538-4d94-8155-9c2fdf5f755d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: be0c02f8396df81af803c365b9ede42610353ed3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680919"
---
# <a name="save-showplan-xml-statistics-profile-events-separately-sql-server-profiler"></a><span data-ttu-id="06a54-102">Salvar eventos de perfil de estatísticas do Plano de Execução XML separadamente (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="06a54-102">Save Showplan XML Statistics Profile Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="06a54-103">Esse tópico descreve como salvar eventos **Showplan XML Statistics Profile** que são capturados nos rastreamentos em arquivos .SQLPlan separados, por meio do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06a54-103">This topic describes how to save **Showplan XML Statistics Profile** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="06a54-104">Você pode abrir os arquivos de eventos **Showplan XML Statistics Profile** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o que permite ver o plano de execução gráfico de cada evento.</span><span class="sxs-lookup"><span data-stu-id="06a54-104">You can open the **Showplan XML Statistics Profile** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-statistics-events-separately"></a><span data-ttu-id="06a54-105">Para salvar eventos de estatísticas do Plano de Execução XML separadamente</span><span class="sxs-lookup"><span data-stu-id="06a54-105">To save Showplan XML statistics events separately</span></span>  
  
1.  <span data-ttu-id="06a54-106">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06a54-106">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="06a54-107">É exibida a caixa de diálogo **Propriedades do Rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="06a54-107">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="06a54-108">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver selecionado, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="06a54-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box does not appear and the trace begins instead.</span></span> <span data-ttu-id="06a54-109">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="06a54-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="06a54-110">Na caixa de diálogo **Propriedades do Rastreamento** , digite um nome para o rastreamento na caixa **Nome do rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="06a54-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="06a54-111">Na lista **Usar o modelo** , selecione um modelo como base para o rastreamento ou **Em branco** , se não quiser usar um modelo.</span><span class="sxs-lookup"><span data-stu-id="06a54-111">In the **Use the template** list, select a trace template to base the trace on, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="06a54-112">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="06a54-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="06a54-113">Clique em**Salvar em arquivo**para capturar o rastreamento em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="06a54-113">Click**Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="06a54-114">Especifique um valor para **Definir tamanho máximo do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="06a54-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="06a54-115">Opcionalmente, selecione **habilitar substituição de arquivo** e **dados de rastreamento de processos de servidor**.</span><span class="sxs-lookup"><span data-stu-id="06a54-115">Optionally select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="06a54-116">Clique em**Salvar em tabela** para capturar o rastreamento em uma tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="06a54-116">Click**Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="06a54-117">Opcionalmente, clique em **Definir máximo de linhas**e especifique um valor.</span><span class="sxs-lookup"><span data-stu-id="06a54-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="06a54-118">Opcionalmente, marque a caixa de seleção **habilitar hora de parada do rastreamento** e especifique uma data e hora de parada.</span><span class="sxs-lookup"><span data-stu-id="06a54-118">Optionally select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="06a54-119">Clique na guia **Seleção de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="06a54-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="06a54-120">Na coluna de dados **Eventos**, expanda a categoria de evento **Desempenho**e marque a caixa de seleção **Showplan XML Statistics Profile**.</span><span class="sxs-lookup"><span data-stu-id="06a54-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML Statistics Profile**check box.</span></span> <span data-ttu-id="06a54-121">Se a categoria de evento **Performance** não estiver disponível, marque **Mostrar todos os eventos** para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="06a54-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="06a54-122">A guia **Configurações de Extração de Eventos**é adicionada à caixa de diálogo **Propriedades do Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="06a54-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog.</span></span>  
  
8.  <span data-ttu-id="06a54-123">No menu **Configurações de Extração de Eventos**, clique em **Salvar eventos de Plano de Execução XML separadamente**.</span><span class="sxs-lookup"><span data-stu-id="06a54-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="06a54-124">Na caixa de diálogo **alvar como** , digite o nome do arquivo para armazenar os eventos **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="06a54-124">In the **Save As** dialog box, enter the file name to store the **Showplan XML Statistics Profile** events.</span></span>  
  
10. <span data-ttu-id="06a54-125">Clique em **Todos os lotes em um único arquivo** para salvar todos os eventos **Showplan XML Statistics Profile** em um único arquivo XML ou clique em **Cada lote de Plano de Execução XML em um arquivo distinto**para criar um novo arquivo XML para cada evento **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="06a54-125">Click **All batches in a single file** to save all **Showplan XML Statistics Profile** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML Statistics Profile** event.</span></span>  
  
11. <span data-ttu-id="06a54-126">Para ver o arquivo do evento **Showplan XML Statistics Profile** no SQL Server Management Studio, no menu **Arquivo** , aponte para **Abrir**e clique em **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="06a54-126">To view the **Showplan XML Statistics Profile** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="06a54-127">Navegue até o diretório em que você salvou o arquivo (ou arquivos) de evento **Showplan XML Statistics Profile** para selecioná-lo e abri-lo.</span><span class="sxs-lookup"><span data-stu-id="06a54-127">Navigate to the directory where you saved the **Showplan XML Statistics Profile** event file or files to select one and open it.</span></span> <span data-ttu-id="06a54-128">Arquivos de evento**Showplan XML Statistics Profile** têm a extensão .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="06a54-128">**Showplan XML Statistics Profile** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a54-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06a54-129">See Also</span></span>  
 [<span data-ttu-id="06a54-130">Analisar consultas com resultados do Plano de Execução no SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="06a54-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
