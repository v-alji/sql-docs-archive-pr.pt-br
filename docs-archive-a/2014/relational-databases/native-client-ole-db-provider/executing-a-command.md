---
title: Executar um comando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581778"
---
# <a name="executing-a-command"></a><span data-ttu-id="54b65-102">Executando um comando</span><span class="sxs-lookup"><span data-stu-id="54b65-102">Executing a Command</span></span>
  <span data-ttu-id="54b65-103">Depois de estabelecida a conexão com uma fonte de dados, o consumidor chama o método **IDBCreateSession::CreateSession** para criar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="54b65-103">After the connection to a data source is established, the consumer calls the **IDBCreateSession::CreateSession** method to create a session.</span></span> <span data-ttu-id="54b65-104">A sessão atua como um comando, conjunto de linhas ou fábrica de transação.</span><span class="sxs-lookup"><span data-stu-id="54b65-104">The session acts as a command, rowset, or transaction factory.</span></span>  
  
 <span data-ttu-id="54b65-105">Para trabalhar diretamente com tabelas ou índices individuais, o consumidor solicita a interface `IOpenRowset`.</span><span class="sxs-lookup"><span data-stu-id="54b65-105">To work directly with individual tables or indexes, the consumer requests the `IOpenRowset` interface.</span></span> <span data-ttu-id="54b65-106">O método `IOpenRowset::OpenRowset` se abre e retorna um conjunto de linhas que inclui todas as linhas de uma única tabela ou índice base.</span><span class="sxs-lookup"><span data-stu-id="54b65-106">The `IOpenRowset::OpenRowset` method opens and returns a rowset that includes all rows from a single base table or index.</span></span>  
  
 <span data-ttu-id="54b65-107">Para executar um comando (como selecionar \* de autores), o consumidor solicita a `IDBCreateCommand` interface.</span><span class="sxs-lookup"><span data-stu-id="54b65-107">To execute a command (such as SELECT \* FROM Authors), the consumer requests the `IDBCreateCommand` interface.</span></span> <span data-ttu-id="54b65-108">O consumidor pode executar o método `IDBCreateCommand::CreateCommand` para criar um objeto de comando e solicitar a interface `ICommandText`.</span><span class="sxs-lookup"><span data-stu-id="54b65-108">The consumer can execute the `IDBCreateCommand::CreateCommand` method to create a command object and request for the `ICommandText` interface.</span></span> <span data-ttu-id="54b65-109">O método `ICommandText::SetCommandText` é usado para especificar o comando que será executado.</span><span class="sxs-lookup"><span data-stu-id="54b65-109">The `ICommandText::SetCommandText` method is used to specify the command that is to be executed.</span></span>  
  
 <span data-ttu-id="54b65-110">O comando `Execute` é usado para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="54b65-110">The `Execute` command is used to execute the command.</span></span> <span data-ttu-id="54b65-111">O comando pode ser qualquer instrução SQL ou nome de procedimento.</span><span class="sxs-lookup"><span data-stu-id="54b65-111">The command can be any SQL statement or procedure name.</span></span> <span data-ttu-id="54b65-112">Nem todos os comandos geram um objeto de conjunto de resultados (conjunto de linhas).</span><span class="sxs-lookup"><span data-stu-id="54b65-112">Not all commands produce a result set (rowset) object.</span></span> <span data-ttu-id="54b65-113">Comandos como SELECT \* FROM Authors geram um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="54b65-113">Commands such as SELECT \* FROM Authors produce a result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b65-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54b65-114">See Also</span></span>  
 [<span data-ttu-id="54b65-115">Criando um aplicativo provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="54b65-115">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
