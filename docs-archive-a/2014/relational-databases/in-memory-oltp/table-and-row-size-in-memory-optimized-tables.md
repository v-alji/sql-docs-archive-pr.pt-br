---
title: Tamanho da tabela e da linha em tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b0a248a4-4488-4cc8-89fc-46906a8c24a1
author: rothja
ms.author: jroth
ms.openlocfilehash: 74cc40b7d1f2d0132d79d1e9ae15c2321ac9b74a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685670"
---
# <a name="table-and-row-size-in-memory-optimized-tables"></a><span data-ttu-id="6ce3b-102">Tamanho da tabela e da linha em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6ce3b-102">Table and Row Size in Memory-Optimized Tables</span></span>
  <span data-ttu-id="6ce3b-103">Uma tabela com otimização de memória consiste em uma coleção de linhas e índices que contêm ponteiros para linhas.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-103">A memory-optimized table consists of a collection of rows and indexes that contain pointers to rows.</span></span> <span data-ttu-id="6ce3b-104">Em uma tabela com otimização de memória, as linhas não podem ter mais de 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-104">In a memory-optimized table, rows cannot be longer than 8,060 bytes.</span></span> <span data-ttu-id="6ce3b-105">Entender o tamanho de uma tabela com otimização de memória ajudará você a saber se o computador tem memória suficiente.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-105">Understanding the size of a memory-optimized table will help you understand if your computer has enough memory.</span></span>  
  
 <span data-ttu-id="6ce3b-106">Há duas razões para calcular o tamanho da tabela e da linha:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-106">There are two reasons for computing table and row size:</span></span>  
  
-   <span data-ttu-id="6ce3b-107">Qual a quantidade de memória que uma tabela usa?</span><span class="sxs-lookup"><span data-stu-id="6ce3b-107">How much memory does a table use?</span></span>  
  
    -   <span data-ttu-id="6ce3b-108">A quantidade de memória usada pela tabela não pode ser calculada exatamente.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-108">The amount of memory used by the table cannot be calculated exactly.</span></span> <span data-ttu-id="6ce3b-109">Muitos fatores afetam a quantidade de memória usada,</span><span class="sxs-lookup"><span data-stu-id="6ce3b-109">Many factors affect the amount of memory used.</span></span> <span data-ttu-id="6ce3b-110">como alocação de memória baseada na página, localidade, cache e preenchimento.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-110">Factors such as page-based memory allocation, locality, caching, and padding.</span></span> <span data-ttu-id="6ce3b-111">Além disso, várias versões de linhas têm transações ativas associadas ou estão aguardando a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-111">Also, multiple versions of rows that either have active transactions associated or that are waiting for garbage collection.</span></span>  
  
    -   <span data-ttu-id="6ce3b-112">O tamanho mínimo necessário para os dados e índices na tabela é determinado pelo cálculo de [tamanho da tabela], discutido a seguir.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-112">The minimum size required for the data and indexes in the table is given by the calculation for [table size], discussed below.</span></span>  
  
    -   <span data-ttu-id="6ce3b-113">Calcular o uso da memória é, na melhor das hipóteses, uma aproximação; portanto, é recomendável incluir o planejamento de capacidade nos planos de implantação.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-113">Calculating memory use is at best an approximation and you are advised to include capacity planning in your deployment plans.</span></span>  
  
-   <span data-ttu-id="6ce3b-114">O tamanho dos dados de uma linha; ele se ajusta à limitação de tamanho de linha de 8.060 bytes?</span><span class="sxs-lookup"><span data-stu-id="6ce3b-114">The data size of a row, and does it fit in the 8,060 byte row size limitation?</span></span> <span data-ttu-id="6ce3b-115">Para responder a essas perguntas, use a computação para [tamanho do corpo da linha], discutida abaixo.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-115">To answer these questions, use the computation for [row body size], discussed below.</span></span>  
  
 <span data-ttu-id="6ce3b-116">A figura a seguir ilustra uma tabela com índices e linhas que, por sua vez, têm cabeçalhos e corpos de linha:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-116">The following figure illustrates a table with indexes and rows, which in turn have row headers and bodies:</span></span>  
  
 <span data-ttu-id="6ce3b-117">![Tabela com otimização de memória.](../../database-engine/media/hekaton-guide-1.gif "Tabela com otimização de memória.")</span><span class="sxs-lookup"><span data-stu-id="6ce3b-117">![Memory optimized table.](../../database-engine/media/hekaton-guide-1.gif "Memory optimized table.")</span></span>  
<span data-ttu-id="6ce3b-118">Tabela com otimização de memória composta por índices e linhas.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-118">Memory-optimized table, consisting of indexes and rows.</span></span>  
  
 <span data-ttu-id="6ce3b-119">O tamanho de uma tabela na memória, em bytes, é calculado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-119">The in-memory size of a table, in bytes, is computed as follows:</span></span>  
  
