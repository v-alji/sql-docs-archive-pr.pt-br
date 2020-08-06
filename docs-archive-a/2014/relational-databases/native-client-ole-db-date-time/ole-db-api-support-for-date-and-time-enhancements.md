---
title: Suporte da API do OLE DB para melhorias de data e hora | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: rothja
ms.author: jroth
ms.openlocfilehash: cdb17f0d2104373ea797ff9403cc417dfaa3d868
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581797"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a><span data-ttu-id="d17aa-102">Suporte da API do OLE DB para melhorias de data e hora</span><span class="sxs-lookup"><span data-stu-id="d17aa-102">OLE DB API Support for Date and Time Enhancements</span></span>
  <span data-ttu-id="d17aa-103">O suporte das APIs do OLE DB a seguir aprimorou os recursos de data/hora.</span><span class="sxs-lookup"><span data-stu-id="d17aa-103">The following OLE DB APIs support enhanced date/time features.</span></span>  
  
|<span data-ttu-id="d17aa-104">Função</span><span class="sxs-lookup"><span data-stu-id="d17aa-104">Function</span></span>|<span data-ttu-id="d17aa-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="d17aa-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d17aa-106">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="d17aa-106">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="d17aa-107">Um sinalizador é adicionado à estrutura DBBINDING para permitir que aplicativos façam discriminação entre valores `datetime`, `datetime2` e `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="d17aa-107">A flag is added in the DBBINDING structure to enable applications to discriminate between `datetime`, `datetime2`, and `smalldatetime` values.</span></span> <span data-ttu-id="d17aa-108">Para obter mais informações, confira [Parâmetro e Metadados do Conjunto de linhas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-108">For more information, see [Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="d17aa-109">IBCPSession::BCPColFmt</span><span class="sxs-lookup"><span data-stu-id="d17aa-109">IBCPSession::BCPColFmt</span></span>|<span data-ttu-id="d17aa-110">Para obter mais informações, consulte [alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-110">For more information, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>|  
|<span data-ttu-id="d17aa-111">ICommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="d17aa-111">ICommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="d17aa-112">Para obter mais informações, confira [Parâmetro e Metadados do Conjunto de Linhas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-112">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="d17aa-113">ICommandWithParameters::SetParameterinfo</span><span class="sxs-lookup"><span data-stu-id="d17aa-113">ICommandWithParameters::SetParameterinfo</span></span>|<span data-ttu-id="d17aa-114">Para obter mais informações, confira [Parâmetro e Metadados do Conjunto de Linhas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-114">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="d17aa-115">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="d17aa-115">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="d17aa-116">Para obter mais informações, confira [Parâmetro e Metadados do Conjunto de Linhas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-116">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="d17aa-117">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="d17aa-117">IColumnsInfo::GetColumnInfo</span></span>|<span data-ttu-id="d17aa-118">Para obter mais informações, confira [Parâmetro e Metadados do Conjunto de Linhas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-118">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="d17aa-119">IDBSchemaRowset::GetRowset</span><span class="sxs-lookup"><span data-stu-id="d17aa-119">IDBSchemaRowset::GetRowset</span></span>|<span data-ttu-id="d17aa-120">Para obter detalhes sobre os conjuntos de linhas dos esquema afetados, confira [Data e hora e conjuntos de linhas do esquema](../native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-120">For details of the affected schema rowsets, see[Date and Time and Schema Rowsets](../native-client-ole-db-rowsets/rowsets.md).</span></span>|  
|<span data-ttu-id="d17aa-121">IRowsetFastLoad</span><span class="sxs-lookup"><span data-stu-id="d17aa-121">IRowsetFastLoad</span></span>|<span data-ttu-id="d17aa-122">Essa interface dá suporte aos novos tipos de data/hora, mas não passou por nenhuma alteração.</span><span class="sxs-lookup"><span data-stu-id="d17aa-122">This interface supports the new date/time types, but there is no change to its interface.</span></span>|  
|<span data-ttu-id="d17aa-123">ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="d17aa-123">ITableDefinition::CreateTable</span></span>|<span data-ttu-id="d17aa-124">Para obter mais informações, confira [Suporte a tipos de dados para aprimoramentos de data e hora do OLE DB](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="d17aa-124">For more information, see [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d17aa-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d17aa-125">See Also</span></span>  
 [<span data-ttu-id="d17aa-126">Melhorias de data e hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d17aa-126">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
