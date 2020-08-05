---
title: Melhorias de data e hora (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC]
- ODBC, date/time improvements
ms.assetid: e31d5ca5-2103-498f-954c-1ee93e217186
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ce8f906fc1949a80bfa8e5a541ecf1e83878775
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573943"
---
# <a name="date-and-time-improvements-odbc"></a><span data-ttu-id="a4de7-102">Aprimoramentos de data e hora (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a4de7-102">Date and Time Improvements (ODBC)</span></span>
  <span data-ttu-id="a4de7-103">O [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduziu novos tipos de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="a4de7-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduced new date and time data types.</span></span> <span data-ttu-id="a4de7-104">Esta seção descreve como esses novos tipos são expostos como extensões no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="a4de7-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="a4de7-105">Para obter uma visão geral do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suporte de cliente nativo para os novos tipos de dados de data e hora, consulte [melhorias de data e hora](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="a4de7-105">For an overview of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="a4de7-106">Para obter um exemplo que demonstra o suporte a data/hora ODBC, consulte [usar tipos de data e hora](../native-client-odbc-how-to/use-date-and-time-types.md).</span><span class="sxs-lookup"><span data-stu-id="a4de7-106">For a sample demonstrating ODBC date/time support, see [Use Date and Time Types](../native-client-odbc-how-to/use-date-and-time-types.md).</span></span>  
  
 <span data-ttu-id="a4de7-107">Para obter informações mais genéricas sobre os tipos de dados de data e hora, confira [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a4de7-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4de7-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a4de7-108">In This Section</span></span>  
 [<span data-ttu-id="a4de7-109">Suporte a tipos de dados para aprimoramentos de data e hora do ODBC</span><span class="sxs-lookup"><span data-stu-id="a4de7-109">Data Type Support for ODBC Date and Time Improvements</span></span>](../../relational-databases/native-client-odbc-date-time/data-type-support-for-odbc-date-and-time-improvements.md)  
 <span data-ttu-id="a4de7-110">Fornece informações sobre tipos ODBC que oferecem suporte a tipos de dados de data e hora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4de7-110">Provides information about ODBC types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="a4de7-111">Metadados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a4de7-111">Metadata &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/metadata-odbc.md)  
 <span data-ttu-id="a4de7-112">Descreve informações retornadas nos campos do IPD (descritor de parâmetro de implementação) e do IRD (descritor de linha de implementação), assim como metadados de coluna retornados por `SQLColumns` e `SQLProcedureColumns`.</span><span class="sxs-lookup"><span data-stu-id="a4de7-112">Describes information returned in the implementation parameter descriptor (IPD) and implementation row descriptor (IRD) fields, as well as column metadata returned by `SQLColumns` and `SQLProcedureColumns`.</span></span> <span data-ttu-id="a4de7-113">Também descreve metadados de tipo de dados retornados por `SQLGetTypeInfo`.</span><span class="sxs-lookup"><span data-stu-id="a4de7-113">Also describes data type metadata returned by `SQLGetTypeInfo`.</span></span>  
  
 [<span data-ttu-id="a4de7-114">conversões de tipo de dados DateTime &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a4de7-114">datetime Data Type Conversions &#40;ODBC&#41;</span></span>](datetime-data-type-conversions-odbc.md)  
 <span data-ttu-id="a4de7-115">Descreve como converter entre valores datetime e datetimeoffset.</span><span class="sxs-lookup"><span data-stu-id="a4de7-115">Describes how to convert between datetime and datetimeoffset values.</span></span>  
  
 [<span data-ttu-id="a4de7-116">Suporte a Sql_variant para tipos de data e hora</span><span class="sxs-lookup"><span data-stu-id="a4de7-116">sql_variant Support for Date and Time Types</span></span>](sql-variant-support-for-date-and-time-types.md)  
 <span data-ttu-id="a4de7-117">Descreve o suporte da função SQL_VARIANT para uma funcionalidade de data e hora aprimorada.</span><span class="sxs-lookup"><span data-stu-id="a4de7-117">Describes SQL_VARIANT function support for enhanced date and time functionality.</span></span>  
  
 [<span data-ttu-id="a4de7-118">Alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a4de7-118">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="a4de7-119">Descreve aprimoramentos de data/hora para dar suporte a operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="a4de7-119">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="a4de7-120">Comportamento de tipo de data e hora aprimorado com versões anteriores do SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a4de7-120">Enhanced Date and Time Type Behavior with Previous SQL Server Versions &#40;ODBC&#41;</span></span>](enhanced-date-and-time-type-behavior-with-previous-sql-server-versions-odbc.md)  
 <span data-ttu-id="a4de7-121">Descreve o comportamento esperado quando um aplicativo cliente usando recursos de data e hora aprimorados se comunica com uma versão mais antiga do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quando um cliente compilado com uma versão mais antiga do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client envia comandos para um servidor que dê suporte os recursos de data e hora aprimorados.</span><span class="sxs-lookup"><span data-stu-id="a4de7-121">Describes the expected behavior when a client application using enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
 [<span data-ttu-id="a4de7-122">Suporte à API ODBC para recursos avançados de data e hora</span><span class="sxs-lookup"><span data-stu-id="a4de7-122">ODBC API Support for Enhanced Date and Time Features</span></span>](odbc-api-support-for-enhanced-date-and-time-features.md)  
 <span data-ttu-id="a4de7-123">Lista as ODBC funções que dão suporte a funcionalidade de data e hora aprimorada.</span><span class="sxs-lookup"><span data-stu-id="a4de7-123">Lists the ODBC functions that support enhanced date and time functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4de7-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4de7-124">See Also</span></span>  
 [<span data-ttu-id="a4de7-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a4de7-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
