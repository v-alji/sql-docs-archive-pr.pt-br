---
title: Processando resultados de procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], results
ms.assetid: 788ef2a4-17de-4526-960b-46bf29aafc9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 5f37a6d8beff88748fa944293bd67f449d29eff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685624"
---
# <a name="processing-stored-procedure-results"></a><span data-ttu-id="ea10a-102">Processando resultados do procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="ea10a-102">Processing Stored Procedure Results</span></span>
  <span data-ttu-id="ea10a-103">Os procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] têm quatro mecanismos usados para retornar dados:</span><span class="sxs-lookup"><span data-stu-id="ea10a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures have four mechanisms used to return data:</span></span>  
  
-   <span data-ttu-id="ea10a-104">Cada instrução SELECT no procedimento gera um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ea10a-104">Each SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="ea10a-105">O procedimento pode retornar dados através de parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="ea10a-105">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="ea10a-106">Um parâmetro de saída de cursor pode devolver um cursor de servidor [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea10a-106">A cursor output parameter can pass back a [!INCLUDE[tsql](../../includes/tsql-md.md)] server cursor.</span></span>  
  
-   <span data-ttu-id="ea10a-107">O procedimento pode ter um código de retorno de inteiro.</span><span class="sxs-lookup"><span data-stu-id="ea10a-107">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="ea10a-108">Os aplicativos devem conseguir tratar todas essas saídas dos procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="ea10a-108">Applications must be able to handle all these outputs from stored procedures.</span></span> <span data-ttu-id="ea10a-109">A instrução CALL ou EXECUTE deve incluir marcadores de parâmetro para o código de retorno e parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="ea10a-109">The CALL or EXECUTE statement should include parameter markers for the return code and output parameters.</span></span> <span data-ttu-id="ea10a-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) para associá-los todos como parâmetros de saída e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client irá transferir os valores de saída para as variáveis associadas.</span><span class="sxs-lookup"><span data-stu-id="ea10a-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind them all as output parameters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will transfer the output values to the bound variables.</span></span> <span data-ttu-id="ea10a-111">Os parâmetros de saída e os códigos de retorno são os últimos itens retornados para o cliente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; eles não são retornados para o aplicativo até que [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) retorne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="ea10a-111">Output parameters and return codes are the last items returned to the client by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they are not returned to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="ea10a-112">O ODBC não dá suporte à associação de parâmetros de cursor do [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea10a-112">ODBC does not support binding [!INCLUDE[tsql](../../includes/tsql-md.md)] cursor parameters.</span></span> <span data-ttu-id="ea10a-113">Como todos os parâmetros de saída devem ser associados antes de executar um procedimento, todos os procedimentos armazenados do [!INCLUDE[tsql](../../includes/tsql-md.md)] que contêm um parâmetro de cursor de saída não podem ser chamados por aplicativos ODBC.</span><span class="sxs-lookup"><span data-stu-id="ea10a-113">Because all output parameters must be bound before executing a procedure, any [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure that contains an output cursor parameter cannot be called by ODBC applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea10a-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea10a-114">See Also</span></span>  
 [<span data-ttu-id="ea10a-115">Executando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ea10a-115">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
