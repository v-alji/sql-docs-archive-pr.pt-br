---
title: Enviando dados como um parâmetro com valor de tabela com todos os valores na memória (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), sending data to a stored procedure with all values in memory
ms.assetid: 8b96282f-00d5-4e28-8111-0a87ae6d7781
author: rothja
ms.author: jroth
ms.openlocfilehash: f53e129ea49b1faa08be5247c51b5e74353e2f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685095"
---
# <a name="sending-data-as-a-table-valued-parameter-with-all-values-in-memory-odbc"></a><span data-ttu-id="55d7d-102">Enviando dados como um parâmetro com valor de tabela com todos os valores na memória (ODBC)</span><span class="sxs-lookup"><span data-stu-id="55d7d-102">Sending Data as a Table-Valued Parameter with All Values in Memory (ODBC)</span></span>
  <span data-ttu-id="55d7d-103">Este tópico descreve como enviar dados a um procedimento armazenado como um parâmetro com valor de tabela quando todos os valores estão na memória.</span><span class="sxs-lookup"><span data-stu-id="55d7d-103">This topic describes how to send data to a stored procedure as a table-valued parameter when all values are in memory.</span></span> <span data-ttu-id="55d7d-104">Para outro exemplo que demonstra parâmetros com valor de tabela, consulte [usar parâmetros com valor de tabela &#40;&#41;ODBC ](table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="55d7d-104">For another sample demonstrating table-valued parameters, see [Use Table-Valued Parameters &#40;ODBC&#41;](table-valued-parameters-odbc.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="55d7d-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="55d7d-105">Prerequisite</span></span>  
 <span data-ttu-id="55d7d-106">Esse procedimento supõe que o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] tenha sido executado no servidor:</span><span class="sxs-lookup"><span data-stu-id="55d7d-106">This procedure assumes that the following [!INCLUDE[tsql](../../includes/tsql-md.md)] has been executed on the server:</span></span>  
  
```  
create type TVParam as table(ProdCode integer, Qty integer)  
create procedure TVPOrderEntry(@CustCode varchar(5), @Items TVPParam,   
            @OrdNo integer output, @OrdDate datetime output)  
         as   
         set @OrdDate = GETDATE();  
         insert into TVPOrd (OrdDate, CustCode)   
values (@OrdDate, @CustCode) output OrdNo);   
         select @OrdNo = SCOPE_IDENTITY();   
         insert into TVPItem (OrdNo, ProdCode, Qty)  
select @OrdNo, @Items.ProdCode, @Items.Qty   
from @Items  
```  
  
## <a name="to-send-the-data"></a><span data-ttu-id="55d7d-107">Para enviar os dados</span><span class="sxs-lookup"><span data-stu-id="55d7d-107">To Send the Data</span></span>  
  
1.  <span data-ttu-id="55d7d-108">Declare variáveis para os parâmetros SQL.</span><span class="sxs-lookup"><span data-stu-id="55d7d-108">Declare variables for the SQL parameters.</span></span> <span data-ttu-id="55d7d-109">Neste caso, o valor de tabela é mantido completamente na memória e, dessa forma, os valores para as colunas do valor de tabela são declarados como matrizes.</span><span class="sxs-lookup"><span data-stu-id="55d7d-109">In this case, the table value is held entirely in memory, so values for the columns of the table value are declared as arrays.</span></span>  
  
    ```  
    SQLRETURN r;  
    // Variables for SQL parameters.  
    #define ITEM_ARRAY_SIZE 20  
  
    SQLCHAR CustCode[6];  
    SQLCHAR *TVP = (SQLCHAR *) "TVParam";  
    SQLINTEGER ProdCode[ITEM_ARRAY_SIZE], Qty[ITEM_ARRAY_SIZE];  
    SQLINTEGER OrdNo;  
    char OrdDate[23];  
  
    // Variables for indicator/length variables associated with parameters.  
    SQLLEN cbCustCode, cbTVP, cbProdCode[ITEM_ARRAY_SIZE], cbQty[ITEM_ARRAY_SIZE], cbOrdNo, cbOrdDate;  
    ```  
  
