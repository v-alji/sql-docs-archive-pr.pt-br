---
title: Implementação da compactação Unicode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Unicode data compression
- compression [SQL Server], Unicode data
ms.assetid: 44e69e60-9b35-43fe-b9c7-8cf34eaea62a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4c928062169ed7feb03f1031362530474109976a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581938"
---
# <a name="unicode-compression-implementation"></a><span data-ttu-id="dc8dd-102">Implementação da compactação Unicode</span><span class="sxs-lookup"><span data-stu-id="dc8dd-102">Unicode Compression Implementation</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dc8dd-103">usa uma implementação do algoritmo SCSU (Esquema de Compactação Padrão para Unicode) para compactar valores Unicode que são armazenados em objetos compactados por linha ou página.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-103">uses an implementation of the Standard Compression Scheme for Unicode (SCSU) algorithm to compress Unicode values that are stored in row or page compressed objects.</span></span> <span data-ttu-id="dc8dd-104">Para esses objetos compactados, a compactação Unicode é automática para as colunas `nchar(n)` e `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-104">For these compressed objects, Unicode compression is automatic for `nchar(n)` and `nvarchar(n)` columns.</span></span> <span data-ttu-id="dc8dd-105">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] armazena dados Unicode como 2 bytes, seja qual for a localidade.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores Unicode data as 2 bytes, regardless of locale.</span></span> <span data-ttu-id="dc8dd-106">Isso é conhecido como codificação UCS-2.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-106">This is known as UCS-2 encoding.</span></span> <span data-ttu-id="dc8dd-107">Para algumas localidades, a implementação da compactação SCSU no SQL Server pode economizar até 50 por cento em espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-107">For some locales, the implementation of SCSU compression in SQL Server can save up to 50 percent in storage space.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="dc8dd-108">Tipos de dados com suporte</span><span class="sxs-lookup"><span data-stu-id="dc8dd-108">Supported Data Types</span></span>  
 <span data-ttu-id="dc8dd-109">A compactação Unicode dá suporte aos tipos de dados de comprimento fixo `nchar(n)` e `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-109">Unicode compression supports the fixed-length `nchar(n)` and `nvarchar(n)` data types.</span></span> <span data-ttu-id="dc8dd-110">Os valores de dados armazenados fora da linha ou em colunas `nvarchar(max)` não são compactados.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-110">Data values that are stored off row or in `nvarchar(max)` columns are not compressed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc8dd-111">A Compactação de Unicode não terá suporte para obter dados `nvarchar(max)` mesmo se forem armazenados em linha.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-111">Unicode compression is not supported for `nvarchar(max)` data even if it is stored in row.</span></span> <span data-ttu-id="dc8dd-112">Porém, este tipo de dados ainda pode aproveitar a compactação de página.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-112">However, this data type can still benefit from page compression.</span></span>  
  
## <a name="upgrading-from-earlier-versions-of-sql-server"></a><span data-ttu-id="dc8dd-113">Atualizando a partir de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc8dd-113">Upgrading from Earlier Versions of SQL Server</span></span>  
 <span data-ttu-id="dc8dd-114">Quando um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é atualizado para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], as alterações feitas devido à compactação Unicode não são feitas em nenhum objeto de banco de dados, compactado ou não.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-114">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Unicode compression-related changes are not made to any database object, compressed or uncompressed.</span></span> <span data-ttu-id="dc8dd-115">Depois que o banco de dados é atualizado, os objetos são afetados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dc8dd-115">After the database is upgraded, objects are affected as follows:</span></span>  
  
-   <span data-ttu-id="dc8dd-116">Se o objeto não for compactado, nenhuma alteração será feita e o objeto continuará funcionando como antes.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-116">If the object is not compressed, no changes are made and the object continues to function as it did previously.</span></span>  
  
-   <span data-ttu-id="dc8dd-117">Objetos compactados por linha ou página continuam funcionando como antes.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-117">Row- or page-compressed objects continue to function as they did previously.</span></span> <span data-ttu-id="dc8dd-118">Dados não compactados permanecerão assim até que seu valor seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-118">Uncompressed data remains in uncompressed form until its value is updated.</span></span>  
  
-   <span data-ttu-id="dc8dd-119">As novas linhas inseridas em uma tabela compactada por linha ou página usam compactação Unicode.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-119">New rows that are inserted into a row- or page-compressed table are compressed using Unicode compression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc8dd-120">Para aproveitar ao máximo os benefícios da compactação Unicode, o objeto deve ser reconstruído com compactação de página ou linha.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-120">To take full advantage of the benefits of Unicode compression, the object must be rebuilt with page or row compression.</span></span>  
  
## <a name="how-unicode-compression-affects-data-storage"></a><span data-ttu-id="dc8dd-121">Como a compactação Unicode afeta o armazenamento de dados</span><span class="sxs-lookup"><span data-stu-id="dc8dd-121">How Unicode Compression Affects Data Storage</span></span>  
 <span data-ttu-id="dc8dd-122">Quando um índice é criado ou reconstruído ou quando um valor é alterado em uma tabela que foi compactada por linha ou página, o índice ou valor afetado será armazenado compactado somente se seu tamanho compactado for menor que seu tamanho atual.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-122">When an index is created or rebuilt or when a value is changed in a table that was compressed with row or page compression, the affected index or value is stored compressed only if its compressed size is less than its current size.</span></span> <span data-ttu-id="dc8dd-123">Isto impede as linhas em uma tabela ou índice de aumentarem de tamanho devido à compactação Unicode.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-123">This prevents rows in a table or index from increasing in size because of Unicode compression.</span></span>  
  
 <span data-ttu-id="dc8dd-124">O espaço de armazenamento que a compactação economiza depende das características e da localidade dos dados que estão sendo compactados.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-124">The storage space that compression saves depends on the characteristics of the data that is being compressed and the locale of the data.</span></span> <span data-ttu-id="dc8dd-125">A tabela a seguir lista a economia de espaço que pode ser obtida para diversas localidades.</span><span class="sxs-lookup"><span data-stu-id="dc8dd-125">The following table lists the space savings that can be achieved for several locales.</span></span>  
  
|<span data-ttu-id="dc8dd-126">Local</span><span class="sxs-lookup"><span data-stu-id="dc8dd-126">Locale</span></span>|<span data-ttu-id="dc8dd-127">Porcentagem de compactação</span><span class="sxs-lookup"><span data-stu-id="dc8dd-127">Compression percent</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="dc8dd-128">Inglês</span><span class="sxs-lookup"><span data-stu-id="dc8dd-128">English</span></span>|<span data-ttu-id="dc8dd-129">50%</span><span class="sxs-lookup"><span data-stu-id="dc8dd-129">50%</span></span>|  
|<span data-ttu-id="dc8dd-130">Alemão</span><span class="sxs-lookup"><span data-stu-id="dc8dd-130">German</span></span>|<span data-ttu-id="dc8dd-131">50%</span><span class="sxs-lookup"><span data-stu-id="dc8dd-131">50%</span></span>|  
|<span data-ttu-id="dc8dd-132">Híndi</span><span class="sxs-lookup"><span data-stu-id="dc8dd-132">Hindi</span></span>|<span data-ttu-id="dc8dd-133">50%</span><span class="sxs-lookup"><span data-stu-id="dc8dd-133">50%</span></span>|  
|<span data-ttu-id="dc8dd-134">Turco</span><span class="sxs-lookup"><span data-stu-id="dc8dd-134">Turkish</span></span>|<span data-ttu-id="dc8dd-135">48%</span><span class="sxs-lookup"><span data-stu-id="dc8dd-135">48%</span></span>|  
|<span data-ttu-id="dc8dd-136">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="dc8dd-136">Vietnamese</span></span>|<span data-ttu-id="dc8dd-137">39%</span><span class="sxs-lookup"><span data-stu-id="dc8dd-137">39%</span></span>|  
|<span data-ttu-id="dc8dd-138">Japonês</span><span class="sxs-lookup"><span data-stu-id="dc8dd-138">Japanese</span></span>|<span data-ttu-id="dc8dd-139">15%</span><span class="sxs-lookup"><span data-stu-id="dc8dd-139">15%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc8dd-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc8dd-140">See Also</span></span>  
 <span data-ttu-id="dc8dd-141">[Compactação de dados](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="dc8dd-141">[Data Compression](data-compression.md) </span></span>  
 <span data-ttu-id="dc8dd-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc8dd-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span></span>  
 <span data-ttu-id="dc8dd-143">[Implementação da compactação de página](page-compression-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="dc8dd-143">[Page Compression Implementation](page-compression-implementation.md) </span></span>  
 [<span data-ttu-id="dc8dd-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dc8dd-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-persisted-sku-features-transact-sql)  
  
  
