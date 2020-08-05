---
title: Tipos de cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: rothja
ms.author: jroth
ms.openlocfilehash: 6937dbb9ce42cd5631201e0c97be42b211742ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572080"
---
# <a name="cursor-types"></a><span data-ttu-id="7dfcf-102">Tipos de cursor</span><span class="sxs-lookup"><span data-stu-id="7dfcf-102">Cursor Types</span></span>
  <span data-ttu-id="7dfcf-103">O ODBC define quatro tipos de cursor com suporte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da Microsoft e do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-103">ODBC defines four cursor types supported by Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="7dfcf-104">Esses cursores variam em sua capacidade de detectar alterações no conjunto de resultados e nos recursos que eles consomem, como memória e espaço em **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-104">These cursors vary in their ability to detect changes to the result set and in the resources they consume, such as memory and space in **tempdb**.</span></span> <span data-ttu-id="7dfcf-105">Um cursor pode detectar alterações nas linhas apenas quando ele tenta buscar essas linhas novamente; não há como a fonte de dados notificar o cursor dessas alterações nas linhas que estão sendo buscadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-105">A cursor can detect changes to rows only when it tries to refetch those rows; there is no way for the data source to notify the cursor of changes to the currently fetched rows.</span></span> <span data-ttu-id="7dfcf-106">A capacidade de um cursor de detectar alterações que não foram feitas pelo cursor também é influenciada pelo nível de isolamento da transação.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-106">A cursor's ability to detect changes that were not made through the cursor is also influenced by the transaction isolation level.</span></span>  
  
 <span data-ttu-id="7dfcf-107">Estes são os quatro tipos de cursor ODBC suportados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7dfcf-107">These are the four ODBC cursor types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="7dfcf-108">Cursores de somente avanço não suportam o recurso de rolagem; eles suportam apenas a busca de linhas em série do início ao fim do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-108">Forward-only cursors do not support scrolling; they only support fetching rows serially from the start to the end of the cursor.</span></span>  
  
-   <span data-ttu-id="7dfcf-109">Cursores estáticos são criados em **tempdb** quando o cursor é aberto.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-109">Static cursors are built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="7dfcf-110">Eles sempre exibem o conjunto de resultados da forma como ele estava quando o cursor foi aberto.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-110">They always display the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="7dfcf-111">Eles nunca refletem alterações aos dados.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-111">They never reflect changes to the data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7dfcf-112">cursores estáticos são sempre somente leitura.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-112">static cursors are always read-only.</span></span> <span data-ttu-id="7dfcf-113">Como um cursor de servidor estático é criado como uma tabela de trabalho em **tempdb**, o tamanho do conjunto de resultados do cursor não pode exceder o tamanho máximo de linha permitido pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7dfcf-113">Because a static server cursor is built as a work table in **tempdb**, the size of the cursor result set cannot exceed the maximum row size allowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7dfcf-114">Os cursores controlados por conjunto de chaves têm a associação (membership) e a ordem das linhas fixas no conjunto de resultados quando o cursor é aberto.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-114">Keyset-driven cursors have the membership and order of rows in the result set fixed when the cursor is opened.</span></span> <span data-ttu-id="7dfcf-115">As alterações nas colunas não chave são visíveis pelo cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-115">Changes to nonkey columns are visible through the cursor.</span></span>  
  
-   <span data-ttu-id="7dfcf-116">Os cursores dinâmicos são o oposto dos cursores estáticos.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-116">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="7dfcf-117">Eles refletem todas as alterações feitas nas linhas de seu conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-117">Dynamic cursors reflect all changes made to the rows in their result set.</span></span> <span data-ttu-id="7dfcf-118">Os valores de dados, a ordem e a associação das linhas do conjunto de resultados podem ser alterados em cada busca.</span><span class="sxs-lookup"><span data-stu-id="7dfcf-118">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfcf-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7dfcf-119">See Also</span></span>  
 [<span data-ttu-id="7dfcf-120">Usando cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="7dfcf-120">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
