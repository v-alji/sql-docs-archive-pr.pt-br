---
title: Aprimoramentos de data e hora (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB]
- OLE DB, date/time improvements
ms.assetid: 71614aaf-0fa4-4fe0-b522-68e2e0b66f43
author: rothja
ms.author: jroth
ms.openlocfilehash: 16bb9e98691aea829eb71a16ddabddb371d7bcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684707"
---
# <a name="date-and-time-improvements-ole-db"></a><span data-ttu-id="e056b-102">Melhorias de data e hora (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e056b-102">Date and Time Improvements (OLE DB)</span></span>
  <span data-ttu-id="e056b-103">O [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] apresenta novos tipos de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="e056b-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduces new date and time data types.</span></span> <span data-ttu-id="e056b-104">Esta seção descreve como esses novos tipos são expostos como extensões no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="e056b-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="e056b-105">Para obter uma visão geral do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suporte de cliente nativo para os novos tipos de dados de data e hora, consulte [melhorias de data e hora](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="e056b-105">For an overview of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="e056b-106">Para ver um exemplo, confira [Usar os recursos aprimorados de data e hora do &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e056b-106">For a sample, see [Use Enhanced Date and Time Features &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span></span>  
  
 <span data-ttu-id="e056b-107">Para obter informações mais genéricas sobre os tipos de dados de data e hora, confira [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e056b-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e056b-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e056b-108">In This Section</span></span>  
 [<span data-ttu-id="e056b-109">Suporte a tipos de dados para melhorias de data e hora do OLE DB</span><span class="sxs-lookup"><span data-stu-id="e056b-109">Data Type Support for OLE DB Date and Time Improvements</span></span>](../../relational-databases/native-client-ole-db-date-time/data-type-support-for-ole-db-date-and-time-improvements.md)  
 <span data-ttu-id="e056b-110">Fornece informações sobre os tipos de OLE DB ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente nativo) que dão suporte aos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="e056b-110">Provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="e056b-111">Metadados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e056b-111">Metadata &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/metadata-ole-db.md)  
 <span data-ttu-id="e056b-112">Contém informações sobre a estrutura DBBINDING,,, `ICommandWithParameters::GetParameterInfo` `ICommandWithParameters::SetParameterInfo` `IColumnsRowset::GetColumnsRowset` e I `ColumnsInfo::GetColumnInfo` . Também fornece informações sobre atualizações para OLE DB conjuntos de linhas de esquema.</span><span class="sxs-lookup"><span data-stu-id="e056b-112">Contains information about the DBBINDING structure, `ICommandWithParameters::GetParameterInfo`, `ICommandWithParameters::SetParameterInfo`, `IColumnsRowset::GetColumnsRowset`, and I`ColumnsInfo::GetColumnInfo`. Also provides information about updates to OLE DB schema rowsets.</span></span>  
  
 [<span data-ttu-id="e056b-113">Associações e conversões &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e056b-113">Bindings and Conversions &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-date-time/conversions-ole-db.md)  
 <span data-ttu-id="e056b-114">Descreve as regras para conversão entre servidor e cliente de tipos de data novos e existentes.</span><span class="sxs-lookup"><span data-stu-id="e056b-114">Describes the rules for conversion between server and client for both existing and new date types.</span></span>  
  
 [<span data-ttu-id="e056b-115">Alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e056b-115">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="e056b-116">Descreve aprimoramentos de data/hora para dar suporte a operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="e056b-116">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="e056b-117">Suporte da API do OLE DB para aprimoramentos de data e hora</span><span class="sxs-lookup"><span data-stu-id="e056b-117">OLE DB API Support for Date and Time Enhancements</span></span>](ole-db-api-support-for-date-and-time-enhancements.md)  
 <span data-ttu-id="e056b-118">Descreve as APIs OLE DB que dão suporte a recursos de data/hora aprimorados.</span><span class="sxs-lookup"><span data-stu-id="e056b-118">Describes the OLE DB APIs that support enhanced date/time features.</span></span>  
  
 [<span data-ttu-id="e056b-119">Comparações de IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="e056b-119">Comparability for IRowsetFind</span></span>](../../relational-databases/native-client-ole-db-date-time/comparability-for-irowsetfind.md)  
 <span data-ttu-id="e056b-120">Descreve os tipos de data/hora e `IRowsetFind`.</span><span class="sxs-lookup"><span data-stu-id="e056b-120">Describes date/time types and `IRowsetFind`.</span></span>  
  
 [<span data-ttu-id="e056b-121">Novos recursos de data e hora com versões anteriores do SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e056b-121">New Date and Time Features with Previous SQL Server Versions &#40;OLE DB&#41;</span></span>](new-date-and-time-features-with-previous-sql-server-versions-ole-db.md)  
 <span data-ttu-id="e056b-122">Descreve o comportamento esperado quando um aplicativo cliente que usa recursos de data e hora aprimorados se comunica com uma versão mais antiga do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quando um cliente compilado com uma versão mais antiga do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client envia comandos para um servidor que dá suporte a recursos de data e hora aprimorados.</span><span class="sxs-lookup"><span data-stu-id="e056b-122">Describes the expected behavior when a client application that uses enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e056b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e056b-123">See Also</span></span>  
 [<span data-ttu-id="e056b-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e056b-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
