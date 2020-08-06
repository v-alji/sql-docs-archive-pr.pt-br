---
title: Modificar uma função de partição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae5bfc09-f27a-4ea9-9518-485278b11674
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bf14e633e62839b1abca7f38f833efab933c18f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679326"
---
# <a name="modify-a-partition-function"></a><span data-ttu-id="5f25d-102">Modificar uma função de partição</span><span class="sxs-lookup"><span data-stu-id="5f25d-102">Modify a Partition Function</span></span>
  <span data-ttu-id="5f25d-103">Você pode alterar o modo como uma tabela ou um índice é particionado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] adicionando ou subtraindo o número de partições especificadas, em incrementos de 1, na função de partição da tabela ou do índice particionado usando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f25d-103">You can change the way a table or index is partitioned in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by adding or subtracting the number of partitions specified, in increments of 1, in the partition function of the partitioned table or index by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5f25d-104">Ao adicionar uma partição, você “divide” em duas uma partição existente e redefine os limites das novas partições.</span><span class="sxs-lookup"><span data-stu-id="5f25d-104">When you add a partition, you do so by "splitting" an existing partition into two partitions and redefining the boundaries of the new partitions.</span></span> <span data-ttu-id="5f25d-105">Ao descartar uma partição, você "funde" os limites das duas partições criando uma só.</span><span class="sxs-lookup"><span data-stu-id="5f25d-105">When you drop a partition, you do so by "merging" the boundaries of two partitions into one.</span></span> <span data-ttu-id="5f25d-106">Esta última ação repopula uma partição e deixa a outra partição não atribuída.</span><span class="sxs-lookup"><span data-stu-id="5f25d-106">This last action repopulates one partition and leaves the other partition unassigned.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="5f25d-107">Mais de uma tabela ou índice podem usar a mesma função de partição.</span><span class="sxs-lookup"><span data-stu-id="5f25d-107">More than one table or index can use the same partition function.</span></span> <span data-ttu-id="5f25d-108">Quando modifica uma função de partição, você afeta todas elas em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="5f25d-108">When you modify a partition function, you affect all of them in a single transaction.</span></span> <span data-ttu-id="5f25d-109">Verifique as dependências da função de partição antes de modificá-la.</span><span class="sxs-lookup"><span data-stu-id="5f25d-109">Check the partition function's dependencies before modifying it.</span></span>  
  
 <span data-ttu-id="5f25d-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5f25d-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5f25d-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5f25d-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5f25d-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5f25d-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5f25d-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="5f25d-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5f25d-114">**Para modificar uma função de partição usando:**</span><span class="sxs-lookup"><span data-stu-id="5f25d-114">**To modify a partition function, using:**</span></span>  
  
     [<span data-ttu-id="5f25d-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f25d-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5f25d-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f25d-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5f25d-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5f25d-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5f25d-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5f25d-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5f25d-119">ALTER PARTITION FUNCTION só pode ser usada para dividir uma partição em duas ou para mesclar duas partições em uma.</span><span class="sxs-lookup"><span data-stu-id="5f25d-119">ALTER PARTITION FUNCTION can only be used for splitting one partition into two, or for merging two partitions into one.</span></span> <span data-ttu-id="5f25d-120">Para alterar a forma como uma tabela ou índice é particionado (por exemplo, de 10 partições em 5), você pode usar qualquer uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f25d-120">To change the way a table or index is partitioned (from 10 partitions to 5, for example), you can use any one of the following options:</span></span>  
  
    -   <span data-ttu-id="5f25d-121">Crie uma nova tabela particionada com a função de partição desejada e insira os dados da tabela antiga na nova tabela, usando uma instrução INSERT INTO... A instrução SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] ou o **Assistente para Gerenciar Partição** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f25d-121">Create a new partitioned table with the desired partition function, and then insert the data from the old table into the new table by using either an INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or the **Manage Partition Wizard** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="5f25d-122">Crie um índice clusterizado particionado em um heap.</span><span class="sxs-lookup"><span data-stu-id="5f25d-122">Create a partitioned clustered index on a heap.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5f25d-123">Descartando resultados de um índice clusterizado particionado em um heap particionado.</span><span class="sxs-lookup"><span data-stu-id="5f25d-123">Dropping a partitioned clustered index results in a partitioned heap.</span></span>  
  
    -   <span data-ttu-id="5f25d-124">Descarte e recrie um índice particionado existente usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX com a cláusula DROP EXISTING = ON.</span><span class="sxs-lookup"><span data-stu-id="5f25d-124">Drop and rebuild an existing partitioned index by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX statement with the DROP EXISTING = ON clause.</span></span>  
  
    -   <span data-ttu-id="5f25d-125">Execute uma sequência de instruções ALTER PARTITION FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="5f25d-125">Perform a sequence of ALTER PARTITION FUNCTION statements.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5f25d-126">não fornece suporte de replicação para modificar uma função de partição.</span><span class="sxs-lookup"><span data-stu-id="5f25d-126">does not provide replication support for modifying a partition function.</span></span> <span data-ttu-id="5f25d-127">Se você quiser fazer alterações em uma função de partição no banco de dados de publicação, será preciso fazê-las manualmente no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="5f25d-127">If you want to make changes to a partition function in the publication database, you must do this manually in the subscription database.</span></span>  
  
