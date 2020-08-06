---
title: Tempos de vida da transação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- lifetimes [SQL Server]
- Transact-SQL vs. managed code
ms.assetid: cb076fda-6488-4959-a6a4-7adaccf3f25c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c00050ee323cade7493d44c4c296ba4ce6811e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685793"
---
# <a name="transaction-lifetimes"></a><span data-ttu-id="a3fe8-102">Vidas úteis de transação</span><span class="sxs-lookup"><span data-stu-id="a3fe8-102">Transaction Lifetimes</span></span>
  <span data-ttu-id="a3fe8-103">Há uma diferença importante entre as transações iniciadas nos procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] e aquelas iniciadas no código gerenciado: o código CLR (common language runtime) não pode desequilibrar o estado da transação na entrada ou saída de uma invocação CLR.</span><span class="sxs-lookup"><span data-stu-id="a3fe8-103">There is an important difference between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and those started in managed code: common language runtime (CLR) code cannot unbalance the transaction state on entry or exit of a CLR invocation.</span></span> <span data-ttu-id="a3fe8-104">Esteja ciente das seguintes implicações dessa diferença:</span><span class="sxs-lookup"><span data-stu-id="a3fe8-104">Be aware of the following implications of this difference:</span></span>  
  
-   <span data-ttu-id="a3fe8-105">Uma transação iniciada em um quadro CLR precisa ser confirmada ou revertida ou o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerará um erro quando o quadro for fechado.</span><span class="sxs-lookup"><span data-stu-id="a3fe8-105">A transaction started inside a CLR frame must be committed or rolled back, or else [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates an error when the frame is exited.</span></span>  
  
-   <span data-ttu-id="a3fe8-106">Uma transação externa não pode ser confirmada ou revertida no código CLR.</span><span class="sxs-lookup"><span data-stu-id="a3fe8-106">An outer transaction cannot be committed or rolled back inside the CLR code.</span></span>  
  
-   <span data-ttu-id="a3fe8-107">Uma tentativa de confirmar uma transação não iniciada no mesmo procedimento causa um erro em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a3fe8-107">An attempt to commit a transaction not started in the same procedure causes a run-time error.</span></span>  
  
-   <span data-ttu-id="a3fe8-108">Uma tentativa de reverter uma transação não iniciada no mesmo procedimento faz com que a transação pare de responder (impedindo que qualquer outra operação de efeito colateral ocorra).</span><span class="sxs-lookup"><span data-stu-id="a3fe8-108">An attempt to roll back a transaction not started in the same procedure causes the transaction to stop responding (preventing any other side-effecting operation from happening).</span></span> <span data-ttu-id="a3fe8-109">A transação é descontinuada até que o código CLR saia do escopo.</span><span class="sxs-lookup"><span data-stu-id="a3fe8-109">The transaction discontinues until the CLR code goes out of scope.</span></span> <span data-ttu-id="a3fe8-110">Observe que isso pode ser útil quando você detecta um erro em seu procedimento e deseja verificar se a transação inteira é finalizada.</span><span class="sxs-lookup"><span data-stu-id="a3fe8-110">Note that this can be useful when you detect an error inside your procedure and want to make sure the whole transaction terminates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fe8-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a3fe8-111">See Also</span></span>  
 [<span data-ttu-id="a3fe8-112">Integração CLR e transações</span><span class="sxs-lookup"><span data-stu-id="a3fe8-112">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
