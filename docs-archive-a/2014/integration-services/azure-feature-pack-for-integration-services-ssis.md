---
title: Feature Pack do Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL11.SSIS.AZURE.F1
- SQL12.SSIS.AZURE.F1
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8bca2b4d3ce91f6010fbe01da836efd8a67ca6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678943"
---
# <a name="azure-feature-pack"></a><span data-ttu-id="3ea67-102">Feature Pack do Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-102">Azure Feature Pack</span></span>
<span data-ttu-id="3ea67-103">O Feature Pack do SSIS (SQL Server Integration Services) para Azure é uma extensão que oferece os componentes listados nesta página para o SSIS se conectar aos serviços do Azure, transferir dados entre o Azure e fontes de dados locais e processar dados armazenados no Azure.</span><span class="sxs-lookup"><span data-stu-id="3ea67-103">SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.</span></span>

## <a name="components-in-the-feature-pack"></a><span data-ttu-id="3ea67-104">Componentes no Feature Pack</span><span class="sxs-lookup"><span data-stu-id="3ea67-104">Components in the Feature Pack</span></span>
  
-   <span data-ttu-id="3ea67-105">Gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="3ea67-105">Connection Managers</span></span>  
  
    -   [<span data-ttu-id="3ea67-106">Gerenciador de conexões do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-106">Azure Storage Connection Manager</span></span>](connection-manager/azure-storage-connection-manager.md)  
  
    -   [<span data-ttu-id="3ea67-107">Gerenciador de Conexões da Assinatura do Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-107">Azure Subscription Connection Manager</span></span>](connection-manager/azure-subscription-connection-manager.md)  
    
    -   [<span data-ttu-id="3ea67-108">Gerenciador de conexões do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="3ea67-108">Azure Data Lake Store Connection Manager</span></span>](../../2014/integration-services/azure-data-lake-store-connection-manager.md)
    
    -   [<span data-ttu-id="3ea67-109">Gerenciador de Conexões do Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="3ea67-109">Azure Resource Manager Connection Manager</span></span>](../../2014/integration-services/azure-resource-manager-connection-manager.md)
    
    -   [<span data-ttu-id="3ea67-110">Gerenciador de Conexões do Microsoft Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="3ea67-110">Azure HDInsight Connection Manager</span></span>](../../2014/integration-services/azure-hdinsight-connection-manager.md)
  
-   <span data-ttu-id="3ea67-111">Tarefas</span><span class="sxs-lookup"><span data-stu-id="3ea67-111">Tasks</span></span>  
  
    -   [<span data-ttu-id="3ea67-112">Tarefa de Upload de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-112">Azure Blob Upload Task</span></span>](control-flow/azure-blob-upload-task.md)  
  
    -   [<span data-ttu-id="3ea67-113">Tarefa de Download do Blob do Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-113">Azure Blob Download Task</span></span>](control-flow/azure-blob-download-task.md)  
  
    -   [<span data-ttu-id="3ea67-114">Tarefa do Hive do Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="3ea67-114">Azure HDInsight Hive Task</span></span>](control-flow/azure-hdinsight-hive-task.md)  
  
    -   <span data-ttu-id="3ea67-115">[Tarefa de Pig de HDInsight do Azure](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="3ea67-115">[Azure HDInsight Pig Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span></span>
  
    -   [<span data-ttu-id="3ea67-116">Tarefa Criar Cluster do Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="3ea67-116">Azure HDInsight Create Cluster Task</span></span>](control-flow/azure-hdinsight-create-cluster-task.md)  
  
    -   [<span data-ttu-id="3ea67-117">Tarefa Excluir Cluster do Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="3ea67-117">Azure HDInsight Delete Cluster Task</span></span>](control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [<span data-ttu-id="3ea67-118">Tarefa de Upload do DW no SQL Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-118">Azure SQL DW Upload Task</span></span>](../../2014/integration-services/azure-sql-dw-upload-task.md)    
    
    -   [<span data-ttu-id="3ea67-119">Tarefa do sistema de arquivos do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="3ea67-119">Azure Data Lake Store File System Task</span></span>](control-flow/file-system-task.md)    
  
-   <span data-ttu-id="3ea67-120">Componentes de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="3ea67-120">Data Flow Components</span></span>  
  
    -   <span data-ttu-id="3ea67-121">[Fonte de Blobs do Azure](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="3ea67-121">[Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span></span>  
  
    -   [<span data-ttu-id="3ea67-122">Destino de Blob do Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-122">Azure Blob Destination</span></span>](data-flow/azure-blob-destination.md)  
    
    -   [<span data-ttu-id="3ea67-123">Fonte do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="3ea67-123">Azure Data Lake Store Source</span></span>](../../2014/integration-services/azure-data-lake-store-source.md)
    
    -   [<span data-ttu-id="3ea67-124">Destino do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="3ea67-124">Azure Data Lake Store Destination</span></span>](../../2014/integration-services/azure-data-lake-store-destination.md)
  
-   <span data-ttu-id="3ea67-125">Enumerador de blob do Azure & enumerador de arquivo ADLS.</span><span class="sxs-lookup"><span data-stu-id="3ea67-125">Azure Blob Enumerator & ADLS File Enumerator.</span></span> <span data-ttu-id="3ea67-126">Consulte [contêiner Loop Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="3ea67-126">See [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 
## <a name="download-the-feature-pack"></a><span data-ttu-id="3ea67-127">Baixe o Feature Pack</span><span class="sxs-lookup"><span data-stu-id="3ea67-127">Download the Feature Pack</span></span>  
<span data-ttu-id="3ea67-128">Baixe o SQL Server Integration Services (SSIS) Feature Pack para o Azure.</span><span class="sxs-lookup"><span data-stu-id="3ea67-128">Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.</span></span>  
  
-   [<span data-ttu-id="3ea67-129">Feature Pack Microsoft SQL Server 2014 Integration Services para o Azure</span><span class="sxs-lookup"><span data-stu-id="3ea67-129">Microsoft SQL Server 2014 Integration Services Feature Pack for Azure</span></span>](https://www.microsoft.com/download/details.aspx?id=47366)  

## <a name="prerequisites"></a><span data-ttu-id="3ea67-130">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3ea67-130">Prerequisites</span></span>  
<span data-ttu-id="3ea67-131">Você deve instalar os seguintes pré-requisitos antes de instalar este feature pack.</span><span class="sxs-lookup"><span data-stu-id="3ea67-131">You must install the following prerequisites before installing this feature pack.</span></span>  
  
-   <span data-ttu-id="3ea67-132">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="3ea67-132">SQL Server Integration Services</span></span>  
-   <span data-ttu-id="3ea67-133">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3ea67-133">.Net Framework 4.5</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="3ea67-134">Cenários</span><span class="sxs-lookup"><span data-stu-id="3ea67-134">Scenarios</span></span>  
  
### <a name="big-data-processing"></a><span data-ttu-id="3ea67-135">Processamento de Big Data</span><span class="sxs-lookup"><span data-stu-id="3ea67-135">Big Data Processing</span></span>  
 <span data-ttu-id="3ea67-136">Use o Conector do Azure para concluir o seguinte trabalho de processamento de Big Data:</span><span class="sxs-lookup"><span data-stu-id="3ea67-136">Use Azure Connector to complete following big data processing work:</span></span>  
  
1.  <span data-ttu-id="3ea67-137">Use a tarefa de upload de blobs do Azure para carregar dados de entrada para o armazenamento de blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="3ea67-137">Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.</span></span>  
  
2.  <span data-ttu-id="3ea67-138">Use a tarefa Criar Cluster do Azure HDInsight para criar um cluster do Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3ea67-138">Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster.</span></span> <span data-ttu-id="3ea67-139">Esta etapa é opcional se você quiser usar seu próprio cluster.</span><span class="sxs-lookup"><span data-stu-id="3ea67-139">This step is optional if you want to use your own cluster.</span></span>  
  
3.  <span data-ttu-id="3ea67-140">Use a tarefa Hive ou Pig do Azure HDInsight para invocar uma tarefa de Pig ou Hive no cluster do Azure HDInsight .</span><span class="sxs-lookup"><span data-stu-id="3ea67-140">Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.</span></span>  
  
4.  <span data-ttu-id="3ea67-141">Use a tarefa Excluir Cluster do Azure HDInsight para excluir o cluster do HDInsight após o uso, se você tiver criado um cluster de HDInsight sob demanda na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3ea67-141">Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.</span></span>  
  
5.  <span data-ttu-id="3ea67-142">Use a tarefa Download de Blob do Azure HDInsight para baixar dados de saída de Pig/Hive do armazenamento de blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="3ea67-142">Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="3ea67-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span><span class="sxs-lookup"><span data-stu-id="3ea67-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span></span>  
  
### <a name="cloud-data-archiving"></a><span data-ttu-id="3ea67-144">Arquivamento de dados em nuvem</span><span class="sxs-lookup"><span data-stu-id="3ea67-144">Cloud Data Archiving</span></span>  
 <span data-ttu-id="3ea67-145">Use o destino de blob do Azure em um pacote do SSIS para gravar dados de saída em um armazenamento de blobs do Azure ou use a fonte de blob do Azure para ler dados de um armazenamento de blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="3ea67-145">Use the Azure Blob Destination in an SSIS package to write output data to an Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="3ea67-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span><span class="sxs-lookup"><span data-stu-id="3ea67-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span></span>  
  
 <span data-ttu-id="3ea67-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span><span class="sxs-lookup"><span data-stu-id="3ea67-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span></span>  
  
 <span data-ttu-id="3ea67-148">E use o contêiner Loop Foreach com o enumerador de blob do Azure para processar dados em vários arquivos de blob.</span><span class="sxs-lookup"><span data-stu-id="3ea67-148">And use the Foreach Loop Container with Azure Blob Enumerator to process data in multiple bob files.</span></span>  
  
 <span data-ttu-id="3ea67-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span><span class="sxs-lookup"><span data-stu-id="3ea67-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span></span>  
  
  
