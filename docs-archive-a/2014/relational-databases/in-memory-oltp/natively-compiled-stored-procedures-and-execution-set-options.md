---
title: Procedimentos armazenados compilados nativamente e opções de execução de set | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c1869cf7-9030-4d18-85d6-0e419a4e9af7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 264a2b3ab1e6f3f0bda97bfe89a4438aa641577d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685681"
---
# <a name="natively-compiled-stored-procedures-and-execution-set-options"></a><span data-ttu-id="7cd5d-102">Procedimentos armazenados compilados nativamente e opções de execução Set</span><span class="sxs-lookup"><span data-stu-id="7cd5d-102">Natively Compiled Stored Procedures and Execution Set Options</span></span>
  <span data-ttu-id="7cd5d-103">As opções de sessão são corrigidas nos blocos atômicos.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-103">Session options are fixed in atomic blocks.</span></span> <span data-ttu-id="7cd5d-104">A execução de um procedimento armazenado não é afetada pelas opções SET de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-104">A stored procedure's execution is not affected by a session's SET options.</span></span> <span data-ttu-id="7cd5d-105">No entanto, determinadas opções SET, como SET NOEXEC e SET SHOWPLAN_XML, fazem com que os procedimentos armazenados (incluindo os procedimentos armazenados compilados nativamente) não sejam executados.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-105">However, certain SET options, such as SET NOEXEC and SET SHOWPLAN_XML, cause stored procedures (including natively compiled stored procedures) to not execute.</span></span>  
  
 <span data-ttu-id="7cd5d-106">Quando um procedimento armazenado compilado nativamente for executado com qualquer opção STATISTICS ativada, as estatísticas serão coletadas para o procedimento como um todo, e não por instrução.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-106">When a natively compiled stored procedure is executed with any STATISTICS option turned on, statistics are gathered for the procedure as a whole and not per statement.</span></span> <span data-ttu-id="7cd5d-107">Para obter mais informações, veja [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql) e [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7cd5d-107">For more information, see [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql), and [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span></span> <span data-ttu-id="7cd5d-108">Para obter estatísticas de execução no nível por instrução em procedimentos armazenados criados nativamente, use uma sessão de evento estendido no evento sp_statement_completed, que inicia quando cada consulta individual em uma execução de procedimentos armazenados é concluída.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-108">To obtain execution statistics on a per-statement level in natively compiled stored procedures, use an Extended Event session on the sp_statement_completed event, which starts when each individual query in a stored procedures execution completes.</span></span> <span data-ttu-id="7cd5d-109">Para obter mais informações sobre como criar sessões de Eventos Estendidos, veja [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7cd5d-109">For more information on creating Extended Event sessions, see [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span></span>  
  
 <span data-ttu-id="7cd5d-110">Há suporte para o `SHOWPLAN_XML` para procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-110">`SHOWPLAN_XML` is supported for natively compiled stored procedures.</span></span> <span data-ttu-id="7cd5d-111">Não há suporte para `SHOWPLAN_ALL` e `SHOWPLAN_TEXT` com procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-111">`SHOWPLAN_ALL` and `SHOWPLAN_TEXT` are not supported with natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="7cd5d-112">Não há suporte para `SET FMTONLY` com procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-112">`SET FMTONLY` in not supported with natively compiled stored procedures.</span></span> <span data-ttu-id="7cd5d-113">Em vez disso, use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7cd5d-113">Use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd5d-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7cd5d-114">See Also</span></span>  
 [<span data-ttu-id="7cd5d-115">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="7cd5d-115">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
