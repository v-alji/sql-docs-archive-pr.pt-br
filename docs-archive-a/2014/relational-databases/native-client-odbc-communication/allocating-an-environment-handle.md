---
title: Alocando um identificador de ambiente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, environment handles
- ODBC applications, connections
- handles [SQL Server Native Client]
- environment handles [SQLNCLI]
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c655b5e9a406c3e1881c9dd199a92666377918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575106"
---
# <a name="allocating-an-environment-handle"></a><span data-ttu-id="b60a0-102">Alocando um identificador de ambiente</span><span class="sxs-lookup"><span data-stu-id="b60a0-102">Allocating an Environment Handle</span></span>
  <span data-ttu-id="b60a0-103">Antes que um aplicativo possa chamar qualquer função ODBC, ele deve inicializar o ambiente de ODBC e alocar um identificador de ambiente.</span><span class="sxs-lookup"><span data-stu-id="b60a0-103">Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle.</span></span> <span data-ttu-id="b60a0-104">Trata-se do identificador de contexto global e do espaço reservado para os demais identificadores no ODBC.</span><span class="sxs-lookup"><span data-stu-id="b60a0-104">This is the global context handle and placeholder for the other handles in ODBC.</span></span> <span data-ttu-id="b60a0-105">Faça isso chamando **SQLAllocHandle** com o parâmetro *HandleType* definido como SQL_HANDLE_ENV e *InputHandle* definido como SQL_NULL_HANDLE.</span><span class="sxs-lookup"><span data-stu-id="b60a0-105">You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.</span></span>  
  
 <span data-ttu-id="b60a0-106">Depois de alocar o identificador de ambiente, o aplicativo deve definir atributos de ambiente para indicar qual versão das chamadas de função ODBC será usada.</span><span class="sxs-lookup"><span data-stu-id="b60a0-106">After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using.</span></span> <span data-ttu-id="b60a0-107">Para usar o ODBC 3. *x* functions, chame [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) com o parâmetro *Attribute* definido como SQL_ATTR_ODBC_VERSION e *ValuePtr* definido como SQL_OV_ODBC3.</span><span class="sxs-lookup"><span data-stu-id="b60a0-107">To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60a0-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b60a0-108">See Also</span></span>  
 [<span data-ttu-id="b60a0-109">Comunicando-se com SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b60a0-109">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
