---
title: Transações em ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: c5a87fa5-827a-4e6f-a0d9-924bac881eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 386b248edfdb6e0ac5eb97b3aeb6c0bbc505a5a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571356"
---
# <a name="transactions-in-odbc"></a><span data-ttu-id="d12bc-102">Transações em ODBC</span><span class="sxs-lookup"><span data-stu-id="d12bc-102">Transactions in ODBC</span></span>
  <span data-ttu-id="d12bc-103">As transações em ODBC são gerenciadas no nível da conexão.</span><span class="sxs-lookup"><span data-stu-id="d12bc-103">Transactions in ODBC are managed at the connection level.</span></span> <span data-ttu-id="d12bc-104">Quando um aplicativo conclui uma transação, ele confirma ou reverte todo o trabalho concluído através de todos os identificadores de instrução nessa conexão.</span><span class="sxs-lookup"><span data-stu-id="d12bc-104">When an application completes a transaction, it commits or rolls back all work completed through all statement handles on that connection.</span></span> <span data-ttu-id="d12bc-105">Para confirmar ou reverter uma transação, os aplicativos devem chamar [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) , em vez de enviar uma instrução COMMIT ou ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="d12bc-105">To commit or roll back a transaction, applications should call [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) instead of submitting a COMMIT or ROLLBACK statement.</span></span>  
  
 <span data-ttu-id="d12bc-106">Um aplicativo chama [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) para alternar entre os dois modos ODBC de gerenciamento de transações:</span><span class="sxs-lookup"><span data-stu-id="d12bc-106">An application calls [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) to switch between the two ODBC modes of managing transactions:</span></span>  
  
-   <span data-ttu-id="d12bc-107">Modo de confirmação automática</span><span class="sxs-lookup"><span data-stu-id="d12bc-107">Autocommit mode</span></span>  
  
     <span data-ttu-id="d12bc-108">Cada instrução é confirmada automaticamente quando concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="d12bc-108">Each statement is automatically committed when it is completed successfully.</span></span> <span data-ttu-id="d12bc-109">Quando o modo de confirmação automática é executado, nenhuma outra função de gerenciamento de transação é necessária.</span><span class="sxs-lookup"><span data-stu-id="d12bc-109">When you run in autocommit mode, no other transaction management functions are required.</span></span>  
  
-   <span data-ttu-id="d12bc-110">Modo de confirmação manual</span><span class="sxs-lookup"><span data-stu-id="d12bc-110">Manual-commit mode</span></span>  
  
     <span data-ttu-id="d12bc-111">Todas as instruções executadas são incluídas na mesma transação até que ela seja interrompida especificamente chamando **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="d12bc-111">All executed statements are included in the same transaction until it is specifically stopped by calling **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="d12bc-112">O modo de confirmação automática é o modo de transação padrão para ODBC.</span><span class="sxs-lookup"><span data-stu-id="d12bc-112">Autocommit mode is the default transaction mode for ODBC.</span></span> <span data-ttu-id="d12bc-113">Quando uma conexão é estabelecida, ela está em modo de confirmação automática até **SQLSetConnectAttr** ser chamado para alternar para o modo de confirmação manual desativando o modo de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="d12bc-113">When a connection is made, it is in autocommit mode until **SQLSetConnectAttr** is called to switch to manual-commit mode by setting autocommit mode off.</span></span> <span data-ttu-id="d12bc-114">Quando um aplicativo desativa a confirmação automática, a instrução seguinte enviada para o banco de dados inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="d12bc-114">When an application turns autocommit off, the next statement sent to the database starts a transaction.</span></span> <span data-ttu-id="d12bc-115">A transação permanece ativa até que o aplicativo chame **SQLEndTran** com as opções SQL_COMMIT ou SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="d12bc-115">The transaction then remains in effect until the application calls **SQLEndTran** with either the SQL_COMMIT or SQL_ROLLBACK options.</span></span> <span data-ttu-id="d12bc-116">O comando enviado para o banco de dados após **SQLEndTran** inicia a transação seguinte.</span><span class="sxs-lookup"><span data-stu-id="d12bc-116">The command sent to the database after **SQLEndTran** starts the next transaction.</span></span>  
  
 <span data-ttu-id="d12bc-117">Se um aplicativo alternar do modo de confirmação manual para o modo de confirmação automática, o driver confirmará todas as transações abertas na conexão no momento.</span><span class="sxs-lookup"><span data-stu-id="d12bc-117">If an application switches from manual-commit to autocommit mode, the driver commits any transactions currently open on the connection.</span></span>  
  
 <span data-ttu-id="d12bc-118">Os aplicativos ODBC não devem usar instruções de transação Transact-SQL como BEGIN TRANSACTION, COMMIT TRANSACTION ou ROLLBACK TRANSACTION porque isso pode causar um comportamento indeterminado no driver.</span><span class="sxs-lookup"><span data-stu-id="d12bc-118">ODBC applications should not use Transact-SQL transaction statements such as BEGIN TRANSACTION, COMMIT TRANSACTION, or ROLLBACK TRANSACTION because this can cause indeterminate behavior in the driver.</span></span> <span data-ttu-id="d12bc-119">Um aplicativo ODBC deve ser executado em modo de confirmação automática e não deve usar nenhuma função ou instrução de gerenciamento de transações, ou deve ser executado em modo de confirmação manual e usar a função **SQLEndTran** de ODBC para confirmar ou reverter transações.</span><span class="sxs-lookup"><span data-stu-id="d12bc-119">An ODBC application should run in autocommit mode and not use any transaction management functions or statements, or run in manual-commit mode and use the ODBC **SQLEndTran** function to either commit or roll back transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12bc-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d12bc-120">See Also</span></span>  
 [<span data-ttu-id="d12bc-121">Executando transações &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="d12bc-121">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
