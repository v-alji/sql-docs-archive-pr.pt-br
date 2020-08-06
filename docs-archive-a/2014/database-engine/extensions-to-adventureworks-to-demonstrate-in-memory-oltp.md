---
title: Extensões para o AdventureWorks para demonstrar o OLTP na memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0186b7f2-cead-4203-8360-b6890f37cde8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73a87751aa6cd4734f81b60cdd87a62939ba4ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684859"
---
# <a name="extensions-to-adventureworks-to-demonstrate-in-memory-oltp"></a><span data-ttu-id="f594c-102">Extensões do AdventureWorks para demonstrar OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="f594c-102">Extensions to AdventureWorks to Demonstrate In-Memory OLTP</span></span>
    
## <a name="overview"></a><span data-ttu-id="f594c-103">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f594c-103">Overview</span></span>  
 <span data-ttu-id="f594c-104">Este exemplo apresenta o novo recurso [!INCLUDE[hek_2](../includes/hek-2-md.md)] , que faz parte do [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-104">This sample showcases the new [!INCLUDE[hek_2](../includes/hek-2-md.md)] feature, which is part of [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="f594c-105">Ele mostra as novas tabelas com otimização de memória e os procedimentos armazenados compilados nativamente, e pode ser usado para demonstrar os benefícios de desempenho do [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-105">It shows the new memory-optimized tables and natively-compiled stored procedures, and can be used to demonstrate performance benefits of [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f594c-106">Para exibir esse tópico para o SQL Server 2016, consulte [Extensões do AdventureWorks para demonstrar OLTP na memória](https://msdn.microsoft.com/library/mt465764.aspx)</span><span class="sxs-lookup"><span data-stu-id="f594c-106">To view this topic for SQL Server 2016, see [Extensions to AdventureWorks to Demonstrate In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span></span>  
  
 <span data-ttu-id="f594c-107">O exemplo a seguir migra 5 tabelas do banco de dados do AdventureWorks para a otimização de memória, e inclui uma carga de trabalho de demonstração para o processamento de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-107">The sample migrates 5 tables in the AdventureWorks database to memory-optimized, and it includes a demo workload for sales order processing.</span></span> <span data-ttu-id="f594c-108">Você pode usar essa carga de trabalho de demonstração para consultar o benefício de desempenho em usar [!INCLUDE[hek_2](../includes/hek-2-md.md)] no servidor.</span><span class="sxs-lookup"><span data-stu-id="f594c-108">You can use this demo workload to see the performance benefit of using [!INCLUDE[hek_2](../includes/hek-2-md.md)] on your server.</span></span>  
  
 <span data-ttu-id="f594c-109">Na descrição do exemplo, abordamos as compensações que foram feitas na migração das tabelas para o [!INCLUDE[hek_2](../includes/hek-2-md.md)] , para levar em consideração os recursos que (ainda) não têm suporte para tabelas com otimização de memória no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-109">In the description of the sample we discuss the tradeoffs that were made in migrating the tables to [!INCLUDE[hek_2](../includes/hek-2-md.md)] to account for the features that are not (yet) supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="f594c-110">A documentação do exemplo foi estruturada como segue:</span><span class="sxs-lookup"><span data-stu-id="f594c-110">The documentation of this sample is structured as follows:</span></span>  
  
-   <span data-ttu-id="f594c-111">[Pré-requisitos](#Prerequisites) para instalar o exemplo e executar a carga de trabalho de demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-111">[Prerequisites](#Prerequisites) for installing the sample and running the demo workload</span></span>  
  
-   <span data-ttu-id="f594c-112">Instruções para [Instalando a amostra do Na Memória OLTP baseada no AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span><span class="sxs-lookup"><span data-stu-id="f594c-112">Instructions for [Installing the In-Memory OLTP sample based on AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span></span>  
  
-   <span data-ttu-id="f594c-113">[Descrição das tabelas e procedimentos de exemplo](#Descriptionofthesampletablesandprocedures) – isso inclui descrições das tabelas e dos procedimentos adicionados ao AdventureWorks pelo [!INCLUDE[hek_2](../includes/hek-2-md.md)] exemplo, bem como considerações para migrar algumas das tabelas AdventureWorks originais para otimização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-113">[Description of the sample tables and procedures](#Descriptionofthesampletablesandprocedures) - this includes descriptions of the tables and procedures added to AdventureWorks by the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample, as well as considerations for migrating some of the original AdventureWorks tables to memory-optimized</span></span>  
  
-   <span data-ttu-id="f594c-114">Instruções para executar [Medidas de desempenho usando a carga de trabalho de demonstração](#PerformanceMeasurementsusingtheDemoWorkload) – inclui instruções para instalar e executar ostress, uma ferramenta usada para direcionar a carga de trabalho, bem como executar a própria carga de trabalho de demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-114">Instructions for performing [Performance Measurements using the Demo Workload](#PerformanceMeasurementsusingtheDemoWorkload) - this includes instructions for installing and running ostress, a tool using for driving the workload, as well as running the demo workload itself</span></span>  
  
-   [<span data-ttu-id="f594c-115">Utilização de memória e espaço em disco na amostra</span><span class="sxs-lookup"><span data-stu-id="f594c-115">Memory and Disk Space Utilization in the Sample</span></span>](#MemoryandDiskSpaceUtilizationintheSample)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f594c-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f594c-116">Prerequisites</span></span>  
  
-   [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]<span data-ttu-id="f594c-117">RTM-avaliação, Developer ou Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f594c-117">RTM - Evaluation, Developer, or Enterprise edition</span></span>  
  
-   <span data-ttu-id="f594c-118">Para testes de desempenho, um servidor com as especificações semelhantes ao ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="f594c-118">For performance testing, a server with specifications similar to your production environment.</span></span> <span data-ttu-id="f594c-119">Para este exemplo específico, você deve ter pelo menos 16 GB de memória disponível para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-119">For this particular sample you should have at least 16GB of memory available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f594c-120">Para obter diretrizes gerais sobre hardware para [!INCLUDE[hek_2](../includes/hek-2-md.md)] o, consulte a seguinte postagem no blog:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span><span class="sxs-lookup"><span data-stu-id="f594c-120">For general guidelines on hardware for [!INCLUDE[hek_2](../includes/hek-2-md.md)], see the following blog post:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span></span>  
  
##  <a name="installing-the-hek_2-sample-based-on-adventureworks"></a><a name="InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks"></a><span data-ttu-id="f594c-121">Instalando o [!INCLUDE[hek_2](../includes/hek-2-md.md)] exemplo com base no AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="f594c-121">Installing the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample based on AdventureWorks</span></span>  
 <span data-ttu-id="f594c-122">Siga estas etapas para instalar o exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-122">Follow these steps to install the sample:</span></span>  
  
1.  <span data-ttu-id="f594c-123">Baixe o arquivo morto do backup completo do banco de dados AdventureWorks2014:</span><span class="sxs-lookup"><span data-stu-id="f594c-123">Download the archive for the full backup of the AdventureWorks2014 database:</span></span>  
  
    1.  <span data-ttu-id="f594c-124">Abra o seguinte: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661) .</span><span class="sxs-lookup"><span data-stu-id="f594c-124">Open the following: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661).</span></span>  
  
    2.  <span data-ttu-id="f594c-125">Quando for solicitado salvar o arquivo em uma pasta local.</span><span class="sxs-lookup"><span data-stu-id="f594c-125">When prompted to save the file to a local folder.</span></span>  
  
2.  <span data-ttu-id="f594c-126">Extraia o arquivo **AdventureWorks2014.bak** para uma pasta local, por exemplo "c:\temp".</span><span class="sxs-lookup"><span data-stu-id="f594c-126">Extract the **AdventureWorks2014.bak** file to a local folder, for example 'c:\temp'.</span></span>  
  
3.  <span data-ttu-id="f594c-127">Restaure o backup de banco de dados usando o [!INCLUDE[tsql](../includes/tsql-md.md)] ou o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f594c-127">Restore the database backup using [!INCLUDE[tsql](../includes/tsql-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="f594c-128">Identifique a pasta de destino e o nome de arquivo para o arquivo de dados, por exemplo,</span><span class="sxs-lookup"><span data-stu-id="f594c-128">Identify the target folder and filename for the data file, for example</span></span>  
  
         <span data-ttu-id="f594c-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span><span class="sxs-lookup"><span data-stu-id="f594c-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span></span>  
  
    2.  <span data-ttu-id="f594c-130">Identifique a pasta de destino e o nome de arquivo para o arquivo de log, por exemplo,</span><span class="sxs-lookup"><span data-stu-id="f594c-130">Identify the target folder and filename for the log file, for example</span></span>  
  
         <span data-ttu-id="f594c-131">'i:\DATA\AdventureWorks2014_log.ldf'</span><span class="sxs-lookup"><span data-stu-id="f594c-131">'i:\DATA\AdventureWorks2014_log.ldf'</span></span>  
  
        1.  <span data-ttu-id="f594c-132">O arquivo de log deve ser colocado em uma unidade que não seja a do arquivo de dados, preferencialmente uma unidade de baixa latência como um armazenamento de SSD ou de PCIe, para obter o desempenho máximo.</span><span class="sxs-lookup"><span data-stu-id="f594c-132">The log file should be placed on a different drive than the data file, ideally a low latency drive such as an SSD or PCIe storage, for maximum performance.</span></span>  
  
     <span data-ttu-id="f594c-133">Exemplo de script T-SQL:</span><span class="sxs-lookup"><span data-stu-id="f594c-133">Example T-SQL script:</span></span>  
  
    ```  
    RESTORE DATABASE [AdventureWorks2014]   
      FROM DISK = N'C:\temp\AdventureWorks2014.bak'   
        WITH FILE = 1,    
      MOVE N'AdventureWorks2014_Data' TO N'h:\DATA\AdventureWorks2014_Data.mdf',    
      MOVE N'AdventureWorks2014_Log' TO N'i:\DATA\AdventureWorks2014_log.ldf'  
     GO  
    ```  
  
4.  <span data-ttu-id="f594c-134">Altere o proprietário do banco de dados para um logon no servidor, executando o seguinte comando na janela de consulta do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f594c-134">Change the database owner to a login on your server, by running the following command in the query window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    ```  
    ALTER AUTHORIZATION ON DATABASE::AdventureWorks2014 TO [<NewLogin>]  
    ```  
  
5.  <span data-ttu-id="f594c-135">Baixe o script de exemplo ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL ' de [SQL Server 2014 RTM de exemplo de OLTP na memória](https://go.microsoft.com/fwlink/?LinkID=396372) para uma pasta local.</span><span class="sxs-lookup"><span data-stu-id="f594c-135">Download the sample script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' from [SQL Server 2014 RTM In-Memory OLTP Sample](https://go.microsoft.com/fwlink/?LinkID=396372) to a local folder.</span></span>  
  
6.  <span data-ttu-id="f594c-136">Atualize o valor da variável ' checkpoint_files_location ' no script ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL ' para apontar para o local de destino dos [!INCLUDE[hek_2](../includes/hek-2-md.md)] arquivos de ponto de verificação.</span><span class="sxs-lookup"><span data-stu-id="f594c-136">Update the value for the variable 'checkpoint_files_location' in the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql', to point to the target location for the [!INCLUDE[hek_2](../includes/hek-2-md.md)] checkpoint files.</span></span> <span data-ttu-id="f594c-137">Os arquivos de ponto de verificação devem ser colocados em uma unidade com bom desempenho sequencial de E/S.</span><span class="sxs-lookup"><span data-stu-id="f594c-137">The checkpoint files should be placed on a drive with good sequential IO performance.</span></span>  
  
     <span data-ttu-id="f594c-138">Atualize o nome da variável 'database_name' para apontar para o banco de dados do AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="f594c-138">Update the value for the variable 'database_name' to point to the AdventureWorks2014 database.</span></span>  
  
    1.  <span data-ttu-id="f594c-139">Certifique-se de incluir a barra invertida ' \' como parte do nome do caminho</span><span class="sxs-lookup"><span data-stu-id="f594c-139">Be sure to include the backslash '\' as part of the path name</span></span>  
  
    2.  <span data-ttu-id="f594c-140">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-140">Example:</span></span>  
  
        ```  
        :setvar checkpoint_files_location "d:\DBData\"  
        ...  
        :setvar database_name "AdventureWorks2014"  
        ```  
  
7.  <span data-ttu-id="f594c-141">Execute o script de exemplo de uma destas duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="f594c-141">Execute the sample script, in one of two ways:</span></span>  
  
    1.  <span data-ttu-id="f594c-142">Usando o utilitário de linha de comando sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="f594c-142">Using the sqlcmd command-line utility.</span></span> <span data-ttu-id="f594c-143">Por exemplo, ao executar o seguinte comando do prompt de linha de comando na pasta que contém o script:</span><span class="sxs-lookup"><span data-stu-id="f594c-143">For example, for example by running the following command from the command-line prompt in the folder containing the script:</span></span>  
  
        ```  
        sqlcmd -S . -E -i "ssSQL14 RTM hek_2 Sample.sql"  
        ```  
  
    2.  <span data-ttu-id="f594c-144">Usando o Management Studio:</span><span class="sxs-lookup"><span data-stu-id="f594c-144">Using Management Studio:</span></span>  
  
        1.  <span data-ttu-id="f594c-145">Abra o script ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL ' em uma janela de consulta</span><span class="sxs-lookup"><span data-stu-id="f594c-145">Open the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' in a query window</span></span>  
  
        2.  <span data-ttu-id="f594c-146">Conecte-se ao servidor de destino que contém o banco de dados AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="f594c-146">Connect to the target server that contains the database AdventureWorks2014</span></span>  
  
        3.  <span data-ttu-id="f594c-147">Habilite o modo SQLCMD clicando em "Query-> modo SQLCMD"</span><span class="sxs-lookup"><span data-stu-id="f594c-147">Enable SQLCMD Mode, by clicking on 'Query -> SQLCMD Mode'</span></span>  
  
        4.  <span data-ttu-id="f594c-148">Clique no botão "executar" para executar o script</span><span class="sxs-lookup"><span data-stu-id="f594c-148">Click the button 'Execute' to run the script</span></span>  
  
##  <a name="description-of-the-sample-tables-and-procedures"></a><a name="Descriptionofthesampletablesandprocedures"></a> <span data-ttu-id="f594c-149">Descrição das tabelas e procedimentos de exemplo</span><span class="sxs-lookup"><span data-stu-id="f594c-149">Description of the sample tables and procedures</span></span>  
 <span data-ttu-id="f594c-150">O exemplo cria novas tabelas para produtos e pedidos de vendas, com base em tabelas existentes no AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f594c-150">The sample creates new tables for products and sales orders, based on existing tables in AdventureWorks.</span></span> <span data-ttu-id="f594c-151">O esquema das novas tabelas é semelhante às tabelas existentes, com algumas diferenças, conforme explicado a seguir.</span><span class="sxs-lookup"><span data-stu-id="f594c-151">The schema of the new tables is similar to the existing tables, with a few differences, as explained below.</span></span>  
  
 <span data-ttu-id="f594c-152">As novas tabelas com otimização de memória têm o sufixo "_inmem".</span><span class="sxs-lookup"><span data-stu-id="f594c-152">The new memory-optimized tables carry the suffix '_inmem'.</span></span> <span data-ttu-id="f594c-153">O exemplo também inclui as tabelas correspondentes que têm o sufixo "_ondisk" – essas tabelas podem ser usadas para fazer uma comparação um-para-um entre o desempenho de tabelas com otimização de memória e tabelas baseadas em disco em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="f594c-153">The sample also includes corresponding tables carrying the suffix '_ondisk' - these tables can be used to make a one-to-one comparison between the performance of memory-optimized tables and disk-based tables on your system..</span></span>  
  
 <span data-ttu-id="f594c-154">Observe que as tabelas com otimização de memória usadas na carga de trabalho para a comparação de desempenho são totalmente duráveis e registradas.</span><span class="sxs-lookup"><span data-stu-id="f594c-154">Note that the memory-optimized tables used in the workload for performance comparison are fully durable and fully logged.</span></span> <span data-ttu-id="f594c-155">Elas não sacrificam a durabilidade ou a confiabilidade para ter o ganho de desempenho.</span><span class="sxs-lookup"><span data-stu-id="f594c-155">They do not sacrifice durability or reliability to attain the performance gain.</span></span>  
  
 <span data-ttu-id="f594c-156">A carga de trabalho de destino para esse exemplo é o processamento de pedidos de vendas, onde também consideramos informações sobre produtos e descontos.</span><span class="sxs-lookup"><span data-stu-id="f594c-156">The target workload for this sample is sales order processing, where we consider also information about products and discounts.</span></span> <span data-ttu-id="f594c-157">Com esse fim, a tabela SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer e SpecialOfferProduct.</span><span class="sxs-lookup"><span data-stu-id="f594c-157">To this end, the table SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, and SpecialOfferProduct.</span></span>  
  
 <span data-ttu-id="f594c-158">Dois novos procedimentos armazenados, Sales.usp_InsertSalesOrder_inmem e Sales.usp_UpdateSalesOrderShipInfo_inmem, são usados para inserir pedidos de vendas e atualizar as informações de envio de um pedido de vendas específico.</span><span class="sxs-lookup"><span data-stu-id="f594c-158">Two new stored procedures, Sales.usp_InsertSalesOrder_inmem and Sales.usp_UpdateSalesOrderShipInfo_inmem, are used to insert sales orders and to update the shipping information of a given sales order.</span></span>  
  
 <span data-ttu-id="f594c-159">O novo esquema 'Demonstração' contém tabelas e procedimentos armazenados auxiliares para executar uma carga de trabalho de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-159">The new schema 'Demo' contains helper tables and stored procedures to execute a demo workload.</span></span>  
  
 <span data-ttu-id="f594c-160">Concretamente, o exemplo de [!INCLUDE[hek_2](../includes/hek-2-md.md)] adiciona os seguintes objetos ao AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="f594c-160">Concretely, the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample adds the following objects to AdventureWorks:</span></span>  
  
### <a name="tables-added-by-the-sample"></a><span data-ttu-id="f594c-161">Tabelas adicionadas pelo exemplo</span><span class="sxs-lookup"><span data-stu-id="f594c-161">Tables added by the sample</span></span>  
  
#### <a name="the-new-tables"></a><span data-ttu-id="f594c-162">As novas tabelas</span><span class="sxs-lookup"><span data-stu-id="f594c-162">The New Tables</span></span>  
 <span data-ttu-id="f594c-163">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-163">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="f594c-164">Informações de cabeçalho sobre os pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-164">Header information about sales orders.</span></span> <span data-ttu-id="f594c-165">Cada pedido de vendas tem uma linha nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="f594c-165">Each sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="f594c-166">Sales.SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-166">Sales.SalesOrderDetail_inmem</span></span>  
  
-   <span data-ttu-id="f594c-167">Detalhes dos pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-167">Details of sales orders.</span></span> <span data-ttu-id="f594c-168">Cada item de linha de um pedido de vendas tem uma linha nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="f594c-168">Each line item of a sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="f594c-169">Sales.SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-169">Sales.SpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="f594c-170">Informações sobre as ofertas especiais, incluindo o percentual de desconto associado a cada oferta especial.</span><span class="sxs-lookup"><span data-stu-id="f594c-170">Information about special offers, including the discount percentage associated with each special offer.</span></span>  
  
 <span data-ttu-id="f594c-171">Sales.SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-171">Sales.SpecialOfferProduct_inmem</span></span>  
  
-   <span data-ttu-id="f594c-172">Tabela de referência entre ofertas especiais e produtos.</span><span class="sxs-lookup"><span data-stu-id="f594c-172">Reference table between special offers and products.</span></span> <span data-ttu-id="f594c-173">Cada oferta especial pode caracterizar zero ou mais produtos, e cada produto pode ser caracterizado em zero ou mais ofertas especiais.</span><span class="sxs-lookup"><span data-stu-id="f594c-173">Each special offer can feature zero or more products, and each product can be featured in zero or more special offers.</span></span>  
  
 <span data-ttu-id="f594c-174">Production.Product_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-174">Production.Product_inmem</span></span>  
  
-   <span data-ttu-id="f594c-175">Informações sobre os produtos, inclusive o preço da lista.</span><span class="sxs-lookup"><span data-stu-id="f594c-175">Information about products, including their list price.</span></span>  
  
 <span data-ttu-id="f594c-176">Demo.DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="f594c-176">Demo.DemoSalesOrderDetailSeed</span></span>  
  
-   <span data-ttu-id="f594c-177">Usado na carga de trabalho de demonstração para criar exemplos de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-177">Used in the demo workload to construct sample sales orders.</span></span>  
  
 <span data-ttu-id="f594c-178">Variações das tabelas baseadas em disco:</span><span class="sxs-lookup"><span data-stu-id="f594c-178">Disk-based variations of the tables:</span></span>  
  
-   <span data-ttu-id="f594c-179">Sales.SalesOrderHeader_ondisk</span><span class="sxs-lookup"><span data-stu-id="f594c-179">Sales.SalesOrderHeader_ondisk</span></span>  
  
-   <span data-ttu-id="f594c-180">Sales.SalesOrderDetail_ondisk</span><span class="sxs-lookup"><span data-stu-id="f594c-180">Sales.SalesOrderDetail_ondisk</span></span>  
  
-   <span data-ttu-id="f594c-181">Sales.SpecialOffer_ondisk</span><span class="sxs-lookup"><span data-stu-id="f594c-181">Sales.SpecialOffer_ondisk</span></span>  
  
-   <span data-ttu-id="f594c-182">Sales.SpecialOfferProduct_ondisk</span><span class="sxs-lookup"><span data-stu-id="f594c-182">Sales.SpecialOfferProduct_ondisk</span></span>  
  
-   <span data-ttu-id="f594c-183">Production.Product_ondisk</span><span class="sxs-lookup"><span data-stu-id="f594c-183">Production.Product_ondisk</span></span>  
  
#### <a name="differences-between-original-disk-based-and-the-and-new-memory-optimized-tables"></a><span data-ttu-id="f594c-184">Diferenças entre as tabelas originais baseadas em disco e as novas tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-184">Differences between original disk-based and the and new memory-optimized tables</span></span>  
 <span data-ttu-id="f594c-185">Geralmente, as novas tabelas apresentadas por este exemplo usam as mesmas colunas e os mesmos tipos de dados que as tabelas originais.</span><span class="sxs-lookup"><span data-stu-id="f594c-185">For the most part, the new tables introduced by this sample use the same columns and the same data types as the original tables.</span></span> <span data-ttu-id="f594c-186">No entanto, há algumas diferenças.</span><span class="sxs-lookup"><span data-stu-id="f594c-186">However, there are a few differences.</span></span> <span data-ttu-id="f594c-187">Listamos as diferenças abaixo, junto com uma razão para as alterações.</span><span class="sxs-lookup"><span data-stu-id="f594c-187">We list the differences below, along with a rationale for the changes.</span></span>  
  
 <span data-ttu-id="f594c-188">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-188">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="f594c-189">*Restrições padrão* têm suporte para tabelas com otimização de memória, e migramos a maioria das restrições padrão como tal.</span><span class="sxs-lookup"><span data-stu-id="f594c-189">*Default constraints* are supported for memory-optimized tables, and most default constraints we migrated as is.</span></span> <span data-ttu-id="f594c-190">No entanto, a tabela Sales.SalesOrderHeader original contém duas restrições padrão que recuperam a data atual, pata as colunas OrderDate e ModifiedDate.</span><span class="sxs-lookup"><span data-stu-id="f594c-190">However, the original table Sales.SalesOrderHeader contains two default constraints that retrieve the current date, for the columns OrderDate and ModifiedDate.</span></span> <span data-ttu-id="f594c-191">Em uma carga de trabalho de processamento de pedidos com alta taxa de transferência e muita simultaneidade, qualquer recurso global pode se tornar um ponto de contenção.</span><span class="sxs-lookup"><span data-stu-id="f594c-191">In a high throughput order processing workload with a lot of concurrency, any global resource can become a point of contention.</span></span> <span data-ttu-id="f594c-192">O tempo do sistema é um recurso bem global, e observamos que ele pode se tornar um gargalo quando você executa uma carga de trabalho de [!INCLUDE[hek_2](../includes/hek-2-md.md)] que insere pedidos de vendas, em particular se o tempo do sistema precisa ser recuperado para várias colunas no cabeçalho do pedido de vendas, bem como os detalhes do pedido de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-192">System time is such a global resource, and we have observed that it can become a bottleneck when running an [!INCLUDE[hek_2](../includes/hek-2-md.md)] workload that inserts sales orders, in particular if the system time needs to be retrieved for multiple columns in the sales order header, as well as the sales order details.</span></span> <span data-ttu-id="f594c-193">O problema é tratado neste exemplo através da recuperação do tempo do sistema apenas uma vez para cada pedido de vendas que é inserido, e o uso desse valor para as colunas de data e hora em SalesOrderHeader_inmem e em SalesOrderDetail_inmem, no procedimento armazenado Sales.usp_InsertSalesOrder_inmem.</span><span class="sxs-lookup"><span data-stu-id="f594c-193">The problem is addressed in this sample by retrieving the system time only once for each sales order that is inserted, and use that value for the datetime columns in SalesOrderHeader_inmem and SalesOrderDetail_inmem, in the stored procedure Sales.usp_InsertSalesOrder_inmem.</span></span>  
  
-   <span data-ttu-id="f594c-194">*UDTs de alias* - a tabela original usa dois alias de tipos de dados definidos pelo usuário (UDTs), dbo.OrderNumber e dbo.AccountNumber, para as colunas PurchaseOrderNumber e AccountNumber, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f594c-194">*Alias UDTs* - The original table uses two alias user-defined data types (UDTs) dbo.OrderNumber and dbo.AccountNumber, for the columns PurchaseOrderNumber and AccountNumber, respectively.</span></span> <span data-ttu-id="f594c-195">O[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] não dá suporte ao UDT de alias para tabelas com otimização de memória; portanto, as novas tabelas usam os tipos de dados do sistema nvarchar(25) e nvarchar(15), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f594c-195">[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support alias UDT for memory-optimized tables, thus the new tables use system data types nvarchar(25) and nvarchar(15), respectively.</span></span>  
  
-   <span data-ttu-id="f594c-196">*Colunas que permitem valor nulo em chaves de índice* - na tabela original, a coluna SalesPersonID é anulável, enquanto em novas tabelas a coluna não é anulável e tem uma restrição padrão com valor (-1).</span><span class="sxs-lookup"><span data-stu-id="f594c-196">*Nullable columns in index keys* - In the original table, the column SalesPersonID is nullable, while in the new tables the column is not nullable and has a default constraint with value (-1).</span></span> <span data-ttu-id="f594c-197">Isso ocorre porque os índices nas tabelas com otimização de memória não podem ter colunas anuláveis na chave do índice; -1 é um substituto de NULL nesse caso.</span><span class="sxs-lookup"><span data-stu-id="f594c-197">This is because indexes on memory-optimized tables cannot have nullable columns in the index key; -1 is a surrogate for NULL in this case.</span></span>  
  
-   <span data-ttu-id="f594c-198">*Colunas computadas* - as colunas computadas SalesOrderNumber e TotalDue são omitidas, pois o [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] não oferece suporte a colunas computadas em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="f594c-198">*Computed columns* - The computed columns SalesOrderNumber and TotalDue are omitted, as [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support computed columns in memory-optimized tables.</span></span> <span data-ttu-id="f594c-199">A nova exibição Sales.vSalesOrderHeader_extended_inmem reflete as colunas SalesOrderNumber e TotalDue.</span><span class="sxs-lookup"><span data-stu-id="f594c-199">The new view Sales.vSalesOrderHeader_extended_inmem reflects the columns SalesOrderNumber and TotalDue.</span></span> <span data-ttu-id="f594c-200">Por disso, você pode usar essa exibição se essas colunas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="f594c-200">Therefore, you can use this view if these columns are needed.</span></span>  
  
-   <span data-ttu-id="f594c-201">As*restrições de chave estrangeira* não têm suporte para tabelas com otimização de memória no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-201">*Foreign key constraints* are not supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="f594c-202">Além disso, SalesOrderHeader_inmem é uma tabela ativa na carga de trabalho de exemplo, e as restrições de chaves estrangeiras exigem processamento adicional para todas as operações DML, pois são necessárias pesquisas em todas as outras tabelas referenciadas nessas restrições.</span><span class="sxs-lookup"><span data-stu-id="f594c-202">In addition, SalesOrderHeader_inmem is a hot table in the example workload, and foreign keys constraints require additional processing for all DML operations, as it requires lookups in all the other tables referenced in these constraints.</span></span> <span data-ttu-id="f594c-203">Consequentemente, a suposição é a de que o aplicativo garante a integridade referencial, e a integridade referencial não é validada quando linhas são inseridas.</span><span class="sxs-lookup"><span data-stu-id="f594c-203">Therefore, the assumption is that the app ensures referential integrity, and referential integrity is not validated when rows are inserted.</span></span> <span data-ttu-id="f594c-204">A integridade referencial dos dados nessa tabela pode ser verificada usando o procedimento armazenado dbo.usp_ValidateIntegrity, através do seguinte script:</span><span class="sxs-lookup"><span data-stu-id="f594c-204">Referential integrity for the data in this table can be verified using the stored procedure dbo.usp_ValidateIntegrity, using the following script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="f594c-205">As*restrições check* não têm suporte para tabelas com otimização de memória no SQ Server 2014.</span><span class="sxs-lookup"><span data-stu-id="f594c-205">*Check constraints* are not supported for memory-optimized tables in SQ Server 2014.</span></span> <span data-ttu-id="f594c-206">A integridade de domínio é validada junto com a integridade referencial usando esse script:</span><span class="sxs-lookup"><span data-stu-id="f594c-206">Domain integrity is validated along with referential integrity using this script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="f594c-207">*Rowguid* - a coluna rowguid é omitida.</span><span class="sxs-lookup"><span data-stu-id="f594c-207">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="f594c-208">Apesar de uniqueidentifier ter suporte para tabelas com otimização de memória, a opção ROWGUIDCOL não tem suporte no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-208">While uniqueidentifier is support for memory-optimized tables, the option ROWGUIDCOL is not supported in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="f594c-209">As colunas desse tipo são geralmente usadas para a replicação de mesclagem ou para tabelas com colunas filestream.</span><span class="sxs-lookup"><span data-stu-id="f594c-209">Columns of this kind are typically used for either merge replication or tables that have filestream columns.</span></span> <span data-ttu-id="f594c-210">Este exemplo não inclui isso.</span><span class="sxs-lookup"><span data-stu-id="f594c-210">This sample includes neither.</span></span>  
  
 <span data-ttu-id="f594c-211">Sales.SalesOrderDetail</span><span class="sxs-lookup"><span data-stu-id="f594c-211">Sales.SalesOrderDetail</span></span>  
  
-   <span data-ttu-id="f594c-212">*Restrições padrão* – semelhante ao SalesOrderHeader, a restrição padrão que requer a data/hora do sistema não é migrada; o procedimento armazenado que insere os pedidos de vendas fica responsável por inserir a data/hora atual do sistema na primeira inserção.</span><span class="sxs-lookup"><span data-stu-id="f594c-212">*Default constraints* - similar to SalesOrderHeader, the default constraint requiring the system date/time is not migrated, instead the stored procedure inserting sales orders takes care of inserting the current system date/time on first insert.</span></span>  
  
-   <span data-ttu-id="f594c-213">*Colunas computadas* – a coluna computada LineTotal não foi migrada pois colunas computadas não são compatíveis com tabelas com otimização de memória no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f594c-213">*Computed columns* - the computed column LineTotal was not migrated as computed columns are not supported with memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="f594c-214">Para acessar essa coluna, use a exibição Sales.vSalesOrderDetail_extended_inmem.</span><span class="sxs-lookup"><span data-stu-id="f594c-214">To access this column use the view Sales.vSalesOrderDetail_extended_inmem.</span></span>  
  
-   <span data-ttu-id="f594c-215">*Rowguid* - a coluna rowguid é omitida.</span><span class="sxs-lookup"><span data-stu-id="f594c-215">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="f594c-216">Para obter detalhes, consulte a descrição da tabela SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="f594c-216">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="f594c-217">Para as restrições de *verificação* e *chave estrangeira* , consulte a descrição de SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="f594c-217">For *check* and *foreign key* constraints see the description of SalesOrderHeader.</span></span> <span data-ttu-id="f594c-218">O seguinte script pode ser usado para verificar o domínio e a integridade referencial dessa tabela:</span><span class="sxs-lookup"><span data-stu-id="f594c-218">The following script can be used to verify domain and referential integrity for this table:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
 <span data-ttu-id="f594c-219">Production.Product</span><span class="sxs-lookup"><span data-stu-id="f594c-219">Production.Product</span></span>  
  
-   <span data-ttu-id="f594c-220">*UDTs de alias* – a tabela original usa tipo de dados definidos pelo usuário dbo.Flag, que equivalem ao tipo de dados bit do sistema.</span><span class="sxs-lookup"><span data-stu-id="f594c-220">*Alias UDTs* - the original table uses the user-defined data type dbo.Flag, which is equivalent to the system data type bit.</span></span> <span data-ttu-id="f594c-221">A tabela migrada usa o tipo de dados bit.</span><span class="sxs-lookup"><span data-stu-id="f594c-221">The migrated table uses the bit data type instead.</span></span>  
  
-   <span data-ttu-id="f594c-222">*Agrupamento BIN2* – as colunas Name e ProductNumber são incluídas em chaves de índice e, portanto, devem ter agrupamentos BIN2 no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f594c-222">*BIN2 collation* - The columns Name and ProductNumber are included in index keys, and must thus have BIN2 collations in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="f594c-223">Aqui, a suposição é a de que o aplicativo não se baseia em especificações de ordenação, como a não diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f594c-223">Here, the assumption is that the app does not rely on collation specifics, like case insensitivity.</span></span>  
  
-   <span data-ttu-id="f594c-224">*Rowguid* - a coluna rowguid é omitida.</span><span class="sxs-lookup"><span data-stu-id="f594c-224">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="f594c-225">Para obter detalhes, consulte a descrição da tabela SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="f594c-225">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="f594c-226">As restrições*Unique*, *Check* e *Foreign Key* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem e Product.usp_DeleteProduct_inmem can be used to insert e delete products; these procedures validate domain e referential integrity, e will fail if integrity is violated.</span><span class="sxs-lookup"><span data-stu-id="f594c-226">*Unique*, *Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem and Product.usp_DeleteProduct_inmem can be used to insert and delete products; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="f594c-227">Além disso, o seguinte script pode ser usado para validar o domínio e a integridade referencial como tal:</span><span class="sxs-lookup"><span data-stu-id="f594c-227">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Production.Product')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
    -   <span data-ttu-id="f594c-228">Observe que os procedimentos armazenados usp_InsertProduct_inmem e usp_DeleteProduct_inmem consideram apenas chaves estrangeiras entre as tabelas migradas.</span><span class="sxs-lookup"><span data-stu-id="f594c-228">Note that the store procedures usp_InsertProduct_inmem and usp_DeleteProduct_inmem consider only foreign keys between the migrated tables.</span></span> <span data-ttu-id="f594c-229">As referências a outras tabelas ProductModel, ProductSubcategory e UnitMeasure não são consideradas.</span><span class="sxs-lookup"><span data-stu-id="f594c-229">References to other tables ProductModel, ProductSubcategory, and UnitMeasure are not considered.</span></span>  
  
 <span data-ttu-id="f594c-230">Sales.SpecialOffer</span><span class="sxs-lookup"><span data-stu-id="f594c-230">Sales.SpecialOffer</span></span>  
  
-   <span data-ttu-id="f594c-231">As restrições*Check* e *Foreign Key* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem e Sales.usp_DeleteSpecialOffer_inmem can be used to insert e delete special offers; these procedures validate domain e referential integrity, e will fail if integrity is violated.</span><span class="sxs-lookup"><span data-stu-id="f594c-231">*Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem and Sales.usp_DeleteSpecialOffer_inmem can be used to insert and delete special offers; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="f594c-232">Além disso, o seguinte script pode ser usado para validar o domínio e a integridade referencial como tal:</span><span class="sxs-lookup"><span data-stu-id="f594c-232">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOffer_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="f594c-233">*Rowguid* - a coluna rowguid é omitida.</span><span class="sxs-lookup"><span data-stu-id="f594c-233">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="f594c-234">Para obter detalhes, consulte a descrição da tabela SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="f594c-234">For details see the description for the table SalesOrderHeader.</span></span>  
  
 <span data-ttu-id="f594c-235">Sales.SpecialOfferProduct</span><span class="sxs-lookup"><span data-stu-id="f594c-235">Sales.SpecialOfferProduct</span></span>  
  
-   <span data-ttu-id="f594c-236">As restrições*Foreign Key* são tratadas de duas maneiras: o procedimento armazenado Sales.usp_InsertSpecialOfferProduct_inmem pode ser usado para inserir relações entre ofertas especiais e produtos; esse procedimento valida a integridade referencial, e falhará se a integridade for violada.</span><span class="sxs-lookup"><span data-stu-id="f594c-236">*Foreign Key constraints* are accounted for in two ways: the stored procedure Sales.usp_InsertSpecialOfferProduct_inmem can be used to insert relationships between special offers and products; this procedures validates referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="f594c-237">Além disso, o seguinte script pode ser usado para validar a integridade referencial como tal:</span><span class="sxs-lookup"><span data-stu-id="f594c-237">In addition, the follow script can be used to validate referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOfferProduct_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="f594c-238">*Rowguid* - a coluna rowguid é omitida.</span><span class="sxs-lookup"><span data-stu-id="f594c-238">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="f594c-239">Para obter detalhes, consulte a descrição da tabela SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="f594c-239">For details see the description for the table SalesOrderHeader.</span></span>  
  
#### <a name="considerations-for-indexes-on-memory-optimized-tables"></a><span data-ttu-id="f594c-240">Considerações para índices em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-240">Considerations for indexes on memory-optimized tables</span></span>  
 <span data-ttu-id="f594c-241">O índice de linha de base para tabelas com otimização de memória é o índice NONCLUSTERED, que dá suporte a pesquisas de ponto (busca de índice em predicado de igualdade), exames de intervalo (busca de índice em predicado de desigualdade), verificações de índice completo e exames ordenados.</span><span class="sxs-lookup"><span data-stu-id="f594c-241">The baseline index for memory-optimized tables is the NONCLUSTERED index, which supports point lookups (index seek on equality predicate), range scans (index seek in inequality predicate), full index scans, and ordered scans.</span></span> <span data-ttu-id="f594c-242">Além disso, os índices NONCLUSTERED dão suporte à pesquisa nas colunas principais da chave de índice.</span><span class="sxs-lookup"><span data-stu-id="f594c-242">In addition, NONCLUSTERED indexes support searching on leading columns of the index key.</span></span> <span data-ttu-id="f594c-243">De fato, os índices NONCLUSTERED com otimização de memória dão suporte a todas as operações com o suporte de índices NONCLUSTERED baseados em disco, exceto apenas para verificações regressivas.</span><span class="sxs-lookup"><span data-stu-id="f594c-243">In fact memory-optimized NONCLUSTERED indexes support all the operations supported by disk-based NONCLUSTERED indexes, with the only exception being backward scans.</span></span> <span data-ttu-id="f594c-244">Portanto, o uso de índices NONCLUSTERED é uma opção confiável para seus índices.</span><span class="sxs-lookup"><span data-stu-id="f594c-244">Therefore, using NONCLUSTERED indexes is a safe choice for your indexes.</span></span>  
  
 <span data-ttu-id="f594c-245">Os índices de HASH podem ser usados para otimizar mais a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f594c-245">HASH indexes are can be used to further optimize the workload.</span></span> <span data-ttu-id="f594c-246">Eles são particularmente otimizados para pesquisas de ponto e inserções de linhas.</span><span class="sxs-lookup"><span data-stu-id="f594c-246">They are particularly optimized for point lookups and row inserts.</span></span> <span data-ttu-id="f594c-247">No entanto, lembre-se de que eles não dão suporte a exames de intervalo, exames ordenados ou pesquisas nas colunas de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="f594c-247">However, one must consider that they do not support range scans, ordered scans, or search on leading index key columns.</span></span> <span data-ttu-id="f594c-248">Consequentemente, tome cuidado ao usar esses índices.</span><span class="sxs-lookup"><span data-stu-id="f594c-248">Therefore, care needs to be taken when using these indexes.</span></span> <span data-ttu-id="f594c-249">Além disso, é necessário especificar o bucket_count na hora da criação.</span><span class="sxs-lookup"><span data-stu-id="f594c-249">In addition, it is necessary to specify the bucket_count at create time.</span></span> <span data-ttu-id="f594c-250">Normalmente, ele deve ser definido entre uma e duas vezes o número de valores de chave de índice, mas valores superestimados não costumam ser um problema.</span><span class="sxs-lookup"><span data-stu-id="f594c-250">It should usually be set at between one and two times the number of index key values, but overestimating is usually not a problem.</span></span>  
  
 <span data-ttu-id="f594c-251">Consulte os Manuais Online para obter mais detalhes sobre [diretrizes de índice](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) e diretrizes para [escolher o bucket_count certo](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f594c-251">See Books Online for more details about [index guidelines](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) and guidelines for [choosing the right bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="f594c-252">Os índices nas tabelas migradas foram ajustados para a carga de trabalho de processamento de pedidos de vendas de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-252">The indexes on the migrated tables have been tuned for the demo sales order processing workload.</span></span> <span data-ttu-id="f594c-253">A carga de trabalho se baseia em inserções e pesquisas de ponto nas tabelas Sales.SalesOrderHeader_inmem e Sales.SalesOrderDetail_inmem, e ela também se baseia em pesquisas de ponto nas colunas de chave primária nas tabelas Production.Product_inmem e Sales.SpecialOffer_inmem.</span><span class="sxs-lookup"><span data-stu-id="f594c-253">The workload relies on inserts and point lookups in the tables Sales.SalesOrderHeader_inmem and Sales.SalesOrderDetail_inmem, and it also relies on point lookups on the primary key columns in the tables Production.Product_inmem and Sales.SpecialOffer_inmem.</span></span>  
  
 <span data-ttu-id="f594c-254">Sales.SalesOrderHeader_inmem tem três índices, que são todos os índices de HASH por motivos de desempenho, e porque exames ordenados ou de intervalo não são necessários para a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f594c-254">Sales.SalesOrderHeader_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="f594c-255">Índice de HASH em (SalesOrderID): o bucket_count é dimensionado em 10 milhões (arredondado para 16 milhões), pois o número esperado de pedidos de vendas é de 10 milhões</span><span class="sxs-lookup"><span data-stu-id="f594c-255">HASH index on (SalesOrderID): bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="f594c-256">Índice de HASH em (SalesPersonID): o bucket_count é de 1 milhão.</span><span class="sxs-lookup"><span data-stu-id="f594c-256">HASH index on (SalesPersonID): bucket_count is 1 million.</span></span> <span data-ttu-id="f594c-257">O conjunto de dados fornecido não tem muitos vendedores, mas permite futuro crescimento; além disso, não haverá uma penalidade de desempenho por pesquisas de ponto se o bucket_count for superdimensionado.</span><span class="sxs-lookup"><span data-stu-id="f594c-257">The data set provided does not have a lot of sales persons, but this allows for future growth, plus you don't pay a performance penalty for point lookups if the bucket_count is oversized.</span></span>  
  
-   <span data-ttu-id="f594c-258">Índice de HASH em (CustomerID): o bucket_count é de 1 milhão.</span><span class="sxs-lookup"><span data-stu-id="f594c-258">HASH index on (CustomerID): bucket_count is 1 million.</span></span> <span data-ttu-id="f594c-259">O conjunto de dados fornecido não tem muitos clientes, mas permite futuro crescimento.</span><span class="sxs-lookup"><span data-stu-id="f594c-259">The data set provided does not have a lot of customers, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="f594c-260">Sales.SalesOrderDetail_inmem tem três índices, que são todos os índices de HASH por motivos de desempenho, e porque exames ordenados ou de intervalo não são necessários para a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f594c-260">Sales.SalesOrderDetail_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="f594c-261">Índice de HASH em (SalesOrderID, SalesOrderDetailID): esse é o índice de chave primária e, apesar de as pesquisas em (SalesOrderID, SalesOrderDetailID) serem raras, o uso de um índice de hash para a chave acelera as inserções de linhas.</span><span class="sxs-lookup"><span data-stu-id="f594c-261">HASH index on (SalesOrderID, SalesOrderDetailID): this is the primary key index, and even though lookups on (SalesOrderID, SalesOrderDetailID) will be infrequent, using a hash index for the key speeds up row inserts.</span></span> <span data-ttu-id="f594c-262">O bucket_count é dimensionado em 50 milhões (arredondado para 67 milhões): o número esperado de pedidos de vendas é de 10 milhões, e esse valor é dimensionado para ter uma média de 5 itens por pedido</span><span class="sxs-lookup"><span data-stu-id="f594c-262">The bucket_count is sized at 50 million (rounded up to 67 million): the expected number of sales orders is 10 million, and this is sized to have an average of 5 items per order</span></span>  
  
-   <span data-ttu-id="f594c-263">Índice de HASH em (SalesOrderID): as pesquisas por pedido de vendas são frequentes: você desejará localizar todos os itens de linha que correspondem a um único pedido.</span><span class="sxs-lookup"><span data-stu-id="f594c-263">HASH index on (SalesOrderID): lookups by sales order are frequent: you will want to find all the line items corresponding to a single order.</span></span>  <span data-ttu-id="f594c-264">O bucket_count é dimensionado em 10 milhões (arredondado para 16 milhões), pois o número esperado de pedidos de vendas é de 10 milhões</span><span class="sxs-lookup"><span data-stu-id="f594c-264">bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="f594c-265">Índice de HASH em (ProductID): o bucket_count é de 1 milhão.</span><span class="sxs-lookup"><span data-stu-id="f594c-265">HASH index on (ProductID): bucket_count is 1 million.</span></span> <span data-ttu-id="f594c-266">O conjunto de dados fornecido não tem muitos produtos, mas permite futuro crescimento.</span><span class="sxs-lookup"><span data-stu-id="f594c-266">The data set provided does not have a lot of product, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="f594c-267">Production.Product_inmem tem três índices</span><span class="sxs-lookup"><span data-stu-id="f594c-267">Production.Product_inmem has three indexes</span></span>  
  
-   <span data-ttu-id="f594c-268">Índice de HASH em (ProductID): as pesquisas em ProductID estão no caminho crítico para a carga de trabalho de demonstração; então, este é um índice de hash</span><span class="sxs-lookup"><span data-stu-id="f594c-268">HASH index on (ProductID): lookups on ProductID are in the critical path for the demo workload, therefore this is a hash index</span></span>  
  
-   <span data-ttu-id="f594c-269">Índice NONCLUSTERED em (Name): isso permitirá exames ordenados de nomes de produtos</span><span class="sxs-lookup"><span data-stu-id="f594c-269">NONCLUSTERED index on (Name): this will allow ordered scans of product names</span></span>  
  
-   <span data-ttu-id="f594c-270">Índice NONCLUSTERED em (ProductNumber): isso permitirá exames ordenados de números de produtos</span><span class="sxs-lookup"><span data-stu-id="f594c-270">NONCLUSTERED index on (ProductNumber): this will allow ordered scans of product numbers</span></span>  
  
 <span data-ttu-id="f594c-271">Sales.SpecialOffer_inmem tem um índice de HASH em (SpecialOfferID): as pesquisas de ponto de ofertas especiais estão na parte essencial da carga de trabalho de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-271">Sales.SpecialOffer_inmem has one HASH index on (SpecialOfferID): point lookups of special offers are in the critical part of the demo workload.</span></span> <span data-ttu-id="f594c-272">O bucket_count é dimensionado em 1 milhão para permitir futuro crescimento.</span><span class="sxs-lookup"><span data-stu-id="f594c-272">The bucket_count is sized at 1 million to allow for future growth.</span></span>  
  
 <span data-ttu-id="f594c-273">Sales.SpecialOfferProduct_inmem não é referenciado na carga de trabalho de demonstração e, assim, não há necessidade aparente de usar índices de hash nessa tabela para otimizar a carga de trabalho – os índices em (SpecialOfferID, ProductID) e (ProductID) são NONCLUSTERED.</span><span class="sxs-lookup"><span data-stu-id="f594c-273">Sales.SpecialOfferProduct_inmem is not referenced in the demo workload, and thus there is no apparent need to use hash indexes on this table to optimize the workload - the indexes on (SpecialOfferID, ProductID) and (ProductID) are NONCLUSTERED.</span></span>  
  
 <span data-ttu-id="f594c-274">Observe que, no exemplo anterior, alguns bucket_counts estão superdimensionados, mas não os bucket_counts para os índices em SalesOrderHeader_inmem e SalesOrderDetail_inmem: eles são dimensionados para apenas 10 milhões de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-274">Notice that in the above some of the bucket_counts are over-sized, but not the bucket_counts for the indexes on SalesOrderHeader_inmem and SalesOrderDetail_inmem: they are sized for just 10 million sales orders.</span></span> <span data-ttu-id="f594c-275">Isso visa permitir a instalação do exemplo em sistemas com baixa disponibilidade de memória, embora nesses casos a carga de trabalho de demonstração falhe quando a memória é insuficiente.</span><span class="sxs-lookup"><span data-stu-id="f594c-275">This was done to allow installing the sample on systems with low memory availability, although in those cases the demo workload will fail with out-of-memory.</span></span> <span data-ttu-id="f594c-276">Se você quiser dimensionar além de 10 milhões de pedidos de vendas, sinta-se à vontade para aumentar o número de buckets de forma correspondente.</span><span class="sxs-lookup"><span data-stu-id="f594c-276">If you do want to scale well beyond 10 million sales orders, feel free to increase the bucket counts accordingly.</span></span>  
  
#### <a name="considerations-for-memory-utilization"></a><span data-ttu-id="f594c-277">Considerações sobre a utilização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-277">Considerations for memory utilization</span></span>  
 <span data-ttu-id="f594c-278">A utilização de memória no banco de dados de exemplo, antes e após executar a carga de trabalho de demonstração, é abordada na seção [Utilização de memória para as tabelas com otimização de memória](#Memoryutilizationforthememory-optimizedtables).</span><span class="sxs-lookup"><span data-stu-id="f594c-278">Memory utilization in the sample database, both before and after running the demo workload, is discussed in the Section [Memory utilization for the memory-optimized tables](#Memoryutilizationforthememory-optimizedtables).</span></span>  
  
### <a name="stored-procedures-added-by-the-sample"></a><span data-ttu-id="f594c-279">Procedimentos armazenados adicionados pelo exemplo</span><span class="sxs-lookup"><span data-stu-id="f594c-279">Stored Procedures added by the sample</span></span>  
 <span data-ttu-id="f594c-280">Os dois principais procedimentos armazenados para inserir o pedido de vendas e atualizar detalhes do envio são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f594c-280">The two key stored procedures for inserting sales order and updating shipping details are as follows:</span></span>  
  
-   <span data-ttu-id="f594c-281">Sales.usp_InsertSalesOrder_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-281">Sales.usp_InsertSalesOrder_inmem</span></span>  
  
    -   <span data-ttu-id="f594c-282">Insere um novo pedido de vendas no banco de dados e gera o SalesOrderID para esse pedido.</span><span class="sxs-lookup"><span data-stu-id="f594c-282">Inserts a new sales order in the database and outputs the SalesOrderID for that sales order.</span></span> <span data-ttu-id="f594c-283">Como os parâmetros de entrada, ele requer detalhes no cabeçalho do pedido de vendas, bem como os itens de linha no pedido</span><span class="sxs-lookup"><span data-stu-id="f594c-283">As input parameters it takes details for the sales order header, as well as the line items in the order.</span></span>  
  
    -   <span data-ttu-id="f594c-284">Parâmetro de saída:</span><span class="sxs-lookup"><span data-stu-id="f594c-284">Output parameter:</span></span>  
  
        -   <span data-ttu-id="f594c-285">@SalesOrderID int – a SalesOrderID do pedido de venda recém-inserido</span><span class="sxs-lookup"><span data-stu-id="f594c-285">@SalesOrderID int - the SalesOrderID for the sales order that was just inserted</span></span>  
  
    -   <span data-ttu-id="f594c-286">Parâmetros de entrada (obrigatório):</span><span class="sxs-lookup"><span data-stu-id="f594c-286">Input parameters (required):</span></span>  
  
        -   <span data-ttu-id="f594c-287">@DueDate datetime2</span><span class="sxs-lookup"><span data-stu-id="f594c-287">@DueDate datetime2</span></span>  
  
        -   <span data-ttu-id="f594c-288">@CustomerID int</span><span class="sxs-lookup"><span data-stu-id="f594c-288">@CustomerID int</span></span>  
  
        -   <span data-ttu-id="f594c-289">@BillToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-289">@BillToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-290">@ShipToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-290">@ShipToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-291">@ShipMethodID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-291">@ShipMethodID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem – TVP que contém os itens de linha do pedido</span><span class="sxs-lookup"><span data-stu-id="f594c-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem - TVP that contains the line items of the order</span></span>  
  
    -   <span data-ttu-id="f594c-293">Parâmetros de entrada (opcional):</span><span class="sxs-lookup"><span data-stu-id="f594c-293">Input parameters (optional):</span></span>  
  
        -   <span data-ttu-id="f594c-294">@Status [tinyint]</span><span class="sxs-lookup"><span data-stu-id="f594c-294">@Status [tinyint]</span></span>  
  
        -   <span data-ttu-id="f594c-295">@OnlineOrderFlag [bit]</span><span class="sxs-lookup"><span data-stu-id="f594c-295">@OnlineOrderFlag [bit]</span></span>  
  
        -   <span data-ttu-id="f594c-296">@PurchaseOrderNumber [nvarchar](25\)</span><span class="sxs-lookup"><span data-stu-id="f594c-296">@PurchaseOrderNumber [nvarchar](25\)</span></span>  
  
        -   <span data-ttu-id="f594c-297">@AccountNumber [nvarchar](15\)</span><span class="sxs-lookup"><span data-stu-id="f594c-297">@AccountNumber [nvarchar](15\)</span></span>  
  
        -   <span data-ttu-id="f594c-298">@SalesPersonID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-298">@SalesPersonID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-299">@TerritoryID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-299">@TerritoryID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-300">@CreditCardID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-300">@CreditCardID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-301">@CreditCardApprovalCode [varchar](15\)</span><span class="sxs-lookup"><span data-stu-id="f594c-301">@CreditCardApprovalCode [varchar](15\)</span></span>  
  
        -   <span data-ttu-id="f594c-302">@CurrencyRateID [int]</span><span class="sxs-lookup"><span data-stu-id="f594c-302">@CurrencyRateID [int]</span></span>  
  
        -   <span data-ttu-id="f594c-303">@Comment nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="f594c-303">@Comment nvarchar(128)</span></span>  
  
-   <span data-ttu-id="f594c-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span></span>  
  
    -   <span data-ttu-id="f594c-305">Atualize as informações de envio de um pedido de vendas específico.</span><span class="sxs-lookup"><span data-stu-id="f594c-305">Update the shipping information for a given sales order.</span></span> <span data-ttu-id="f594c-306">Isso também atualizará as informações de envio para todos os itens de linha do pedido de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-306">This will also update the shipping information for all line items of the sales order.</span></span>  
  
    -   <span data-ttu-id="f594c-307">Este é um procedimento de wrapper para os procedimentos armazenados compilados nativamente Sales.usp_UpdateSalesOrderShipInfo_native, com a lógica de repetição para lidar com conflitos em potencial (inesperados) em transações simultâneas que atualizam o mesmo pedido.</span><span class="sxs-lookup"><span data-stu-id="f594c-307">This is a wrapper procedure for the natively compiled stored procedures Sales.usp_UpdateSalesOrderShipInfo_native with retry logic to deal with (unexpected) potential conflicts with concurrent transactions updating the same order.</span></span> <span data-ttu-id="f594c-308">Para obter mais informações sobre a lógica de repetição, consulte o tópico dos Manuais Online [aqui](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f594c-308">For more information about retry logic see the Books Online topic [here](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="f594c-309">Sales.usp_UpdateSalesOrderShipInfo_native</span><span class="sxs-lookup"><span data-stu-id="f594c-309">Sales.usp_UpdateSalesOrderShipInfo_native</span></span>  
  
    -   <span data-ttu-id="f594c-310">Este é o procedimento armazenado compilado nativamente que efetivamente processa a atualização das informações de envio.</span><span class="sxs-lookup"><span data-stu-id="f594c-310">This is the natively compiled stored procedure that actually processes the update to the shipping information.</span></span> <span data-ttu-id="f594c-311">Ele é o meio a ser chamado do procedimento armazenado de wrapper Sales.usp_UpdateSalesOrderShipInfo_inmem.</span><span class="sxs-lookup"><span data-stu-id="f594c-311">It is means to be called from the wrapper stored procedure Sales.usp_UpdateSalesOrderShipInfo_inmem.</span></span> <span data-ttu-id="f594c-312">Se o cliente pode tratar as falhas e implementa a lógica de repetição, você pode chamar esse procedimento diretamente, e não usar o procedimento armazenado de wrapper.</span><span class="sxs-lookup"><span data-stu-id="f594c-312">If the client can deal with failures and implements retry logic, you can call this procedure directly, rather than using the wrapper stored procedure.</span></span>  
  
 <span data-ttu-id="f594c-313">O procedimento armazenado a seguir é usado para a carga de trabalho de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-313">The following stored procedure is used for the demo workload.</span></span>  
  
-   <span data-ttu-id="f594c-314">Demo.usp_DemoReset</span><span class="sxs-lookup"><span data-stu-id="f594c-314">Demo.usp_DemoReset</span></span>  
  
    -   <span data-ttu-id="f594c-315">Redefine a demonstração, esvaziando e repropagando as tabelas SalesOrderHeader e SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="f594c-315">Resets the demo by emptying and reseeding the SalesOrderHeader and SalesOrderDetail tables.</span></span>  
  
 <span data-ttu-id="f594c-316">Os procedimentos armazenados a seguir são usados para inserir e excluir das tabelas com otimização de memória para garantir o domínio e a integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="f594c-316">The following stored procedures are used for inserting in and deleting from memory-optimized tables while guaranteeing domain and referential integrity.</span></span>  
  
-   <span data-ttu-id="f594c-317">Production.usp_InsertProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-317">Production.usp_InsertProduct_inmem</span></span>  
  
-   <span data-ttu-id="f594c-318">Production.usp_DeleteProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-318">Production.usp_DeleteProduct_inmem</span></span>  
  
-   <span data-ttu-id="f594c-319">Sales.usp_InsertSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-319">Sales.usp_InsertSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="f594c-320">Sales.usp_DeleteSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-320">Sales.usp_DeleteSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="f594c-321">Sales.usp_InsertSpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-321">Sales.usp_InsertSpecialOfferProduct_inmem</span></span>  
  
 <span data-ttu-id="f594c-322">Finalmente, o procedimento armazenado a seguir é usado para verificar o domínio e a integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="f594c-322">Finally the following stored procedure is used to verify domain and referential integrity.</span></span>  
  
1.  <span data-ttu-id="f594c-323">dbo.usp_ValidateIntegrity</span><span class="sxs-lookup"><span data-stu-id="f594c-323">dbo.usp_ValidateIntegrity</span></span>  
  
    -   <span data-ttu-id="f594c-324">Parâmetro opcional: @object_id – ID do objeto para o qual validar a integridade</span><span class="sxs-lookup"><span data-stu-id="f594c-324">Optional parameter: @object_id - ID of the object to validate integrity for</span></span>  
  
    -   <span data-ttu-id="f594c-325">Esse procedimento depende das tabelas dbo.DomainIntegrity, dbo.ReferentialIntegrity e dbo.UniqueIntegrity para as regras de integridade que precisam ser verificadas – o exemplo popula essas tabelas com base na verificação, na chave estrangeira e nas restrições exclusivas que existem para as tabelas originais no banco de dados do AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f594c-325">This procedure relies on the tables dbo.DomainIntegrity, dbo.ReferentialIntegrity, and dbo.UniqueIntegrity for the integrity rules that need to be verified - the sample populates these tables based on the check, foreign key, and unique constraints that exist for the original tables in the AdventureWorks database.</span></span>  
  
    -   <span data-ttu-id="f594c-326">Ele se baseia nos procedimentos auxiliares dbo.usp_GenerateCKCheck auxiliares, dbo.usp_GenerateFKCheck e dbo.GenerateUQCheck para gerar o T-SQL necessário para executar as verificações de integridade.</span><span class="sxs-lookup"><span data-stu-id="f594c-326">It relies on the helper procedures dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, and dbo.GenerateUQCheck to generate the T-SQL needed for performing the integrity checks.</span></span>  
  
##  <a name="performance-measurements-using-the-demo-workload"></a><a name="PerformanceMeasurementsusingtheDemoWorkload"></a> <span data-ttu-id="f594c-327">Medidas de desempenho usando a carga de trabalho de demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-327">Performance Measurements using the Demo Workload</span></span>  
 <span data-ttu-id="f594c-328">Ostress é uma ferramenta de linha de comando que foi desenvolvida pela equipe de suporte do [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f594c-328">Ostress is a command-line tool that was developed by the [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] support team.</span></span> <span data-ttu-id="f594c-329">Essa ferramenta pode ser usada para executar consultas ou executar procedimentos armazenados em paralelo.</span><span class="sxs-lookup"><span data-stu-id="f594c-329">This tool can be used to execute queries or run stored procedures in parallel.</span></span> <span data-ttu-id="f594c-330">Você pode configurar o número de threads para executar em paralelo determinada instrução T-SQL, e pode especificar quantas vezes a instrução deve ser executada neste thread; ostress girará os threads e executará a instrução em todos os threads em paralelo.</span><span class="sxs-lookup"><span data-stu-id="f594c-330">You can configure the number of threads to run a given T-SQL statement in parallel, and you can specify how many times the statement should be executed on this thread; ostress will spin up the threads and execute the statement on all threads in parallel.</span></span> <span data-ttu-id="f594c-331">Ao término da execução de todos os threads, ostress relatará quanto tempo levou para concluir a execução de todos os threads.</span><span class="sxs-lookup"><span data-stu-id="f594c-331">After execution finishes for all threads, ostress will report the time taken for all threads to finish execution.</span></span>  
  
### <a name="installing-ostress"></a><span data-ttu-id="f594c-332">Instalando ostress</span><span class="sxs-lookup"><span data-stu-id="f594c-332">Installing ostress</span></span>  
 <span data-ttu-id="f594c-333">Ostress é instalada como parte dos utilitários de RML; não há instalação autônoma para ostress.</span><span class="sxs-lookup"><span data-stu-id="f594c-333">Ostress is installed as part of the RML Utilities; there is no standalone installation for ostress.</span></span>  
  
 <span data-ttu-id="f594c-334">Etapas da instalação:</span><span class="sxs-lookup"><span data-stu-id="f594c-334">Installation steps:</span></span>  
  
1.  <span data-ttu-id="f594c-335">Baixe e execute o pacote de instalação x64 para os utilitários RML da seguinte página:[https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span><span class="sxs-lookup"><span data-stu-id="f594c-335">Download and run the x64 installation package for the RML utilities from the following page: [https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span></span>  
  
2.  <span data-ttu-id="f594c-336">Se houver uma caixa de diálogo indicando que alguns arquivos estão em uso, clique em "Continuar"</span><span class="sxs-lookup"><span data-stu-id="f594c-336">If there is a dialog box saying certain files are in use, click 'Continue'</span></span>  
  
### <a name="running-ostress"></a><span data-ttu-id="f594c-337">Executando ostress</span><span class="sxs-lookup"><span data-stu-id="f594c-337">Running ostress</span></span>  
 <span data-ttu-id="f594c-338">Ostress é executada do prompt de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f594c-338">Ostress is run from the command-line prompt.</span></span> <span data-ttu-id="f594c-339">É mais conveniente executar a ferramenta do “Prompt Cmd RML”, que é instalado como parte dos utilitários de RML.</span><span class="sxs-lookup"><span data-stu-id="f594c-339">It is most convenient to run the tool from the "RML Cmd Prompt", which is installed as part of the RML Utilities.</span></span>  
  
 <span data-ttu-id="f594c-340">Para abrir o Prompt Cmd RML, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="f594c-340">To open the RML Cmd Prompt follow these instructions:</span></span>  
  
 <span data-ttu-id="f594c-341">No Windows Server 2012 [R2] e no Windows 8 e 8.1, abra o menu iniciar clicando na tecla Windows e digite "rml".</span><span class="sxs-lookup"><span data-stu-id="f594c-341">In Windows Server 2012 [R2] and in Windows 8 and 8.1, open the start menu by clicking the Windows key, and type 'rml'.</span></span> <span data-ttu-id="f594c-342">Clique em "RML Cmd Prompt", que estará na lista de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f594c-342">Click on "RML Cmd Prompt", which will be in the list of search results.</span></span>  
  
 <span data-ttu-id="f594c-343">Verifique se o prompt de comando está localizado na pasta de instalação Utilitários de RML.</span><span class="sxs-lookup"><span data-stu-id="f594c-343">Ensure that the command prompt is located in the RML Utilities installation folder.</span></span> <span data-ttu-id="f594c-344">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-344">For example:</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP01.jpg)  
  
 <span data-ttu-id="f594c-345">As opções de linha de comando para ostress podem ser vista simplesmente ao executar ostress.exe sem opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f594c-345">The command-line options for ostress can be seen when simply running ostress.exe without any command-line options.</span></span> <span data-ttu-id="f594c-346">As opções principais a serem consideradas para executar ostress com este exemplo são:</span><span class="sxs-lookup"><span data-stu-id="f594c-346">The main options to consider for running ostress with this sample are:</span></span>  
  
-   <span data-ttu-id="f594c-347">-S nome da instância do [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à qual se conectar</span><span class="sxs-lookup"><span data-stu-id="f594c-347">-S name of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to</span></span>  
  
-   <span data-ttu-id="f594c-348">-E usar a autenticação do Windows para se conectar (padrão); Se você usar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a autenticação do, use as opções-você e-P para especificar o nome de usuário e a senha, respectivamente</span><span class="sxs-lookup"><span data-stu-id="f594c-348">-E use Windows authentication to connect (default); if you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, use the options -U and -P to specify the username and password, respectively</span></span>  
  
-   <span data-ttu-id="f594c-349">-d nome do banco de dados; para este exemplo, AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="f594c-349">-d name of the database, for this example AdventureWorks2014</span></span>  
  
-   <span data-ttu-id="f594c-350">-Q a instrução T-SQL a ser executada</span><span class="sxs-lookup"><span data-stu-id="f594c-350">-Q the T-SQL statement to be executed</span></span>  
  
-   <span data-ttu-id="f594c-351">-n número de conexões que processam cada arquivo de entrada/consulta</span><span class="sxs-lookup"><span data-stu-id="f594c-351">-n number of connections processing each input file/query</span></span>  
  
-   <span data-ttu-id="f594c-352">-r o número de iterações para cada conexão para executar cada arquivo de entrada/consulta</span><span class="sxs-lookup"><span data-stu-id="f594c-352">-r the number of iterations for each connection to execute each input file/query</span></span>  
  
### <a name="demo-workload"></a><span data-ttu-id="f594c-353">Carga de trabalho de demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-353">Demo Workload</span></span>  
 <span data-ttu-id="f594c-354">O procedimento armazenado principal usado na carga de trabalho de demonstração é Sales.usp_InsertSalesOrder_inmem/ondisk.</span><span class="sxs-lookup"><span data-stu-id="f594c-354">The main stored procedure used in the demo workload is Sales.usp_InsertSalesOrder_inmem/ondisk.</span></span> <span data-ttu-id="f594c-355">O script a seguir cria um parâmetro com valor de tabela (TVP) com dados de exemplo, e chama o procedimento para inserir um pedido de vendas com 5 itens de linha.</span><span class="sxs-lookup"><span data-stu-id="f594c-355">The script in the below constructs a table-valued parameter (TVP) with sample data, and calls the procedure to insert a sales order with 5 line items.</span></span>  
  
 <span data-ttu-id="f594c-356">A ferramenta ostress é usada para executar as chamadas de procedimento armazenado em paralelo, para simular os clientes que inserem pedidos de vendas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f594c-356">The ostress tool is used to execute the stored procedure calls in parallel, to simulate clients inserting sales orders concurrently.</span></span>  
  
 <span data-ttu-id="f594c-357">Redefinir a demonstração após cada verificação de estresse executando o Demo.usp_DemoReset.</span><span class="sxs-lookup"><span data-stu-id="f594c-357">Reset the demo after each stress run executing Demo.usp_DemoReset.</span></span> <span data-ttu-id="f594c-358">Este procedimento exclui as linhas nas tabelas com otimização de memória, trunca as tabelas baseadas em disco e executa um ponto de verificação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f594c-358">This procedure deletes the rows in the memory-optimized tables, truncates the disk-based tables, and executes a database checkpoint.</span></span>  
  
 <span data-ttu-id="f594c-359">O seguinte script é executado simultaneamente para simular uma carga de trabalho de processamento de pedido de vendas:</span><span class="sxs-lookup"><span data-stu-id="f594c-359">The following script is executed concurrently to simulate a sales order processing workload:</span></span>  
  
```  
DECLARE   
      @i int = 0,   
      @od Sales.SalesOrderDetailType_inmem,   
      @SalesOrderID int,   
      @DueDate datetime2 = sysdatetime(),   
      @CustomerID int = rand() * 8000,   
      @BillToAddressID int = rand() * 10000,   
      @ShipToAddressID int = rand() * 10000,   
      @ShipMethodID int = (rand() * 5) + 1;   
  
INSERT INTO @od   
SELECT OrderQty, ProductID, SpecialOfferID   
FROM Demo.DemoSalesOrderDetailSeed   
WHERE OrderID= cast((rand()*106) + 1 as int);   
  
WHILE (@i < 20)   
BEGIN;   
      EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od;   
      SET @i += 1   
END  
  
```  
  
 <span data-ttu-id="f594c-360">Com esse script, cada pedido de exemplo criado é inserido 20 vezes, com 20 procedimentos armazenados executados em um loop WHILE.</span><span class="sxs-lookup"><span data-stu-id="f594c-360">With this script, each sample order that is constructed is inserted 20 times, through 20 stored procedures executed in a WHILE loop.</span></span> <span data-ttu-id="f594c-361">O loop é usado para considerar o fato de que o banco de dados é usado para criar o pedido de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f594c-361">The loop is used to account for the fact that the database is used to construct the sample order.</span></span> <span data-ttu-id="f594c-362">Em ambientes de produção típicos, o aplicativo da camada intermediária criará o pedido de vendas a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="f594c-362">In typical production environments, the mid-tier application will construct the sales order to be inserted.</span></span>  
  
 <span data-ttu-id="f594c-363">O script anterior insere pedidos de vendas em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="f594c-363">The above script inserts sales orders into memory-optimized tables.</span></span> <span data-ttu-id="f594c-364">O script para inserir pedidos de vendas em tabelas baseadas em disco é derivado substituindo as duas ocorrências de "_inmem" por "_ondisk".</span><span class="sxs-lookup"><span data-stu-id="f594c-364">The script to insert sales orders into disk-based tables is derived by replacing the two occurrences of '_inmem' with '_ondisk'.</span></span>  
  
 <span data-ttu-id="f594c-365">Usaremos a ferramenta ostress para executar os scripts através de várias conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="f594c-365">We will use the ostress tool to execute the scripts using several concurrent connections.</span></span> <span data-ttu-id="f594c-366">Usaremos o parâmetro "-n" para controlar o número de conexões e o parâmetro "r" para controlar quantas vezes o script é executado em cada conexão.</span><span class="sxs-lookup"><span data-stu-id="f594c-366">We will use the parameter '-n' to control the number of connections, and the parameter 'r' to control how many times the script is executed on each connection.</span></span>  
  
#### <a name="functional-validation-of-the-workload"></a><span data-ttu-id="f594c-367">Validação funcional da carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="f594c-367">Functional Validation of the Workload</span></span>  
 <span data-ttu-id="f594c-368">Para verificar se tudo funciona, começaremos com um teste de exemplo, usando 10 conexões simultâneas e cinco iterações, inserindo um total de 10 \* 5 \* 20 = 1000 de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f594c-368">To verify everything works, we will start with a sample test, using 10 concurrent connects and 5 iterations, inserting a total of 10 \* 5 \* 20 = 1000 sales order.</span></span>  
  
 <span data-ttu-id="f594c-369">Com o comando a seguir, supomos que a instância padrão é usada no computador local.</span><span class="sxs-lookup"><span data-stu-id="f594c-369">With the below command we assume using the default instance on the local machine.</span></span> <span data-ttu-id="f594c-370">Se você estiver usando uma instância nomeada ou um servidor remoto, altere o nome do servidor em conformidade, usando o parâmetro -S.</span><span class="sxs-lookup"><span data-stu-id="f594c-370">If you are using a named instance or using a remote server, change the server name accordingly, using the parameter -S.</span></span>  
  
 <span data-ttu-id="f594c-371">Insira 1000 pedidos de vendas em tabelas com otimização de memória, usando o seguinte comando no Prompt Cmd RML:</span><span class="sxs-lookup"><span data-stu-id="f594c-371">Insert 1000 sales orders in memory-optimized tables use the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="f594c-372">Clique no botão Copiar para copiar o comando, e cole-o no prompt de comando Utilitários de RML.</span><span class="sxs-lookup"><span data-stu-id="f594c-372">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="f594c-373">Se tudo funcionar conforme esperado, a janela de comando terá a aparência a seguir.</span><span class="sxs-lookup"><span data-stu-id="f594c-373">If everything works as expected, your command window will look similar to the following.</span></span> <span data-ttu-id="f594c-374">Mensagens de erro não são esperadas.</span><span class="sxs-lookup"><span data-stu-id="f594c-374">Error messages are not expected.</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP02.jpg)  
  
 <span data-ttu-id="f594c-375">Valide que a carga de trabalho também funciona conforme esperado para tabelas baseadas em disco, executando o seguinte comando no Prompt Cmd RML:</span><span class="sxs-lookup"><span data-stu-id="f594c-375">Validate that also the workload functions as expected for disk-based tables by running the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="f594c-376">Clique no botão Copiar para copiar o comando, e cole-o no prompt de comando Utilitários de RML.</span><span class="sxs-lookup"><span data-stu-id="f594c-376">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
#### <a name="running-the-workload"></a><span data-ttu-id="f594c-377">Executando a carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="f594c-377">Running the Workload</span></span>  
 <span data-ttu-id="f594c-378">Para testar na escala, inserimos 10 milhões de pedidos de vendas, usando 100 conexões.</span><span class="sxs-lookup"><span data-stu-id="f594c-378">To test at scale we insert 10 million sales orders, using 100 connections.</span></span> <span data-ttu-id="f594c-379">Esse teste é executado de forma razoável em um servidor modesto (por exemplo, 8 núcleos físicos, 16 núcleos lógicos), e o armazenamento básico de SSD para o log.</span><span class="sxs-lookup"><span data-stu-id="f594c-379">This test performs reasonably on a modest server (e.g., 8 physical, 16 logical cores), and basic SSD storage for the log.</span></span> <span data-ttu-id="f594c-380">Se o teste não for bem-executado no hardware, verifique a seção [Solução de problemas em testes com execução lenta](#Troubleshootingslow-runningtests). Se desejar reduzir o nível de estresse nesse teste, diminua o número de conexões, alterando o parâmetro "-n".</span><span class="sxs-lookup"><span data-stu-id="f594c-380">If the test does not perform well on your hardware, take look at the Section [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).If you want to reduce the level of stress for this test, lower the number of connections by changing the parameter '-n'.</span></span> <span data-ttu-id="f594c-381">Por exemplo, para diminuir a contagem de conexões para 40, altere o parâmetro "-n100" para "-n40".</span><span class="sxs-lookup"><span data-stu-id="f594c-381">For example to lower the connection count to 40, change the parameter '-n100' to '-n40'.</span></span>  
  
 <span data-ttu-id="f594c-382">Como medida de desempenho da carga de trabalho, usamos o tempo decorrido conforme relatado por ostress.exe após executar a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f594c-382">As a performance measure for the workload we use the elapsed time as reported by ostress.exe after running the workload.</span></span>  
  
##### <a name="memory-optimized-tables"></a><span data-ttu-id="f594c-383">Tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-383">Memory-optimized tables</span></span>  
 <span data-ttu-id="f594c-384">Começaremos executando a carga de trabalho em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="f594c-384">We will start by running the workload on memory-optimized tables.</span></span> <span data-ttu-id="f594c-385">O comando a seguir abre 100 threads, cada um executado para 5.000 iterações.</span><span class="sxs-lookup"><span data-stu-id="f594c-385">The following command opens 100 threads, each running for 5,000 iterations.</span></span>  <span data-ttu-id="f594c-386">Cada iteração insere 20 pedidos de vendas em transações separadas.</span><span class="sxs-lookup"><span data-stu-id="f594c-386">Each iteration inserts 20 sales orders in separate transactions.</span></span> <span data-ttu-id="f594c-387">Há 20 inserções por iteração para compensar o fato de que o banco de dados é usado para gerar os dados a serem inseridos.</span><span class="sxs-lookup"><span data-stu-id="f594c-387">There are 20 inserts per iteration to compensate for the fact that the database is used to generate the data to be inserted.</span></span> <span data-ttu-id="f594c-388">Isso gera um total de 20 \* 5.000 \* 100 = 10.000.000 inserções de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-388">This yield a total of 20 \* 5,000 \* 100 = 10,000,000 sales order inserts.</span></span>  
  
 <span data-ttu-id="f594c-389">Abra o Prompt Cmd RML e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f594c-389">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="f594c-390">Clique no botão Copiar para copiar o comando, e cole-o no prompt de comando Utilitários de RML.</span><span class="sxs-lookup"><span data-stu-id="f594c-390">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="f594c-391">Em um servidor de teste com um número total de 8 núcleos físicos (16 lógicos), isso levou 2 minutos e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="f594c-391">On one test server with a total number of 8 physical (16 logical) cores, this took 2 minutes and 5 seconds.</span></span> <span data-ttu-id="f594c-392">Em um segundo servidor de teste com 24 núcleos físicos (48 lógicos), isso levou 1 minuto e 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="f594c-392">On a second test server with 24 physical (48 logical) cores, this took 1 minute and 0 seconds.</span></span>  
  
 <span data-ttu-id="f594c-393">Observe a utilização da CPU enquanto a carga de trabalho está em execução. Use, por exemplo, o gerenciador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="f594c-393">Observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="f594c-394">Você verá que quase 100% da CPU é utilizada.</span><span class="sxs-lookup"><span data-stu-id="f594c-394">You will see that CPU utilization is close to 100%.</span></span> <span data-ttu-id="f594c-395">Se esse não é o caso, você tem um gargalo de E/S de log. Consulte também [Solução de problemas em testes com execução lenta](#Troubleshootingslow-runningtests).</span><span class="sxs-lookup"><span data-stu-id="f594c-395">If this is not the case, you have a log IO bottleneck see also [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).</span></span>  
  
##### <a name="disk-based-tables"></a><span data-ttu-id="f594c-396">Tabelas baseadas em disco</span><span class="sxs-lookup"><span data-stu-id="f594c-396">Disk-based tables</span></span>  
 <span data-ttu-id="f594c-397">O comando a seguir executará a carga de trabalho em tabelas baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="f594c-397">The following command will run the workload on disk-based tables.</span></span> <span data-ttu-id="f594c-398">Observe que essa carga de trabalho pode demorar um pouco para ser executada, o que em grande parte se deve a uma contenção de trava no sistema.</span><span class="sxs-lookup"><span data-stu-id="f594c-398">Note that this workload may take a while to execute, which is largely due to latch contention in the system.</span></span> <span data-ttu-id="f594c-399">A tabela com otimização de memória é livre de travas e, assim, não tem esse problema.</span><span class="sxs-lookup"><span data-stu-id="f594c-399">Memory-optimized table are latch-free and thus do not suffer from this problem.</span></span>  
  
 <span data-ttu-id="f594c-400">Abra o Prompt Cmd RML e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f594c-400">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="f594c-401">Clique no botão Copiar para copiar o comando, e cole-o no prompt de comando Utilitários de RML.</span><span class="sxs-lookup"><span data-stu-id="f594c-401">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="f594c-402">Em um servidor de teste com um número total de 8 núcleos físicos (16 lógicos), isso levou 41 minutos e 25 segundos.</span><span class="sxs-lookup"><span data-stu-id="f594c-402">On one test server with a total number of 8 physical (16 logical) cores, this took 41 minutes and 25 seconds.</span></span> <span data-ttu-id="f594c-403">Em um segundo servidor de teste com 24 núcleos físicos (48 lógicos), isso levou 52 minutos e 16 segundos.</span><span class="sxs-lookup"><span data-stu-id="f594c-403">On a second test server with 24 physical (48 logical) cores, this took 52 minutes and 16 seconds.</span></span>  
  
 <span data-ttu-id="f594c-404">O fator principal na diferença de desempenho entre tabelas com otimização de memória e tabelas baseadas em disco nesse teste é o fato de que, ao usar tabelas baseadas em disco, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não pode fazer uso total da CPU.</span><span class="sxs-lookup"><span data-stu-id="f594c-404">The main factor in the performance difference between memory-optimized tables and disk-based tables in this test is the fact that when using disk-based tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot not fully utilize the CPU.</span></span> <span data-ttu-id="f594c-405">A razão é a contenção de trava: as transações simultâneas estão tentando gravar na mesma página de dados; as travas são usadas para garantir que somente uma transação de cada vez possa gravar em uma página.</span><span class="sxs-lookup"><span data-stu-id="f594c-405">The reason is latch contention: concurrent transactions are attempting to write to the same data page; latches are used to ensure only one transaction at a time can write to a page.</span></span> <span data-ttu-id="f594c-406">O mecanismo [!INCLUDE[hek_2](../includes/hek-2-md.md)] é livre de travas, e as linhas de dados não são organizadas em páginas.</span><span class="sxs-lookup"><span data-stu-id="f594c-406">The [!INCLUDE[hek_2](../includes/hek-2-md.md)] engine is latch-free, and data rows are not organized in pages.</span></span> <span data-ttu-id="f594c-407">Assim, as transações simultâneas não bloqueiam as inserções umas das outras, permitindo, portanto, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizar totalmente a CPU.</span><span class="sxs-lookup"><span data-stu-id="f594c-407">Thus, concurrent transactions do not block each other's inserts, thus enabling [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to fully utilize the CPU.</span></span>  
  
 <span data-ttu-id="f594c-408">Você pode observar a utilização da CPU enquanto a carga de trabalho está em execução. Use, por exemplo, o gerenciador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="f594c-408">You can observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="f594c-409">Note que, em tabelas baseadas em disco, a utilização da CPU é bem inferior a 100%.</span><span class="sxs-lookup"><span data-stu-id="f594c-409">You will see with disk-based tables the CPU utilization is far from 100%.</span></span> <span data-ttu-id="f594c-410">Em uma configuração de teste com 16 processadores lógicos, a utilização fica em torno de 24%.</span><span class="sxs-lookup"><span data-stu-id="f594c-410">On a test configuration with 16 logical processors, the utilization would hover around 24%.</span></span>  
  
 <span data-ttu-id="f594c-411">Opcionalmente, você pode exibir o número de esperas de trava por segundo usando o Monitor de Desempenho, com o contador de desempenho "\SQL Server:Latches\Latch Waits/sec".</span><span class="sxs-lookup"><span data-stu-id="f594c-411">Optionally, you can view the number of latch waits per second using Performance Monitor, with the performance counter '\SQL Server:Latches\Latch Waits/sec'.</span></span>  
  
#### <a name="resetting-the-demo"></a><span data-ttu-id="f594c-412">Redefinindo a demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-412">Resetting the demo</span></span>  
 <span data-ttu-id="f594c-413">Para redefinir a demonstração, abra o Prompt Cmd RML e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f594c-413">To reset the demo, open the RML Cmd Prompt, and execute the following command:</span></span>  
  
```  
ostress.exe -S. -E -dAdventureWorks2014 -Q"EXEC Demo.usp_DemoReset"  
```  
  
 <span data-ttu-id="f594c-414">Dependendo do hardware, isso pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="f594c-414">Depending on the hardware this may take a few minutes to run.</span></span>  
  
 <span data-ttu-id="f594c-415">Recomendamos uma redefinição após cada demonstração executada.</span><span class="sxs-lookup"><span data-stu-id="f594c-415">We recommend a reset after every demo run.</span></span> <span data-ttu-id="f594c-416">Como essa carga de trabalho é somente de inserção, cada execução consumirá mais memória e, portanto, uma redefinição é necessária para evitar ficar sem memória.</span><span class="sxs-lookup"><span data-stu-id="f594c-416">Because this workload is insert-only, each run will consume more memory, and thus a reset is required to prevent running out of memory.</span></span> <span data-ttu-id="f594c-417">A quantidade de memória consumida após uma execução é discutida na seção [Utilização de memória após executar a carga de trabalho](#Memoryutilizationafterrunningtheworkload).</span><span class="sxs-lookup"><span data-stu-id="f594c-417">The amount of memory consumed after a run is discussed in Section [Memory utilization after running the workload](#Memoryutilizationafterrunningtheworkload).</span></span>  
  
###  <a name="troubleshooting-slow-running-tests"></a><a name="Troubleshootingslow-runningtests"></a> <span data-ttu-id="f594c-418">Solução de problemas em testes com execução lenta</span><span class="sxs-lookup"><span data-stu-id="f594c-418">Troubleshooting slow-running tests</span></span>  
 <span data-ttu-id="f594c-419">Os resultados de testes variam de acordo com o hardware, e também com o nível de simultaneidade usado na execução do teste.</span><span class="sxs-lookup"><span data-stu-id="f594c-419">Test results will typically vary with hardware, and also the level of concurrency used in the test run.</span></span> <span data-ttu-id="f594c-420">Alguns itens a serem pesquisados se os resultados não forem os esperados:</span><span class="sxs-lookup"><span data-stu-id="f594c-420">A couple of things to look for if the results are not as expected:</span></span>  
  
-   <span data-ttu-id="f594c-421">Número de transações simultâneas: ao executar a carga de trabalho em um único thread, o ganho de desempenho com [!INCLUDE[hek_2](../includes/hek-2-md.md)] provavelmente será menor que 2X.</span><span class="sxs-lookup"><span data-stu-id="f594c-421">Number of concurrent transactions: When running the workload on a single thread, performance gain with [!INCLUDE[hek_2](../includes/hek-2-md.md)] will likely be less than 2X.</span></span> <span data-ttu-id="f594c-422">A contenção de trava se torna um grande problema apenas se há um nível alto de simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="f594c-422">Latch contention is only a big problem if there is a high level of concurrency.</span></span>  
  
-   <span data-ttu-id="f594c-423">Número baixo de núcleos disponíveis para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: isso significa que haverá um nível baixo de simultaneidade no sistema, pois a quantidade de transações executadas simultaneamente equivale ao número de núcleos disponíveis para o SQL.</span><span class="sxs-lookup"><span data-stu-id="f594c-423">Low number of cores available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: This means there will be a low level of concurrency in the system, as there can only be as many concurrently executing transactions as there are cores available to SQL.</span></span>  
  
    -   <span data-ttu-id="f594c-424">Sintoma: se há alta utilização da CPU ao executar a carga de trabalho em tabelas baseadas em disco, isso significa não há muita contenção, apontando para uma falta de simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="f594c-424">Symptom: if the CPU utilization is high when running the workload on disk-based tables, this means there is not a lot of contention, pointing to a lack of concurrency.</span></span>  
  
-   <span data-ttu-id="f594c-425">Velocidade da unidade de log: se a unidade de log não consegue acompanhar o nível de taxa de transferência de transações no sistema, a carga de trabalho se torna um gargalo na E/S de log.</span><span class="sxs-lookup"><span data-stu-id="f594c-425">Speed of the log drive: If the log drive cannot keep up with the level of transaction throughput in the system, the workload becomes bottlenecked on log IO.</span></span> <span data-ttu-id="f594c-426">Embora o log seja mais eficiente com [!INCLUDE[hek_2](../includes/hek-2-md.md)], se a E/S de log é um gargalo, o ganho de desempenho potencial é limitado.</span><span class="sxs-lookup"><span data-stu-id="f594c-426">Although logging is more efficient with [!INCLUDE[hek_2](../includes/hek-2-md.md)], if log IO is a bottleneck, the potential performance gain is limited.</span></span>  
  
    -   <span data-ttu-id="f594c-427">Sintoma: caso quase 100% da CPU seja utilizada ou apresentar um pico de uso ao executar a carga de trabalho em tabelas com otimização de memória, talvez exista um gargalo de E/S de log.</span><span class="sxs-lookup"><span data-stu-id="f594c-427">Symptom: if the CPU utilization is not close to 100% or is very spiky when running the workload on memory-optimized tables, it is possible there is a log IO bottleneck.</span></span> <span data-ttu-id="f594c-428">Isso pode ser confirmado abrindo o Monitor de Recursos e examinando o comprimento da fila para a unidade de log.</span><span class="sxs-lookup"><span data-stu-id="f594c-428">This can be confirmed by opening Resource Monitor and looking at the queue length for the log drive.</span></span>  
  
##  <a name="memory-and-disk-space-utilization-in-the-sample"></a><a name="MemoryandDiskSpaceUtilizationintheSample"></a> <span data-ttu-id="f594c-429">Utilização de memória e espaço em disco na amostra</span><span class="sxs-lookup"><span data-stu-id="f594c-429">Memory and Disk Space Utilization in the Sample</span></span>  
 <span data-ttu-id="f594c-430">A seguir, descrevemos o que esperar em termos de utilização da memória e do espaço em disco para o banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f594c-430">In the below we describe what to expect in terms of memory and disk space utilization for the sample database.</span></span> <span data-ttu-id="f594c-431">Também mostramos os resultados observados em um servidor de teste com 16 núcleos lógicos.</span><span class="sxs-lookup"><span data-stu-id="f594c-431">We also show the results we have seen in on a test server with 16 logical cores.</span></span>  
  
###  <a name="memory-utilization-for-the-memory-optimized-tables"></a><a name="Memoryutilizationforthememory-optimizedtables"></a> <span data-ttu-id="f594c-432">Utilização de memória para as tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-432">Memory utilization for the memory-optimized tables</span></span>  
  
#### <a name="overall-utilization-of-the-database"></a><span data-ttu-id="f594c-433">Utilização geral do banco de dados</span><span class="sxs-lookup"><span data-stu-id="f594c-433">Overall utilization of the database</span></span>  
 <span data-ttu-id="f594c-434">A consulta a seguir pode ser usada para obter a utilização total de memória de [!INCLUDE[hek_2](../includes/hek-2-md.md)] no sistema.</span><span class="sxs-lookup"><span data-stu-id="f594c-434">The following query can be used to obtain the total memory utilization for [!INCLUDE[hek_2](../includes/hek-2-md.md)] in the system.</span></span>  
  
```  
SELECT type  
   , name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
 <span data-ttu-id="f594c-435">Instantâneo logo após a criação do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="f594c-435">Snapshot after the database has just been created:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="f594c-436">**tipo**</span><span class="sxs-lookup"><span data-stu-id="f594c-436">**type**</span></span>|<span data-ttu-id="f594c-437">**name**</span><span class="sxs-lookup"><span data-stu-id="f594c-437">**name**</span></span>|<span data-ttu-id="f594c-438">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-438">**pages_MB**</span></span>|  
|<span data-ttu-id="f594c-439">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-439">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-440">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-440">Default</span></span>|<span data-ttu-id="f594c-441">94</span><span class="sxs-lookup"><span data-stu-id="f594c-441">94</span></span>|  
|<span data-ttu-id="f594c-442">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-442">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-443">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="f594c-443">DB_ID_5</span></span>|<span data-ttu-id="f594c-444">877</span><span class="sxs-lookup"><span data-stu-id="f594c-444">877</span></span>|  
|<span data-ttu-id="f594c-445">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-445">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-446">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-446">Default</span></span>|<span data-ttu-id="f594c-447">0</span><span class="sxs-lookup"><span data-stu-id="f594c-447">0</span></span>|  
|<span data-ttu-id="f594c-448">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-448">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-449">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-449">Default</span></span>|<span data-ttu-id="f594c-450">0</span><span class="sxs-lookup"><span data-stu-id="f594c-450">0</span></span>|  
  
 <span data-ttu-id="f594c-451">Os administradores de memória padrão contêm estruturas de memória do sistema e são relativamente pequenos.</span><span class="sxs-lookup"><span data-stu-id="f594c-451">The default memory clerks contain system-wide memory structures and are relatively small.</span></span> <span data-ttu-id="f594c-452">O administrador de memória do banco de dados de usuário, nesse caso o banco de dados com ID 5, tem cerca de 900MB.</span><span class="sxs-lookup"><span data-stu-id="f594c-452">The memory clerk for the user database, in this case database with ID 5, is about 900MB.</span></span>  
  
#### <a name="memory-utilization-per-table"></a><span data-ttu-id="f594c-453">Utilização da memória por tabela</span><span class="sxs-lookup"><span data-stu-id="f594c-453">Memory utilization per table</span></span>  
 <span data-ttu-id="f594c-454">A seguinte consulta pode ser usada para fazer uma busca detalhada na utilização da memória das tabelas individuais e de seus índices:</span><span class="sxs-lookup"><span data-stu-id="f594c-454">The following query can be used to drill down into the memory utilization of the individual tables and their indexes:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
 <span data-ttu-id="f594c-455">O seguinte exemplo mostra os resultados dessa consulta para uma instalação atualizada do exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-455">The following shows the results of this query for a fresh installation of the sample:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="f594c-456">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="f594c-456">**Table Name**</span></span>|<span data-ttu-id="f594c-457">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="f594c-457">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="f594c-458">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="f594c-458">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="f594c-459">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-459">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="f594c-460">64</span><span class="sxs-lookup"><span data-stu-id="f594c-460">64</span></span>|<span data-ttu-id="f594c-461">3840</span><span class="sxs-lookup"><span data-stu-id="f594c-461">3840</span></span>|  
|<span data-ttu-id="f594c-462">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="f594c-462">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="f594c-463">1984</span><span class="sxs-lookup"><span data-stu-id="f594c-463">1984</span></span>|<span data-ttu-id="f594c-464">5504</span><span class="sxs-lookup"><span data-stu-id="f594c-464">5504</span></span>|  
|<span data-ttu-id="f594c-465">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-465">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="f594c-466">15316</span><span class="sxs-lookup"><span data-stu-id="f594c-466">15316</span></span>|<span data-ttu-id="f594c-467">663552</span><span class="sxs-lookup"><span data-stu-id="f594c-467">663552</span></span>|  
|<span data-ttu-id="f594c-468">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="f594c-468">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="f594c-469">64</span><span class="sxs-lookup"><span data-stu-id="f594c-469">64</span></span>|<span data-ttu-id="f594c-470">10432</span><span class="sxs-lookup"><span data-stu-id="f594c-470">10432</span></span>|  
|<span data-ttu-id="f594c-471">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-471">SpecialOffer_inmem</span></span>|<span data-ttu-id="f594c-472">3</span><span class="sxs-lookup"><span data-stu-id="f594c-472">3</span></span>|<span data-ttu-id="f594c-473">8192</span><span class="sxs-lookup"><span data-stu-id="f594c-473">8192</span></span>|  
|<span data-ttu-id="f594c-474">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-474">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="f594c-475">7168</span><span class="sxs-lookup"><span data-stu-id="f594c-475">7168</span></span>|<span data-ttu-id="f594c-476">147456</span><span class="sxs-lookup"><span data-stu-id="f594c-476">147456</span></span>|  
|<span data-ttu-id="f594c-477">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-477">Product_inmem</span></span>|<span data-ttu-id="f594c-478">124</span><span class="sxs-lookup"><span data-stu-id="f594c-478">124</span></span>|<span data-ttu-id="f594c-479">12352</span><span class="sxs-lookup"><span data-stu-id="f594c-479">12352</span></span>|  
  
 <span data-ttu-id="f594c-480">Como você pode observar, as tabelas são bem pequenas: SalesOrderHeader_inmem tem cerca de 7MB e SalesOrderDetail_inmem mede cerca de 15MB.</span><span class="sxs-lookup"><span data-stu-id="f594c-480">As you can see the tables are fairly small: SalesOrderHeader_inmem is about 7MB, and SalesOrderDetail_inmem is about 15MB in size.</span></span>  
  
 <span data-ttu-id="f594c-481">O que chama a atenção aqui é o tamanho da memória alocada para índices, comparado ao tamanho dos dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="f594c-481">What is striking here is the size of the memory allocated for indexes, compared to the size of the table data.</span></span> <span data-ttu-id="f594c-482">Isso ocorre porque os índices de hash no exemplo são dimensionados previamente para um tamanho maior de dados.</span><span class="sxs-lookup"><span data-stu-id="f594c-482">That is because the hash indexes in the sample are pre-sized for a larger data size.</span></span> <span data-ttu-id="f594c-483">Observe que os índices de hash têm um tamanho fixo e, assim, seu tamanho não aumentará conforme o tamanho dos dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="f594c-483">Note that hash indexes have a fixed size, and thus their size will not grow with the size of data in the table.</span></span>  
  
####  <a name="memory-utilization-after-running-the-workload"></a><a name="Memoryutilizationafterrunningtheworkload"></a> <span data-ttu-id="f594c-484">Utilização de memória após executar a carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="f594c-484">Memory utilization after running the workload</span></span>  
 <span data-ttu-id="f594c-485">Após a inserção de 10 milhões de pedidos de vendas, qualquer utilização de memória superior terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="f594c-485">After insert 10 million sales orders, the all-up memory utilization looks similar to the following:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="f594c-486">**tipo**</span><span class="sxs-lookup"><span data-stu-id="f594c-486">**type**</span></span>|<span data-ttu-id="f594c-487">**name**</span><span class="sxs-lookup"><span data-stu-id="f594c-487">**name**</span></span>|<span data-ttu-id="f594c-488">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-488">**pages_MB**</span></span>|  
|<span data-ttu-id="f594c-489">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-489">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-490">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-490">Default</span></span>|<span data-ttu-id="f594c-491">146</span><span class="sxs-lookup"><span data-stu-id="f594c-491">146</span></span>|  
|<span data-ttu-id="f594c-492">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-492">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-493">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="f594c-493">DB_ID_5</span></span>|<span data-ttu-id="f594c-494">7374</span><span class="sxs-lookup"><span data-stu-id="f594c-494">7374</span></span>|  
|<span data-ttu-id="f594c-495">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-495">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-496">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-496">Default</span></span>|<span data-ttu-id="f594c-497">0</span><span class="sxs-lookup"><span data-stu-id="f594c-497">0</span></span>|  
|<span data-ttu-id="f594c-498">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-498">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-499">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-499">Default</span></span>|<span data-ttu-id="f594c-500">0</span><span class="sxs-lookup"><span data-stu-id="f594c-500">0</span></span>|  
  
 <span data-ttu-id="f594c-501">Como você pode notar, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] está usando um pouco menos de 8GB para as tabelas e os índices com otimização de memória no banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f594c-501">As you can see, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is using a bit under 8GB for the memory-optimized tables and indexes in the sample database.</span></span>  
  
 <span data-ttu-id="f594c-502">Verificando o uso detalhado de memória pela tabela após a execução de um exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-502">Looking at the detailed memory usage per table after one example run:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="f594c-503">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="f594c-503">**Table Name**</span></span>|<span data-ttu-id="f594c-504">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="f594c-504">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="f594c-505">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="f594c-505">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="f594c-506">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-506">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="f594c-507">5113761</span><span class="sxs-lookup"><span data-stu-id="f594c-507">5113761</span></span>|<span data-ttu-id="f594c-508">663552</span><span class="sxs-lookup"><span data-stu-id="f594c-508">663552</span></span>|  
|<span data-ttu-id="f594c-509">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="f594c-509">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="f594c-510">64</span><span class="sxs-lookup"><span data-stu-id="f594c-510">64</span></span>|<span data-ttu-id="f594c-511">10368</span><span class="sxs-lookup"><span data-stu-id="f594c-511">10368</span></span>|  
|<span data-ttu-id="f594c-512">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-512">SpecialOffer_inmem</span></span>|<span data-ttu-id="f594c-513">2</span><span class="sxs-lookup"><span data-stu-id="f594c-513">2</span></span>|<span data-ttu-id="f594c-514">8192</span><span class="sxs-lookup"><span data-stu-id="f594c-514">8192</span></span>|  
|<span data-ttu-id="f594c-515">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-515">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="f594c-516">1575679</span><span class="sxs-lookup"><span data-stu-id="f594c-516">1575679</span></span>|<span data-ttu-id="f594c-517">147456</span><span class="sxs-lookup"><span data-stu-id="f594c-517">147456</span></span>|  
|<span data-ttu-id="f594c-518">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-518">Product_inmem</span></span>|<span data-ttu-id="f594c-519">111</span><span class="sxs-lookup"><span data-stu-id="f594c-519">111</span></span>|<span data-ttu-id="f594c-520">12032</span><span class="sxs-lookup"><span data-stu-id="f594c-520">12032</span></span>|  
|<span data-ttu-id="f594c-521">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="f594c-521">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="f594c-522">64</span><span class="sxs-lookup"><span data-stu-id="f594c-522">64</span></span>|<span data-ttu-id="f594c-523">3712</span><span class="sxs-lookup"><span data-stu-id="f594c-523">3712</span></span>|  
|<span data-ttu-id="f594c-524">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="f594c-524">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="f594c-525">1984</span><span class="sxs-lookup"><span data-stu-id="f594c-525">1984</span></span>|<span data-ttu-id="f594c-526">5504</span><span class="sxs-lookup"><span data-stu-id="f594c-526">5504</span></span>|  
  
 <span data-ttu-id="f594c-527">Podemos ver um total de aproximadamente 6,5 GB de dados.</span><span class="sxs-lookup"><span data-stu-id="f594c-527">We can see a total of about 6.5GB of data.</span></span> <span data-ttu-id="f594c-528">Observe que o tamanho dos índices nas tabelas SalesOrderHeader_inmem e SalesOrderDetail_inmem equivale ao tamanho dos índices antes de inserir os pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="f594c-528">Notice that the size of the indexes on the table SalesOrderHeader_inmem and SalesOrderDetail_inmem is the same as the size of the indexes before inserting the sales orders.</span></span> <span data-ttu-id="f594c-529">O tamanho do índice não foi alterado porque ambas as tabelas estão usando índices de hash, e os índices de hash são estáticos.</span><span class="sxs-lookup"><span data-stu-id="f594c-529">The index size did not change because both tables are using hash indexes, and hash indexes are static.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="f594c-530">Após a redefinição de demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-530">After demo reset</span></span>  
 <span data-ttu-id="f594c-531">O procedimento armazenado Demo.usp_DemoReset pode ser usado para redefinir a demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-531">The stored procedure Demo.usp_DemoReset can be used to reset the demo.</span></span> <span data-ttu-id="f594c-532">Ele exclui os dados nas tabelas SalesOrderHeader_inmem e SalesOrderDetail_inmem, e repropaga os dados das tabelas originais SalesOrderHeader e SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="f594c-532">It deletes the data in the tables SalesOrderHeader_inmem and SalesOrderDetail_inmem, and re-seeds the data from the original tables SalesOrderHeader and SalesOrderDetail.</span></span>  
  
 <span data-ttu-id="f594c-533">Agora, apesar de as linhas das tabelas terem sido excluídas, isso não significa que a memória é recuperada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f594c-533">Now, even though the rows in the tables have been deleted, this does not mean that memory is reclaimed immediately.</span></span> <span data-ttu-id="f594c-534">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] recupera a memória das linhas excluídas em tabelas com otimização de memória no plano de fundo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f594c-534">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] reclaims memory from deleted rows in memory-optimized tables in the background, as needed.</span></span> <span data-ttu-id="f594c-535">Note que, imediatamente após a redefinição da demonstração, sem a carga de trabalho transacional no sistema, a memória das linhas excluídas ainda não foi recuperada:</span><span class="sxs-lookup"><span data-stu-id="f594c-535">You will see that immediately after demo reset, with no transactional workload on the system, memory from deleted rows is not yet reclaimed:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="f594c-536">**tipo**</span><span class="sxs-lookup"><span data-stu-id="f594c-536">**type**</span></span>|<span data-ttu-id="f594c-537">**name**</span><span class="sxs-lookup"><span data-stu-id="f594c-537">**name**</span></span>|<span data-ttu-id="f594c-538">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-538">**pages_MB**</span></span>|  
|<span data-ttu-id="f594c-539">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-539">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-540">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-540">Default</span></span>|<span data-ttu-id="f594c-541">2261</span><span class="sxs-lookup"><span data-stu-id="f594c-541">2261</span></span>|  
|<span data-ttu-id="f594c-542">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-542">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-543">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="f594c-543">DB_ID_5</span></span>|<span data-ttu-id="f594c-544">7396</span><span class="sxs-lookup"><span data-stu-id="f594c-544">7396</span></span>|  
|<span data-ttu-id="f594c-545">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-545">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-546">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-546">Default</span></span>|<span data-ttu-id="f594c-547">0</span><span class="sxs-lookup"><span data-stu-id="f594c-547">0</span></span>|  
|<span data-ttu-id="f594c-548">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-548">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-549">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-549">Default</span></span>|<span data-ttu-id="f594c-550">0</span><span class="sxs-lookup"><span data-stu-id="f594c-550">0</span></span>|  
  
 <span data-ttu-id="f594c-551">Isso é esperado: a memória será recuperada quando a carga de trabalho transacional estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="f594c-551">This is expected: memory will be reclaimed when the transactional workload is running.</span></span>  
  
 <span data-ttu-id="f594c-552">Se você iniciar uma segunda execução da carga de trabalho de demonstração, notará que inicialmente a utilização da memória diminui, pois as linhas excluídas anteriormente são limpadas.</span><span class="sxs-lookup"><span data-stu-id="f594c-552">If you start a second run of the demo workload you will see the memory utilization decrease initially, as the previously deleted rows are cleaned up.</span></span> <span data-ttu-id="f594c-553">Em algum momento, o tamanho da memória aumentará novamente, até que a carga de trabalho seja concluída.</span><span class="sxs-lookup"><span data-stu-id="f594c-553">At some point the memory size will increase again, until the workload finishes.</span></span> <span data-ttu-id="f594c-554">Após inserir 10 milhões de linhas após a redefinição de demonstração, a utilização da memória será muito semelhante à utilização após a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="f594c-554">After inserting 10 million rows after demo reset, the memory utilization will be very similar to the utilization after the first run.</span></span> <span data-ttu-id="f594c-555">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-555">For example:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="f594c-556">**tipo**</span><span class="sxs-lookup"><span data-stu-id="f594c-556">**type**</span></span>|<span data-ttu-id="f594c-557">**name**</span><span class="sxs-lookup"><span data-stu-id="f594c-557">**name**</span></span>|<span data-ttu-id="f594c-558">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-558">**pages_MB**</span></span>|  
|<span data-ttu-id="f594c-559">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-559">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-560">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-560">Default</span></span>|<span data-ttu-id="f594c-561">1863</span><span class="sxs-lookup"><span data-stu-id="f594c-561">1863</span></span>|  
|<span data-ttu-id="f594c-562">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-562">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-563">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="f594c-563">DB_ID_5</span></span>|<span data-ttu-id="f594c-564">7390</span><span class="sxs-lookup"><span data-stu-id="f594c-564">7390</span></span>|  
|<span data-ttu-id="f594c-565">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-565">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-566">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-566">Default</span></span>|<span data-ttu-id="f594c-567">0</span><span class="sxs-lookup"><span data-stu-id="f594c-567">0</span></span>|  
|<span data-ttu-id="f594c-568">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="f594c-568">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="f594c-569">Padrão</span><span class="sxs-lookup"><span data-stu-id="f594c-569">Default</span></span>|<span data-ttu-id="f594c-570">0</span><span class="sxs-lookup"><span data-stu-id="f594c-570">0</span></span>|  
  
### <a name="disk-utilization-for-memory-optimized-tables"></a><span data-ttu-id="f594c-571">Utilização de disco para as tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="f594c-571">Disk utilization for memory-optimized tables</span></span>  
 <span data-ttu-id="f594c-572">O tamanho geral em disco para os arquivos de ponto de verificação de um banco de dados em determinado momento pode ser localizado usando a consulta:</span><span class="sxs-lookup"><span data-stu-id="f594c-572">The overall on-disk size for the checkpoint files of a database at a given time can be found using the query:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
  
```  
  
#### <a name="initial-state"></a><span data-ttu-id="f594c-573">Estado inicial</span><span class="sxs-lookup"><span data-stu-id="f594c-573">Initial state</span></span>  
 <span data-ttu-id="f594c-574">Quando o grupo de arquivos de exemplo e as tabelas com otimização de memória de exemplo são criados inicialmente, um número de arquivos de ponto de verificação são pré-criados e o sistema começa a preencher os arquivos – o número de arquivos de ponto de verificação pré-criados depende do número de processadores lógicos no sistema.</span><span class="sxs-lookup"><span data-stu-id="f594c-574">When the sample filegroup and sample memory-optimized tables are created initially, a number of checkpoint files are pre-created and the system starts filling the files - the number of checkpoint files pre-created depends on the number of logical processors in the system.</span></span> <span data-ttu-id="f594c-575">Como o exemplo é inicialmente muito pequeno, os arquivos pré-criados serão os mais vazios após a criação inicial.</span><span class="sxs-lookup"><span data-stu-id="f594c-575">As the sample is initially very small, the pre-created files will be mostly empty after initial create.</span></span>  
  
 <span data-ttu-id="f594c-576">O seguinte exemplo mostra o tamanho inicial em disco para o exemplo em um computador com 16 processadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="f594c-576">The following shows the initial on-disk size for the sample on a machine with 16 logical processors:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="f594c-577">**Tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-577">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="f594c-578">2312</span><span class="sxs-lookup"><span data-stu-id="f594c-578">2312</span></span>|  
  
 <span data-ttu-id="f594c-579">Como você pode observar, há uma discrepância grande entre o tamanho em disco dos arquivos de ponto de verificação, que é de 2,3 GB, e o tamanho real dos dados, que é em torno de 30 MB.</span><span class="sxs-lookup"><span data-stu-id="f594c-579">As you can see, there is a big discrepancy between the on-disk size of the checkpoint files, which is 2.3GB, and the actual data size, which is closer to 30MB.</span></span>  
  
 <span data-ttu-id="f594c-580">Levando em conta a origem da utilização do espaço em disco, você pode usar a seguinte consulta.</span><span class="sxs-lookup"><span data-stu-id="f594c-580">Looking closer at where the disk-space utilization comes from, you can use the following query.</span></span> <span data-ttu-id="f594c-581">O tamanho do disco retornado por esta consulta é aproximado para os arquivos com estado 5 (NECESSÁRIO PARA BACKUP/AD), 6 (EM TRANSIÇÃO PARA MARCA DE EXCLUSÃO) ou 7 (MARCA DE EXCLUSÃO).</span><span class="sxs-lookup"><span data-stu-id="f594c-581">The size on disk returned by this query is approximate for files with state in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE), or 7 (TOMBSTONE).</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
 <span data-ttu-id="f594c-582">Para o estado inicial do exemplo, o resultado terá a seguinte aparência para um servidor com 16 processadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="f594c-582">For the initial state of the sample, the result will look something like for a server with 16 logical processors:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="f594c-583">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-583">**state_desc**</span></span>|<span data-ttu-id="f594c-584">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-584">**file_type_desc**</span></span>|<span data-ttu-id="f594c-585">**contagem**</span><span class="sxs-lookup"><span data-stu-id="f594c-585">**count**</span></span>|<span data-ttu-id="f594c-586">**tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-586">**on-disk size MB**</span></span>|  
|<span data-ttu-id="f594c-587">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-587">PRECREATED</span></span>|<span data-ttu-id="f594c-588">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-588">DATA</span></span>|<span data-ttu-id="f594c-589">16</span><span class="sxs-lookup"><span data-stu-id="f594c-589">16</span></span>|<span data-ttu-id="f594c-590">2.048</span><span class="sxs-lookup"><span data-stu-id="f594c-590">2048</span></span>|  
|<span data-ttu-id="f594c-591">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-591">PRECREATED</span></span>|<span data-ttu-id="f594c-592">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-592">DELTA</span></span>|<span data-ttu-id="f594c-593">16</span><span class="sxs-lookup"><span data-stu-id="f594c-593">16</span></span>|<span data-ttu-id="f594c-594">128</span><span class="sxs-lookup"><span data-stu-id="f594c-594">128</span></span>|  
|<span data-ttu-id="f594c-595">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="f594c-595">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="f594c-596">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-596">DATA</span></span>|<span data-ttu-id="f594c-597">1</span><span class="sxs-lookup"><span data-stu-id="f594c-597">1</span></span>|<span data-ttu-id="f594c-598">128</span><span class="sxs-lookup"><span data-stu-id="f594c-598">128</span></span>|  
|<span data-ttu-id="f594c-599">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="f594c-599">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="f594c-600">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-600">DELTA</span></span>|<span data-ttu-id="f594c-601">1</span><span class="sxs-lookup"><span data-stu-id="f594c-601">1</span></span>|<span data-ttu-id="f594c-602">8</span><span class="sxs-lookup"><span data-stu-id="f594c-602">8</span></span>|  
  
 <span data-ttu-id="f594c-603">Como você pode ver, a maior parte do espaço é usado por dados e arquivos delta criados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f594c-603">As you can see, most of the space is used by precreated data and delta files.</span></span> <span data-ttu-id="f594c-604">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] criou previamente um par de arquivos (dados, delta) por processador lógico.</span><span class="sxs-lookup"><span data-stu-id="f594c-604">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pre-created one pair of (data, delta) files per logical processor.</span></span> <span data-ttu-id="f594c-605">Além disso, os arquivos de dados são dimensionados previamente em 128MB, e os arquivos delta em 8MB, para tornar a inserção de dados nesses arquivos mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="f594c-605">In addition, data files are pre-sized at 128MB, and delta files at 8MB, in order to make inserting data into these files more efficient.</span></span>  
  
 <span data-ttu-id="f594c-606">Os dados reais nas tabelas com otimização de memória estão no único arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="f594c-606">The actual data in the memory-optimized tables is in the single data file.</span></span>  
  
#### <a name="after-running-the-workload"></a><span data-ttu-id="f594c-607">Após executar a carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="f594c-607">After running the workload</span></span>  
 <span data-ttu-id="f594c-608">Após a execução de um único teste que insere 10 milhões de pedidos de vendas, o tamanho geral em disco tem a seguinte aparência (para um servidor de teste com 16 núcleos):</span><span class="sxs-lookup"><span data-stu-id="f594c-608">After a single test run that inserts 10 million sales orders, the overall on-disk size looks something like this (for a 16-core test server):</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="f594c-609">**Tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-609">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="f594c-610">8828</span><span class="sxs-lookup"><span data-stu-id="f594c-610">8828</span></span>|  
  
 <span data-ttu-id="f594c-611">O tamanho em disco é em torno de 9GB, um valor próximo ao tamanho dos dados na memória.</span><span class="sxs-lookup"><span data-stu-id="f594c-611">The on-disk size is close to 9GB, which comes close to the in-memory size of the data.</span></span>  
  
 <span data-ttu-id="f594c-612">Verificando melhor os tamanhos dos arquivos de ponto de verificação em vários estados:</span><span class="sxs-lookup"><span data-stu-id="f594c-612">Looking more closely at the sizes of the checkpoint files across the various states:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="f594c-613">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-613">**state_desc**</span></span>|<span data-ttu-id="f594c-614">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-614">**file_type_desc**</span></span>|<span data-ttu-id="f594c-615">**contagem**</span><span class="sxs-lookup"><span data-stu-id="f594c-615">**count**</span></span>|<span data-ttu-id="f594c-616">**tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-616">**on-disk size MB**</span></span>|  
|<span data-ttu-id="f594c-617">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-617">PRECREATED</span></span>|<span data-ttu-id="f594c-618">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-618">DATA</span></span>|<span data-ttu-id="f594c-619">16</span><span class="sxs-lookup"><span data-stu-id="f594c-619">16</span></span>|<span data-ttu-id="f594c-620">2.048</span><span class="sxs-lookup"><span data-stu-id="f594c-620">2048</span></span>|  
|<span data-ttu-id="f594c-621">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-621">PRECREATED</span></span>|<span data-ttu-id="f594c-622">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-622">DELTA</span></span>|<span data-ttu-id="f594c-623">16</span><span class="sxs-lookup"><span data-stu-id="f594c-623">16</span></span>|<span data-ttu-id="f594c-624">128</span><span class="sxs-lookup"><span data-stu-id="f594c-624">128</span></span>|  
|<span data-ttu-id="f594c-625">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="f594c-625">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="f594c-626">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-626">DATA</span></span>|<span data-ttu-id="f594c-627">1</span><span class="sxs-lookup"><span data-stu-id="f594c-627">1</span></span>|<span data-ttu-id="f594c-628">128</span><span class="sxs-lookup"><span data-stu-id="f594c-628">128</span></span>|  
|<span data-ttu-id="f594c-629">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="f594c-629">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="f594c-630">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-630">DELTA</span></span>|<span data-ttu-id="f594c-631">1</span><span class="sxs-lookup"><span data-stu-id="f594c-631">1</span></span>|<span data-ttu-id="f594c-632">8</span><span class="sxs-lookup"><span data-stu-id="f594c-632">8</span></span>|  
  
 <span data-ttu-id="f594c-633">Temos ainda 16 pares de arquivos pré-criados, prontos para uso pois os pontos de verificação estão fechados.</span><span class="sxs-lookup"><span data-stu-id="f594c-633">We still have 16 pairs of pre-created files, ready to go as checkpoints are closed.</span></span>  
  
 <span data-ttu-id="f594c-634">Há um par em construção, que é usado até que o ponto de verificação atual seja fechado.</span><span class="sxs-lookup"><span data-stu-id="f594c-634">There is one pair under construction, which is used until the current checkpoint is closed.</span></span> <span data-ttu-id="f594c-635">Junto com os arquivos de ponto de verificação ativos, isso representa em torno de 6,5 GB de utilização de disco para 6,5 GB de dados na memória.</span><span class="sxs-lookup"><span data-stu-id="f594c-635">Along with the active checkpoint files this gives about 6.5GB of disk utilization for 6.5GB of data in memory.</span></span> <span data-ttu-id="f594c-636">Lembre-se de que os índices não são mantidos em disco e, assim, o tamanho geral em disco é menor do que o tamanho da memória, nesse caso.</span><span class="sxs-lookup"><span data-stu-id="f594c-636">Recall that indexes are not persisted on disk, and thus the overall size on disk is smaller than the size in memory in this case.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="f594c-637">Após a redefinição de demonstração</span><span class="sxs-lookup"><span data-stu-id="f594c-637">After demo reset</span></span>  
 <span data-ttu-id="f594c-638">Após a redefinição de demonstração, o espaço em disco não é recuperado imediatamente se não há carga de trabalho transacional no sistema, e não há pontos de verificação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f594c-638">After demo reset, disk space is not reclaimed immediately if there is no transactional workload on the system, and there are not database checkpoints.</span></span> <span data-ttu-id="f594c-639">Para que os arquivos de ponto de verificação sejam executados em suas várias fases e acabem sendo descartados, é necessário que ocorram alguns pontos de verificação e eventos de truncamento de log, a fim de iniciar a mesclagem de arquivos de pontos de verificação, bem como a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="f594c-639">For checkpoint files to be moved through their various stages and eventually be discarded, a number of checkpoints and log truncation events need to happen, to initiate merge of checkpoint files, as well as to initiate garbage collection.</span></span> <span data-ttu-id="f594c-640">Isso ocorrerá automaticamente se você tiver uma carga de trabalho transacional no sistema [e fizer backups de log regulares, caso você esteja usando o modelo de recuperação completa], mas não quando o sistema estiver ocioso, como em um cenário de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-640">These will happen automatically if you have a transactional workload in the system [and take regular log backups, in case you are using the FULL recovery model], but not when the system is idle, as in a demo scenario.</span></span>  
  
 <span data-ttu-id="f594c-641">No exemplo, após a redefinição de demonstração, você verá algo semelhante a</span><span class="sxs-lookup"><span data-stu-id="f594c-641">In the example, after demo reset, you may see something like</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="f594c-642">**Tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-642">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="f594c-643">11839</span><span class="sxs-lookup"><span data-stu-id="f594c-643">11839</span></span>|  
  
 <span data-ttu-id="f594c-644">Com quase 12GB, isso é significativamente mais do que os 9GB que tínhamos antes da redefinição de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f594c-644">At nearly 12GB, this is significantly more than the 9GB we had before the demo reset.</span></span> <span data-ttu-id="f594c-645">Isso ocorre porque algumas mesclagens do arquivo de ponto de verificação foram iniciadas, mas alguns dos destinos de mesclagem ainda não foram instalados, e alguns dos arquivos de origem de mesclagem ainda não foram limpos, como podemos observar aqui:</span><span class="sxs-lookup"><span data-stu-id="f594c-645">This is because some checkpoint file merges have been started, but some of the merge targets have not yet been installed, and some of the merge source files have not yet been cleaned up, as can be seen from the following:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="f594c-646">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-646">**state_desc**</span></span>|<span data-ttu-id="f594c-647">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-647">**file_type_desc**</span></span>|<span data-ttu-id="f594c-648">**contagem**</span><span class="sxs-lookup"><span data-stu-id="f594c-648">**count**</span></span>|<span data-ttu-id="f594c-649">**tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-649">**on-disk size MB**</span></span>|  
|<span data-ttu-id="f594c-650">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-650">PRECREATED</span></span>|<span data-ttu-id="f594c-651">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-651">DATA</span></span>|<span data-ttu-id="f594c-652">16</span><span class="sxs-lookup"><span data-stu-id="f594c-652">16</span></span>|<span data-ttu-id="f594c-653">2.048</span><span class="sxs-lookup"><span data-stu-id="f594c-653">2048</span></span>|  
|<span data-ttu-id="f594c-654">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-654">PRECREATED</span></span>|<span data-ttu-id="f594c-655">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-655">DELTA</span></span>|<span data-ttu-id="f594c-656">16</span><span class="sxs-lookup"><span data-stu-id="f594c-656">16</span></span>|<span data-ttu-id="f594c-657">128</span><span class="sxs-lookup"><span data-stu-id="f594c-657">128</span></span>|  
|<span data-ttu-id="f594c-658">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="f594c-658">ACTIVE</span></span>|<span data-ttu-id="f594c-659">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-659">DATA</span></span>|<span data-ttu-id="f594c-660">38</span><span class="sxs-lookup"><span data-stu-id="f594c-660">38</span></span>|<span data-ttu-id="f594c-661">5152</span><span class="sxs-lookup"><span data-stu-id="f594c-661">5152</span></span>|  
|<span data-ttu-id="f594c-662">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="f594c-662">ACTIVE</span></span>|<span data-ttu-id="f594c-663">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-663">DELTA</span></span>|<span data-ttu-id="f594c-664">38</span><span class="sxs-lookup"><span data-stu-id="f594c-664">38</span></span>|<span data-ttu-id="f594c-665">1331</span><span class="sxs-lookup"><span data-stu-id="f594c-665">1331</span></span>|  
|<span data-ttu-id="f594c-666">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="f594c-666">MERGE TARGET</span></span>|<span data-ttu-id="f594c-667">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-667">DATA</span></span>|<span data-ttu-id="f594c-668">7</span><span class="sxs-lookup"><span data-stu-id="f594c-668">7</span></span>|<span data-ttu-id="f594c-669">896</span><span class="sxs-lookup"><span data-stu-id="f594c-669">896</span></span>|  
|<span data-ttu-id="f594c-670">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="f594c-670">MERGE TARGET</span></span>|<span data-ttu-id="f594c-671">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-671">DELTA</span></span>|<span data-ttu-id="f594c-672">7</span><span class="sxs-lookup"><span data-stu-id="f594c-672">7</span></span>|<span data-ttu-id="f594c-673">56</span><span class="sxs-lookup"><span data-stu-id="f594c-673">56</span></span>|  
|<span data-ttu-id="f594c-674">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="f594c-674">MERGED SOURCE</span></span>|<span data-ttu-id="f594c-675">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-675">DATA</span></span>|<span data-ttu-id="f594c-676">13</span><span class="sxs-lookup"><span data-stu-id="f594c-676">13</span></span>|<span data-ttu-id="f594c-677">1772</span><span class="sxs-lookup"><span data-stu-id="f594c-677">1772</span></span>|  
|<span data-ttu-id="f594c-678">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="f594c-678">MERGED SOURCE</span></span>|<span data-ttu-id="f594c-679">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-679">DELTA</span></span>|<span data-ttu-id="f594c-680">13</span><span class="sxs-lookup"><span data-stu-id="f594c-680">13</span></span>|<span data-ttu-id="f594c-681">455</span><span class="sxs-lookup"><span data-stu-id="f594c-681">455</span></span>|  
  
 <span data-ttu-id="f594c-682">Os destinos de mesclagem serão instalados e a origem mesclada será limpa à medida que a atividade transacional ocorrer no sistema.</span><span class="sxs-lookup"><span data-stu-id="f594c-682">Merge targets are installed and merged source are cleaned up as transactional activity happens in the system.</span></span>  
  
 <span data-ttu-id="f594c-683">Após uma segunda execução da carga de trabalho de demonstração, inserindo 10 milhões de pedidos de vendas após a redefinição de demonstração, você verá que os arquivos criados durante a primeira execução da carga de trabalho foram limpos.</span><span class="sxs-lookup"><span data-stu-id="f594c-683">After a second run of the demo workload, inserting 10 million sales orders after the demo reset, you will see that the files constructed during the first run of the workload have been cleaned up.</span></span> <span data-ttu-id="f594c-684">Se você executar a consulta anterior várias vezes enquanto a carga de trabalho estiver em execução, verá que os arquivos de ponto de verificação passarão por várias fases.</span><span class="sxs-lookup"><span data-stu-id="f594c-684">If you run the above query several times while the workload is running, you can see the checkpoint files make their way through the various stages.</span></span>  
  
 <span data-ttu-id="f594c-685">Após a segunda execução da carga de trabalho inserir 10 milhões de pedidos de vendas, você notará que a utilização de disco é bem semelhante, embora não necessariamente igual, à da primeira execução, pois o sistema é dinâmico por natureza.</span><span class="sxs-lookup"><span data-stu-id="f594c-685">After the second run of the workload insert 10 million sales orders you will see disk utilization very similar to, though not necessarily the same as after the first run, as the system is dynamic in nature.</span></span> <span data-ttu-id="f594c-686">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f594c-686">For example:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="f594c-687">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-687">**state_desc**</span></span>|<span data-ttu-id="f594c-688">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="f594c-688">**file_type_desc**</span></span>|<span data-ttu-id="f594c-689">**contagem**</span><span class="sxs-lookup"><span data-stu-id="f594c-689">**count**</span></span>|<span data-ttu-id="f594c-690">**tamanho em disco em MB**</span><span class="sxs-lookup"><span data-stu-id="f594c-690">**on-disk size MB**</span></span>|  
|<span data-ttu-id="f594c-691">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-691">PRECREATED</span></span>|<span data-ttu-id="f594c-692">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-692">DATA</span></span>|<span data-ttu-id="f594c-693">16</span><span class="sxs-lookup"><span data-stu-id="f594c-693">16</span></span>|<span data-ttu-id="f594c-694">2.048</span><span class="sxs-lookup"><span data-stu-id="f594c-694">2048</span></span>|  
|<span data-ttu-id="f594c-695">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="f594c-695">PRECREATED</span></span>|<span data-ttu-id="f594c-696">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-696">DELTA</span></span>|<span data-ttu-id="f594c-697">16</span><span class="sxs-lookup"><span data-stu-id="f594c-697">16</span></span>|<span data-ttu-id="f594c-698">128</span><span class="sxs-lookup"><span data-stu-id="f594c-698">128</span></span>|  
|<span data-ttu-id="f594c-699">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="f594c-699">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="f594c-700">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-700">DATA</span></span>|<span data-ttu-id="f594c-701">2</span><span class="sxs-lookup"><span data-stu-id="f594c-701">2</span></span>|<span data-ttu-id="f594c-702">268</span><span class="sxs-lookup"><span data-stu-id="f594c-702">268</span></span>|  
|<span data-ttu-id="f594c-703">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="f594c-703">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="f594c-704">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-704">DELTA</span></span>|<span data-ttu-id="f594c-705">2</span><span class="sxs-lookup"><span data-stu-id="f594c-705">2</span></span>|<span data-ttu-id="f594c-706">16</span><span class="sxs-lookup"><span data-stu-id="f594c-706">16</span></span>|  
|<span data-ttu-id="f594c-707">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="f594c-707">ACTIVE</span></span>|<span data-ttu-id="f594c-708">DATA</span><span class="sxs-lookup"><span data-stu-id="f594c-708">DATA</span></span>|<span data-ttu-id="f594c-709">41</span><span class="sxs-lookup"><span data-stu-id="f594c-709">41</span></span>|<span data-ttu-id="f594c-710">5608</span><span class="sxs-lookup"><span data-stu-id="f594c-710">5608</span></span>|  
|<span data-ttu-id="f594c-711">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="f594c-711">ACTIVE</span></span>|<span data-ttu-id="f594c-712">DELTA</span><span class="sxs-lookup"><span data-stu-id="f594c-712">DELTA</span></span>|<span data-ttu-id="f594c-713">41</span><span class="sxs-lookup"><span data-stu-id="f594c-713">41</span></span>|<span data-ttu-id="f594c-714">328</span><span class="sxs-lookup"><span data-stu-id="f594c-714">328</span></span>|  
  
 <span data-ttu-id="f594c-715">Nesse caso, há dois pares de arquivos do ponto de verificação no estado "em construção", o que significa que vários pares de arquivos foram movidos para o estado "em construção", provavelmente devido ao nível alto de simultaneidade na carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f594c-715">In this case, there are two checkpoint file pairs in the 'under construction' state, which means multiple file pairs were moved to the 'under construction' state, likely due to the high level of concurrency in the workload.</span></span> <span data-ttu-id="f594c-716">Vários threads simultâneos exigiam um novo par de arquivos ao mesmo tempo e, portanto, moviam um par de "pré-criados" para "em construção".</span><span class="sxs-lookup"><span data-stu-id="f594c-716">Multiple concurrent threads required a new file pair at the same time, and thus moved a pair from 'precreated' to 'under construction'.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f594c-717">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f594c-717">See Also</span></span>  
 [<span data-ttu-id="f594c-718">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="f594c-718">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
