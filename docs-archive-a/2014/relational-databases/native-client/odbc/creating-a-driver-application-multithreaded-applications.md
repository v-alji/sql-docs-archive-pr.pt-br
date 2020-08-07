---
title: Aplicativos multithread | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576305"
---
# <a name="multithreaded-applications"></a><span data-ttu-id="23b24-102">Aplicativos multi-threaded</span><span class="sxs-lookup"><span data-stu-id="23b24-102">Multithreaded Applications</span></span>
  <span data-ttu-id="23b24-103">O driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client é um driver multi-threaded.</span><span class="sxs-lookup"><span data-stu-id="23b24-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver is a multithreaded driver.</span></span> <span data-ttu-id="23b24-104">Criar um aplicativo multi-threaded é uma alternativa ao uso de chamadas assíncronas para processar várias chamadas de ODBC.</span><span class="sxs-lookup"><span data-stu-id="23b24-104">Writing a multithreaded application is an alternative to using asynchronous calls to process multiple ODBC calls.</span></span> <span data-ttu-id="23b24-105">Um thread pode fazer uma chamada de ODBC síncrona e outros threads podem ser processados enquanto o primeiro thread está bloqueado esperando a resposta à sua chamada.</span><span class="sxs-lookup"><span data-stu-id="23b24-105">A thread can make a synchronous ODBC call, and other threads can process while the first thread is blocked waiting for the response to its call.</span></span> <span data-ttu-id="23b24-106">Esse modelo é mais eficiente que fazer chamadas assíncronas, pois elimina sobrecarga, como tráfego de rede e a realização repetida de testes de chamadas a funções ODBC para SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="23b24-106">This model is more efficient than making asynchronous calls because it eliminates overhead such as network traffic and making repeated ODBC function calls testing for SQL_STILL_EXECUTING.</span></span>  
  
 <span data-ttu-id="23b24-107">O modo assíncrono ainda é um método eficaz de processamento.</span><span class="sxs-lookup"><span data-stu-id="23b24-107">Asynchronous mode is still an effective method of processing.</span></span> <span data-ttu-id="23b24-108">As melhorias de desempenho de um modelo multi-threaded não são suficientes para justificar a reformulação de aplicativos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="23b24-108">The performance improvements of a multithreaded model are not enough to justify rewriting asynchronous applications.</span></span> <span data-ttu-id="23b24-109">Se os usuários estiverem convertendo aplicativos DB-Library que usam o modelo assíncrono do DB-Library, será mais fácil convertê-los ao modelo assíncrono do ODBC.</span><span class="sxs-lookup"><span data-stu-id="23b24-109">If users are converting DB-Library applications that use the DB-Library asynchronous model, it is easier to convert them to the ODBC asynchronous model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b24-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23b24-110">See Also</span></span>  
 [<span data-ttu-id="23b24-111">Criando um aplicativo de driver ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="23b24-111">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
