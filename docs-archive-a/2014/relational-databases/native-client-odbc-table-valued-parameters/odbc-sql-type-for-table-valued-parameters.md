---
title: Tipo ODBC SQL para parâmetros com valor de tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
author: rothja
ms.author: jroth
ms.openlocfilehash: c8ed46bf117c9158ae5b60c10ebd89e3d348f77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581803"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a><span data-ttu-id="b4b72-102">Tipo ODBC SQL para parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="b4b72-102">ODBC SQL Type for Table-Valued Parameters</span></span>
  <span data-ttu-id="b4b72-103">O suporte para parâmetros com valor de tabela é fornecido por um novo tipo ODBC SQL, SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="b4b72-103">Support for table-valued parameters is provided by a new ODBC SQL type, SQL_SS_TABLE.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4b72-104">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4b72-104">Remarks</span></span>  
 <span data-ttu-id="b4b72-105">SQL_SS_TABLE não pode ser convertido em qualquer outro tipo de dados ODBC ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4b72-105">SQL_SS_TABLE cannot be converted to any other ODBC or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="b4b72-106">Se SQL_SS_TABLE for usado como um tipo de dados C no parâmetro *ValueType* de SQLBindParameter, ou se for feita uma tentativa de definir SQL_DESC_TYPE em um registro APD (descritor de parâmetro de aplicativo) como SQL_SS_TABLE, SQL_ERROR será retornado e um registro de diagnóstico será gerado com SQLSTATE = HY003, "tipo de buffer de aplicativo inválido".</span><span class="sxs-lookup"><span data-stu-id="b4b72-106">If SQL_SS_TABLE is used as a C data type in the *ValueType* parameter of SQLBindParameter, or an attempt is made to set SQL_DESC_TYPE in an application parameter descriptor (APD) record to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="b4b72-107">Se SQL_DESC_TYPE for definido como SQL_SS_TABLE em um registro do IPD e o registro do descritor de parâmetro de aplicativo correspondente não for SQL_C_DEFAULT, SQL_ERROR será retornado e um registro de diagnóstico será gerado com SQLSTATE=HY003, "Tipo de buffer de aplicativo inválido".</span><span class="sxs-lookup"><span data-stu-id="b4b72-107">If SQL_DESC_TYPE is set to SQL_SS_TABLE in an IPD record and the corresponding application parameter descriptor record is not SQL_C_DEFAULT, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span> <span data-ttu-id="b4b72-108">Isso pode ocorrer com o *ParameterType* de SQLSetDescField, SQLSetDescRec ou SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="b4b72-108">This can occur with the *ParameterType* of a SQLSetDescField, SQLSetDescRec or SQLBindParameter.</span></span>  
  
 <span data-ttu-id="b4b72-109">Se o parâmetro *TargetType* for SQL_SS_TABLE ao chamar SQLGetData, SQL_ERROR será retornado e um registro de diagnóstico será gerado com SQLSTATE = HY003, "tipo de buffer de aplicativo inválido".</span><span class="sxs-lookup"><span data-stu-id="b4b72-109">If the *TargetType* parameter is SQL_SS_TABLE when calling SQLGetData, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="b4b72-110">Não é possível associar uma coluna de parâmetros com valor de tabela como o tipo SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="b4b72-110">A table-valued parameter column cannot be bound as type SQL_SS_TABLE.</span></span> <span data-ttu-id="b4b72-111">Se `SQLBindParameter` for chamado com *ParameterType* definido como SQL_SS_TABLE, SQL_ERROR será retornado e um registro de diagnóstico será gerado com SQLSTATE = HY004, "tipo de dados SQL inválido".</span><span class="sxs-lookup"><span data-stu-id="b4b72-111">If `SQLBindParameter` is called with *ParameterType* set to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY004, "Invalid SQL data type".</span></span> <span data-ttu-id="b4b72-112">Isso também pode ocorrer com SQLSetDescField e SQLSetDescRec.</span><span class="sxs-lookup"><span data-stu-id="b4b72-112">This can also occur with SQLSetDescField and SQLSetDescRec.</span></span>  
  
 <span data-ttu-id="b4b72-113">Os valores de coluna de parâmetros com valor de tabela têm as mesmas opções de conversão de dados que as colunas de parâmetros e resultados.</span><span class="sxs-lookup"><span data-stu-id="b4b72-113">Table-valued parameter column values have the same data conversion options as parameters and result columns.</span></span>  
  
 <span data-ttu-id="b4b72-114">Um parâmetro com valor de tabela pode ser um parâmetro de entrada somente no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b4b72-114">A table-valued parameter can only be an input parameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="b4b72-115">Se for feita uma tentativa de definir SQL_DESC_PARAMETER_TYPE com um valor diferente de SQL_PARAM_INPUT por meio de SQLBindParameter ou SQLSetDescField, SQL_ERROR será retornado e um registro de diagnóstico será adicionado à instrução com SQLSTATE = HY105 e a mensagem "tipo de parâmetro inválido".</span><span class="sxs-lookup"><span data-stu-id="b4b72-115">If an attempt is made to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT via SQLBindParameter or SQLSetDescField, SQL_ERROR is returned and a diagnostic record is added to the statement with SQLSTATE=HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="b4b72-116">As colunas de parâmetros com valor de tabela não podem usar SQL_DEFAULT_PARAM em *StrLen_or_IndPtr*, porque não há suporte para valores padrão por linha com parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="b4b72-116">Table-valued parameter columns cannot use SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*, because per-row default values are not supported with table-valued parameters.</span></span> <span data-ttu-id="b4b72-117">Em vez disso, um aplicativo pode definir o atributo de coluna SQL_CA_SS_COL_HAS_DEFAULT_VALUE como 1.</span><span class="sxs-lookup"><span data-stu-id="b4b72-117">Instead, an application can set the column attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span> <span data-ttu-id="b4b72-118">Isso significa que a coluna terá valores padrão para todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="b4b72-118">This means that the column will have default values for all rows.</span></span> <span data-ttu-id="b4b72-119">Se *StrLen_or_IndPtr* for definido como SQL_DEFAULT_PARAM, SQLExecute ou SQLExecDirect retornará SQL_ERROR e um registro de diagnóstico será adicionado à instrução com SQLSTATE = HY090 e a mensagem "comprimento de buffer ou de cadeia de caracteres inválido".</span><span class="sxs-lookup"><span data-stu-id="b4b72-119">If *StrLen_or_IndPtr* is set to SQL_DEFAULT_PARAM, SQLExecute or SQLExecDirect will return SQL_ERROR, and a diagnostic record will be added to the statement with SQLSTATE=HY090 and the message "Invalid string or buffer length".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b72-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4b72-120">See Also</span></span>  
 [<span data-ttu-id="b4b72-121">Parâmetros com valor de tabela &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="b4b72-121">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
