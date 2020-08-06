---
title: Caixa de diálogo Editar propriedades da tabela (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.edittablepropdb.f1
ms.assetid: 8d913e83-7246-44cc-8fc7-31729023c0d8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6664d244f5f653610b37bd628abdb2263e015c0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582186"
---
# <a name="edit-table-properties-dialog-box-ssas"></a><span data-ttu-id="682e1-102">Caixa de diálogo Editar Propriedades da Tabela (SSAS)</span><span class="sxs-lookup"><span data-stu-id="682e1-102">Edit Table Properties Dialog Box (SSAS)</span></span>
  <span data-ttu-id="682e1-103">A caixa de diálogo **Editar Propriedades da Tabela** o habilita a exibir e modificar as propriedades de tabelas que são importadas para o designer de modelo usando o Assistente de Importação de Tabela.</span><span class="sxs-lookup"><span data-stu-id="682e1-103">The **Edit Table Properties** dialog box enables you to view and modify the properties of tables that are imported into the model designer by using the Table Import Wizard.</span></span> <span data-ttu-id="682e1-104">Para acessar essa caixa de diálogo, no designer de modelo, selecione uma tabela de dados que foi importada, clique no menu **Tabela** e em **Propriedades da Tabela**.</span><span class="sxs-lookup"><span data-stu-id="682e1-104">To access this dialog box, in the model designer, select a table, then click the **Table** menu, and then click **Table Properties**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="682e1-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="682e1-105">UI element list</span></span>  
 <span data-ttu-id="682e1-106">As opções desta caixa de diálogo são diferentes, dependendo de como você importou os dados: originalmente selecionando tabelas em uma lista ou usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="682e1-106">The options for this dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span>  
  
## <a name="table-preview-mode"></a><span data-ttu-id="682e1-107">Modo de visualização de tabela</span><span class="sxs-lookup"><span data-stu-id="682e1-107">Table Preview Mode</span></span>  
 <span data-ttu-id="682e1-108">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="682e1-108">**Table name**</span></span>  
 <span data-ttu-id="682e1-109">Exibe o nome da tabela de dados no modelo.</span><span class="sxs-lookup"><span data-stu-id="682e1-109">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="682e1-110">Não é possível editar o nome aqui.</span><span class="sxs-lookup"><span data-stu-id="682e1-110">You cannot edit the name here.</span></span> <span data-ttu-id="682e1-111">No entanto, você pode alterar o nome da tabela clicando com o botão direito do mouse na guia da tabela, na parte inferior do designer do modelo.</span><span class="sxs-lookup"><span data-stu-id="682e1-111">However, you can change the name of the table by right-clicking the table tab at the bottom of the model designer.</span></span>  
  
 <span data-ttu-id="682e1-112">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="682e1-112">**Connection name**</span></span>  
 <span data-ttu-id="682e1-113">Exibe o nome da conexão que está em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="682e1-113">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="682e1-114">**Nome de origem**</span><span class="sxs-lookup"><span data-stu-id="682e1-114">**Source name**</span></span>  
 <span data-ttu-id="682e1-115">Exiba ou altere a tabela a partir da qual os dados são obtidos.</span><span class="sxs-lookup"><span data-stu-id="682e1-115">Display or change the table from which the data is obtained.</span></span>  
  
 <span data-ttu-id="682e1-116">Se você alterar a origem para uma tabela que tenha colunas diferentes das da tabela atual, uma mensagem será exibida, avisando que as colunas são diferentes.</span><span class="sxs-lookup"><span data-stu-id="682e1-116">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="682e1-117">Em seguida, você deve selecionar as colunas que deseja colocar na tabela atual e clicar em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="682e1-117">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="682e1-118">Você pode substituir toda a tabela marcando a caixa de seleção no lado esquerdo da tabela.</span><span class="sxs-lookup"><span data-stu-id="682e1-118">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="682e1-119">Quando você altera a fonte de dados de uma tabela, basicamente substitui o conteúdo da tabela atual pelo conteúdo da nova tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="682e1-119">When you change the data source of a table, you essentially replace the contents of the current table with the contents of the new source table.</span></span>  
  
 <span data-ttu-id="682e1-120">**Nomes das colunas de**</span><span class="sxs-lookup"><span data-stu-id="682e1-120">**Column names from**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="682e1-121">**Origem**</span><span class="sxs-lookup"><span data-stu-id="682e1-121">**Source**</span></span>|<span data-ttu-id="682e1-122">Selecione esta opção para substituir os nomes de colunas atuais pelos nomes das colunas da tabela de origem selecionada.</span><span class="sxs-lookup"><span data-stu-id="682e1-122">Select this option to replace the current column names with the column names from the selected source table.</span></span>|  
|<span data-ttu-id="682e1-123">**Deprecia**</span><span class="sxs-lookup"><span data-stu-id="682e1-123">**Model**</span></span>|<span data-ttu-id="682e1-124">Selecione esta opção para usar os nomes de colunas atuais como existem no modelo.</span><span class="sxs-lookup"><span data-stu-id="682e1-124">Select this option to use the current column names as they exist in the model.</span></span>|  
  
 <span data-ttu-id="682e1-125">**Atualizar visualização**</span><span class="sxs-lookup"><span data-stu-id="682e1-125">**Refresh preview**</span></span>  
 <span data-ttu-id="682e1-126">Clique para exibir as colunas de dados na tabela de origem selecionada atualmente.</span><span class="sxs-lookup"><span data-stu-id="682e1-126">Click to view the columns of data in the currently selected source table.</span></span>  
  
 <span data-ttu-id="682e1-127">**Alternar para**</span><span class="sxs-lookup"><span data-stu-id="682e1-127">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="682e1-128">**Visualização de tabela**</span><span class="sxs-lookup"><span data-stu-id="682e1-128">**Table preview**</span></span>|<span data-ttu-id="682e1-129">Selecione esta opção para visualizar a tabela selecionada e um número limitado de linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="682e1-129">Select this option to preview the selected table and a limited number of rows of data.</span></span>|  
|<span data-ttu-id="682e1-130">**Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="682e1-130">**Query editor**</span></span>|<span data-ttu-id="682e1-131">Selecione esta opção para exibir a consulta em relação à fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="682e1-131">Select this option to view the query against the selected data source.</span></span> <span data-ttu-id="682e1-132">Esta opção não está disponível para todas as fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="682e1-132">This option is not available for all data sources.</span></span>|  
  
 <span data-ttu-id="682e1-133">**Caixa de seleção no cabeçalho da coluna**</span><span class="sxs-lookup"><span data-stu-id="682e1-133">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="682e1-134">Marque a caixa de seleção para incluir a coluna na importação de dados.</span><span class="sxs-lookup"><span data-stu-id="682e1-134">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="682e1-135">Desmarque a caixa de seleção para remover a coluna da importação de dados.</span><span class="sxs-lookup"><span data-stu-id="682e1-135">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="682e1-136">**Botão de seta para baixo no cabeçalho da coluna**</span><span class="sxs-lookup"><span data-stu-id="682e1-136">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="682e1-137">Filtre dados na coluna.</span><span class="sxs-lookup"><span data-stu-id="682e1-137">Filter data in the column.</span></span>  
  
 <span data-ttu-id="682e1-138">**Limpar filtros de linha**</span><span class="sxs-lookup"><span data-stu-id="682e1-138">**Clear row filters**</span></span>  
 <span data-ttu-id="682e1-139">Clique para remover os filtros que foram aplicados.</span><span class="sxs-lookup"><span data-stu-id="682e1-139">Click to remove any filters that have been applied.</span></span>  
  
 <span data-ttu-id="682e1-140">**OK**</span><span class="sxs-lookup"><span data-stu-id="682e1-140">**OK**</span></span>  
 <span data-ttu-id="682e1-141">Clique para aplicar todas as alterações feitas, incluindo a substituição de colunas.</span><span class="sxs-lookup"><span data-stu-id="682e1-141">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="query-design-mode"></a><span data-ttu-id="682e1-142">Modo de design de consulta</span><span class="sxs-lookup"><span data-stu-id="682e1-142">Query Design Mode</span></span>  
 <span data-ttu-id="682e1-143">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="682e1-143">**Table name**</span></span>  
 <span data-ttu-id="682e1-144">Exibe o nome da tabela de dados no modelo.</span><span class="sxs-lookup"><span data-stu-id="682e1-144">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="682e1-145">O nome não pode ser editado aqui, mas pode ser alterado clicando com o botão direito do mouse na guia da tabela, na parte inferior do designer.</span><span class="sxs-lookup"><span data-stu-id="682e1-145">You cannot edit the name here; however, you can change the name of the table by right-clicking the table tab at the bottom of the designer.</span></span>  
  
 <span data-ttu-id="682e1-146">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="682e1-146">**Connection name**</span></span>  
 <span data-ttu-id="682e1-147">Exibe o nome da conexão que está em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="682e1-147">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="682e1-148">**Alternar para**</span><span class="sxs-lookup"><span data-stu-id="682e1-148">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="682e1-149">**Visualização de tabela**</span><span class="sxs-lookup"><span data-stu-id="682e1-149">**Table preview**</span></span>|<span data-ttu-id="682e1-150">Selecione esta opção para visualizar a tabela selecionada e algumas linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="682e1-150">Select this option to preview the selected table and a few rows of data.</span></span>|  
|<span data-ttu-id="682e1-151">**Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="682e1-151">**Query editor**</span></span>|<span data-ttu-id="682e1-152">Selecione esta opção para visualizar a consulta que será emitida em relação à fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="682e1-152">Select this option to view the query that will be issued against the selected data source.</span></span>|  
  
 <span data-ttu-id="682e1-153">**Instrução SQL**</span><span class="sxs-lookup"><span data-stu-id="682e1-153">**Sql statement**</span></span>  
 <span data-ttu-id="682e1-154">Exibe a instrução SQL emitida em relação à fonte de dados atual para recuperar linhas.</span><span class="sxs-lookup"><span data-stu-id="682e1-154">Displays the SQL statement that is issued against the current data source to retrieve rows.</span></span> <span data-ttu-id="682e1-155">Por padrão, todas as linhas são recuperadas, mas é possível recuperar um subconjunto de linhas, criando um filtro ou editando manualmente a instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="682e1-155">By default, all rows are retrieved, but you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="682e1-156">**Validar**</span><span class="sxs-lookup"><span data-stu-id="682e1-156">**Validate**</span></span>  
 <span data-ttu-id="682e1-157">Clique para verificar se a instrução está sintaticamente correta para a fonte de dados selecionada e o provedor.</span><span class="sxs-lookup"><span data-stu-id="682e1-157">Click to verify that the statement is syntactically correct for the selected data source and provider.</span></span>  
  
 <span data-ttu-id="682e1-158">**Projetar**</span><span class="sxs-lookup"><span data-stu-id="682e1-158">**Design**</span></span>  
 <span data-ttu-id="682e1-159">Clique para abrir um designer de consulta visual e criar uma instrução de consulta.</span><span class="sxs-lookup"><span data-stu-id="682e1-159">Click to open a visual query designer and build a query statement.</span></span> <span data-ttu-id="682e1-160">Para obter informações sobre como usar o designer, pressione F1 no designer.</span><span class="sxs-lookup"><span data-stu-id="682e1-160">For information about how to use the designer, press F1 from the designer.</span></span>  
  
 <span data-ttu-id="682e1-161">**OK**</span><span class="sxs-lookup"><span data-stu-id="682e1-161">**OK**</span></span>  
 <span data-ttu-id="682e1-162">Clique para aplicar todas as alterações feitas, incluindo a substituição de colunas.</span><span class="sxs-lookup"><span data-stu-id="682e1-162">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="682e1-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="682e1-163">See Also</span></span>  
 [<span data-ttu-id="682e1-164">Tabelas e colunas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="682e1-164">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
