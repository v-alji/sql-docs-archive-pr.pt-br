---
title: Conjuntos de linhas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], about rowsets
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets
- OLE DB rowsets, about rowsets
- rowsets [OLE DB]
ms.assetid: 5e7b3cbe-3670-4e18-8172-2226e0b6b142
author: rothja
ms.author: jroth
ms.openlocfilehash: 1245d17dc0f3757b3c212146c8c162de6e48a483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571380"
---
# <a name="rowsets"></a><span data-ttu-id="52b68-102">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="52b68-102">Rowsets</span></span>
  <span data-ttu-id="52b68-103">Um conjunto de linhas contém colunas de dados.</span><span class="sxs-lookup"><span data-stu-id="52b68-103">A rowset is a set of rows that contain columns of data.</span></span> <span data-ttu-id="52b68-104">Os conjuntos de linhas são objetos centrais que permitem que todos os provedores de dados OLE DB exponham dados de conjuntos de resultados em formato tabular.</span><span class="sxs-lookup"><span data-stu-id="52b68-104">Rowsets are central objects that enable all OLE DB data providers to expose result set data in tabular form.</span></span>  
  
 <span data-ttu-id="52b68-105">Depois que um consumidor cria uma sessão usando o método **IDBCreateSession::CreateSession**, ele pode usar a interface **IOpenRowset** ou **IDBCreateCommand** na sessão para criar um conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="52b68-105">After a consumer creates a session by using the **IDBCreateSession::CreateSession** method, the consumer can use either the **IOpenRowset** or **IDBCreateCommand** interface on the session to create a rowset.</span></span> <span data-ttu-id="52b68-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte a essas duas interfaces.</span><span class="sxs-lookup"><span data-stu-id="52b68-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports both of these interfaces.</span></span> <span data-ttu-id="52b68-107">Esses dois métodos são descritos aqui.</span><span class="sxs-lookup"><span data-stu-id="52b68-107">Both of these methods are described here.</span></span>  
  
-   <span data-ttu-id="52b68-108">Criar um conjunto de linhas chamando o método **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="52b68-108">Create a rowset by calling the **IOpenRowset::OpenRowset** method.</span></span>  
  
     <span data-ttu-id="52b68-109">Isto equivale a criar um conjunto de linhas sobre uma única tabela.</span><span class="sxs-lookup"><span data-stu-id="52b68-109">This is equivalent to creating a rowset over a single table.</span></span> <span data-ttu-id="52b68-110">Este método abre e retorna um conjunto de linhas que inclui todas as linhas de uma única tabela base.</span><span class="sxs-lookup"><span data-stu-id="52b68-110">This method opens and returns a rowset that includes all of the rows from a single base table.</span></span> <span data-ttu-id="52b68-111">Um dos argumentos para **OpenRowset** é uma ID de tabela que identifica a tabela com base na qual criar o conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="52b68-111">One of the arguments to **OpenRowset** is a table ID that identifies the table from which to create the rowset.</span></span>  
  
