---
title: Criar tabelas e índices particionados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.createpartition.partitionscheme.f1
- sql12.swb.createpartition.selectoutput.f1
- sql12.swb.createpartition.finish.f1
- sql12.swb.createpartition.summary.f1
- sql12.swb.createpartition.mappartition.f1
- sql12.swb.createpartition.partitioncolumn.f1
- sql12.swb.createpartition.progress.f1
- sql12.swb.createpartition.createjob.f1
- sql12.swb.createpartition.getstart.f1
- sql12.swb.createpartition.partitionfunction.f1
helpviewer_keywords:
- partitioned indexes [SQL Server], creating
- partition schemes [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], creating
- partition functions [SQL Server]
- partition schemes [SQL Server]
ms.assetid: 7641df10-1921-42a7-ba6e-4cb03b3ba9c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 76ccd8b784902f8542f06f3823e5f8dcb78e9201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572511"
---
# <a name="create-partitioned-tables-and-indexes"></a><span data-ttu-id="de81f-102">Criar tabelas e índices particionados</span><span class="sxs-lookup"><span data-stu-id="de81f-102">Create Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="de81f-103">Você pode criar uma tabela ou um índice particionado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de81f-103">You can create a partitioned table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="de81f-104">Os dados das tabelas e dos índices particionados são divididos horizontalmente em unidades que podem ser disseminadas por mais de um grupo de arquivos em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de81f-104">The data in partitioned tables and indexes is horizontally divided into units that can be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="de81f-105">O particionamento pode tornar as tabelas e os índices grandes mais gerenciáveis e escalonáveis.</span><span class="sxs-lookup"><span data-stu-id="de81f-105">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
 <span data-ttu-id="de81f-106">A criação de uma tabela ou um índice particionado ocorre normalmente em quatro partes:</span><span class="sxs-lookup"><span data-stu-id="de81f-106">Creating a partitioned table or index typically happens in four parts:</span></span>  
  
1.  <span data-ttu-id="de81f-107">Crie um grupo ou grupos de arquivos e os arquivos correspondentes que terão as partições especificadas pelo esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-107">Create a filegroup or filegroups and corresponding files that will hold the partitions specified by the partition scheme.</span></span>  
  
2.  <span data-ttu-id="de81f-108">Cria uma função de partição que mapeia as linhas de uma tabela ou de um índice em partições com base nos valores de uma coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="de81f-108">Create a partition function that maps the rows of a table or index into partitions based on the values of a specified column.</span></span>  
  
3.  <span data-ttu-id="de81f-109">Cria um esquema de partição que mapeia as partições de uma tabela particionada ou índice para os novos grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="de81f-109">Create a partition scheme that maps the partitions of a partitioned table or index to the new filegroups.</span></span>  
  
4.  <span data-ttu-id="de81f-110">Crie ou modifique uma tabela ou um índice e especifique o esquema de partição como local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="de81f-110">Create or modify a table or index and specify the partition scheme as the storage location.</span></span>  
  
 <span data-ttu-id="de81f-111">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="de81f-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="de81f-112">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="de81f-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="de81f-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="de81f-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="de81f-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="de81f-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="de81f-115">**Para criar uma tabela ou um índice particionado usando:**</span><span class="sxs-lookup"><span data-stu-id="de81f-115">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="de81f-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de81f-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="de81f-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de81f-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="de81f-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="de81f-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="de81f-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="de81f-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="de81f-120">O escopo de uma função e de um esquema de partição é limitado ao banco de dados em que foram criados.</span><span class="sxs-lookup"><span data-stu-id="de81f-120">The scope of a partition function and scheme is limited to the database in which they have been created.</span></span> <span data-ttu-id="de81f-121">No banco de dados, as funções de partição residem em um namespace separado das outras funções.</span><span class="sxs-lookup"><span data-stu-id="de81f-121">Within the database, partition functions reside in a separate namespace from other functions.</span></span>  
  
-   <span data-ttu-id="de81f-122">Se alguma linha dentro de uma função de partição tiver colunas de particionamento com valores nulos, essas linhas serão alocadas para a partição à extrema esquerda.</span><span class="sxs-lookup"><span data-stu-id="de81f-122">If any rows within a partition function have partitioning columns with null values, these rows are allocated to the left-most partition.</span></span> <span data-ttu-id="de81f-123">No entanto, se NULL for especificado como valor de limite e RIGHT for indicado, a partição extrema esquerda permanecerá vazia e os valores NULL serão colocados na segunda partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-123">However, if NULL is specified as a boundary value and RIGHT is indicated, the left-most partition remains empty and NULL values are placed in the second partition.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="de81f-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="de81f-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="de81f-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="de81f-125">Permissions</span></span>  
 <span data-ttu-id="de81f-126">A criação de uma tabela particionada requer a permissão CREATE TABLE no banco de dados e a permissão ALTER no esquema no qual a tabela está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="de81f-126">Creating a partitioned table requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span> <span data-ttu-id="de81f-127">A criação de um índice particionado requer a permissão ALTER na tabela ou exibição onde o índice está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="de81f-127">Creating a partitioned index requires ALTER permission on the table or view where the index is being created.</span></span> <span data-ttu-id="de81f-128">A criação de uma tabela ou um índice particionado requer uma das permissões adicionais a seguir:</span><span class="sxs-lookup"><span data-stu-id="de81f-128">Creating either a partitioned table or index requires any one of the following additional permissions:</span></span>  
  
