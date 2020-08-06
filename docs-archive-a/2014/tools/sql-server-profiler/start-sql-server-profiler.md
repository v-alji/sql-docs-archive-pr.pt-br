---
title: Iniciar SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: 22e57ffa-63b0-4de3-b92e-df297dda1226
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05743927420865a9b6341fc050ca999f494d64d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681988"
---
# <a name="start-sql-server-profiler"></a><span data-ttu-id="87d7c-102">Iniciar o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="87d7c-102">Start SQL Server Profiler</span></span>
  <span data-ttu-id="87d7c-103">É possível iniciar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] de várias maneiras diferentes para dar suporte à coleta da saída de rastreamento em vários cenários.</span><span class="sxs-lookup"><span data-stu-id="87d7c-103">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in several different ways to support gathering trace output in a variety of scenarios.</span></span> <span data-ttu-id="87d7c-104">Você pode iniciar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] no menu **Iniciar** , no menu **Ferramentas** do [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor e em vários locais do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87d7c-104">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] include from the **Start** menu, from the **Tools** menu in [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, and from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="87d7c-105">Quando você inicia o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pela primeira vez e seleciona **Novo Rastreamento** no menu **Arquivo** , o aplicativo exibe uma caixa de diálogo **Conectar ao Servidor** onde é possível especificar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="87d7c-105">When you first start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and select **New Trace** from the **File** menu, the application displays a **Connect to Server** dialog box where you can specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you want to connect.</span></span>  
  
### <a name="to-start-sql-server-profiler-from-the-start-menu"></a><span data-ttu-id="87d7c-106">Para iniciar o SQL Server Profiler no menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="87d7c-106">To start SQL Server Profiler from the Start menu</span></span>  
  
1.  <span data-ttu-id="87d7c-107">No menu **Iniciar** , aponte para **Todos os Programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Ferramentas de Desempenho**e clique em **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-107">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **SQL Server Profiler**.</span></span>  
  
### <a name="to-start-sql-server-profiler-in-database-engine-tuning-advisor"></a><span data-ttu-id="87d7c-108">Para iniciar o SQL Server Profiler no Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="87d7c-108">To start SQL Server Profiler in Database Engine Tuning Advisor</span></span>  
  
1.  <span data-ttu-id="87d7c-109">No menu [!INCLUDE[ssDE](../../includes/ssde-md.md)] Ferramentas **do Orientador de Otimização do** , clique em **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-109">On the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
## <a name="starting-sql-server-profiler-in-management-studio"></a><span data-ttu-id="87d7c-110">Iniciando o SQL Server Profiler no Management Studio</span><span class="sxs-lookup"><span data-stu-id="87d7c-110">Starting SQL Server Profiler in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="87d7c-111">inicia cada sessão do Profiler em sua própria instância e mantém a execução se você desligar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87d7c-111">starts each profiler session in its own instance and continues to run if you shutdown [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="87d7c-112">Você pode iniciar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] em vários locais do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conforme ilustrado nos procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="87d7c-112">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as illustrated in the following procedures.</span></span> <span data-ttu-id="87d7c-113">Quando é iniciado, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] carrega o contexto de conexão, o modelo de rastreamento e o contexto de filtro de seu ponto de inicialização.</span><span class="sxs-lookup"><span data-stu-id="87d7c-113">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] starts it loads the connection context, trace template, and filter context of its launch point.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-tools-menu"></a><span data-ttu-id="87d7c-114">Para iniciar o SQL Server Profiler no menu Ferramentas</span><span class="sxs-lookup"><span data-stu-id="87d7c-114">To start SQL Server Profiler from the Tools menu</span></span>  
  
1.  <span data-ttu-id="87d7c-115">No menu [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Ferramentas**, clique em **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-115">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-query-editor"></a><span data-ttu-id="87d7c-116">Para iniciar o SQL Server Profiler no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="87d7c-116">To start SQL Server Profiler from the Query Editor</span></span>  
  
1.  <span data-ttu-id="87d7c-117">Na barra de menus do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-117">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] menu bar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="87d7c-118">No Editor de Consultas, clique com o botão direito do mouse e selecione **Rastrear Consulta no SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-118">In Query Editor, right-click and then select **Trace Query in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="87d7c-119">O contexto de conexão é a conexão do editor, o modelo de rastreamento é TSQL_SPs e o filtro aplicado é SPID = SPID da janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="87d7c-119">The connection context is the editor connection, the trace template is TSQL_SPs, and the applied filter is SPID = query window SPID.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-activity-monitor"></a><span data-ttu-id="87d7c-120">Para iniciar o SQL Server Profiler no Monitor de Atividade</span><span class="sxs-lookup"><span data-stu-id="87d7c-120">To start SQL Server Profiler from Activity Monitor</span></span>  
  
1.  <span data-ttu-id="87d7c-121">No Pesquisador de Objetos, clique com o botão direito do mouse em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e clique em **Monitor de Atividade**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-121">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="87d7c-122">Clique no painel **Processos** , clique com o botão direito do mouse no processo cujo perfil você deseja criar e clique em **Rastrear Processo no SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="87d7c-122">Click the **Processes** pane, right-click the process that you want to profile, and then click **Trace Process in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="87d7c-123">Quando um processo é selecionado, o contexto de conexão é a conexão do Pesquisador de Objetos quando o Monitor de Atividade foi aberto.</span><span class="sxs-lookup"><span data-stu-id="87d7c-123">When a process is selected, the connection context is the Object Explorer connection when Activity Monitor was opened.</span></span> <span data-ttu-id="87d7c-124">O modelo de rastreamento é o padrão com base no tipo de servidor e o SPID é igual ao SPID do processo selecionado.</span><span class="sxs-lookup"><span data-stu-id="87d7c-124">The trace template is the default based on the server type, and the SPID equals the SPID for the selected process.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="87d7c-125">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="87d7c-125">.NET Framework Security</span></span>  
 <span data-ttu-id="87d7c-126">No modo de Autenticação do Windows, a conta do usuário que executa o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] deve ter permissão para conectar-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87d7c-126">In Windows Authentication mode, the user account that runs [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] must have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="87d7c-127">Para executar rastreamento com o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], os usuários também devem ter a permissão ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="87d7c-127">To perform tracing with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], users must also have the ALTER TRACE permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d7c-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87d7c-128">See Also</span></span>  
 <span data-ttu-id="87d7c-129">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="87d7c-129">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="87d7c-130">Usar o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="87d7c-130">Use SQL Server Management Studio</span></span>](../../database-engine/use-sql-server-management-studio.md)  
  
  
