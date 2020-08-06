---
title: Estimar o tamanho de um índice clusterizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- disk space [SQL Server], indexes
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- space [SQL Server], indexes
- clustered indexes, table size
- nonclustered indexes [SQL Server], table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: 2b5137f8-98ad-46b5-9aae-4c980259bf8d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d224c5ae55cc5ec7690ca0962cbc2130bac22e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685741"
---
# <a name="estimate-the-size-of-a-clustered-index"></a><span data-ttu-id="25aa2-102">Estimar o tamanho de um índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="25aa2-102">Estimate the Size of a Clustered Index</span></span>
  <span data-ttu-id="25aa2-103">Você pode usar as seguintes etapas para estimar a quantidade de espaço exigida para armazenar dados em um índice clusterizado:</span><span class="sxs-lookup"><span data-stu-id="25aa2-103">You can use the following steps to estimate the amount of space that is required to store data in a clustered index:</span></span>  
  
1.  <span data-ttu-id="25aa2-104">Calcule o espaço usado para armazenar dados no nível folha do índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="25aa2-104">Calculate the space used to store data in the leaf level of the clustered index.</span></span>  
  
2.  <span data-ttu-id="25aa2-105">Calcule o espaço usado para armazenar as informações de índice para o índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="25aa2-105">Calculate the space used to store index information for the clustered index.</span></span>  
  
3.  <span data-ttu-id="25aa2-106">Some os valores calculados.</span><span class="sxs-lookup"><span data-stu-id="25aa2-106">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-the-space-used-to-store-data-in-the-leaf-level"></a><span data-ttu-id="25aa2-107">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="25aa2-107">Step 1.</span></span> <span data-ttu-id="25aa2-108">Calcular o espaço usado para armazenar dados no nível folha</span><span class="sxs-lookup"><span data-stu-id="25aa2-108">Calculate the Space Used to Store Data in the Leaf Level</span></span>  
  
1.  <span data-ttu-id="25aa2-109">Especifique o número de linhas que estarão presentes na tabela:</span><span class="sxs-lookup"><span data-stu-id="25aa2-109">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="25aa2-110">***Num_Rows***  = número de linhas na tabela</span><span class="sxs-lookup"><span data-stu-id="25aa2-110">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="25aa2-111">Especifique o número de colunas de comprimento fixo e variável e calcule o espaço necessário para o seu armazenamento:</span><span class="sxs-lookup"><span data-stu-id="25aa2-111">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="25aa2-112">Calcule o espaço que cada um desses grupos de colunas ocupa dentro da linha de dados.</span><span class="sxs-lookup"><span data-stu-id="25aa2-112">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="25aa2-113">O tamanho de uma coluna depende do tipo de dados e da especificação de comprimento.</span><span class="sxs-lookup"><span data-stu-id="25aa2-113">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="25aa2-114">***Num_Cols***  = número total de colunas (comprimento fixo e tamanho variável)</span><span class="sxs-lookup"><span data-stu-id="25aa2-114">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="25aa2-115">***Fixed_Data_Size***  = tamanho total em bytes de todas as colunas de tamanho fixo</span><span class="sxs-lookup"><span data-stu-id="25aa2-115">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="25aa2-116">***Num_Variable_Cols***  = número de colunas de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="25aa2-116">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="25aa2-117">***Max_Var_Size***  = tamanho máximo em bytes de todas as colunas de comprimento variável</span><span class="sxs-lookup"><span data-stu-id="25aa2-117">***Max_Var_Size***  = maximum byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="25aa2-118">Se o índice clusterizado for do tipo não exclusivo, explique a coluna do *indicador de exclusividade* :</span><span class="sxs-lookup"><span data-stu-id="25aa2-118">If the clustered index is nonunique, account for the *uniqueifier* column:</span></span>  
  
     <span data-ttu-id="25aa2-119">O identificador de exclusividade é uma coluna de comprimento variável que permite valor nulo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-119">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="25aa2-120">Ele será não nulo e terá 4 bytes de tamanho em linhas com valores de chave não exclusivos.</span><span class="sxs-lookup"><span data-stu-id="25aa2-120">It will be nonnull and 4 bytes in size in rows that have nonunique key values.</span></span> <span data-ttu-id="25aa2-121">Esse valor faz parte da chave de índice e é necessário para garantir que cada linha tenha um valor de chave exclusivo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-121">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="25aa2-122">***Num_Cols***  = ***Num_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="25aa2-122">***Num_Cols***  = ***Num_Cols*** + 1</span></span>  
  
     <span data-ttu-id="25aa2-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="25aa2-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span></span>  
  
     <span data-ttu-id="25aa2-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="25aa2-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span></span>  
  
     <span data-ttu-id="25aa2-125">Essas modificações assumem que todos os valores serão do tipo não exclusivo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-125">These modifications assume that all values will be nonunique.</span></span>  
  
