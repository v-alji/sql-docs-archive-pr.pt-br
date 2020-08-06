---
title: SQLSetEnvAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
author: rothja
ms.author: jroth
ms.openlocfilehash: f0dbd4d01de9ca769c46a93f810f0149f5b86981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582989"
---
# <a name="sqlsetenvattr"></a><span data-ttu-id="117a2-102">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="117a2-102">SQLSetEnvAttr</span></span>
  <span data-ttu-id="117a2-103">A [referência do programador de ODBC](https://go.microsoft.com/fwlink/?LinkId=45250) define como os drivers de ODBC devem interpretar as especificações de atributos de **SQLSetEnvAttr** de aplicativos criados para a API do ODBC 2.*x* ou do ODBC 3.*x* .</span><span class="sxs-lookup"><span data-stu-id="117a2-103">The [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) defines how ODBC drivers should interpret the **SQLSetEnvAttr** attribute specifications from applications written to either the ODBC 2.*x* or ODBC 3.*x* API.</span></span> <span data-ttu-id="117a2-104">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client obedece a essas regras.</span><span class="sxs-lookup"><span data-stu-id="117a2-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with those rules.</span></span>  
  
 <span data-ttu-id="117a2-105">Um dos atributos controlados por **SQLSetEnvAttr** é se o pool de conexões deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="117a2-105">One of the attributes controlled by **SQLSetEnvAttr** is whether connection pooling is to be used.</span></span> <span data-ttu-id="117a2-106">Se o pool de conexões for usado com o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, o parâmetro *DriverCompletion* deverá ser definido como SQL_DRIVER_NOPROMPT ao fazer a conexão com [SQLDriverConnect](sqldriverconnect.md) ou **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="117a2-106">If connection pooling is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, the *DriverCompletion* parameter must be set to SQL_DRIVER_NOPROMPT when connecting with either [SQLDriverConnect](sqldriverconnect.md) or **SQLConnect**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117a2-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="117a2-107">See Also</span></span>  
 <span data-ttu-id="117a2-108">[Função SQLSetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=59369) </span><span class="sxs-lookup"><span data-stu-id="117a2-108">[SQLSetEnvAttr Function](https://go.microsoft.com/fwlink/?LinkId=59369) </span></span>  
 [<span data-ttu-id="117a2-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="117a2-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
