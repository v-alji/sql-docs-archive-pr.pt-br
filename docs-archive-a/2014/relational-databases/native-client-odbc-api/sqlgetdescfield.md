---
title: SQLGetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetDescField function
ms.assetid: 3e59a37a-28ee-4c91-8968-7fe3b966739d
author: rothja
ms.author: jroth
ms.openlocfilehash: 4538396dbfb5406d0464c4730c1f6f3bd5882799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575108"
---
# <a name="sqlgetdescfield"></a><span data-ttu-id="96ddb-102">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="96ddb-102">SQLGetDescField</span></span>
  <span data-ttu-id="96ddb-103">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client expõe campos de descritor específicos de driver apenas para o IRD (descritor de linhas de implementação).</span><span class="sxs-lookup"><span data-stu-id="96ddb-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver exposes driver-specific descriptor fields for the implementation row descriptor (IRD) only.</span></span> <span data-ttu-id="96ddb-104">No IRD, a referência aos campos de descritor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é feita com atributos de coluna específicos de driver.</span><span class="sxs-lookup"><span data-stu-id="96ddb-104">Within the IRD, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] descriptor fields are referenced through driver-specific column attributes.</span></span> <span data-ttu-id="96ddb-105">Para obter uma lista completa dos campos de descritor específicos de driver disponíveis, consulte [SQLColAttribute](sqlcolattribute.md).</span><span class="sxs-lookup"><span data-stu-id="96ddb-105">For information about a complete list of available driver-specific descriptor fields, see [SQLColAttribute](sqlcolattribute.md).</span></span>  
  
 <span data-ttu-id="96ddb-106">Os campos de descritor que contêm cadeias de caracteres de identificador de coluna são, em geral, cadeias de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="96ddb-106">Descriptor fields that contain column identifier strings are often zero-length strings.</span></span> <span data-ttu-id="96ddb-107">Todos os valores de campos de descritor específicos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="96ddb-107">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific descriptor field values are read-only.</span></span>  
  
 <span data-ttu-id="96ddb-108">Como os atributos recuperados com SQLColAttribute, os campos de descritor que relatam atributos de nível de linha (como SQL_CA_SS_COMPUTE_ID) são relatados para todas as colunas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="96ddb-108">Like attributes retrieved with SQLColAttribute, descriptor fields that report row-level attributes (such as SQL_CA_SS_COMPUTE_ID) are reported for all columns in the result set.</span></span>  
  
## <a name="sqlgetdescfield-and-table-valued-parameters"></a><span data-ttu-id="96ddb-109">SQLGetDescField e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="96ddb-109">SQLGetDescField and Table-Valued Parameters</span></span>  
 <span data-ttu-id="96ddb-110">SQLGetDescField pode ser usado para obter valores para atributos estendidos de parâmetros com valor de tabela e colunas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="96ddb-110">SQLGetDescField can be used to get values for extended attributes of table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="96ddb-111">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="96ddb-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="96ddb-112">Suporte do SQLGetDescField a recursos avançados de data e hora</span><span class="sxs-lookup"><span data-stu-id="96ddb-112">SQLGetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="96ddb-113">Para obter informações sobre os campos de descritor disponíveis com os novos tipos de data/hora, consulte [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="96ddb-113">For information about the descriptor fields available with the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="96ddb-114">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="96ddb-114">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
 <span data-ttu-id="96ddb-115">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , SQLGetDescField pode retornar `SQL_C_SS_TIME2` (para `time` tipos) ou `SQL_C_SS_TIMESTAMPOFFSET` (for `datetimeoffset` ) em vez de `SQL_C_BINARY` , se seu aplicativo usar o ODBC 3,8.</span><span class="sxs-lookup"><span data-stu-id="96ddb-115">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], SQLGetDescField can return `SQL_C_SS_TIME2` (for `time` types) or `SQL_C_SS_TIMESTAMPOFFSET` (for `datetimeoffset`) instead of `SQL_C_BINARY`, if your application uses ODBC 3.8.</span></span>  
  
