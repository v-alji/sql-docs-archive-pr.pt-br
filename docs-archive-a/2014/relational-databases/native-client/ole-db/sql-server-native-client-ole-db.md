---
title: SQL Server Native Client (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, about SQL Server Native Client OLE DB provider
- OLE DB, SQL Server Native Client OLE DB provider
- data access [SQL Server Native Client], OLE DB
- SQLNCLI, OLE DB
- OLE DB
- SQL Server Native Client OLE DB provider
- SQL Server Native Client, OLE DB
ms.assetid: da846da4-ec19-4a4f-81fb-7d5a2b2bf80a
author: rothja
ms.author: jroth
ms.openlocfilehash: 46b948eb1d075edc6000849dcb2d18ea372809d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572516"
---
# <a name="sql-server-native-client-ole-db"></a><span data-ttu-id="f94a3-102">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f94a3-102">SQL Server Native Client (OLE DB)</span></span>
  <span data-ttu-id="f94a3-103">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client é uma API COM de baixo nível usada para acessar dados.</span><span class="sxs-lookup"><span data-stu-id="f94a3-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a low-level COM API that is used for accessing data.</span></span> <span data-ttu-id="f94a3-104">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client é recomendado para desenvolver ferramentas, utilitários ou componentes de baixo nível que precisem de alto desempenho.</span><span class="sxs-lookup"><span data-stu-id="f94a3-104">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is recommended for developing tools, utilities, or low-level components that need high performance.</span></span> <span data-ttu-id="f94a3-105">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client é um provedor nativo de alto desempenho que acessa o protocolo TDS do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diretamente.</span><span class="sxs-lookup"><span data-stu-id="f94a3-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a native, high performance provider that accesses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Tabular Data Stream (TDS) protocol directly.</span></span>  
  
 <span data-ttu-id="f94a3-106">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client fornece suporte de OLE DB a aplicativos que se conectam ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f94a3-106">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client provides OLE DB support to applications connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f94a3-107">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo é um provedor compatível com OLE DB versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="f94a3-107">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is an OLE DB version 2.0-compliant provider.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f94a3-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f94a3-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f94a3-109">Criando um aplicativo provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f94a3-109">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](../../native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
-   [<span data-ttu-id="f94a3-110">Objetos de fonte de dados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-110">Data Source Objects &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-111">Comandos</span><span class="sxs-lookup"><span data-stu-id="f94a3-111">Commands</span></span>](../../native-client-ole-db-commands/commands.md)  
  
-   [<span data-ttu-id="f94a3-112">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="f94a3-112">Rowsets</span></span>](../../native-client-ole-db-rowsets/rowsets.md)  
  
-   [<span data-ttu-id="f94a3-113">Procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="f94a3-113">Stored Procedures</span></span>](stored-procedures.md)  
  
-   [<span data-ttu-id="f94a3-114">BLOBs e objetos OLE</span><span class="sxs-lookup"><span data-stu-id="f94a3-114">BLOBs and OLE Objects</span></span>](../../native-client-ole-db-blobs/blobs-and-ole-objects.md)  
  
-   [<span data-ttu-id="f94a3-115">Tabelas e índices</span><span class="sxs-lookup"><span data-stu-id="f94a3-115">Tables and Indexes</span></span>](../../native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
-   [<span data-ttu-id="f94a3-116">Tipos de dados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-116">Data Types &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-types/data-types-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-117">Suporte ao conjunto de linhas de esquema &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-117">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-118">Parâmetros com valor de tabela &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-118">Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-119">Melhorias de data e hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-119">Date and Time Improvements &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-120">Tipos CLR grandes definidos pelo usuário &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-120">Large CLR User-Defined Types &#40;OLE DB&#41;</span></span>](large-clr-user-defined-types-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-121">Suporte a FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-121">FILESTREAM Support &#40;OLE DB&#41;</span></span>](filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-122">Transações</span><span class="sxs-lookup"><span data-stu-id="f94a3-122">Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
  
-   [<span data-ttu-id="f94a3-123">Erros</span><span class="sxs-lookup"><span data-stu-id="f94a3-123">Errors</span></span>](../../native-client-ole-db-errors/errors.md)  
  
-   [<span data-ttu-id="f94a3-124">SPNs &#40;Nomes da Entidade de Serviço&#41; em conexões de cliente &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-124">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;OLE DB&#41;</span></span>](service-principal-names-spns-in-client-connections-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-125">Suporte a colunas esparsas &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-125">Sparse Columns Support &#40;OLE DB&#41;</span></span>](sparse-columns-support-ole-db.md)  
  
-   [<span data-ttu-id="f94a3-126">SQL Server Native Client &#40;OLE DB referência de&#41;</span><span class="sxs-lookup"><span data-stu-id="f94a3-126">SQL Server Native Client &#40;OLE DB&#41; Reference</span></span>](../../native-client-ole-db-interfaces/sql-server-native-client-ole-db-interfaces.md)  
  
-   [<span data-ttu-id="f94a3-127">Tópicos de instruções do OLE DB</span><span class="sxs-lookup"><span data-stu-id="f94a3-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="f94a3-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f94a3-128">See Also</span></span>  
 [<span data-ttu-id="f94a3-129">Programação do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f94a3-129">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
