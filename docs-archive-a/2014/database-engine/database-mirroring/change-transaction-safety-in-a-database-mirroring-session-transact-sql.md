---
title: Alterar a segurança da transação em uma sessão de espelhamento de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- transaction safety [SQL Server database mirroring]
ms.assetid: 8b03bb82-8589-4558-8545-9942fe008391
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d8bc9d0fb639770d33507c29a6ec67f60bd0434a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571586"
---
# <a name="change-transaction-safety-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="74145-102">Alterar a segurança da transação em uma sessão de espelhamento de banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="74145-102">Change Transaction Safety in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="74145-103">A segurança da transação é o atributo que controla o modo de operação da sessão.</span><span class="sxs-lookup"><span data-stu-id="74145-103">Transaction safety is the attribute that controls the operating mode of the session.</span></span> <span data-ttu-id="74145-104">Em qualquer momento, porém, o proprietário do banco de dados pode alterar a segurança da transação.</span><span class="sxs-lookup"><span data-stu-id="74145-104">At any time, however, the database owner can change the transaction safety.</span></span> <span data-ttu-id="74145-105">Por padrão, o nível de segurança da transação é definido como FULL (modo de operação síncrono).</span><span class="sxs-lookup"><span data-stu-id="74145-105">By default, the level of transaction safety is set to FULL (synchronous operating mode).</span></span>  
  
 <span data-ttu-id="74145-106">Quando a segurança da transação é desativada, a sessão é alternada para o modo de operação assíncrono, que maximiza desempenho.</span><span class="sxs-lookup"><span data-stu-id="74145-106">Turning off transaction safety shifts the session into asynchronous operating mode, which maximizes performance.</span></span> <span data-ttu-id="74145-107">Se o servidor principal ficar indisponível, o espelho para, mas fica disponível em espera passiva (failover requer que o serviço seja forçado com possível perda de dados).</span><span class="sxs-lookup"><span data-stu-id="74145-107">If the principal becomes unavailable, the mirror stops but is available as a warm standby (failover requires forcing service with possible data loss).</span></span>  
  
### <a name="to-turn-on-transaction-safety"></a><span data-ttu-id="74145-108">Para ativar a segurança da transação</span><span class="sxs-lookup"><span data-stu-id="74145-108">To turn on transaction safety</span></span>  
  
1.  <span data-ttu-id="74145-109">Conecte-se ao servidor principal.</span><span class="sxs-lookup"><span data-stu-id="74145-109">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="74145-110">Emita a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="74145-110">Issue the following Transact-SQL statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY FULL  
    ```  
  
     <span data-ttu-id="74145-111">em que *\<database>* é o nome do banco de dados espelhado.</span><span class="sxs-lookup"><span data-stu-id="74145-111">where *\<database>* is the name of the mirrored database.</span></span>  
  
### <a name="to-turn-off-transaction-safety"></a><span data-ttu-id="74145-112">Para desativar a segurança da transação</span><span class="sxs-lookup"><span data-stu-id="74145-112">To turn off transaction safety</span></span>  
  
1.  <span data-ttu-id="74145-113">Conecte-se ao servidor principal.</span><span class="sxs-lookup"><span data-stu-id="74145-113">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="74145-114">Emita a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="74145-114">Issue the following statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY OFF  
    ```  
  
     <span data-ttu-id="74145-115">em que *\<database>* é o banco de dados espelhado.</span><span class="sxs-lookup"><span data-stu-id="74145-115">where *\<database>* is the mirrored database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74145-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74145-116">See Also</span></span>  
 <span data-ttu-id="74145-117">[Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="74145-117">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 [<span data-ttu-id="74145-118">Modos de operação de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="74145-118">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
