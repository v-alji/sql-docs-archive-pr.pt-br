---
title: Configurar operações de índice paralelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index parallel operations [SQL Server]
- processors [SQL Server], parallel index operations
- max degree of parallelism option
- MAXDOP index option, parallel index operations
- parallel index operations [SQL Server]
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8831aadae15af03a05f4ab03cfe514e54566df1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569443"
---
# <a name="configure-parallel-index-operations"></a><span data-ttu-id="5ae0f-102">Configurar operações de índice paralelo</span><span class="sxs-lookup"><span data-stu-id="5ae0f-102">Configure Parallel Index Operations</span></span>
  <span data-ttu-id="5ae0f-103">Este tópico define o grau máximo de paralelismo e explica como modificar essa configuração no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae0f-103">This topic defines max degree of parallelism and explains how to modify this setting in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5ae0f-104">Em computadores multiprocessadores em execução no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise ou superior, as instruções de índice podem usar vários processadores para executar operações de verificação, classificação e índice associadas à instrução de índice da mesma forma que outras consultas.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-104">On multiprocessor computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise or higher, index statements may use multiple processors to perform the scan, sort, and index operations associated with the index statement just like other queries do.</span></span> <span data-ttu-id="5ae0f-105">O número de processadores usados para executar uma única instrução de índice é determinado pela opção de configuração [Grau Máximo de Paralelismo](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) , pela carga de trabalho atual e pelas estatísticas de índice.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-105">The number of processors used to run a single index statement is determined by the [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) configuration option, the current workload, and the index statistics.</span></span> <span data-ttu-id="5ae0f-106">A opção grau máximo de paralelismo determina o número máximo de processadores a serem usados na execução no plano paralelo.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-106">The max degree of parallelism option determines the maximum number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="5ae0f-107">Se o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detectar que o sistema está ocupado, o grau de paralelismo da operação de índice será automaticamente reduzido antes do início da execução da instrução.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-107">If the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detects that the system is busy, the degree of parallelism of the index operation is automatically reduced before statement execution starts.</span></span> <span data-ttu-id="5ae0f-108">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] também poderá diminuir o grau de paralelismo se a coluna de chave à esquerda de um índice não particionado tiver um número limitado de valores distintos ou a frequência de cada valor distinto variar de forma significativa.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-108">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can also reduce the degree of parallelism if the leading key column of a non-partitioned index has a limited number of distinct values or the frequency of each distinct value varies significantly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ae0f-109">As operações de índice paralelas não estão disponíveis em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ae0f-109">Parallel index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="5ae0f-110">Para obter mais informações, consulte [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="5ae0f-110">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="5ae0f-111">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5ae0f-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5ae0f-112">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5ae0f-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5ae0f-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5ae0f-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5ae0f-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="5ae0f-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5ae0f-115">**Para definir a opção max degree of paralelismo, usando:**</span><span class="sxs-lookup"><span data-stu-id="5ae0f-115">**To set the max degree of parallelism, using:**</span></span>  
  
     [<span data-ttu-id="5ae0f-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ae0f-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5ae0f-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ae0f-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5ae0f-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5ae0f-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5ae0f-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5ae0f-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5ae0f-120">O número de processadores usados pelo otimizador de consulta normalmente fornece melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-120">The number of processors that are used by the query optimizer typically provides optimal performance.</span></span> <span data-ttu-id="5ae0f-121">Porém, operações como criar, recriar ou cancelar índices muito grandes são recursos intensivos e podem causar recursos insuficientes em outros aplicativos e operações de banco de dados durante a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-121">However, operations such as creating, rebuilding, or dropping very large indexes are resource intensive and can cause insufficient resources for other applications and database operations for the duration of the index operation.</span></span> <span data-ttu-id="5ae0f-122">Quando ocorrer esse problema, você poderá configurar manualmente o número máximo de processadores usados para executar a instrução de índice, limitando o número de processadores para a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-122">When this problem occurs, you can manually configure the maximum number of processors that are used to run the index statement by limiting the number of processors to use for the index operation.</span></span>  
  
-   <span data-ttu-id="5ae0f-123">A opção de índice MAXDOP substitui a opção de configuração max degree of parallelism apenas para consultas que especificam essa opção.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-123">The MAXDOP index option overrides the max degree of parallelism configuration option only for the query specifying this option.</span></span> <span data-ttu-id="5ae0f-124">A tabela a seguir lista os valores inteiros válidos que podem ser especificados com a opção de configuração grau máximo de paralelismo e a opção de índice MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-124">The following table lists the valid integer values that can be specified with the max degree of parallelism configuration option and the MAXDOP index option.</span></span>  
  
    |<span data-ttu-id="5ae0f-125">Valor</span><span class="sxs-lookup"><span data-stu-id="5ae0f-125">Value</span></span>|<span data-ttu-id="5ae0f-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ae0f-126">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="5ae0f-127">0</span><span class="sxs-lookup"><span data-stu-id="5ae0f-127">0</span></span>|<span data-ttu-id="5ae0f-128">Especifica que o servidor determina o número de CPUs que são usadas, dependendo da carga de trabalho do sistema atual.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-128">Specifies that the server determines the number of CPUs that are used, depending on the current system workload.</span></span> <span data-ttu-id="5ae0f-129">Esse é o valor padrão e a configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-129">This is the default value and recommended setting.</span></span>|  
    |<span data-ttu-id="5ae0f-130">1</span><span class="sxs-lookup"><span data-stu-id="5ae0f-130">1</span></span>|<span data-ttu-id="5ae0f-131">Suprime a geração de plano paralelo.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-131">Suppresses parallel plan generation.</span></span> <span data-ttu-id="5ae0f-132">A operação será executada em série.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-132">The operation will be executed serially.</span></span>|  
    |<span data-ttu-id="5ae0f-133">2-64</span><span class="sxs-lookup"><span data-stu-id="5ae0f-133">2-64</span></span>|<span data-ttu-id="5ae0f-134">Limita o número de processadores ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-134">Limits the number of processors to the specified value.</span></span> <span data-ttu-id="5ae0f-135">Menos processadores podem ser usados dependendo da carga de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-135">Fewer processors may be used depending on the current workload.</span></span> <span data-ttu-id="5ae0f-136">Se um valor maior que o número de CPUs disponíveis for especificado, o número atual de CPUs disponíveis será usado.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-136">If a value larger than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>|  
  
-   <span data-ttu-id="5ae0f-137">Execução de índice paralelo e a opção de índice MAXDOP se aplicam às seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5ae0f-137">Parallel index execution and the MAXDOP index option apply to the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    -   <span data-ttu-id="5ae0f-138">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="5ae0f-138">CREATE INDEX</span></span>  
  
    -   <span data-ttu-id="5ae0f-139">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="5ae0f-139">ALTER INDEX REBUILD</span></span>  
  
    -   <span data-ttu-id="5ae0f-140">DROP INDEX (Isso só se aplica aos índices cluster.)</span><span class="sxs-lookup"><span data-stu-id="5ae0f-140">DROP INDEX (This applies to clustered indexes only.)</span></span>  
  
    -   <span data-ttu-id="5ae0f-141">ALTER TABLE ADD (índice) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="5ae0f-141">ALTER TABLE ADD (index) CONSTRAINT</span></span>  
  
    -   <span data-ttu-id="5ae0f-142">ALTER TABLE DROP (índice cluster) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="5ae0f-142">ALTER TABLE DROP (clustered index) CONSTRAINT</span></span>  
  
-   <span data-ttu-id="5ae0f-143">A opção de índice MAXDOP não pode ser especificada na instrução ALTER INDEX REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-143">The MAXDOP index option cannot be specified in the ALTER INDEX REORGANIZE statement.</span></span>  
  
-   <span data-ttu-id="5ae0f-144">Requisitos de memória para operações de índice de partição que necessitam de classificação poderão ser maiores se o otimizador de consulta aplicar graus de paralelismo à operação de criação.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-144">Memory requirements for partitioned index operations that require sorting can be greater if the query optimizer applies degrees of parallelism to the build operation.</span></span> <span data-ttu-id="5ae0f-145">Quanto maior os graus de paralelismo, o maior será o requisito de memória.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-145">The higher the degrees of parallelism, the greater the memory requirement is.</span></span> <span data-ttu-id="5ae0f-146">Para saber mais, confira [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="5ae0f-146">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5ae0f-147">Segurança</span><span class="sxs-lookup"><span data-stu-id="5ae0f-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5ae0f-148">Permissões</span><span class="sxs-lookup"><span data-stu-id="5ae0f-148">Permissions</span></span>  
 <span data-ttu-id="5ae0f-149">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-149">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5ae0f-150">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ae0f-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-index"></a><span data-ttu-id="5ae0f-151">Para definir o grau máximo de paralelismo de um índice</span><span class="sxs-lookup"><span data-stu-id="5ae0f-151">To set max degree of parallelism on an index</span></span>  
  
1.  <span data-ttu-id="5ae0f-152">No Pesquisador de Objetos, clique no sinal de mais para expandir o banco de dados que contém a tabela na qual você deseja definir o grau máximo de paralelismo de um índice.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to set max degree of parallelism for an index.</span></span>  
  
2.  <span data-ttu-id="5ae0f-153">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="5ae0f-153">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5ae0f-154">Clique no sinal de mais para expandir a tabela na qual você deseja definir o grau máximo de paralelismo de um índice.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-154">Click the plus sign to expand the table on which you want to set max degree of parallelism for an index.</span></span>  
  
4.  <span data-ttu-id="5ae0f-155">Expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="5ae0f-155">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="5ae0f-156">Clique com o botão direito do mouse no índice do qual você deseja definir o grau máximo de paralelismo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-156">Right-click the index for which you want to set the max degree of parallelism and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="5ae0f-157">Em **Selecione uma página**, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="5ae0f-158">Selecione **Grau máximo de paralelismo**e insira um valor entre 1 e 64.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-158">Select **Maximum degree of parallelism**, and then enter some value between 1 and 64.</span></span>  
  
8.  <span data-ttu-id="5ae0f-159">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5ae0f-160">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ae0f-160">Using Transact-SQL</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-existing-index"></a><span data-ttu-id="5ae0f-161">Para definir o grau máximo de paralelismo de um índice existente</span><span class="sxs-lookup"><span data-stu-id="5ae0f-161">To set max degree of parallelism on an existing index</span></span>  
  
1.  <span data-ttu-id="5ae0f-162">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae0f-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5ae0f-163">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5ae0f-164">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-164">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 <span data-ttu-id="5ae0f-165">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ae0f-165">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
#### <a name="set-max-degree-of-parallelism-on-a-new-index"></a><span data-ttu-id="5ae0f-166">Defina o grau máximo de paralelismo de um novo índice</span><span class="sxs-lookup"><span data-stu-id="5ae0f-166">Set max degree of parallelism on a new index</span></span>  
  
1.  <span data-ttu-id="5ae0f-167">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae0f-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5ae0f-168">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5ae0f-169">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 <span data-ttu-id="5ae0f-170">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ae0f-170">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
