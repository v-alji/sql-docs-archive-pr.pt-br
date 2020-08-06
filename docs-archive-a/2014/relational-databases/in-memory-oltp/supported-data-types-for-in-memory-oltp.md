---
title: Tipos de dados com suporte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a7dda500486c39a66f871d5934f957028fc51e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685138"
---
# <a name="supported-data-types"></a><span data-ttu-id="e3862-102">Tipos de dados com suporte</span><span class="sxs-lookup"><span data-stu-id="e3862-102">Supported Data Types</span></span>
  <span data-ttu-id="e3862-103">Os tipos de dados a seguir têm **suporte** nas tabelas com otimização de memória e nos procedimentos armazenados compilados de modo nativo:</span><span class="sxs-lookup"><span data-stu-id="e3862-103">The following data types are **supported** in memory-optimized tables and natively compiled stored procedures:</span></span>  
  
 <span data-ttu-id="e3862-104">**Tipos de dados numéricos**</span><span class="sxs-lookup"><span data-stu-id="e3862-104">**Numeric Data Types**</span></span>  
  
|<span data-ttu-id="e3862-105">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e3862-105">Data type</span></span>|<span data-ttu-id="e3862-106">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e3862-106">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="e3862-107">int</span><span class="sxs-lookup"><span data-stu-id="e3862-107">int</span></span>|[<span data-ttu-id="e3862-108">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-108">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="e3862-109">BIGINT</span><span class="sxs-lookup"><span data-stu-id="e3862-109">bigint</span></span>|[<span data-ttu-id="e3862-110">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-110">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="e3862-111">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="e3862-111">smallint</span></span>|[<span data-ttu-id="e3862-112">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-112">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="e3862-113">TINYINT</span><span class="sxs-lookup"><span data-stu-id="e3862-113">tinyint</span></span>|[<span data-ttu-id="e3862-114">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-114">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="e3862-115">decimal</span><span class="sxs-lookup"><span data-stu-id="e3862-115">decimal</span></span>|[<span data-ttu-id="e3862-116">decimal e numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-116">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="e3862-117">numeric</span><span class="sxs-lookup"><span data-stu-id="e3862-117">numeric</span></span>|[<span data-ttu-id="e3862-118">decimal e numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-118">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="e3862-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="e3862-119">float</span></span>|[<span data-ttu-id="e3862-120">float e real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-120">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="e3862-121">real</span><span class="sxs-lookup"><span data-stu-id="e3862-121">real</span></span>|[<span data-ttu-id="e3862-122">float e real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-122">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="e3862-123">money</span><span class="sxs-lookup"><span data-stu-id="e3862-123">money</span></span>|[<span data-ttu-id="e3862-124">money e smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-124">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|<span data-ttu-id="e3862-125">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="e3862-125">smallmoney</span></span>|[<span data-ttu-id="e3862-126">money e smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-126">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 <span data-ttu-id="e3862-127">**Tipos de dados de cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="e3862-127">**String Data Types**</span></span>  
  
|<span data-ttu-id="e3862-128">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e3862-128">Data type</span></span>|<span data-ttu-id="e3862-129">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e3862-129">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="e3862-130">char(n)</span><span class="sxs-lookup"><span data-stu-id="e3862-130">char(n)</span></span>|[<span data-ttu-id="e3862-131">char e varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-131">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="e3862-132">varchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3862-132">varchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="e3862-133">char e varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-133">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="e3862-134">nchar(n)</span><span class="sxs-lookup"><span data-stu-id="e3862-134">nchar(n)</span></span>|[<span data-ttu-id="e3862-135">nchar and nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-135">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="e3862-136">nvarchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3862-136">nvarchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="e3862-137">nchar and nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-137">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="e3862-138">sysname</span><span class="sxs-lookup"><span data-stu-id="e3862-138">sysname</span></span>|[<span data-ttu-id="e3862-139">nchar and nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-139">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <span data-ttu-id="e3862-140"><sup>1</sup> a limitação é de 8060 bytes por total de linha, contando (n) em tipos de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="e3862-140"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="e3862-141">Para obter informações sobre ordenações suportadas, consulte [Páginas de código de ordenações](../../database-engine/collations-and-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="e3862-141">For information about supported collations, see [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span></span>  
  
 <span data-ttu-id="e3862-142">**Tipos de dados de data e hora**</span><span class="sxs-lookup"><span data-stu-id="e3862-142">**Date and Time Data Types**</span></span>  
  
|<span data-ttu-id="e3862-143">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e3862-143">Data type</span></span>|<span data-ttu-id="e3862-144">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e3862-144">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="e3862-145">date</span><span class="sxs-lookup"><span data-stu-id="e3862-145">date</span></span>|[<span data-ttu-id="e3862-146">date &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-146">date &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/date-transact-sql)|  
|<span data-ttu-id="e3862-147">time</span><span class="sxs-lookup"><span data-stu-id="e3862-147">time</span></span>|[<span data-ttu-id="e3862-148">time &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-148">time &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/time-transact-sql)|  
|<span data-ttu-id="e3862-149">DATETIME</span><span class="sxs-lookup"><span data-stu-id="e3862-149">datetime</span></span>|[<span data-ttu-id="e3862-150">datetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-150">datetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime-transact-sql)|  
|<span data-ttu-id="e3862-151">datetime2</span><span class="sxs-lookup"><span data-stu-id="e3862-151">datetime2</span></span>|[<span data-ttu-id="e3862-152">datetime2 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-152">datetime2 &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime2-transact-sql)|  
|<span data-ttu-id="e3862-153">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="e3862-153">smalldatetime</span></span>|[<span data-ttu-id="e3862-154">smalldatetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-154">smalldatetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 <span data-ttu-id="e3862-155">**Tipos de dados binários**</span><span class="sxs-lookup"><span data-stu-id="e3862-155">**Binary Data Types**</span></span>  
  
|<span data-ttu-id="e3862-156">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e3862-156">Data type</span></span>|<span data-ttu-id="e3862-157">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e3862-157">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="e3862-158">bit</span><span class="sxs-lookup"><span data-stu-id="e3862-158">bit</span></span>|[<span data-ttu-id="e3862-159">bit &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-159">bit &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/bit-transact-sql)|  
|<span data-ttu-id="e3862-160">binary(n)</span><span class="sxs-lookup"><span data-stu-id="e3862-160">binary(n)</span></span>|[<span data-ttu-id="e3862-161">binary e varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-161">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|<span data-ttu-id="e3862-162">varbinary (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3862-162">varbinary(n) <sup>1</sup></span></span>|[<span data-ttu-id="e3862-163">binary e varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-163">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <span data-ttu-id="e3862-164"><sup>1</sup> a limitação é de 8060 bytes por total de linha, contando (n) em tipos de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="e3862-164"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="e3862-165">**Outros tipos de dados**</span><span class="sxs-lookup"><span data-stu-id="e3862-165">**Other data types**</span></span>  
  
|<span data-ttu-id="e3862-166">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e3862-166">Data type</span></span>|<span data-ttu-id="e3862-167">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e3862-167">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="e3862-168">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="e3862-168">uniqueidentifier</span></span>|[<span data-ttu-id="e3862-169">uniqueidentifier &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3862-169">uniqueidentifier &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 <span data-ttu-id="e3862-170">**Tipos de dados sem-suporte**</span><span class="sxs-lookup"><span data-stu-id="e3862-170">**Unsupported Data Types**</span></span>  
  
 <span data-ttu-id="e3862-171">Não há suporte para os seguintes tipos de dados:</span><span class="sxs-lookup"><span data-stu-id="e3862-171">The following data types are not supported:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="e3862-172">DATETIMEOFFSET</span><span class="sxs-lookup"><span data-stu-id="e3862-172">DATETIMEOFFSET</span></span>|<span data-ttu-id="e3862-173">GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="e3862-173">GEOGRAPHY</span></span>|<span data-ttu-id="e3862-174">GEOMETRY</span><span class="sxs-lookup"><span data-stu-id="e3862-174">GEOMETRY</span></span>|  
|<span data-ttu-id="e3862-175">HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="e3862-175">HIERARCHYID</span></span>|<span data-ttu-id="e3862-176">Objetos Grandes (LOBs).</span><span class="sxs-lookup"><span data-stu-id="e3862-176">Large Objects (LOBs).</span></span> <span data-ttu-id="e3862-177">Por exemplo, varchar(max), nvarchar(max), varbinary(max), image, xml, text e ntext.</span><span class="sxs-lookup"><span data-stu-id="e3862-177">For example, varchar(max), nvarchar(max), varbinary(max), image, xml, text, and ntext.</span></span>|<span data-ttu-id="e3862-178">ROWVERSION</span><span class="sxs-lookup"><span data-stu-id="e3862-178">ROWVERSION</span></span>|  
|<span data-ttu-id="e3862-179">sql_variant</span><span class="sxs-lookup"><span data-stu-id="e3862-179">sql_variant</span></span>|<span data-ttu-id="e3862-180">Funções CLR</span><span class="sxs-lookup"><span data-stu-id="e3862-180">CLR functions</span></span>|<span data-ttu-id="e3862-181">Tipos definidos pelo usuário (UDTs)</span><span class="sxs-lookup"><span data-stu-id="e3862-181">User-defined types (UDTs)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3862-182">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3862-182">See Also</span></span>  
 <span data-ttu-id="e3862-183">[Suporte ao Transact-SQL para OLTP na memória](transact-sql-support-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="e3862-183">[Transact-SQL Support for In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="e3862-184">[Implementando colunas LOB em uma tabela com otimização de memória](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span><span class="sxs-lookup"><span data-stu-id="e3862-184">[Implementing LOB Columns in a Memory-Optimized Table](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span></span>  
 [<span data-ttu-id="e3862-185">Implementando SQL_VARIANT em uma tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="e3862-185">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  