-   <span data-ttu-id="52b68-112">Criar um objeto de comando chamando o método **IDBCreateCommand::CreateCommand**.</span><span class="sxs-lookup"><span data-stu-id="52b68-112">Create a command object by calling the **IDBCreateCommand::CreateCommand** method.</span></span>  
  
     <span data-ttu-id="52b68-113">O objeto de comando executa comandos aos quais o provedor dá suporte.</span><span class="sxs-lookup"><span data-stu-id="52b68-113">The command object executes commands that the provider supports.</span></span> <span data-ttu-id="52b68-114">Com o provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, o consumidor pode especificar qualquer instrução [!INCLUDE[tsql](../../includes/tsql-md.md)], como a instrução SELECT, ou uma chamada para um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="52b68-114">With the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer can specify any [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as a SELECT statement or a call to a stored procedure.</span></span> <span data-ttu-id="52b68-115">As etapas para a criação de um conjunto de linhas usando um objeto de comando são:</span><span class="sxs-lookup"><span data-stu-id="52b68-115">The steps for creating a rowset by using a command object are:</span></span>  
  
    1.  <span data-ttu-id="52b68-116">O consumidor chama o método **IDBCreateCommand::CreateCommand** na sessão para obter um objeto de comando que solicita a interface **ICommandText** no objeto de comando.</span><span class="sxs-lookup"><span data-stu-id="52b68-116">The consumer calls the **IDBCreateCommand::CreateCommand** method on the session to get a command object requesting the **ICommandText** interface on the command object.</span></span> <span data-ttu-id="52b68-117">Essa interface **ICommandText** define e recupera o texto de comando real.</span><span class="sxs-lookup"><span data-stu-id="52b68-117">This **ICommandText** interface sets and retrieves the actual command text.</span></span> <span data-ttu-id="52b68-118">O consumidor preenche o comando de texto chamando o método **ICommandText::SetCommandText**.</span><span class="sxs-lookup"><span data-stu-id="52b68-118">The consumer fills in the text command by calling the **ICommandText::SetCommandText** method.</span></span>  
  
    2.  <span data-ttu-id="52b68-119">O usuário chama o método **ICommand::Execute** no comando.</span><span class="sxs-lookup"><span data-stu-id="52b68-119">The user calls the **ICommand::Execute** method on the command.</span></span> <span data-ttu-id="52b68-120">O objeto do conjunto de linhas criado quando o comando é executado contém o conjunto de resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="52b68-120">The rowset object built when the command executes contains the result set from the command.</span></span>  
  
 <span data-ttu-id="52b68-121">O consumidor pode usar a interface **ICommandProperties** para obter ou definir as propriedades do conjunto de linhas retornado pelo comando executado pelas interfaces **ICommand::Execute**.</span><span class="sxs-lookup"><span data-stu-id="52b68-121">The consumer can use the **ICommandProperties** interface to get or set the properties for the rowset returned by the command executed by the **ICommand::Execute** interfaces.</span></span> <span data-ttu-id="52b68-122">As propriedades solicitadas com mais frequência são as interfaces às quais o conjunto de linhas deve dar suporte.</span><span class="sxs-lookup"><span data-stu-id="52b68-122">The most commonly requested properties are the interfaces the rowset must support.</span></span> <span data-ttu-id="52b68-123">Além das interfaces, o consumidor pode solicitar propriedades que modificam o comportamento do conjunto de linhas ou da interface.</span><span class="sxs-lookup"><span data-stu-id="52b68-123">In addition to interfaces, the consumer can request properties that modify the behavior of the rowset or interface.</span></span>  
  
 <span data-ttu-id="52b68-124">Os consumidores liberam conjuntos de linhas com o método **IRowset::Release**.</span><span class="sxs-lookup"><span data-stu-id="52b68-124">Consumers release rowsets with the **IRowset::Release** method.</span></span> <span data-ttu-id="52b68-125">A liberação de um conjunto de linhas libera todos os indicadores de linha mantidos pelo consumidor nesse conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="52b68-125">Releasing a rowset releases any row handles held by the consumer on that rowset.</span></span> <span data-ttu-id="52b68-126">A liberação de um conjunto de linhas não libera os acessadores.</span><span class="sxs-lookup"><span data-stu-id="52b68-126">Releasing a rowset does not release the accessors.</span></span> <span data-ttu-id="52b68-127">Se você tiver uma interface **IAccessor**, ela ainda deverá ser liberada.</span><span class="sxs-lookup"><span data-stu-id="52b68-127">If you have an **IAccessor** interface, it still has to be released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52b68-128">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="52b68-128">In This Section</span></span>  
  
-   [<span data-ttu-id="52b68-129">Criando um conjunto de linhas com IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="52b68-129">Creating a Rowset with IOpenRowset</span></span>](creating-a-rowset-with-iopenrowset.md)  
  
-   [<span data-ttu-id="52b68-130">Criando conjuntos de linhas com ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="52b68-130">Creating Rowsets with ICommand::Execute</span></span>](creating-rowsets-with-icommand-execute.md)  
  
-   [<span data-ttu-id="52b68-131">Propriedades e comportamentos do conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="52b68-131">Rowset Properties and Behaviors</span></span>](rowset-properties-and-behaviors.md)  
  
-   [<span data-ttu-id="52b68-132">Conjuntos de linha e cursores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="52b68-132">Rowsets and SQL Server Cursors</span></span>](rowsets-and-sql-server-cursors.md)  
  
-   [<span data-ttu-id="52b68-133">Buscando linhas</span><span class="sxs-lookup"><span data-stu-id="52b68-133">Fetching Rows</span></span>](fetching-rows.md)  
  
-   [<span data-ttu-id="52b68-134">Buscando uma única linha com IRow</span><span class="sxs-lookup"><span data-stu-id="52b68-134">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
-   [<span data-ttu-id="52b68-135">Indicadores</span><span class="sxs-lookup"><span data-stu-id="52b68-135">Bookmarks</span></span>](bookmarks.md)  
  
-   [<span data-ttu-id="52b68-136">Atualizando dados em conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="52b68-136">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
## <a name="see-also"></a><span data-ttu-id="52b68-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="52b68-137">See Also</span></span>  
 [<span data-ttu-id="52b68-138">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="52b68-138">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
