---
title: bcp_batch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_batch
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_batch function
ms.assetid: 0bda489e-86bc-4a7e-80f6-96047e03f281
author: rothja
ms.author: jroth
ms.openlocfilehash: 24cdf6e2934c2b80a55d8fa1fcc572a976b636ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573941"
---
# <a name="bcp_batch"></a><span data-ttu-id="30cf8-102">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="30cf8-102">bcp_batch</span></span>
  <span data-ttu-id="30cf8-103">Confirma todas as linhas copiadas em massa anteriormente de variáveis de programa e enviadas para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="30cf8-103">Commits all rows previously bulk copied from program variables and sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30cf8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="30cf8-104">Syntax</span></span>  
  
```  
  
DBINT bcp_batch (HDBC  
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="30cf8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="30cf8-105">Arguments</span></span>  
 <span data-ttu-id="30cf8-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="30cf8-106">*hdbc*</span></span>  
 <span data-ttu-id="30cf8-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="30cf8-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="30cf8-108">Retornos</span><span class="sxs-lookup"><span data-stu-id="30cf8-108">Returns</span></span>  
 <span data-ttu-id="30cf8-109">O número de linhas salvas depois da última chamada para **bcp_batch**, ou -1 em caso de erro.</span><span class="sxs-lookup"><span data-stu-id="30cf8-109">The number of rows saved after the last call to **bcp_batch**, or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30cf8-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="30cf8-110">Remarks</span></span>  
 <span data-ttu-id="30cf8-111">Lotes de cópias em massa definem transações.</span><span class="sxs-lookup"><span data-stu-id="30cf8-111">Bulk copy batches define transactions.</span></span> <span data-ttu-id="30cf8-112">Quando um aplicativo usar [bcp_bind](bcp-bind.md) e **bcp_sendrow** para copiar linhas em massa de variáveis de programa para tabelas do SQL Server, as linhas serão confirmadas apenas quando o programa chamar **bcp_batch** ou [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="30cf8-112">When an application uses [bcp_bind](bcp-bind.md) and **bcp_sendrow** to bulk copy rows from program variables to SQL Server tables, the rows are committed only when the program calls **bcp_batch** or [bcp_done](bcp-done.md).</span></span>  
  
 <span data-ttu-id="30cf8-113">Você poderá chamar **bcp_batch** uma vez a cada *n* linhas ou quando houver uma pausa nos dados de entrada (como em um aplicativo de telemetria).</span><span class="sxs-lookup"><span data-stu-id="30cf8-113">You can call **bcp_batch** once every *n* rows or when there is a lull in incoming data (as in a telemetry application).</span></span> <span data-ttu-id="30cf8-114">Se um aplicativo não chamar **bcp_batch** , as linhas copiadas em massa serão confirmadas apenas quando **bcp_done** for chamado.</span><span class="sxs-lookup"><span data-stu-id="30cf8-114">If an application does not call **bcp_batch** the bulk copied rows are committed only when **bcp_done** is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30cf8-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="30cf8-115">See Also</span></span>  
 [<span data-ttu-id="30cf8-116">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="30cf8-116">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
