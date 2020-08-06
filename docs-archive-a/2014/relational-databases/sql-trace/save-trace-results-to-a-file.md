---
title: Salvar resultados de rastreamento em um arquivo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 74f80667-62f3-4e14-bb1a-f0c2b6ef3402
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 644fc812bbb4863c336ff2f53f5b2d67ee0a4d5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569843"
---
# <a name="save-trace-results-to-a-file"></a><span data-ttu-id="55956-102">Salvar resultados de rastreamento em um arquivo</span><span class="sxs-lookup"><span data-stu-id="55956-102">Save Trace Results to a File</span></span>
  <span data-ttu-id="55956-103">Você pode salvar os resultados de rastreamentos em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="55956-103">You can save trace results to a file.</span></span> <span data-ttu-id="55956-104">Um arquivo de rastreamento é um arquivo no qual são gravados os resultados de um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="55956-104">A trace file is a file where the trace results are written.</span></span> <span data-ttu-id="55956-105">Um arquivo de rastreamento pode estar localizado em um diretório local (como C:\\*foldername*\\*filename.trc*) ou em um diretório de rede (como \\\computername\sharename\filename.trc).</span><span class="sxs-lookup"><span data-stu-id="55956-105">A trace file can be located either in a local directory (such as C:\\*foldername*\\*filename.trc*) or a network directory (such as \\\computername\sharename\filename.trc).</span></span>  
  
 <span data-ttu-id="55956-106">É possível usar os arquivos de rastreamento para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55956-106">You can use the trace files to do the following:</span></span>  
  
-   <span data-ttu-id="55956-107">Repetir rastreamentos</span><span class="sxs-lookup"><span data-stu-id="55956-107">Replay traces</span></span>  
  
-   <span data-ttu-id="55956-108">Auditar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55956-108">Audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="55956-109">Conduzir análises de desempenho</span><span class="sxs-lookup"><span data-stu-id="55956-109">Conduct performance analysis</span></span>  
  
-   <span data-ttu-id="55956-110">Correlacionar eventos de rastreamento com contadores de desempenho para aperfeiçoar a detecção de problemas</span><span class="sxs-lookup"><span data-stu-id="55956-110">Correlate trace events with performance counters to enhance problem detection</span></span>  
  
-   <span data-ttu-id="55956-111">Executar análises do Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="55956-111">Perform Database Engine Tuning Advisor analysis</span></span>  
  
-   <span data-ttu-id="55956-112">Efetuar otimização de consultas</span><span class="sxs-lookup"><span data-stu-id="55956-112">Carry out query optimization</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="55956-113">salva os resultados de rastreamento em um arquivo quando um caminho e um nome de arquivo são especificados para o **@tracefile** argumento do procedimento armazenado **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="55956-113">saves trace results to a file when a path and file name are specified for the **@tracefile** argument of the stored procedure **sp_trace_create**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55956-114">Se for especificado um caminho para que o procedimento armazenado **sp_trace_create** para salvar o arquivo de rastreamento, o diretório deverá estar acessível ao servidor.</span><span class="sxs-lookup"><span data-stu-id="55956-114">If a path is specified to the **sp_trace_create** stored procedure for saving the trace file, the directory must be accessible to the server.</span></span> <span data-ttu-id="55956-115">Esteja ciente, ainda, de que, se for especificado um diretório local para **sp_trace_create**, terá de ser um diretório local no computador do servidor.</span><span class="sxs-lookup"><span data-stu-id="55956-115">Also be aware that if a local directory is specified to **sp_trace_create**, it is a local directory on the server computer.</span></span>  
  
 <span data-ttu-id="55956-116">Se o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] for usado, ele permitirá salvar os resultados do rastreamento em um arquivo ou em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="55956-116">If [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is used, it allows you to save trace results to a file or to a table.</span></span> <span data-ttu-id="55956-117">Salvar resultados de rastreamento em uma tabela permite o mesmo acesso que salvá-los em um arquivo, com o adicional de que a tabela poderá ser consultada quanto a eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="55956-117">Saving trace results to a table allows the same access as saving the trace to a file plus you can query the table to search for specific events.</span></span>  
  
 <span data-ttu-id="55956-118">Para obter mais informações sobre como salvar os resultados do rastreamento, veja [Salvar resultados de rastreamento em uma tabela &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) e [Salvar resultados de rastreamento em um arquivo &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="55956-118">For more information about saving trace results, see [Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) and [Save Trace Results to a File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55956-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55956-119">See Also</span></span>  
 <span data-ttu-id="55956-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="55956-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="55956-121">[Criar um rastreamento &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="55956-121">[Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span></span>  
 [<span data-ttu-id="55956-122">Criar um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="55956-122">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
