---
title: Modificar um esquema de partição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d57984228e23143d2061df6bf447f978f9bd3c46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575794"
---
# <a name="modify-a-partition-scheme"></a><span data-ttu-id="02b56-102">Modificar um esquema de partição</span><span class="sxs-lookup"><span data-stu-id="02b56-102">Modify a Partition Scheme</span></span>
  <span data-ttu-id="02b56-103">Você pode Modificar um esquema de partição no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ao designar um grupo de arquivos para manter a partição seguinte que será adicionada à tabela particionada usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02b56-103">You can modify a partition scheme in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by designating a filegroup to hold the next partition that is added to a partitioned table using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="02b56-104">Isso é feito ao atribuir a propriedade NEXT USED a um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="02b56-104">You do this by assigning the NEXT USED property to a filegroup.</span></span> <span data-ttu-id="02b56-105">Você pode atribuir a propriedade NEXT USED a um grupo de arquivos vazio ou para um que já mantenha uma partição.</span><span class="sxs-lookup"><span data-stu-id="02b56-105">You can assign the NEXT USED property to an empty filegroup or to one that already holds a partition.</span></span> <span data-ttu-id="02b56-106">Em outras palavras, um grupo de arquivos pode manter mais de uma partição.</span><span class="sxs-lookup"><span data-stu-id="02b56-106">In other words, a filegroup can hold more than one partition.</span></span>  
  
 <span data-ttu-id="02b56-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="02b56-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="02b56-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="02b56-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="02b56-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="02b56-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="02b56-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="02b56-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="02b56-111">**Para criar uma tabela ou um índice particionado usando:**</span><span class="sxs-lookup"><span data-stu-id="02b56-111">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="02b56-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02b56-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="02b56-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02b56-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02b56-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="02b56-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="02b56-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="02b56-115">Limitations and Restrictions</span></span>  
 <span data-ttu-id="02b56-116">Qualquer grupo de arquivos afetado por ALTER PARTITION SCHEME deve estar online.</span><span class="sxs-lookup"><span data-stu-id="02b56-116">Any filegroup affected by ALTER PARTITION SCHEME must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02b56-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="02b56-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02b56-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="02b56-118">Permissions</span></span>  
 <span data-ttu-id="02b56-119">As seguintes permissões podem ser usadas para executar ALTER PARTITION SCHEME:</span><span class="sxs-lookup"><span data-stu-id="02b56-119">The following permissions can be used to execute ALTER PARTITION SCHEME:</span></span>  
  
-   <span data-ttu-id="02b56-120">Permissão ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="02b56-120">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="02b56-121">Essa permissão tem como padrão os membros da função de servidor fixa **sysadmin** e das funções de banco de dados fixas **db_owner** e **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="02b56-121">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="02b56-122">Permissão CONTROL ou ALTER no banco de dados no qual o esquema de partição foi criado.</span><span class="sxs-lookup"><span data-stu-id="02b56-122">CONTROL or ALTER permission on the database in which the partition scheme was created.</span></span>  
  
-   <span data-ttu-id="02b56-123">Permissão CONTROL SERVER ou ALTER ANY DATABASE no servidor do banco de dados no qual o esquema de partição foi criado.</span><span class="sxs-lookup"><span data-stu-id="02b56-123">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition scheme was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="02b56-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02b56-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="02b56-125">**Para modificar um esquema de partição:**</span><span class="sxs-lookup"><span data-stu-id="02b56-125">**To modify a partition scheme:**</span></span>  
  
 <span data-ttu-id="02b56-126">Essa ação específica não pode ser executada com o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02b56-126">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="02b56-127">Para modificar um esquema de partição, primeiro você deve excluir o esquema e depois criar um novo com as propriedades desejadas usando o Assistente para Criar Partição.</span><span class="sxs-lookup"><span data-stu-id="02b56-127">In order to modify a partition scheme, you must first delete the scheme and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="02b56-128">Para obter mais informações, consulte [criar tabelas e índices particionados usando SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) em **criar tabelas e índices particionados**.</span><span class="sxs-lookup"><span data-stu-id="02b56-128">For more information, see [Create Partitioned Tables and Indexes Using SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) under **Create Partitioned Tables and Indexes**.</span></span>  
  
#### <a name="to-delete-a-partition-scheme"></a><span data-ttu-id="02b56-129">Para excluir um esquema de partição</span><span class="sxs-lookup"><span data-stu-id="02b56-129">To delete a partition scheme</span></span>  
  
1.  <span data-ttu-id="02b56-130">Clique no sinal de adição para expandir o banco de dados onde você quer excluir um esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="02b56-130">Click the plus sign to expand the database where you want to delete the partition scheme.</span></span>  
  
2.  <span data-ttu-id="02b56-131">Clique no sinal de adição para expandir a pasta **Armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="02b56-131">Click the plus sign to expand the **Storage** folder.</span></span>  
  
3.  <span data-ttu-id="02b56-132">Clique no sinal de adição para expandir a pasta **Esquemas de Partição** .</span><span class="sxs-lookup"><span data-stu-id="02b56-132">Click the plus sign to expand the **Partition Schemes** folder.</span></span>  
  
4.  <span data-ttu-id="02b56-133">Clique com o botão direito do mouse no esquema de partição a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="02b56-133">Right-click the partition scheme you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="02b56-134">Na caixa de diálogo **Excluir Objeto** , verifique se o esquema de partição correto está selecionado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b56-134">In the **Delete Object** dialog box, ensure that the correct partition scheme is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="02b56-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02b56-135">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-partition-scheme"></a><span data-ttu-id="02b56-136">Para modificar um esquema de partição</span><span class="sxs-lookup"><span data-stu-id="02b56-136">To modify a partition scheme</span></span>  
  
1.  <span data-ttu-id="02b56-137">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02b56-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="02b56-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="02b56-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="02b56-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="02b56-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
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
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 <span data-ttu-id="02b56-140">Para obter mais informações, veja [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02b56-140">For more information, see [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span></span>  
  
  
