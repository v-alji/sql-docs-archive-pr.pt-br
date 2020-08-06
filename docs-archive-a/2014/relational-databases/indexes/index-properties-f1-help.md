---
title: Ajuda de F1 de propriedades do índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 390a63d21dc72e052017f2d30b061d71de863bc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685667"
---
# <a name="index-properties-f1-help"></a><span data-ttu-id="12d57-102">Ajuda de F1 de Propriedades do Índice</span><span class="sxs-lookup"><span data-stu-id="12d57-102">Index Properties F1 Help</span></span>
  <span data-ttu-id="12d57-103">As seções neste tópico referem-se a várias propriedades de índice que estão disponíveis usando caixas de diálogo do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12d57-103">The sections in this topic refer to various index properties that are available by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialogs.</span></span>  
  
 <span data-ttu-id="12d57-104">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="12d57-104">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="12d57-105">Página geral das propriedades do índice</span><span class="sxs-lookup"><span data-stu-id="12d57-105">Index Properties General Page</span></span>](#General)  
  
 [<span data-ttu-id="12d57-106">Caixa de diálogo Selecionar Colunas (Índice)</span><span class="sxs-lookup"><span data-stu-id="12d57-106">Select (Index) Columns Dialog Box</span></span>](#Columns)  
  
 [<span data-ttu-id="12d57-107">Página de armazenamento das propriedades do índice</span><span class="sxs-lookup"><span data-stu-id="12d57-107">Index Properties Storage Page</span></span>](#Storage)  
  
 [<span data-ttu-id="12d57-108">Página Espacial das propriedades do índice</span><span class="sxs-lookup"><span data-stu-id="12d57-108">Index Properties Spatial Page</span></span>](#Spatial)  
  
 [<span data-ttu-id="12d57-109">Página Filtrar das propriedades do índice</span><span class="sxs-lookup"><span data-stu-id="12d57-109">Index Properties Filter Page</span></span>](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> <span data-ttu-id="12d57-110">Página geral das propriedades do índice</span><span class="sxs-lookup"><span data-stu-id="12d57-110">Index Properties General Page</span></span>  
 <span data-ttu-id="12d57-111">Use a página Geral para exibir ou modificar propriedades de índice para a tabela ou exibição selecionada.</span><span class="sxs-lookup"><span data-stu-id="12d57-111">Use the General page to view or modify index properties for the selected table or view.</span></span> <span data-ttu-id="12d57-112">As opções para cada página podem mudar de acordo com o tipo de índice selecionado.</span><span class="sxs-lookup"><span data-stu-id="12d57-112">The options for each page may change based on the type of index selected.</span></span>  
  
 <span data-ttu-id="12d57-113">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="12d57-113">**Table name**</span></span>  
 <span data-ttu-id="12d57-114">Exibe o nome da tabela ou exibição na qual o índice foi criado.</span><span class="sxs-lookup"><span data-stu-id="12d57-114">Displays the name of the table or view that the index was created on.</span></span> <span data-ttu-id="12d57-115">Esse campo é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="12d57-115">This field is read-only.</span></span> <span data-ttu-id="12d57-116">Para selecionar uma tabela diferente, feche a página Propriedades do Índice, selecione a tabela correta e, em seguida, abra a página Propriedades do Índice novamente.</span><span class="sxs-lookup"><span data-stu-id="12d57-116">To select a different table, close the Index Properties page, select the correct table, and then open the Index Properties page again.</span></span>  
  
 <span data-ttu-id="12d57-117">Não é possível especificar índices espaciais em exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="12d57-117">Spatial indexes cannot be specified on indexed views.</span></span> <span data-ttu-id="12d57-118">Os índices espaciais podem ser definidos apenas em uma tabela com uma chave primária.</span><span class="sxs-lookup"><span data-stu-id="12d57-118">Spatial indexes can be defined only for a table that has a primary key.</span></span> <span data-ttu-id="12d57-119">O número máximo de colunas de chave primária na tabela é 15.</span><span class="sxs-lookup"><span data-stu-id="12d57-119">The maximum number of primary key columns on the table is 15.</span></span> <span data-ttu-id="12d57-120">O tamanho por linha combinado das colunas de chave primária é limitado a um máximo de 895 bytes.</span><span class="sxs-lookup"><span data-stu-id="12d57-120">The combined per-row size of the primary-key columns is limited to a maximum of 895 bytes.</span></span>  
  
 <span data-ttu-id="12d57-121">**Nome do índice**</span><span class="sxs-lookup"><span data-stu-id="12d57-121">**Index name**</span></span>  
 <span data-ttu-id="12d57-122">Exibe o nome do índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-122">Displays the name of the index.</span></span> <span data-ttu-id="12d57-123">Este campo é somente leitura para um índice existente.</span><span class="sxs-lookup"><span data-stu-id="12d57-123">This field is read-only for an existing index.</span></span> <span data-ttu-id="12d57-124">Ao criar um novo índice, digite o nome do índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-124">When creating a new index, type the name of the index.</span></span>  
  
 <span data-ttu-id="12d57-125">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="12d57-125">**Index type**</span></span>  
 <span data-ttu-id="12d57-126">Indica o tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-126">Indicates the type of index.</span></span> <span data-ttu-id="12d57-127">Para novos índices, indica o tipo de índice selecionado ao abrir a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="12d57-127">For new indexes, indicates the type of index selected when opening the dialog box.</span></span> <span data-ttu-id="12d57-128">Os índices podem ser: **Clusterizado**, **Não clusterizado**, **XML primário**, **XML secundário**, **Espacial**, **Columnstore clusterizado** ou **Columnstore não clusterizado**.</span><span class="sxs-lookup"><span data-stu-id="12d57-128">Indexes can be: **Clustered**, **Nonclustered**, **Primary XML**, **Secondary XML**, **Spatial**, **Clustered columnstore**, or **Nonclustered Columnstore**.</span></span>  
  
 <span data-ttu-id="12d57-129">**Observação** É permitido somente um índice clusterizado para cada tabela.</span><span class="sxs-lookup"><span data-stu-id="12d57-129">**Note** Only one clustered index is allowed for each table.</span></span> <span data-ttu-id="12d57-130">É permitido somente um índice columnstore xVelocity de memória otimizada para cada tabela.</span><span class="sxs-lookup"><span data-stu-id="12d57-130">Only one xVelocity memory optimized columnstore index is allowed for each table.</span></span>  
  
 <span data-ttu-id="12d57-131">**Exclusivo**</span><span class="sxs-lookup"><span data-stu-id="12d57-131">**Unique**</span></span>  
 <span data-ttu-id="12d57-132">A marcação desta caixa de seleção torna o índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="12d57-132">Selecting this check box makes the index unique.</span></span> <span data-ttu-id="12d57-133">Não é permitido que duas linhas tenham o mesmo valor de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-133">No two rows are permitted to have the same index value.</span></span> <span data-ttu-id="12d57-134">Por padrão, essa caixa de seleção é desmarcada.</span><span class="sxs-lookup"><span data-stu-id="12d57-134">By default, this check box is cleared.</span></span> <span data-ttu-id="12d57-135">Ao modificar um índice existente, haverá falha na criação do índice se duas linhas tiverem o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="12d57-135">When modifying an existing index, index creation will fail if two rows have the same value.</span></span> <span data-ttu-id="12d57-136">Para colunas onde NULL é permitido, um índice exclusivo permite um valor NULL.</span><span class="sxs-lookup"><span data-stu-id="12d57-136">For columns where NULL is permitted, a unique index permits one NULL value.</span></span>  
  
 <span data-ttu-id="12d57-137">Se você selecionar **Espacial** no campo **Tipo de índice** , a caixa de seleção **Exclusiva** ficará esmaecida.</span><span class="sxs-lookup"><span data-stu-id="12d57-137">If you select **Spatial** in the **Index type** field, the **Unique** check box is dimmed.</span></span>  
  
 <span data-ttu-id="12d57-138">**Colunas de chave de índice**</span><span class="sxs-lookup"><span data-stu-id="12d57-138">**Index key columns**</span></span>  
 <span data-ttu-id="12d57-139">Adicione as colunas desejadas à grade **Colunas de chave de índice** .</span><span class="sxs-lookup"><span data-stu-id="12d57-139">Add the desired columns to the **Index key columns** grid.</span></span> <span data-ttu-id="12d57-140">Quando mais de uma coluna é adicionada, as colunas devem ser listadas na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="12d57-140">When more than one column is added, the columns must be listed in the order desired.</span></span> <span data-ttu-id="12d57-141">A ordem de coluna em um índice pode ter um grande impacto no desempenho do índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-141">The column order in an index can have a great impact on the index performance.</span></span>  
  
 <span data-ttu-id="12d57-142">Não é permitido que mais de 16 colunas participem de um único índice composto.</span><span class="sxs-lookup"><span data-stu-id="12d57-142">No more than 16 columns can participate in a single composite index.</span></span> <span data-ttu-id="12d57-143">Para mais de 16 colunas, consulte as colunas incluídas no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="12d57-143">For greater than 16 columns, see included columns at the end of this topic.</span></span>  
  
 <span data-ttu-id="12d57-144">É possível definir um índice espacial apenas em uma coluna que contenha um tipo de dados espaciais (uma *coluna espacial*).</span><span class="sxs-lookup"><span data-stu-id="12d57-144">A spatial index can be defined only on a single column that contains a spatial data type (a *spatial column*).</span></span>  
  
 <span data-ttu-id="12d57-145">**Nome**</span><span class="sxs-lookup"><span data-stu-id="12d57-145">**Name**</span></span>  
 <span data-ttu-id="12d57-146">Exibe o nome da coluna que participa da chave de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-146">Displays the name of the column that participates in the index key.</span></span>  
  
 <span data-ttu-id="12d57-147">**Sort Order**</span><span class="sxs-lookup"><span data-stu-id="12d57-147">**Sort Order**</span></span>  
 <span data-ttu-id="12d57-148">Especifica a direção da classificação da coluna de índice selecionada, **Crescente** ou **Decrescente**.</span><span class="sxs-lookup"><span data-stu-id="12d57-148">Specifies the sort direction of the selected index column, either **Ascending** or **Descending**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d57-149">Se o tipo de índice for **XML primário** ou **Espacial**, esta coluna não aparecerá na tabela.</span><span class="sxs-lookup"><span data-stu-id="12d57-149">If the index type is **Primary XML** or **Spatial**, this column does not appear in the table.</span></span>  
  
 <span data-ttu-id="12d57-150">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="12d57-150">**Data Type**</span></span>  
 <span data-ttu-id="12d57-151">Exibe a informações de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="12d57-151">Displays the data type information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d57-152">Se a coluna de tabela for uma coluna computada, **Tipo de dados** exibirá "coluna computada".</span><span class="sxs-lookup"><span data-stu-id="12d57-152">If the table column is a computed column, **Data type** displays "computed column."</span></span>  
  
 <span data-ttu-id="12d57-153">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="12d57-153">**Size**</span></span>  
 <span data-ttu-id="12d57-154">Exibe o número máximo de bytes necessários para armazenar o tipo de dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="12d57-154">Displays the maximum number of bytes required to store the column data type.</span></span> <span data-ttu-id="12d57-155">Exibe zero (0) para uma coluna espacial ou XML.</span><span class="sxs-lookup"><span data-stu-id="12d57-155">Displays zero (0) for a spatial or XML column.</span></span>  
  
 <span data-ttu-id="12d57-156">**Identidade**</span><span class="sxs-lookup"><span data-stu-id="12d57-156">**Identity**</span></span>  
 <span data-ttu-id="12d57-157">Exibe se a coluna que participa da chave de índice é uma coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="12d57-157">Displays whether the column participating in the index key is an identity column.</span></span>  
  
 <span data-ttu-id="12d57-158">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="12d57-158">**Allow NULLs**</span></span>  
 <span data-ttu-id="12d57-159">Exibe se a coluna que participa da chave de índice permite armazenar valores NULL na tabela ou coluna de exibição.</span><span class="sxs-lookup"><span data-stu-id="12d57-159">Displays whether the column participating in the index key allows NULL values to be stored in the table or view column.</span></span>  
  
 <span data-ttu-id="12d57-160">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="12d57-160">**Add**</span></span>  
 <span data-ttu-id="12d57-161">Adiciona uma coluna à chave de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-161">Adds a column to the index key.</span></span> <span data-ttu-id="12d57-162">Selecione colunas de tabela na caixa de diálogo **Selecionar Colunas de** *\<table name>* que aparece quando você clica em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="12d57-162">Select table columns from the **Select Columns from** *\<table name>* dialog box that appears when you click **Add**.</span></span> <span data-ttu-id="12d57-163">No caso de um índice espacial, depois que você seleciona uma coluna, este botão fica esmaecido.</span><span class="sxs-lookup"><span data-stu-id="12d57-163">For a spatial index, after you select one column, this button is dimmed.</span></span>  
  
 <span data-ttu-id="12d57-164">**Remover**</span><span class="sxs-lookup"><span data-stu-id="12d57-164">**Remove**</span></span>  
 <span data-ttu-id="12d57-165">Remove a coluna selecionada da participação na chave de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-165">Removes the selected column from participation in the index key.</span></span>  
  
 <span data-ttu-id="12d57-166">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="12d57-166">**Move Up**</span></span>  
 <span data-ttu-id="12d57-167">Move a coluna selecionada para cima na grade de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-167">Moves the selected column up in the index key grid.</span></span>  
  
 <span data-ttu-id="12d57-168">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="12d57-168">**Move Down**</span></span>  
 <span data-ttu-id="12d57-169">Move a coluna selecionada para baixo na grade de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-169">Moves the selected column down in the index key grid.</span></span>  
  
 <span data-ttu-id="12d57-170">**Colunas Columnstore**</span><span class="sxs-lookup"><span data-stu-id="12d57-170">**Columnstore columns**</span></span>  
 <span data-ttu-id="12d57-171">Clique em **Adicionar** para selecionar colunas para o índice columnstore.</span><span class="sxs-lookup"><span data-stu-id="12d57-171">Click **Add** to select columns for the columnstore index.</span></span> <span data-ttu-id="12d57-172">Para limitações em um índice columnstore, consulte [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12d57-172">For limitations on a columnstore index, see [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span></span>  
  
 <span data-ttu-id="12d57-173">**Colunas incluídas**</span><span class="sxs-lookup"><span data-stu-id="12d57-173">**Included columns**</span></span>  
 <span data-ttu-id="12d57-174">Inclua colunas não chave no índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="12d57-174">Include nonkey columns in the nonclustered index.</span></span> <span data-ttu-id="12d57-175">Essa opção permite ignorar os limites de índices atuais no tamanho total de uma chave de índice e o número máximo de colunas que participam de uma chave de índice, adicionando colunas como colunas não chave no nível folha do índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="12d57-175">This option allows you to bypass the current index limits on the total size of an index key and the maximum number of columns participating in an index key by adding columns as nonkey columns in the leaf level of the nonclustered index.</span></span> <span data-ttu-id="12d57-176">Para obter mais informações, consulte [Criar índices com colunas incluídas](create-indexes-with-included-columns.md)</span><span class="sxs-lookup"><span data-stu-id="12d57-176">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md)</span></span>  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> <span data-ttu-id="12d57-177">Caixa de diálogo Selecionar Colunas (Índice)</span><span class="sxs-lookup"><span data-stu-id="12d57-177">Select (Index) Columns Dialog Box</span></span>  
 <span data-ttu-id="12d57-178">Use esta página para adicionar colunas à página **Propriedades Gerais do Índice** ao criar ou modificar um índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-178">Use this page to add columns to the **Index Properties General** page when creating or modifying an index.</span></span>  
  
 <span data-ttu-id="12d57-179">**Caixa de seleção**</span><span class="sxs-lookup"><span data-stu-id="12d57-179">**Check box**</span></span>  
 <span data-ttu-id="12d57-180">Selecione para adicionar colunas.</span><span class="sxs-lookup"><span data-stu-id="12d57-180">Select to add columns.</span></span>  
  
 <span data-ttu-id="12d57-181">**Nome**</span><span class="sxs-lookup"><span data-stu-id="12d57-181">**Name**</span></span>  
 <span data-ttu-id="12d57-182">Nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="12d57-182">Name of the column.</span></span>  
  
 <span data-ttu-id="12d57-183">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="12d57-183">**Data Type**</span></span>  
 <span data-ttu-id="12d57-184">O tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="12d57-184">The data type of the column.</span></span>  
  
 <span data-ttu-id="12d57-185">**Bytes**</span><span class="sxs-lookup"><span data-stu-id="12d57-185">**Bytes**</span></span>  
 <span data-ttu-id="12d57-186">Tamanho da coluna em bytes.</span><span class="sxs-lookup"><span data-stu-id="12d57-186">The size of the column in bytes.</span></span>  
  
 <span data-ttu-id="12d57-187">**Identidade**</span><span class="sxs-lookup"><span data-stu-id="12d57-187">**Identity**</span></span>  
 <span data-ttu-id="12d57-188">Exibe **Sim** para colunas de identidade e **Não** quando a coluna não é uma coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="12d57-188">Displays **Yes** for identity columns, and **No** when the column is not an identity column.</span></span>  
  
 <span data-ttu-id="12d57-189">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="12d57-189">**Allow Nulls**</span></span>  
 <span data-ttu-id="12d57-190">Exibe **Sim** quando a definição da tabela permitir valores nulos para a coluna.</span><span class="sxs-lookup"><span data-stu-id="12d57-190">Displays **Yes** when the table definition allows null values for the column.</span></span> <span data-ttu-id="12d57-191">Exibe **Não** quando a definição da tabela não permite nulos para a coluna.</span><span class="sxs-lookup"><span data-stu-id="12d57-191">Displays **No** when the table definition does not allow nulls for the column.</span></span>  
  
##  <a name="storage-page-options"></a><a name="Storage"></a> <span data-ttu-id="12d57-192">Opções da página de armazenamento</span><span class="sxs-lookup"><span data-stu-id="12d57-192">Storage Page Options</span></span>  
 <span data-ttu-id="12d57-193">Use essa página para exibir ou modificar grupo de arquivos ou propriedades de esquema de partição para o índice selecionado.</span><span class="sxs-lookup"><span data-stu-id="12d57-193">Use this page to view or modify filegroup or partition scheme properties for the selected index.</span></span> <span data-ttu-id="12d57-194">Mostra apenas opções relacionadas ao tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-194">Only shows options related to the type of index.</span></span>  
  
 <span data-ttu-id="12d57-195">**Grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="12d57-195">**Filegroup**</span></span>  
 <span data-ttu-id="12d57-196">Armazena o índice no grupo de arquivos especificado.</span><span class="sxs-lookup"><span data-stu-id="12d57-196">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="12d57-197">A lista exibe apenas grupos de arquivos padrão (linha).</span><span class="sxs-lookup"><span data-stu-id="12d57-197">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="12d57-198">A seleção de lista padrão é o grupo de arquivos PRIMARY do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12d57-198">The default list selection is the PRIMARY filegroup of the database.</span></span> <span data-ttu-id="12d57-199">Para obter mais informações, consulte [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-199">For more information, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
 <span data-ttu-id="12d57-200">**Grupos de Arquivos do Fluxo de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="12d57-200">**Filestream filegroup**</span></span>  
 <span data-ttu-id="12d57-201">Especifica o grupo de arquivos para obter dados de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="12d57-201">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="12d57-202">Essa lista exibe apenas grupos de arquivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="12d57-202">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="12d57-203">A seleção de lista padrão é o grupo de arquivos PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="12d57-203">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span> <span data-ttu-id="12d57-204">Para obter mais informações, veja [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-204">For more information, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="12d57-205">**Esquema de partição**</span><span class="sxs-lookup"><span data-stu-id="12d57-205">**Partition scheme**</span></span>  
 <span data-ttu-id="12d57-206">Armazena o índice em um esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="12d57-206">Stores the index in a partition scheme.</span></span> <span data-ttu-id="12d57-207">Clicando em **Esquema de Partição** a grade abaixo é habilitada.</span><span class="sxs-lookup"><span data-stu-id="12d57-207">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="12d57-208">A seleção de lista padrão é o esquema de partição usado para armazenar os dados de tabela.</span><span class="sxs-lookup"><span data-stu-id="12d57-208">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="12d57-209">Ao selecionar um esquema de partição diferente na lista, a informações na grade é atualizada.</span><span class="sxs-lookup"><span data-stu-id="12d57-209">When you select a different partition scheme in the list, the information in the grid is updated.</span></span> <span data-ttu-id="12d57-210">Para saber mais, confira [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-210">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="12d57-211">A opção de esquema de partição fica indisponível se não houver nenhum esquema de partição no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12d57-211">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="12d57-212">**Esquema de Partição do Fluxo de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="12d57-212">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="12d57-213">Especifica o esquema de partição para dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="12d57-213">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="12d57-214">O esquema de partição deve ser simétrico com o esquema especificado na opção **Esquema de partição** .</span><span class="sxs-lookup"><span data-stu-id="12d57-214">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="12d57-215">Se a tabela não for particionada, o campo fica em branco.</span><span class="sxs-lookup"><span data-stu-id="12d57-215">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="12d57-216">**Parâmetro do Esquema de Partição**</span><span class="sxs-lookup"><span data-stu-id="12d57-216">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="12d57-217">Exibe o nome da coluna que participa do esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="12d57-217">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="12d57-218">**Coluna de tabela**</span><span class="sxs-lookup"><span data-stu-id="12d57-218">**Table Column**</span></span>  
 <span data-ttu-id="12d57-219">Selecione a tabela ou exiba para mapear para o esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="12d57-219">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="12d57-220">**Tipo de dados da coluna**</span><span class="sxs-lookup"><span data-stu-id="12d57-220">**Column Data Type**</span></span>  
 <span data-ttu-id="12d57-221">Exibe informações de tipo de dados sobre a coluna.</span><span class="sxs-lookup"><span data-stu-id="12d57-221">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d57-222">Se a coluna de tabela for uma coluna computada, **Tipo de Dados da Coluna** exibirá "coluna computada."</span><span class="sxs-lookup"><span data-stu-id="12d57-222">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="12d57-223">**Permitir o processamento online de instruções DML ao mover o índice**</span><span class="sxs-lookup"><span data-stu-id="12d57-223">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="12d57-224">Permite aos usuários acessar a tabela subjacente ou dados de índice clusterizado associados a quaisquer índices não clusterizados durante a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-224">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span> <span data-ttu-id="12d57-225">Para obter mais informações, consulte [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-225">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d57-226">Esta opção não está disponível para índices XML ou se o índice for um índice clusterizadoF desabilitado.</span><span class="sxs-lookup"><span data-stu-id="12d57-226">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="12d57-227">**Definir grau máximo de paralelismo**</span><span class="sxs-lookup"><span data-stu-id="12d57-227">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="12d57-228">Limita o número de processadores a serem usados durante execução do plano paralelo.</span><span class="sxs-lookup"><span data-stu-id="12d57-228">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="12d57-229">O valor padrão, 0, usa o número real de CPUs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12d57-229">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="12d57-230">A definição do valor como 1 elimina a geração em plano paralelo; a definição do valor como um número maior que 1 restringe o número máximo de processadores usados por uma única execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="12d57-230">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="12d57-231">Esta opção ficará disponível apenas se a caixa de diálogo estiver no estado **Recriar** ou **Recriar** .</span><span class="sxs-lookup"><span data-stu-id="12d57-231">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span> <span data-ttu-id="12d57-232">Para obter mais informações, consulte [definir o Max Degree of Parallelism opção para otimizar o desempenho](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-232">For more information, see [Set the Max Degree of Parallelism Option for Optimal Performance](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d57-233">Se um valor maior que o número de CPUs disponíveis for especificado, será usado o número real de CPUs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12d57-233">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> <span data-ttu-id="12d57-234">Opções de índice da página Espacial</span><span class="sxs-lookup"><span data-stu-id="12d57-234">Spatial Page Index Options</span></span>  
 <span data-ttu-id="12d57-235">Use a página **Espacial** para exibir ou especificar os valores das propriedades espaciais.</span><span class="sxs-lookup"><span data-stu-id="12d57-235">Use the **Spatial** page to view or specify the values of the spatial properties.</span></span> <span data-ttu-id="12d57-236">Para obter mais informações, veja [Dados espaciais &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-236">For more information, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
### <a name="bounding-box"></a><span data-ttu-id="12d57-237">Caixa delimitadora</span><span class="sxs-lookup"><span data-stu-id="12d57-237">Bounding Box</span></span>  
 <span data-ttu-id="12d57-238">A *caixa delimitadora* é o perímetro da grade de alto nível de um plano geométrico.</span><span class="sxs-lookup"><span data-stu-id="12d57-238">The *bounding box* is the perimeter of the top-level grid of a geometric plane.</span></span> <span data-ttu-id="12d57-239">Os parâmetros da caixa delimitadora só existem no mosaico de grade geométrica.</span><span class="sxs-lookup"><span data-stu-id="12d57-239">The bounding-box parameters exist only in the geometry grid tessellation.</span></span> <span data-ttu-id="12d57-240">Esses parâmetros ficarão indisponíveis se o **Esquema de Mosaico** for **Grade geográfica**.</span><span class="sxs-lookup"><span data-stu-id="12d57-240">These parameters are unavailable if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="12d57-241">O painel exibe as coordenadas **( *`X-min`* , *`Y-min`* )** e **( *`X-max`* , *`Y-max`* )** da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="12d57-241">The panel displays the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="12d57-242">Não há valores de coordenada padrão.</span><span class="sxs-lookup"><span data-stu-id="12d57-242">There are no default coordinate values.</span></span> <span data-ttu-id="12d57-243">Portanto, ao criar um novo índice espacial em uma `geometry` coluna de tipo, será necessário especificar os valores de coordenada.</span><span class="sxs-lookup"><span data-stu-id="12d57-243">Therefore, when you are creating a new spatial index on a `geometry` type column, you must specify the coordinate values.</span></span>  
  
 `X-min`  
 <span data-ttu-id="12d57-244">A coordenada X do canto inferior esquerdo da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="12d57-244">The X-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `Y-min`  
 <span data-ttu-id="12d57-245">A coordenada Y do canto inferior esquerdo da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="12d57-245">The Y-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `X-max`  
 <span data-ttu-id="12d57-246">Coordenada X do canto superior direito da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="12d57-246">The X-coordinate of the upper-right corner of the bounding box.</span></span>  
  
 `Y-max`  
 <span data-ttu-id="12d57-247">Coordenada Y do canto superior direito da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="12d57-247">The Y-coordinate of upper-right corner of the bounding box.</span></span>  
  
### <a name="general"></a><span data-ttu-id="12d57-248">Geral</span><span class="sxs-lookup"><span data-stu-id="12d57-248">General</span></span>  
 <span data-ttu-id="12d57-249">**Esquema de Mosaico**</span><span class="sxs-lookup"><span data-stu-id="12d57-249">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="12d57-250">Indica o esquema de mosaico do índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-250">Indicates the tessellation scheme of the index.</span></span> <span data-ttu-id="12d57-251">Os esquemas de mosaico com suporte são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="12d57-251">The supported tessellation schemes are as follows.</span></span>  
  
 <span data-ttu-id="12d57-252">**Grade geométrica**</span><span class="sxs-lookup"><span data-stu-id="12d57-252">**Geometry grid**</span></span>  
 <span data-ttu-id="12d57-253">Especifica o esquema de mosaico de grade geométrica, que se aplica a uma coluna do tipo de dados `geometry`.</span><span class="sxs-lookup"><span data-stu-id="12d57-253">Specifies the geometry grid tessellation scheme, which applies to a column of the `geometry` data type.</span></span>  
  
 <span data-ttu-id="12d57-254">**Grade Automática de Geometria**</span><span class="sxs-lookup"><span data-stu-id="12d57-254">**Geometry Auto grid**</span></span>  
 <span data-ttu-id="12d57-255">Esta opção é habilitada para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando o nível de compatibilidade de banco de dados é definido como 110 ou superior.</span><span class="sxs-lookup"><span data-stu-id="12d57-255">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="12d57-256">**Grade geográfica**</span><span class="sxs-lookup"><span data-stu-id="12d57-256">**Geography grid**</span></span>  
 <span data-ttu-id="12d57-257">Especifica o esquema de mosaico de grade de geografia, que se aplica a uma coluna do tipo de dados **geografia** .</span><span class="sxs-lookup"><span data-stu-id="12d57-257">Specifies the geography grid tessellation scheme, which applies to a column of the **geography** data type.</span></span>  
  
 <span data-ttu-id="12d57-258">**Grade Automática de Geografia**</span><span class="sxs-lookup"><span data-stu-id="12d57-258">**Geography Auto grid**</span></span>  
 <span data-ttu-id="12d57-259">Esta opção é habilitada para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando o nível de compatibilidade de banco de dados é definido como 110 ou superior.</span><span class="sxs-lookup"><span data-stu-id="12d57-259">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="12d57-260">Para obter informações sobre como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implementa o mosaico, consulte [Dados espaciais &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-260">For information about how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implements tessellation, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="12d57-261">**Células por Objeto**</span><span class="sxs-lookup"><span data-stu-id="12d57-261">**Cells Per Object**</span></span>  
 <span data-ttu-id="12d57-262">Indica o número de células por objeto do mosaico que pode ser usado para um único objeto espacial no índice.</span><span class="sxs-lookup"><span data-stu-id="12d57-262">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="12d57-263">Esse número pode ser qualquer inteiro entre 1 e 8.192, inclusive.</span><span class="sxs-lookup"><span data-stu-id="12d57-263">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="12d57-264">O padrão é 16, e 8 para versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando o nível de compatibilidade de banco de dados é definido como 110 ou superior.</span><span class="sxs-lookup"><span data-stu-id="12d57-264">The default is 16, and 8 for earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="12d57-265">No nível superior, se um objeto abranger mais células que o especificado por *n*, a indexação usará o número de células necessário para fornecer um mosaico de nível superior completo.</span><span class="sxs-lookup"><span data-stu-id="12d57-265">At the top level, if an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="12d57-266">Nesses casos, um objeto poderia receber mais que o número de células especificado.</span><span class="sxs-lookup"><span data-stu-id="12d57-266">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="12d57-267">Nesse caso, o número máximo de células geradas pela grade de nível superior, que depende da densidade **Nível 1** .</span><span class="sxs-lookup"><span data-stu-id="12d57-267">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
### <a name="grids"></a><span data-ttu-id="12d57-268">Grades</span><span class="sxs-lookup"><span data-stu-id="12d57-268">Grids</span></span>  
 <span data-ttu-id="12d57-269">Este painel mostra a densidade da grade a cada nível do esquema de mosaico.</span><span class="sxs-lookup"><span data-stu-id="12d57-269">This panel shows the density of the grid at each level of the tessellation scheme.</span></span> <span data-ttu-id="12d57-270">A densidade é especificada como **Baixa**, **Média**ou **Alta**.</span><span class="sxs-lookup"><span data-stu-id="12d57-270">Density is specified as **Low**, **Medium**, or **High**.</span></span> <span data-ttu-id="12d57-271">O padrão **Média**.</span><span class="sxs-lookup"><span data-stu-id="12d57-271">The default is **Medium**.</span></span> <span data-ttu-id="12d57-272">**Baixa** representa uma grade de 4x4 (16 células), **Média** representa uma grade de 8x8 (64 células) e **Alta** representa uma grade de 16x16 (256 células).</span><span class="sxs-lookup"><span data-stu-id="12d57-272">**Low** represents a 4x4 grid (16 cells), **Medium** represents an 8x8 grid (64 cells), and **High** represents a 16x16 grid (256 cells).</span></span> <span data-ttu-id="12d57-273">Essas opções não estão disponíveis quando as opções de mosaico **Grade Automática de Geometria** ou **Grade Automática de Geografia** são escolhidas.</span><span class="sxs-lookup"><span data-stu-id="12d57-273">These options are not available when the **Geometry Auto grid** or **Geography Auto grid** tessellation options are chosen.</span></span>  
  
 <span data-ttu-id="12d57-274">**Nível 1**</span><span class="sxs-lookup"><span data-stu-id="12d57-274">**Level 1**</span></span>  
 <span data-ttu-id="12d57-275">A densidade da grade de primeiro nível (superior).</span><span class="sxs-lookup"><span data-stu-id="12d57-275">The density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="12d57-276">**Nível 2**</span><span class="sxs-lookup"><span data-stu-id="12d57-276">**Level 2**</span></span>  
 <span data-ttu-id="12d57-277">A densidade da grade de segundo nível.</span><span class="sxs-lookup"><span data-stu-id="12d57-277">The density of the second-level grid.</span></span>  
  
 <span data-ttu-id="12d57-278">**Nível 3**</span><span class="sxs-lookup"><span data-stu-id="12d57-278">**Level 3**</span></span>  
 <span data-ttu-id="12d57-279">A densidade da grade de terceiro nível.</span><span class="sxs-lookup"><span data-stu-id="12d57-279">The density of the third-level grid.</span></span>  
  
 <span data-ttu-id="12d57-280">**Nível 4**</span><span class="sxs-lookup"><span data-stu-id="12d57-280">**Level 4**</span></span>  
 <span data-ttu-id="12d57-281">A densidade da grade de quarto nível.</span><span class="sxs-lookup"><span data-stu-id="12d57-281">The density of the fourth-level grid.</span></span>  
  
##  <a name="filter-page"></a><a name="Filter"></a> <span data-ttu-id="12d57-282">Página de filtros</span><span class="sxs-lookup"><span data-stu-id="12d57-282">Filter Page</span></span>  
 <span data-ttu-id="12d57-283">Use esta página para inserir o predicado do filtro para um índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="12d57-283">Use this page to enter the filter predicate for a filtered index.</span></span> <span data-ttu-id="12d57-284">Para saber mais, confira [Create Filtered Indexes](create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="12d57-284">For more information, see [Create Filtered Indexes](create-filtered-indexes.md).</span></span>  
  
 <span data-ttu-id="12d57-285">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="12d57-285">**Filter Expression**</span></span>  
 <span data-ttu-id="12d57-286">Define quais linhas de dados devem ser incluídas no índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="12d57-286">Defines which data rows to include in the filtered index.</span></span> <span data-ttu-id="12d57-287">Por exemplo, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span><span class="sxs-lookup"><span data-stu-id="12d57-287">For example, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d57-288">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12d57-288">See Also</span></span>  
 <span data-ttu-id="12d57-289">[Opções Set Index](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="12d57-289">[Set Index Options](set-index-options.md) </span></span>  
 <span data-ttu-id="12d57-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12d57-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 [<span data-ttu-id="12d57-291">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="12d57-291">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
