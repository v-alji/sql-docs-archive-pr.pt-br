---
title: Mover um índice existente para outro grupo de arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- moving tables
- switching filegroups for index
- moving indexes
- indexes [SQL Server], moving
- filegroups [SQL Server], switching
ms.assetid: 167ebe77-487d-4ca8-9452-4b2c7d5cb96e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c99847dcb8d4d65272dd3660c7fd60d3efb8d951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583039"
---
# <a name="move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="8ebbc-102">Mover um índice existente para um grupo de arquivos diferente</span><span class="sxs-lookup"><span data-stu-id="8ebbc-102">Move an Existing Index to a Different Filegroup</span></span>
  <span data-ttu-id="8ebbc-103">Este tópico descreve como mover um índice existente do seu grupo de arquivos atual para um grupo de arquivos diferente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebbc-103">This topic describes how to move an existing index from its current filegroup to a different filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8ebbc-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8ebbc-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8ebbc-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8ebbc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8ebbc-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="8ebbc-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8ebbc-108">**Para mover um índice existente para um grupo de arquivos diferente, usando:**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-108">**To move an existing index to a different filegroup, using:**</span></span>  
  
     [<span data-ttu-id="8ebbc-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ebbc-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8ebbc-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ebbc-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8ebbc-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8ebbc-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8ebbc-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8ebbc-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8ebbc-113">Se uma tabela tiver um índice clusterizado, mover o índice clusterizado a um novo grupo de arquivos moverá a tabela àquele grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-113">If a table has a clustered index, moving the clustered index to a new filegroup moves the table to that filegroup.</span></span>  
  
-   <span data-ttu-id="8ebbc-114">Você não pode mover índices criados usando uma restrição UNIQUE ou PRIMARY KEY usando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebbc-114">You cannot move indexes created using a UNIQUE or PRIMARY KEY constraint using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="8ebbc-115">Para mover esses índices, use a instrução [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) com a opção (DROP_EXISTING=ON) no [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebbc-115">To move these indexes use the [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) statement with the (DROP_EXISTING=ON) option in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8ebbc-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="8ebbc-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ebbc-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="8ebbc-117">Permissions</span></span>  
 <span data-ttu-id="8ebbc-118">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-118">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="8ebbc-119">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="8ebbc-119">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8ebbc-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ebbc-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-using-table-designer"></a><span data-ttu-id="8ebbc-121">Para mover um índice existente para um grupo de arquivos diferente, usando o Designer de Tabelas</span><span class="sxs-lookup"><span data-stu-id="8ebbc-121">To move an existing index to a different filegroup using Table Designer</span></span>  
  
1.  <span data-ttu-id="8ebbc-122">No Pesquisador de Objetos, clique no sinal de adição para expandir a tabela que contém o índice que você quer mover.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-122">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="8ebbc-123">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="8ebbc-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8ebbc-124">Clique com o botão direito do mouse na tabela que contém o índice que você quer mover e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-124">Right-click the table containing the index that you want to move and select **Design**.</span></span>  
  
4.  <span data-ttu-id="8ebbc-125">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-125">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="8ebbc-126">Selecione o índice a ser movido.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-126">Select the index that you want to move.</span></span>  
  
6.  <span data-ttu-id="8ebbc-127">Na grade principal, expanda **Especificação de Espaço de Dados**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-127">In the main grid, expand **Data Space Specification**.</span></span>  
  
7.  <span data-ttu-id="8ebbc-128">Selecione **Nome do Esquema de Partição ou Grupo de Arquivos** e selecione da lista o grupo de arquivos ou esquema de partição para onde você deseja mover o índice.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-128">Select **Filegroup or Partition Scheme Name** and select from the list the filegroup or partition scheme to where you want to move the index.</span></span>  
  
8.  <span data-ttu-id="8ebbc-129">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-129">Click **Close**.</span></span>  
  
9. <span data-ttu-id="8ebbc-130">No menu **Arquivo** , selecione **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-130">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-in-object-explorer"></a><span data-ttu-id="8ebbc-131">Para mover um índice existente a um grupo de arquivos diferente no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="8ebbc-131">To move an existing index to a different filegroup in Object Explorer</span></span>  
  
1.  <span data-ttu-id="8ebbc-132">No Pesquisador de Objetos, clique no sinal de adição para expandir a tabela que contém o índice que você quer mover.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-132">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="8ebbc-133">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="8ebbc-133">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8ebbc-134">Clique no sinal de adição para expandir a tabela que contém o índice a ser movido.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-134">Click the plus sign to expand the table containing the index that you want to move.</span></span>  
  
4.  <span data-ttu-id="8ebbc-135">Clique no sinal de adição para expandir a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="8ebbc-135">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="8ebbc-136">Clique com o botão direito do mouse no índice a ser movido e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-136">Right-click the index that you want to move and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="8ebbc-137">Em **Selecione uma página**, selecione **Armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-137">Under **Select a page**, select **Storage**.</span></span>  
  
7.  <span data-ttu-id="8ebbc-138">Selecione o grupo de arquivos para onde mover o índice.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-138">Select the filegroup in which to move the index.</span></span>  
  
     <span data-ttu-id="8ebbc-139">Se a tabela ou o índice for particionado, selecione o esquema de partição no qual mover o índice.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-139">If the table or index is partitioned, select the partition scheme in which to move the index.</span></span> <span data-ttu-id="8ebbc-140">Para obter mais informações sobre índices particionados, consulte [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8ebbc-140">For more information about partitioned indexes, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
     <span data-ttu-id="8ebbc-141">Se você estiver movendo um índice clusterizado, poderá usar o processamento online.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-141">If you are moving a clustered index, you can use online processing.</span></span> <span data-ttu-id="8ebbc-142">O processamento online permite o acesso simultâneo de usuários aos dados subjacentes e a índices não clusterizados durante a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-142">Online processing allows concurrent user access to the underlying data and to nonclustered indexes during the index operation.</span></span> <span data-ttu-id="8ebbc-143">Para obter mais informações, consulte [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="8ebbc-143">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
     <span data-ttu-id="8ebbc-144">Em computadores multiprocessadores que usam o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], é possível configurar o número de processadores usados para executar a instrução de índice especificando um grau máximo de valor de paralelismo.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-144">On multiprocessor computers using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can configure the number of processors used to execute the index statement by specifying a maximum degree of parallelism value.</span></span> <span data-ttu-id="8ebbc-145">O recurso de operações de índice paralelas não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebbc-145">The Parallel indexed operations feature is not available in every edition of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8ebbc-146">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="8ebbc-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="8ebbc-147">Para obter mais informações sobre as operações indexadas paralelas, consulte [Configurar operações de índice paralelo](configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8ebbc-147">For more information about Parallel indexed operations, see [Configure Parallel Index Operations](configure-parallel-index-operations.md).</span></span>  
  
8.  <span data-ttu-id="8ebbc-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-148">Click **OK**.</span></span>  
  
 <span data-ttu-id="8ebbc-149">As seguintes informações estão disponíveis na página **Armazenamento** da caixa de diálogo **Propriedades do Índice –**  _index_name_:</span><span class="sxs-lookup"><span data-stu-id="8ebbc-149">The following information is available on the **Storage** page of the **Index Properties -** _index_name_ dialog box:</span></span>  
  
 <span data-ttu-id="8ebbc-150">**Grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-150">**Filegroup**</span></span>  
 <span data-ttu-id="8ebbc-151">Armazena o índice no grupo de arquivos especificado.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-151">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="8ebbc-152">A lista exibe apenas grupos de arquivos padrão (linha).</span><span class="sxs-lookup"><span data-stu-id="8ebbc-152">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="8ebbc-153">A seleção de lista padrão é o grupo de arquivos PRIMARY do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-153">The default list selection is the PRIMARY filegroup of the database.</span></span>  
  
 <span data-ttu-id="8ebbc-154">**Grupos de Arquivos do Fluxo de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-154">**Filestream filegroup**</span></span>  
 <span data-ttu-id="8ebbc-155">Especifica o grupo de arquivos para obter dados de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-155">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="8ebbc-156">Essa lista exibe apenas grupos de arquivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-156">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="8ebbc-157">A seleção de lista padrão é o grupo de arquivos PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-157">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span>  
  
 <span data-ttu-id="8ebbc-158">**Esquema de partição**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-158">**Partition scheme**</span></span>  
 <span data-ttu-id="8ebbc-159">Armazena o índice em um esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-159">Stores the index in a partition scheme.</span></span> <span data-ttu-id="8ebbc-160">Clicando em **Esquema de Partição** a grade abaixo é habilitada.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-160">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="8ebbc-161">A seleção de lista padrão é o esquema de partição usado para armazenar os dados de tabela.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-161">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="8ebbc-162">Ao selecionar um esquema de partição diferente na lista, a informações na grade é atualizada.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-162">When you select a different partition scheme in the list, the information in the grid is updated.</span></span>  
  
 <span data-ttu-id="8ebbc-163">A opção de esquema de partição fica indisponível se não houver nenhum esquema de partição no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-163">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="8ebbc-164">**Esquema de Partição do Fluxo de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-164">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="8ebbc-165">Especifica o esquema de partição para dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-165">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="8ebbc-166">O esquema de partição deve ser simétrico com o esquema especificado na opção **Esquema de partição** .</span><span class="sxs-lookup"><span data-stu-id="8ebbc-166">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="8ebbc-167">Se a tabela não for particionada, o campo fica em branco.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-167">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="8ebbc-168">**Parâmetro do Esquema de Partição**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-168">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="8ebbc-169">Exibe o nome da coluna que participa do esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-169">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="8ebbc-170">**Coluna de tabela**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-170">**Table Column**</span></span>  
 <span data-ttu-id="8ebbc-171">Selecione a tabela ou exiba para mapear para o esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-171">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="8ebbc-172">**Tipo de dados da coluna**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-172">**Column Data Type**</span></span>  
 <span data-ttu-id="8ebbc-173">Exibe informações de tipo de dados sobre a coluna.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-173">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ebbc-174">Se a coluna de tabela for uma coluna computada, **Tipo de Dados da Coluna** exibirá "coluna computada."</span><span class="sxs-lookup"><span data-stu-id="8ebbc-174">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="8ebbc-175">**Permitir o processamento online de instruções DML ao mover o índice**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-175">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="8ebbc-176">Permite aos usuários acessar a tabela subjacente ou dados de índice clusterizado associados a quaisquer índices não clusterizados durante a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-176">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ebbc-177">Esta opção não está disponível para índices XML ou se o índice for um índice clusterizadoF desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-177">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="8ebbc-178">**Definir grau máximo de paralelismo**</span><span class="sxs-lookup"><span data-stu-id="8ebbc-178">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="8ebbc-179">Limita o número de processadores a serem usados durante execução do plano paralelo.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-179">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="8ebbc-180">O valor padrão, 0, usa o número real de CPUs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-180">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="8ebbc-181">A definição do valor como 1 elimina a geração em plano paralelo; a definição do valor como um número maior que 1 restringe o número máximo de processadores usados por uma única execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-181">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="8ebbc-182">Esta opção ficará disponível apenas se a caixa de diálogo estiver no estado **Recriar** ou **Recriar** .</span><span class="sxs-lookup"><span data-stu-id="8ebbc-182">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ebbc-183">Se um valor maior que o número de CPUs disponíveis for especificado, será usado o número real de CPUs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-183">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8ebbc-184">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ebbc-184">Using Transact-SQL</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="8ebbc-185">Para mover um índice existente para um grupo de arquivos diferente</span><span class="sxs-lookup"><span data-stu-id="8ebbc-185">To move an existing index to a different filegroup</span></span>  
  
1.  <span data-ttu-id="8ebbc-186">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebbc-186">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ebbc-187">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-187">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ebbc-188">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8ebbc-188">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the TransactionsFG1 filegroup on the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP TransactionsFG1;  
    GO  
    /* Adds the TransactionsFG1dat3 file to the TransactionsFG1 filegroup. Please note that you will have to change the filename parameter in this statement to execute it without errors.  
    */  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = TransactionsFG1dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\TransactionsFG1dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP TransactionsFG1;  
    GO  
    /*Creates the IX_Employee_OrganizationLevel_OrganizationNode index  
      on the TransactionsPS1 filegroup and drops the original IX_Employee_OrganizationLevel_OrganizationNode index.  
    */  
    CREATE NONCLUSTERED INDEX IX_Employee_OrganizationLevel_OrganizationNode  
        ON HumanResources.Employee (OrganizationLevel, OrganizationNode)  
        WITH (DROP_EXISTING = ON)  
        ON TransactionsFG1;  
    GO  
    ```  
  
 <span data-ttu-id="8ebbc-189">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ebbc-189">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
