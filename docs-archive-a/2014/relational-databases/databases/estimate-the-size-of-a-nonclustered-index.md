---
title: Estimar o tamanho de um índice não clusterizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: c183b0e4-ef4c-4bfc-8575-5ac219c25b0a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 097c0e5568ba17b12f83d09e347eb3bf8b0bd7da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683546"
---
# <a name="estimate-the-size-of-a-nonclustered-index"></a><span data-ttu-id="21e20-102">Estimar o tamanho de um índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="21e20-102">Estimate the Size of a Nonclustered Index</span></span>
  <span data-ttu-id="21e20-103">Siga estas etapas para estimar a quantidade de espaço necessária para armazenar um índice não clusterizado:</span><span class="sxs-lookup"><span data-stu-id="21e20-103">Follow these steps to estimate the amount of space that is required to store a nonclustered index:</span></span>  
  
1.  <span data-ttu-id="21e20-104">Calcule as variáveis a serem usadas nas etapas 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="21e20-104">Calculate variables for use in steps 2 and 3.</span></span>  
  
2.  <span data-ttu-id="21e20-105">Calcule o espaço usado para armazenar informações de índice no nível folha do índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-105">Calculate the space used to store index information in the leaf level of the nonclustered index.</span></span>  
  
3.  <span data-ttu-id="21e20-106">Calcule o espaço usado para armazenar informações de índice nos níveis não folha do índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-106">Calculate the space used to store index information in the non-leaf levels of the nonclustered index.</span></span>  
  
4.  <span data-ttu-id="21e20-107">Some os valores calculados.</span><span class="sxs-lookup"><span data-stu-id="21e20-107">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-variables-for-use-in-steps-2-and-3"></a><span data-ttu-id="21e20-108">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="21e20-108">Step 1.</span></span> <span data-ttu-id="21e20-109">Calcule as variáveis a serem usadas nas etapas 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="21e20-109">Calculate Variables for Use in Steps 2 and 3</span></span>  
 <span data-ttu-id="21e20-110">Você pode usar as seguintes etapas para calcular as variáveis a serem usadas para estimar a quantidade de espaço necessária para armazenar os níveis superiores do índice.</span><span class="sxs-lookup"><span data-stu-id="21e20-110">You can use the following steps to calculate variables that are used to estimate the amount of space that is required to store the upper levels of the index.</span></span>  
  
