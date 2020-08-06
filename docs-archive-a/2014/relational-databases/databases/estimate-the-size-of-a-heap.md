---
title: Estimar o tamanho de um heap | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- estimating heap size
- size [SQL Server], heap
- space [SQL Server], indexes
- heaps
ms.assetid: 81fd5ec9-ce0f-4c2c-8ba0-6c483cea6c75
author: stevestein
ms.author: sstein
ms.openlocfilehash: f32432d07a9731d849ceb793daf209cfc505b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583612"
---
# <a name="estimate-the-size-of-a-heap"></a><span data-ttu-id="2d571-102">Estimar o tamanho de um heap</span><span class="sxs-lookup"><span data-stu-id="2d571-102">Estimate the Size of a Heap</span></span>
  <span data-ttu-id="2d571-103">Você pode usar as seguintes etapas para estimar a quantidade de espaço exigida para armazenar dados em um heap:</span><span class="sxs-lookup"><span data-stu-id="2d571-103">You can use the following steps to estimate the amount of space that is required to store data in a heap:</span></span>  
  
1.  <span data-ttu-id="2d571-104">Especifique o número de linhas que estarão presentes na tabela:</span><span class="sxs-lookup"><span data-stu-id="2d571-104">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="2d571-105">***Num_Rows***  = número de linhas na tabela</span><span class="sxs-lookup"><span data-stu-id="2d571-105">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="2d571-106">Especifique o número de colunas de comprimento fixo e variável e calcule o espaço necessário para o seu armazenamento:</span><span class="sxs-lookup"><span data-stu-id="2d571-106">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="2d571-107">Calcule o espaço que cada um desses grupos de colunas ocupa dentro da linha de dados.</span><span class="sxs-lookup"><span data-stu-id="2d571-107">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="2d571-108">O tamanho de uma coluna depende do tipo de dados e da especificação de comprimento.</span><span class="sxs-lookup"><span data-stu-id="2d571-108">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="2d571-109">***Num_Cols***  = número total de colunas (comprimento fixo e tamanho variável)</span><span class="sxs-lookup"><span data-stu-id="2d571-109">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="2d571-110">***Fixed_Data_Size***  = tamanho total em bytes de todas as colunas de tamanho fixo</span><span class="sxs-lookup"><span data-stu-id="2d571-110">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="2d571-111">***Num_Variable_Cols***  = número de colunas de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="2d571-111">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="2d571-112">***Max_Var_Size*** = total máximo em bytes de todas as colunas de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="2d571-112">***Max_Var_Size***  = maximum total byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="2d571-113">Parte da linha, conhecida como bitmap nulo, é reservada para gerenciar a nulabilidade da coluna.</span><span class="sxs-lookup"><span data-stu-id="2d571-113">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="2d571-114">Calcule seu tamanho:</span><span class="sxs-lookup"><span data-stu-id="2d571-114">Calculate its size:</span></span>  
  
     <span data-ttu-id="2d571-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="2d571-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="2d571-116">Somente a parte do inteiro dessa expressão deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="2d571-116">Only the integer part of this expression should be used.</span></span> <span data-ttu-id="2d571-117">Descarte todo o restante.</span><span class="sxs-lookup"><span data-stu-id="2d571-117">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="2d571-118">Calcule o tamanho dos dados de comprimento variável:</span><span class="sxs-lookup"><span data-stu-id="2d571-118">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="2d571-119">Se houver colunas de comprimento variável na tabela, determine quanto espaço será usado para armazenar as colunas dentro da linha:</span><span class="sxs-lookup"><span data-stu-id="2d571-119">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="2d571-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="2d571-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="2d571-121">Os bytes adicionados a ***Max_Var_Size*** servem para acompanhar cada coluna de tamanho variável.</span><span class="sxs-lookup"><span data-stu-id="2d571-121">The bytes added to ***Max_Var_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="2d571-122">Essa fórmula presume que todas as colunas de comprimento variável estão 100% completas.</span><span class="sxs-lookup"><span data-stu-id="2d571-122">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="2d571-123">Se você prevê que um percentual menor do espaço de armazenamento da coluna de tamanho variável será usada, poderá ajustar o valor ***Max_Var_Size*** de acordo com esse percentual para obter uma estimativa mais precisa do tamanho geral da tabela.</span><span class="sxs-lookup"><span data-stu-id="2d571-123">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d571-124">Você pode combinar as colunas `varchar`, `nvarchar`, `varbinary` ou `sql_variant` que fazem com que a largura total definida da tabela exceda 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="2d571-124">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="2d571-125">O comprimento de cada uma dessas colunas ainda deve estar dentro do limite de 8.000 bytes para uma `varchar` coluna, `nvarchar,``varbinary` ou `sql_variant` .</span><span class="sxs-lookup"><span data-stu-id="2d571-125">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `nvarchar,``varbinary`, or `sql_variant` column.</span></span> <span data-ttu-id="2d571-126">Entretanto, as larguras combinadas podem exceder o limite de 8.060 bytes em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2d571-126">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="2d571-127">Se não houver colunas de tamanho variável, defina ***Variable_Data_Size*** como 0.</span><span class="sxs-lookup"><span data-stu-id="2d571-127">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="2d571-128">Calcule o tamanho total da linha:</span><span class="sxs-lookup"><span data-stu-id="2d571-128">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="2d571-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="2d571-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="2d571-130">O valor 4 na fórmula é a sobrecarga do cabeçalho da linha de dados.</span><span class="sxs-lookup"><span data-stu-id="2d571-130">The value 4 in the formula is the row header overhead of the data row.</span></span>  
  
