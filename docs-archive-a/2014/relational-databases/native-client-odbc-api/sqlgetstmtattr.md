---
title: SQLGetStmtAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574679"
---
# <a name="sqlgetstmtattr"></a><span data-ttu-id="4ebc6-102">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="4ebc6-102">SQLGetStmtAttr</span></span>
  <span data-ttu-id="4ebc6-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client estende o SQLGetStmtAttr para expor atributos de instrução específicos do driver.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver extends SQLGetStmtAttr to expose driver-specific statement attributes.</span></span>  
  
 <span data-ttu-id="4ebc6-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lista atributos de instrução que sejam de leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lists statement attributes that are both read and write.</span></span> <span data-ttu-id="4ebc6-105">Este tópico lista os atributos de instrução somente leitura.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-105">This topic lists the read only statement attributes.</span></span>  
  
## <a name="sql_sopt_ss_current_command"></a><span data-ttu-id="4ebc6-106">SQL_SOPT_SS_CURRENT_COMMAND</span><span class="sxs-lookup"><span data-stu-id="4ebc6-106">SQL_SOPT_SS_CURRENT_COMMAND</span></span>  
 <span data-ttu-id="4ebc6-107">O atributo SQL_SOPT_SS_CURRENT_COMMAND expõe o comando atual de um lote de comando.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-107">The SQL_SOPT_SS_CURRENT_COMMAND attribute exposes the current command of a command batch.</span></span> <span data-ttu-id="4ebc6-108">O retorno é um inteiro que especifica o local do comando no lote.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-108">The return is an integer that specifies the location of the command in the batch.</span></span> <span data-ttu-id="4ebc6-109">O valor *ValuePtr* é do tipo SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-109">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
## <a name="sql_sopt_ss_nocount_status"></a><span data-ttu-id="4ebc6-110">SQL_SOPT_SS_NOCOUNT_STATUS</span><span class="sxs-lookup"><span data-stu-id="4ebc6-110">SQL_SOPT_SS_NOCOUNT_STATUS</span></span>  
 <span data-ttu-id="4ebc6-111">O atributo SQL_SOPT_SS_NOCOUNT_STATUS indica a configuração atual da opção NOCOUNT, que controla se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relata o número de linhas afetadas por uma instrução quando [SQLRowCount](sqlrowcount.md) é chamado.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-111">The SQL_SOPT_SS_NOCOUNT_STATUS attribute indicates the current setting of the NOCOUNT option, which controls whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reports the numbers of rows affected by a statement when [SQLRowCount](sqlrowcount.md) is called.</span></span> <span data-ttu-id="4ebc6-112">O valor *ValuePtr* é do tipo SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-112">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
|<span data-ttu-id="4ebc6-113">Valor</span><span class="sxs-lookup"><span data-stu-id="4ebc6-113">Value</span></span>|<span data-ttu-id="4ebc6-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="4ebc6-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4ebc6-115">SQL_NC_OFF</span><span class="sxs-lookup"><span data-stu-id="4ebc6-115">SQL_NC_OFF</span></span>|<span data-ttu-id="4ebc6-116">NOCOUNT é OFF.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-116">NOCOUNT is OFF.</span></span> <span data-ttu-id="4ebc6-117">SQLRowCount retorna o número de linhas afetadas.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-117">SQLRowCount returns number of rows affected.</span></span>|  
|<span data-ttu-id="4ebc6-118">SQL_NC_ON</span><span class="sxs-lookup"><span data-stu-id="4ebc6-118">SQL_NC_ON</span></span>|<span data-ttu-id="4ebc6-119">NOCOUNT é ON.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-119">NOCOUNT is ON.</span></span> <span data-ttu-id="4ebc6-120">O número de linhas afetadas não é retornado por SQLRowCount e o valor retornado é 0.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-120">The number of rows affected is not returned by SQLRowCount and the returned value is 0.</span></span>|  
  
 <span data-ttu-id="4ebc6-121">Se SQLRowCount retornar 0, o aplicativo deverá testar SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-121">If SQLRowCount returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="4ebc6-122">Se SQL_NC_ON for retornado, o valor de 0 de SQLRowCount indicará apenas que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não retornou uma contagem de linhas.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-122">If SQL_NC_ON is returned, the value of 0 from SQLRowCount only indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has not returned a row count.</span></span> <span data-ttu-id="4ebc6-123">Se SQL_NC_OFF for retornado, isso significa que NOCOUNT está desativado e que o valor 0 de SQLRowCount indicará que a instrução não afetou nenhuma linha.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-123">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from SQLRowCount indicates that the statement did not affect any rows.</span></span>  
  
 <span data-ttu-id="4ebc6-124">Os aplicativos não deverão exibir o valor de SQLRowCount quando SQL_SOPT_SS_NOCOUNT_STATUS for SQL_NC_OFF.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-124">Applications should not display the value of SQLRowCount when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="4ebc6-125">Lotes grandes ou procedimentos armazenados podem conter várias instruções SET NOCOUNT, portanto não é possível supor que SQL_SOPT_SS_NOCOUNT_STATUS permaneça constante.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-125">Large batches or stored procedures can contain multiple SET NOCOUNT statements, so it cannot be assumed that SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="4ebc6-126">Essa opção deve ser testada cada vez que SQLRowCount retorna 0.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-126">This option should be tested each time SQLRowCount returns 0.</span></span>  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a><span data-ttu-id="4ebc6-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span><span class="sxs-lookup"><span data-stu-id="4ebc6-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span></span>  
 <span data-ttu-id="4ebc6-128">O atributo SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT retorna o texto de mensagem para a solicitação de notificação de consulta.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-128">The SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT attribute returns the message text for the query notification request.</span></span>  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a><span data-ttu-id="4ebc6-129">SQLGetStmtAttr e Parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="4ebc6-129">SQLGetStmtAttr and Table-valued Parameters</span></span>  
 <span data-ttu-id="4ebc6-130">SQLGetStmtAttr pode ser chamado para obter o valor de SQL_SOPT_SS_PARAM_FOCUS no descritor de parâmetro do aplicativo (APD) ao trabalhar com parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="4ebc6-130">SQLGetStmtAttr can be called to get the value of SQL_SOPT_SS_PARAM_FOCUS in the application parameter descriptor (APD) when working with table-valued parameters.</span></span> <span data-ttu-id="4ebc6-131">Para obter mais informações sobre SQL_SOPT_SS_PARAM_FOCUS, consulte [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="4ebc6-131">For more information on SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="4ebc6-132">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4ebc6-132">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebc6-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ebc6-133">See Also</span></span>  
 <span data-ttu-id="4ebc6-134">[Função SQLSetStmtAttr](https://go.microsoft.com/fwlink/?LinkId=59370) </span><span class="sxs-lookup"><span data-stu-id="4ebc6-134">[SQLSetStmtAttr Function](https://go.microsoft.com/fwlink/?LinkId=59370) </span></span>  
 [<span data-ttu-id="4ebc6-135">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="4ebc6-135">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
