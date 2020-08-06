---
title: Tarefa do Pig do Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afppigtask.f1
- sql11.dts.designer.afppigtask.f1
ms.assetid: 26f34f64-f344-486e-9190-acf71aef29a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 214db5e83272b1fa70c9e70eef8f8b9a43bac095
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571502"
---
# <a name="azure-hdinsight-pig-task"></a><span data-ttu-id="dfc21-102">Tarefa de Pig de HDInsight do Azure</span><span class="sxs-lookup"><span data-stu-id="dfc21-102">Azure HDInsight Pig Task</span></span>
<span data-ttu-id="dfc21-103">Use a **Tarefa de Pig do Azure HDInsight** para executar o script do Pig em um cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="dfc21-103">Use the **Azure HDInsight Pig Task** to run Pig script on an Azure HDInsight cluster.</span></span>
     
<span data-ttu-id="dfc21-104">Para adicionar uma **Tarefa do Pig do Azure HDInsight**, arraste e solte-a no Designer do SSIS e clique duas vezes ou com o botão direito do mouse e clique em **Editar** para ver a caixa de diálogo **Editor de Tarefa do Pig do Azure HDInsight** a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfc21-104">To add an **Azure HDInsight Pig Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Pig Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="dfc21-105">A lista a seguir descreve os campos dessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="dfc21-105">The following list describes fields in this dialog box.</span></span>  
  
1.  <span data-ttu-id="dfc21-106">Para o campo **HDInsightConnection**, selecione um Gerenciador de Conexões do Azure HDInsight existente ou crie um novo que se refere ao cluster do Azure HDInsight usado para executar o script.</span><span class="sxs-lookup"><span data-stu-id="dfc21-106">For the **HDInsightConnection** field, select an existing Azure HDInsight Connection Manager or create a new one that refers to the Azure HDInsight cluster used to execute the script.</span></span>
  
2.  <span data-ttu-id="dfc21-107">Para o campo **AzureStorageConnection**, selecione um Gerenciador de Conexões do Armazenamento do Azure existente ou crie um novo que se refere à Conta de Armazenamento do Azure associada ao cluster.</span><span class="sxs-lookup"><span data-stu-id="dfc21-107">For the **AzureStorageConnection** field, select an existing Azure Storage Connection Manager or create a new one that refers to the Azure Storage Account associated with the cluster.</span></span> <span data-ttu-id="dfc21-108">Isso só é necessário se você deseja baixar os logs de erro e de saída de execução do script.</span><span class="sxs-lookup"><span data-stu-id="dfc21-108">This is only necessary if you want to download the script execution output and error logs.</span></span>
 
3.  <span data-ttu-id="dfc21-109">Para o campo **BlobContainer**, especifique o nome do contêiner de armazenamento associado ao cluster.</span><span class="sxs-lookup"><span data-stu-id="dfc21-109">For the **BlobContainer** field, specify the storage container name associated with the cluster.</span></span> <span data-ttu-id="dfc21-110">Isso só é necessário se você deseja baixar os logs de erro e de saída de execução do script.</span><span class="sxs-lookup"><span data-stu-id="dfc21-110">This is only necessary if you want to download the script execution output and error logs.</span></span>
  
4.  <span data-ttu-id="dfc21-111">Para o campo **LocalLogFolder**, especifique a pasta para a qual os logs de erro e de saída de execução do script serão baixados.</span><span class="sxs-lookup"><span data-stu-id="dfc21-111">For the **LocalLogFolder** field, specify the folder to which the script execution output and error logs will be downloaded to.</span></span> <span data-ttu-id="dfc21-112">Isso só é necessário se você deseja baixar os logs de erro e de saída de execução do script.</span><span class="sxs-lookup"><span data-stu-id="dfc21-112">This is only necessary if you want to download the script execution output and error logs.</span></span>   
  
5.  <span data-ttu-id="dfc21-113">Há duas maneiras de especificar o script do Pig a ser executado:</span><span class="sxs-lookup"><span data-stu-id="dfc21-113">There are two ways to specify the Pig script to execute:</span></span>
  
    1.  <span data-ttu-id="dfc21-114">**Script em linha**: especifique o campo **Script** digitando em linha o script a ser executado na caixa de diálogo **Inserir Script**.</span><span class="sxs-lookup"><span data-stu-id="dfc21-114">**In-line script**: Specify the **Script** field by typing in-line the script to execute in the **Enter Script** dialog box.</span></span>
  
    2.  <span data-ttu-id="dfc21-115">**Arquivo de script**: carregue o arquivo de script para o Armazenamento de Blobs do Azure e especifique o campo **BlobName**.</span><span class="sxs-lookup"><span data-stu-id="dfc21-115">**Script file**: Upload the script file to Azure Blob Storage and specify the **BlobName** field.</span></span> <span data-ttu-id="dfc21-116">Se o blob não estiver na conta de armazenamento padrão ou no contêiner associado ao cluster HDInsight, os campos **ExternalStorageAccountName** e **ExternalBlobContainer** deverão ser especificados.</span><span class="sxs-lookup"><span data-stu-id="dfc21-116">If the blob is not in the default storage account or container associated with the HDInsight cluster, the **ExternalStorageAccountName** and **ExternalBlobContainer** fields must be specified.</span></span> <span data-ttu-id="dfc21-117">Para um blob externo, verifique se ele está configurado como acessível ao público.</span><span class="sxs-lookup"><span data-stu-id="dfc21-117">For an external blob, make sure that it is configured as publicly accessible.</span></span>  
  
     <span data-ttu-id="dfc21-118">Se ambos estiverem especificados, o arquivo de script será usado e o script embutido será ignorado.</span><span class="sxs-lookup"><span data-stu-id="dfc21-118">If both are specified, script file will be used and the in-line script will be ignored.</span></span>
