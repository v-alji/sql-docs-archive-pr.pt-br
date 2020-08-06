---
title: 'Passo a passo: adicionando e alterando um diagrama de banco de dados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], about database diagrams
- database diagrams [SQL Server], designing
- database diagrams [SQL Server], creating
ms.assetid: 228caa0d-8f24-46ab-86d1-b6d8631322bc
author: stevestein
ms.author: sstein
ms.openlocfilehash: c35eb3674c817e98a25a74cd0309fc7376fe2f58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569800"
---
# <a name="walkthrough-adding-and-changing-a-database-diagram"></a><span data-ttu-id="53bbd-102">Passo a passo: Adicionando e alterando um diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="53bbd-102">Walkthrough: Adding and Changing a Database Diagram</span></span>
  <span data-ttu-id="53bbd-103">Este passo a passo ilustra como criar e modificar um diagrama de banco de dados e fazer alterações no banco de dados por meio do componente de diagramas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="53bbd-103">This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component.</span></span> <span data-ttu-id="53bbd-104">Você verá como adicionar tabelas a diagramas, criar relações entre tabelas, criar restrições e índices em colunas, e alterar o nível das informações exibidas em cada tabela.</span><span class="sxs-lookup"><span data-stu-id="53bbd-104">You will see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53bbd-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="53bbd-105">Prerequisites</span></span>  
 <span data-ttu-id="53bbd-106">Para concluir este passo a passo, você precisará de:</span><span class="sxs-lookup"><span data-stu-id="53bbd-106">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="53bbd-107">Acesso ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53bbd-107">Access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database</span></span>  
  
-   <span data-ttu-id="53bbd-108">Uma conta com privilégios `dbo` de proprietário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="53bbd-108">An account with database owner `dbo` privileges</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53bbd-109">Se você tentar fazer alterações ao usar uma conta sem privilégios suficientes para fazer alterações em tabelas, uma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-109">If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.</span></span>  
  
## <a name="creating-a-diagram"></a><span data-ttu-id="53bbd-110">Criando um diagrama</span><span class="sxs-lookup"><span data-stu-id="53bbd-110">Creating a Diagram</span></span>  
  
#### <a name="to-create-a-new-database-diagram"></a><span data-ttu-id="53bbd-111">Para criar um novo diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="53bbd-111">To create a new database diagram</span></span>  
  
1.  <span data-ttu-id="53bbd-112">No menu **Exibir** , clique em **Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-112">On the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="53bbd-113">Abra o nó Bancos de dados e abra o nó do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53bbd-113">Open the Databases node and then open the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] node.</span></span>  
  
3.  <span data-ttu-id="53bbd-114">Clique com o botão direito do mouse no nó Diagramas de Banco de Dados e escolha **Novo Diagrama de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-114">Right-click the Database Diagrams node and choose **New Database Diagram**.</span></span>  
  
     <span data-ttu-id="53bbd-115">Se o banco de dados não tiver os objetos necessários para criar diagramas, a mensagem a seguir será exibida: **Este banco de dados não tem um ou mais dos objetos de suporte necessários para usar a diagramação de banco de dados. Deseja criá-los?**</span><span class="sxs-lookup"><span data-stu-id="53bbd-115">If the database does not have objects necessary to create diagrams, the following message appears: **This database does not have one or more of the support objects required to use database diagramming. Do you wish to create them?**</span></span> <span data-ttu-id="53bbd-116">Escolha **Sim**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-116">Choose **Yes**.</span></span>  
  
     <span data-ttu-id="53bbd-117">A caixa de diálogo **Adicionar Tabela** será exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-117">The **Add Table** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="53bbd-118">Selecione **Tipo de Endereço (Pessoa)** e **Endereço (Pessoa)** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-118">Select **AddressType (Person)** and **Address (Person)** and click **Add**.</span></span>  
  
     <span data-ttu-id="53bbd-119">Duas tabelas são adicionadas ao diagrama.</span><span class="sxs-lookup"><span data-stu-id="53bbd-119">Two tables are added to the diagram.</span></span>  
  
