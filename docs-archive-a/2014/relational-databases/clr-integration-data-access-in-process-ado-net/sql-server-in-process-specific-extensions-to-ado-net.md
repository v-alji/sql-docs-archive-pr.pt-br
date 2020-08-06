---
title: SQL Server extensões específicas em processo para ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
ms.openlocfilehash: 37d8aedc1d8f93739c2e9386665adfc67b43e312
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583116"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a><span data-ttu-id="5bb46-102">Extensões específicas em processo do SQL Server para o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5bb46-102">SQL Server In-Process Specific Extensions to ADO.NET</span></span>
  <span data-ttu-id="5bb46-103">Há quatro extensões funcionais principais para o ADO.NET que se destinam especificamente ao uso em processo.</span><span class="sxs-lookup"><span data-stu-id="5bb46-103">There are four main functional extensions to ADO.NET that are specifically for in-process use.</span></span> <span data-ttu-id="5bb46-104">Os tópicos a seguir abrangem essas extensões detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="5bb46-104">The following topics will cover these extensions in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bb46-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5bb46-105">In This Section</span></span>  
 [<span data-ttu-id="5bb46-106">Objeto SqlContext</span><span class="sxs-lookup"><span data-stu-id="5bb46-106">SqlContext Object</span></span>](sqlcontext-object.md)  
 <span data-ttu-id="5bb46-107">Esta classe fornece acesso às outras extensões abstraindo o contexto de um chamador de uma rotina do SQL Server que executa código gerenciado em processo.</span><span class="sxs-lookup"><span data-stu-id="5bb46-107">This class provides access to the other extensions by abstracting the context of a caller of a SQL Server routine that executes managed code in-process.</span></span>  
  
 [<span data-ttu-id="5bb46-108">Objeto SqlPipe</span><span class="sxs-lookup"><span data-stu-id="5bb46-108">SqlPipe Object</span></span>](sqlpipe-object.md)  
 <span data-ttu-id="5bb46-109">Esta classe contém rotinas para enviar mensagens e resultados tabulares ao cliente.</span><span class="sxs-lookup"><span data-stu-id="5bb46-109">This class contains routines to send tabular results and messages to the client.</span></span>  
  
 [<span data-ttu-id="5bb46-110">Objeto SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="5bb46-110">SqlTriggerContext Object</span></span>](sqltriggercontext-object.md)  
 <span data-ttu-id="5bb46-111">Esta classe fornece informações sobre o contexto no qual um gatilho é executado.</span><span class="sxs-lookup"><span data-stu-id="5bb46-111">This class provides information on the context in which a trigger is run.</span></span>  
  
 [<span data-ttu-id="5bb46-112">Objeto SqlDataRecord</span><span class="sxs-lookup"><span data-stu-id="5bb46-112">SqlDataRecord Object</span></span>](sqldatarecord-object.md)  
 <span data-ttu-id="5bb46-113">A classe SqlDataRecord representa uma única linha de dados, juntamente com seus metadados relacionados, e permite que procedimentos armazenados retornem conjuntos de resultados personalizados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="5bb46-113">The SqlDataRecord class represents a single row of data, along with its related metadata, and allows stored procedures to return custom result sets to the client.</span></span>  
  
  
