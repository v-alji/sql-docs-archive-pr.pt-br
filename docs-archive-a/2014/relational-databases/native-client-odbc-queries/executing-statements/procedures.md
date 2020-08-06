---
title: Procedimentos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- stored procedures [ODBC], about ODBC stored procedures
- ODBC applications, statements
- statements [ODBC], stored procedures
- ODBC applications, stored procedures
ms.assetid: c64d5f3a-376b-48ef-84f3-b6148ac8600a
author: rothja
ms.author: jroth
ms.openlocfilehash: a7ae4678d324ba7d07ae429793b1f75b57bb15e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569407"
---
# <a name="procedures"></a><span data-ttu-id="e5ade-102">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="e5ade-102">Procedures</span></span>
  <span data-ttu-id="e5ade-103">Um procedimento armazenado é um objeto executável pré-compilado que contém uma ou mais instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5ade-103">A stored procedure is a precompiled executable object that contains one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="e5ade-104">Os procedimentos armazenados podem ter parâmetros de entrada e saída, além de gerar saída de um código de retorno de inteiro.</span><span class="sxs-lookup"><span data-stu-id="e5ade-104">Stored procedures can have input and output parameters and can also put out an integer return code.</span></span> <span data-ttu-id="e5ade-105">Um aplicativo pode enumerar os procedimentos armazenados disponíveis usando funções de catálogo.</span><span class="sxs-lookup"><span data-stu-id="e5ade-105">An application can enumerate available stored procedures by using catalog functions.</span></span>  
  
 <span data-ttu-id="e5ade-106">Os aplicativos ODBC cujo destino é o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] só devem usar a execução direta para chamar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e5ade-106">ODBC applications that target [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should only use direct execution to call a stored procedure.</span></span> <span data-ttu-id="e5ade-107">Quando conectado a versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client implementa a [função SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) criando um procedimento armazenado temporário, que é então chamado em **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="e5ade-107">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver implements [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) by creating a temporary stored procedure, which is then called on **SQLExecute**.</span></span> <span data-ttu-id="e5ade-108">Ele adiciona sobrecarga para que o **SQLPrepare** crie um procedimento armazenado temporário que só chame o procedimento armazenado de destino em comparação com a execução direta do procedimento armazenado de destino.</span><span class="sxs-lookup"><span data-stu-id="e5ade-108">It adds overhead to have **SQLPrepare** create a temporary stored procedure that only calls the target stored procedure versus directly executing the target stored procedure.</span></span> <span data-ttu-id="e5ade-109">Mesmo quando conectado a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a preparação de uma chamada exige uma viagem de ida e volta adicional na rede e a elaboração de um plano de execução que apenas chama o plano de execução de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e5ade-109">Even when connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], preparing a call requires an extra round trip across the network and the building of an execution plan that just calls the stored procedure execution plan.</span></span>  
  
 <span data-ttu-id="e5ade-110">Os aplicativos ODBC devem usar a sintaxe de ODBC CALL ao executar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e5ade-110">ODBC applications should use the ODBC CALL syntax when executing a stored procedure.</span></span> <span data-ttu-id="e5ade-111">O driver é otimizado para usar um mecanismo de chamada de procedimento remoto para chamar o procedimento quando a sintaxe de ODBC CALL é usada.</span><span class="sxs-lookup"><span data-stu-id="e5ade-111">The driver is optimized to use a remote procedure call mechanism to call the procedure when the ODBC CALL syntax is used.</span></span> <span data-ttu-id="e5ade-112">Isso é mais eficiente do que o mecanismo usado para enviar uma instrução EXECUTE [!INCLUDE[tsql](../../../includes/tsql-md.md)] para o servidor.</span><span class="sxs-lookup"><span data-stu-id="e5ade-112">This is more efficient than the mechanism used to send a [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE statement to the server.</span></span>  
  
 <span data-ttu-id="e5ade-113">Para obter mais informações, consulte [executando procedimentos armazenados](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e5ade-113">For more information, see [Running Stored Procedures](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ade-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5ade-114">See Also</span></span>  
 [<span data-ttu-id="e5ade-115">Executando instruções &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="e5ade-115">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
