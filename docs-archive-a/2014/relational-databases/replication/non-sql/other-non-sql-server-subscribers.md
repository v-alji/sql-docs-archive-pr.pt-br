---
title: Outros Assinantes não SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, other types
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3849ca717e82bcf1bed5769190c9f898209a454a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568450"
---
# <a name="other-non-sql-server-subscribers"></a><span data-ttu-id="945f3-102">Outros assinantes não SQL Server</span><span class="sxs-lookup"><span data-stu-id="945f3-102">Other Non-SQL Server Subscribers</span></span>
  <span data-ttu-id="945f3-103">Para uma lista de Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , suportados por [!INCLUDE[msCoName](../../../includes/msconame-md.md)], consulte [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="945f3-103">For a list of non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers supported by [!INCLUDE[msCoName](../../../includes/msconame-md.md)], see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span> <span data-ttu-id="945f3-104">Esse tópico inclui informações sobre exigências para drivers ODBC e provedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="945f3-104">This topic includes information about requirements for ODBC drivers and OLE DB providers.</span></span>  
  
## <a name="odbc-driver-requirements"></a><span data-ttu-id="945f3-105">Exigências do driver ODBC</span><span class="sxs-lookup"><span data-stu-id="945f3-105">ODBC Driver Requirements</span></span>  
 <span data-ttu-id="945f3-106">O driver ODBC:</span><span class="sxs-lookup"><span data-stu-id="945f3-106">The ODBC driver:</span></span>  
  
-   <span data-ttu-id="945f3-107">Deve estar em conformidade com nível 1 do ODBC.</span><span class="sxs-lookup"><span data-stu-id="945f3-107">Must be ODBC level-1 compliant.</span></span>  
  
-   <span data-ttu-id="945f3-108">Deve ser isento de threads e para a arquitetura do processador (Intel ou Alpha) e plataforma (32 bit ou 64 bit) na qual o Distribuidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é executado.</span><span class="sxs-lookup"><span data-stu-id="945f3-108">Must be thread-safe, and for the processor architecture (Intel or Alpha) and platform (32 bit or 64 bit) on which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor runs.</span></span>  
  
-   <span data-ttu-id="945f3-109">Deve ser capaz em termos de transação.</span><span class="sxs-lookup"><span data-stu-id="945f3-109">Must be transaction capable.</span></span>  
  
-   <span data-ttu-id="945f3-110">Deve oferecer suporte para linguagem de definição de dados (DLL).</span><span class="sxs-lookup"><span data-stu-id="945f3-110">Must support the Data Definition Language (DDL).</span></span>  
  
-   <span data-ttu-id="945f3-111">Não pode ser somente leitura.</span><span class="sxs-lookup"><span data-stu-id="945f3-111">Cannot be read-only.</span></span>  
  
-   <span data-ttu-id="945f3-112">Deve oferecer suporte para nomes de tabela longos como **MSreplication_subscriptions**.</span><span class="sxs-lookup"><span data-stu-id="945f3-112">Must support long table names such as **MSreplication_subscriptions**.</span></span>  
  
## <a name="replicating-using-ole-db-interfaces"></a><span data-ttu-id="945f3-113">Replicação com o uso de interfaces OLE DB</span><span class="sxs-lookup"><span data-stu-id="945f3-113">Replicating Using OLE DB Interfaces</span></span>  
 <span data-ttu-id="945f3-114">Provedores OLE DB devem oferecer suporte a esses objetos para replicação transacional:</span><span class="sxs-lookup"><span data-stu-id="945f3-114">OLE DB providers must support these objects for transactional replication:</span></span>  
  
-   <span data-ttu-id="945f3-115">Objeto**DataSource**</span><span class="sxs-lookup"><span data-stu-id="945f3-115">**DataSource** object</span></span>  
  
-   <span data-ttu-id="945f3-116">Objeto**Sessão**</span><span class="sxs-lookup"><span data-stu-id="945f3-116">**Session** object</span></span>  
  
-   <span data-ttu-id="945f3-117">Objeto**Comando**</span><span class="sxs-lookup"><span data-stu-id="945f3-117">**Command** object</span></span>  
  
-   <span data-ttu-id="945f3-118">Objeto**Conjunto de linhas**</span><span class="sxs-lookup"><span data-stu-id="945f3-118">**Rowset** object</span></span>  
  
-   <span data-ttu-id="945f3-119">Objeto**Erro**</span><span class="sxs-lookup"><span data-stu-id="945f3-119">**Error** object</span></span>  
  
### <a name="datasource-object-interfaces"></a><span data-ttu-id="945f3-120">Interfaces de objeto DataSource</span><span class="sxs-lookup"><span data-stu-id="945f3-120">DataSource Object Interfaces</span></span>  
 <span data-ttu-id="945f3-121">As interfaces a seguir são exigidas para a conexão com uma fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="945f3-121">The following interfaces are required to connect to a data source:</span></span>  
  
-   `IDBInitialize`  
  
-   `IDBCreateSession`  
  
-   `IDBProperties`  
  
 <span data-ttu-id="945f3-122">Se o provedor der suporte à interface **IDBInfo**, o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usará a interface para recuperar informações, como o caractere identificador entre aspas, tamanho máximo da instrução SQL e número máximo de caracteres em nomes de tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="945f3-122">If the provider supports the **IDBInfo** interface, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses the interface to retrieve information such as the quoted identifier character, maximum SQL statement length, and maximum number of characters in table and column names.</span></span>  
  
### <a name="session-object-interfaces"></a><span data-ttu-id="945f3-123">Interfaces de objeto de sessão</span><span class="sxs-lookup"><span data-stu-id="945f3-123">Session Object Interfaces</span></span>  
 <span data-ttu-id="945f3-124">As seguintes interfaces são exigidas:</span><span class="sxs-lookup"><span data-stu-id="945f3-124">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="945f3-125">**IDBCreateCommand**</span><span class="sxs-lookup"><span data-stu-id="945f3-125">**IDBCreateCommand**</span></span>  
  
-   <span data-ttu-id="945f3-126">**ITransaction**</span><span class="sxs-lookup"><span data-stu-id="945f3-126">**ITransaction**</span></span>  
  
-   <span data-ttu-id="945f3-127">**ITransactionLocal**</span><span class="sxs-lookup"><span data-stu-id="945f3-127">**ITransactionLocal**</span></span>  
  
-   <span data-ttu-id="945f3-128">**IDBSchemaRowset**</span><span class="sxs-lookup"><span data-stu-id="945f3-128">**IDBSchemaRowset**</span></span>  
  
### <a name="command-object-interfaces"></a><span data-ttu-id="945f3-129">Interfaces de objeto de comando</span><span class="sxs-lookup"><span data-stu-id="945f3-129">Command Object Interfaces</span></span>  
 <span data-ttu-id="945f3-130">As seguintes interfaces são exigidas:</span><span class="sxs-lookup"><span data-stu-id="945f3-130">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="945f3-131">**ICommand**</span><span class="sxs-lookup"><span data-stu-id="945f3-131">**ICommand**</span></span>  
  
-   <span data-ttu-id="945f3-132">**ICommandProperties**</span><span class="sxs-lookup"><span data-stu-id="945f3-132">**ICommandProperties**</span></span>  
  
-   <span data-ttu-id="945f3-133">**ICommandText**</span><span class="sxs-lookup"><span data-stu-id="945f3-133">**ICommandText**</span></span>  
  
-   <span data-ttu-id="945f3-134">**ICommandPrepare**</span><span class="sxs-lookup"><span data-stu-id="945f3-134">**ICommandPrepare**</span></span>  
  
-   <span data-ttu-id="945f3-135">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="945f3-135">**IColumnsInfo**</span></span>  
  
-   <span data-ttu-id="945f3-136">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="945f3-136">**IAccessor**</span></span>  
  
-   <span data-ttu-id="945f3-137">**ICommandWithParameters**</span><span class="sxs-lookup"><span data-stu-id="945f3-137">**ICommandWithParameters**</span></span>  
  
 <span data-ttu-id="945f3-138">**IAccessor** é necessário criar acessadores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="945f3-138">**IAccessor** is necessary to create parameter accessors.</span></span> <span data-ttu-id="945f3-139">Se o provedor oferecer suporte a **IColumnRowset**, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usará essa interface para determinar se uma coluna é uma coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="945f3-139">If the provider supports **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses that interface to determine whether a column is an identity column.</span></span>  
  
### <a name="rowset-object-interfaces"></a><span data-ttu-id="945f3-140">Interfaces de objeto de conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="945f3-140">Rowset Object Interfaces</span></span>  
 <span data-ttu-id="945f3-141">As seguintes interfaces são exigidas:</span><span class="sxs-lookup"><span data-stu-id="945f3-141">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="945f3-142">**IRowset**</span><span class="sxs-lookup"><span data-stu-id="945f3-142">**IRowset**</span></span>  
  
-   <span data-ttu-id="945f3-143">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="945f3-143">**IAccessor**</span></span>  
  
-   <span data-ttu-id="945f3-144">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="945f3-144">**IColumnsInfo**</span></span>  
  
 <span data-ttu-id="945f3-145">Um aplicativo deve abrir um conjunto de linhas em uma tabela replicada que é criada no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="945f3-145">An application should open a rowset on a replicated table that is created in the subscription database.</span></span> <span data-ttu-id="945f3-146">**IColumnsInfo** e **IAccessor** são necessários para acessar dados no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="945f3-146">**IColumnsInfo** and **IAccessor** are needed to access data in the rowset.</span></span>  
  
### <a name="error-object-interfaces"></a><span data-ttu-id="945f3-147">Interfaces de objeto de erro</span><span class="sxs-lookup"><span data-stu-id="945f3-147">Error Object Interfaces</span></span>  
 <span data-ttu-id="945f3-148">Use as seguintes interfaces para gerenciar erros:</span><span class="sxs-lookup"><span data-stu-id="945f3-148">Use the following interfaces to manage errors:</span></span>  
  
-   <span data-ttu-id="945f3-149">**IErrorRecords**</span><span class="sxs-lookup"><span data-stu-id="945f3-149">**IErrorRecords**</span></span>  
  
-   <span data-ttu-id="945f3-150">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="945f3-150">**IErrorInfo**</span></span>  
  
 <span data-ttu-id="945f3-151">Use **ISQLErrorInfo** se for suportado pelo provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="945f3-151">Use **ISQLErrorInfo** if it is supported by the OLE DB provider.</span></span>  
  
 <span data-ttu-id="945f3-152">Para obter mais informações sobre o provedor OLE DB, consulte a documentação fornecida com seu provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="945f3-152">For more information about the OLE DB provider, see the documentation supplied with your OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945f3-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="945f3-153">See Also</span></span>  
 [<span data-ttu-id="945f3-154">Non-SQL Server Subscribers</span><span class="sxs-lookup"><span data-stu-id="945f3-154">Non-SQL Server Subscribers</span></span>](non-sql-server-subscribers.md)  
  
  