1.  <span data-ttu-id="21e20-111">Especifique o número de linhas que estarão presentes na tabela:</span><span class="sxs-lookup"><span data-stu-id="21e20-111">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="21e20-112">***Num_Rows***  = número de linhas na tabela</span><span class="sxs-lookup"><span data-stu-id="21e20-112">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="21e20-113">Especifique o número de colunas de comprimento fixo e variável na chave do índice e calcule o espaço necessário para seu armazenamento:</span><span class="sxs-lookup"><span data-stu-id="21e20-113">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="21e20-114">As colunas de chave de um índice podem incluir colunas de comprimento fixo e variável.</span><span class="sxs-lookup"><span data-stu-id="21e20-114">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="21e20-115">Para estimar o tamanho da linha de índice no nível interior, calcule o espaço que cada um desses grupos de colunas ocupa na linha do índice.</span><span class="sxs-lookup"><span data-stu-id="21e20-115">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="21e20-116">O tamanho de uma coluna depende do tipo de dados e da especificação de comprimento.</span><span class="sxs-lookup"><span data-stu-id="21e20-116">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="21e20-117">***Num_Key_Cols***  = número total de colunas de chaves (tamanho fixo e tamanho variável)</span><span class="sxs-lookup"><span data-stu-id="21e20-117">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="21e20-118">***Fixed_Key_Size***  = tamanho total em bytes de todas as colunas de chaves de tamanho fixo</span><span class="sxs-lookup"><span data-stu-id="21e20-118">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="21e20-119">***Num_Variable_Key_Cols***  = número de colunas de chaves de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="21e20-119">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="21e20-120">***Max_Var_Key_Size***  = tamanho máximo em bytes de todas as colunas de chaves de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="21e20-120">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
3.  <span data-ttu-id="21e20-121">Considere o localizador de linha de dados que é necessário se o índice for não exclusivo:</span><span class="sxs-lookup"><span data-stu-id="21e20-121">Account for the data row locator that is required if the index is nonunique:</span></span>  
  
     <span data-ttu-id="21e20-122">Se o índice não clusterizado for não exclusivo, o localizador de linha de dados será combinado com a chave de índice não clusterizado para produzir um valor de chave exclusivo para cada linha.</span><span class="sxs-lookup"><span data-stu-id="21e20-122">If the nonclustered index is nonunique, the data row locator is combined with the nonclustered index key to produce a unique key value for every row.</span></span>  
  
     <span data-ttu-id="21e20-123">Se o índice não clusterizado estiver em um heap, o localizador de linha de dados será o RID do heap.</span><span class="sxs-lookup"><span data-stu-id="21e20-123">If the nonclustered index is over a heap, the data row locator is the heap RID.</span></span> <span data-ttu-id="21e20-124">Este é um tamanho de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="21e20-124">This is a size of 8 bytes.</span></span>  
  
     <span data-ttu-id="21e20-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="21e20-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="21e20-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="21e20-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="21e20-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="21e20-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span></span>  
  
     <span data-ttu-id="21e20-128">Se o índice não clusterizado estiver em um índice clusterizado, o localizador de linha de dados será a chave de clustering.</span><span class="sxs-lookup"><span data-stu-id="21e20-128">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="21e20-129">As colunas que devem ser combinadas com a chave de índice não clusterizado são as colunas na chave de clustering que ainda não estiverem presentes no conjunto de colunas de chave de índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-129">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="21e20-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + número de colunas de chave de clustering não presentes no conjunto de colunas de chave de índice não clusterizado (+ 1 se o índice clusterizado for não exclusivo)</span><span class="sxs-lookup"><span data-stu-id="21e20-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="21e20-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + tamanho total de bytes de colunas de chave de clustering de tamanho fixo não presentes no conjunto de colunas de chave de índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="21e20-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="21e20-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + número de colunas de chave de clustering de tamanho variável não presentes no conjunto de colunas de chave de índice não clusterizado (+ 1 se o índice clusterizado for não exclusivo)</span><span class="sxs-lookup"><span data-stu-id="21e20-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="21e20-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + tamanho máximo de bytes de colunas de chave de clustering de tamanho variável não presentes no conjunto de colunas de chave de índice não clusterizado (+ 4 se o índice clusterizado for não exclusivo)</span><span class="sxs-lookup"><span data-stu-id="21e20-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
4.  <span data-ttu-id="21e20-134">Parte da linha, conhecida como bitmap nulo, pode ser reservada para gerenciar a anulabilidade da coluna.</span><span class="sxs-lookup"><span data-stu-id="21e20-134">Part of the row, known as the null bitmap, may be reserved to manage column nullability.</span></span> <span data-ttu-id="21e20-135">Calcule seu tamanho:</span><span class="sxs-lookup"><span data-stu-id="21e20-135">Calculate its size:</span></span>  
  
     <span data-ttu-id="21e20-136">Se houver colunas que possam ser anuladas na chave do índice, inclusive qualquer coluna de chave de clustering necessária, conforme descrito na etapa 1.3, parte da linha de índice será reservada para o bitmap nulo.</span><span class="sxs-lookup"><span data-stu-id="21e20-136">If there are nullable columns in the index key, including any necessary clustering key columns as described in Step 1.3, part of the index row is reserved for the null bitmap.</span></span>  
  
     <span data-ttu-id="21e20-137">***Index_Null_Bitmap***  = 2 + ([número de colunas na linha de índice + 7] / 8)</span><span class="sxs-lookup"><span data-stu-id="21e20-137">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="21e20-138">Somente a parte do inteiro da expressão anterior deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="21e20-138">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="21e20-139">Descarte todo o restante.</span><span class="sxs-lookup"><span data-stu-id="21e20-139">Discard any remainder.</span></span>  
  
     <span data-ttu-id="21e20-140">Se não houver colunas de chave anuláveis, defina ***Index_Null_Bitmap*** como 0.</span><span class="sxs-lookup"><span data-stu-id="21e20-140">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
