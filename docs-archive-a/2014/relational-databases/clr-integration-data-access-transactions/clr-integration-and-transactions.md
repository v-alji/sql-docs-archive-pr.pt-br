---
title: Integração e transações do CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
author: rothja
ms.author: jroth
ms.openlocfilehash: de72a2113aeb568decbdc9b5ee0174160cc0d3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685796"
---
# <a name="clr-integration-and-transactions"></a><span data-ttu-id="a141f-102">Integração CLR e transações</span><span class="sxs-lookup"><span data-stu-id="a141f-102">CLR Integration and Transactions</span></span>
  <span data-ttu-id="a141f-103">O `System.Transactions` fornece uma estrutura de transação que é totalmente integrada com o ADO.NET e a integração CLR (Common Language Runtime) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a141f-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="a141f-104">`System.Transactions` e o ADO.NET operam juntos para estender e simplificar o uso de transações locais e distribuídas nos aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="a141f-104">`System.Transactions` and ADO.NET work together to extend and simplify the use of local and distributed transactions in managed applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a141f-105">Um UDP (user-defined procedure) CLR não pode estabelecer uma conexão com o mesmo servidor no qual está sendo executado (uma conexão de loopback) e se inscrever na mesma transação.</span><span class="sxs-lookup"><span data-stu-id="a141f-105">A CLR user-defined procedure (UDP) cannot establish a connection to the same server it is running on (a loopback connection) and enlist in the same transaction.</span></span> <span data-ttu-id="a141f-106">Caso uma dessas ações seja tentada, a tentativa de conexão será bloqueada e o controle não será devolvido ao UDP.</span><span class="sxs-lookup"><span data-stu-id="a141f-106">If this is attempted, the connection attempt will be blocked and control will not be passed back to the UDP.</span></span> <span data-ttu-id="a141f-107">Isso resultará em um erro de tempo limite (Msg 1206) no UDP.</span><span class="sxs-lookup"><span data-stu-id="a141f-107">This will result in a timeout error (Msg 1206) on the UDP.</span></span>  
  
 <span data-ttu-id="a141f-108">Para obter mais informações sobre transações e o .NET Framework, consulte "Performing Transactions" e "Leveraging Transactions" no SDK do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a141f-108">For more information about transactions and the .NET Framework, see "Performing Transactions" and "Leveraging Transactions" in the .NET Framework SDK.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a141f-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a141f-109">In This Section</span></span>  
 [<span data-ttu-id="a141f-110">Promoção de transações</span><span class="sxs-lookup"><span data-stu-id="a141f-110">Transaction Promotion</span></span>](transaction-promotion.md)  
 <span data-ttu-id="a141f-111">Descreve a capacidade de promover transações e como usar este recurso.</span><span class="sxs-lookup"><span data-stu-id="a141f-111">Describes the ability to promote transactions, and how to use this feature.</span></span>  
  
 [<span data-ttu-id="a141f-112">Acessando a transação atual</span><span class="sxs-lookup"><span data-stu-id="a141f-112">Accessing the Current Transaction</span></span>](accessing-the-current-transaction.md)  
 <span data-ttu-id="a141f-113">Descreve como acessar uma transação que está atualmente sendo executada em processo no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a141f-113">Describes how to access a transaction currently running in-process on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a141f-114">Usando System.Transactions</span><span class="sxs-lookup"><span data-stu-id="a141f-114">Using System.Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="a141f-115">Descreve como usar a API (application programming interface) `System.Transactions` em seu aplicativo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="a141f-115">Describes how to use the `System.Transactions` application programming interface (API) in your managed application.</span></span>  
  
 [<span data-ttu-id="a141f-116">Vidas úteis de transação</span><span class="sxs-lookup"><span data-stu-id="a141f-116">Transaction Lifetimes</span></span>](transaction-lifetimes.md)  
 <span data-ttu-id="a141f-117">Descreve a diferença no tempo de vida entre transações iniciadas nos procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] e transações iniciadas nos aplicativos de CLR.</span><span class="sxs-lookup"><span data-stu-id="a141f-117">Describes the difference in lifetime between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and transactions started in CLR applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a141f-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a141f-118">See Also</span></span>  
 [<span data-ttu-id="a141f-119">Acesso aos dados dos objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="a141f-119">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
