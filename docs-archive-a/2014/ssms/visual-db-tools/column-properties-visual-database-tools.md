---
title: Propriedades de Coluna (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.Column.ColumnIdentitySpec
- vdt.designers.properties.Column
- vdt.tablecolumn
- vdt.designers.properties.Column.ColumnComputedColumnSpec
- vdt.designers.properties.Column.ColumnFulltextSpec
ms.assetid: e549a2a8-4154-4ec8-b146-614564169b39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6aeb4d01cae7c09c27cafa8284638bf0a7de9691
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678521"
---
# <a name="column-properties-visual-database-tools"></a><span data-ttu-id="26f27-102">Propriedades de Coluna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="26f27-102">Column Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="26f27-103">Existem dois conjuntos de propriedades para colunas: um conjunto completo que pode ser visto na guia **Propriedades da Coluna** dentro do Designer de Tabela (disponível somente para bancos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) e um subconjunto que pode ser visto na janela Propriedades usando o Gerenciador de Servidores.</span><span class="sxs-lookup"><span data-stu-id="26f27-103">There are two sets of properties for columns: a full set that you can see in the **Column Properties** tab within Table Designer (available only for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) and a subset you can see in the Properties window using Server Explorer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26f27-104">As propriedades desse tópico são classificadas por categoria e não em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="26f27-104">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26f27-105">As caixas de diálogo e os comandos de menu encontrados podem diferir daqueles descritos na Ajuda, dependendo das configurações ativas ou edição.</span><span class="sxs-lookup"><span data-stu-id="26f27-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="26f27-106">Para alterar suas configurações, selecione **Importar e Exportar Configurações** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="26f27-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
## <a name="properties-window"></a><span data-ttu-id="26f27-107">Janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="26f27-107">Properties Window</span></span>  
 <span data-ttu-id="26f27-108">Essas propriedades aparecem na janela Propriedades quando você seleciona a coluna em Gerenciador de Servidores.</span><span class="sxs-lookup"><span data-stu-id="26f27-108">These properties appear in the Properties window when you select a column in Server Explorer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26f27-109">Essas propriedades, acessadas usando-se o Gerenciador de Servidores, são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="26f27-109">These properties, accessed using Server Explorer, are read-only.</span></span> <span data-ttu-id="26f27-110">Para editar as propriedades da coluna para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , selecione a coluna no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="26f27-110">To edit column properties for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, select the column in Table Designer.</span></span> <span data-ttu-id="26f27-111">Essas propriedades são descritas mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="26f27-111">Those properties are described later in this topic.</span></span>  
  
 <span data-ttu-id="26f27-112">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-112">**Identity Category**</span></span>  
 <span data-ttu-id="26f27-113">Expande para mostrar o **Nome** e propriedades de **Banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="26f27-113">Expands to show the **Name** and **Database** properties.</span></span>  
  
 <span data-ttu-id="26f27-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="26f27-114">**Name**</span></span>  
 <span data-ttu-id="26f27-115">Mostra o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-115">Shows the name of the column.</span></span>  
  
 <span data-ttu-id="26f27-116">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="26f27-116">**Database**</span></span>  
 <span data-ttu-id="26f27-117">Mostra o nome da fonte dos dados para a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="26f27-117">Shows the name of the data source for the selected column.</span></span> <span data-ttu-id="26f27-118">(Aplica-se somente a OLE DB.)</span><span class="sxs-lookup"><span data-stu-id="26f27-118">(Applies only to OLE DB.)</span></span>  
  
 <span data-ttu-id="26f27-119">**Categoria Misc**</span><span class="sxs-lookup"><span data-stu-id="26f27-119">**Misc Category**</span></span>  
 <span data-ttu-id="26f27-120">Expande para mostrar as propriedades restantes.</span><span class="sxs-lookup"><span data-stu-id="26f27-120">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="26f27-121">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="26f27-121">**Data Type**</span></span>  
 <span data-ttu-id="26f27-122">Mostra o tipo de dados da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="26f27-122">Shows the data type of the selected column.</span></span> <span data-ttu-id="26f27-123">Para obter mais informações, veja [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="26f27-123">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="26f27-124">**Incremento de Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-124">**Identity Increment**</span></span>  
 <span data-ttu-id="26f27-125">Mostra o incremento a ser adicionado à **Semente de Identidade** para cada linha seguinte da coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="26f27-125">Shows the increment that will be added to the **Identity Seed** for each subsequent row of the identity column.</span></span> <span data-ttu-id="26f27-126">(Aplica-se somente ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="26f27-126">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="26f27-127">**Semente de Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-127">**Identity Seed**</span></span>  
 <span data-ttu-id="26f27-128">Mostra o valor da semente atribuído à primeira linha da tabela para a coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="26f27-128">Shows the seed value assigned to the first row in the table for the identity column.</span></span> <span data-ttu-id="26f27-129">(Aplica-se somente ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="26f27-129">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="26f27-130">**É Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-130">**Is Identity**</span></span>  
 <span data-ttu-id="26f27-131">Mostra se a coluna selecionada é a coluna de identidade para a tabela.</span><span class="sxs-lookup"><span data-stu-id="26f27-131">Shows whether the selected column is the identity column for the table.</span></span> <span data-ttu-id="26f27-132">(Aplica-se somente ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="26f27-132">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="26f27-133">**Comprimento**</span><span class="sxs-lookup"><span data-stu-id="26f27-133">**Length**</span></span>  
 <span data-ttu-id="26f27-134">Mostra o número de caracteres permitido para tipos de dados com base em caractere.</span><span class="sxs-lookup"><span data-stu-id="26f27-134">Shows the number of characters allowed for character-based data types.</span></span>  
  
 <span data-ttu-id="26f27-135">**Permite valor nulo**</span><span class="sxs-lookup"><span data-stu-id="26f27-135">**Nullable**</span></span>  
 <span data-ttu-id="26f27-136">Mostra se a coluna permite ou não valores nulos.</span><span class="sxs-lookup"><span data-stu-id="26f27-136">Shows whether or not the column allows null values.</span></span>  
  
 <span data-ttu-id="26f27-137">**Precisão**</span><span class="sxs-lookup"><span data-stu-id="26f27-137">**Precision**</span></span>  
 <span data-ttu-id="26f27-138">Mostra o número máximo de dígitos permitido para tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-138">Shows the maximum number of digits allowed for numeric data types.</span></span> <span data-ttu-id="26f27-139">Essa propriedade mostra **0** para tipos de dados não numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-139">This property shows **0** for nonnumeric data types.</span></span>  
  
 <span data-ttu-id="26f27-140">**Escala**</span><span class="sxs-lookup"><span data-stu-id="26f27-140">**Scale**</span></span>  
 <span data-ttu-id="26f27-141">Mostra o número máximo de dígitos que podem aparecer à direita do ponto decimal para tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-141">Shows the maximum number of digits that can appear to the right of the decimal point for numeric data types.</span></span> <span data-ttu-id="26f27-142">Esse valor deve ser menor do que ou igual à precisão.</span><span class="sxs-lookup"><span data-stu-id="26f27-142">This value must be less than or equal to the precision.</span></span> <span data-ttu-id="26f27-143">Essa propriedade mostra **0** para tipos de dados não numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-143">This property shows **0** for nonnumeric data types.</span></span>  
  
## <a name="column-properties-tab"></a><span data-ttu-id="26f27-144">Guia Propriedades da Coluna</span><span class="sxs-lookup"><span data-stu-id="26f27-144">Column Properties Tab</span></span>  
 <span data-ttu-id="26f27-145">Para acessar essas propriedades, no Gerenciador de Servidores, clique com o botão direito do mouse na tabela à qual a coluna pertence, escolha **Abrir Definição de Tabela**e selecione a linha na grade de tabela em Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="26f27-145">To access these properties, in Server Explorer right-click the table to which the column belongs, choose **Open Table Definition**, and select the row in the table grid in Table Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26f27-146">Essas propriedades só se aplicam a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26f27-146">These properties apply only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="26f27-147">**Categoria Geral**</span><span class="sxs-lookup"><span data-stu-id="26f27-147">**General Category**</span></span>  
 <span data-ttu-id="26f27-148">Expande para mostrar **Nome**, **Permitir Nulos**, **Tipo de Dados**, **Valor Padrão ou Associação**, **Comprimento**, **Precisão**e **Escala**.</span><span class="sxs-lookup"><span data-stu-id="26f27-148">Expands to show **Name**, **Allow Nulls**, **Data Type**, **Default Value or Binding**, **Length**, **Precision**, and **Scale**.</span></span>  
  
 <span data-ttu-id="26f27-149">**Nome**</span><span class="sxs-lookup"><span data-stu-id="26f27-149">**Name**</span></span>  
 <span data-ttu-id="26f27-150">Exibe o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-150">Displays the name of the column.</span></span> <span data-ttu-id="26f27-151">Para editar o nome, digite-o na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="26f27-151">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="26f27-152">Se as consultas, exibições, funções definidas pelo usuário, procedimentos armazenados ou programas existentes se referirem à coluna, a alteração de nome tornará esses objetivos inválidos.</span><span class="sxs-lookup"><span data-stu-id="26f27-152">If existing queries, views, user-defined functions, stored procedures, or programs refer to the column, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="26f27-153">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="26f27-153">**Allow Nulls**</span></span>  
 <span data-ttu-id="26f27-154">Mostra se o tipo de dados da coluna permite ou não valores nulos.</span><span class="sxs-lookup"><span data-stu-id="26f27-154">Shows whether or not the column's data type allows null values.</span></span>  
  
 <span data-ttu-id="26f27-155">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="26f27-155">**Data Type**</span></span>  
 <span data-ttu-id="26f27-156">Mostra o tipo de dados para a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="26f27-156">Shows the data type for the selected column.</span></span> <span data-ttu-id="26f27-157">Para editar essa propriedade, clique em seu valor, expanda a lista suspensa e escolha outro valor.</span><span class="sxs-lookup"><span data-stu-id="26f27-157">To edit this property, click its value, expand the drop-down list, and choose another value.</span></span> <span data-ttu-id="26f27-158">Para obter mais informações, veja [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="26f27-158">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="26f27-159">**Valor Padrão ou Associação**</span><span class="sxs-lookup"><span data-stu-id="26f27-159">**Default Value or Binding**</span></span>  
 <span data-ttu-id="26f27-160">Mostra o padrão para essa coluna quando nenhum valor for especificado para essa coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-160">Shows the default for this column when no value is specified for this column.</span></span> <span data-ttu-id="26f27-161">A lista suspensa contém todos os padrões gerais definidos na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="26f27-161">The drop-down list contains all global defaults defined in the data source.</span></span> <span data-ttu-id="26f27-162">Para associar a coluna a um padrão geral, faça a seleção na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="26f27-162">To bind the column to a global default, select from the drop-down list.</span></span> <span data-ttu-id="26f27-163">Alternativamente, para criar uma restrição padrão para a coluna, digite o valor padrão diretamente como texto.</span><span class="sxs-lookup"><span data-stu-id="26f27-163">Alternatively, to create a default constraint for the column, type the default value directly as text.</span></span>  
  
 <span data-ttu-id="26f27-164">**Comprimento**</span><span class="sxs-lookup"><span data-stu-id="26f27-164">**Length**</span></span>  
 <span data-ttu-id="26f27-165">Mostra o número de caracteres permitido para tipos de dados com base em caractere.</span><span class="sxs-lookup"><span data-stu-id="26f27-165">Shows the number of characters allowed for character-based data types.</span></span> <span data-ttu-id="26f27-166">Essa propriedade só fica disponível para tipos de dados baseados em caractere.</span><span class="sxs-lookup"><span data-stu-id="26f27-166">This property is only available for character-based data types.</span></span>  
  
 <span data-ttu-id="26f27-167">**Precisão**</span><span class="sxs-lookup"><span data-stu-id="26f27-167">**Precision**</span></span>  
 <span data-ttu-id="26f27-168">Mostra o número máximo de dígitos permitido para tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-168">Shows the maximum number of digits allowed for numeric data types.</span></span> <span data-ttu-id="26f27-169">Essa propriedade mostra **0** para tipos de dados não numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-169">This property shows **0** for nonnumeric data types.</span></span> <span data-ttu-id="26f27-170">Essa propriedade só fica disponível para tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-170">This property is only available for numeric data types.</span></span>  
  
 <span data-ttu-id="26f27-171">**Escala**</span><span class="sxs-lookup"><span data-stu-id="26f27-171">**Scale**</span></span>  
 <span data-ttu-id="26f27-172">Mostra o número máximo de dígitos que podem aparecer à direita do ponto decimal para tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-172">Shows the maximum number of digits that can appear to the right of the decimal point for numeric data types.</span></span> <span data-ttu-id="26f27-173">Esse valor deve ser menor do que ou igual à precisão.</span><span class="sxs-lookup"><span data-stu-id="26f27-173">This value must be less than or equal to the precision.</span></span> <span data-ttu-id="26f27-174">Essa propriedade mostra **0** para tipos de dados não numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-174">This property shows **0** for nonnumeric data types.</span></span> <span data-ttu-id="26f27-175">Essa propriedade só fica disponível para tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="26f27-175">This property is only available for numeric data types.</span></span>  
  
 <span data-ttu-id="26f27-176">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="26f27-176">**Table Designer Category**</span></span>  
 <span data-ttu-id="26f27-177">Expande para mostrar as propriedades restantes.</span><span class="sxs-lookup"><span data-stu-id="26f27-177">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="26f27-178">**Ordenação**</span><span class="sxs-lookup"><span data-stu-id="26f27-178">**Collation**</span></span>  
 <span data-ttu-id="26f27-179">Mostra a configuração de ordenação da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="26f27-179">Shows the collation setting for the selected column.</span></span> <span data-ttu-id="26f27-180">Para alterar a configuração, clique em **Ordenação** e, então, clique nas reticências **(…)** à direita do valor.</span><span class="sxs-lookup"><span data-stu-id="26f27-180">To change this setting, click **Collation** and then click the ellipses **(...)** to the right of the value.</span></span>  
  
 <span data-ttu-id="26f27-181">**Categoria Especificação de Coluna Computada**</span><span class="sxs-lookup"><span data-stu-id="26f27-181">**Computed Column Specification Category**</span></span>  
 <span data-ttu-id="26f27-182">Expande para mostrar propriedades para **Fórmula** e **É Persistido**.</span><span class="sxs-lookup"><span data-stu-id="26f27-182">Expands to show properties for **Formula** and **Is Persisted**.</span></span> <span data-ttu-id="26f27-183">Se a coluna for computada, a fórmula também será exibida.</span><span class="sxs-lookup"><span data-stu-id="26f27-183">If the column is computed, the formula will also be displayed.</span></span> <span data-ttu-id="26f27-184">Para editar a fórmula, expanda essa categoria e edite na propriedade **Fórmula** .</span><span class="sxs-lookup"><span data-stu-id="26f27-184">To edit the formula, expand this category and edit it in the **Formula** property.</span></span>  
  
 <span data-ttu-id="26f27-185">**Fórmula**</span><span class="sxs-lookup"><span data-stu-id="26f27-185">**Formula**</span></span>  
 <span data-ttu-id="26f27-186">Mostra a fórmula que a coluna selecionada usa se for uma coluna computada.</span><span class="sxs-lookup"><span data-stu-id="26f27-186">Shows the formula that the selected column uses if it is a computed column.</span></span> <span data-ttu-id="26f27-187">Nesse campo é possível digitar ou alterar uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="26f27-187">In this field you can enter or change a formula.</span></span>  
  
 <span data-ttu-id="26f27-188">**É Persistido**</span><span class="sxs-lookup"><span data-stu-id="26f27-188">**Is Persisted**</span></span>  
 <span data-ttu-id="26f27-189">É possível salvar a coluna computada com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="26f27-189">Allows you to save the computed column with the data source.</span></span> <span data-ttu-id="26f27-190">É possível indexar uma coluna computada persistente.</span><span class="sxs-lookup"><span data-stu-id="26f27-190">A persisted computed column can be indexed.</span></span>  
  
 <span data-ttu-id="26f27-191">**Tipo de Dados Condensado**</span><span class="sxs-lookup"><span data-stu-id="26f27-191">**Condensed Data Type**</span></span>  
 <span data-ttu-id="26f27-192">Exibe informações sobre o tipo de dados do campo, no mesmo formato que a instrução SQL CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="26f27-192">Displays information about the field's data type, in the same format as the SQL CREATE TABLE statement.</span></span> <span data-ttu-id="26f27-193">Por exemplo, um campo que contém uma cadeia de caracteres de comprimento-variável com um comprimento máximo de 20 caracteres seria representado como "varchar(20).”</span><span class="sxs-lookup"><span data-stu-id="26f27-193">For example, a field containing a variable-length string with a maximum length of 20 characters would be represented as "varchar(20)."</span></span> <span data-ttu-id="26f27-194">Para alterar essa propriedade, digite o valor diretamente.</span><span class="sxs-lookup"><span data-stu-id="26f27-194">To change this property, type the value directly.</span></span>  
  
 <span data-ttu-id="26f27-195">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="26f27-195">**Description**</span></span>  
 <span data-ttu-id="26f27-196">Mostra a descrição da coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-196">Shows the description of the column.</span></span> <span data-ttu-id="26f27-197">Para ver a descrição completa ou editá-la, clique em Descrição e, então, clique nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="26f27-197">To see the full description or to edit it, click Description, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="26f27-198">**Categoria Especificação de Texto Completo**</span><span class="sxs-lookup"><span data-stu-id="26f27-198">**Full-text Specification Category**</span></span>  
 <span data-ttu-id="26f27-199">Expande para mostrar propriedades específicas para colunas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="26f27-199">Expands to show properties specific to full-text columns.</span></span>  
  
 <span data-ttu-id="26f27-200">**É Indexado com Texto Completo**</span><span class="sxs-lookup"><span data-stu-id="26f27-200">**Is Full-text Indexed**</span></span>  
 <span data-ttu-id="26f27-201">Indica se essa coluna é indexada com texto completo.</span><span class="sxs-lookup"><span data-stu-id="26f27-201">Indicates whether this column is full-text indexed.</span></span> <span data-ttu-id="26f27-202">Essa propriedade só poderá ser definida como **Sim** se o tipo de dados para essa coluna for pesquisável com texto completo e se a tabela à qual essa coluna pertence tiver um índice de texto completo especificado para isso.</span><span class="sxs-lookup"><span data-stu-id="26f27-202">This property can be set to **Yes** only if the data type for this column is full-text searchable and if the table to which this column belongs has a full-text index specified for it.</span></span> <span data-ttu-id="26f27-203">Para alterar esse valor, clique nele, expanda a lista suspensa e escolha um valor novo.</span><span class="sxs-lookup"><span data-stu-id="26f27-203">To change this value, click it, expand the drop-down list, and choose a new value.</span></span>  
  
 <span data-ttu-id="26f27-204">**Coluna de tipo de texto completo**</span><span class="sxs-lookup"><span data-stu-id="26f27-204">**Full-text type column**</span></span>  
 <span data-ttu-id="26f27-205">Mostra que coluna é usada para definir o tipo de documento de uma coluna do tipo imagem.</span><span class="sxs-lookup"><span data-stu-id="26f27-205">Shows which column is used to define the document type of a column of type image.</span></span> <span data-ttu-id="26f27-206">O tipo de dados de imagem pode ser usado para armazenar documentos que variam de arquivos .doc a arquivos a xml.</span><span class="sxs-lookup"><span data-stu-id="26f27-206">The image data type can be used to store documents ranging from .doc files to xml files.</span></span>  
  
 <span data-ttu-id="26f27-207">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="26f27-207">**Language**</span></span>  
 <span data-ttu-id="26f27-208">Indica a linguagem usada para indexar a coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-208">Indicates the language used to index the column.</span></span>  
  
 <span data-ttu-id="26f27-209">**Semântica Estatística**</span><span class="sxs-lookup"><span data-stu-id="26f27-209">**Statistical Semantics**</span></span>  
 <span data-ttu-id="26f27-210">Especifique se habilitará a semântica estatística da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="26f27-210">Select whether to enable statistical semantic indexing for the selected column.</span></span> <span data-ttu-id="26f27-211">Para obter mais informações, veja [Pesquisa semântica &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="26f27-211">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="26f27-212">Se você selecionar um **Idioma** antes de selecionar **Semântica Estatística**, e o idioma selecionado não tiver um Modelo de Idioma Semântico associado, a caixa de seleção **Semântica Estatística** será definida como **Não** e não poderá ser modificada.</span><span class="sxs-lookup"><span data-stu-id="26f27-212">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** option is set to **No** and cannot be modified.</span></span> <span data-ttu-id="26f27-213">Se você selecionar **Sim** na opção **Semântica Estatística** antes de selecionar um **Idioma**, os idiomas disponíveis na coluna **Idioma** serão restringidos a esses para os quais o Modelo de Idioma Semântico oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="26f27-213">If you select **Yes** for the **Statistical Semantics** option prior to selecting a **Language**, then the languages available in the **Language** column will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
 <span data-ttu-id="26f27-214">**Tem Assinante Não SQL Server**</span><span class="sxs-lookup"><span data-stu-id="26f27-214">**Has Non-SQL Server Subscriber**</span></span>  
 <span data-ttu-id="26f27-215">Mostra se a coluna tem um assinante não Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f27-215">Shows whether the column has a non-Microsoft SQL Server subscriber.</span></span>  
  
 <span data-ttu-id="26f27-216">**Categoria Especificação de Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-216">**Identity Specification Category**</span></span>  
 <span data-ttu-id="26f27-217">Expande para mostrar propriedades para **É Identidade**, **Incremento de Identidade**e **Semente de Identidade**.</span><span class="sxs-lookup"><span data-stu-id="26f27-217">Expands to show properties for **Is Identity**, **Identity Increment**, and **Identity Seed**.</span></span>  
  
 <span data-ttu-id="26f27-218">**É Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-218">**Is Identity**</span></span>  
 <span data-ttu-id="26f27-219">Mostra se a coluna selecionada é a coluna de identidade para a tabela.</span><span class="sxs-lookup"><span data-stu-id="26f27-219">Shows whether the selected column is the identity column for the table.</span></span> <span data-ttu-id="26f27-220">Para alterar a propriedade, abra a tabela em Designer de Tabela e edite as propriedades na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="26f27-220">To change the property, open the table in Table Designer and edit the properties in the **Properties** window.</span></span> <span data-ttu-id="26f27-221">Essa configuração se aplica apenas a colunas com um tipo de dados baseado em número, como *int*.</span><span class="sxs-lookup"><span data-stu-id="26f27-221">This setting applies only to columns with a number-based data type, such as *int*.</span></span>  
  
 <span data-ttu-id="26f27-222">**Incremento de Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-222">**Identity Increment**</span></span>  
 <span data-ttu-id="26f27-223">Mostra o incremento que será adicionado à **Semente de Identidade** para cada linha seguinte.</span><span class="sxs-lookup"><span data-stu-id="26f27-223">Shows the increment that will be added to the **Identity Seed** for each subsequent row.</span></span> <span data-ttu-id="26f27-224">Se essa célula for deixada em branco, o valor 1 será atribuído como padrão.</span><span class="sxs-lookup"><span data-stu-id="26f27-224">If you leave this cell blank, the value 1 will be assigned by default.</span></span> <span data-ttu-id="26f27-225">Para editar essa propriedade, digite o valor novo diretamente.</span><span class="sxs-lookup"><span data-stu-id="26f27-225">To edit this property, type the new value directly.</span></span>  
  
 <span data-ttu-id="26f27-226">**Semente de Identidade**</span><span class="sxs-lookup"><span data-stu-id="26f27-226">**Identity Seed**</span></span>  
 <span data-ttu-id="26f27-227">Mostra o valor atribuído à primeira linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="26f27-227">Shows the value assigned to the first row in the table.</span></span> <span data-ttu-id="26f27-228">Se essa célula for deixada em branco, o valor 1 será atribuído como padrão.</span><span class="sxs-lookup"><span data-stu-id="26f27-228">If you leave this cell blank, the value 1 will be assigned by default.</span></span> <span data-ttu-id="26f27-229">Para editar essa propriedade, digite o valor novo diretamente.</span><span class="sxs-lookup"><span data-stu-id="26f27-229">To edit this property, type the new value directly.</span></span>  
  
 <span data-ttu-id="26f27-230">**É Determinístico**</span><span class="sxs-lookup"><span data-stu-id="26f27-230">**Is Deterministic**</span></span>  
 <span data-ttu-id="26f27-231">Mostra se o tipo de dados da coluna selecionada pode ser determinado com certeza.</span><span class="sxs-lookup"><span data-stu-id="26f27-231">Shows whether the data type of the selected column can be determined with certainty.</span></span>  
  
 <span data-ttu-id="26f27-232">**É publicado por DTS**</span><span class="sxs-lookup"><span data-stu-id="26f27-232">**Is DTS-published**</span></span>  
 <span data-ttu-id="26f27-233">Mostra se a coluna é publicada por DTS.</span><span class="sxs-lookup"><span data-stu-id="26f27-233">Shows whether the column is DTS-published.</span></span>  
  
 <span data-ttu-id="26f27-234">**É Indexável**</span><span class="sxs-lookup"><span data-stu-id="26f27-234">**Is Indexable**</span></span>  
 <span data-ttu-id="26f27-235">Mostra se a coluna selecionada pode ser indexada.</span><span class="sxs-lookup"><span data-stu-id="26f27-235">Shows whether the selected column can be indexed.</span></span> <span data-ttu-id="26f27-236">Por exemplo, colunas calculadas não determinísticas não podem ser indexadas.</span><span class="sxs-lookup"><span data-stu-id="26f27-236">For example, non-deterministic computed columns cannot be indexed.</span></span>  
  
 <span data-ttu-id="26f27-237">**É Publicado por Mesclagem**</span><span class="sxs-lookup"><span data-stu-id="26f27-237">**Is Merge-published**</span></span>  
 <span data-ttu-id="26f27-238">Mostra se uma coluna é publicada por mesclagem.</span><span class="sxs-lookup"><span data-stu-id="26f27-238">Shows whether the column is merge-published.</span></span>  
  
 <span data-ttu-id="26f27-239">**Não é para Replicação**</span><span class="sxs-lookup"><span data-stu-id="26f27-239">**Is Not For Replication**</span></span>  
 <span data-ttu-id="26f27-240">Indica se os valores de identidade originais são preservados durante a replicação.</span><span class="sxs-lookup"><span data-stu-id="26f27-240">Indicates whether original identity values are preserved during replication.</span></span> <span data-ttu-id="26f27-241">Para editar essa propriedade, clique em seu valor, expanda a lista suspensa e escolha outro valor.</span><span class="sxs-lookup"><span data-stu-id="26f27-241">To edit this property, click its value, expand the drop-down list, and choose another value.</span></span>  
  
 <span data-ttu-id="26f27-242">**É Replicável**</span><span class="sxs-lookup"><span data-stu-id="26f27-242">**Is Replicated**</span></span>  
 <span data-ttu-id="26f27-243">Mostra se essa coluna é replicada em outro local.</span><span class="sxs-lookup"><span data-stu-id="26f27-243">Shows whether this column is replicated in another location.</span></span>  
  
 <span data-ttu-id="26f27-244">**É RowGuid**</span><span class="sxs-lookup"><span data-stu-id="26f27-244">**Is RowGuid**</span></span>  
 <span data-ttu-id="26f27-245">Indica se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa a coluna como ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="26f27-245">Indicates whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the column as a ROWGUID.</span></span> <span data-ttu-id="26f27-246">Você pode definir esse valor como **Sim** apenas para uma coluna com o tipo de dados de `uniqueidentifier` .</span><span class="sxs-lookup"><span data-stu-id="26f27-246">You can set this value to **Yes** only for a column with the data type of `uniqueidentifier`.</span></span> <span data-ttu-id="26f27-247">Para editar essa propriedade, clique em seu valor, expanda a lista suspensa e escolha outro valor.</span><span class="sxs-lookup"><span data-stu-id="26f27-247">To edit this property, click its value, expand the drop-down list, and choose another value.</span></span>  
  
 <span data-ttu-id="26f27-248">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="26f27-248">**Size**</span></span>  
 <span data-ttu-id="26f27-249">Mostra o tamanho em bytes permitido pelo tipo de dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-249">Shows the size in bytes allowed by column's data type.</span></span> <span data-ttu-id="26f27-250">Por exemplo, um tipo de dados `nchar` pode ter um comprimento de 10 (número de caracteres), mas teria um tamanho de 20 para conjuntos de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="26f27-250">For example, a `nchar` data type may have a length of 10 (the number of characters) but it would have a size of 20 to account for Unicode character sets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26f27-251">O comprimento de um tipo de dados `varchar(max)` varia para cada linha.</span><span class="sxs-lookup"><span data-stu-id="26f27-251">The length of a `varchar(max)` data type varies for each row.</span></span> <span data-ttu-id="26f27-252">sp_help retorna (-1) como o comprimento da `varchar(max)` coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-252">sp_help returns (-1) as the length of `varchar(max)` column.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="26f27-253">exibe -1 como o tamanho de coluna.</span><span class="sxs-lookup"><span data-stu-id="26f27-253">displays -1 as the column size.</span></span>  
  
  