4.  <span data-ttu-id="25aa2-126">Parte da linha, conhecida como bitmap nulo, é reservada para gerenciar a nulabilidade da coluna.</span><span class="sxs-lookup"><span data-stu-id="25aa2-126">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="25aa2-127">Calcule seu tamanho:</span><span class="sxs-lookup"><span data-stu-id="25aa2-127">Calculate its size:</span></span>  
  
     <span data-ttu-id="25aa2-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="25aa2-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="25aa2-129">Somente a parte de inteiro da expressão anterior deve ser usada; descarte todo o restante.</span><span class="sxs-lookup"><span data-stu-id="25aa2-129">Only the integer part of the previous expression should be used; discard any remainder.</span></span>  
  
5.  <span data-ttu-id="25aa2-130">Calcule o tamanho dos dados de comprimento variável:</span><span class="sxs-lookup"><span data-stu-id="25aa2-130">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="25aa2-131">Se houver colunas de comprimento variável na tabela, determine quanto espaço será usado para armazenar as colunas dentro da linha:</span><span class="sxs-lookup"><span data-stu-id="25aa2-131">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="25aa2-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="25aa2-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="25aa2-133">Os bytes adicionados a ***Max_Var_Size*** são para acompanhar cada coluna de variáveis.</span><span class="sxs-lookup"><span data-stu-id="25aa2-133">The bytes added to ***Max_Var_Size*** are for tracking each variable column.</span></span> <span data-ttu-id="25aa2-134">Essa fórmula presume que todas as colunas de comprimento variável estão 100% completas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-134">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="25aa2-135">Se você prevê que um percentual menor do espaço de armazenamento da coluna de tamanho variável será usada, poderá ajustar o valor ***Max_Var_Size*** de acordo com esse percentual para obter uma estimativa mais precisa do tamanho geral da tabela.</span><span class="sxs-lookup"><span data-stu-id="25aa2-135">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25aa2-136">Você pode combinar as colunas `varchar`, `nvarchar`, `varbinary` ou `sql_variant` que fazem com que a largura total definida da tabela exceda 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="25aa2-136">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="25aa2-137">O comprimento de cada uma dessas colunas ainda deve ficar dentro do limite de 8.000 bytes para uma coluna `varchar`, `varbinary` ou `sql_variant` e de 4.000 bytes para colunas `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="25aa2-137">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="25aa2-138">Entretanto, as larguras combinadas podem exceder o limite de 8.060 bytes em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="25aa2-138">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="25aa2-139">Se não houver colunas de tamanho variável, defina ***Variable_Data_Size*** como 0.</span><span class="sxs-lookup"><span data-stu-id="25aa2-139">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="25aa2-140">Calcule o tamanho total da linha:</span><span class="sxs-lookup"><span data-stu-id="25aa2-140">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="25aa2-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="25aa2-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="25aa2-142">O valor 4 é a sobrecarga de cabeçalho de uma linha de dados.</span><span class="sxs-lookup"><span data-stu-id="25aa2-142">The value 4 is the row header overhead of a data row.</span></span>  
  
7.  <span data-ttu-id="25aa2-143">Calcule o número de linhas por página (8.096 bytes livres por página):</span><span class="sxs-lookup"><span data-stu-id="25aa2-143">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="25aa2-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="25aa2-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="25aa2-145">Como as linhas não se estendem por mais de uma página, o número de linhas por página deve ser arredondado para baixo, para a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="25aa2-145">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="25aa2-146">O valor 2 na fórmula é para a entrada da linha na matriz de slot da página.</span><span class="sxs-lookup"><span data-stu-id="25aa2-146">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
8.  <span data-ttu-id="25aa2-147">Calcule o número de linhas livres reservadas por página, com base no [fator de preenchimento](../indexes/specify-fill-factor-for-an-index.md) especificado:</span><span class="sxs-lookup"><span data-stu-id="25aa2-147">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="25aa2-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="25aa2-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="25aa2-149">O fator de preenchimento usado no cálculo é um valor inteiro, em vez de uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="25aa2-149">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="25aa2-150">Como as linhas não se estendem por mais de uma página, o número de linhas por página deve ser arredondado para baixo, para a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="25aa2-150">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="25aa2-151">À medida que o fator de preenchimento aumenta, mais dados são armazenados em cada página e haverá menos páginas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-151">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="25aa2-152">O valor 2 na fórmula é para a entrada da linha na matriz de slot da página.</span><span class="sxs-lookup"><span data-stu-id="25aa2-152">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
9. <span data-ttu-id="25aa2-153">Calcule o número de páginas necessário para armazenar todas as linhas:</span><span class="sxs-lookup"><span data-stu-id="25aa2-153">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="25aa2-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="25aa2-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="25aa2-155">O número de páginas estimado deve ser arredondado para cima, até a página inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="25aa2-155">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
10. <span data-ttu-id="25aa2-156">Calcule a quantidade de espaço necessária para armazenar os dados no nível folha (total de 8.192 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="25aa2-156">Calculate the amount of space that is required to store the data in the leaf level (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="25aa2-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="25aa2-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information"></a><span data-ttu-id="25aa2-158">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="25aa2-158">Step 2.</span></span> <span data-ttu-id="25aa2-159">Calcular o espaço usado para armazenar as informações de índice</span><span class="sxs-lookup"><span data-stu-id="25aa2-159">Calculate the Space Used to Store Index Information</span></span>  
 <span data-ttu-id="25aa2-160">Você pode usar as seguintes etapas para estimar a quantidade de espaço necessária para armazenar os níveis superiores do índice:</span><span class="sxs-lookup"><span data-stu-id="25aa2-160">You can use the following steps to estimate the amount of space that is required to store the upper levels of the index:</span></span>  
  
1.  <span data-ttu-id="25aa2-161">Especifique o número de colunas de comprimento fixo e variável na chave do índice e calcule o espaço necessário para seu armazenamento:</span><span class="sxs-lookup"><span data-stu-id="25aa2-161">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="25aa2-162">As colunas de chave de um índice podem incluir colunas de comprimento fixo e variável.</span><span class="sxs-lookup"><span data-stu-id="25aa2-162">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="25aa2-163">Para estimar o tamanho da linha de índice no nível interior, calcule o espaço que cada um desses grupos de colunas ocupa na linha do índice.</span><span class="sxs-lookup"><span data-stu-id="25aa2-163">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="25aa2-164">O tamanho de uma coluna depende do tipo de dados e da especificação de comprimento.</span><span class="sxs-lookup"><span data-stu-id="25aa2-164">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="25aa2-165">***Num_Key_Cols***  = número total de colunas de chaves (tamanho fixo e tamanho variável)</span><span class="sxs-lookup"><span data-stu-id="25aa2-165">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="25aa2-166">***Fixed_Key_Size***  = tamanho total em bytes de todas as colunas de chaves de tamanho fixo</span><span class="sxs-lookup"><span data-stu-id="25aa2-166">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="25aa2-167">***Num_Variable_Key_Cols***  = número de colunas de chaves de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="25aa2-167">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="25aa2-168">***Max_Var_Key_Size***  = tamanho máximo em bytes de todas as colunas de chaves de tamanho variável</span><span class="sxs-lookup"><span data-stu-id="25aa2-168">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
2.  <span data-ttu-id="25aa2-169">Explique qualquer indicador de exclusividade, caso o índice seja do tipo não exclusivo:</span><span class="sxs-lookup"><span data-stu-id="25aa2-169">Account for any uniqueifier needed if the index is nonunique:</span></span>  
  
     <span data-ttu-id="25aa2-170">O identificador de exclusividade é uma coluna de comprimento variável que permite valor nulo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-170">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="25aa2-171">Ele será não nulo e com 4 bytes de tamanho em linhas com valores de chave não exclusivos.</span><span class="sxs-lookup"><span data-stu-id="25aa2-171">It will be nonnull and 4 bytes in size in rows that have nonunique index key values.</span></span> <span data-ttu-id="25aa2-172">Esse valor faz parte da chave de índice e é necessário para garantir que cada linha tenha um valor de chave exclusivo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-172">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="25aa2-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="25aa2-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="25aa2-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="25aa2-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="25aa2-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="25aa2-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span></span>  
  
     <span data-ttu-id="25aa2-176">Essas modificações assumem que todos os valores serão do tipo não exclusivo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-176">These modifications assume that all values will be nonunique.</span></span>  
  
3.  <span data-ttu-id="25aa2-177">Calcule o tamanho do bitmap nulo:</span><span class="sxs-lookup"><span data-stu-id="25aa2-177">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="25aa2-178">Se houver colunas que permitem valor nulo na chave de índice, parte da linha do índice será reservada para o bitmap nulo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-178">If there are nullable columns in the index key, part of the index row is reserved for the null bitmap.</span></span> <span data-ttu-id="25aa2-179">Calcule seu tamanho:</span><span class="sxs-lookup"><span data-stu-id="25aa2-179">Calculate its size:</span></span>  
  
     <span data-ttu-id="25aa2-180">***Index_Null_Bitmap***  = 2 + ([número de colunas na linha de índice + 7] / 8)</span><span class="sxs-lookup"><span data-stu-id="25aa2-180">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="25aa2-181">Somente a parte do inteiro da expressão anterior deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="25aa2-181">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="25aa2-182">Descarte todo o restante.</span><span class="sxs-lookup"><span data-stu-id="25aa2-182">Discard any remainder.</span></span>  
  
     <span data-ttu-id="25aa2-183">Se não houver colunas de chave anuláveis, defina ***Index_Null_Bitmap*** como 0.</span><span class="sxs-lookup"><span data-stu-id="25aa2-183">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
4.  <span data-ttu-id="25aa2-184">Calcule o tamanho dos dados de comprimento variável:</span><span class="sxs-lookup"><span data-stu-id="25aa2-184">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="25aa2-185">Se houver colunas de comprimento variável no índice, determine quanto espaço será usado para armazenar as colunas dentro da linha do índice:</span><span class="sxs-lookup"><span data-stu-id="25aa2-185">If there are variable-length columns in the index, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="25aa2-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="25aa2-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="25aa2-187">Os bytes adicionados a ***Max_Var_Key_Size*** são para acompanhamento de cada coluna de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="25aa2-187">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="25aa2-188">Essa fórmula presume que todas as colunas de comprimento variável estão 100% completas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-188">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="25aa2-189">Se você se previr que um percentual menor do espaço de armazenamento de coluna de tamanho variável será usado, poderá ajustar o valor ***Max_Var_Key_Size*** com esse percentual para obter uma estimativa mais precisa do tamanho geral da tabela.</span><span class="sxs-lookup"><span data-stu-id="25aa2-189">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="25aa2-190">Se não houver colunas de tamanho variável, defina ***Variable_Key_Size*** como 0.</span><span class="sxs-lookup"><span data-stu-id="25aa2-190">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="25aa2-191">Calcule o tamanho da linha de índice:</span><span class="sxs-lookup"><span data-stu-id="25aa2-191">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="25aa2-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (para a sobrecarga de cabeçalho de linha de uma linha de índice) + 6 (para o ponteiro de ID da página filho)</span><span class="sxs-lookup"><span data-stu-id="25aa2-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="25aa2-193">Calcule o número de linhas de índice por página (8.096 bytes livres por página):</span><span class="sxs-lookup"><span data-stu-id="25aa2-193">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="25aa2-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="25aa2-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="25aa2-195">Como as linhas de índice não se estendem por mais de uma página, o número de linhas de índice por página deve ser arredondado para baixo, até a linha inteira mais próxima.</span><span class="sxs-lookup"><span data-stu-id="25aa2-195">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="25aa2-196">O 2 na fórmula é para a entrada da linha na matriz de slots da página.</span><span class="sxs-lookup"><span data-stu-id="25aa2-196">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="25aa2-197">Calcule o número de níveis no índice:</span><span class="sxs-lookup"><span data-stu-id="25aa2-197">Calculate the number of levels in the index:</span></span>  
  
     <span data-ttu-id="25aa2-198">***Não leaf_Levels*** = 1 + Index_Rows_Per_Page de log (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="25aa2-198">***Non-leaf_Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="25aa2-199">Arredonde esse valor até o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-199">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="25aa2-200">Esse valor não inclui o nível folha do índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="25aa2-200">This value does not include the leaf level of the clustered index.</span></span>  
  
8.  <span data-ttu-id="25aa2-201">Calcule o número de páginas não folha no índice:</span><span class="sxs-lookup"><span data-stu-id="25aa2-201">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="25aa2-202">***Num_Index_Pages =*** nível ***de ∑ (Num_Leaf_Pages/(nível de Index_Rows_Per_Page***<sup>Level</sup>***))***</span><span class="sxs-lookup"><span data-stu-id="25aa2-202">***Num_Index_Pages =*** ∑Level ***(Num_Leaf_Pages / (Index_Rows_Per_Page***<sup>Level</sup>***))***</span></span>  
  
     <span data-ttu-id="25aa2-203">em que 1 <= Level <= ***Non-leaf_Levels***</span><span class="sxs-lookup"><span data-stu-id="25aa2-203">where 1 <= Level <= ***Non-leaf_Levels***</span></span>  
  
     <span data-ttu-id="25aa2-204">Arredonde cada soma até o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-204">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="25aa2-205">Como um exemplo simples, considere um índice em que ***Num_Leaf_Pages*** = 1000 e ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="25aa2-205">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="25aa2-206">O primeiro nível de índice acima do nível folha armazena 1.000 linhas de índice que representa uma linha de índice por página de folha, e 25 linhas de índice podem ser ajustadas por página.</span><span class="sxs-lookup"><span data-stu-id="25aa2-206">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="25aa2-207">Isso significa que são necessárias 40 páginas para armazenar essas 1.000 linhas de índice.</span><span class="sxs-lookup"><span data-stu-id="25aa2-207">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="25aa2-208">O próximo nível do índice precisa armazenar 40 linhas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-208">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="25aa2-209">Isso significa que são necessárias 2 páginas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-209">This means it requires 2 pages.</span></span> <span data-ttu-id="25aa2-210">O nível final do índice precisa armazenar 2 linhas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-210">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="25aa2-211">Isso significa que é necessária 1 página.</span><span class="sxs-lookup"><span data-stu-id="25aa2-211">This means it requires 1 page.</span></span> <span data-ttu-id="25aa2-212">Isso resulta em 43 páginas de índice não folha.</span><span class="sxs-lookup"><span data-stu-id="25aa2-212">This gives 43 non-leaf index pages.</span></span> <span data-ttu-id="25aa2-213">Quando esses números são usados nas fórmulas anteriores, o resultado é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="25aa2-213">When these numbers are used in the previous formulas, the outcome is as follows:</span></span>  
  
     <span data-ttu-id="25aa2-214">***Não leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="25aa2-214">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="25aa2-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, que é o número de páginas descritas no exemplo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
9. <span data-ttu-id="25aa2-216">Calcule o tamanho do índice (total de 8.912 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="25aa2-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="25aa2-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="25aa2-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-3-total-the-calculated-values"></a><span data-ttu-id="25aa2-218">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="25aa2-218">Step 3.</span></span> <span data-ttu-id="25aa2-219">Some os valores calculados</span><span class="sxs-lookup"><span data-stu-id="25aa2-219">Total the Calculated Values</span></span>  
 <span data-ttu-id="25aa2-220">Some os valores obtidos nas duas etapas anteriores:</span><span class="sxs-lookup"><span data-stu-id="25aa2-220">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="25aa2-221">Tamanho do índice clusterizado (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="25aa2-221">Clustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="25aa2-222">Esse cálculo não considera o seguinte:</span><span class="sxs-lookup"><span data-stu-id="25aa2-222">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="25aa2-223">Particionamento</span><span class="sxs-lookup"><span data-stu-id="25aa2-223">Partitioning</span></span>  
  
     <span data-ttu-id="25aa2-224">A sobrecarga de espaço do particionamento é mínima, mas complexa para ser calculada.</span><span class="sxs-lookup"><span data-stu-id="25aa2-224">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="25aa2-225">Não é importante incluí-la.</span><span class="sxs-lookup"><span data-stu-id="25aa2-225">It is not important to include.</span></span>  
  
-   <span data-ttu-id="25aa2-226">Páginas de alocação</span><span class="sxs-lookup"><span data-stu-id="25aa2-226">Allocation pages</span></span>  
  
     <span data-ttu-id="25aa2-227">Há pelo menos uma página de IAM usada para rastrear as páginas alocadas a um heap, mas a sobrecarga de espaço é mínima e não há nenhum algoritmo para calcular de forma determinista exatamente quantas páginas de IAM serão usadas.</span><span class="sxs-lookup"><span data-stu-id="25aa2-227">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="25aa2-228">Valores de LOB (Objeto Grande)</span><span class="sxs-lookup"><span data-stu-id="25aa2-228">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="25aa2-229">O algoritmo para determinar exatamente quanto espaço será usado armazenar os valores `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` e `image` dos tipos de dados LOB é complexo.</span><span class="sxs-lookup"><span data-stu-id="25aa2-229">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="25aa2-230">É suficiente adicionar o tamanho médio dos valores LOB esperados, multiplicá-lo por ***Num_Rows***e adicioná-lo ao tamanho total de índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="25aa2-230">It is sufficient to just add the average size of the LOB values that are expected, multiply by ***Num_Rows***, and add that to the total clustered index size.</span></span>  
  
-   <span data-ttu-id="25aa2-231">Compactação</span><span class="sxs-lookup"><span data-stu-id="25aa2-231">Compression</span></span>  
  
     <span data-ttu-id="25aa2-232">Não é possível pré-calcular o tamanho de um índice compactado.</span><span class="sxs-lookup"><span data-stu-id="25aa2-232">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="25aa2-233">Colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="25aa2-233">Sparse columns</span></span>  
  
     <span data-ttu-id="25aa2-234">Para obter informações sobre os requisitos de espaço de colunas esparsas, consulte [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="25aa2-234">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25aa2-235">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25aa2-235">See Also</span></span>  
 <span data-ttu-id="25aa2-236">[Índices clusterizados e não clusterizados descritos](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="25aa2-236">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="25aa2-237">[Estimar o tamanho de uma tabela](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="25aa2-237">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="25aa2-238">[Criar índices clusterizados](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="25aa2-238">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="25aa2-239">[Criar índices não clusterizados](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="25aa2-239">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="25aa2-240">[Estimar o tamanho de um índice não clusterizado](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="25aa2-240">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 <span data-ttu-id="25aa2-241">[Estimar o tamanho de um heap](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="25aa2-241">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="25aa2-242">Estimar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="25aa2-242">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