## <a name="sqlgetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="96ddb-116">Suporte do SQLGetDescField a UDTs de CLR grandes</span><span class="sxs-lookup"><span data-stu-id="96ddb-116">SQLGetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="96ddb-117">`SQLGetDescField` dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="96ddb-117">`SQLGetDescField` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="96ddb-118">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="96ddb-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-sparse-columns"></a><span data-ttu-id="96ddb-119">Suporte do SQLGetDescField a colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="96ddb-119">SQLGetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="96ddb-120">SQLGetDescField pode ser usado para consultar o novo campo IRD SQL_CA_SS_IS_COLUMN_SET para determinar se uma coluna é uma `column_set` coluna.</span><span class="sxs-lookup"><span data-stu-id="96ddb-120">SQLGetDescField can be used to query the new IRD field SQL_CA_SS_IS_COLUMN_SET to determine if a column is a `column_set` column.</span></span>  
  
 <span data-ttu-id="96ddb-121">Para obter mais informações, consulte [suporte a colunas esparsas &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="96ddb-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96ddb-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="96ddb-122">Example</span></span>  
  
```  
typedef struct tagCOMPUTEBYLIST  
    {  
    SQLSMALLINT nBys;  
    SQLSMALLINT aByList[1];  
    } COMPUTEBYLIST;  
typedef COMPUTEBYLIST* PCOMPUTEBYLIST;   
  
SQLHDESC    hIRD;   
SQLINTEGER  cbIRD;   
SQLINTEGER  nSet = 0;   
  
// . . .  
// Execute a statement that contains a COMPUTE clause,  
//  then get the descriptor handle of the IRD and  
//  get some IRD values.  
  
SQLGetStmtAttr(g_hStmt, SQL_ATTR_IMP_ROW_DESC,  
    (SQLPOINTER) &hIRD, sizeof(SQLHDESC), &cbIRD);  
  
// For statement-wide column attributes, any  
//  descriptor record will do. You know that 1 exists,  
//  so use it.  
SQLGetDescField(hIRD, 1, SQL_CA_SS_NUM_COMPUTES,  
    (SQLPOINTER) &nComputes, SQL_IS_INTEGER, &cbIRD);  
  
if (nSet == 0)  
    {  
    SQLINTEGER      nOrderID;  
  
    printf_s("Normal result set.\n");  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ORDER,  
            (SQLPOINTER) &nOrderID, SQL_IS_INTEGER,  
            &cbIRD);  
  
        if (nOrderID != 0)  
            {  
            printf_s("Col in ORDER BY, pos: %ld",  
                nOrderID);  
            }  
            printf_s("\n");  
        }  
  
    printf_s("\n");  
    }  
else  
    {  
    PCOMPUTEBYLIST  pByList;  
    SQLSMALLINT     nBy;  
    SQLINTEGER      nColID;  
  
    printf_s("Computed result set number: %lu\n",  
        nSet);  
  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_BYLIST,  
        (SQLPOINTER) &pByList, SQL_IS_INTEGER,  
        &cbIRD);  
  
    if (pByList != NULL)  
        {  
        printf_s("Clause ordered by columns: ");  
        for (nBy = 0; nBy < pByList->nBys; )  
            {  
            printf_s("%u", pByList->aByList[nBy]);  
            nBy++;  
  
            if (nBy == pByList->nBys)  
                {  
                printf_s("\n");  
                }  
            else  
                {  
                printf_s(", ");  
                }  
            }  
        }  
    else  
        {  
        printf_s("Compute clause set not ordered.\n");  
        }  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ID, (SQLPOINTER) &nColID,  
            SQL_IS_INTEGER, &cbIRD);  
        printf_s("ColumnID: %lu, nColID);  
        }  
    printf_s("\n");  
    }  
  
if (SQLMoreResults(g_hStmt) == SQL_SUCCESS)  
    {  
    // Determine the result set indicator.  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_ID,  
        (SQLPOINTER) &nSet, SQL_IS_INTEGER, &cbIRD);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="96ddb-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96ddb-123">See Also</span></span>  
 <span data-ttu-id="96ddb-124">[Função SQLGetDescField](https://go.microsoft.com/fwlink/?LinkId=59351) </span><span class="sxs-lookup"><span data-stu-id="96ddb-124">[SQLGetDescField Function](https://go.microsoft.com/fwlink/?LinkId=59351) </span></span>  
 [<span data-ttu-id="96ddb-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="96ddb-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
