---
title: Permissões necessárias para executar o SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], permissions
- traces [SQL Server], replaying
- replaying traces
- SQL Server Profiler, permissions
- security [SQL Server], SQL Server Profiler
ms.assetid: 5c580a87-88ae-4314-8fe1-54ade83f227f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e73ffe2e127299db9a9e37e48f089aab2cccca52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683847"
---
# <a name="permissions-required-to-run-sql-server-profiler"></a><span data-ttu-id="f2531-102">Permissões necessárias para executar o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f2531-102">Permissions Required to Run SQL Server Profiler</span></span>
  <span data-ttu-id="f2531-103">Por padrão, executar o [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requer as mesmas permissões de usuário que os procedimentos armazenados Transact-SQL utilizados para criar rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="f2531-103">By default, running [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requires the same user permissions as the Transact-SQL stored procedures that are used to create traces.</span></span> <span data-ttu-id="f2531-104">Para executar o [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], os usuários devem dispor da permissão ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="f2531-104">To run [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], users must be granted the ALTER TRACE permission.</span></span> <span data-ttu-id="f2531-105">Para obter mais informações, veja [Permissões GRANT do servidor &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f2531-105">For more information, see [GRANT Server Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="f2531-106">Os usuários que tiverem a permissão SHOWPLAN, ALTER TRACE ou VIEW SERVER STATE poderão exibir consultas capturadas na saída do Plano de Execução.</span><span class="sxs-lookup"><span data-stu-id="f2531-106">Users who have the SHOWPLAN, the ALTER TRACE, or the VIEW SERVER STATE permission can view queries that are captured in Showplan output.</span></span> <span data-ttu-id="f2531-107">Essas consultas podem conter informações confidenciais, como senhas.</span><span class="sxs-lookup"><span data-stu-id="f2531-107">These queries may contain sensitive information such as passwords.</span></span> <span data-ttu-id="f2531-108">Portanto, é recomendável que você somente conceda essas permissões a usuários autorizados a exibir informações confidenciais, como membros da função de banco de dados fixa db_owner, ou membros da função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="f2531-108">Therefore, we recommend that you only grant these permissions to users who are authorized to view sensitive information, such as members of the db_owner fixed database role, or members of the sysadmin fixed server role.</span></span> <span data-ttu-id="f2531-109">Além disso, também é recomendável somente salvar arquivos do Plano de Execução ou arquivos de rastreamento que contenham eventos relacionados ao Plano de Execução em um local que use o sistema de arquivos NTFS e restringir o acesso a usuários autorizados a exibir informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="f2531-109">Additionally, we recommend that you only save Showplan files or trace files that contain Showplan-related events to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view sensitive information.</span></span>

## <a name="permissions-used-to-replay-traces"></a><span data-ttu-id="f2531-110">Permissões usadas para repetir rastreamentos</span><span class="sxs-lookup"><span data-stu-id="f2531-110">Permissions Used to Replay Traces</span></span>
 <span data-ttu-id="f2531-111">Repetir rastreamentos também requer que o usuário responsável disponha da permissão ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="f2531-111">Replaying traces also requires that the user who is replaying the trace have the ALTER TRACE permission.</span></span>

 <span data-ttu-id="f2531-112">No entanto, durante a repetição, o [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] usará o comando EXECUTE AS se um evento Audit Login for encontrado no rastreamento que está sendo repetido.</span><span class="sxs-lookup"><span data-stu-id="f2531-112">However, during replay, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] uses the EXECUTE AS command if an Audit Login event is encountered in the trace that is being replayed.</span></span> [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f2531-113">usa o comando EXECUTE AS para representar o usuário associado ao evento de logon.</span><span class="sxs-lookup"><span data-stu-id="f2531-113">uses the EXECUTE AS command to impersonate the user who is associated with the login event.</span></span>

 <span data-ttu-id="f2531-114">Se o [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encontrar um evento de logon em um rastreamento que está sendo repetido, serão realizadas as seguintes verificações de permissão:</span><span class="sxs-lookup"><span data-stu-id="f2531-114">If [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encounters a login event in a trace that is being replayed, the following permission checks are performed:</span></span>

1.  <span data-ttu-id="f2531-115">O Usuário1, que tem a permissão ALTER TRACE, inicia a repetição de um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="f2531-115">User1, who has the ALTER TRACE permission, starts replaying a trace.</span></span>

2.  <span data-ttu-id="f2531-116">Um evento de logon para o Usuário2 é encontrado no rastreamento que está sendo repetido.</span><span class="sxs-lookup"><span data-stu-id="f2531-116">A login event for User2 is encountered in the replayed trace.</span></span>

3.  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f2531-117">usa o comando EXECUTE AS para representar o User2.</span><span class="sxs-lookup"><span data-stu-id="f2531-117">uses the EXECUTE AS command to impersonate User2.</span></span>

4.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f2531-118">tenta autenticar User2 e, dependendo dos resultados, uma destas situações ocorrerá:</span><span class="sxs-lookup"><span data-stu-id="f2531-118">attempts to authenticate User2, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="f2531-119">Se o Usuário2 não puder ser autenticado, o [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] retornará um erro e continuará repetindo o rastreamento como Usuário1.</span><span class="sxs-lookup"><span data-stu-id="f2531-119">If User2 cannot be authenticated, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] returns an error, and continues replaying the trace as User1.</span></span>

    2.  <span data-ttu-id="f2531-120">Se o Usuário2 for autenticado com êxito, a repetição do rastreamento continua como Usuário2.</span><span class="sxs-lookup"><span data-stu-id="f2531-120">If User2 is successfully authenticated, replaying the trace as User2 continues.</span></span>

5.  <span data-ttu-id="f2531-121">As permissões do Usuário2 são verificadas no banco de dados de destino e, dependendo dos resultados, uma destas situações ocorrerá:</span><span class="sxs-lookup"><span data-stu-id="f2531-121">Permissions for User2 are checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="f2531-122">Se o Usuário2 tiver permissões no banco de dados de destino, a representação tem êxito e o rastreamento é repetido como Usuário2.</span><span class="sxs-lookup"><span data-stu-id="f2531-122">If User2 has permissions on the target database, impersonation has succeeded, and the trace is replayed as User2.</span></span>

    2.  <span data-ttu-id="f2531-123">Se o Usuário2 não tiver permissões no banco de dados de destino, o servidor buscará um usuário Convidado naquele banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f2531-123">If User2 does not have permissions on the target database, the server checks for a Guest user on that database.</span></span>

6.  <span data-ttu-id="f2531-124">A existência de um usuário Convidado é verificada no banco de dados de destino e, dependendo dos resultados, uma destas situações ocorrerá:</span><span class="sxs-lookup"><span data-stu-id="f2531-124">Existence of a Guest user is checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="f2531-125">Se existir uma conta Convidado, o rastreamento é repetido como a conta Convidado.</span><span class="sxs-lookup"><span data-stu-id="f2531-125">If a Guest account exists, the trace is replayed as the Guest account.</span></span>

    2.  <span data-ttu-id="f2531-126">Se não existir conta Convidado no banco de dados de destino, é retornado um erro e o rastreamento é repetido como Usuário1.</span><span class="sxs-lookup"><span data-stu-id="f2531-126">If no Guest account exists on the target database, an error is returned and the trace is replayed as User1.</span></span>

 <span data-ttu-id="f2531-127">O diagrama a seguir mostra esse processo de verificação de permissões durante a repetição de rastreamentos:</span><span class="sxs-lookup"><span data-stu-id="f2531-127">The following diagram shows this process of checking permission when replaying traces:</span></span>

 <span data-ttu-id="f2531-128">![Permissões de rastreamento de repetição do SQL Server Profiler](../../database-engine/media/replaytracedecisiontree.gif "Permissões de rastreamento de repetição do SQL Server Profiler")</span><span class="sxs-lookup"><span data-stu-id="f2531-128">![SQL Server Profiler replay trace permissions](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler replay trace permissions")</span></span>

## <a name="see-also"></a><span data-ttu-id="f2531-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2531-129">See Also</span></span>
 <span data-ttu-id="f2531-130">[SQL Server Profiler procedimentos armazenados &#40;o Transact-SQL&#41;os](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [rastreamentos de reprodução](replay-traces.md) [criam um &#40;de rastreamento SQL Server Profiler](create-a-trace-sql-server-profiler.md)&#41;[reprodução de uma tabela de rastreamento &#40;](replay-a-trace-table-sql-server-profiler.md) SQL Server Profiler&#41;[reproduz um arquivo de rastreamento &#40;](replay-a-trace-file-sql-server-profiler.md) SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f2531-130">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [Create a Trace &#40;SQL Server Profiler&#41;](create-a-trace-sql-server-profiler.md) [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md)</span></span>


