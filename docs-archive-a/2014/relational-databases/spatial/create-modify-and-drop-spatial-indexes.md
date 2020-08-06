---
title: Criar, modificar e remover índices espaciais | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], creating
- spatial indexes [SQL Server], dropping
- spatial indexes [SQL Server], creating
- indexes [SQL Server], dropping
- indexes [SQL Server], modifying
- spatial indexes [SQL Server], modifying
ms.assetid: 00c1b927-8ec5-44cf-87c2-c8de59745735
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 88de17e8c487d9a965f2e236edac064dc2fe4c7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569862"
---
# <a name="create-modify-and-drop-spatial-indexes"></a><span data-ttu-id="0e679-102">Criar, modificar e remover índices espaciais</span><span class="sxs-lookup"><span data-stu-id="0e679-102">Create, Modify, and Drop Spatial Indexes</span></span>
  <span data-ttu-id="0e679-103">Um índice espacial pode executar determinadas operações com mais eficiência em uma coluna do `geometry` `geography` tipo de dados ou (uma *coluna espacial*).</span><span class="sxs-lookup"><span data-stu-id="0e679-103">A spatial index can more efficiently perform certain operations on a column of the `geometry` or `geography` data type (a *spatial column*).</span></span> <span data-ttu-id="0e679-104">Mais de um índice espacial pode ser especificado em uma coluna espacial.</span><span class="sxs-lookup"><span data-stu-id="0e679-104">More than one spatial index can be specified on a spatial column.</span></span> <span data-ttu-id="0e679-105">Por exemplo, isto é útil para indexar diferentes parâmetros de mosaico em uma única coluna.</span><span class="sxs-lookup"><span data-stu-id="0e679-105">This is useful, for example, for indexing different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="0e679-106">Há várias restrições na criação de índices espaciais.</span><span class="sxs-lookup"><span data-stu-id="0e679-106">There are a number of restrictions on creating spatial indexes.</span></span> <span data-ttu-id="0e679-107">Para obter mais informações, consulte [Restrições em índices espaciais](#restrictions) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0e679-107">For more information, see [Restrictions on Spatial Indexes](#restrictions) in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e679-108">Para obter informações sobre a relação de índices espaciais com a partição e os grupos de arquivos, consulte a seção "Comentários" em [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0e679-108">For information about the relationship of spatial indexes to partition and to filegroups, see the "Remarks" section in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
##  <a name="creating-modifying-and-dropping-spatial-indexes"></a><a name="creating"></a> <span data-ttu-id="0e679-109">Criando, modificando e removendo índices espaciais</span><span class="sxs-lookup"><span data-stu-id="0e679-109">Creating, Modifying, and Dropping Spatial Indexes</span></span>  
  
###  <a name="to-create-a-spatial-index"></a><a name="create"></a> <span data-ttu-id="0e679-110">Para criar um índice espacial</span><span class="sxs-lookup"><span data-stu-id="0e679-110">To create a spatial index</span></span>  
 <span data-ttu-id="0e679-111">**Para criar um índice espacial com o Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="0e679-111">**To create a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="0e679-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e679-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-spatial-index-transact-sql)  
  
 <span data-ttu-id="0e679-113">**Para criar um índice espacial usando a caixa de diálogo Novo Índice no Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0e679-113">**To create a spatial index by using the New Index dialog box in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-management-studio"></a><span data-ttu-id="0e679-114">Para criar um índice espacial no Management Studio</span><span class="sxs-lookup"><span data-stu-id="0e679-114">To create a spatial index in Management Studio</span></span>  
  
1.  <span data-ttu-id="0e679-115">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="0e679-115">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0e679-116">Expanda **Bancos de Dados**, expanda o banco de dados que contém a tabela com o índice especificado e expanda **Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="0e679-116">Expand **Databases**, expand the database that contains the table with the specified index, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="0e679-117">Expanda a tabela para a qual você deseja criar o índice.</span><span class="sxs-lookup"><span data-stu-id="0e679-117">Expand the table for which you want to create the index.</span></span>  
  
4.  <span data-ttu-id="0e679-118">Clique com o botão direito do mouse em **Índices** e selecione **Novo Índice**.</span><span class="sxs-lookup"><span data-stu-id="0e679-118">Right-click **Indexes** and select **New Index**.</span></span>  
  
5.  <span data-ttu-id="0e679-119">No campo **Nome do índice** , digite um nome para o índice.</span><span class="sxs-lookup"><span data-stu-id="0e679-119">In the **Index name** field, enter a name for the index.</span></span>  
  
6.  <span data-ttu-id="0e679-120">Na lista suspensa **Tipo de índice** , selecione **Espacial**.</span><span class="sxs-lookup"><span data-stu-id="0e679-120">In the **Index type** drop-down list, select **Spatial**.</span></span>  
  
7.  <span data-ttu-id="0e679-121">Para especificar a coluna espacial que você deseja indexar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0e679-121">To specify the spatial column that you want to index, click **Add**.</span></span>  
  
8.  <span data-ttu-id="0e679-122">Na caixa de diálogo **selecionar colunas de** *\<table name>* , selecione uma coluna do tipo `geometry` ou `geography` marcando a caixa de seleção correspondente.</span><span class="sxs-lookup"><span data-stu-id="0e679-122">In the **Select Columns from** *\<table name>* dialog box, select a column of type `geometry` or `geography` by selecting the corresponding check box.</span></span> <span data-ttu-id="0e679-123">Todas as outras colunas espaciais se tornam não editáveis.</span><span class="sxs-lookup"><span data-stu-id="0e679-123">Any other spatial columns then become uneditable.</span></span> <span data-ttu-id="0e679-124">Para selecionar uma coluna espacial diferente, primeiro desmarque a coluna selecionada no momento.</span><span class="sxs-lookup"><span data-stu-id="0e679-124">If you want to select a different spatial column, you must first clear the currently selected column.</span></span> <span data-ttu-id="0e679-125">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e679-125">When finished, click **OK**.</span></span>  
  
9. <span data-ttu-id="0e679-126">Verifique a seleção da coluna na grade **Colunas de chave de índice** .</span><span class="sxs-lookup"><span data-stu-id="0e679-126">Verify your column selection in the **Index key columns** grid.</span></span>  
  
10. <span data-ttu-id="0e679-127">No painel **Selecionar uma página** da caixa de diálogo **Propriedades do Índice** , clique em **Espacial**.</span><span class="sxs-lookup"><span data-stu-id="0e679-127">In the **Select a page** pane of the **Index Properties** dialog box, click **Spatial**.</span></span>  
  
11. <span data-ttu-id="0e679-128">Na página **Espacial** , especifique os valores que você deseja usar para as propriedades espaciais do índice.</span><span class="sxs-lookup"><span data-stu-id="0e679-128">On the **Spatial** page, specify the values that you want to use for the spatial properties of the index.</span></span>  
  
     <span data-ttu-id="0e679-129">Ao criar um índice em uma `geometry` coluna de tipo, você deve especificar as coordenadas **( *`X-min`* , *`Y-min`* )** e **( *`X-max`* , *`Y-max`* )** da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="0e679-129">When creating an index on a `geometry` type column, you must specify the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="0e679-130">Para um índice em uma `geography` coluna de tipo, os campos de caixa delimitadora se tornam somente leitura depois que você especifica o esquema de mosaico de **grade geográfica** , porque o mosaico de grade de geografia não usa uma caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="0e679-130">For an index on a `geography` type column, the bounding-box fields become read-only after you specify the **Geography grid** tessellation scheme, because geography grid tessellation does not use a bounding box.</span></span>  
  
     <span data-ttu-id="0e679-131">Opcionalmente, é possível especificar valores não padrão para o campo **Células por Objeto** e para a densidade da grade em qualquer nível do esquema de mosaico.</span><span class="sxs-lookup"><span data-stu-id="0e679-131">Optionally, you can specify nondefault values for the **Cells Per Object** field and for the grid density at any level of the tessellation scheme.</span></span> <span data-ttu-id="0e679-132">O número padrão de células por objeto é 16 para o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ou 8 para o [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] ou versão superior, e a densidade padrão da grade é **Média** para o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e679-132">The default number of cells per object is 16 for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or 8 for [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] or higher, and the default grid density is **Medium** for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span>  
  
     <span data-ttu-id="0e679-133">Você pode selecionar GEOMETRY_AUTO_GRID ou GEOGRAPHY_AUTO_GRID para o esquema de mosaico no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e679-133">You can select GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID for tessellation scheme in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0e679-134">Quando GEOMETRY_AUTO_GRID ou GEOGRAPHY_AUTO_GRID é selecionado, as opções de densidade de grade Nível 1, Nível 2, Nível 3 e Nível 4 são desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="0e679-134">When GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID is selected, then Level 1, Level 2, Level 3, and Level 4 grid density options are disabled.</span></span>  
  
     <span data-ttu-id="0e679-135">Para obter mais informações sobre essas propriedades, consulte [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="0e679-135">For more information about these properties, see [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span></span>  
  
12. <span data-ttu-id="0e679-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e679-136">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e679-137">Para criar outro índice espacial na mesma ou em outra coluna espacial, repita as etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="0e679-137">To create another spatial index on the same or a different spatial column, repeat the preceding steps.</span></span>  
  
  
 <span data-ttu-id="0e679-138">**Para criar um índice espacial usando o Designer de Tabela no Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0e679-138">**To create a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-table-designer"></a><span data-ttu-id="0e679-139">Para criar um índice espacial no Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="0e679-139">To create a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="0e679-140">No Pesquisador de Objetos, clique com o botão direito do mouse na tabela para a qual deseja criar um índice espacial e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="0e679-140">In Object Explorer, right-click the table for which you want to create a spatial index, and then click **Design**.</span></span>  
  
     <span data-ttu-id="0e679-141">A tabela é aberta no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="0e679-141">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="0e679-142">Selecione uma coluna `geometry` ou `geography` para o índice.</span><span class="sxs-lookup"><span data-stu-id="0e679-142">Select a `geometry` or `geography` column for the index.</span></span>  
  
3.  <span data-ttu-id="0e679-143">No menu **Designer de Tabela** , clique em **Índice Espacial**.</span><span class="sxs-lookup"><span data-stu-id="0e679-143">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
4.  <span data-ttu-id="0e679-144">Na caixa de diálogo **Índices Espaciais** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0e679-144">In the **Spatial Indexes** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="0e679-145">Selecione o novo índice na lista **Índice Espacial Selecionado** e, na grade à direita, defina as propriedades do índice espacial.</span><span class="sxs-lookup"><span data-stu-id="0e679-145">Select the new index in the **Selected Spatial Index** list, and in the grid to the right, set the properties for the spatial index.</span></span> <span data-ttu-id="0e679-146">Para obter informações sobre as propriedades, consulte [Caixa de diálogo Índices Espaciais &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e679-146">For information about the properties, see [Spatial Indexes Dialog Box &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
  
###  <a name="to-alter-a-spatial-index"></a><a name="alter"></a> <span data-ttu-id="0e679-147">Para alterar um índice espacial</span><span class="sxs-lookup"><span data-stu-id="0e679-147">To alter a spatial index</span></span>  
  
-   [<span data-ttu-id="0e679-148">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e679-148">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0e679-149">Para alterar opções específicas a um índice espacial, como BOUNDING_BOX ou GRID, é possível usar uma instrução CREATE SPATIAL INDEX que especifique DROP_EXISTING = ON ou descartar o índice espacial e criar um novo.</span><span class="sxs-lookup"><span data-stu-id="0e679-149">To change options that are specific to a spatial index, such as BOUNDING_BOX or GRID, you can either use a CREATE SPATIAL INDEX statement that specifies DROP_EXISTING = ON, or drop the spatial index and create a new one.</span></span> <span data-ttu-id="0e679-150">Para obter um exemplo, consulte [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0e679-150">For an example, see [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
-   [<span data-ttu-id="0e679-151">Modificar um índice</span><span class="sxs-lookup"><span data-stu-id="0e679-151">Modify an Index</span></span>](../indexes/modify-an-index.md)  
  
-   [<span data-ttu-id="0e679-152">Mover um índice existente para um grupo de arquivos diferente</span><span class="sxs-lookup"><span data-stu-id="0e679-152">Move an Existing Index to a Different Filegroup</span></span>](../indexes/move-an-existing-index-to-a-different-filegroup.md)  
  
  
###  <a name="to-drop-a-spatial-index"></a><a name="drop"></a> <span data-ttu-id="0e679-153">Para descartar um índice espacial</span><span class="sxs-lookup"><span data-stu-id="0e679-153">To drop a spatial index</span></span>  
 <span data-ttu-id="0e679-154">**Para descartar um índice espacial com o Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="0e679-154">**To drop a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="0e679-155">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e679-155">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 <span data-ttu-id="0e679-156">**Para descartar um índice usando o Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0e679-156">**To drop an index by using Management Studio**</span></span>  
 [<span data-ttu-id="0e679-157">Excluir um índice</span><span class="sxs-lookup"><span data-stu-id="0e679-157">Delete an Index</span></span>](../indexes/delete-an-index.md)  
  
 <span data-ttu-id="0e679-158">**Para descartar um índice espacial usando o Designer de Tabela no Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0e679-158">**To drop a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-drop-a-spatial-index-in-table-designer"></a><span data-ttu-id="0e679-159">Para descartar um índice espacial no Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="0e679-159">To drop a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="0e679-160">No Pesquisador de Objetos, clique com o botão direito do mouse no índice espacial que você deseja excluir e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="0e679-160">In Object Explorer, right-click the table with the spatial index you want to delete and click **Design**.</span></span>  
  
     <span data-ttu-id="0e679-161">A tabela é aberta no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="0e679-161">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="0e679-162">No menu **Designer de Tabela** , clique em **Índice Espacial**.</span><span class="sxs-lookup"><span data-stu-id="0e679-162">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
     <span data-ttu-id="0e679-163">A caixa de diálogo **Índice Espacial** é aberta.</span><span class="sxs-lookup"><span data-stu-id="0e679-163">The **Spatial Index** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="0e679-164">Clique no índice que você deseja excluir na coluna **Índice Espacial Selecionado** .</span><span class="sxs-lookup"><span data-stu-id="0e679-164">Click the index you want to delete in the **Selected Spatial Index** column.</span></span>  
  
4.  <span data-ttu-id="0e679-165">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0e679-165">Click **Delete**.</span></span>  
  
  
##  <a name="restrictions-on-spatial-indexes"></a><a name="restrictions"></a> <span data-ttu-id="0e679-166">Restrições em índices espaciais</span><span class="sxs-lookup"><span data-stu-id="0e679-166">Restrictions on Spatial Indexes</span></span>  
 <span data-ttu-id="0e679-167">Um índice espacial pode ser criado apenas em uma coluna do tipo `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="0e679-167">A spatial index can be created only on a column of type `geometry` or `geography`.</span></span>  
  
### <a name="table-and-view-restrictions"></a><span data-ttu-id="0e679-168">Restrições de tabela e de exibição</span><span class="sxs-lookup"><span data-stu-id="0e679-168">Table and View Restrictions</span></span>  
 <span data-ttu-id="0e679-169">Índices espaciais podem ser definidos apenas em uma tabela que tenha uma chave primária.</span><span class="sxs-lookup"><span data-stu-id="0e679-169">Spatial indexes can be defined only on a table that has a primary key.</span></span> <span data-ttu-id="0e679-170">O número máximo de colunas de chave primária na tabela é 15.</span><span class="sxs-lookup"><span data-stu-id="0e679-170">The maximum number of primary key columns on the table is 15.</span></span>  
  
 <span data-ttu-id="0e679-171">O tamanho de máximo de registros de chave de índice é 895 bytes.</span><span class="sxs-lookup"><span data-stu-id="0e679-171">The maximum size of index key records is 895 bytes.</span></span> <span data-ttu-id="0e679-172">Tamanhos maiores retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="0e679-172">Larger sizes raise an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e679-173">Metadados de chave primária não podem ser alterados enquanto um índice espacial estiver definido em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0e679-173">Primary key metadata cannot be changed while a spatial index is defined on a table.</span></span>  
  
 <span data-ttu-id="0e679-174">Não é possível especificar índices espaciais em exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="0e679-174">Spatial indexes cannot be specified on indexed views.</span></span>  
  
### <a name="multiple-spatial-index-restrictions"></a><span data-ttu-id="0e679-175">Várias restrições de índices espaciais</span><span class="sxs-lookup"><span data-stu-id="0e679-175">Multiple Spatial Index Restrictions</span></span>  
 <span data-ttu-id="0e679-176">É possível criar até 249 índices espaciais em qualquer uma das colunas espaciais em uma tabela com suporte.</span><span class="sxs-lookup"><span data-stu-id="0e679-176">You can create up to 249 spatial indexes on any of the spatial columns in a supported table.</span></span> <span data-ttu-id="0e679-177">A criação de mais de um índice espacial na mesma coluna espacial pode ser útil, por exemplo, para indexar diferentes parâmetros de mosaico em uma única coluna.</span><span class="sxs-lookup"><span data-stu-id="0e679-177">Creating more than one spatial index on the same spatial column can be useful, for example, to index different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="0e679-178">É possível criar apenas um índice espacial de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0e679-178">You can create only one spatial index at a time.</span></span>  
  
### <a name="spatial-indexes-and-process-parallelism"></a><span data-ttu-id="0e679-179">Índices espaciais e paralelismo do processo</span><span class="sxs-lookup"><span data-stu-id="0e679-179">Spatial Indexes and Process Parallelism</span></span>  
 <span data-ttu-id="0e679-180">Uma criação de índice pode usar o paralelismo de processo disponível.</span><span class="sxs-lookup"><span data-stu-id="0e679-180">An index build can use available process parallelism.</span></span>  
  
### <a name="version-restrictions"></a><span data-ttu-id="0e679-181">Restrições de versões</span><span class="sxs-lookup"><span data-stu-id="0e679-181">Version Restrictions</span></span>  
 <span data-ttu-id="0e679-182">Os mosaicos espaciais introduzidos no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] não podem ser replicados para o [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ou o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e679-182">Spatial tessellations introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] cannot be replicated to [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="0e679-183">Você deverá usar mosaicos espaciais do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ou do [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] em índices espaciais quando a compatibilidade com versões anteriores com bancos de dados do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ou do [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] for um requisito.</span><span class="sxs-lookup"><span data-stu-id="0e679-183">You must use [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] spatial tessellations for spatial indexes when backward compatibility with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] databases is a requirement.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="0e679-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e679-184">See Also</span></span>  
 [<span data-ttu-id="0e679-185">Visão geral de índices espaciais</span><span class="sxs-lookup"><span data-stu-id="0e679-185">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
  
  
