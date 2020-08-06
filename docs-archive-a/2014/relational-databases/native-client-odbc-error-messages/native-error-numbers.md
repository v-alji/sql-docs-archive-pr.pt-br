---
title: Números de erro nativos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, native error numbers
- SQL Server Native Client ODBC driver, errors
- native error numbers [SQL Server Native Client]
- messages [ODBC], native error numbers
- errors [ODBC], native error numbers
ms.assetid: 77cbc826-f47f-4803-8e7a-223d6df069b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7232a921027246c3ceb7d0ae1ffd5efbd3672895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679946"
---
# <a name="native-error-numbers"></a><span data-ttu-id="e1bd2-102">Números de erro nativos</span><span class="sxs-lookup"><span data-stu-id="e1bd2-102">Native Error Numbers</span></span>
  <span data-ttu-id="e1bd2-103">Para erros que ocorrem na fonte de dados (retornada por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client retorna o número de erro nativo retornado a ele pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1bd2-103">For errors that occur in the data source (returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns the native error number returned to it by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e1bd2-104">Para erros detectados pelo driver, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client retorna um número de erro nativo de 0.</span><span class="sxs-lookup"><span data-stu-id="e1bd2-104">For errors detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns a native error number of 0.</span></span> <span data-ttu-id="e1bd2-105">Para obter mais informações sobre uma lista de números de erro nativos, consulte a coluna erro da tabela do sistema **sysmessages** no banco de dados **mestre** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1bd2-105">For more information about a list of native error numbers, see the error column of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e1bd2-106">Para obter informações sobre os códigos de erro de estado, consulte [SQLSTATE &#40;códigos de erro ODBC&#41;](sqlstate-odbc-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="e1bd2-106">For information about the state error codes, see [SQLSTATE &#40;ODBC Error Codes&#41;](sqlstate-odbc-error-codes.md).</span></span> <span data-ttu-id="e1bd2-107">Para erros retornados pela Biblioteca de Rede, o número de erro nativo é do software de rede subjacente.</span><span class="sxs-lookup"><span data-stu-id="e1bd2-107">For errors returned by the Net-Library, the native error number is from the underlying network software.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bd2-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1bd2-108">See Also</span></span>  
 [<span data-ttu-id="e1bd2-109">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="e1bd2-109">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