5.  <span data-ttu-id="21e20-141">Calcule o tamanho dos dados de comprimento variável:</span><span class="sxs-lookup"><span data-stu-id="21e20-141">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="21e20-142">Se houver colunas de comprimento variável na chave do índice, incluindo qualquer coluna de chave de índice clusterizado necessária, determine quanto espaço será usado para armazenar as colunas dentro da linha de índice:</span><span class="sxs-lookup"><span data-stu-id="21e20-142">If there are variable-length columns in the index key, including any necessary clustered index key columns, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="21e20-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="21e20-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="21e20-144">Os bytes adicionados a ***Max_Var_Key_Size*** servem para acompanhar cada fórmula de coluna variável. Essa fórmula presume que todas as colunas de tamanho variável estão 100% completas.</span><span class="sxs-lookup"><span data-stu-id="21e20-144">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="21e20-145">Se você se previr que um percentual menor do espaço de armazenamento de coluna de tamanho variável será usado, poderá ajustar o valor ***Max_Var_Key_Size*** com esse percentual para obter uma estimativa mais precisa do tamanho geral da tabela.</span><span class="sxs-lookup"><span data-stu-id="21e20-145">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="21e20-146">Se não houver colunas de tamanho variável, defina ***Variable_Key_Size*** como 0.</span><span class="sxs-lookup"><span data-stu-id="21e20-146">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="21e20-147">Calcule o tamanho da linha de índice:</span><span class="sxs-lookup"><span data-stu-id="21e20-147">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="21e20-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (para a sobrecarga de cabeçalho de linha de uma linha de índice) + 6 (para o ponteiro de ID da página filho)</span><span class="sxs-lookup"><span data-stu-id="21e20-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
7.  <span data-ttu-id="21e20-149">Calcule o número de linhas de índice por página (8.096 bytes livres por página):</span><span class="sxs-lookup"><span data-stu-id="21e20-149">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="21e20-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="21e20-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="21e20-151">Como as linhas de índice não se estendem por mais de uma página, o número de linhas de índice por página deve ser arredondado para baixo, até a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="21e20-151">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="21e20-152">O 2 na fórmula é para a entrada da linha na matriz de slots da página.</span><span class="sxs-lookup"><span data-stu-id="21e20-152">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information-in-the-leaf-level"></a><span data-ttu-id="21e20-153">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="21e20-153">Step 2.</span></span> <span data-ttu-id="21e20-154">Calcule o espaço usado para armazenar informações de índice no nível folha</span><span class="sxs-lookup"><span data-stu-id="21e20-154">Calculate the Space Used to Store Index Information in the Leaf Level</span></span>  
 <span data-ttu-id="21e20-155">Você pode usar as etapas a seguir para estimar a quantidade de espaço necessária para armazenar o nível folha do índice.</span><span class="sxs-lookup"><span data-stu-id="21e20-155">You can use the following steps to estimate the amount of space that is required to store the leaf level of the index.</span></span> <span data-ttu-id="21e20-156">Você precisará dos valores provenientes da etapa 1 para completar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="21e20-156">You will need the values preserved from Step 1 to complete this step.</span></span>  
  
