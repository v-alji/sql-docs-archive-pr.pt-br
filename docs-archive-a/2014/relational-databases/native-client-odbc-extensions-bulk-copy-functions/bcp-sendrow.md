---
title: bcp_sendrow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572050"
---
# <a name="bcp_sendrow"></a><span data-ttu-id="cef78-102">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="cef78-102">bcp_sendrow</span></span>
  <span data-ttu-id="cef78-103">Envia uma linha de dados de variáveis de programa para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cef78-103">Sends a row of data from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef78-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cef78-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cef78-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cef78-105">Arguments</span></span>  
 <span data-ttu-id="cef78-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="cef78-106">*hdbc*</span></span>  
 <span data-ttu-id="cef78-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="cef78-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cef78-108">Retornos</span><span class="sxs-lookup"><span data-stu-id="cef78-108">Returns</span></span>  
 <span data-ttu-id="cef78-109">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="cef78-109">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cef78-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="cef78-110">Remarks</span></span>  
 <span data-ttu-id="cef78-111">A função **bcp_sendrow** compila uma linha de variáveis de programa e a envia para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cef78-111">The **bcp_sendrow** function builds a row from program variables and sends it to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cef78-112">Antes de chamar **bcp_sendrow**, você deve fazer chamadas para [bcp_bind](bcp-bind.md) para especificar as variáveis de programa que contêm os dados da linha.</span><span class="sxs-lookup"><span data-stu-id="cef78-112">Before calling **bcp_sendrow**, you must make calls to [bcp_bind](bcp-bind.md) to specify the program variables containing row data.</span></span>  
  
 <span data-ttu-id="cef78-113">Caso **bcp_bind** seja chamado especificando um tipo de dados longo de comprimento variável, por exemplo um parâmetro *eDataType* de SQLTEXT e um parâmetro *pData* diferente de NULL, **bcp_sendrow** envia todo o valor de dados, exatamente como faz para qualquer outro tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="cef78-113">If **bcp_bind** is called specifying a long, variable-length data type, for example, an *eDataType* parameter of SQLTEXT and a nonNULL *pData* parameter, **bcp_sendrow** sends the entiredata value, just as it does for any other data type.</span></span> <span data-ttu-id="cef78-114">Entretanto, se **bcp_bind** tiver um parâmetro *pData* igual a NULL, **bcp_sendrow** retorna o controle para o aplicativo imediatamente após todas as colunas com os dados especificados serem enviadas ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cef78-114">If, however, **bcp_bind** has a NULL *pData* parameter, **bcp_sendrow** returns control to the application immediately after all columns with data specified are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cef78-115">Então, o aplicativo pode chamar [bcp_moretext](bcp-moretext.md) repetidamente para enviar os dados longos de comprimento variável para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], uma parte de cada vez.</span><span class="sxs-lookup"><span data-stu-id="cef78-115">The application can then call [bcp_moretext](bcp-moretext.md) repeatedly to send the long, variable-length data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a chunk at a time.</span></span> <span data-ttu-id="cef78-116">Para obter mais informações, consulte [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="cef78-116">For more information, see [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="cef78-117">Quando **bcp_sendrow** for usado para copiar linhas em massa de variáveis do programa para tabelas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , as linhas são confirmadas somente quando o usuário chamar [bcp_batch](bcp-batch.md) ou [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="cef78-117">When **bcp_sendrow** is used to bulk copy rows from program variables into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, rows are committed only when the user calls [bcp_batch](bcp-batch.md) or [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="cef78-118">O usuário pode escolher chamar **bcp_batch** uma vez a cada *n* linhas ou quando houver uma pausa entre períodos de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="cef78-118">The user can choose to call **bcp_batch** once every *n* rows or when there is a lull between periods of incoming data.</span></span> <span data-ttu-id="cef78-119">Se **bcp_batch** nunca for chamado, as linhas serão confirmadas quando **bcp_done** for chamado.</span><span class="sxs-lookup"><span data-stu-id="cef78-119">If **bcp_batch** is never called, the rows are committed when **bcp_done** is called.</span></span>  
  
 <span data-ttu-id="cef78-120">Para obter informações sobre uma alteração significativa na cópia em massa a partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , consulte [executando operações de cópia em massa &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cef78-120">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef78-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cef78-121">See Also</span></span>  
 [<span data-ttu-id="cef78-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cef78-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