```  
[table size] = [size of index 1] + ... + [size of index n] + ([row size] * [row count])  
```  
  
 <span data-ttu-id="6ce3b-120">O tamanho de um índice de hash é fixado no momento da criação da tabela e depende do número real de buckets.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-120">The size of a hash index is fixed at table creation time and depends on the actual bucket count.</span></span> <span data-ttu-id="6ce3b-121">O bucket_count na especificação de índice é arredondado para a potência mais próxima de 2, de modo a obter [número real de buckets].</span><span class="sxs-lookup"><span data-stu-id="6ce3b-121">The bucket_count specified with the index specification is rounded up to the nearest power of 2 to obtain the [actual bucket count].</span></span> <span data-ttu-id="6ce3b-122">Por exemplo, se o bucket_count especificado for 100000, o [número real de buckets] para o índice será 131072.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-122">For example, if the specified bucket_count is 100000, the [actual bucket count] for the index is 131072.</span></span>  
  
```  
[hash index size] = 8 * [actual bucket count]  
```  
  
 <span data-ttu-id="6ce3b-123">O tamanho da linha é calculado adicionando-se o cabeçalho e o corpo:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-123">The row size is computed by adding the header and the body:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices]  
```  
  
 <span data-ttu-id="6ce3b-124">**Tamanho do corpo da linha**</span><span class="sxs-lookup"><span data-stu-id="6ce3b-124">**Row body size**</span></span>  
  
 <span data-ttu-id="6ce3b-125">O cálculo do [tamanho do corpo da linha] é abordado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-125">The calculation of [row body size] is discussed in the following table.</span></span>  
  
 <span data-ttu-id="6ce3b-126">Há dois cálculos diferentes para o tamanho do corpo da linha: tamanho calculado e o tamanho real:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-126">There are two different computations for row body size: computed size and the actual size:</span></span>  
  
-   <span data-ttu-id="6ce3b-127">O tamanho calculado, marcado com [tamanho do corpo da linha calculado], é usado para determinar se a limitação do tamanho da linha de 8.060 bytes foi excedida.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-127">The computed size, denoted with [computed row body size], is used to determine if the row size limitation of 8,060 bytes is exceeded.</span></span>  
  
-   <span data-ttu-id="6ce3b-128">O tamanho real, marcado com [tamanho do corpo da linha real], é o tamanho real do armazenamento do corpo da linha na memória e nos arquivos de ponto de verificação.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-128">The actual size, denoted with [actual row body size], is the actual storage size of the row body in memory and in the checkpoint files.</span></span>  
  
 <span data-ttu-id="6ce3b-129">O [tamanho do corpo da linha calculado] e o [tamanho do corpo da linha real] são calculados de modo semelhante.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-129">Both [computed row body size] and [actual row body size] are calculated similarly.</span></span> <span data-ttu-id="6ce3b-130">A única diferença é o cálculo do tamanho das colunas (n)varchar(i) e varbinary(i), como refletido na parte inferior da tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-130">The only difference is the calculation of the size of (n)varchar(i) and varbinary(i) columns, as reflected at the bottom of the following table.</span></span> <span data-ttu-id="6ce3b-131">O tamanho do corpo da linha calculado usa o tamanho declarado *i* como o tamanho da coluna, enquanto o tamanho do corpo da linha real usa o tamanho real dos dados.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-131">The computed row body size uses the declared size *i* as the size of the column, while the actual row body size uses the actual size of the data.</span></span>  
  
 <span data-ttu-id="6ce3b-132">A tabela a seguir descreve o cálculo do tamanho do corpo da linha, fornecido como [tamanho do corpo real da linha] = SUM([tamanho de tipos rasos]) + 2 + 2 \* [número de colunas de tipo profundo].</span><span class="sxs-lookup"><span data-stu-id="6ce3b-132">The following table describes the calculation of the row body size, given as [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span></span>  
  
|<span data-ttu-id="6ce3b-133">Seção</span><span class="sxs-lookup"><span data-stu-id="6ce3b-133">Section</span></span>|<span data-ttu-id="6ce3b-134">Tamanho</span><span class="sxs-lookup"><span data-stu-id="6ce3b-134">Size</span></span>|<span data-ttu-id="6ce3b-135">Comentários</span><span class="sxs-lookup"><span data-stu-id="6ce3b-135">Comments</span></span>|  
|-------------|----------|--------------|  
|<span data-ttu-id="6ce3b-136">Colunas do tipo superficial</span><span class="sxs-lookup"><span data-stu-id="6ce3b-136">Shallow type columns</span></span>|<span data-ttu-id="6ce3b-137">SUM([tamanho dos tipos superficiais])</span><span class="sxs-lookup"><span data-stu-id="6ce3b-137">SUM([size of shallow types])</span></span><br /><br /> <span data-ttu-id="6ce3b-138">**O tamanho dos tipos individuais é o seguinte:**</span><span class="sxs-lookup"><span data-stu-id="6ce3b-138">**Size of the individual types is as follows:**</span></span><br /><br /> <span data-ttu-id="6ce3b-139">Bit &#124; 1</span><span class="sxs-lookup"><span data-stu-id="6ce3b-139">Bit &#124; 1</span></span><br /><br /> <span data-ttu-id="6ce3b-140">Tinyint &#124; 1</span><span class="sxs-lookup"><span data-stu-id="6ce3b-140">Tinyint &#124; 1</span></span><br /><br /> <span data-ttu-id="6ce3b-141">Smallint &#124; 2</span><span class="sxs-lookup"><span data-stu-id="6ce3b-141">Smallint &#124; 2</span></span><br /><br /> <span data-ttu-id="6ce3b-142">Int &#124; 4</span><span class="sxs-lookup"><span data-stu-id="6ce3b-142">Int &#124; 4</span></span><br /><br /> <span data-ttu-id="6ce3b-143">Real &#124; 4</span><span class="sxs-lookup"><span data-stu-id="6ce3b-143">Real &#124; 4</span></span><br /><br /> <span data-ttu-id="6ce3b-144">Smalldatetime &#124; 4</span><span class="sxs-lookup"><span data-stu-id="6ce3b-144">Smalldatetime &#124; 4</span></span><br /><br /> <span data-ttu-id="6ce3b-145">Smallmoney &#124; 4</span><span class="sxs-lookup"><span data-stu-id="6ce3b-145">Smallmoney &#124; 4</span></span><br /><br /> <span data-ttu-id="6ce3b-146">Bigint &#124; 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-146">Bigint &#124; 8</span></span><br /><br /> <span data-ttu-id="6ce3b-147">Datetime &#124; 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-147">Datetime &#124; 8</span></span><br /><br /> <span data-ttu-id="6ce3b-148">Datetime2 &#124; 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-148">Datetime2 &#124; 8</span></span><br /><br /> <span data-ttu-id="6ce3b-149">Float 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-149">Float 8</span></span><br /><br /> <span data-ttu-id="6ce3b-150">Money 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-150">Money 8</span></span><br /><br /> <span data-ttu-id="6ce3b-151">Numeric (Precision <= 18) &#124; 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-151">Numeric (precision <=18) &#124; 8</span></span><br /><br /> <span data-ttu-id="6ce3b-152">Time &#124; 8</span><span class="sxs-lookup"><span data-stu-id="6ce3b-152">Time &#124; 8</span></span><br /><br /> <span data-ttu-id="6ce3b-153">Numeric (precisão>18) &#124; 16</span><span class="sxs-lookup"><span data-stu-id="6ce3b-153">Numeric(precision>18) &#124; 16</span></span><br /><br /> <span data-ttu-id="6ce3b-154">Uniqueidentifier &#124; 16</span><span class="sxs-lookup"><span data-stu-id="6ce3b-154">Uniqueidentifier &#124; 16</span></span>||  
|<span data-ttu-id="6ce3b-155">Preenchimento da coluna superficial</span><span class="sxs-lookup"><span data-stu-id="6ce3b-155">Shallow column padding</span></span>|<span data-ttu-id="6ce3b-156">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-156">Possible values are:</span></span><br /><br /> <span data-ttu-id="6ce3b-157">1 se houver colunas do tipo profundas e o tamanho total dos dados das colunas superficiais for como um número ímpar.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-157">1 if there are deep type columns and the total data size of the shallow columns is as odd number.</span></span><br /><br /> <span data-ttu-id="6ce3b-158">Caso contrário, será 0</span><span class="sxs-lookup"><span data-stu-id="6ce3b-158">0 otherwise</span></span>|<span data-ttu-id="6ce3b-159">Os tipos profundos são os tipos (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-159">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="6ce3b-160">Matriz de deslocamento para colunas do tipo profundas</span><span class="sxs-lookup"><span data-stu-id="6ce3b-160">Offset array for deep type columns</span></span>|<span data-ttu-id="6ce3b-161">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-161">Possible values are:</span></span><br /><br /> <span data-ttu-id="6ce3b-162">0 se não houver nenhuma coluna do tipo profunda</span><span class="sxs-lookup"><span data-stu-id="6ce3b-162">0 if there are no deep type columns</span></span><br /><br /> <span data-ttu-id="6ce3b-163">Caso contrário, 2 + 2 \* [número de colunas do tipo profundas]</span><span class="sxs-lookup"><span data-stu-id="6ce3b-163">2 + 2 \* [number of deep type columns] otherwise</span></span>|<span data-ttu-id="6ce3b-164">Os tipos profundos são os tipos (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-164">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="6ce3b-165">Matriz NULL</span><span class="sxs-lookup"><span data-stu-id="6ce3b-165">NULL array</span></span>|<span data-ttu-id="6ce3b-166">[número de colunas que permitem valor nulo] / 8, arredondado para bytes completos.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-166">[number of nullable columns] / 8, rounded up to full bytes.</span></span>|<span data-ttu-id="6ce3b-167">A matriz tem um bit por coluna que permite valor nulo.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-167">The array has one bit per nullable column.</span></span> <span data-ttu-id="6ce3b-168">Ele é arredondado para bytes completos.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-168">This is rounded up to full bytes.</span></span>|  
|<span data-ttu-id="6ce3b-169">Preenchimento da matriz NULL</span><span class="sxs-lookup"><span data-stu-id="6ce3b-169">NULL array padding</span></span>|<span data-ttu-id="6ce3b-170">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-170">Possible values are:</span></span><br /><br /> <span data-ttu-id="6ce3b-171">1 se houver colunas do tipo profundas e o tamanho da matriz NULL é um número ímpar de bytes.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-171">1 if there are deep type columns and the size of the NULL array is an odd number of bytes.</span></span><br /><br /> <span data-ttu-id="6ce3b-172">Caso contrário, será 0</span><span class="sxs-lookup"><span data-stu-id="6ce3b-172">0 otherwise</span></span>|<span data-ttu-id="6ce3b-173">Os tipos profundos são os tipos (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-173">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="6ce3b-174">Preenchimento</span><span class="sxs-lookup"><span data-stu-id="6ce3b-174">Padding</span></span>|<span data-ttu-id="6ce3b-175">Se não houver colunas de tipo profunda: 0</span><span class="sxs-lookup"><span data-stu-id="6ce3b-175">If there are no deep type columns: 0</span></span><br /><br /> <span data-ttu-id="6ce3b-176">Se houver colunas do tipo profundas, de 0 a 7 bytes de preenchimento serão adicionados, com base no maior alinhamento exigido por uma coluna superficial.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-176">If there are deep type columns, 0-7 bytes of padding is added, based on the largest alignment required by a shallow column.</span></span> <span data-ttu-id="6ce3b-177">Cada coluna superficial exige alinhamento igual a seu tamanho, como documentado acima, exceto pelo fato de que as colunas GUID precisam de alinhamento de 1 byte (e não 16) e as colunas numéricas sempre precisam de alinhamento de 8 bytes (nunca 16).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-177">Each shallow column requires alignment equal to its size as documented above, except that GUID columns need alignment of 1 byte (not 16) and numeric columns always need alignment of 8 bytes (never 16).</span></span> <span data-ttu-id="6ce3b-178">O requisito de maior alinhamento entre todas as colunas superficiais é usado, e de 0 a 7 bytes de preenchimento são adicionados, de modo que o tamanho total até agora (sem as colunas do tipo profundas) é um múltiplo do alinhamento requerido.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-178">The largest alignment requirement among all shallow columns is used, and 0-7 bytes of padding is added in such a way that the total size so far (without the deep type columns) is a multiple of the required alignment.</span></span>|<span data-ttu-id="6ce3b-179">Os tipos profundos são os tipos (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-179">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="6ce3b-180">Colunas do tipo profundas de comprimento fixo</span><span class="sxs-lookup"><span data-stu-id="6ce3b-180">Fixed-length deep type columns</span></span>|<span data-ttu-id="6ce3b-181">SUM([tamanho das colunas do tipo profundas de comprimento fixo])</span><span class="sxs-lookup"><span data-stu-id="6ce3b-181">SUM([size of fixed length deep type columns])</span></span><br /><br /> <span data-ttu-id="6ce3b-182">O tamanho de cada coluna é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-182">The size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="6ce3b-183">i para char(i) e binary(i).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-183">i for char(i) and binary(i).</span></span><br /><br /> <span data-ttu-id="6ce3b-184">2 \* i para nchar(i)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-184">2 \* i for nchar(i)</span></span>|<span data-ttu-id="6ce3b-185">As colunas do tipo profundas de comprimento fixo são colunas do tipo char(i), nchar(i) ou binary(i).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-185">Fixed-length deep type columns are columns of type char(i), nchar(i), or binary(i).</span></span>|  
|<span data-ttu-id="6ce3b-186">Colunas do tipo profundas de comprimento variável [tamanho calculado]</span><span class="sxs-lookup"><span data-stu-id="6ce3b-186">Variable length deep type columns [computed size]</span></span>|<span data-ttu-id="6ce3b-187">SUM([tamanho calculado das colunas do tipo profundas de comprimento variável])</span><span class="sxs-lookup"><span data-stu-id="6ce3b-187">SUM([computed size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="6ce3b-188">O tamanho calculado de cada coluna é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-188">The computed size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="6ce3b-189">i para varchar(i) e varbinary(i)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-189">i for varchar(i) and varbinary(i)</span></span><br /><br /> <span data-ttu-id="6ce3b-190">2 \* i para nvarchar(i)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-190">2 \* i for nvarchar(i)</span></span>|<span data-ttu-id="6ce3b-191">Essa linha é aplicada somente ao [tamanho do corpo da linha calculado].</span><span class="sxs-lookup"><span data-stu-id="6ce3b-191">This row only applied to [computed row body size].</span></span><br /><br /> <span data-ttu-id="6ce3b-192">As colunas do tipo profundas de comprimento variável são colunas do tipo varchar(i), nvarchar(i) ou varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-192">Variable-length deep type columns are columns of type varchar(i), nvarchar(i), or varbinary(i).</span></span> <span data-ttu-id="6ce3b-193">O tamanho calculado é determinado pelo comprimento máximo (i) da coluna.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-193">The computed size is determined by the max length (i) of the column.</span></span>|  
|<span data-ttu-id="6ce3b-194">Colunas do tipo profundas de comprimento variável [tamanho real]</span><span class="sxs-lookup"><span data-stu-id="6ce3b-194">Variable length deep type columns [actual size]</span></span>|<span data-ttu-id="6ce3b-195">SUM([tamanho real das colunas do tipo profundas de comprimento variável])</span><span class="sxs-lookup"><span data-stu-id="6ce3b-195">SUM([actual size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="6ce3b-196">O tamanho real de cada coluna é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-196">The actual size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="6ce3b-197">n, onde n é o número de caracteres armazenados na coluna, para varchar(i).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-197">n, where n is the number of characters stored in the column, for varchar(i).</span></span><br /><br /> <span data-ttu-id="6ce3b-198">2 \* n, onde n é o número de caracteres armazenados na coluna, para nvarchar(i).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-198">2 \* n, where n is the number of characters stored in the column, for nvarchar(i).</span></span><br /><br /> <span data-ttu-id="6ce3b-199">n, onde n é o número de bytes armazenados na coluna, para varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-199">n, where n is the number of bytes stored in the column, for varbinary(i).</span></span>|<span data-ttu-id="6ce3b-200">Essa linha é aplicada somente ao [tamanho do corpo da linha real].</span><span class="sxs-lookup"><span data-stu-id="6ce3b-200">This row only applied to [actual row body size].</span></span><br /><br /> <span data-ttu-id="6ce3b-201">O tamanho real é determinado pelos dados armazenados nas colunas da linha.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-201">The actual size is determined by the data stored in the columns in the row.</span></span>|  
  
##  <a name="row-structure"></a><a name="bkmk_RowStructure"></a><span data-ttu-id="6ce3b-202">Estrutura de linha</span><span class="sxs-lookup"><span data-stu-id="6ce3b-202">Row Structure</span></span>  
 <span data-ttu-id="6ce3b-203">As linhas em uma tabela com otimização de memória têm os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-203">The rows in a memory-optimized table have the following components:</span></span>  
  
-   <span data-ttu-id="6ce3b-204">O cabeçalho de linha contém o carimbo de data/hora necessário para implementar o controle de versão de linha.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-204">The row header contains the timestamp necessary to implement row versioning.</span></span> <span data-ttu-id="6ce3b-205">O cabeçalho da linha também contém o ponteiro de índice para implementar o encadeamento de linhas nos buckets de hash (descrito acima).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-205">The row header also contains the index pointer to implement the row chaining in the hash buckets (described above).</span></span>  
  
-   <span data-ttu-id="6ce3b-206">O corpo da linha contém os dados reais da coluna, que incluem algumas informações auxiliares como a matriz nula das colunas que permitem valor nulo e a matriz de deslocamento dos tipos de dados de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-206">The row body contains the actual column data, which includes some auxiliary information like the null array for nullable columns and the offset array for variable-length data types.</span></span>  
  
 <span data-ttu-id="6ce3b-207">A figura a seguir ilustra a estrutura de linha de uma tabela que tem dois índices:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-207">The following figure illustrates the row structure for a table that has two indexes:</span></span>  
  
 <span data-ttu-id="6ce3b-208">![Estrutura de linha para uma tabela que tem dois índices.](../../database-engine/media/hekaton-tables-4.gif "Estrutura de linha para uma tabela que tem dois índices.")</span><span class="sxs-lookup"><span data-stu-id="6ce3b-208">![Row structure for a table that has two indexes.](../../database-engine/media/hekaton-tables-4.gif "Row structure for a table that has two indexes.")</span></span>  
  
 <span data-ttu-id="6ce3b-209">Os carimbos de data/hora de início e de término indicam o período em que uma determinada versão de linha é válida.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-209">The begin and end timestamps indicate the period in which a particular row version is valid.</span></span> <span data-ttu-id="6ce3b-210">As transações que começam nesse intervalo podem ver essa versão de linha.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-210">Transactions that start in this interval can see this row version.</span></span> <span data-ttu-id="6ce3b-211">Para obter mais detalhes consulte [Transações em Tabelas com Otimização de Memória](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-211">For more details see [Transactions in Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="6ce3b-212">Os ponteiros de índice apontam para a próxima linha da cadeia de caracteres que pertence ao bucket de hash.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-212">The index pointers point to the next row in the chain belonging to the hash bucket.</span></span> <span data-ttu-id="6ce3b-213">A figura a seguir ilustra a estrutura de uma tabela com duas colunas (nome, cidade), e com dois índices, um na coluna nome e outro na coluna cidade.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-213">The following figure illustrates the structure of a table with two columns (name, city), and with two indexes, one on the column name, and one on the column city.</span></span>  
  
 <span data-ttu-id="6ce3b-214">![Estrutura de uma tabela com duas colunas e índices.](../../database-engine/media/hekaton-tables-5.gif "Estrutura de uma tabela com duas colunas e índices.")</span><span class="sxs-lookup"><span data-stu-id="6ce3b-214">![Structure of a table with two columns and indexes.](../../database-engine/media/hekaton-tables-5.gif "Structure of a table with two columns and indexes.")</span></span>  
  
 <span data-ttu-id="6ce3b-215">Nesta figura, os nomes John e Jane são transformados em hash no primeiro bucket.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-215">In this figure, the names John and Jane are hashed to the first bucket.</span></span> <span data-ttu-id="6ce3b-216">Susan é transformado em hash no segundo bucket.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-216">Susan is hashed to the second bucket.</span></span> <span data-ttu-id="6ce3b-217">As cidades Beijing e Bogotá são transformadas em hash no primeiro bucket.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-217">The cities Beijing and Bogota are hashed to the first bucket.</span></span> <span data-ttu-id="6ce3b-218">Paris e Praga são transformadas em hash no segundo bucket.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-218">Paris and Prague are hashed to the second bucket.</span></span>  
  
 <span data-ttu-id="6ce3b-219">Desse modo, as cadeias do índice de hash na coluna nome são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-219">Thus, the chains for the hash index on name are as follows:</span></span>  
  
-   <span data-ttu-id="6ce3b-220">Primeiro bucket: (John, Beijing); (John, Paris); (Jane, Praga)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-220">First bucket: (John, Beijing); (John, Paris); (Jane, Prague)</span></span>  
  
-   <span data-ttu-id="6ce3b-221">Segundo bucket: (Susan, Bogotá)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-221">Second bucket: (Susan, Bogota)</span></span>  
  
 <span data-ttu-id="6ce3b-222">As cadeias do índice de cidade são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-222">The chains for the index on city are as follows:</span></span>  
  
-   <span data-ttu-id="6ce3b-223">Primeiro bucket: (John, Beijing), (Susan, Bogotá)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-223">First bucket: (John, Beijing), (Susan, Bogota)</span></span>  
  
-   <span data-ttu-id="6ce3b-224">Segundo bucket: (John, Paris), (Jane, Praga)</span><span class="sxs-lookup"><span data-stu-id="6ce3b-224">Second bucket: (John, Paris), (Jane, Prague)</span></span>  
  
 <span data-ttu-id="6ce3b-225">Um carimbo de data/hora final &#x221e; (infinito) indica que esta é a versão válida atualmente da linha.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-225">An end timestamp &#x221e; (infinity) indicates that this is the currently valid version of the row.</span></span> <span data-ttu-id="6ce3b-226">A linha não foi atualizada nem excluída desde que essa versão de linha foi gravada.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-226">The row has not been updated or deleted since this row version was written.</span></span>  
  
 <span data-ttu-id="6ce3b-227">Para um tempo maior que 200, a tabela contém as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-227">For a time greater than 200, the table contains the following rows:</span></span>  
  
|<span data-ttu-id="6ce3b-228">Nome</span><span class="sxs-lookup"><span data-stu-id="6ce3b-228">Name</span></span>|<span data-ttu-id="6ce3b-229">City</span><span class="sxs-lookup"><span data-stu-id="6ce3b-229">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="6ce3b-230">John</span><span class="sxs-lookup"><span data-stu-id="6ce3b-230">John</span></span>|<span data-ttu-id="6ce3b-231">Pequim</span><span class="sxs-lookup"><span data-stu-id="6ce3b-231">Beijing</span></span>|  
|<span data-ttu-id="6ce3b-232">Jane</span><span class="sxs-lookup"><span data-stu-id="6ce3b-232">Jane</span></span>|<span data-ttu-id="6ce3b-233">Praga</span><span class="sxs-lookup"><span data-stu-id="6ce3b-233">Prague</span></span>|  
  
 <span data-ttu-id="6ce3b-234">Entretanto, qualquer transação ativa com tempo inicial igual a 100 resultará na seguinte versão da tabela:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-234">However, any active transaction with begin time 100 will see the following version of the table:</span></span>  
  
|<span data-ttu-id="6ce3b-235">Nome</span><span class="sxs-lookup"><span data-stu-id="6ce3b-235">Name</span></span>|<span data-ttu-id="6ce3b-236">City</span><span class="sxs-lookup"><span data-stu-id="6ce3b-236">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="6ce3b-237">John</span><span class="sxs-lookup"><span data-stu-id="6ce3b-237">John</span></span>|<span data-ttu-id="6ce3b-238">Paris</span><span class="sxs-lookup"><span data-stu-id="6ce3b-238">Paris</span></span>|  
|<span data-ttu-id="6ce3b-239">Jane</span><span class="sxs-lookup"><span data-stu-id="6ce3b-239">Jane</span></span>|<span data-ttu-id="6ce3b-240">Praga</span><span class="sxs-lookup"><span data-stu-id="6ce3b-240">Prague</span></span>|  
|<span data-ttu-id="6ce3b-241">Susan</span><span class="sxs-lookup"><span data-stu-id="6ce3b-241">Susan</span></span>|<span data-ttu-id="6ce3b-242">Bogotá</span><span class="sxs-lookup"><span data-stu-id="6ce3b-242">Bogata</span></span>|  
  
##  <a name="example-table-and-row-size-computation"></a><a name="bkmk_ExampleComputation"></a> <span data-ttu-id="6ce3b-243">Exemplo: cálculo do tamanho da tabela e da linha</span><span class="sxs-lookup"><span data-stu-id="6ce3b-243">Example: Table and Row Size Computation</span></span>  
 <span data-ttu-id="6ce3b-244">Para índices de hash, o número de buckets real é arredondado até a potência mais próxima de 2.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-244">For hash indexes, the actual bucket count is rounded up to the nearest power of 2.</span></span> <span data-ttu-id="6ce3b-245">Por exemplo, se o bucket_count especificado for 100000, o número real de buckets para o índice será 131072.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-245">For example, if the specified bucket_count is 100000, the actual bucket count for the index is 131072.</span></span>  
  
 <span data-ttu-id="6ce3b-246">Considere uma tabela Orders com a seguinte definição:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-246">Consider an Orders table with the following definition:</span></span>  
  
```sql  
CREATE TABLE dbo.Orders (  
     OrderID int NOT NULL   
           PRIMARY KEY NONCLUSTERED,  
     CustomerID int NOT NULL   
           INDEX IX_CustomerID HASH WITH (BUCKET_COUNT=10000),  
     OrderDate datetime NOT NULL,  
     OrderDescription nvarchar(1000)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
```  
  
 <span data-ttu-id="6ce3b-247">Observe que esta tabela tem um índice de hash e um índice não clusterizado (a chave primária).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-247">Notice that this table has one hash index and a nonclustered index (the primary key).</span></span> <span data-ttu-id="6ce3b-248">Ela também tem três colunas de comprimento fixo e uma coluna de comprimento variável, com uma das colunas sendo NULLable (OrderDescription).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-248">It also has three fixed-length columns and one variable-length column, with one of the columns being NULLable (OrderDescription).</span></span> <span data-ttu-id="6ce3b-249">Vamos supor que a tabela Orders tenha 8379 linhas e que o comprimento médio dos valores na coluna OrderDescription seja de 78 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-249">Let's assume the Orders table has 8379 rows, and the average length of the values in the OrderDescription column is 78 characters.</span></span>  
  
 <span data-ttu-id="6ce3b-250">Para determinar o tamanho da tabela, primeiro determine o tamanho dos índices.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-250">To determine the table size, first determine the size of the indexes.</span></span> <span data-ttu-id="6ce3b-251">O bucket_count para ambos os índices é especificado como 10000.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-251">The bucket_count for both indexes is specified as 10000.</span></span> <span data-ttu-id="6ce3b-252">Isso é arredondado para a potência mais próxima de 2: 16384.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-252">This is rounded up to the nearest power of 2: 16384.</span></span> <span data-ttu-id="6ce3b-253">Consequentemente, o tamanho total dos índices da tabela Orders é:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-253">Therefore, the total size of the indexes for the Orders table is:</span></span>  
  
```  
8 * 16384 = 131072 bytes  
```  
  
 <span data-ttu-id="6ce3b-254">O que sobra é o tamanho dos dados da tabela, que é</span><span class="sxs-lookup"><span data-stu-id="6ce3b-254">What remains is the table data size, which is,</span></span>  
  
```  
[row size] * [row count] = [row size] * 8379  
```  
  
 <span data-ttu-id="6ce3b-255">(A tabela de exemplo tem 8379 linhas.) Agora, temos:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-255">(The example table has 8379 rows.) Now, we have:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices] = 24 + 8 * 1 = 32 bytes  
```  
  
 <span data-ttu-id="6ce3b-256">Em seguida, vamos calcular o [tamanho real do corpo da linha]:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-256">Next, let's calculate [actual row body size]:</span></span>  
  
-   <span data-ttu-id="6ce3b-257">Colunas do tipo superficial:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-257">Shallow type columns:</span></span>  
  
    ```  
    SUM([size of shallow types]) = 4 [int] + 4 [int] + 8 [datetime] = 16  
    ```  
  
-   <span data-ttu-id="6ce3b-258">O preenchimento da coluna superficial é 0, pois o tamanho total da coluna superficial é par.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-258">Shallow column padding is 0, as the total shallow column size is even.</span></span>  
  
-   <span data-ttu-id="6ce3b-259">Matriz de deslocamento para colunas do tipo profundas:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-259">Offset array for deep type columns:</span></span>  
  
    ```  
    2 + 2 * [number of deep type columns] = 2 + 2 * 1 = 4  
    ```  
  
-   <span data-ttu-id="6ce3b-260">Matriz NULL = 1</span><span class="sxs-lookup"><span data-stu-id="6ce3b-260">NULL array = 1</span></span>  
  
-   <span data-ttu-id="6ce3b-261">Preenchimento da matriz NULL = 1, pois o tamanho da matriz é ímpar e há uma coluna do tipo profunda.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-261">NULL array padding = 1, as the NULL array size is odd and there is a deep type column.</span></span>  
  
-   <span data-ttu-id="6ce3b-262">Preenchimento</span><span class="sxs-lookup"><span data-stu-id="6ce3b-262">Padding</span></span>  
  
    -   <span data-ttu-id="6ce3b-263">8 é o maior requisito de alinhamento.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-263">8 is the largest alignment requirement.</span></span>  
  
    -   <span data-ttu-id="6ce3b-264">O tamanho até agora é 16 + 0 + 4 + 1 + 1 = 22.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-264">Size so far is 16 + 0 + 4 + 1 + 1 = 22.</span></span>  
  
    -   <span data-ttu-id="6ce3b-265">O múltiplo mais próximo de 8 é 24.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-265">Nearest multiple of 8 is 24.</span></span>  
  
    -   <span data-ttu-id="6ce3b-266">O preenchimento total é 24 - 22 = 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-266">Total padding is 24 - 22 = 2 bytes.</span></span>  
  
-   <span data-ttu-id="6ce3b-267">Não há colunas de tipo profundas de comprimento fixo (colunas de tipo profundas de comprimento fixo: 0.).</span><span class="sxs-lookup"><span data-stu-id="6ce3b-267">There are no fixed-length deep type columns (Fixed-length deep type columns: 0.).</span></span>  
  
-   <span data-ttu-id="6ce3b-268">O tamanho real da coluna do tipo profunda é 2 \* 78 = 156.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-268">The actual size of deep type column is 2 \* 78 = 156.</span></span> <span data-ttu-id="6ce3b-269">Uma única coluna do tipo profunda OrderDescription tem o tipo nvarchar.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-269">The single deep type column OrderDescription has type nvarchar.</span></span>  
  
```  
[actual row body size] = 24 + 156 = 180 bytes  
```  
  
 <span data-ttu-id="6ce3b-270">Para concluir o cálculo:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-270">To complete the calculation:</span></span>  
  
```  
[row size] = 32 + 180 = 212 bytes  
[table size] = 8 * 16384 + 212 * 8379 = 131072 + 1776348 = 1907420  
```  
  
 <span data-ttu-id="6ce3b-271">O tamanho total da tabela na memória é de aproximadamente 2 megabytes.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-271">Total table size in memory is thus approximately 2 megabytes.</span></span> <span data-ttu-id="6ce3b-272">Isso não conta para a possível sobrecarga incorrida pela alocação de memória, bem como para qualquer controle de versão de linha exigido para as transações que acessam essa tabela.</span><span class="sxs-lookup"><span data-stu-id="6ce3b-272">This does not account for potential overhead incurred by memory allocation as well as any row versioning required for the transactions accessing this table.</span></span>  
  
 <span data-ttu-id="6ce3b-273">A memória real alocada para essa tabela, e usada por ela, bem como seus índices, podem ser obtidos por meio da seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="6ce3b-273">The actual memory allocated for and used by this table and its indexes can be obtained through the following query:</span></span>  
  
```sql  
select * from sys.dm_db_xtp_table_memory_stats  
where object_id = object_id('dbo.Orders')  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ce3b-274">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ce3b-274">See Also</span></span>  
 [<span data-ttu-id="6ce3b-275">Memory-Optimized Tables</span><span class="sxs-lookup"><span data-stu-id="6ce3b-275">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