5.  <span data-ttu-id="53bbd-120">Feche a caixa de diálogo **Adicionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="53bbd-120">Close the **Add Table** dialog box.</span></span>  
  
#### <a name="to-view-different-column-data"></a><span data-ttu-id="53bbd-121">Para exibir diferentes dados de coluna</span><span class="sxs-lookup"><span data-stu-id="53bbd-121">To view different column data</span></span>  
  
1.  <span data-ttu-id="53bbd-122">Clique com o botão direito do mouse na tabela `Address` .</span><span class="sxs-lookup"><span data-stu-id="53bbd-122">Right-click the `Address` table.</span></span> <span data-ttu-id="53bbd-123">No menu de atalho, aponte para **Exibição de Tabela**e clique em **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-123">On the shortcut menu, point to **Table View**, and then click **Standard**.</span></span>  
  
     <span data-ttu-id="53bbd-124">A grade da tabela mostra três colunas: **Nome da Coluna**, **Tipo de Dados**e **Permitir Nulos**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-124">The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
2.  <span data-ttu-id="53bbd-125">Clique com o botão direito do mouse na tabela `Address` , clique em **Exibir Tabela** e selecione **Chaves**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-125">Right-click the `Address` table, click **Table View** and select **Keys**.</span></span>  
  
     <span data-ttu-id="53bbd-126">A grade da tabela mostra uma coluna, com os nomes da coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="53bbd-126">The table grid shows one column, with the table-column names.</span></span> <span data-ttu-id="53bbd-127">Somente as colunas que fazem parte dos índices aparecem.</span><span class="sxs-lookup"><span data-stu-id="53bbd-127">Only those columns participating in indexes appear.</span></span>  
  
## <a name="creating-new-tables"></a><span data-ttu-id="53bbd-128">Criando novas tabelas</span><span class="sxs-lookup"><span data-stu-id="53bbd-128">Creating New Tables</span></span>  
  
#### <a name="to-create-tables-within-diagram-designer"></a><span data-ttu-id="53bbd-129">Para criar tabelas dentro do Designer de Diagrama</span><span class="sxs-lookup"><span data-stu-id="53bbd-129">To create tables within Diagram Designer</span></span>  
  
1.  <span data-ttu-id="53bbd-130">Clique com o botão direito do mouse no Designer de Diagramas fora das tabelas existentes e escolha **Nova Tabela**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-130">Right-click the Diagram Designer outside the existing tables and choose **New Table**.</span></span>  
  
2.  <span data-ttu-id="53bbd-131">Na caixa de diálogo **escolher nome** , clique em **OK** para aceitar o nome padrão `Table1` .</span><span class="sxs-lookup"><span data-stu-id="53bbd-131">In the **Choose Name** dialog box, click **OK** to accept the default name `Table1`.</span></span>  
  
     <span data-ttu-id="53bbd-132">Uma nova grade de tabela aparece com três colunas: **Nome da Coluna**, **Tipo de Dados**e **Permitir Nulos**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-132">A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
