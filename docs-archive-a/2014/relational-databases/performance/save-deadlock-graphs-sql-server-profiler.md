---
title: Salvar gráficos de deadlock (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], saving deadlock graphs
- graphs [SQL Server]
- saving deadlock graphs
ms.assetid: bf1fc906-abd6-4a89-842e-da0d66b2defe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cdd0bd808ba4b934e5b2d91c9079909acf6e3997
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575778"
---
# <a name="save-deadlock-graphs-sql-server-profiler"></a><span data-ttu-id="091e4-102">Salvar gráficos de deadlock (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="091e4-102">Save Deadlock Graphs (SQL Server Profiler)</span></span>
  <span data-ttu-id="091e4-103">Este tópico descreve como salvar um gráfico de deadlock usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="091e4-103">This topic describes how to save a deadlock graph by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="091e4-104">Gráficos de deadlock são salvos como arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="091e4-104">Deadlock graphs are saved as XML files.</span></span>  
  
### <a name="to-save-deadlock-graph-events-separately"></a><span data-ttu-id="091e4-105">Para salvar eventos de gráfico de deadlock separadamente</span><span class="sxs-lookup"><span data-stu-id="091e4-105">To save deadlock graph events separately</span></span>  
  
1.  <span data-ttu-id="091e4-106">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte a uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="091e4-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="091e4-107">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="091e4-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="091e4-108">Se a opção **Iniciar rastreamento imediatamente após estabelecer a conexão** estiver marcada, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="091e4-108">If **Start tracing immediately after making connection** is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="091e4-109">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="091e4-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="091e4-110">Na caixa de diálogo Propriedades do Rastreamento, digite um nome para o rastreamento na caixa**Nome do rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="091e4-110">In the Trace Properties dialog box, type a name for the trace in the**Trace name** box.</span></span>  
  
3.  <span data-ttu-id="091e4-111">Na lista **Usar o modelo** , selecione um modelo como base para o rastreamento ou **Em branco** , se não quiser usar um modelo.</span><span class="sxs-lookup"><span data-stu-id="091e4-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="091e4-112">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="091e4-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="091e4-113">Marque a caixa de seleção**Salvar em arquivo** para capturar o rastreamento em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="091e4-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="091e4-114">Especifique um valor para **Definir tamanho máximo do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="091e4-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="091e4-115">Opcionalmente, selecione **Habilitar substituição de arquivo** e **Dados de rastreamento de processos do servidor**.</span><span class="sxs-lookup"><span data-stu-id="091e4-115">Optionally, select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="091e4-116">Marque a caixa de seleção **Salvar em tabela** para capturar o rastreamento em uma tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="091e4-116">Select the **Save to table** check box to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="091e4-117">Opcionalmente, clique em **Definir máximo de linhas**e especifique um valor.</span><span class="sxs-lookup"><span data-stu-id="091e4-117">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="091e4-118">Opcionalmente, marque a caixa de seleção **Habilitar horário de parada do rastreamento** e especifique uma data e hora de parada.</span><span class="sxs-lookup"><span data-stu-id="091e4-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="091e4-119">Clique na guia **Seleção de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="091e4-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="091e4-120">Na coluna de dados **Eventos**, expanda a categoria de evento **Locks**e marque a caixa de seleção **Gráfico de deadlock**.</span><span class="sxs-lookup"><span data-stu-id="091e4-120">In the **Events**data column, expand the **Locks**event category, and then select the **Deadlock graph**check box.</span></span> <span data-ttu-id="091e4-121">Se a categoria de evento Locks não estiver disponível, marque **Mostrar todos os eventos** para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="091e4-121">If the Locks event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="091e4-122">A caixa de diálogo **Configurações de Extração de Eventos**é adicionada à caixa de diálogo **Propriedades do Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="091e4-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="091e4-123">Na guia **Configurações de Extração de Eventos**, clique em **Salvar eventos deadlock XML separadamente**.</span><span class="sxs-lookup"><span data-stu-id="091e4-123">On the **Events Extraction Settings**tab, click **Save Deadlock XML Events Separately**.</span></span>  
  
9. <span data-ttu-id="091e4-124">Na caixa de diálogo **Salvar Como** , digite um nome para o arquivo no qual armazenar os eventos de gráfico de deadlock.</span><span class="sxs-lookup"><span data-stu-id="091e4-124">In the **Save As** dialog box, enter the name of the file in which to store the deadlock graph events.</span></span>  
  
10. <span data-ttu-id="091e4-125">Clique em **Todos os lotes de deadlock XML em um único arquivo** para salvar todos os eventos de gráfico de deadlock em um mesmo arquivo XML, ou clique em **Cada lote de deadlock XML em um arquivo distinto**, para criar um novo arquivo XML para cada gráfico de deadlock.</span><span class="sxs-lookup"><span data-stu-id="091e4-125">Click **All Deadlock XML batches in a single file** to save all deadlock graph events in a single XML file, or click **Each Deadlock XML batch in a distinct file**to create a new XML file for each deadlock graph.</span></span>  
  
 <span data-ttu-id="091e4-126">Após salvar o arquivo de deadlock, você pode abri-lo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="091e4-126">After you have saved the deadlock file, you can open the file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="091e4-127">Para obter mais informações, consulte [abrir, exibir e imprimir um arquivo de Deadlock &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="091e4-127">For more information, see [Open, View, and Print a Deadlock File &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091e4-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="091e4-128">See Also</span></span>  
 [<span data-ttu-id="091e4-129">Analisar deadlocks com o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="091e4-129">Analyze Deadlocks with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler.md)  
  
  