2.  <span data-ttu-id="55d7d-110">Associe os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="55d7d-110">Bind the parameters.</span></span> <span data-ttu-id="55d7d-111">A associação de parâmetros é um processo de dois estágios quando são usados parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="55d7d-111">Binding parameters is a two stage process when table-valued parameters are used.</span></span> <span data-ttu-id="55d7d-112">No primeiro estágio, os parâmetros das etapas para o procedimento armazenado são associados de maneira normal, como a seguir.</span><span class="sxs-lookup"><span data-stu-id="55d7d-112">In the first stage, step parameters for the stored procedure are bound in the normal way, as follows.</span></span>  
  
    ```  
    // Bind parameters for call to TVPOrderEntryDirect.  
    // 1 - Custcode input  
    r = SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT,SQL_VARCHAR, SQL_C_CHAR, 5, 0, CustCode, sizeof(CustCode), &cbCustCode);  
  
    // 2 - Items TVP  
    r = SQLBindParameter(hstmt,   
        2,// ParameterNumber  
        SQL_PARAM_INPUT,// InputOutputType  
        SQL_C_DEFAULT,// ValueType   
        SQL_SS_TABLE,// Parametertype  
        ITEM_ARRAY_SIZE,// ColumnSize: For a table-valued parameter this is the row array size.  
        0,// DecimalDigits: For a table-valued parameter this is always 0.   
        TVP,// ParameterValuePtr: For a table-valued parameter this is the type name of the   
    //table-valued parameter, and also a token returned by SQLParamData.  
        SQL_NTS,// BufferLength: For a table-valued parameter this is the length of the type name or SQL_NTS.  
        &cbTVP);// StrLen_or_IndPtr: For a table-valued parameter this is the number of rows actually used.  
  
    // 3 - OrdNo output  
    r = SQLBindParameter(hstmt, 3, SQL_PARAM_OUTPUT,SQL_INTEGER, SQL_C_LONG, 0, 0, &OrdNo,  
       sizeof(SQLINTEGER), &cbOrdNo);  
    // 4 - OrdDate output  
    r = SQLBindParameter(hstmt, 4, SQL_PARAM_OUTPUT,SQL_TYPE_TIMESTAMP, SQL_C_CHAR, 23, 3, &OrdDate,   
       sizeof(OrdDate), &cbOrdDate);  
    ```  
  
3.  <span data-ttu-id="55d7d-113">O segundo estágio da associação de parâmetros é associar as colunas para o parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="55d7d-113">The second stage of parameter binding is to bind the columns for the table-valued parameter.</span></span> <span data-ttu-id="55d7d-114">O foco do parâmetro é definido primeiro para o ordinal do parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="55d7d-114">The parameter focus is first set to the ordinal of the table-valued parameter.</span></span> <span data-ttu-id="55d7d-115">Em seguida, as colunas do valor da tabela são associadas usando SQLBindParameter da mesma maneira como seriam se fossem parâmetros do procedimento armazenado, mas com ordinais de coluna para ParameterNumber.</span><span class="sxs-lookup"><span data-stu-id="55d7d-115">Then columns of the table value are bound by using SQLBindParameter in the same way as they would be if they were parameters of the stored procedure, but with column ordinals for ParameterNumber.</span></span> <span data-ttu-id="55d7d-116">Se houvesse mais parâmetros com valor de tabela, nós definiríamos o foco para cada um deles sucessivamente e associaríamos suas colunas.</span><span class="sxs-lookup"><span data-stu-id="55d7d-116">If there were more table-valued parameters, we would set the focus to each in turn and bind their columns.</span></span> <span data-ttu-id="55d7d-117">Finalmente, o foco de parâmetro é redefinido para 0.</span><span class="sxs-lookup"><span data-stu-id="55d7d-117">Finally, the parameter focus is reset to 0.</span></span>  
  
    ```  
    // Bind columns for the table-valued parameter (param 2).  
    // First set focus on param 2.  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 2, SQL_IS_INTEGER);  
  
    // Col 1 - ProdCode  
    r = SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT,SQL_INTEGER, SQL_C_LONG, 0, 0, ProdCode, sizeof(SQLINTEGER), cbProdCode);  
    // Col 2 - Qty  
    r = SQLBindParameter(hstmt, 2, SQL_PARAM_INPUT,SQL_INTEGER, SQL_C_LONG, 0, 0, Qty, sizeof(SQLINTEGER), cbQty);  
  
    // Reset param focus.  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 0, SQL_IS_INTEGER);  
    ```  
  
4.  <span data-ttu-id="55d7d-118">Popule os buffers de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="55d7d-118">Populate the parameter buffers.</span></span> <span data-ttu-id="55d7d-119">`cbTVP` é definido como o número de linhas a serem enviadas ao servidor.</span><span class="sxs-lookup"><span data-stu-id="55d7d-119">`cbTVP` is set to the number of rows to be sent to the server.</span></span>  
  
    ```  
    // Populate parameters.  
    cbTVP = 0; // Number of rows available for input.  
    strcpy_s((char *) CustCode, sizeof(CustCode), "CUST1"); cbCustCode = SQL_NTS;  
  
    ProdCode[cbTVP] = 1215;cbProdCode[cbTVP] = sizeof(SQLINTEGER);   
    Qty[cbTVP] = 5;cbQty[cbTVP] = sizeof(SQLINTEGER);   
    cbTVP++; // Number of rows available for input  
  
    ProdCode[cbTVP] = 1017;cbProdCode[cbTVP] = sizeof(SQLINTEGER);   
    Qty[cbTVP] = 2;cbQty[cbTVP] = sizeof(SQLINTEGER);   
    cbTVP++; // Number of rows available for input.  
    ```  
  
5.  <span data-ttu-id="55d7d-120">Chame o procedimento:</span><span class="sxs-lookup"><span data-stu-id="55d7d-120">Call the procedure:</span></span>  
  
    ```  
    // Call the procedure.  
    r = SQLExecDirect(hstmt, (SQLCHAR *) "{call TVPOrderEntry(?, ?, ?, ?)}",SQL_NTS);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="55d7d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55d7d-121">See Also</span></span>  
 [<span data-ttu-id="55d7d-122">Exemplos de programação de parâmetros com valor de tabela (ODBC)</span><span class="sxs-lookup"><span data-stu-id="55d7d-122">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
  
  