3.  <span data-ttu-id="53bbd-133">Adicione as seguintes informações a `Table1` :</span><span class="sxs-lookup"><span data-stu-id="53bbd-133">Add the following information to `Table1`:</span></span>  
  
    |<span data-ttu-id="53bbd-134">**Nome da Coluna**</span><span class="sxs-lookup"><span data-stu-id="53bbd-134">**Column Name**</span></span>|<span data-ttu-id="53bbd-135">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="53bbd-135">**Data Type**</span></span>|<span data-ttu-id="53bbd-136">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="53bbd-136">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T1col1`|`int`|<span data-ttu-id="53bbd-137">checked</span><span class="sxs-lookup"><span data-stu-id="53bbd-137">checked</span></span>|  
    |`T1col2`|`varchar(50)`|<span data-ttu-id="53bbd-138">checked</span><span class="sxs-lookup"><span data-stu-id="53bbd-138">checked</span></span>|  
    |`T1col3`|`float`|<span data-ttu-id="53bbd-139">verificado</span><span class="sxs-lookup"><span data-stu-id="53bbd-139">checked</span></span>|  
  
4.  <span data-ttu-id="53bbd-140">Clique com o botão direito do mouse em `T1col1` e selecione **Definir Chave Primária**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-140">Right-click `T1col1` and select **Set Primary Key**.</span></span>  
  
     <span data-ttu-id="53bbd-141">Um ícone de chave aparecerá ao lado do nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="53bbd-141">A key icon will appear beside the column name.</span></span>  
  
5.  <span data-ttu-id="53bbd-142">No menu **Arquivo** , clique em **Salvar Diagrama1**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-142">From the **File** menu, click **Save Diagram1**.</span></span>  
  
6.  <span data-ttu-id="53bbd-143">Na caixa de diálogo **escolher nome** , clique em **OK** para aceitar o nome padrão `Diagram1` .</span><span class="sxs-lookup"><span data-stu-id="53bbd-143">In the **Choose Name** dialog box, click **OK** to accept the default name `Diagram1`.</span></span>  
  
7.  <span data-ttu-id="53bbd-144">A caixa de diálogo **Save** aparece com uma mensagem informando que `Table1` será salva no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="53bbd-144">The **Save** dialog box appears with a message that `Table1` will be saved to the database.</span></span> <span data-ttu-id="53bbd-145">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-145">Click **Yes**.</span></span>  
  
## <a name="modifying-table-structure"></a><span data-ttu-id="53bbd-146">Modificando a estrutura da tabela</span><span class="sxs-lookup"><span data-stu-id="53bbd-146">Modifying Table Structure</span></span>  
 <span data-ttu-id="53bbd-147">Você pode adicionar restrições de verificação e fazer relações entre tabelas no Designer de Diagrama.</span><span class="sxs-lookup"><span data-stu-id="53bbd-147">You can add check constraints and make relationships between tables in Diagram Designer.</span></span>  
  
#### <a name="to-create-check-constraints"></a><span data-ttu-id="53bbd-148">Para criar restrições de verificação</span><span class="sxs-lookup"><span data-stu-id="53bbd-148">To create check constraints</span></span>  
  
1.  <span data-ttu-id="53bbd-149">Na `Table1`, clique com o botão direito do mouse na linha `T1col3` e escolha **Restrições de Verificação**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-149">In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.</span></span>  
  
     <span data-ttu-id="53bbd-150">A caixa de diálogo **Restrições de Verificação** será exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-150">The **Check Constraints** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="53bbd-151">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-151">Click **Add**.</span></span>  
  
     <span data-ttu-id="53bbd-152">Uma nova restrição aparece na lista **Restrição de Verificação Selecionada** , com o nome padrão `CK_Table1`.</span><span class="sxs-lookup"><span data-stu-id="53bbd-152">A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.</span></span>  
  
3.  <span data-ttu-id="53bbd-153">Selecione a linha **Expressão** na grade e clique no botão de reticências.</span><span class="sxs-lookup"><span data-stu-id="53bbd-153">Select the **Expression** row in the grid and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="53bbd-154">A caixa de diálogo **Expressão de Restrição de Verificação** é exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-154">The **Check Constraint Expression** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="53bbd-155">Digite `T1col3 > 5` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-155">Type `T1col3 > 5` and click **OK**.</span></span>  
  
     <span data-ttu-id="53bbd-156">`Table1` agora tem uma restrição que todos os valores inseridos em `T1col3` devem ser maior que 5.</span><span class="sxs-lookup"><span data-stu-id="53bbd-156">`Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.</span></span>  
  
5.  <span data-ttu-id="53bbd-157">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-157">Click **Close**.</span></span>  
  
#### <a name="to-create-relationships-between-tables"></a><span data-ttu-id="53bbd-158">Para criar relações entre tabelas</span><span class="sxs-lookup"><span data-stu-id="53bbd-158">To create relationships between tables</span></span>  
  
