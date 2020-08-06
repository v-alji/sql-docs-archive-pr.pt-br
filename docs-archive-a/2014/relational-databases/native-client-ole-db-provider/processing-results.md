---
title: Processar resultados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [SQL Server Native Client]
ms.assetid: 20887ac4-f649-4e7f-92e6-f929e2e70952
author: rothja
ms.author: jroth
ms.openlocfilehash: b9e5bf00b4d2e554536c9f2ba1a328390b93a8a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581777"
---
# <a name="processing-results"></a><span data-ttu-id="a62be-102">Processando resultados</span><span class="sxs-lookup"><span data-stu-id="a62be-102">Processing Results</span></span>
  <span data-ttu-id="a62be-103">Caso um objeto de conjunto de linhas seja produzido pela execução de um comando ou pela geração direta de um objeto de conjunto de linhas no provedor, o consumidor precisa recuperar e acessar dados no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="a62be-103">If a rowset object is produced by either the execution of a command or the generation of a rowset object directly from the provider, the consumer needs to retrieve and access data in the rowset.</span></span>  
  
 <span data-ttu-id="a62be-104">Conjuntos de linhas são os objetos centrais que permitem ao provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client expor dados em forma tabular.</span><span class="sxs-lookup"><span data-stu-id="a62be-104">Rowsets are the central objects that enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to expose data in tabular form.</span></span> <span data-ttu-id="a62be-105">Conceitualmente, um conjunto de linhas é um conjunto de linhas em que cada linha tem dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="a62be-105">Conceptually, a rowset is a set of rows in which each row has column data.</span></span> <span data-ttu-id="a62be-106">Um objeto de conjunto de linhas expõe interfaces como **IRowset** (contém métodos para buscar linhas no conjunto sequencialmente), **IAccessor** (permite a definição de um grupo de associações de coluna que descrevem a forma como dados tabulares são associados a variáveis de programa do consumidor), **IColumnsInfo** (fornece informações sobre colunas no conjunto de linhas) e **IRowsetInfo** (fornece informações sobre o conjunto de linhas).</span><span class="sxs-lookup"><span data-stu-id="a62be-106">A rowset object exposes interfaces such as **IRowset** (contains methods for fetching rows from the rowset sequentially), **IAccessor** (permits the definition of a group of column bindings describing the way tabular data is bound to consumer program variables), **IColumnsInfo** (provides information about columns in the rowset), and **IRowsetInfo** (provides information about rowset).</span></span>  
  
 <span data-ttu-id="a62be-107">Um consumidor pode chamar o método **IRowset::GetData** para recuperar uma linha de dados do conjunto de linhas em um buffer.</span><span class="sxs-lookup"><span data-stu-id="a62be-107">A consumer can call the **IRowset::GetData** method to retrieve a row of data from the rowset into a buffer.</span></span> <span data-ttu-id="a62be-108">Antes de **GetData** ser chamado, o consumidor descreve o buffer usando um conjunto de estruturas DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="a62be-108">Before **GetData** is called, the consumer describes the buffer using a set of DBBINDING structures.</span></span> <span data-ttu-id="a62be-109">Cada associação descreve como uma coluna em um conjunto de linhas é armazenada em um buffer de consumidor e contém o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a62be-109">Each binding describes how a column in a rowset is stored in a consumer buffer and contains the following:</span></span>  
  
-   <span data-ttu-id="a62be-110">Ordinal da coluna (ou parâmetro) a que a associação se aplica.</span><span class="sxs-lookup"><span data-stu-id="a62be-110">Ordinal of the column (or parameter) to which the binding applies.</span></span>  
  
-   <span data-ttu-id="a62be-111">Informações sobre a associação (por exemplo, valor de dados, comprimento dos dados e o status da associação).</span><span class="sxs-lookup"><span data-stu-id="a62be-111">Information about what is bound (for example, data value, length of the data, and its binding status).</span></span>  
  
-   <span data-ttu-id="a62be-112">Informações sobre o que é deslocado no buffer para cada uma das partes.</span><span class="sxs-lookup"><span data-stu-id="a62be-112">Information about what is offset in the buffer to each of these parts.</span></span>  
  
-   <span data-ttu-id="a62be-113">Comprimento e tipo dos valores de dados como se apresentam no buffer de consumidor.</span><span class="sxs-lookup"><span data-stu-id="a62be-113">Length and type of the data values as they exist in the consumer buffer.</span></span>  
  
 <span data-ttu-id="a62be-114">Ao obter os dados, o provedor usa informações de cada associação para determinar onde e como recuperar dados do buffer de consumidor.</span><span class="sxs-lookup"><span data-stu-id="a62be-114">When getting the data, the provider uses information in each binding to determine where and how to retrieve data from the consumer buffer.</span></span> <span data-ttu-id="a62be-115">Ao definir dados no buffer de consumidor, o provedor usa informações de cada associação para determinar onde e como retornar dados no buffer.</span><span class="sxs-lookup"><span data-stu-id="a62be-115">When setting data in the consumer buffer, the provider uses information in each binding to determine where and how to return data in the consumer's buffer.</span></span>  
  
 <span data-ttu-id="a62be-116">Depois que as estruturas DBBINDING são especificadas, um acessador é criado (**IAccessor::CreateAccessor**).</span><span class="sxs-lookup"><span data-stu-id="a62be-116">After the DBBINDING structures are specified, an accessor is created (**IAccessor::CreateAccessor**).</span></span> <span data-ttu-id="a62be-117">Um acessador é uma coleção de associações, sendo usado para obter ou definir os dados no buffer de consumidor.</span><span class="sxs-lookup"><span data-stu-id="a62be-117">An accessor is a collection of bindings and is used to get or set the data in the consumer buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62be-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a62be-118">See Also</span></span>  
 <span data-ttu-id="a62be-119">[Criando um aplicativo de provedor de OLE DB de SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="a62be-119">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="a62be-120">Tópicos de instruções do OLE DB</span><span class="sxs-lookup"><span data-stu-id="a62be-120">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