-   <span data-ttu-id="de81f-129">Permissão ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="de81f-129">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="de81f-130">Essa permissão tem como padrão os membros da função de servidor fixa **sysadmin** e das funções de banco de dados fixas **db_owner** e **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="de81f-130">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="de81f-131">Permissão CONTROL ou ALTER no banco de dados no qual a função e o esquema de partição estão sendo criados.</span><span class="sxs-lookup"><span data-stu-id="de81f-131">CONTROL or ALTER permission on the database in which the partition function and partition scheme are being created.</span></span>  
  
-   <span data-ttu-id="de81f-132">Permissão CONTROL SERVER ou ALTER ANY DATABASE no servidor do banco de dados no qual a função e o esquema de partição estão sendo criados.</span><span class="sxs-lookup"><span data-stu-id="de81f-132">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function and partition scheme are being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="de81f-133">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de81f-133">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="de81f-134">Siga as etapas deste procedimento para criar um ou mais grupos de arquivos, arquivos correspondentes e uma tabela.</span><span class="sxs-lookup"><span data-stu-id="de81f-134">Follow the steps in this procedure to create one or more filegroups, corresponding files, and a table.</span></span> <span data-ttu-id="de81f-135">Você fará referência a esses objetos no próximo procedimento quando criar a tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="de81f-135">You will reference these objects in the next procedure when you create the partitioned table.</span></span>  
  
#### <a name="to-create-new-filegroups-for-a-partitioned-table"></a><span data-ttu-id="de81f-136">Para criar novos grupos de arquivos para uma tabela particionada</span><span class="sxs-lookup"><span data-stu-id="de81f-136">To create new filegroups for a partitioned table</span></span>  
  
1.  <span data-ttu-id="de81f-137">No Pesquisador de Objetos, clique com o botão direito do mouse no banco de dados no qual você deseja criar uma tabela particionada e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="de81f-137">In Object Explorer, right-click the database in which you want to create a partitioned table and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="de81f-138">Na caixa de diálogo **Propriedades do Banco de Dados –** *nome_do_banco_de_dados*, em **Selecionar uma página**, selecione **Grupos de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="de81f-138">In the **Database Properties -** *database_name* dialog box, under **Select a page**, select **Filegroups**.</span></span>  
  
3.  <span data-ttu-id="de81f-139">Em **Linhas**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-139">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="de81f-140">Na nova linha, digite o nome do grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="de81f-140">In the new row, enter the filegroup name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="de81f-141">Você deve sempre ter um grupo de arquivos extra, além do número de grupos de arquivos especificado para os valores de limite durante a criação de partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-141">You must always have one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
4.  <span data-ttu-id="de81f-142">Continue adicionando linhas até que você tenha criado todos os grupos de arquivos para a tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="de81f-142">Continue adding rows until you have created all of the filegroups for the partitioned table.</span></span>  
  
5.  <span data-ttu-id="de81f-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="de81f-143">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="de81f-144">Em **Selecione uma página**, selecione **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="de81f-144">Under **Select a page**, select **Files**.</span></span>  
  
7.  <span data-ttu-id="de81f-145">Em **Linhas**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-145">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="de81f-146">Na nova linha, digite um nome de arquivo e selecione um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="de81f-146">In the new row, enter a filename and select a filegroup.</span></span>  
  
8.  <span data-ttu-id="de81f-147">Continue adicionando linhas até que tenha criado ao menos um arquivo para cada grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="de81f-147">Continue adding rows until you have created at least one file for each filegroup.</span></span>  
  