1.  <span data-ttu-id="53bbd-159">Crie uma nova tabela no Designer de Diagrama denominada `Table2` com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="53bbd-159">Create a new table in Diagram designer named `Table2` with the following columns:</span></span>  
  
    |<span data-ttu-id="53bbd-160">**Nome da coluna**</span><span class="sxs-lookup"><span data-stu-id="53bbd-160">**Column Name**</span></span>|<span data-ttu-id="53bbd-161">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="53bbd-161">**Data Type**</span></span>|<span data-ttu-id="53bbd-162">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="53bbd-162">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T2col1`|`int`|<span data-ttu-id="53bbd-163">não verificado</span><span class="sxs-lookup"><span data-stu-id="53bbd-163">not checked</span></span>|  
    |`T2col2`|`varchar(50)`|<span data-ttu-id="53bbd-164">checked</span><span class="sxs-lookup"><span data-stu-id="53bbd-164">checked</span></span>|  
    |`T2col3`|`xml`|<span data-ttu-id="53bbd-165">checked</span><span class="sxs-lookup"><span data-stu-id="53bbd-165">checked</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="53bbd-166">As colunas no lado da chave primária de uma relação de chave estrangeira devem participar de uma Chave Primária ou de uma Restrição Exclusiva.</span><span class="sxs-lookup"><span data-stu-id="53bbd-166">The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.</span></span>  
  
2.  <span data-ttu-id="53bbd-167">Arraste `T2col1` para `T1col1`.</span><span class="sxs-lookup"><span data-stu-id="53bbd-167">Drag `T2col1` to `T1col1`.</span></span>  
  
     <span data-ttu-id="53bbd-168">Duas caixas de diálogo são exibidas: **Relação de Chaves Estrangeiras** na tela de fundo e **Tabelas e Colunas** em primeiro plano.</span><span class="sxs-lookup"><span data-stu-id="53bbd-168">Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.</span></span>  
  
3.  <span data-ttu-id="53bbd-169">Clique em **OK** para salvar a nova relação.</span><span class="sxs-lookup"><span data-stu-id="53bbd-169">Click **OK** to save the new relationship.</span></span>  
  
4.  <span data-ttu-id="53bbd-170">Clique em **OK** novamente.</span><span class="sxs-lookup"><span data-stu-id="53bbd-170">Click **OK** again.</span></span>  
  
## <a name="creating-indexes"></a><span data-ttu-id="53bbd-171">Criando índices</span><span class="sxs-lookup"><span data-stu-id="53bbd-171">Creating Indexes</span></span>  
 <span data-ttu-id="53bbd-172">Você pode criar índices na maioria dos tipos de dados, incluindo XML.</span><span class="sxs-lookup"><span data-stu-id="53bbd-172">You can create indexes on most types of data, including XML.</span></span>  
  
#### <a name="to-create-a-standard-index"></a><span data-ttu-id="53bbd-173">Para criar um índice padrão</span><span class="sxs-lookup"><span data-stu-id="53bbd-173">To create a standard index</span></span>  
  
1.  <span data-ttu-id="53bbd-174">Clique com o botão direito do mouse na `Table1` e escolha **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-174">Right-click `Table1` and choose **Indexes/Keys**.</span></span>  
  
     <span data-ttu-id="53bbd-175">A caixa de diálogo **Índices/Chaves** é exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-175">The **Indexes/Keys** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="53bbd-176">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-176">Click **Add**.</span></span>  
  
     <span data-ttu-id="53bbd-177">Um novo índice é exibido na lista **Índice ou Chave Exclusiva/Primária Selecionada** , com um nome padrão similar a `IX_Table1`.</span><span class="sxs-lookup"><span data-stu-id="53bbd-177">A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.</span></span>  
  
3.  <span data-ttu-id="53bbd-178">Selecione a linha **Colunas** e clique no botão de reticências.</span><span class="sxs-lookup"><span data-stu-id="53bbd-178">Select the **Columns** row and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="53bbd-179">A caixa de diálogo **Colunas de Índice** é exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-179">The **Index Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="53bbd-180">Clique na seta suspensa debaixo de **Nome da Coluna** e selecione `T1col2`.</span><span class="sxs-lookup"><span data-stu-id="53bbd-180">Click the drop-down arrow under **Column Name** and select `T1col2`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="53bbd-181">Você pode adicionar outras colunas a esse índice selecionando a célula debaixo de `T1col2` e escolhendo outro nome de coluna.</span><span class="sxs-lookup"><span data-stu-id="53bbd-181">You may add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.</span></span>  
  
5.  <span data-ttu-id="53bbd-182">Clique em **OK** para salvar esse índice.</span><span class="sxs-lookup"><span data-stu-id="53bbd-182">Click **OK** to save this index.</span></span>  
  
6.  <span data-ttu-id="53bbd-183">Clique em **Fechar** na caixa de diálogo **Índices/Chaves** .</span><span class="sxs-lookup"><span data-stu-id="53bbd-183">Click **Close** in the **Indexes/Keys** dialog box.</span></span>  
  
#### <a name="to-create-an-xml-index"></a><span data-ttu-id="53bbd-184">Para criar um índice XML</span><span class="sxs-lookup"><span data-stu-id="53bbd-184">To create an XML index</span></span>  
  
1.  <span data-ttu-id="53bbd-185">Clique com o botão direito do mouse em `T2col1` e escolha **Definir Chave Primária**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-185">Right-click `T2col1` and choose **Set Primary Key**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="53bbd-186">Adicionar um índice XML exige que outra coluna na tabela seja definida como uma chave primária clusterizada.</span><span class="sxs-lookup"><span data-stu-id="53bbd-186">Adding an XML index requires that another column in the table be set as a clustered primary key.</span></span>  
  
2.  <span data-ttu-id="53bbd-187">Clique com o botão direito do mouse na linha `T2col3` na `Table2` e selecione **Índices XML**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-187">Right-click the `T2col3` row in `Table2` and select **XML Indexes**.</span></span>  
  
     <span data-ttu-id="53bbd-188">A caixa de diálogo **Índices XML** é exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-188">The **XML Indexes** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="53bbd-189">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-189">Click **Add**.</span></span>  
  
     <span data-ttu-id="53bbd-190">Um índice XML com valores padrão será adicionado à lista **Índice XML Selecionado** .</span><span class="sxs-lookup"><span data-stu-id="53bbd-190">An XML index with default values will be added to the **Selected XML Index** list.</span></span>  
  
4.  <span data-ttu-id="53bbd-191">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-191">Click **Close**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="53bbd-192">Os índices XML são criados por coluna.</span><span class="sxs-lookup"><span data-stu-id="53bbd-192">XML indexes are created per-column.</span></span> <span data-ttu-id="53bbd-193">O primeiro índice XML é primário; qualquer índice adicional é secundário.</span><span class="sxs-lookup"><span data-stu-id="53bbd-193">The first XML index is primary; any additional indexes are secondary.</span></span>  
  
## <a name="saving-the-diagram"></a><span data-ttu-id="53bbd-194">Salvando o diagrama</span><span class="sxs-lookup"><span data-stu-id="53bbd-194">Saving the Diagram</span></span>  
 <span data-ttu-id="53bbd-195">Todas as alterações feitas em um diagrama não são postadas ao banco de dados até serem salvas.</span><span class="sxs-lookup"><span data-stu-id="53bbd-195">All of the changes you make to a diagram are not posted to the database until you save it.</span></span> <span data-ttu-id="53bbd-196">Se houver problemas ou conflitos, uma caixa de diálogo será exibida com mais informações.</span><span class="sxs-lookup"><span data-stu-id="53bbd-196">If there are problems or conflicts, a dialog box appears with more information.</span></span>  
  
#### <a name="to-save-a-database-diagram"></a><span data-ttu-id="53bbd-197">Para salvar um diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="53bbd-197">To save a database diagram</span></span>  
  
1.  <span data-ttu-id="53bbd-198">No menu **Arquivo** , selecione **Salvar Diagrama1**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-198">On the **File** menu, select **Save Diagram1**.</span></span>  
  
     <span data-ttu-id="53bbd-199">A caixa de diálogo **Salvar** é exibida.</span><span class="sxs-lookup"><span data-stu-id="53bbd-199">The **Save** dialog box appears.</span></span> <span data-ttu-id="53bbd-200">Se a opção **Avisar sobre Tabelas Afetadas** for selecionada, as informações sobre tabelas novas ou alteradas serão listadas.</span><span class="sxs-lookup"><span data-stu-id="53bbd-200">If **Warn about Tables Affected** is selected, information about new or changed tables is listed.</span></span>  
  
2.  <span data-ttu-id="53bbd-201">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="53bbd-201">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="53bbd-202">Na ocorrência de qualquer erro, a caixa de diálogo **Notificações Pós-salvamento** é exibida com os erros e respectivas causas.</span><span class="sxs-lookup"><span data-stu-id="53bbd-202">If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes.</span></span> <span data-ttu-id="53bbd-203">Corrija os erros e salve o diagrama novamente.</span><span class="sxs-lookup"><span data-stu-id="53bbd-203">Fix the errors and save the diagram again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="53bbd-204">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="53bbd-204">Next Steps</span></span>  
 <span data-ttu-id="53bbd-205">Esse é um diagrama básico somente com duas tabelas existentes e duas tabelas novas, mas ilustra o potencial de diagramação de um banco de dados existente ou de criação de um novo esquema visualmente.</span><span class="sxs-lookup"><span data-stu-id="53bbd-205">This is a basic diagram with just two existing and two new tables, but it illustrates the potential for diagramming an existing database or creating a new schema visually.</span></span> <span data-ttu-id="53bbd-206">Sugestões para exploração adicional incluem:</span><span class="sxs-lookup"><span data-stu-id="53bbd-206">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="53bbd-207">Criar novos diagramas contendo grupos de tabelas relacionadas</span><span class="sxs-lookup"><span data-stu-id="53bbd-207">Create new diagrams containing groups of related tables</span></span>  
  
-   <span data-ttu-id="53bbd-208">Personalizar a quantidade de informações mostrada para cada tabela</span><span class="sxs-lookup"><span data-stu-id="53bbd-208">Customize the amount of information shown for each table</span></span>  
  
-   <span data-ttu-id="53bbd-209">Alterar o layout e adicionar anotações</span><span class="sxs-lookup"><span data-stu-id="53bbd-209">Change the layout and add annotations</span></span>  
  
-   <span data-ttu-id="53bbd-210">Copiar o diagrama em um bitmap</span><span class="sxs-lookup"><span data-stu-id="53bbd-210">Copy the diagram to a bitmap</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53bbd-211">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="53bbd-211">See Also</span></span>  
 <span data-ttu-id="53bbd-212">[Personalize a quantidade de informações exibidas em diagramas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="53bbd-212">[Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="53bbd-213">[Configurar o designer de diagramas de banco de dados &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="53bbd-213">[Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span></span>  
 <span data-ttu-id="53bbd-214">[Adicionar tabelas a diagramas &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="53bbd-214">[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="53bbd-215">[Crie relações entre tabelas em um diagrama &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="53bbd-215">[Create Relationships Between Tables on a Diagram &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span></span>  
 <span data-ttu-id="53bbd-216">[Criar índices XML](../../relational-databases/xml/create-xml-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="53bbd-216">[Create XML Indexes](../../relational-databases/xml/create-xml-indexes.md) </span></span>  
 <span data-ttu-id="53bbd-217">[Copiar uma imagem de um diagrama de banco de dados para a área de transferência &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="53bbd-217">[Copy an Image of a Database Diagram to the Clipboard &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="53bbd-218">Trabalhar com layout de diagrama &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="53bbd-218">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  
