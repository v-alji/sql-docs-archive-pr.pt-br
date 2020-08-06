---
title: Tipos de dados de instância Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678913"
---
# <a name="oracle-cdc-instance-data-types"></a><span data-ttu-id="582d6-102">Tipos de dados de instância Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="582d6-102">Oracle CDC Instance Data Types</span></span>
  <span data-ttu-id="582d6-103">A Instância Oracle CDC oferece suporte à maioria dos tipos de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="582d6-103">The Oracle CDC Instance supports most Oracle data types.</span></span> <span data-ttu-id="582d6-104">As seções a seguir descrevem os tipos de dados com suporte e sem suporte.</span><span class="sxs-lookup"><span data-stu-id="582d6-104">The following sections describe the supported data types and the non-supported data types.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="582d6-105">Tipos de dados com suporte</span><span class="sxs-lookup"><span data-stu-id="582d6-105">Supported Data Types</span></span>  
 <span data-ttu-id="582d6-106">A tabela a seguir descreve os tipos de dados Oracle que podem ser capturados e o seu mapeamento padrão para tipos de dados do SQL Server nas tabelas de alteração.</span><span class="sxs-lookup"><span data-stu-id="582d6-106">The following table describes the Oracle data types that can be captured and their default mapping to SQL Server data types in the change tables.</span></span> <span data-ttu-id="582d6-107">Ao adicionar uma instância de captura para uma tabela do Oracle de origem, você pode substituir alguns destes mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="582d6-107">When adding a capture instance for a source Oracle table, you can override some of these mappings.</span></span>  
  
|<span data-ttu-id="582d6-108">Tipo de dados de banco de dados Oracle</span><span class="sxs-lookup"><span data-stu-id="582d6-108">Oracle Database Data Type</span></span>|<span data-ttu-id="582d6-109">Tipo de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="582d6-109">SQL Server Data Type</span></span>|  
|-------------------------------|--------------------------|  
|<span data-ttu-id="582d6-110">BINARY_FLOAT</span><span class="sxs-lookup"><span data-stu-id="582d6-110">BINARY_FLOAT</span></span>|<span data-ttu-id="582d6-111">real</span><span class="sxs-lookup"><span data-stu-id="582d6-111">REAL</span></span>|  
|<span data-ttu-id="582d6-112">BINARY_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="582d6-112">BINARY_DOUBLE</span></span>|<span data-ttu-id="582d6-113">FLOAT</span><span class="sxs-lookup"><span data-stu-id="582d6-113">FLOAT</span></span>|  
|<span data-ttu-id="582d6-114">CHAR</span><span class="sxs-lookup"><span data-stu-id="582d6-114">CHAR</span></span>|<span data-ttu-id="582d6-115">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="582d6-115">NVARCHAR</span></span>|  
|<span data-ttu-id="582d6-116">DATE</span><span class="sxs-lookup"><span data-stu-id="582d6-116">DATE</span></span>|<span data-ttu-id="582d6-117">DATETIME</span><span class="sxs-lookup"><span data-stu-id="582d6-117">DATETIME</span></span>|  
|<span data-ttu-id="582d6-118">FLOAT</span><span class="sxs-lookup"><span data-stu-id="582d6-118">FLOAT</span></span>|<span data-ttu-id="582d6-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="582d6-119">FLOAT</span></span>|  
|<span data-ttu-id="582d6-120">INT</span><span class="sxs-lookup"><span data-stu-id="582d6-120">INT</span></span>|<span data-ttu-id="582d6-121">NUMERIC (38)</span><span class="sxs-lookup"><span data-stu-id="582d6-121">NUMERIC (38)</span></span>|  
|<span data-ttu-id="582d6-122">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="582d6-122">INTERVAL</span></span>|<span data-ttu-id="582d6-123">DATETIME</span><span class="sxs-lookup"><span data-stu-id="582d6-123">DATETIME</span></span>|  
|<span data-ttu-id="582d6-124">NCHAR</span><span class="sxs-lookup"><span data-stu-id="582d6-124">NCHAR</span></span>|<span data-ttu-id="582d6-125">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="582d6-125">NVARCHAR</span></span>|  
|<span data-ttu-id="582d6-126">NUMBER</span><span class="sxs-lookup"><span data-stu-id="582d6-126">NUMBER</span></span>|<span data-ttu-id="582d6-127">FLOAT</span><span class="sxs-lookup"><span data-stu-id="582d6-127">FLOAT</span></span>|  
|<span data-ttu-id="582d6-128">NAVARCHAR2</span><span class="sxs-lookup"><span data-stu-id="582d6-128">NAVARCHAR2</span></span>|<span data-ttu-id="582d6-129">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="582d6-129">NVARCHAR</span></span>|  
|<span data-ttu-id="582d6-130">RAW</span><span class="sxs-lookup"><span data-stu-id="582d6-130">RAW</span></span>|<span data-ttu-id="582d6-131">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="582d6-131">VARBINARY</span></span>|  
|<span data-ttu-id="582d6-132">real</span><span class="sxs-lookup"><span data-stu-id="582d6-132">REAL</span></span>|<span data-ttu-id="582d6-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="582d6-133">FLOAT</span></span>|  
|<span data-ttu-id="582d6-134">timestamp</span><span class="sxs-lookup"><span data-stu-id="582d6-134">TIMESTAMP</span></span>|<span data-ttu-id="582d6-135">DATETIME2</span><span class="sxs-lookup"><span data-stu-id="582d6-135">DATETIME2</span></span>|  
|<span data-ttu-id="582d6-136">TIMESTAMP WITH TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="582d6-136">TIMESTAMP WITH TIME ZONE</span></span>|<span data-ttu-id="582d6-137">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="582d6-137">VARCHAR (37)</span></span>|  
|<span data-ttu-id="582d6-138">TIMESTAMP WITH LOCAL TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="582d6-138">TIMESTAMP WITH LOCAL TIME ZONE</span></span>|<span data-ttu-id="582d6-139">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="582d6-139">VARCHAR (37)</span></span>|  
|<span data-ttu-id="582d6-140">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="582d6-140">VARCHAR2</span></span>|<span data-ttu-id="582d6-141">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="582d6-141">VARCHAR</span></span>|  
|<span data-ttu-id="582d6-142">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="582d6-142">XMLTYPE</span></span>|<span data-ttu-id="582d6-143">NVARCHAR (MAX)</span><span class="sxs-lookup"><span data-stu-id="582d6-143">NVARCHAR (MAX)</span></span>|  
  
