---
title: SQLSTATE (códigos de erro ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- ODBC error handling, cause information
- messages [ODBC], cause information
- SQLSTATEs
- errors [ODBC], cause information
ms.assetid: 84cce528-edb0-473f-a85f-3eb87fbe2cf3
author: rothja
ms.author: jroth
ms.openlocfilehash: ff3ec0a5cdc8f24f34e42849f7c8f6d1d9d41478
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568544"
---
# <a name="sqlstate-odbc-error-codes"></a><span data-ttu-id="d620e-102">SQLSTATE (códigos de erro ODBC)</span><span class="sxs-lookup"><span data-stu-id="d620e-102">SQLSTATE (ODBC Error Codes)</span></span>
  <span data-ttu-id="d620e-103">SQLSTATE fornece informações detalhadas sobre a causa de um aviso ou um erro.</span><span class="sxs-lookup"><span data-stu-id="d620e-103">SQLSTATE provides detailed information about the cause of a warning or error.</span></span> <span data-ttu-id="d620e-104">Para erros que ocorrem na fonte de dados detectada e retornada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client mapeia o número de erro nativo retornado para o SQLSTATE apropriado.</span><span class="sxs-lookup"><span data-stu-id="d620e-104">For errors that occur in the data source detected and returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps the returned native error number to the appropriate SQLSTATE.</span></span> <span data-ttu-id="d620e-105">Se um número de erro nativo não tiver um código de erro ODBC para mapear, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client retornará SQLSTATE 42000 ("erro de sintaxe ou violação de acesso").</span><span class="sxs-lookup"><span data-stu-id="d620e-105">If a native error number does not have an ODBC error code to map to, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQLSTATE 42000 ("syntax error or access violation").</span></span> <span data-ttu-id="d620e-106">Para erros detectados pelo driver, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client gera o SQLSTATE apropriado.</span><span class="sxs-lookup"><span data-stu-id="d620e-106">For errors that are detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates the appropriate SQLSTATE.</span></span>  
  
 <span data-ttu-id="d620e-107">Para obter mais informações sobre códigos de erro de estado, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d620e-107">For more information about the state error codes, see the following topics:</span></span>  
  
-   [<span data-ttu-id="d620e-108">Apêndice A: Códigos de erro ODBC</span><span class="sxs-lookup"><span data-stu-id="d620e-108">Appendix A: ODBC Error Codes</span></span>](https://go.microsoft.com/fwlink/?LinkId=89356)  
  
-   [<span data-ttu-id="d620e-109">Mapeamentos de SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="d620e-109">SQLSTATE Mappings</span></span>](https://go.microsoft.com/fwlink/?LinkId=89355)  
  
## <a name="see-also"></a><span data-ttu-id="d620e-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d620e-110">See Also</span></span>  
 [<span data-ttu-id="d620e-111">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="d620e-111">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
