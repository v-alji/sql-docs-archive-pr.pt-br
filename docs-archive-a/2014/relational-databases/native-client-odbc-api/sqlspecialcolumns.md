---
title: SQLSpecialColumns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: rothja
ms.author: jroth
ms.openlocfilehash: c36ff73606e95ed7ee5e713b81acf7c177a42563
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573962"
---
# <a name="sqlspecialcolumns"></a><span data-ttu-id="44cac-102">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="44cac-102">SQLSpecialColumns</span></span>
  <span data-ttu-id="44cac-103">Ao pedir identificadores de linha (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** retorna um conjunto de resultados vazio (nenhuma linha de dados) para qualquer escopo solicitado que não seja SQL_SCOPE_CURROW.</span><span class="sxs-lookup"><span data-stu-id="44cac-103">When requesting row identifiers (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** returns an empty result set (no data rows) for any requested scope other than SQL_SCOPE_CURROW.</span></span> <span data-ttu-id="44cac-104">O conjunto de resultados gerado indica que as colunas são válidas somente dentro desse escopo.</span><span class="sxs-lookup"><span data-stu-id="44cac-104">The generated result set indicates that the columns are only valid within this scope.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="44cac-105">não dá suporte a pseudocolunas para identificadores.</span><span class="sxs-lookup"><span data-stu-id="44cac-105">does not support pseudocolumns for identifiers.</span></span> <span data-ttu-id="44cac-106">O conjunto de resultados de **SQLSpecialColumns** identificará todas as colunas como SQL_PC_NOT_PSEUDO.</span><span class="sxs-lookup"><span data-stu-id="44cac-106">The **SQLSpecialColumns** result set will identify all columns as SQL_PC_NOT_PSEUDO.</span></span>  
  
 <span data-ttu-id="44cac-107">É possível executar**SQLSpecialColumns** em um cursor estático.</span><span class="sxs-lookup"><span data-stu-id="44cac-107">**SQLSpecialColumns** can be executed on a static cursor.</span></span> <span data-ttu-id="44cac-108">Uma tentativa de executar **SQLSpecialColumns** em um cursor atualizável (controlado por conjunto de chaves ou dinâmico) retorna SQL_SUCCESS_WITH_INFO, indicando que indica o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="44cac-108">An attempt to execute **SQLSpecialColumns** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="44cac-109">Suporte de SQLSpecialColumns a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="44cac-109">SQLSpecialColumns Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="44cac-110">Para obter informações sobre os valores de retorno para as colunas DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH e DECIMAL_DIGTS para tipos de data/hora, consulte [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="44cac-110">For information about the values returned for the columns DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH, and DECIMAL_DIGTS for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="44cac-111">Para obter mais informações gerais, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="44cac-111">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a><span data-ttu-id="44cac-112">Suporte a SQLSpecialColumns para UDTs grandes do CLR</span><span class="sxs-lookup"><span data-stu-id="44cac-112">SQLSpecialColumns Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="44cac-113">**SQLSpecialColumns** dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="44cac-113">**SQLSpecialColumns** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="44cac-114">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="44cac-114">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44cac-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44cac-115">See Also</span></span>  
 <span data-ttu-id="44cac-116">[Função SQLSpecialColumns](https://go.microsoft.com/fwlink/?LinkId=59371) </span><span class="sxs-lookup"><span data-stu-id="44cac-116">[SQLSpecialColumns Function](https://go.microsoft.com/fwlink/?LinkId=59371) </span></span>  
 [<span data-ttu-id="44cac-117">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="44cac-117">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