1.  <span data-ttu-id="21e20-157">Especifique o número de colunas de comprimento fixo e variável no nível folha e calcule o espaço necessário para seu armazenamento:</span><span class="sxs-lookup"><span data-stu-id="21e20-157">Specify the number of fixed-length and variable-length columns at the leaf level and calculate the space that is required for their storage:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21e20-158">Você pode ampliar um índice não clusterizado incluindo colunas não chave, além das colunas de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="21e20-158">You can extend a nonclustered index by including nonkey columns in addition to the index key columns.</span></span> <span data-ttu-id="21e20-159">Essas colunas adicionais só são armazenadas no nível folha do índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-159">These additional columns are only stored at the leaf level of the nonclustered index.</span></span> <span data-ttu-id="21e20-160">Para obter mais informações, consulte [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="21e20-160">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21e20-161">Você pode combinar as colunas `varchar`, `nvarchar`, `varbinary` ou `sql_variant` que fazem com que a largura total definida da tabela exceda 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="21e20-161">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="21e20-162">O comprimento de cada uma dessas colunas ainda deve ficar dentro do limite de 8.000 bytes para uma coluna `varchar`, `varbinary` ou `sql_variant` e de 4.000 bytes para colunas `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="21e20-162">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="21e20-163">Entretanto, as larguras combinadas podem exceder o limite de 8.060 bytes em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="21e20-163">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span> <span data-ttu-id="21e20-164">Isso também se aplica a linhas de folha de índice não clusterizado que têm colunas incluídas.</span><span class="sxs-lookup"><span data-stu-id="21e20-164">This also applies to nonclustered index leaf rows that have included columns.</span></span>  
  
     <span data-ttu-id="21e20-165">Se o índice não clusterizado não tiver nenhuma coluna incluída, use os valores da Etapa 1, incluindo qualquer modificação determinada na etapa 1.3:</span><span class="sxs-lookup"><span data-stu-id="21e20-165">If the nonclustered index does not have any included columns, use the values from Step 1, including any modifications determined in Step 1.3:</span></span>  
  
     <span data-ttu-id="21e20-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="21e20-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span></span>  
  
     <span data-ttu-id="21e20-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="21e20-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span></span>  
  
     <span data-ttu-id="21e20-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="21e20-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span></span>  
  
     <span data-ttu-id="21e20-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="21e20-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="21e20-170">Se o índice não clusterizado tiver colunas incluídas, adicione os valores apropriados aos valores da etapa 1, inclusive qualquer modificação na etapa 1.3.</span><span class="sxs-lookup"><span data-stu-id="21e20-170">If the nonclustered index does have included columns, add the appropriate values to the values from Step 1, including any modifications in Step 1.3.</span></span> <span data-ttu-id="21e20-171">O tamanho de uma coluna depende do tipo de dados e da especificação de comprimento.</span><span class="sxs-lookup"><span data-stu-id="21e20-171">The size of a column depends on the data type and length specification.</span></span> <span data-ttu-id="21e20-172">Para obter mais informações, veja [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21e20-172">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
     <span data-ttu-id="21e20-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + número de colunas incluídas</span><span class="sxs-lookup"><span data-stu-id="21e20-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + number of included columns</span></span>  
  
     <span data-ttu-id="21e20-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + tamanho total de bytes de colunas de tamanho fixo incluídas</span><span class="sxs-lookup"><span data-stu-id="21e20-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length included columns</span></span>  
  
     <span data-ttu-id="21e20-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + número de colunas de tamanho variável incluídas</span><span class="sxs-lookup"><span data-stu-id="21e20-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span></span>  
  
     <span data-ttu-id="21e20-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + tamanho máximo em bytes das colunas de tamanho variável incluídas</span><span class="sxs-lookup"><span data-stu-id="21e20-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length included columns</span></span>  
  
2.  <span data-ttu-id="21e20-177">Considere o localizador da linha de dados:</span><span class="sxs-lookup"><span data-stu-id="21e20-177">Account for the data row locator:</span></span>  
  
     <span data-ttu-id="21e20-178">Se o índice não clusterizado for não exclusivo, a sobrecarga para o localizador da linha de dados já terá sido considerada na etapa 1.3 e nenhuma modificação adicional será necessária.</span><span class="sxs-lookup"><span data-stu-id="21e20-178">If the nonclustered index is nonunique, the overhead for the data row locator has already been considered in Step 1.3 and no additional modifications are required.</span></span> <span data-ttu-id="21e20-179">Vá para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="21e20-179">Go to the next step.</span></span>  
  
     <span data-ttu-id="21e20-180">Se o índice não clusterizado for exclusivo, o localizador de linha de dados deverá ser considerado em todas as linhas no nível folha.</span><span class="sxs-lookup"><span data-stu-id="21e20-180">If the nonclustered index is unique, the data row locator must be accounted for in all rows at the leaf level.</span></span>  
  
     <span data-ttu-id="21e20-181">Se o índice não clusterizado estiver em um heap, o localizador da linha de dados será o RID do heap (tamanho de 8 bytes).</span><span class="sxs-lookup"><span data-stu-id="21e20-181">If the nonclustered index is over a heap, the data row locator is the heap RID (size 8 bytes).</span></span>  
  
     <span data-ttu-id="21e20-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="21e20-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="21e20-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="21e20-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="21e20-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="21e20-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span></span>  
  
     <span data-ttu-id="21e20-185">Se o índice não clusterizado estiver em um índice clusterizado, o localizador de linha de dados será a chave de clustering.</span><span class="sxs-lookup"><span data-stu-id="21e20-185">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="21e20-186">As colunas que devem ser combinadas com a chave de índice não clusterizado são as colunas na chave de clustering que ainda não estiverem presentes no conjunto de colunas de chave de índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-186">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="21e20-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + número de colunas de chave de clustering não presentes no conjunto de colunas de chave de índice não clusterizado (+ 1 se o índice clusterizado for não exclusivo)</span><span class="sxs-lookup"><span data-stu-id="21e20-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="21e20-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + número de colunas de chave de clustering não presentes no conjunto de colunas de chave de índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="21e20-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + number of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="21e20-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + número de colunas de chave de clustering de tamanho variável não presentes no conjunto de colunas de chave de índice não clusterizado (+ 1 se o índice clusterizado for não exclusivo)</span><span class="sxs-lookup"><span data-stu-id="21e20-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="21e20-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + tamanho em bytes das colunas de chave de clustering de tamanho variável não presentes no conjunto de colunas de chave de índice não clusterizado (+ 4 se o índice clusterizado for não exclusivo)</span><span class="sxs-lookup"><span data-stu-id="21e20-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + size in bytes of the variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
3.  <span data-ttu-id="21e20-191">Calcule o tamanho do bitmap nulo:</span><span class="sxs-lookup"><span data-stu-id="21e20-191">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="21e20-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="21e20-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="21e20-193">Somente a parte do inteiro da expressão anterior deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="21e20-193">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="21e20-194">Descarte todo o restante.</span><span class="sxs-lookup"><span data-stu-id="21e20-194">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="21e20-195">Calcule o tamanho dos dados de comprimento variável:</span><span class="sxs-lookup"><span data-stu-id="21e20-195">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="21e20-196">Se houver colunas de comprimento variável na chave de índice, inclusive qualquer coluna de chave de clustering necessária, como anteriormente descrito nas Etapa 2.2, determine quanto espaço é usado para armazenar as colunas dentro da linha de índice:</span><span class="sxs-lookup"><span data-stu-id="21e20-196">If there are variable-length columns in the index key, including any necessary clustering key columns as described previously in Step 2.2, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="21e20-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span><span class="sxs-lookup"><span data-stu-id="21e20-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span></span>  
  
     <span data-ttu-id="21e20-198">Os bytes adicionados a ***Max_Var_Key_Size*** servem para acompanhar cada fórmula de coluna variável. Essa fórmula presume que todas as colunas de tamanho variável estão 100% completas.</span><span class="sxs-lookup"><span data-stu-id="21e20-198">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="21e20-199">Se você se previr que um percentual menor do espaço de armazenamento da coluna de tamanho variável será usado, poderá ajustar o valor ***Max_Var_Leaf_Size*** com esse percentual para obter uma estimativa mais precisa do tamanho geral da tabela.</span><span class="sxs-lookup"><span data-stu-id="21e20-199">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Leaf_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="21e20-200">Se não houver colunas de tamanho variável, defina ***Variable_Leaf_Size*** como 0.</span><span class="sxs-lookup"><span data-stu-id="21e20-200">If there are no variable-length columns, set ***Variable_Leaf_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="21e20-201">Calcule o tamanho da linha de índice:</span><span class="sxs-lookup"><span data-stu-id="21e20-201">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="21e20-202">***Leaf_Row_Size***   =  ***Fixed_Leaf_Size***  +  ***Variable_Leaf_Size***  +  ***Leaf_Null_Bitmap*** + 1 (para sobrecarga de cabeçalho de linha de uma linha de índice) + 6 (para o ponteiro de ID de página filho)</span><span class="sxs-lookup"><span data-stu-id="21e20-202">***Leaf_Row_Size***  = ***Fixed_Leaf_Size*** + ***Variable_Leaf_Size*** + ***Leaf_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="21e20-203">Calcule o número de linhas de índice por página (8.096 bytes livres por página):</span><span class="sxs-lookup"><span data-stu-id="21e20-203">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="21e20-204">***Leaf_Rows_Per_Page***  = 8.096 / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="21e20-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="21e20-205">Como as linhas de índice não se estendem por mais de uma página, o número de linhas de índice por página deve ser arredondado para baixo, até a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="21e20-205">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="21e20-206">O 2 na fórmula é para a entrada da linha na matriz de slots da página.</span><span class="sxs-lookup"><span data-stu-id="21e20-206">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="21e20-207">Calcule o número de linhas livres reservadas por página, com base no [fator de preenchimento](../indexes/specify-fill-factor-for-an-index.md) especificado:</span><span class="sxs-lookup"><span data-stu-id="21e20-207">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="21e20-208">***Free_Rows_Per_Page***  = 8.096 x ([100 - ***Fill_Factor***] / 100) / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="21e20-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="21e20-209">O fator de preenchimento usado no cálculo é um valor inteiro, em vez de uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="21e20-209">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="21e20-210">Como as linhas não se estendem por mais de uma página, o número de linhas por página deve ser arredondado para baixo, para a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="21e20-210">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="21e20-211">À medida que o fator de preenchimento aumenta, mais dados são armazenados em cada página e haverá menos páginas.</span><span class="sxs-lookup"><span data-stu-id="21e20-211">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="21e20-212">O 2 na fórmula é para a entrada da linha na matriz de slots da página.</span><span class="sxs-lookup"><span data-stu-id="21e20-212">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
8.  <span data-ttu-id="21e20-213">Calcule o número de páginas necessário para armazenar todas as linhas:</span><span class="sxs-lookup"><span data-stu-id="21e20-213">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="21e20-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="21e20-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="21e20-215">O número de páginas estimado deve ser arredondado para cima, até a página inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="21e20-215">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
9. <span data-ttu-id="21e20-216">Calcule o tamanho do índice (total de 8.912 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="21e20-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="21e20-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="21e20-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-3-calculate-the-space-used-to-store-index-information-in-the-non-leaf-levels"></a><span data-ttu-id="21e20-218">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="21e20-218">Step 3.</span></span> <span data-ttu-id="21e20-219">Calcule o espaço usado para armazenar informações de índice nos níveis não folha</span><span class="sxs-lookup"><span data-stu-id="21e20-219">Calculate the Space Used to Store Index Information in the Non-leaf Levels</span></span>  
 <span data-ttu-id="21e20-220">Siga estas etapas para estimar a quantidade de espaço necessária para armazenar os níveis intermediário e raiz do índice.</span><span class="sxs-lookup"><span data-stu-id="21e20-220">Follow these steps to estimate the amount of space that is required to store the intermediate and root levels of the index.</span></span> <span data-ttu-id="21e20-221">Você precisará dos valores preservados das etapas 1 e 3 para concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="21e20-221">You will need the values preserved from steps 2 and 3 to complete this step.</span></span>  
  
1.  <span data-ttu-id="21e20-222">Calcule o número de níveis não folha no índice:</span><span class="sxs-lookup"><span data-stu-id="21e20-222">Calculate the number of non-leaf levels in the index:</span></span>  
  
     <span data-ttu-id="21e20-223">***Níveis não folha*** = 1 + Index_Rows_Per_Page de log (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="21e20-223">***Non-leaf Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="21e20-224">Arredonde esse valor até o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="21e20-224">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="21e20-225">Esse valor não inclui o nível folha do índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-225">This value does not include the leaf level of the nonclustered index.</span></span>  
  
2.  <span data-ttu-id="21e20-226">Calcule o número de páginas não folha no índice:</span><span class="sxs-lookup"><span data-stu-id="21e20-226">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="21e20-227">***Num_Index_Pages*** = nível de ∑ (***Num_Leaf_Pages/***<sup>nível</sup>de Index_Rows_Per_Page) em que 1 <= nível <= ***níveis***</span><span class="sxs-lookup"><span data-stu-id="21e20-227">***Num_Index_Pages***  = ∑Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>)where 1 <= Level <= ***Levels***</span></span>  
  
     <span data-ttu-id="21e20-228">Arredonde cada soma até o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="21e20-228">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="21e20-229">Como um exemplo simples, considere um índice em que ***Num_Leaf_Pages*** = 1000 e ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="21e20-229">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="21e20-230">O primeiro nível de índice acima do nível folha armazena 1.000 linhas de índice que representa uma linha de índice por página de folha, e 25 linhas de índice podem ser ajustadas por página.</span><span class="sxs-lookup"><span data-stu-id="21e20-230">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="21e20-231">Isso significa que são necessárias 40 páginas para armazenar essas 1.000 linhas de índice.</span><span class="sxs-lookup"><span data-stu-id="21e20-231">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="21e20-232">O próximo nível do índice precisa armazenar 40 linhas.</span><span class="sxs-lookup"><span data-stu-id="21e20-232">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="21e20-233">Isso significa que são necessárias 2 páginas.</span><span class="sxs-lookup"><span data-stu-id="21e20-233">This means that it requires 2 pages.</span></span> <span data-ttu-id="21e20-234">O nível final do índice precisa armazenar 2 linhas.</span><span class="sxs-lookup"><span data-stu-id="21e20-234">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="21e20-235">Isso significa que é necessária 1 página.</span><span class="sxs-lookup"><span data-stu-id="21e20-235">This means that it requires 1 page.</span></span> <span data-ttu-id="21e20-236">Isso resulta em 43 páginas de índice não folha.</span><span class="sxs-lookup"><span data-stu-id="21e20-236">This yields 43 non-leaf index pages.</span></span> <span data-ttu-id="21e20-237">Quando esses números são usados nas fórmulas anteriores, o resultado é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="21e20-237">When these numbers are used in the previous formulas, the result is as follows:</span></span>  
  
     <span data-ttu-id="21e20-238">***Não leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="21e20-238">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="21e20-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, que é o número de páginas descritas no exemplo.</span><span class="sxs-lookup"><span data-stu-id="21e20-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
3.  <span data-ttu-id="21e20-240">Calcule o tamanho do índice (total de 8.912 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="21e20-240">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="21e20-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="21e20-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-4-total-the-calculated-values"></a><span data-ttu-id="21e20-242">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="21e20-242">Step 4.</span></span> <span data-ttu-id="21e20-243">Some os valores calculados</span><span class="sxs-lookup"><span data-stu-id="21e20-243">Total the Calculated Values</span></span>  
 <span data-ttu-id="21e20-244">Some os valores obtidos nas duas etapas anteriores:</span><span class="sxs-lookup"><span data-stu-id="21e20-244">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="21e20-245">Tamanho do índice não clusterizado (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="21e20-245">Nonclustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="21e20-246">Esse cálculo não considera o seguinte:</span><span class="sxs-lookup"><span data-stu-id="21e20-246">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="21e20-247">Particionamento</span><span class="sxs-lookup"><span data-stu-id="21e20-247">Partitioning</span></span>  
  
     <span data-ttu-id="21e20-248">A sobrecarga de espaço do particionamento é mínima, mas complexa para ser calculada.</span><span class="sxs-lookup"><span data-stu-id="21e20-248">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="21e20-249">Não é importante incluí-la.</span><span class="sxs-lookup"><span data-stu-id="21e20-249">It is not important to include.</span></span>  
  
-   <span data-ttu-id="21e20-250">Páginas de alocação</span><span class="sxs-lookup"><span data-stu-id="21e20-250">Allocation pages</span></span>  
  
     <span data-ttu-id="21e20-251">Há pelo menos uma página de IAM usada para rastrear as páginas alocadas a um heap, mas a sobrecarga de espaço é mínima e não há nenhum algoritmo para calcular de forma determinista exatamente quantas páginas de IAM serão usadas.</span><span class="sxs-lookup"><span data-stu-id="21e20-251">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="21e20-252">Valores de LOB (Objeto Grande)</span><span class="sxs-lookup"><span data-stu-id="21e20-252">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="21e20-253">O algoritmo para determinar exatamente quanto espaço será usado armazenar os valores `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` e `image` dos tipos de dados LOB é complexo.</span><span class="sxs-lookup"><span data-stu-id="21e20-253">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="21e20-254">É suficiente adicionar o tamanho médio dos valores LOB esperados, multiplicá-lo por ***Num_Rows***e adicioná-lo ao tamanho total de índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="21e20-254">It is sufficient to just add the average size of the LOB values expected, multiply by ***Num_Rows***, and add that to the total nonclustered index size.</span></span>  
  
-   <span data-ttu-id="21e20-255">Compactação</span><span class="sxs-lookup"><span data-stu-id="21e20-255">Compression</span></span>  
  
     <span data-ttu-id="21e20-256">Não é possível pré-calcular o tamanho de um índice compactado.</span><span class="sxs-lookup"><span data-stu-id="21e20-256">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="21e20-257">Colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="21e20-257">Sparse columns</span></span>  
  
     <span data-ttu-id="21e20-258">Para obter informações sobre os requisitos de espaço de colunas esparsas, consulte [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="21e20-258">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e20-259">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21e20-259">See Also</span></span>  
 <span data-ttu-id="21e20-260">[Índices clusterizados e não clusterizados descritos](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="21e20-260">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="21e20-261">[Criar índices não clusterizados](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="21e20-261">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="21e20-262">[Criar índices clusterizados](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="21e20-262">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="21e20-263">[Estimar o tamanho de uma tabela](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="21e20-263">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="21e20-264">[Estimar o tamanho de um índice clusterizado](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="21e20-264">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="21e20-265">[Estimar o tamanho de um heap](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="21e20-265">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="21e20-266">Estimar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="21e20-266">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
