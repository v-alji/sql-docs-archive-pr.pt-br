---
title: Rastreando e reproduzindo eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7f0d570c70ef1cba080217e6c3a0f9b6055a4d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680864"
---
# <a name="tracing-and-replaying-events"></a><span data-ttu-id="c6b4d-102">Rastreando e reproduzindo eventos</span><span class="sxs-lookup"><span data-stu-id="c6b4d-102">Tracing and Replaying Events</span></span>
  <span data-ttu-id="c6b4d-103">No SMO, os objetos `Trace` e `Replay` no namespace <xref:Microsoft.SqlServer.Management.Trace> fornecem acesso de programação à funcionalidade [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], usada para monitorar uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b4d-103">In SMO, the `Trace` and `Replay` objects in the <xref:Microsoft.SqlServer.Management.Trace> namespace provide programmatic access to the [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] functionality, which is used for monitoring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c6b4d-104">Você pode capturar e salvar dados sobre cada evento em um arquivo ou tabela para análise posterior.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-104">You can capture and save data about each event to a file or table to analyze later.</span></span> <span data-ttu-id="c6b4d-105">Por exemplo, é possível monitorar um ambiente de produção para observar quais procedimentos estão impedindo o desempenho devido à lentidão na execução.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-105">For example, you can monitor a production environment to see which procedures are impeding performance by executing too slowly.</span></span>  
  
 <span data-ttu-id="c6b4d-106">Os objetos `Trace` e `Replay` fornecem um conjunto de objetos que podem ser usados para criar rastreamentos em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b4d-106">The `Trace` and `Replay` objects provide a set of objects that can be used to create traces on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6b4d-107">Esses objetos podem ser usados de dentro dos seus aplicativos para criar rastreamentos manualmente para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b4d-107">These objects can be used from within your own applications to create traces manually for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c6b4d-108">Além disso, os objetos `Trace` de SMO podem ser usados para ler arquivos e tabelas de Rastreamento do SQL que foram criadas monitorando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou o log de DTS.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-108">Additionally, SMO `Trace` objects can be used to read SQL Trace files and tables that were created by monitoring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], or DTS logging.</span></span>  
  
 <span data-ttu-id="c6b4d-109">Os objetos `Trace` de SMO permitem que você execute estas funções:</span><span class="sxs-lookup"><span data-stu-id="c6b4d-109">SMO `Trace` objects let you perform the following functions:</span></span>  
  
-   <span data-ttu-id="c6b4d-110">Criar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-110">Create a trace.</span></span>  
  
-   <span data-ttu-id="c6b4d-111">Definir os filtros no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-111">Set filters on the trace.</span></span>  
  
-   <span data-ttu-id="c6b4d-112">Definir os eventos que estão sendo localizados.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-112">Set the events that are being traced.</span></span>  
  
-   <span data-ttu-id="c6b4d-113">Interromper ou iniciar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-113">Stop or start a trace.</span></span>  
  
-   <span data-ttu-id="c6b4d-114">Ler arquivos e tabelas de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-114">Read trace files, and trace tables.</span></span>  
  
-   <span data-ttu-id="c6b4d-115">Obter informações sobre eventos em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-115">Get information about events on a trace.</span></span>  
  
-   <span data-ttu-id="c6b4d-116">Obter informações sobre filtros em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-116">Get information about filters on a trace.</span></span>  
  
-   <span data-ttu-id="c6b4d-117">Manipular dados de rastreamento programaticamente.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-117">Manipulate trace data programmatically.</span></span>  
  
-   <span data-ttu-id="c6b4d-118">Escrever tabelas e arquivos de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-118">Write trace tables and trace files.</span></span>  
  
-   <span data-ttu-id="c6b4d-119">Reproduzir arquivos ou tabelas de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-119">Replay trace files or trace tables.</span></span>  
  
 <span data-ttu-id="c6b4d-120">Os dados de rastreamento dos `Trace` `Replay` objetos e podem ser usados pelo aplicativo Smo ou podem ser examinados manualmente usando [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="c6b4d-120">The trace data from the `Trace` and `Replay` objects can be used by the SMO application, or it can be examined manually by using [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span></span> <span data-ttu-id="c6b4d-121">Os dados de rastreamento também são compatíveis com os procedimentos armazenados [SQL Trace](../../sql-trace/sql-trace.md) que também fornecem capacidades de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-121">The trace data is also compatible with the [SQL Trace](../../sql-trace/sql-trace.md) stored procedures that also provide tracing capabilities.</span></span>  
  
 <span data-ttu-id="c6b4d-122">Os objetos de rastreamento SMO residem no namespace <xref:Microsoft.SqlServer.Management.Trace>, que requer uma referência ao arquivo Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-122">The SMO trace objects reside in the <xref:Microsoft.SqlServer.Management.Trace> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
 <span data-ttu-id="c6b4d-123">Os objetos `Trace` e `Replay` exigem um objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> para estabelecer uma conexão com a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b4d-123">The `Trace` and `Replay` objects require a <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> object to establish a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6b4d-124">O objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> reside no namespace <xref:Microsoft.SqlServer.Management.Common>, que requer uma referência ao arquivo Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-124">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object resides in the <xref:Microsoft.SqlServer.Management.Common> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6b4d-125">Os objetos `Trace` e `Replay` não têm suporte em uma plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c6b4d-125">The `Trace` and `Replay` objects are not supported on a 64-bit platform.</span></span>  
  
  
