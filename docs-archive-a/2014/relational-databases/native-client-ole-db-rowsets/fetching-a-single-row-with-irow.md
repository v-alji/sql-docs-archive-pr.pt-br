---
title: Buscar uma linha única com IRow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- SQL Server Native Client OLE DB provider, fetching
ms.assetid: 07c803ca-299a-42c5-ba02-360b9631d15f
author: rothja
ms.author: jroth
ms.openlocfilehash: b5573fe1fef39f29329e373323f5f8aaf15f2c58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581776"
---
# <a name="fetching-a-single-row-with-irow"></a><span data-ttu-id="4a4d6-102">Buscando uma única linha com IRow</span><span class="sxs-lookup"><span data-stu-id="4a4d6-102">Fetching a Single Row with IRow</span></span>
  <span data-ttu-id="4a4d6-103">A implementação da interface **IRow** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo é simplificada para aumentar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-103">The **IRow** interface implementation in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is simplified to increase performance.</span></span> <span data-ttu-id="4a4d6-104">**IRow** permite o acesso direto a colunas de um único objeto de linha.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-104">**IRow** allows direct access to columns of a single row object.</span></span> <span data-ttu-id="4a4d6-105">Se você souber com antecedência que o resultado de uma execução de comando produzirá exatamente uma linha, **IRow** recuperará as colunas da linha.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-105">If you know beforehand that the result of a command execution will produce exactly one row, **IRow** will retrieve the columns of that row.</span></span> <span data-ttu-id="4a4d6-106">Se o conjunto de resultados incluir várias linhas, **IRow** exporá apenas a primeira linha.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-106">If the result set includes multiple rows, **IRow** will expose only the first row.</span></span>  
  
 <span data-ttu-id="4a4d6-107">A implementação de **IRow** não permite nenhuma navegação da linha.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-107">The **IRow** implementation does not allow any navigation of the row.</span></span> <span data-ttu-id="4a4d6-108">Todas as colunas na linha são acessadas apenas uma vez com uma exceção: uma coluna pode ser acessada uma vez para localizar o tamanho da coluna e novamente para buscar os dados.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-108">Each column in the row is accessed only one time with one exception: A column can be accessed one time to find the column size and again to fetch the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a4d6-109">**IRow::Open** só dá suporte à abertura do tipo de objetos DBGUID_STREAM e DBGUID_NULL.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-109">**IRow::Open** supports only DBGUID_STREAM and DBGUID_NULL type of objects to be opened.</span></span>  
  
 <span data-ttu-id="4a4d6-110">Para obter um objeto de linha que usa o método **ICommand::Execute**, IID_IRow precisa ser passado.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-110">To obtain a row object using **ICommand::Execute** method, IID_IRow must be passed.</span></span> <span data-ttu-id="4a4d6-111">A interface **IMultipleResults** precisa ser usada para manipular vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-111">The **IMultipleResults** interface must be used to handle multiple result sets.</span></span> <span data-ttu-id="4a4d6-112">**IMultipleResults** dá suporte a **IRow** e **IRowset**.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-112">**IMultipleResults** supports **IRow** and **IRowset**.</span></span> <span data-ttu-id="4a4d6-113">**IRowset** é usado para operações em massa.</span><span class="sxs-lookup"><span data-stu-id="4a4d6-113">**IRowset** is used for bulk operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a4d6-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4a4d6-114">In This Section</span></span>  
  
-   [<span data-ttu-id="4a4d6-115">Usando IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="4a4d6-115">Using IRow::GetColumns</span></span>](using-irow-getcolumns.md)  
  
-   [<span data-ttu-id="4a4d6-116">Buscando dados BLOB usando IRow</span><span class="sxs-lookup"><span data-stu-id="4a4d6-116">Fetching BLOB Data Using IRow</span></span>](../../database-engine/dev-guide/fetching-blob-data-using-irow.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a4d6-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a4d6-117">See Also</span></span>  
 [<span data-ttu-id="4a4d6-118">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="4a4d6-118">Rowsets</span></span>](rowsets.md)  
  
  