9. <span data-ttu-id="de81f-148">Expanda a pasta **Tabelas** e crie uma tabela como você faz normalmente.</span><span class="sxs-lookup"><span data-stu-id="de81f-148">Expand the **Tables** folder and create a table as you normally would.</span></span> <span data-ttu-id="de81f-149">Para obter mais informações, veja [Criar tabelas &#40;Mecanismo de Banco de Dados&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="de81f-149">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span> <span data-ttu-id="de81f-150">Opcionalmente, você pode especificar uma tabela existente no próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="de81f-150">Alternatively, you can specify an existing table in the next procedure.</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="de81f-151">Para criar uma tabela particionada</span><span class="sxs-lookup"><span data-stu-id="de81f-151">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="de81f-152">Clique com o botão direito do mouse na tabela que você deseja particionar, aponte para **Armazenamento**e clique em **Criar Partição...** .</span><span class="sxs-lookup"><span data-stu-id="de81f-152">Right-click the table that you wish to partition, point to **Storage**, and then click **Create Partition...**.</span></span>  
  
2.  <span data-ttu-id="de81f-153">No **Assistente para Criar Partição**, na página **Bem-vindo ao Assistente para Criar Partição** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-153">In the **Create Partition Wizard**, on the **Welcome to the Create Partition Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="de81f-154">Na página **Selecione uma Coluna de Particionamento** , na grade **Colunas de particionamento disponíveis** , selecione a coluna em que deseja particionar sua tabela.</span><span class="sxs-lookup"><span data-stu-id="de81f-154">On the **Select a Partitioning Column** page, in the **Available partitioning columns** grid, select the column on which you want to partition your table.</span></span> <span data-ttu-id="de81f-155">Somente colunas com tipos de dados que possam ser usados para particionar dados serão exibidas na grade **Colunas de particionamento disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="de81f-155">Only columns with data types that can be used to partition data will be displayed in the **Available partitioning columns** grid.</span></span> <span data-ttu-id="de81f-156">Se você selecionar uma coluna computada como a coluna de particionamento, a coluna deverá ser designada como persistente.</span><span class="sxs-lookup"><span data-stu-id="de81f-156">If you select a computed column as the partitioning column, the column must be designated as a persisted column.</span></span>  
  
     <span data-ttu-id="de81f-157">As opções que você tem para as colunas de particionamento e o intervalo de valores são determinadas, basicamente, pela extensão na qual seus dados podem ser agrupados de forma lógica.</span><span class="sxs-lookup"><span data-stu-id="de81f-157">The choices you have for the partitioning column and the values range are determined primarily by the extent to which your data can be grouped in a logical way.</span></span> <span data-ttu-id="de81f-158">Por exemplo, você pode optar por dividir seus dados em agrupamentos lógicos por meses ou trimestres de um ano.</span><span class="sxs-lookup"><span data-stu-id="de81f-158">For example, you may choose to divide your data into logical groupings by months or quarters of a year.</span></span> <span data-ttu-id="de81f-159">As consultas que você planejar fazer nos seus dados determinarão se o agrupamento lógico é adequado para o gerenciamento de suas partições de tabela.</span><span class="sxs-lookup"><span data-stu-id="de81f-159">The queries you plan to make against your data will determine whether this logical grouping is adequate for managing your table partitions.</span></span> <span data-ttu-id="de81f-160">Todos os tipos de dados são válidos para uso como colunas de particionamento, com exceção de `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, tipos de dados de alias ou tipos de dados CLR definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="de81f-160">All data types are valid for use as partitioning columns, except `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, alias data types, or CLR user-defined data types.</span></span>  
  
     <span data-ttu-id="de81f-161">As opções adicionais a seguir estão disponíveis nessa página:</span><span class="sxs-lookup"><span data-stu-id="de81f-161">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="de81f-162">**Colocar essa tabela na tabela particionada selecionada**</span><span class="sxs-lookup"><span data-stu-id="de81f-162">**Collocate this table to the selected partitioned table**</span></span>  
     <span data-ttu-id="de81f-163">Permite selecionar uma tabela particionada que contenha dados relacionados para unir a essa tabela na coluna de particionamento.</span><span class="sxs-lookup"><span data-stu-id="de81f-163">Allows you to select a partitioned table that contains related data to join with this table on the partitioning column.</span></span> <span data-ttu-id="de81f-164">Tabelas com partições unidas nas colunas de particionamento costumam ser consultadas de forma mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="de81f-164">Tables with partitions joined on the partitioning columns are typically queried more efficiently.</span></span>  
  
     <span data-ttu-id="de81f-165">**Alinhamento de armazenamento de índices não exclusivos e índices exclusivos com uma coluna de partição indexada**</span><span class="sxs-lookup"><span data-stu-id="de81f-165">**Storage-align non-unique indexes and unique indexes with an indexed partition column**</span></span>  
     <span data-ttu-id="de81f-166">Alinha todos os índices da tabela que são particionados com o mesmo esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-166">Aligns all indexes of the table that are partitioned with the same partition scheme.</span></span> <span data-ttu-id="de81f-167">Quando uma tabela e seus índices são alinhados, você pode mover partições para dentro e fora de tabelas particionadas com mais eficiência, pois seus dados são particionados com o mesmo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="de81f-167">When a table and its indexes are aligned, you can move partitions in and out of partitioned tables more effectively, because your data is partitioned with the same algorithm.</span></span>  
  
     <span data-ttu-id="de81f-168">Depois de selecionar a coluna de particionamento e as outras opções, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-168">After selecting the partitioning column and any other options, click **Next**.</span></span>  
  
4.  <span data-ttu-id="de81f-169">Na página **Selecione uma Função de Partição** , em **Selecione uma função de partição**, clique em **Nova função de partição** ou em **Função de partição existente**.</span><span class="sxs-lookup"><span data-stu-id="de81f-169">On the **Select a Partition Function** page, under **Select partition function**, click either **New partition function** or **Existing partition function**.</span></span> <span data-ttu-id="de81f-170">Se você escolher **Nova função de partição**, digite o nome da função.</span><span class="sxs-lookup"><span data-stu-id="de81f-170">If you choose **New partition function**, enter the name of the function.</span></span> <span data-ttu-id="de81f-171">Se você escolher **Função de partição existente**, selecione o nome da função que você gostaria de usar na lista.</span><span class="sxs-lookup"><span data-stu-id="de81f-171">If you choose **Existing partition function**, select the name of the function you'd like to use from the list.</span></span> <span data-ttu-id="de81f-172">A opção **Função de partição existente** não estará disponível se não houver outra função de partição no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de81f-172">The **Existing partition function** option will not be available if there are no other partition functions on the database.</span></span>  
  
     <span data-ttu-id="de81f-173">Depois de concluir essa página, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-173">After completing this page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="de81f-174">Na página **Selecione um Esquema de Partição** , em **Selecione um esquema de partição**, clique em **Novo esquema de partição** ou em **Esquema de partição existente**.</span><span class="sxs-lookup"><span data-stu-id="de81f-174">On the **Select a Partition Scheme** page, under **Select partition scheme**, click either **New partition scheme** or **Existing partition scheme**.</span></span> <span data-ttu-id="de81f-175">Se você escolher **Novo esquema de partição**, digite o nome do esquema.</span><span class="sxs-lookup"><span data-stu-id="de81f-175">If you choose **New partition scheme**, enter the name of the scheme.</span></span> <span data-ttu-id="de81f-176">Se você escolher **Esquema de partição existente**, selecione o nome do esquema que você gostaria de usar na lista.</span><span class="sxs-lookup"><span data-stu-id="de81f-176">If you choose **Existing partition scheme**, select the name of the scheme you'd like to use from the list.</span></span> <span data-ttu-id="de81f-177">A opção **Esquema de partição existente** não estará disponível se não houver outro esquema de partição no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de81f-177">The **Existing partition scheme** option will not be available if there are no other partition schemes on the database.</span></span>  
  
     <span data-ttu-id="de81f-178">Depois de concluir essa página, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-178">After completing this page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="de81f-179">Na página **Mapear Partições** , em **Intervalo**, selecione **Limite esquerdo** ou **Limite direito** para especificar se é para incluir o maior ou o menor valor de limite dentro de cada grupo de arquivos criado.</span><span class="sxs-lookup"><span data-stu-id="de81f-179">On the **Map Partitions** page, under **Range**, select either **Left boundary** or **Right boundary** to specify whether to include the highest or lowest bounding value within each filegroup you create.</span></span> <span data-ttu-id="de81f-180">Você deve sempre inserir um grupo de arquivos extra, além do número de grupos de arquivos especificado para os valores de limite durante a criação de partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-180">You must always enter one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
     <span data-ttu-id="de81f-181">Na grade **Selecione os grupos de arquivos e especifique os valores de limite** , em **Grupo de arquivos**, selecione um grupo de arquivos no qual deseja particionar seus dados.</span><span class="sxs-lookup"><span data-stu-id="de81f-181">In the **Select filegroups and specify boundary values** grid, under **Filegroup**, select the filegroup into which you want to partition your data.</span></span> <span data-ttu-id="de81f-182">Em **Limite**, digite o valor de limite para cada grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="de81f-182">Under **Boundary**, enter the boundary value for each filegroup.</span></span> <span data-ttu-id="de81f-183">Se o valor de limite ficar em branco, a função de partição mapeará a tabela inteira ou o índice em uma única partição usando o nome da função de partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-183">If boundary value is left empty, the partition function maps the whole table or index into a single partition using the partition function name.</span></span>  
  
     <span data-ttu-id="de81f-184">As opções adicionais a seguir estão disponíveis nessa página:</span><span class="sxs-lookup"><span data-stu-id="de81f-184">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="de81f-185">**Definir Limites...**</span><span class="sxs-lookup"><span data-stu-id="de81f-185">**Set Boundaries...**</span></span>  
     <span data-ttu-id="de81f-186">Abre a caixa de diálogo **Definir Valores de Limite** para selecionar os valores de limite e os intervalos de datas que deseja para suas partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-186">Opens the **Set Boundary Values** dialog box to select the boundary values and date ranges you want for your partitions.</span></span> <span data-ttu-id="de81f-187">Essa opção estará disponível somente quando você tiver selecionado uma coluna de particionamento que contenha um dos seguintes tipos de dados: `date`, `datetime`, `smalldatetime`, `datetime2` ou `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="de81f-187">This option is only available when you have selected a partitioning column that contains one of the following data types: `date`, `datetime`, `smalldatetime`, `datetime2`, or `datetimeoffset`.</span></span>  
  
     <span data-ttu-id="de81f-188">**Estimar armazenamento**</span><span class="sxs-lookup"><span data-stu-id="de81f-188">**Estimate storage**</span></span>  
     <span data-ttu-id="de81f-189">Calcula o número de linhas, o espaço necessário e o espaço disponível para armazenamento para cada grupo de arquivos especificado para as partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-189">Estimates rowcount, required space, and available space for storage for each filegroup specified for the partitions.</span></span> <span data-ttu-id="de81f-190">Esses valores são exibidos na grade como valores somente leitura.</span><span class="sxs-lookup"><span data-stu-id="de81f-190">These values are displayed in the grid as read-only values.</span></span>  
  
     <span data-ttu-id="de81f-191">A caixa de diálogo **Definir Valores de Limite** permite as opções adicionais a seguir:</span><span class="sxs-lookup"><span data-stu-id="de81f-191">The **Set Boundary Values** dialog box allows for the following additional options:</span></span>  
  
     <span data-ttu-id="de81f-192">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="de81f-192">**Start date**</span></span>  
     <span data-ttu-id="de81f-193">Seleciona a data inicial para obter os valores de intervalo de suas partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-193">Selects the starting date for the range values of your partitions.</span></span>  
  
     <span data-ttu-id="de81f-194">**Data de término**</span><span class="sxs-lookup"><span data-stu-id="de81f-194">**End date**</span></span>  
     <span data-ttu-id="de81f-195">Seleciona a data de término para obter os valores de intervalo de suas partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-195">Selects the ending date for the range values of your partitions.</span></span> <span data-ttu-id="de81f-196">Se você selecionar **Limite esquerdo** na página **Mapear Partições** , essa data será o último valor de cada grupo de arquivos/partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-196">If you selected **Left boundary** on the **Map Partitions** page, this date will be the last value for each filegroup/partition.</span></span> <span data-ttu-id="de81f-197">Se você selecionar **Limite direito** na página **Mapear Partições** , essa data será o primeiro valor do próximo ao último grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="de81f-197">If you selected **Right boundary** on the **Map Partitions** page, this date will be the first value in the next-to-last filegroup.</span></span>  
  
     <span data-ttu-id="de81f-198">**Intervalo de datas**</span><span class="sxs-lookup"><span data-stu-id="de81f-198">**Date range**</span></span>  
     <span data-ttu-id="de81f-199">Seleciona a granularidade de data ou incremento de valor de intervalo desejado para cada partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-199">Selects the date granularity or range value increment you want for each partition.</span></span>  
  
     <span data-ttu-id="de81f-200">Depois de concluir essa página, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-200">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="de81f-201">Na página **Selecione uma Opção de Saída** , especifique como você deseja preencher sua tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="de81f-201">In the **Select an Output Option** page, specify how you want to complete your partitioned table.</span></span> <span data-ttu-id="de81f-202">Selecione **Criar Script** para criar um script SQL baseado nas páginas anteriores no assistente.</span><span class="sxs-lookup"><span data-stu-id="de81f-202">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="de81f-203">Selecione **Executar imediatamente** para criar a nova tabela particionada depois de concluir todas as páginas restantes no assistente.</span><span class="sxs-lookup"><span data-stu-id="de81f-203">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="de81f-204">Selecione **Agenda** para criar uma nova tabela particionada em um momento predeterminado no futuro.</span><span class="sxs-lookup"><span data-stu-id="de81f-204">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="de81f-205">Se você selecionar **Criar script**, as opções a seguir estarão disponíveis em **Opções de script**:</span><span class="sxs-lookup"><span data-stu-id="de81f-205">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="de81f-206">**Script para arquivo**</span><span class="sxs-lookup"><span data-stu-id="de81f-206">**Script to file**</span></span>  
     <span data-ttu-id="de81f-207">Gera o script como um arquivo .sql.</span><span class="sxs-lookup"><span data-stu-id="de81f-207">Generates the script as a .sql file.</span></span> <span data-ttu-id="de81f-208">Digite um nome de arquivo e o local na caixa **Nome do arquivo** ou clique em **Procurar** para abrir a caixa de diálogo **Local do Arquivo de Script** .</span><span class="sxs-lookup"><span data-stu-id="de81f-208">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="de81f-209">Em **Salvar Como**, selecione **Texto Unicode** ou **Texto ANSI**.</span><span class="sxs-lookup"><span data-stu-id="de81f-209">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="de81f-210">**Script para Área de Transferência**</span><span class="sxs-lookup"><span data-stu-id="de81f-210">**Script to Clipboard**</span></span>  
     <span data-ttu-id="de81f-211">Salva o script na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="de81f-211">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="de81f-212">**Script para Nova Janela de Consulta**</span><span class="sxs-lookup"><span data-stu-id="de81f-212">**Script to New Query Window**</span></span>  
     <span data-ttu-id="de81f-213">Gera o script para uma nova janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="de81f-213">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="de81f-214">Essa é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="de81f-214">This is the default selection.</span></span>  
  
     <span data-ttu-id="de81f-215">Se você selecionar **Agenda**, clique em **Alterar agenda**.</span><span class="sxs-lookup"><span data-stu-id="de81f-215">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="de81f-216">Na caixa de diálogo **Nova Agenda de Trabalho**, na caixa **Nome**, digite o nome da agenda de trabalho.</span><span class="sxs-lookup"><span data-stu-id="de81f-216">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="de81f-217">Na lista **Tipo de Agenda** , selecione o tipo de agenda:</span><span class="sxs-lookup"><span data-stu-id="de81f-217">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="de81f-218">**Iniciar automaticamente quando o SQL Server Agent for iniciado**</span><span class="sxs-lookup"><span data-stu-id="de81f-218">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="de81f-219">**Iniciar sempre que as CPUs estiverem ociosas**</span><span class="sxs-lookup"><span data-stu-id="de81f-219">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="de81f-220">**Recorrente**.</span><span class="sxs-lookup"><span data-stu-id="de81f-220">**Recurring**.</span></span> <span data-ttu-id="de81f-221">Selecione essa opção se sua nova tabela particionada for atualizada com novas informações regularmente.</span><span class="sxs-lookup"><span data-stu-id="de81f-221">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="de81f-222">**Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="de81f-222">**One time**.</span></span> <span data-ttu-id="de81f-223">Essa é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="de81f-223">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="de81f-224">Marque ou desmarque a caixa de seleção **Habilitado** para habilitar ou desabilitar a agenda.</span><span class="sxs-lookup"><span data-stu-id="de81f-224">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="de81f-225">Se você selecionar **Recorrente**:</span><span class="sxs-lookup"><span data-stu-id="de81f-225">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="de81f-226">Em **Frequência**, na lista **Ocorre** , especifique a frequência de ocorrência:</span><span class="sxs-lookup"><span data-stu-id="de81f-226">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="de81f-227">Se você selecionar **Diário**, na caixa **Ocorre periodicamente a cada** , digite a frequência com que a agenda de trabalho se repete em dias.</span><span class="sxs-lookup"><span data-stu-id="de81f-227">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="de81f-228">Se você selecionar **Semanal**, na caixa **Ocorre periodicamente a cada** , digite a frequência com que a agenda de trabalho se repete em semanas.</span><span class="sxs-lookup"><span data-stu-id="de81f-228">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="de81f-229">Selecione o dia ou os dias da semana em que a agenda de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="de81f-229">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="de81f-230">Se você selecionar **Mensalmente**, selecione **Dia** ou **O**.</span><span class="sxs-lookup"><span data-stu-id="de81f-230">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="de81f-231">Se você selecionar **Dia**, digite o dia do mês que você deseja que a agenda de trabalho seja executada e a frequência com que a agenda de trabalho se repete em meses.</span><span class="sxs-lookup"><span data-stu-id="de81f-231">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="de81f-232">Por exemplo, se desejar que a agenda de trabalho seja executada no 15º dia do mês a cada dois meses, selecione **Dia** e digite "15" na primeira caixa e "2" na segunda caixa.</span><span class="sxs-lookup"><span data-stu-id="de81f-232">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="de81f-233">Observe que o maior número permitido na segunda caixa é "99".</span><span class="sxs-lookup"><span data-stu-id="de81f-233">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="de81f-234">Se você selecionar **O**, selecione o dia específico da semana no mês que você deseja que a agenda de trabalho seja executada e a frequência com que a agenda de trabalho se repete em meses.</span><span class="sxs-lookup"><span data-stu-id="de81f-234">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="de81f-235">Por exemplo, se você desejar que a agenda de trabalho seja executada no último dia da semana do mês a cada dois meses, selecione **Dia**, selecione **último** na primeira lista e **dia da semana** na segunda lista e depois digite “2” na última caixa.</span><span class="sxs-lookup"><span data-stu-id="de81f-235">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="de81f-236">Você também pode selecionar **primeiro**, **segundo**, **terceiro**ou **quarto**, bem como dias específicos da semana (por exemplo: domingo ou quarta-feira) nas primeiras duas listas.</span><span class="sxs-lookup"><span data-stu-id="de81f-236">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="de81f-237">Observe que o maior número permitido na última caixa é "99".</span><span class="sxs-lookup"><span data-stu-id="de81f-237">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="de81f-238">Em **Frequência diária**, especifique a frequência com que a agenda de trabalho se repete no dia da execução da agenda de trabalho:</span><span class="sxs-lookup"><span data-stu-id="de81f-238">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="de81f-239">Se você selecionar **Ocorre uma vez às**, digite a hora específica do dia em que a agenda de trabalho deve ser executada na caixa **Ocorre uma vez às** .</span><span class="sxs-lookup"><span data-stu-id="de81f-239">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="de81f-240">Digite a hora, os minutos e os segundos do dia, bem como AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="de81f-240">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="de81f-241">Se você selecionar **Ocorre a cada**, especifique a frequência com que a agenda de trabalho é executada durante o dia escolhido em **Frequência**.</span><span class="sxs-lookup"><span data-stu-id="de81f-241">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="de81f-242">Por exemplo, se você desejar que o agendamento de trabalho se repita a cada 2 horas durante o dia em que é executado, selecione **Ocorre a cada**, digite "2" na primeira caixa e selecione **hora(s)** na lista.</span><span class="sxs-lookup"><span data-stu-id="de81f-242">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="de81f-243">Nessa lista, você pode selecionar também **minuto(s)** e **segundo(s)** .</span><span class="sxs-lookup"><span data-stu-id="de81f-243">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="de81f-244">Observe que o maior número permitido na primeira caixa é "100".</span><span class="sxs-lookup"><span data-stu-id="de81f-244">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="de81f-245">Na caixa **Iniciando às** , digite a hora em que a agenda de trabalho deve começar a ser executada.</span><span class="sxs-lookup"><span data-stu-id="de81f-245">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="de81f-246">Na caixa **Terminando às** , digite a hora em que a agenda de trabalho deve parar de se repetir.</span><span class="sxs-lookup"><span data-stu-id="de81f-246">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="de81f-247">Digite a hora, os minutos e os segundos do dia, bem como AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="de81f-247">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="de81f-248">Em **Duração**, em **Data de início**, digite a data que você deseja que a agenda de trabalho inicie a execução.</span><span class="sxs-lookup"><span data-stu-id="de81f-248">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="de81f-249">Selecione **Data de término** ou **Nenhuma data de término** para indicar quando a execução da agenda de trabalho deve parar.</span><span class="sxs-lookup"><span data-stu-id="de81f-249">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="de81f-250">Se você selecionar **Data de término**, digite a data em que você deseja que a execução da agenda de trabalho pare.</span><span class="sxs-lookup"><span data-stu-id="de81f-250">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="de81f-251">Se você selecionar **Uma Vez**, em **Ocorrência única**, na caixa **Data** , insira a data em que o agendamento de trabalho será executado.</span><span class="sxs-lookup"><span data-stu-id="de81f-251">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="de81f-252">Na caixa **Hora** , digite a hora em que a agenda de trabalho será executada.</span><span class="sxs-lookup"><span data-stu-id="de81f-252">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="de81f-253">Digite a hora, os minutos e os segundos do dia, bem como AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="de81f-253">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="de81f-254">Em **Resumo**, em **Descrição**, verifique se todas as configurações da agenda de trabalho estão corretas.</span><span class="sxs-lookup"><span data-stu-id="de81f-254">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="de81f-255">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="de81f-255">Click **OK**.</span></span>  
  
     <span data-ttu-id="de81f-256">Depois de concluir essa página, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-256">After completing this page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="de81f-257">Na página **Resumo da Revisão** , em **Examinar as seleções**, expanda todas as opções disponíveis para verificar se todas as configurações de partição estão corretas.</span><span class="sxs-lookup"><span data-stu-id="de81f-257">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all partition settings are correct.</span></span> <span data-ttu-id="de81f-258">Se tudo estiver como esperado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="de81f-258">If everything is as expected, click **Finish**.</span></span>  
  
9. <span data-ttu-id="de81f-259">Na página **Progresso do Assistente para Criar Partição** , monitore as informações de status das ações do Assistente para Criar Partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-259">On the **Create Partition Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="de81f-260">Dependendo das opções selecionadas no assistente, a página de progresso pode conter uma ou várias ações.</span><span class="sxs-lookup"><span data-stu-id="de81f-260">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="de81f-261">A caixa superior exibe o status geral do assistente e o número de mensagens de status, erro e aviso que ele recebeu.</span><span class="sxs-lookup"><span data-stu-id="de81f-261">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="de81f-262">As opções a seguir estão disponíveis na página **Progresso do Assistente para Criar Partição** :</span><span class="sxs-lookup"><span data-stu-id="de81f-262">The following options are available on the **Create Partition Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="de81f-263">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="de81f-263">**Details**</span></span>  
     <span data-ttu-id="de81f-264">Fornece a ação, status e qualquer mensagem retornada pela ação executada pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="de81f-264">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="de81f-265">**Ação**</span><span class="sxs-lookup"><span data-stu-id="de81f-265">**Action**</span></span>  
     <span data-ttu-id="de81f-266">Especifica o tipo e o nome de cada ação.</span><span class="sxs-lookup"><span data-stu-id="de81f-266">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="de81f-267">**Status**</span><span class="sxs-lookup"><span data-stu-id="de81f-267">**Status**</span></span>  
     <span data-ttu-id="de81f-268">Indica se a ação do assistente retornou como um todo o valor de **Êxito** ou de **Falha**.</span><span class="sxs-lookup"><span data-stu-id="de81f-268">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="de81f-269">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="de81f-269">**Message**</span></span>  
     <span data-ttu-id="de81f-270">Fornece qualquer mensagem de aviso ou erro retornada pelo processo.</span><span class="sxs-lookup"><span data-stu-id="de81f-270">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="de81f-271">**Report**</span><span class="sxs-lookup"><span data-stu-id="de81f-271">**Report**</span></span>  
     <span data-ttu-id="de81f-272">Cria um relatório contendo os resultados do Assistente para Criar Partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-272">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="de81f-273">As opções são **Exibir Relatório**, **Salvar Relatório no Arquivo**, **Copiar Relatório na Área de Transferência**e **Enviar Relatório como Email**.</span><span class="sxs-lookup"><span data-stu-id="de81f-273">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="de81f-274">**Exibir Relatório**</span><span class="sxs-lookup"><span data-stu-id="de81f-274">**View Report**</span></span>  
     <span data-ttu-id="de81f-275">Abre a caixa de diálogo **Exibir Relatório** , que contém um relatório de texto do progresso do Assistente para Criar Partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-275">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="de81f-276">**Salvar Relatório no Arquivo**</span><span class="sxs-lookup"><span data-stu-id="de81f-276">**Save Report to File**</span></span>  
     <span data-ttu-id="de81f-277">Abre a caixa de diálogo **Salvar Relatório Como** .</span><span class="sxs-lookup"><span data-stu-id="de81f-277">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="de81f-278">**Copiar Relatório na Área de Transferência**</span><span class="sxs-lookup"><span data-stu-id="de81f-278">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="de81f-279">Copia os resultados do relatório de progresso do assistente na Área de transferência.</span><span class="sxs-lookup"><span data-stu-id="de81f-279">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="de81f-280">**Enviar Relatório como Email**</span><span class="sxs-lookup"><span data-stu-id="de81f-280">**Send Report as Email**</span></span>  
     <span data-ttu-id="de81f-281">Copia os resultados do relatório de progresso do assistente para uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="de81f-281">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="de81f-282">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-282">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="de81f-283">O Assistente para Criar Partição cria a função e o esquema de partição e aplica o particionamento à tabela especificada.</span><span class="sxs-lookup"><span data-stu-id="de81f-283">The Create Partition Wizard creates the partition function and scheme and then applies the partitioning to the specified table.</span></span> <span data-ttu-id="de81f-284">Para verificar o particionamento da tabela, no Pesquisador de Objetos, clique com o botão direito do mouse na tabela e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="de81f-284">To verify the table partitioning, in Object Explorer, right-click the table and select **Properties**.</span></span> <span data-ttu-id="de81f-285">Clique na página **Armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="de81f-285">Click the **Storage** page.</span></span> <span data-ttu-id="de81f-286">A página exibe informações como o nome da função e do esquema de partição e o número de partições.</span><span class="sxs-lookup"><span data-stu-id="de81f-286">The page displays information such as the name of the partition function and scheme and the number of partitions.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="de81f-287">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de81f-287">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="de81f-288">Para criar uma tabela particionada</span><span class="sxs-lookup"><span data-stu-id="de81f-288">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="de81f-289">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de81f-289">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="de81f-290">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="de81f-290">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="de81f-291">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="de81f-291">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="de81f-292">O exemplo cria novos grupos de arquivos, uma função e um esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="de81f-292">The example creates new filegroups, a partition function, and a partition scheme.</span></span> <span data-ttu-id="de81f-293">Uma nova tabela é criada com o esquema de partição especificado no local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="de81f-293">A new table is created with the partition scheme specified as the storage location.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Adds four new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;   
  
    -- Adds one file for each filegroup.  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test1dat1,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t1dat1.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test1fg;  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test2dat2,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t2dat2.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test3dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t3dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test4dat4,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t4dat4.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test4fg;  
    GO  
    -- Creates a partition function called myRangePF1 that will partition a table into four partitions  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
        AS RANGE LEFT FOR VALUES (1, 100, 1000) ;  
    GO  
    -- Creates a partition scheme called myRangePS1 that applies myRangePF1 to the four filegroups created above  
    CREATE PARTITION SCHEME myRangePS1  
        AS PARTITION myRangePF1  
        TO (test1fg, test2fg, test3fg, test4fg) ;  
    GO  
    -- Creates a partitioned table called PartitionTable that uses myRangePS1 to partition col1  
    CREATE TABLE PartitionTable (col1 int PRIMARY KEY, col2 char(10))  
        ON myRangePS1 (col1) ;  
    GO  
    ```  
  
#### <a name="to-determine-if-a-table-is-partitioned"></a><span data-ttu-id="de81f-294">Para determinar se uma tabela é particionada</span><span class="sxs-lookup"><span data-stu-id="de81f-294">To determine if a table is partitioned</span></span>  
  
1.  <span data-ttu-id="de81f-295">A consulta a seguir retornará uma ou mais linhas se a tabela `PartitionTable` for particionada.</span><span class="sxs-lookup"><span data-stu-id="de81f-295">The following query returns one or more rows if the table `PartitionTable` is partitioned.</span></span> <span data-ttu-id="de81f-296">Se a tabela não for particionada, nenhuma linha será retornada.</span><span class="sxs-lookup"><span data-stu-id="de81f-296">If the table is not partitioned, no rows are returned.</span></span>  
  
    ```  
    SELECT *   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] IN (0,1)   
    JOIN sys.partition_schemes ps   
        ON i.data_space_id = ps.data_space_id   
    WHERE t.name = 'PartitionTable';   
    GO  
    ```  
  
#### <a name="to-determine-the-boundary-values-for-a-partitioned-table"></a><span data-ttu-id="de81f-297">Para determinar os valores de limite para uma tabela particionada</span><span class="sxs-lookup"><span data-stu-id="de81f-297">To determine the boundary values for a partitioned table</span></span>  
  
1.  <span data-ttu-id="de81f-298">A consulta a seguir retorna os valores de limite para cada partição na tabela `PartitionTable` .</span><span class="sxs-lookup"><span data-stu-id="de81f-298">The following query returns the boundary values for each partition in the `PartitionTable` table.</span></span>  
  
    ```  
    SELECT t.name AS TableName, i.name AS IndexName, p.partition_number, p.partition_id, i.data_space_id, f.function_id, f.type_desc, r.boundary_id, r.value AS BoundaryValue   
    FROM sys.tables AS t  
    JOIN sys.indexes AS i  
        ON t.object_id = i.object_id  
    JOIN sys.partitions AS p  
        ON i.object_id = p.object_id AND i.index_id = p.index_id   
    JOIN  sys.partition_schemes AS s   
        ON i.data_space_id = s.data_space_id  
    JOIN sys.partition_functions AS f   
        ON s.function_id = f.function_id  
    LEFT JOIN sys.partition_range_values AS r   
        ON f.function_id = r.function_id and r.boundary_id = p.partition_number  
    WHERE t.name = 'PartitionTable' AND i.type <= 1  
    ORDER BY p.partition_number;  
    ```  
  
#### <a name="to-determine-the-partition-column-for-a-partitioned-table"></a><span data-ttu-id="de81f-299">Para determinar a coluna de partição para uma tabela particionada</span><span class="sxs-lookup"><span data-stu-id="de81f-299">To determine the partition column for a partitioned table</span></span>  
  
1.  <span data-ttu-id="de81f-300">A consulta a seguir retorna o nome da coluna de particionamento para a tabela.</span><span class="sxs-lookup"><span data-stu-id="de81f-300">The following query returns the name of the partitioning column for table.</span></span> <span data-ttu-id="de81f-301">`PartitionTable`.</span><span class="sxs-lookup"><span data-stu-id="de81f-301">`PartitionTable`.</span></span>  
  
    ```  
    SELECT   
        t.[object_id] AS ObjectID   
        , t.name AS TableName   
        , ic.column_id AS PartitioningColumnID   
        , c.name AS PartitioningColumnName   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] <= 1 -- clustered index or a heap   
    JOIN sys.partition_schemes AS ps   
        ON ps.data_space_id = i.data_space_id   
    JOIN sys.index_columns AS ic   
        ON ic.[object_id] = i.[object_id]   
        AND ic.index_id = i.index_id   
        AND ic.partition_ordinal >= 1 -- because 0 = non-partitioning column   
    JOIN sys.columns AS c   
        ON t.[object_id] = c.[object_id]   
        AND ic.column_id = c.column_id   
    WHERE t.name = 'PartitionTable' ;   
    GO  
    ```  
  
 <span data-ttu-id="de81f-302">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="de81f-302">For more information, see:</span></span>  
  
-   [<span data-ttu-id="de81f-303">Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="de81f-303">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
-   [<span data-ttu-id="de81f-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="de81f-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-function-transact-sql)  
  
-   [<span data-ttu-id="de81f-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="de81f-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-scheme-transact-sql)  
  
-   [<span data-ttu-id="de81f-306">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="de81f-306">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
