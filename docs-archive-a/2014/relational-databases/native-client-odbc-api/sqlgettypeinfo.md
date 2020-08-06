---
title: SQLGetTypeInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetTypeInfo function
ms.assetid: 13b982c3-ae03-4155-bc0d-e225050703ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b2bca833eeed5e51237347a5ea118d839dd36de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583025"
---
# <a name="sqlgettypeinfo"></a><span data-ttu-id="4f01f-102">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="4f01f-102">SQLGetTypeInfo</span></span>
  <span data-ttu-id="4f01f-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client relata o tipo de coluna adicional no conjunto de resultados de `SQLGetTypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="4f01f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports the additional column USERTYPE in the result set of `SQLGetTypeInfo`.</span></span> <span data-ttu-id="4f01f-104">USERTYPE informa a definição do tipo de dados da biblioteca do banco de dados, sendo útil para desenvolvedores que estejam portando aplicativos existentes da biblioteca para ODBC.</span><span class="sxs-lookup"><span data-stu-id="4f01f-104">USERTYPE reports the DB-Library data type definition and is useful to developers porting existing DB-Library applications to ODBC.</span></span>  
  
 <span data-ttu-id="4f01f-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trata identidade como um atributo, ao passo que o ODBC a trata como um tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="4f01f-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats identity as an attribute, whereas ODBC treats it as a data type.</span></span> <span data-ttu-id="4f01f-106">Para resolver essa incompatibilidade, `SQLGetTypeInfo` retorna os tipos de dados: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**e **NumericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="4f01f-106">To resolve this mismatch, `SQLGetTypeInfo` returns the data types: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**, and **numericidentity**.</span></span> <span data-ttu-id="4f01f-107">A `SQLGetTypeInfo` coluna conjunto de resultados AUTO_UNIQUE_VALUE relata o valor true para esses tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="4f01f-107">The `SQLGetTypeInfo` result set column AUTO_UNIQUE_VALUE reports the value TRUE for these data types.</span></span>  
  
 <span data-ttu-id="4f01f-108">Para **varchar**, **nvarchar** e **varbinary**, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client continua a relatar 8000, 4000 e 8000, respectivamente, para o valor COLUMN_SIZE, mesmo que seja realmente ilimitado.</span><span class="sxs-lookup"><span data-stu-id="4f01f-108">For **varchar**, **nvarchar** and **varbinary**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver continues to report 8000, 4000 and 8000 respectively for the COLUMN_SIZE value, even though it is actually unlimited.</span></span> <span data-ttu-id="4f01f-109">Isso é para assegurar a compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="4f01f-109">This is to ensure backward compatibility.</span></span>  
  
 <span data-ttu-id="4f01f-110">Para o tipo de dados **XML** , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client relata SQL_SS_LENGTH_UNLIMITED para COLUMN_SIZE para denotar tamanho ilimitado.</span><span class="sxs-lookup"><span data-stu-id="4f01f-110">For the **xml** data type, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports SQL_SS_LENGTH_UNLIMITED for COLUMN_SIZE to denote unlimited size.</span></span>  
  
## <a name="sqlgettypeinfo-and-table-valued-parameters"></a><span data-ttu-id="4f01f-111">SQLGetTypeInfo e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="4f01f-111">SQLGetTypeInfo and Table-Valued Parameters</span></span>  
 <span data-ttu-id="4f01f-112">O tipo de tabela para parâmetros com valor de tabela é efetivamente um meta-tipo, ou seja, um tipo usado para definir outros tipos.</span><span class="sxs-lookup"><span data-stu-id="4f01f-112">The table type for table-valued parameters is effectively a meta-type-that is, a type used to define other types.</span></span> <span data-ttu-id="4f01f-113">Portanto, ele não precisa ser exposto por meio do SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="4f01f-113">Therefore, it does not have to be exposed through SQLGetTypeInfo.</span></span> <span data-ttu-id="4f01f-114">Os aplicativos devem usar SQLTables, em vez de SQLGetTypeInfo, para recuperar metadados para tipos de tabela usados com parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="4f01f-114">Applications must use SQLTables, rather than SQLGetTypeInfo, to retrieve metadata for table types used with table-valued parameters.</span></span>  
  
 <span data-ttu-id="4f01f-115">Para obter mais informações, sobre como recuperar metdata para parâmetros com valor de tabela, consulte [atributos de instrução que afetam os parâmetros com valor de tabela](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4f01f-115">For more information, about retrieving metdata for table-valued parameters, see [Statement Attributes that Affect Table-Valued Parameters](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span></span>  
  
 <span data-ttu-id="4f01f-116">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f01f-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="4f01f-117">Suporte de SQLGetTypeInfo a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="4f01f-117">SQLGetTypeInfo Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="4f01f-118">Para obter os valores retornados para tipos de data/hora, consulte [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="4f01f-118">For the values returned for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="4f01f-119">Para obter mais informações gerais, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f01f-119">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-large-clr-udts"></a><span data-ttu-id="4f01f-120">Suporte de SQLGetTypeInfo a grandes UDTs do CLR</span><span class="sxs-lookup"><span data-stu-id="4f01f-120">SQLGetTypeInfo Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="4f01f-121">`SQLGetTypeInfo` dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="4f01f-121">`SQLGetTypeInfo` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="4f01f-122">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f01f-122">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f01f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f01f-123">See Also</span></span>  
 <span data-ttu-id="4f01f-124">[Função SQLGetTypeInfo](https://go.microsoft.com/fwlink/?LinkId=59356) </span><span class="sxs-lookup"><span data-stu-id="4f01f-124">[SQLGetTypeInfo Function](https://go.microsoft.com/fwlink/?LinkId=59356) </span></span>  
 [<span data-ttu-id="4f01f-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="4f01f-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
