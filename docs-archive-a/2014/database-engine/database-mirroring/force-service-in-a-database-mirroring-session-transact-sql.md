---
title: Forçar o serviço em uma sessão de espelhamento de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b909f3602a78f3244ab3cf4479b8745956a7bd62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685930"
---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="deff5-102">Forçar serviço em uma sessão de espelhamento de banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="deff5-102">Force Service in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="deff5-103">Em modo de alto desempenho e em modo de alta segurança sem failover automático, se o servidor principal falhar enquanto o servidor espelho estiver disponível, o proprietário do banco de dados poderá disponibilizar o banco de dados forçando o serviço para failover (com possível perda de dados) no banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="deff5-103">In high-performance mode and high-safety mode without automatic failover, if the principal server fails while the mirror server is available, the database owner can make the database available by forcing service to fail over (with possible data loss) to the mirror database.</span></span> <span data-ttu-id="deff5-104">Essa opção só está disponível sob todas as condições seguintes:</span><span class="sxs-lookup"><span data-stu-id="deff5-104">This option is available only under all the following conditions:</span></span>  
  
-   <span data-ttu-id="deff5-105">O servidor principal está fora de operação.</span><span class="sxs-lookup"><span data-stu-id="deff5-105">The principal server is down.</span></span>  
  
-   <span data-ttu-id="deff5-106">WITNESS está definido como OFF ou está conectado ao servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="deff5-106">WITNESS is set to OFF or is connected to the mirror server.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="deff5-107">O serviço forçado é estritamente um método de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="deff5-107">Forced service is strictly a disaster recovery method.</span></span> <span data-ttu-id="deff5-108">O serviço forçado pode envolver alguma perda de dados.</span><span class="sxs-lookup"><span data-stu-id="deff5-108">Forcing service may involve some data loss.</span></span> <span data-ttu-id="deff5-109">Portanto, só force o serviço se você estiver disposto a se arriscar perder alguns dados para restaurar o serviço no banco de dados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="deff5-109">Therefore, force service only if you are willing to risk losing some data in order to restore service to the database immediately.</span></span> <span data-ttu-id="deff5-110">Se forçar o serviço resultar em perda significativa de dados, recomendamos que você pare o espelhamento e sincronize novamente os bancos de dados manualmente.</span><span class="sxs-lookup"><span data-stu-id="deff5-110">If forcing service risks losing significant data, we recommend that you stop mirroring and manually resynchronize the databases.</span></span> <span data-ttu-id="deff5-111">Para obter mais informações sobre os riscos de forçar o serviço, veja [Modos de operação do espelhamento de banco de dados](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="deff5-111">For more information about the risks of forcing service, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="deff5-112">Quando o serviço é forçado, a sessão é suspensa e um novo ponto de bifurcação da recuperação é iniciado.</span><span class="sxs-lookup"><span data-stu-id="deff5-112">Forcing service suspends the session and starts a new recovery fork.</span></span> <span data-ttu-id="deff5-113">O efeito de forçar o serviço é semelhante a remover o espelhamento e recuperar o banco de dados principal antigo.</span><span class="sxs-lookup"><span data-stu-id="deff5-113">The effect of forcing service is similar to removing mirroring and recovering the former principal database.</span></span> <span data-ttu-id="deff5-114">No entanto, forçar o serviço facilita nova sincronização dos bancos de dados (com possível perda de dados) quando o espelhamento é retomado.</span><span class="sxs-lookup"><span data-stu-id="deff5-114">However, forcing service facilitates resynchronizing the databases (with possible data loss) when mirroring resumes.</span></span>  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a><span data-ttu-id="deff5-115">Para forçar serviço em uma sessão de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="deff5-115">To force service in a database mirroring session</span></span>  
  
1.  <span data-ttu-id="deff5-116">Conecte-se ao servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="deff5-116">Connect to the mirror server.</span></span>  
  
2.  <span data-ttu-id="deff5-117">Emita a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="deff5-117">Issue the following statement:</span></span>  
  
     <span data-ttu-id="deff5-118">ALTER DATABASE *<nome_banco_dados>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span><span class="sxs-lookup"><span data-stu-id="deff5-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span></span>  
  
     <span data-ttu-id="deff5-119">em que *<nome_banco_dados>* é o banco de dados espelhado.</span><span class="sxs-lookup"><span data-stu-id="deff5-119">where *<database_name>* is the mirrored database.</span></span>  
  
     <span data-ttu-id="deff5-120">O servidor espelho imediatamente faz a transição para servidor principal e o espelhamento é suspenso.</span><span class="sxs-lookup"><span data-stu-id="deff5-120">The mirror server immediately transitions to principal server, and mirroring is suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deff5-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="deff5-121">See Also</span></span>  
 <span data-ttu-id="deff5-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deff5-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="deff5-123">Modos de operação de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="deff5-123">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