-   <span data-ttu-id="5f25d-128">Todos os grupos de arquivos afetados por ALTER PARTITION FUNCTION devem estar online.</span><span class="sxs-lookup"><span data-stu-id="5f25d-128">All filegroups that are affected by ALTER PARTITION FUNCTION must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5f25d-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="5f25d-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5f25d-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="5f25d-130">Permissions</span></span>  
 <span data-ttu-id="5f25d-131">Qualquer uma das permissões a seguir pode ser usada para executar ALTER PARTITION FUNCTION:</span><span class="sxs-lookup"><span data-stu-id="5f25d-131">Any one of the following permissions can be used to execute ALTER PARTITION FUNCTION:</span></span>  
  
-   <span data-ttu-id="5f25d-132">Permissão ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="5f25d-132">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="5f25d-133">Essa permissão tem como padrão os membros da função de servidor fixa **sysadmin** e das funções de banco de dados fixas **db_owner** e **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="5f25d-133">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="5f25d-134">A permissão CONTROL ou ALTER no banco de dados no qual a função de partição foi criada.</span><span class="sxs-lookup"><span data-stu-id="5f25d-134">CONTROL or ALTER permission on the database in which the partition function was created.</span></span>  
  
-   <span data-ttu-id="5f25d-135">A permissão CONTROL SERVER ou ALTER ANY DATABASE no servidor do banco de dados no qual a função de partição foi criada.</span><span class="sxs-lookup"><span data-stu-id="5f25d-135">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5f25d-136">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f25d-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5f25d-137">**Para modificar uma função de partição:**</span><span class="sxs-lookup"><span data-stu-id="5f25d-137">**To modify a partition function:**</span></span>  
  
 <span data-ttu-id="5f25d-138">Essa ação específica não pode ser executada com o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f25d-138">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5f25d-139">Para modificar uma função de partição, primeiro você deve excluir a função e depois criar uma nova função com as propriedades desejadas usando o Assistente para Criar Partição.</span><span class="sxs-lookup"><span data-stu-id="5f25d-139">In order to modify a partition function, you must first delete the function and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="5f25d-140">Para obter mais informações, consulte</span><span class="sxs-lookup"><span data-stu-id="5f25d-140">For more information, see</span></span>  
  
#### <a name="to-delete-a-partition-function"></a><span data-ttu-id="5f25d-141">Para excluir uma função de partição</span><span class="sxs-lookup"><span data-stu-id="5f25d-141">To delete a partition function</span></span>  
  
1.  <span data-ttu-id="5f25d-142">Expanda o banco de dados no qual você deseja excluir a função de partição e expanda a pasta **Repositório** .</span><span class="sxs-lookup"><span data-stu-id="5f25d-142">Expand the database where you want to delete the partition function and then expand the **Storage** folder.</span></span>  
  
2.  <span data-ttu-id="5f25d-143">Expanda a pasta **Funções de partição** .</span><span class="sxs-lookup"><span data-stu-id="5f25d-143">Expand the **Partition Functions** folder.</span></span>  
  
3.  <span data-ttu-id="5f25d-144">Clique com o botão direito do mouse na função de partição a ser excluída e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5f25d-144">Right-click the partition function you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="5f25d-145">Na caixa de diálogo **Excluir Objeto** , verifique se a função de partição correta está selecionada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f25d-145">In the **Delete Object** dialog box, ensure that the correct partition function is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5f25d-146">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f25d-146">Using Transact-SQL</span></span>  
  
#### <a name="to-split-a-single-partition-into-two-partitions"></a><span data-ttu-id="5f25d-147">Para dividir uma única partição em duas partições</span><span class="sxs-lookup"><span data-stu-id="5f25d-147">To split a single partition into two partitions</span></span>  
  
1.  <span data-ttu-id="5f25d-148">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f25d-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f25d-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5f25d-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5f25d-150">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5f25d-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Split the partition between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    ```  
  
#### <a name="to-merge-two-partitions-into-one-partition"></a><span data-ttu-id="5f25d-151">Para mesclar duas partições em uma partição</span><span class="sxs-lookup"><span data-stu-id="5f25d-151">To merge two partitions into one partition</span></span>  
  
1.  <span data-ttu-id="5f25d-152">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f25d-152">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f25d-153">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5f25d-153">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5f25d-154">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5f25d-154">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Merge the partitions between boundary_values 1 and 100  
    --and between boundary_values 100 and 1000 to create one partition  
    --between boundary_values 1 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    MERGE RANGE (100);  
    ```  
  
 <span data-ttu-id="5f25d-155">Para obter mais informações, veja [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f25d-155">For more information, see [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span></span>  
  
  
