---
title: Requisitos de repetição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event classes [SQL Server], replaying traces
- traces [SQL Server], replaying
- replaying traces
- TSQL_Replay template [SQL Server]
ms.assetid: 0e01dfc7-84b9-47f6-8bf7-b0656df4fa7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65546f6820765286b558d2043e0155a79a07eb58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683833"
---
# <a name="replay-requirements"></a><span data-ttu-id="36798-102">Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="36798-102">Replay Requirements</span></span>
  <span data-ttu-id="36798-103">Para reproduzir dados de rastreamento com o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou o Distributed Replay Utility, um conjunto específico de colunas e classes de evento deve ser capturado no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="36798-103">In order to replay trace data with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or the Distributed Replay Utility, a specific set of event classes and columns must be captured in the trace.</span></span> <span data-ttu-id="36798-104">Essas configurações serão habilitadas por padrão se o modelo de rastreamento **TSQL_Replay** for usado para configurar um rastreamento que será usado posteriormente para reprodução.</span><span class="sxs-lookup"><span data-stu-id="36798-104">These settings are enabled by default if the **TSQL_Replay** trace template is used to configure a trace that is later used for replay.</span></span> <span data-ttu-id="36798-105">Este tópico descreve estas configurações e outros requisitos de reprodução.</span><span class="sxs-lookup"><span data-stu-id="36798-105">This topic describes these settings and other replay requirements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36798-106">É recomendável usar o Distributed Replay Utility para reproduzir um aplicativo OLTP intensivo (com muitas conexões simultâneas ativas ou alta taxa de transferência).</span><span class="sxs-lookup"><span data-stu-id="36798-106">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="36798-107">O Distributed Replay Utility pode reproduzir dados de rastreamento de vários computadores, com uma simulação melhor de uma carga de trabalho de missão crítica.</span><span class="sxs-lookup"><span data-stu-id="36798-107">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="36798-108">Para obter mais informações, consulte [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="36798-108">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="event-classes-required-for-replay"></a><span data-ttu-id="36798-109">Classes de evento necessárias para reprodução</span><span class="sxs-lookup"><span data-stu-id="36798-109">Event Classes Required for Replay</span></span>  
 <span data-ttu-id="36798-110">Para serem reproduzidos pelo [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], o conjunto de classes de evento a seguir, além de outras classes de evento que você deseja monitorar, deve ser capturado no rastreamento:</span><span class="sxs-lookup"><span data-stu-id="36798-110">To be replayed by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], the following set of event classes, in addition to any other event classes you want to monitor, must be captured in the trace:</span></span>  
  