6.  <span data-ttu-id="2d571-131">Calcule o número de linhas por página (8.096 bytes livres por página):</span><span class="sxs-lookup"><span data-stu-id="2d571-131">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="2d571-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="2d571-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="2d571-133">Como as linhas não se estendem por mais de uma página, o número de linhas por página deve ser arredondado para baixo, para a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="2d571-133">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="2d571-134">O valor 2 na fórmula é para a entrada da linha na matriz de slot da página.</span><span class="sxs-lookup"><span data-stu-id="2d571-134">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
7.  <span data-ttu-id="2d571-135">Calcule o número de páginas necessário para armazenar todas as linhas:</span><span class="sxs-lookup"><span data-stu-id="2d571-135">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="2d571-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span><span class="sxs-lookup"><span data-stu-id="2d571-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span></span>  
  
     <span data-ttu-id="2d571-137">O número de páginas estimado deve ser arredondado para cima, até a página inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="2d571-137">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
8.  <span data-ttu-id="2d571-138">Calcule a quantidade de espaço necessária para armazenar os dados no heap (total de 8.192 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="2d571-138">Calculate the amount of space that is required to store the data in the heap (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="2d571-139">Tamanho do heap (bytes) = 8192 x ***Num_Pages***</span><span class="sxs-lookup"><span data-stu-id="2d571-139">Heap size (bytes) = 8192 x ***Num_Pages***</span></span>  
  
 <span data-ttu-id="2d571-140">Esse cálculo não considera o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d571-140">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="2d571-141">Particionamento</span><span class="sxs-lookup"><span data-stu-id="2d571-141">Partitioning</span></span>  
  
     <span data-ttu-id="2d571-142">A sobrecarga de espaço do particionamento é mínima, mas complexa para ser calculada.</span><span class="sxs-lookup"><span data-stu-id="2d571-142">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="2d571-143">Não é importante incluí-la.</span><span class="sxs-lookup"><span data-stu-id="2d571-143">It is not important to include.</span></span>  
  
-   <span data-ttu-id="2d571-144">Páginas de alocação</span><span class="sxs-lookup"><span data-stu-id="2d571-144">Allocation pages</span></span>  
  
     <span data-ttu-id="2d571-145">Há pelo menos uma página de IAM usada para rastrear as páginas alocadas a um heap, mas a sobrecarga de espaço é mínima e não há nenhum algoritmo para calcular de forma determinista exatamente quantas páginas de IAM serão usadas.</span><span class="sxs-lookup"><span data-stu-id="2d571-145">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="2d571-146">Valores de LOB (Objeto Grande)</span><span class="sxs-lookup"><span data-stu-id="2d571-146">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="2d571-147">O algoritmo para determinar exatamente quanto espaço será usado para armazenar os tipos de dados LOB `varchar(max)` ,,,, `varbinary(max)` `nvarchar(max)` `text` **ntextxml**, e `image` os valores é complexo.</span><span class="sxs-lookup"><span data-stu-id="2d571-147">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, **ntextxml**, and `image` values is complex.</span></span> <span data-ttu-id="2d571-148">É suficiente apenas para adicionar o tamanho médio dos valores de LOB esperados e adicioná-lo ao tamanho do heap.</span><span class="sxs-lookup"><span data-stu-id="2d571-148">It is sufficient to just add the average size of the LOB values that are expected and add that to the total heap size.</span></span>  
  
-   <span data-ttu-id="2d571-149">Compactação</span><span class="sxs-lookup"><span data-stu-id="2d571-149">Compression</span></span>  
  
     <span data-ttu-id="2d571-150">Não é possível pré-calcular o tamanho de um heap compactado.</span><span class="sxs-lookup"><span data-stu-id="2d571-150">You cannot pre-calculate the size of a compressed heap.</span></span>  
  
-   <span data-ttu-id="2d571-151">Colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="2d571-151">Sparse columns</span></span>  
  
     <span data-ttu-id="2d571-152">Para obter informações sobre os requisitos de espaço de colunas esparsas, consulte [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2d571-152">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d571-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d571-153">See Also</span></span>  
 <span data-ttu-id="2d571-154">[Heaps &#40;Tabelas sem índices clusterizados&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-154">[Heaps &#40;Tables without Clustered Indexes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span></span>  
 <span data-ttu-id="2d571-155">[Índices clusterizados e não clusterizados descritos](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-155">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="2d571-156">[Criar índices clusterizados](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-156">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="2d571-157">[Criar índices não clusterizados](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-157">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="2d571-158">[Estimar o tamanho de uma tabela](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-158">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="2d571-159">[Estimar o tamanho de um índice clusterizado](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-159">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="2d571-160">[Estimar o tamanho de um índice não clusterizado](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="2d571-160">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 [<span data-ttu-id="2d571-161">Estimar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="2d571-161">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
