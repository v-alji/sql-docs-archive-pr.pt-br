---
title: Obtendo informações sobre assemblies | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], metadata
- status information [SQL Server], assemblies
- metadata [SQL Server], assemblies
ms.assetid: 6aa7f18e-baad-4481-9777-8c3b230b392f
author: rothja
ms.author: jroth
ms.openlocfilehash: ec559ba5ccbb53dd92f3a5e1175a10a59fbaf43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682294"
---
# <a name="getting-information-about-assemblies"></a><span data-ttu-id="a49f2-102">Obtendo informações sobre assemblies</span><span class="sxs-lookup"><span data-stu-id="a49f2-102">Getting Information About Assemblies</span></span>
  <span data-ttu-id="a49f2-103">As exibições do catálogo e as funções a seguir podem ser consultadas para pesquisar metadados sobre assemblies.</span><span class="sxs-lookup"><span data-stu-id="a49f2-103">The following catalog views and functions can be queried for metadata about assemblies.</span></span>  
  
 <span data-ttu-id="a49f2-104">**Para obter informações sobre assemblies individuais**</span><span class="sxs-lookup"><span data-stu-id="a49f2-104">**To get information about individual assemblies**</span></span>  
  
-   [<span data-ttu-id="a49f2-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/assemblyproperty-transact-sql)  
  
 <span data-ttu-id="a49f2-106">**Para obter informações sobre todos os assemblies do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a49f2-106">**To get information about all assemblies in the database**</span></span>  
  
-   [<span data-ttu-id="a49f2-107">sys.assemblies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-107">sys.assemblies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assemblies-transact-sql)  
  
 <span data-ttu-id="a49f2-108">**Para obter informações sobre arquivos de assembly, inclusive binários de assembly, arquivos de origem e arquivos de depuração**</span><span class="sxs-lookup"><span data-stu-id="a49f2-108">**To get information about assembly files, including assembly binaries, source files, and debug files**</span></span>  
  
-   [<span data-ttu-id="a49f2-109">sys.assembly_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-109">sys.assembly_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-files-transact-sql)  
  
 <span data-ttu-id="a49f2-110">**Para obter informações sobre referências entre assemblies**</span><span class="sxs-lookup"><span data-stu-id="a49f2-110">**To get information about cross-assembly references**</span></span>  
  
-   [<span data-ttu-id="a49f2-111">sys.assembly_references &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-111">sys.assembly_references &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-references-transact-sql)  
  
 <span data-ttu-id="a49f2-112">**Para obter informações de assembly sobre tipos definidos pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="a49f2-112">**To get assembly information about user-defined types**</span></span>  
  
-   [<span data-ttu-id="a49f2-113">sys.assembly_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-113">sys.assembly_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-types-transact-sql)  
  
-   [<span data-ttu-id="a49f2-114">sys.types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-114">sys.types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-types-transact-sql)  
  
 <span data-ttu-id="a49f2-115">**Para obter informações de assembly sobre procedimentos armazenados CLR (Common Language Runtime), gatilhos e funções**</span><span class="sxs-lookup"><span data-stu-id="a49f2-115">**To get assembly information about common language runtime (CLR) stored procedures, triggers, and functions**</span></span>  
  
-   [<span data-ttu-id="a49f2-116">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-116">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
 <span data-ttu-id="a49f2-117">**Para obter informações sobre objetos não CLR**</span><span class="sxs-lookup"><span data-stu-id="a49f2-117">**To get information about non-CLR objects**</span></span>  
  
-   [<span data-ttu-id="a49f2-118">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a49f2-118">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="a49f2-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a49f2-119">See Also</span></span>  
 <span data-ttu-id="a49f2-120">[Assemblies &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="a49f2-120">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="a49f2-121">[Projetando assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span><span class="sxs-lookup"><span data-stu-id="a49f2-121">[Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span></span>  
 [<span data-ttu-id="a49f2-122">Implementando assemblies</span><span class="sxs-lookup"><span data-stu-id="a49f2-122">Implementing Assemblies</span></span>](assemblies-implementing.md)  
  
  
