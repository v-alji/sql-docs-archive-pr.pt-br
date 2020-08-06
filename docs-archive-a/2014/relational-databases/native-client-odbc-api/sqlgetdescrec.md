---
title: SQLGetDescRec | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLGetDescRec function
ms.assetid: f3389ff2-f3be-4035-9fb5-c9ebc2f15025
author: rothja
ms.author: jroth
ms.openlocfilehash: 11e0e43b5c9cec15627b7f32ebe51fc28d74786c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570679"
---
# <a name="sqlgetdescrec"></a><span data-ttu-id="20ff7-102">SQLGetDescRec</span><span class="sxs-lookup"><span data-stu-id="20ff7-102">SQLGetDescRec</span></span>
  <span data-ttu-id="20ff7-103">Este tópico discute a funcionalidade do SQLGetDescRec que é específica para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="20ff7-103">This topic discusses SQLGetDescRec functionality that is specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="sqlgetdescrec-and-table-valued-parameters"></a><span data-ttu-id="20ff7-104">SQLGetDescRec e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="20ff7-104">SQLGetDescRec and Table-Valued Parameters</span></span>  
 <span data-ttu-id="20ff7-105">SQLGetDescRec pode ser usado para obter valores para atributos de parâmetros com valor de tabela e colunas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="20ff7-105">SQLGetDescRec can be used to get values for attributes of table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="20ff7-106">O parâmetro *RecNumber* de SQLGetDescRec corresponde ao parâmetro *ParameterNumber* de SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="20ff7-106">The *RecNumber* parameter of SQLGetDescRec corresponds to the *ParameterNumber* parameter of SQLBindParameter.</span></span>  
  
 <span data-ttu-id="20ff7-107">As colunas do parâmetro com valor de tabela ficam disponíveis somente quando o campo do cabeçalho do descritor SQL_SOPT_SS_PARAM_FOCUS é definido como o ordinal de um registro que tenha SQL_DESC_TYPE definido como SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="20ff7-107">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="20ff7-108">Para obter mais informações sobre SQL_SOPT_SS_PARAM_FOCUS, consulte [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="20ff7-108">For more information about SQL_SOPT_SS_PARAM_FOCUS about, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="20ff7-109">SQLGetDescRec retorna os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="20ff7-109">SQLGetDescRec returns the following data:</span></span>  
  
|<span data-ttu-id="20ff7-110">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="20ff7-110">Parameter</span></span>|<span data-ttu-id="20ff7-111">Parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="20ff7-111">Table-valued parameter</span></span>|<span data-ttu-id="20ff7-112">Colunas de parâmetro com valor de tabela e outros parâmetros</span><span class="sxs-lookup"><span data-stu-id="20ff7-112">Table-valued parameter columns and other parameters</span></span>|  
|---------------|-----------------------------|----------------------------------------------------------|  
|<span data-ttu-id="20ff7-113">*Nome*</span><span class="sxs-lookup"><span data-stu-id="20ff7-113">*Name*</span></span>|<span data-ttu-id="20ff7-114">O nome de parâmetro formal para uma chamada de procedimento armazenado; caso contrário, uma cadeia de caracteres de comprimento 0.</span><span class="sxs-lookup"><span data-stu-id="20ff7-114">The formal parameter name for a stored procedure call; otherwise, a 0 length string.</span></span>|<span data-ttu-id="20ff7-115">O nome da coluna do parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="20ff7-115">The table-valued parameter column name.</span></span>|  
|<span data-ttu-id="20ff7-116">*TypePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-116">*TypePtr*</span></span>|<span data-ttu-id="20ff7-117">SQL_DESC_TYPE.</span><span class="sxs-lookup"><span data-stu-id="20ff7-117">SQL_DESC_TYPE.</span></span> <span data-ttu-id="20ff7-118">Para parâmetros com valor de tabela, este é SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="20ff7-118">For table-vaued parameters, this is SQL_SS_TABLE.</span></span>|<span data-ttu-id="20ff7-119">SQL_DESC_TYPE</span><span class="sxs-lookup"><span data-stu-id="20ff7-119">SQL_DESC_TYPE</span></span>|  
|<span data-ttu-id="20ff7-120">*SubTypePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-120">*SubTypePtr*</span></span>|<span data-ttu-id="20ff7-121">Indefinido</span><span class="sxs-lookup"><span data-stu-id="20ff7-121">Undefined</span></span>|<span data-ttu-id="20ff7-122">SQL_DESC_DATETIME_INTERVAL_CODE (Para registros do tipo SQL_DATETIME ou SQL_INTERVAL.)</span><span class="sxs-lookup"><span data-stu-id="20ff7-122">SQL_DESC_DATETIME_INTERVAL_CODE (For records of type SQL_DATETIME or SQL_INTERVAL.)</span></span>|  
|<span data-ttu-id="20ff7-123">*LengthPtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-123">*LengthPtr*</span></span>|<span data-ttu-id="20ff7-124">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-124">0</span></span>|<span data-ttu-id="20ff7-125">SQL_DESC_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20ff7-125">SQL_DESC_OCTET_LENGTH</span></span>|  
|<span data-ttu-id="20ff7-126">*PrecisionPtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-126">*PrecisionPtr*</span></span>|<span data-ttu-id="20ff7-127">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-127">0</span></span>|<span data-ttu-id="20ff7-128">SQL_DESC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20ff7-128">SQL_DESC_PRECISION</span></span>|  
|<span data-ttu-id="20ff7-129">*ScalePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-129">*ScalePtr*</span></span>|<span data-ttu-id="20ff7-130">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-130">0</span></span>|<span data-ttu-id="20ff7-131">SQL_DESC_SCALE</span><span class="sxs-lookup"><span data-stu-id="20ff7-131">SQL_DESC_SCALE</span></span>|  
|<span data-ttu-id="20ff7-132">*NullablePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-132">*NullablePtr*</span></span>|<span data-ttu-id="20ff7-133">1</span><span class="sxs-lookup"><span data-stu-id="20ff7-133">1</span></span>|<span data-ttu-id="20ff7-134">SQL_DESC_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="20ff7-134">SQL_DESC_NULLABLE</span></span>|  
  
 <span data-ttu-id="20ff7-135">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="20ff7-135">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgetdescrec-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="20ff7-136">Suporte de SQLGetDescRec a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="20ff7-136">SQLGetDescRec Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="20ff7-137">Os valores retornados para tipos de data/hora são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="20ff7-137">The values returned for date/time types are as follows:</span></span>  
  
||<span data-ttu-id="20ff7-138">*TypePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-138">*TypePtr*</span></span>|<span data-ttu-id="20ff7-139">*SubTypePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-139">*SubTypePtr*</span></span>|<span data-ttu-id="20ff7-140">*LengthPtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-140">*LengthPtr*</span></span>|<span data-ttu-id="20ff7-141">*PrecisionPtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-141">*PrecisionPtr*</span></span>|<span data-ttu-id="20ff7-142">*ScalePtr*</span><span class="sxs-lookup"><span data-stu-id="20ff7-142">*ScalePtr*</span></span>|  
|-|---------------|------------------|-----------------|--------------------|----------------|  
|<span data-ttu-id="20ff7-143">DATETIME</span><span class="sxs-lookup"><span data-stu-id="20ff7-143">datetime</span></span>|<span data-ttu-id="20ff7-144">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="20ff7-144">SQL_DATETIME</span></span>|<span data-ttu-id="20ff7-145">SQL_CODE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="20ff7-145">SQL_CODE_TIMESTAMP</span></span>|<span data-ttu-id="20ff7-146">4</span><span class="sxs-lookup"><span data-stu-id="20ff7-146">4</span></span>|<span data-ttu-id="20ff7-147">3</span><span class="sxs-lookup"><span data-stu-id="20ff7-147">3</span></span>|<span data-ttu-id="20ff7-148">3</span><span class="sxs-lookup"><span data-stu-id="20ff7-148">3</span></span>|  
|<span data-ttu-id="20ff7-149">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="20ff7-149">smalldatetime</span></span>|<span data-ttu-id="20ff7-150">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="20ff7-150">SQL_DATETIME</span></span>|<span data-ttu-id="20ff7-151">SQL_CODE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="20ff7-151">SQL_CODE_TIMESTAMP</span></span>|<span data-ttu-id="20ff7-152">8</span><span class="sxs-lookup"><span data-stu-id="20ff7-152">8</span></span>|<span data-ttu-id="20ff7-153">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-153">0</span></span>|<span data-ttu-id="20ff7-154">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-154">0</span></span>|  
|<span data-ttu-id="20ff7-155">date</span><span class="sxs-lookup"><span data-stu-id="20ff7-155">date</span></span>|<span data-ttu-id="20ff7-156">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="20ff7-156">SQL_DATETIME</span></span>|<span data-ttu-id="20ff7-157">SQL_CODE_DATE</span><span class="sxs-lookup"><span data-stu-id="20ff7-157">SQL_CODE_DATE</span></span>|<span data-ttu-id="20ff7-158">6</span><span class="sxs-lookup"><span data-stu-id="20ff7-158">6</span></span>|<span data-ttu-id="20ff7-159">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-159">0</span></span>|<span data-ttu-id="20ff7-160">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-160">0</span></span>|  
|<span data-ttu-id="20ff7-161">time</span><span class="sxs-lookup"><span data-stu-id="20ff7-161">time</span></span>|<span data-ttu-id="20ff7-162">SQL_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="20ff7-162">SQL_SS_TIME2</span></span>|<span data-ttu-id="20ff7-163">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-163">0</span></span>|<span data-ttu-id="20ff7-164">10</span><span class="sxs-lookup"><span data-stu-id="20ff7-164">10</span></span>|<span data-ttu-id="20ff7-165">0..7</span><span class="sxs-lookup"><span data-stu-id="20ff7-165">0..7</span></span>|<span data-ttu-id="20ff7-166">0..7</span><span class="sxs-lookup"><span data-stu-id="20ff7-166">0..7</span></span>|  
|<span data-ttu-id="20ff7-167">datetime2</span><span class="sxs-lookup"><span data-stu-id="20ff7-167">datetime2</span></span>|<span data-ttu-id="20ff7-168">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="20ff7-168">SQL_DATETIME</span></span>|<span data-ttu-id="20ff7-169">SQL_CODE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="20ff7-169">SQL_CODE_TIMESTAMP</span></span>|<span data-ttu-id="20ff7-170">16</span><span class="sxs-lookup"><span data-stu-id="20ff7-170">16</span></span>|<span data-ttu-id="20ff7-171">0..7</span><span class="sxs-lookup"><span data-stu-id="20ff7-171">0..7</span></span>|<span data-ttu-id="20ff7-172">0..7</span><span class="sxs-lookup"><span data-stu-id="20ff7-172">0..7</span></span>|  
|<span data-ttu-id="20ff7-173">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="20ff7-173">datetimeoffset</span></span>|<span data-ttu-id="20ff7-174">SQL_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="20ff7-174">SQL_SS_TIMESTAMPOFFSET</span></span>|<span data-ttu-id="20ff7-175">0</span><span class="sxs-lookup"><span data-stu-id="20ff7-175">0</span></span>|<span data-ttu-id="20ff7-176">20</span><span class="sxs-lookup"><span data-stu-id="20ff7-176">20</span></span>|<span data-ttu-id="20ff7-177">0..7</span><span class="sxs-lookup"><span data-stu-id="20ff7-177">0..7</span></span>|<span data-ttu-id="20ff7-178">0..7</span><span class="sxs-lookup"><span data-stu-id="20ff7-178">0..7</span></span>|  
  
 <span data-ttu-id="20ff7-179">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="20ff7-179">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdescrec-support-for-large-clr-udts"></a><span data-ttu-id="20ff7-180">Suporte de SQLGetDescRec para UDTs CLR grandes</span><span class="sxs-lookup"><span data-stu-id="20ff7-180">SQLGetDescRec Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="20ff7-181">`SQLGetDescRec` dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="20ff7-181">`SQLGetDescRec` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="20ff7-182">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="20ff7-182">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ff7-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="20ff7-183">See Also</span></span>  
 <span data-ttu-id="20ff7-184">[SQLGetDescRec](https://go.microsoft.com/fwlink/?LinkId=80707) </span><span class="sxs-lookup"><span data-stu-id="20ff7-184">[SQLGetDescRec](https://go.microsoft.com/fwlink/?LinkId=80707) </span></span>  
 [<span data-ttu-id="20ff7-185">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="20ff7-185">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  