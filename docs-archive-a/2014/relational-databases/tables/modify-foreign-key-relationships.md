---
title: Modificar relações de chave estrangeira | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65538
- vdt.ppg.relationships
helpviewer_keywords:
- foreign keys [SQL Server], modifying
- modifying foreign keys
ms.assetid: 0c9ca80d-d79b-44c4-a21e-0fce39c398ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: ba9010b0d634a174dd35391c870d5003aa78efa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569844"
---
# <a name="modify-foreign-key-relationships"></a><span data-ttu-id="5aa6b-102">Modificar relações de chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="5aa6b-102">Modify Foreign Key Relationships</span></span>
  <span data-ttu-id="5aa6b-103">Você pode modificar parte da chave estrangeira de uma relação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aa6b-103">You can modify the foreign key side of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5aa6b-104">Modificar a chave estrangeira de uma tabela altera as colunas que estão relacionadas às colunas na tabela de chaves primárias.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-104">Modifying a table's foreign key changes which columns are related to columns in the primary key table.</span></span>  
  
 <span data-ttu-id="5aa6b-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5aa6b-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5aa6b-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5aa6b-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5aa6b-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="5aa6b-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5aa6b-109">**Para modificar uma chave estrangeira usando:**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-109">**To modify a foreign key using:**</span></span>  
  
     [<span data-ttu-id="5aa6b-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5aa6b-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5aa6b-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5aa6b-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5aa6b-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5aa6b-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5aa6b-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5aa6b-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5aa6b-114">A nova coluna de chave estrangeira deve corresponder ao tipo de dados e ao tamanho da coluna de chave primária à qual está relacionada, com estas exceções:</span><span class="sxs-lookup"><span data-stu-id="5aa6b-114">The new foreign key column must match the data type and size of the primary key column to which it relates, with these exceptions:</span></span>  
  
-   <span data-ttu-id="5aa6b-115">Uma coluna `char` ou `sysname` pode estar relacionada a uma coluna `varchar`.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-115">A `char` column or `sysname` column can relate to a `varchar` column.</span></span>  
  
-   <span data-ttu-id="5aa6b-116">Uma coluna `binary` pode estar relacionada a uma coluna `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-116">A `binary` column can relate to a `varbinary` column.</span></span>  
  
-   <span data-ttu-id="5aa6b-117">Um tipo de dados de alias pode estar relacionado ao seu tipo base.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-117">An alias data type can relate to its base type.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5aa6b-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="5aa6b-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5aa6b-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="5aa6b-119">Permissions</span></span>  
 <span data-ttu-id="5aa6b-120">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-120">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5aa6b-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5aa6b-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-foreign-key"></a><span data-ttu-id="5aa6b-122">Para modificar uma chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="5aa6b-122">To modify a foreign key</span></span>  
  
1.  <span data-ttu-id="5aa6b-123">No **Pesquisador de Objetos**, expanda a tabela com a chave estrangeira e expanda **Chaves**.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-123">In **Object Explorer**, expand the table with the foreign key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="5aa6b-124">Clique com o botão direito do mouse na chave estrangeira a ser modificada e selecione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-124">Right-click the foreign key to be modified and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="5aa6b-125">Na caixa de diálogo **Relações de Chaves Estrangeiras** , você pode fazer as modificações a seguir.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-125">In the **Foreign Key Relationships** dialog box, you can make the following modifications.</span></span>  
  
     <span data-ttu-id="5aa6b-126">**Relações Selecionadas**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-126">**Selected Relationship**</span></span>  
     <span data-ttu-id="5aa6b-127">Lista de relações existentes.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-127">Lists existing relationships.</span></span> <span data-ttu-id="5aa6b-128">Selecione uma relação para mostrar as propriedades na grade à direita.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-128">Select a relationship to show its properties in the grid to the right.</span></span> <span data-ttu-id="5aa6b-129">Se a lista estiver vazia, nenhuma relação foi definida para a tabela.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-129">If the list is empty, no relationships have been defined for the table.</span></span>  
  
     <span data-ttu-id="5aa6b-130">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-130">**Add**</span></span>  
     <span data-ttu-id="5aa6b-131">Crie uma nova relação.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-131">Create a new relationship.</span></span> <span data-ttu-id="5aa6b-132">As **Especificações de Tabelas e Colunas** devem ser definidas antes de a relação tornar-se válida.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-132">The **Tables and Columns Specifications** must be set before the relationship will be valid.</span></span>  
  
     <span data-ttu-id="5aa6b-133">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-133">**Delete**</span></span>  
     <span data-ttu-id="5aa6b-134">Exclua a relação selecionada na lista de **Relações Selecionadas** .</span><span class="sxs-lookup"><span data-stu-id="5aa6b-134">Delete the relationship selected in the **Selected Relationships** list.</span></span> <span data-ttu-id="5aa6b-135">Para cancelar a adição de uma relação, use esse botão para remover a relação.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-135">To cancel the addition of a relationship, use this button to remove the relationship.</span></span>  
  
     <span data-ttu-id="5aa6b-136">**Categoria Geral**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-136">**General Category**</span></span>  
     <span data-ttu-id="5aa6b-137">Expanda para mostrar **Verificar Dados Existentes ao Criar ou Habilitar Novamente** e **Especificações de Tabelas e Colunas**.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-137">Expand to show **Check Existing Data on Creation or RE-Enabling** and **Tables and Columns Specifications**.</span></span>  
  
     <span data-ttu-id="5aa6b-138">**Check Existing Data on Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-138">**Check Existing Data on Creation or Re-Enabling**</span></span>  
     <span data-ttu-id="5aa6b-139">Verifique todos os dados anteriores existentes na tabela quando a restrição foi criada ou habilitada novamente, em relação à restrição.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-139">Verify all existing data in the table before the constraint was created or re-enabled, against the constraint.</span></span>  
  
     <span data-ttu-id="5aa6b-140">**Categoria de Especificações de Tabelas e Colunas**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-140">**Tables and Columns Specifications Category**</span></span>  
     <span data-ttu-id="5aa6b-141">Expanda para mostrar quais colunas de quais tabelas atuam como a chave estrangeira e chave primária (ou exclusiva) na relação.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-141">Expand to show which columns from which tables act as the foreign key and primary (or unique) key in the relationship.</span></span> <span data-ttu-id="5aa6b-142">Para editar ou definir esses valores, clique no botão de reticências ( **...** ) à direita do campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-142">To edit or define these values, click the ellipsis button (**...**) to the right of the property field.</span></span>  
  
     <span data-ttu-id="5aa6b-143">**Tabela Base de Chaves Estrangeiras**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-143">**Foreign Key Base Table**</span></span>  
     <span data-ttu-id="5aa6b-144">Mostra qual tabela contém a coluna que atua como uma chave estrangeira na relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-144">Shows which table contains the column acting as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="5aa6b-145">**Colunas de Chave Estrangeira**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-145">**Foreign Key Columns**</span></span>  
     <span data-ttu-id="5aa6b-146">Mostra qual coluna atua como uma chave estrangeira na relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-146">Shows which column acts as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="5aa6b-147">**Tabela Base de Chaves Primárias/Exclusivas**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-147">**Primary/Unique Key Base Table**</span></span>  
     <span data-ttu-id="5aa6b-148">Mostra qual tabela contém a coluna que atua como uma chave primária (ou exclusiva) na relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-148">Shows which table contains the column acting as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="5aa6b-149">**Colunas de Chaves Primárias/Exclusivas**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-149">**Primary/Unique Key Columns**</span></span>  
     <span data-ttu-id="5aa6b-150">Mostra qual coluna atua como uma chave primária (ou exclusiva) na relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-150">Shows which column acts as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="5aa6b-151">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-151">**Identity Category**</span></span>  
     <span data-ttu-id="5aa6b-152">Expanda para mostrar os campos de propriedade para **Nome** e **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-152">Expand to show the property fields for **Name** and **Description**.</span></span>  
  
     <span data-ttu-id="5aa6b-153">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-153">**Name**</span></span>  
     <span data-ttu-id="5aa6b-154">Mostra o nome da relação.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-154">Shows the name of the relationship.</span></span> <span data-ttu-id="5aa6b-155">Quando uma nova relação é criada, é determinado um nome padrão com base na tabela na janela ativa em **Designer de Tabela**.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-155">When a new relationship is created, it is given a default name based on the table in the active window in **Table Designer**.</span></span> <span data-ttu-id="5aa6b-156">É possível alterar o nome a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-156">You can change the name at any time.</span></span>  
  
     <span data-ttu-id="5aa6b-157">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-157">**Description**</span></span>  
     <span data-ttu-id="5aa6b-158">Descreve a relação.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-158">Describe the relationship.</span></span> <span data-ttu-id="5aa6b-159">Para redigir uma descrição mais detalhada, clique em **Descrição** e nas reticências **(...)** que aparecem à direita do campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-159">To write a more detailed description, click **Description** and then click the ellipsis **(...)** that appears to the right of the property field.</span></span> <span data-ttu-id="5aa6b-160">Isso criará uma área maior para a redação do texto.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-160">This provides a larger area in which to write text.</span></span>  
  
     <span data-ttu-id="5aa6b-161">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-161">**Table Designer Category**</span></span>  
     <span data-ttu-id="5aa6b-162">Expanda para mostrar informações por **Verificar Dados Existentes ao Criar ou Habilitar Novamente** e **Impor para Replicação**.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-162">Expand to show information for **Check Existing Data on Creation or Re-Enabling** and **Enforce for Replication**.</span></span>  
  
     <span data-ttu-id="5aa6b-163">**Impor para Replicação**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-163">**Enforce For Replication**</span></span>  
     <span data-ttu-id="5aa6b-164">Indica se a restrição será imposta quando um agente de replicação realizar uma inserção, atualização ou exclusão na tabela.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-164">Indicates whether to enforce the constraint when a replication agent performs an insert, update, or delete on this table.</span></span>  
  
     <span data-ttu-id="5aa6b-165">**Impor Restrição de Chave Estrangeira**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-165">**Enforce Foreign Key Constraint**</span></span>  
     <span data-ttu-id="5aa6b-166">Especifique se alterações são permitidas para dados das colunas na relação, caso as alterações invalidem a integridade da relação de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-166">Specify whether changes are allowed to the data of the columns in the relationship if those changes would invalidate the integrity of the foreign key relationship.</span></span> <span data-ttu-id="5aa6b-167">Escolha **Sim** se não deseja permitir mudanças, e escolha **Não** se deseja permiti-las.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-167">Choose **Yes** if you do not want to allow such changes, and choose **No** if you do want to allow them.</span></span>  
  
     <span data-ttu-id="5aa6b-168">**Categoria de Especificação INSERT e UPDATE**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-168">**INSERT and UPDATE Specification Category**</span></span>  
     <span data-ttu-id="5aa6b-169">Expanda para mostrar informações pelo **Excluir Regra** e o **Atualizar Regra** para a relação.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-169">Expand to show information for the **Delete Rule** and the **Update Rule** for the relationship.</span></span>  
  
     <span data-ttu-id="5aa6b-170">**Excluir Regra**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-170">**Delete Rule**</span></span>  
     <span data-ttu-id="5aa6b-171">Especifique o que acontece se um usuário tenta excluir uma linha com dados que é envolvida em uma relação de chave estrangeira:</span><span class="sxs-lookup"><span data-stu-id="5aa6b-171">Specify what happens if a user tries to delete a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="5aa6b-172">**Sem Ação** Uma mensagem de erro avisa ao usuário que a exclusão não é permitida e o DELETE será revertido.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-172">**No Action** An error message tells the user that the deletion is not allowed and the DELETE is rolled back.</span></span>  
  
    -   <span data-ttu-id="5aa6b-173">**Cascata** Exclui todas as linhas que contêm dados envolvidos na relação de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-173">**Cascade** Deletes all rows containing data involved in the foreign key relationship.</span></span> <span data-ttu-id="5aa6b-174">Não especifique CASCADE se a tabela for incluída em uma publicação de mesclagem que usa registros lógicos.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-174">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="5aa6b-175">**Definir Nulo** Definirá o valor como nulo se todas as colunas de chave estrangeira da tabela puderem aceitar valores nulos.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-175">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="5aa6b-176">**Definir Padrão** Definirá o valor para o valor padrão definido para a coluna, se todas as colunas de chave estrangeira para a tabela possuírem padrões definidos.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-176">**Set Default** Sets the value to the default value defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
     <span data-ttu-id="5aa6b-177">**Atualizar Regra**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-177">**Update Rule**</span></span>  
     <span data-ttu-id="5aa6b-178">Especifique o que ocorre se um usuário tenta atualizar uma linha com dados que é envolvida em uma relação de chave estrangeira:</span><span class="sxs-lookup"><span data-stu-id="5aa6b-178">Specify what occurs if a user tries to update a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="5aa6b-179">**Sem Ação** Uma mensagem de erro avisa ao usuário que a atualização não é permitida e o UPDATE será revertido.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-179">**No Action** An error message tells the user that the update is not allowed and the UPDATE is rolled back.</span></span>  
  
    -   <span data-ttu-id="5aa6b-180">**Cascata** Atualiza todas as linhas que contêm dados envolvidos na relação de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-180">**Cascade** Updates all rows that contain data involved in the foreign key relationship.</span></span> <span data-ttu-id="5aa6b-181">Não especifique CASCADE se a tabela for incluída em uma publicação de mesclagem que usa registros lógicos.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-181">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="5aa6b-182">**Definir Nulo** Definirá o valor como nulo se todas as colunas de chave estrangeira da tabela puderem aceitar valores nulos.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-182">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="5aa6b-183">**Definir Padrão** Define o valor como o valor padrão que é definido para a coluna se todas as colunas de chave estrangeira para a tabela têm padrões definidos.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-183">**Set Default** Sets the value to the default value that is defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
4.  <span data-ttu-id="5aa6b-184">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-184">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5aa6b-185">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5aa6b-185">Using Transact-SQL</span></span>  
 <span data-ttu-id="5aa6b-186">**Para modificar uma chave estrangeira**</span><span class="sxs-lookup"><span data-stu-id="5aa6b-186">**To modify a foreign key**</span></span>  
  
 <span data-ttu-id="5aa6b-187">Para modificar uma restrição FOREIGN KEY usando o Transact-SQL, exclua primeiramente a FOREIGN KEY já existente e, em seguida, recrie-a com a nova definição.</span><span class="sxs-lookup"><span data-stu-id="5aa6b-187">To modify a FOREIGN KEY constraint by using Transact-SQL, you must first delete the existing FOREIGN KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="5aa6b-188">Para obter mais informações, consulte [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) e [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="5aa6b-188">For more information, see [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) and [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