## <a name="non-supported-data-types"></a><span data-ttu-id="582d6-144">Tipos de dados sem suporte</span><span class="sxs-lookup"><span data-stu-id="582d6-144">Non-Supported Data Types</span></span>  
 <span data-ttu-id="582d6-145">As tabelas Oracle de origem com colunas dos seguintes tipos de dados Oracle não podem ser capturadas.</span><span class="sxs-lookup"><span data-stu-id="582d6-145">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span> <span data-ttu-id="582d6-146">As colunas capturadas com estes tipos de dados mostrarão como nulo; porém, uma alteração no seu valor é indicada na máscara de alteração das tabelas capturadas.</span><span class="sxs-lookup"><span data-stu-id="582d6-146">Captured columns with these data types will show as null; however, a change in their value is indicated in the change mask of the captured tables.</span></span>  
  
-   <span data-ttu-id="582d6-147">LONG</span><span class="sxs-lookup"><span data-stu-id="582d6-147">LONG</span></span>  
  
-   <span data-ttu-id="582d6-148">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="582d6-148">XMLTYPE</span></span>  
  
-   <span data-ttu-id="582d6-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="582d6-149">BLOB</span></span>  
  
-   <span data-ttu-id="582d6-150">CLOB</span><span class="sxs-lookup"><span data-stu-id="582d6-150">CLOB</span></span>  
  
 <span data-ttu-id="582d6-151">As tabelas Oracle de origem com colunas dos seguintes tipos de dados Oracle não podem ser capturadas.</span><span class="sxs-lookup"><span data-stu-id="582d6-151">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span>  
  
-   <span data-ttu-id="582d6-152">BFILE</span><span class="sxs-lookup"><span data-stu-id="582d6-152">BFILE</span></span>  
  
-   <span data-ttu-id="582d6-153">ROWID</span><span class="sxs-lookup"><span data-stu-id="582d6-153">ROWID</span></span>  
  
-   <span data-ttu-id="582d6-154">REF</span><span class="sxs-lookup"><span data-stu-id="582d6-154">REF</span></span>  
  
-   <span data-ttu-id="582d6-155">UROWID</span><span class="sxs-lookup"><span data-stu-id="582d6-155">UROWID</span></span>  
  
-   <span data-ttu-id="582d6-156">Tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="582d6-156">Nested Table</span></span>  
  
 <span data-ttu-id="582d6-157">Se os seguintes tipos de dados estiverem presentes em uma tabela, eles impedirão que o LogMiner obtenha dados para qualquer coluna da tabela:</span><span class="sxs-lookup"><span data-stu-id="582d6-157">If the following data types are present in a table they will prevent the LogMinder from getting any data for any column of the table:</span></span>  
  
-   <span data-ttu-id="582d6-158">Tipos de dados definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="582d6-158">User-defined data types</span></span>  
  
-   <span data-ttu-id="582d6-159">VARRAY</span><span class="sxs-lookup"><span data-stu-id="582d6-159">VARRAY</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="582d6-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="582d6-160">See Also</span></span>  
 <span data-ttu-id="582d6-161">[Change Data Capture Designer para Oracle da Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="582d6-161">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="582d6-162">A instância Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="582d6-162">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  
  
  
