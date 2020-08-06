---
title: Criar um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], creating
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7d73333bbf0ba985ed4952e03584b4e4c130ab6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678414"
---
# <a name="create-a-trace-sql-server-profiler"></a><span data-ttu-id="5236d-102">Criar um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="5236d-102">Create a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="5236d-103">Este tópico descreve como usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para criar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5236d-103">This topic describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="5236d-104">Para criar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="5236d-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="5236d-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5236d-105">On the **File** menu, click **New Trace**, and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="5236d-106">É exibida a caixa de diálogo **Propriedades do Rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="5236d-106">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5236d-107">A caixa de diálogo **Propriedades do Rastreamento** não aparecerá, e o rastreamento será iniciado, se **Iniciar rastreamento imediatamente após estabelecer a conexão** será selecionado.</span><span class="sxs-lookup"><span data-stu-id="5236d-107">The **Trace Properties** dialog box fails to appear, and the trace begins instead, if **Start tracing immediately after making connection** is selected.</span></span> <span data-ttu-id="5236d-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="5236d-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="5236d-109">Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5236d-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="5236d-110">Na lista **Usar o modelo** , selecione um modelo como base para o rastreamento ou **Em branco** , se não quiser usar um modelo.</span><span class="sxs-lookup"><span data-stu-id="5236d-110">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="5236d-111">Para salvar os resultados do rastreamento, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5236d-111">To save the trace results, do one of the following:</span></span>  
  
    -   <span data-ttu-id="5236d-112">Clique em **Salvar em arquivo** para capturar o rastreamento em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="5236d-112">Click **Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="5236d-113">Especifique um valor para **Definir tamanho máximo do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="5236d-113">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="5236d-114">O valor padrão é 5 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="5236d-114">The default value is 5 megabytes (MB).</span></span>  
  
         <span data-ttu-id="5236d-115">Opcionalmente, selecione **Habilitar substituição de arquivo** para criar um novo arquivo automaticamente toda vez que o tamanho máximo for atingido.</span><span class="sxs-lookup"><span data-stu-id="5236d-115">Optionally, select **Enable file rollover** to automatically create new files when the maximum file size is reached.</span></span> <span data-ttu-id="5236d-116">Opcionalmente, você também pode selecionar **Dados de rastreamento de processos do servidor**, o que faz com que o serviço que estiver executando o rastreamento processe os dados do rastreamento, em vez do aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="5236d-116">You can also optionally select **Server processes trace data**, which causes the service that is running the trace to process trace data instead of the client application.</span></span> <span data-ttu-id="5236d-117">Quando o servidor processa dados de rastreamento, nenhum evento é ignorado, nem mesmo sob condições de estresse, mas o desempenho do servidor pode ser afetado.</span><span class="sxs-lookup"><span data-stu-id="5236d-117">When the server processes trace data, no events are skipped even under stress conditions, but server performance may be affected.</span></span>  
  
    -   <span data-ttu-id="5236d-118">Clique em **Salvar em tabela** para capturar o rastreamento em uma tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5236d-118">Click **Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="5236d-119">Opcionalmente, clique em **Definir máximo de linhas**e especifique um valor.</span><span class="sxs-lookup"><span data-stu-id="5236d-119">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="5236d-120">Quando você não salva os resultados do rastreamento em um arquivo ou tabela, pode exibir o rastreamento enquanto o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="5236d-120">When you do not save the trace results to a file or table, you can view the trace while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is open.</span></span> <span data-ttu-id="5236d-121">No entanto, os resultados serão perdidos depois que o rastreamento for interrompido e o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]for fechado.</span><span class="sxs-lookup"><span data-stu-id="5236d-121">However, you lose the trace results after you stop the trace and close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="5236d-122">Para evitar perder os resultados do rastreamento dessa forma, clique em **Salvar** no menu **Arquivo** para salvar os resultados antes de fechar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5236d-122">To avoid losing the trace results in this way, click **Save** on the **File** menu to save the results before you close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
5.  <span data-ttu-id="5236d-123">Opcionalmente, marque a caixa de seleção **Habilitar horário de parada do rastreamento** e especifique uma data e hora de parada.</span><span class="sxs-lookup"><span data-stu-id="5236d-123">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="5236d-124">Para adicionar ou remover eventos, colunas de dados ou filtros, clique na guia **Seleção de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="5236d-124">To add or remove events, data columns or filters, click the **Events Selection**tab.</span></span> <span data-ttu-id="5236d-125">Para obter mais informações, consulte: [Especificar eventos e colunas de dados para um arquivo de rastreamento &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="5236d-125">For more information, see: [Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span></span>  
  
7.  <span data-ttu-id="5236d-126">Clique em **Executar** para iniciar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5236d-126">Click **Run** to start the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5236d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5236d-127">See Also</span></span>  
 <span data-ttu-id="5236d-128">[Permissões necessárias para executar o SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5236d-128">[Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5236d-129">[Modelos e permissões do SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="5236d-129">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="5236d-130">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5236d-130">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="5236d-131">Correlacionar um rastreamento com dados do log de desempenho do Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="5236d-131">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
