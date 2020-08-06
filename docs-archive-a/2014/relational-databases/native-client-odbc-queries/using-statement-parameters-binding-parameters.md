---
title: Parâmetros de associação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- statements [ODBC], parameters
- binding parameters [SQL Server Native Client]
- parameter markers [ODBC]
- unbound parameter markers
- SQLBindParameter function
- ODBC applications, parameters
- bound parameter markers [SQL Server Native Client]
ms.assetid: d6c69739-8f89-475f-a60a-b2f6c06576e2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3402a7efce43d0ce94a20c93504ac1dcb2c7b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569402"
---
# <a name="binding-parameters"></a><span data-ttu-id="af856-102">Associando parâmetros</span><span class="sxs-lookup"><span data-stu-id="af856-102">Binding Parameters</span></span>
  <span data-ttu-id="af856-103">Para que a instrução possa ser executada, cada marcador de parâmetro em uma instrução SQL deve ser associado a uma variável no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="af856-103">Each parameter marker in an SQL statement must be associated, or bound, to a variable in the application before the statement can be executed.</span></span> <span data-ttu-id="af856-104">Isso é feito chamando a função [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) .</span><span class="sxs-lookup"><span data-stu-id="af856-104">This is done by calling the [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) function.</span></span> <span data-ttu-id="af856-105">**SQLBindParameter** descreve a variável do programa (endereço, tipo de dados C e assim por diante) para o driver.</span><span class="sxs-lookup"><span data-stu-id="af856-105">**SQLBindParameter** describes the program variable (address, C data type, and so on) to the driver.</span></span> <span data-ttu-id="af856-106">Ela também identifica o marcador de parâmetro indicando seu valor ordinal e, em seguida, descreve as características do objeto SQL que representa (tipo de dados SQL, precisão e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="af856-106">It also identifies the parameter marker by indicating its ordinal value and then describes the characteristics of the SQL object it represents (SQL data type, precision, and so on).</span></span>

 <span data-ttu-id="af856-107">Marcadores de parâmetro podem ser associados ou reassociados a qualquer momento, antes de uma instrução ser executada.</span><span class="sxs-lookup"><span data-stu-id="af856-107">Parameter markers can be bound or rebound at any time before a statement is executed.</span></span> <span data-ttu-id="af856-108">Uma associação de parâmetro permanece em vigor até ocorrer um dos seguintes eventos:</span><span class="sxs-lookup"><span data-stu-id="af856-108">A parameter binding remains in effect until one of the following occurs:</span></span>

-   <span data-ttu-id="af856-109">Uma chamada para [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) com o parâmetro *Option* definido como SQL_RESET_PARAMS libera todos os parâmetros associados ao identificador da instrução.</span><span class="sxs-lookup"><span data-stu-id="af856-109">A call to [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the *Option* parameter set to SQL_RESET_PARAMS frees all parameters bound to the statement handle.</span></span>

-   <span data-ttu-id="af856-110">Uma chamada para **SQLBindParameter** com *ParameterNumber* definida como o ordinal de um marcador de parâmetro associado libera automaticamente a Associação anterior.</span><span class="sxs-lookup"><span data-stu-id="af856-110">A call to **SQLBindParameter** with *ParameterNumber* set to the ordinal of a bound parameter marker automatically releases the previous binding.</span></span>

 <span data-ttu-id="af856-111">Um aplicativo também pode associar parâmetros a matrizes de variáveis de programa para processar uma instrução SQL em lotes.</span><span class="sxs-lookup"><span data-stu-id="af856-111">An application can also bind parameters to arrays of program variables to process an SQL statement in batches.</span></span> <span data-ttu-id="af856-112">Há dois tipos de associação de matriz:</span><span class="sxs-lookup"><span data-stu-id="af856-112">There are two types of array binding:</span></span>

-   <span data-ttu-id="af856-113">A associação em colunas é feita quando cada um dos parâmetros é associado à sua própria matriz de variáveis.</span><span class="sxs-lookup"><span data-stu-id="af856-113">Column-wise binding is done when each individual parameter is bound to its own array of variables.</span></span>

     <span data-ttu-id="af856-114">A associação de coluna é especificada chamando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) com o *atributo* definido como SQL_ATTR_PARAM_BIND_TYPE e *ValuePtr* definido como SQL_PARAM_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="af856-114">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to SQL_PARAM_BIND_BY_COLUMN.</span></span>

-   <span data-ttu-id="af856-115">A associação em linhas é feita quando todos os parâmetros na instrução SQL são associados como uma unidade a uma matriz de estruturas que contém cada uma das variáveis para os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="af856-115">Row-wise binding is done when all of the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>

     <span data-ttu-id="af856-116">A associação de linha é especificada chamando **SQLSetStmtAttr** com o *atributo* definido como SQL_ATTR_PARAM_BIND_TYPE e *ValuePtr* definido como o tamanho da estrutura que contém as variáveis do programa.</span><span class="sxs-lookup"><span data-stu-id="af856-116">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to the size of the structure holding the program variables.</span></span>

 <span data-ttu-id="af856-117">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client envia parâmetros de cadeia de caracteres ou de caracteres binários para o servidor, ele coloca os valores no comprimento especificado no parâmetro **SQLBindParameter** *colunasize* .</span><span class="sxs-lookup"><span data-stu-id="af856-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sends character or binary string parameters to the server, it pads the values to the length specified in **SQLBindParameter** *ColumnSize* parameter.</span></span> <span data-ttu-id="af856-118">Se um aplicativo ODBC 2. x especificar 0 para *colunasize*, o driver remeterá o valor do parâmetro para a precisão do tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="af856-118">If an ODBC 2.x application specifies 0 for *ColumnSize*, the driver pads the parameter value to the precision of the data type.</span></span> <span data-ttu-id="af856-119">A precisão é 8000 quando houver conexão a servidores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 255 quando houver conexões a versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af856-119">The precision is 8000 when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers, 255 when connected to earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af856-120">*Colunasize* é em bytes para colunas Variant.</span><span class="sxs-lookup"><span data-stu-id="af856-120">*ColumnSize* is in bytes for variant columns.</span></span>

 <span data-ttu-id="af856-121">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte à definição de nomes para parâmetros de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="af856-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports defining names for stored procedure parameters.</span></span> <span data-ttu-id="af856-122">O ODBC 3.5 também introduziu o suporte a parâmetros nomeados usados ao chamar procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af856-122">ODBC 3.5 also introduced support for named parameters used when calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="af856-123">Esse suporte pode ser usado para:</span><span class="sxs-lookup"><span data-stu-id="af856-123">This support can be used to:</span></span>

-   <span data-ttu-id="af856-124">Chamar um procedimento armazenado e fornecer valores para um subconjunto dos parâmetros definidos para o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="af856-124">Call a stored procedure and provide values for a subset of the parameters defined for the stored procedure.</span></span>

-   <span data-ttu-id="af856-125">Especificar os parâmetros no aplicativo em uma ordem diferente daquela especificada quando o procedimento armazenado foi criado.</span><span class="sxs-lookup"><span data-stu-id="af856-125">Specify the parameters in a different order in the application than the order specified when the stored procedure was created.</span></span>

 <span data-ttu-id="af856-126">Só há suporte para parâmetros nomeados ao usar a [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` instrução ou a sequência de escape de chamada ODBC para executar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="af856-126">Named parameters are only supported when using the [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` statement or the ODBC CALL escape sequence to execute a stored procedure.</span></span>

 <span data-ttu-id="af856-127">Se `SQL_DESC_NAME` for definido para um parâmetro de procedimento armazenado, todos os parâmetros de procedimento armazenado na consulta também deverão definir `SQL_DESC_NAME`.</span><span class="sxs-lookup"><span data-stu-id="af856-127">If `SQL_DESC_NAME` is set for a stored procedure parameter, all stored procedure parameters in the query should also set `SQL_DESC_NAME`.</span></span>  <span data-ttu-id="af856-128">Se literais forem usadas em chamadas de procedimento armazenado, em que `SQL_DESC_NAME` os parâmetros foram definidos, os literais deverão usar o formato *' name* = *Value*', em que *Name* é o nome do parâmetro de procedimento armazenado (por exemplo, @p1 ).</span><span class="sxs-lookup"><span data-stu-id="af856-128">If literals are used in stored procedure calls, where parameters have `SQL_DESC_NAME` set, the literals should use the format *'name*=*value*', where *name* is the stored procedure parameter name (for example, @p1).</span></span> <span data-ttu-id="af856-129">Para obter mais informações, consulte [ligando parâmetros por nome (parâmetros nomeados)](https://go.microsoft.com/fwlink/?LinkId=167215).</span><span class="sxs-lookup"><span data-stu-id="af856-129">For more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkId=167215).</span></span>

## <a name="see-also"></a><span data-ttu-id="af856-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af856-130">See Also</span></span>
 [<span data-ttu-id="af856-131">Usando parâmetros de instrução</span><span class="sxs-lookup"><span data-stu-id="af856-131">Using Statement Parameters</span></span>](using-statement-parameters.md)