-   <span data-ttu-id="36798-111">**CursorClose (** necessário apenas para a reprodução de cursores do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-111">**CursorClose (** only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="36798-112">**CursorExecute** (necessário apenas para a repetição de cursores do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-112">**CursorExecute** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="36798-113">**CursorOpen** (necessário apenas para a repetição de cursores do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-113">**CursorOpen** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="36798-114">**CursorPrepare** (necessário apenas para a repetição de cursores do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-114">**CursorPrepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="36798-115">**CursorUnprepare** (necessário apenas para a repetição de cursores do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-115">**CursorUnprepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="36798-116">**Audit Login**</span><span class="sxs-lookup"><span data-stu-id="36798-116">**Audit Login**</span></span>  
  
-   <span data-ttu-id="36798-117">**Audit Logout**</span><span class="sxs-lookup"><span data-stu-id="36798-117">**Audit Logout**</span></span>  
  
-   <span data-ttu-id="36798-118">**ExistingConnection**</span><span class="sxs-lookup"><span data-stu-id="36798-118">**ExistingConnection**</span></span>  
  
-   <span data-ttu-id="36798-119">**RPC Output Parameter**</span><span class="sxs-lookup"><span data-stu-id="36798-119">**RPC Output Parameter**</span></span>  
  
-   <span data-ttu-id="36798-120">**RPC:Completed**</span><span class="sxs-lookup"><span data-stu-id="36798-120">**RPC:Completed**</span></span>  
  
-   <span data-ttu-id="36798-121">**RPC:Starting**</span><span class="sxs-lookup"><span data-stu-id="36798-121">**RPC:Starting**</span></span>  
  
-   <span data-ttu-id="36798-122">**Exec Prepared SQL** (necessário apenas para a repetição de instruções SQL preparadas do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-122">**Exec Prepared SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="36798-123">**Prepare SQL** (necessário apenas para a reprodução de instruções SQL preparadas do lado do servidor)</span><span class="sxs-lookup"><span data-stu-id="36798-123">**Prepare SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="36798-124">**SQL:BatchCompleted**</span><span class="sxs-lookup"><span data-stu-id="36798-124">**SQL:BatchCompleted**</span></span>  
  
-   <span data-ttu-id="36798-125">**SQL:BatchStarting**</span><span class="sxs-lookup"><span data-stu-id="36798-125">**SQL:BatchStarting**</span></span>  
  
## <a name="data-columns-required-for-replay"></a><span data-ttu-id="36798-126">Colunas de dados necessárias para reprodução</span><span class="sxs-lookup"><span data-stu-id="36798-126">Data Columns Required for Replay</span></span>  
 <span data-ttu-id="36798-127">Além das outras colunas de dados que você deseja capturar, as seguintes colunas de dados devem ser capturadas em um rastreamento para que ele possa ser reproduzido:</span><span class="sxs-lookup"><span data-stu-id="36798-127">In addition to any other data columns you want to capture, the following data columns must be captured in a trace to allow the trace to be replayed:</span></span>  
  
-   <span data-ttu-id="36798-128">**Event Class**</span><span class="sxs-lookup"><span data-stu-id="36798-128">**Event Class**</span></span>  
  
-   <span data-ttu-id="36798-129">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="36798-129">**EventSequence**</span></span>  
  
-   <span data-ttu-id="36798-130">**TextData**</span><span class="sxs-lookup"><span data-stu-id="36798-130">**TextData**</span></span>  
  
-   <span data-ttu-id="36798-131">**Nome do Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="36798-131">**Application Name**</span></span>  
  
-   <span data-ttu-id="36798-132">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="36798-132">**LoginName**</span></span>  
  
-   <span data-ttu-id="36798-133">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="36798-133">**DatabaseName**</span></span>  
  
-   <span data-ttu-id="36798-134">**ID do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="36798-134">**Database ID**</span></span>  
  
-   <span data-ttu-id="36798-135">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="36798-135">**ClientProcessID**</span></span>  
  
-   <span data-ttu-id="36798-136">**HostName**</span><span class="sxs-lookup"><span data-stu-id="36798-136">**HostName**</span></span>  
  
-   <span data-ttu-id="36798-137">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="36798-137">**ServerName**</span></span>  
  
-   <span data-ttu-id="36798-138">**Binary Data**</span><span class="sxs-lookup"><span data-stu-id="36798-138">**Binary Data**</span></span>  
  
-   <span data-ttu-id="36798-139">**SPID**</span><span class="sxs-lookup"><span data-stu-id="36798-139">**SPID**</span></span>  
  
-   <span data-ttu-id="36798-140">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="36798-140">**Start Time**</span></span>  
  
-   <span data-ttu-id="36798-141">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="36798-141">**EndTime**</span></span>  
  
-   <span data-ttu-id="36798-142">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="36798-142">**IsSystem**</span></span>  
  
-   <span data-ttu-id="36798-143">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="36798-143">**NTDomainName**</span></span>  
  
-   <span data-ttu-id="36798-144">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="36798-144">**NTUserName**</span></span>  
  
-   <span data-ttu-id="36798-145">**Erro**</span><span class="sxs-lookup"><span data-stu-id="36798-145">**Error**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36798-146">Use o modelo de rastreamento **TSQL_Replay** para rastreamentos que capturam dados para reprodução.</span><span class="sxs-lookup"><span data-stu-id="36798-146">Use the trace template **TSQL_Replay** for traces that capture data for replay.</span></span>  
  
## <a name="other-replay-requirements"></a><span data-ttu-id="36798-147">Outros requisitos da reprodução</span><span class="sxs-lookup"><span data-stu-id="36798-147">Other Replay Requirements</span></span>  
 <span data-ttu-id="36798-148">No Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a reprodução verifica a presença dos eventos e colunas necessários.</span><span class="sxs-lookup"><span data-stu-id="36798-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], replay checks for the presence of required events and columns.</span></span> <span data-ttu-id="36798-149">Esta alteração ajuda a melhorar a precisão de repetição e retira a incerteza da repetição para solução de problemas, quando há dados necessários faltando.</span><span class="sxs-lookup"><span data-stu-id="36798-149">This change helps improve the accuracy of replay and takes the guesswork out of troubleshooting replay when required data is missing.</span></span> <span data-ttu-id="36798-150">A repetição retorna um erro e para de repetir um arquivo quando dados necessários estão faltando em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="36798-150">Replay returns an error and stops replaying a file when required data is missing from a trace.</span></span>  
  
 <span data-ttu-id="36798-151">Para repetir um rastreamento contra um servidor (o destino) no qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esteja executando, diferente do que foi rastreado originalmente (a origem), certifique-se de ter sido feito o seguinte:</span><span class="sxs-lookup"><span data-stu-id="36798-151">To replay a trace against a server (the target) on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running other than the server originally traced (the source), make sure the following has been done:</span></span>  
  
-   <span data-ttu-id="36798-152">Todos os logons e usuários contidos no rastreamento já devem ter sido criados no destino e no mesmo banco de dados da origem.</span><span class="sxs-lookup"><span data-stu-id="36798-152">All logins and users contained in the trace must be created already on the target and in the same database as the source.</span></span>  
  
-   <span data-ttu-id="36798-153">Todos os logons e usuários no destino devem ter as mesmas permissões que tinham na origem.</span><span class="sxs-lookup"><span data-stu-id="36798-153">All logins and users in the target must have the same permissions they had in the source.</span></span>  
  
-   <span data-ttu-id="36798-154">Todas as senhas de logon devem ser idênticas àquelas do usuário que executa a repetição.</span><span class="sxs-lookup"><span data-stu-id="36798-154">All login passwords must be the same as those of the user that executes the replay.</span></span>  
  
-   <span data-ttu-id="36798-155">As IDs do banco de dados no destino devem, idealmente, ser idênticas àquela na origem.</span><span class="sxs-lookup"><span data-stu-id="36798-155">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="36798-156">No entanto, se essas permissões não forem iguais, a correspondência poderá ser executada com base no **DatabaseName** se estiver presente no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="36798-156">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="36798-157">O banco de dados padrão de cada logon contido no rastreamento deve estar configurado (no destino) para o respectivo banco de dados de destino do logon.</span><span class="sxs-lookup"><span data-stu-id="36798-157">The default database for each login contained in the trace must be set (on the target) to the respective target database of the login.</span></span> <span data-ttu-id="36798-158">Por exemplo, o rastreamento a ser repetido contém atividade do logon **Fred**no banco de dados **Fred_Db** na origem.</span><span class="sxs-lookup"><span data-stu-id="36798-158">For example, the trace to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the source.</span></span> <span data-ttu-id="36798-159">Portanto, no destino, o banco de dados padrão do logon **Fred**deve estar configurado para o banco de dados que corresponde a **Fred_Db** (mesmo que o nome do banco de dados seja diferente).</span><span class="sxs-lookup"><span data-stu-id="36798-159">Therefore, on the target, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="36798-160">Para configurar o banco de dados padrão do logon, use o procedimento armazenado de sistema **sp_defaultdb** .</span><span class="sxs-lookup"><span data-stu-id="36798-160">To set the default database of the login, use the **sp_defaultdb** system stored procedure.</span></span>  
  
 <span data-ttu-id="36798-161">A repetição de eventos associados com logons faltantes ou incorretos resulta em erros de repetição, mas a operação de repetição continua.</span><span class="sxs-lookup"><span data-stu-id="36798-161">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
 <span data-ttu-id="36798-162">Para obter informações sobre quais permissões são necessárias para reproduzir um rastreamento, veja [Permissões necessárias para executar o SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="36798-162">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36798-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36798-163">See Also</span></span>  
 <span data-ttu-id="36798-164">[Reproduzir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="36798-164">[Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="36798-165">[Reproduzir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="36798-165">[Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="36798-166">[Referência de classe de evento do SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="36798-166">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="36798-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="36798-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span></span>  
 [<span data-ttu-id="36798-168">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="36798-168">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
