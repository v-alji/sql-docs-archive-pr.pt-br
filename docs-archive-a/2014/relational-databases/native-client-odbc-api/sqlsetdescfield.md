---
title: SQLSetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b8290fd90c0c9bb91f08d94e119689d38fbc04e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582992"
---
# <a name="sqlsetdescfield"></a><span data-ttu-id="79574-102">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="79574-102">SQLSetDescField</span></span>
  <span data-ttu-id="79574-103">SQLSetDescField pode ser usado para definir campos de descritor para parâmetros com valor de tabela e colunas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="79574-103">SQLSetDescField can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="79574-104">Para obter informações sobre os campos disponíveis, consulte [campos de descritor de parâmetro com valor de tabela](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) e [campos de descritor para colunas constituintes de parâmetro com valor de tabela](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span><span class="sxs-lookup"><span data-stu-id="79574-104">For information about the available fields, see [Table-Valued Parameter Descriptor Fields](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) and [Descriptor Fields for Table-Valued Parameter Constituent Columns](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79574-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="79574-105">Remarks</span></span>  
 <span data-ttu-id="79574-106">As colunas do parâmetro com valor de tabela ficam disponíveis somente quando o campo do cabeçalho do descritor SQL_SOPT_SS_PARAM_FOCUS é definido como o ordinal de um registro que tenha SQL_DESC_TYPE definido como SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="79574-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="79574-107">Para obter mais informações sobre SQL_SPOT_SS_PARAM_FOCUS, consulte [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="79574-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="79574-108">Se for feita uma tentativa de definir SQL_SOPT_SS_PARAM_FOCUS para o ordinal de um parâmetro que não seja um parâmetro com valor de tabela, SQLSetStmtAttr retornará SQL_ERROR e um registro de diagnóstico será criado com SQLSTATE = HY024 e a mensagem "valor de atributo inválido".</span><span class="sxs-lookup"><span data-stu-id="79574-108">If an attempt is made to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a parameter that is not a table-valued parameter, SQLSetStmtAttr returns SQL_ERROR, and a diagnostic record is created with SQLSTATE = HY024 and the message "Invalid attribute value".</span></span> <span data-ttu-id="79574-109">SQL_SOPT_SS_PARAM_FOCUS não é alterado quando SQL_ERROR é retornado.</span><span class="sxs-lookup"><span data-stu-id="79574-109">SQL_SOPT_SS_PARAM_FOCUS is not changed when SQL_ERROR is returned.</span></span>  
  
 <span data-ttu-id="79574-110">A definição de SQL_SOPT_SS_PARAM_FOCUS como 0 restaura o acesso a registros de descritor para parâmetros.</span><span class="sxs-lookup"><span data-stu-id="79574-110">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores access to descriptor records for parameters.</span></span>  
  
 <span data-ttu-id="79574-111">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="79574-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="79574-112">Suporte do SQLSetDescField a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="79574-112">SQLSetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="79574-113">Os recursos de data/hora foram aprimorados no ODBC.</span><span class="sxs-lookup"><span data-stu-id="79574-113">Date/time features have been enhanced in ODBC.</span></span> <span data-ttu-id="79574-114">Para obter informações sobre o campo de descritor fornecido para os novos tipos de data/hora, consulte [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="79574-114">For information about the descriptor field provided for the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="79574-115">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="79574-115">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="79574-116">Suporte de SQLSetDescField a UDTs grandes do CLR</span><span class="sxs-lookup"><span data-stu-id="79574-116">SQLSetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="79574-117">O SQLSetDescField dá suporte a UDTs (tipos definidos pelo usuário) CLR grandes.</span><span class="sxs-lookup"><span data-stu-id="79574-117">SQLSetDescField supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="79574-118">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="79574-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a><span data-ttu-id="79574-119">Suporte de SQLSetDescField a colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="79574-119">SQLSetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="79574-120">SQLSetDecField pode ser usado para definir SQL_SOPT_SS_NAME_SCOPE no descritor de parâmetro do aplicativo (APD) para os valores SQL_SS_NAME_SCOPE_EXTENDED e SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="79574-120">SQLSetDecField can be used to set SQL_SOPT_SS_NAME_SCOPE in the application parameter descriptor (APD) to the values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span>  
  
 <span data-ttu-id="79574-121">Para obter mais informações, consulte [suporte a colunas esparsas &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="79574-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79574-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79574-122">See Also</span></span>  
 <span data-ttu-id="79574-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span><span class="sxs-lookup"><span data-stu-id="79574-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span></span>  
 [<span data-ttu-id="79574-124">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="79574-124">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
