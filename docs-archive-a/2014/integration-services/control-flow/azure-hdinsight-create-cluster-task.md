---
title: Tarefa Criar Cluster do Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpcreatecltask.f1
- sql11.dts.designer.afpcreatecltask.f1
ms.assetid: a8ec413a-38d3-45df-887e-6f5f4d9f8465
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4029e3a01cbcfe04be5f2879a9b60866bfc867a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679471"
---
# <a name="azure-hdinsight-create-cluster-task"></a><span data-ttu-id="85a53-102">Tarefa Criar Cluster do Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="85a53-102">Azure HDInsight Create Cluster Task</span></span>
<span data-ttu-id="85a53-103">A **Tarefa Criar Cluster do Azure HDInsight** permite que um pacote do SSIS crie um cluster do Azure HDInsight na assinatura e grupo de recursos do Azure especificados.</span><span class="sxs-lookup"><span data-stu-id="85a53-103">The **Azure HDInsight Create Cluster Task** enables an SSIS package to create an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]  
> - <span data-ttu-id="85a53-104">Criar um novo cluster HDInsight pode levar entre 10 e 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="85a53-104">Creating a new HDInsight cluster may take 10~20 minutes.</span></span>  
> - <span data-ttu-id="85a53-105">Há um custo associado à criação e execução de um cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-105">There is a cost associated with creating and running an Azure HDInsight cluster.</span></span> <span data-ttu-id="85a53-106">Consulte [Preços do HDInsight](https://azure.microsoft.com/pricing/details/hdinsight/) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="85a53-106">See [HDInsight Pricing](https://azure.microsoft.com/pricing/details/hdinsight/) for details.</span></span>  
  
<span data-ttu-id="85a53-107">Para adicionar uma **Tarefa Criar Cluster do Azure HDInsight**, arraste e solte-a no Designer SSIS e clique duas vezes ou, com o botão direito do mouse, clique em **Editar** para ver a caixa de diálogo **Editor de Tarefa Criar Cluster do Azure HDInsight** a seguir.</span><span class="sxs-lookup"><span data-stu-id="85a53-107">To add an **Azure HDInsight Create Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Create Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="85a53-108">A tabela a seguir fornece uma descrição para os campos nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="85a53-108">The following table provides a description of the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85a53-109">**Campo**</span><span class="sxs-lookup"><span data-stu-id="85a53-109">**Field**</span></span>|<span data-ttu-id="85a53-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="85a53-110">**Description**</span></span>|  
|<span data-ttu-id="85a53-111">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="85a53-111">AzureResourceManagerConnection</span></span>|<span data-ttu-id="85a53-112">Selecione um Gerenciador de Conexão do Azure Resource Manager existente ou crie um novo que será usado para criar o cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-112">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to create the HDInsight cluster.</span></span>|  
|<span data-ttu-id="85a53-113">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="85a53-113">AzureStorageConnection</span></span>|<span data-ttu-id="85a53-114">Selecione um Gerenciador de conexão de armazenamento do Azure existente ou crie um novo, relacionado a uma conta de armazenamento do Azure, que será associado com o cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-114">Select an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account that will be associated with the HDInsight cluster.</span></span>|
|<span data-ttu-id="85a53-115">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="85a53-115">SubscriptionId</span></span>|<span data-ttu-id="85a53-116">Especifique a ID da assinatura na qual o cluster HDInsight será criado.</span><span class="sxs-lookup"><span data-stu-id="85a53-116">Specify the ID of the subscription the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="85a53-117">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="85a53-117">ResourceGroup</span></span>|<span data-ttu-id="85a53-118">Especifique o grupo de recursos do Azure no qual o cluster HDInsight será criado.</span><span class="sxs-lookup"><span data-stu-id="85a53-118">Specify the Azure resource group the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="85a53-119">Localização</span><span class="sxs-lookup"><span data-stu-id="85a53-119">Location</span></span>|<span data-ttu-id="85a53-120">Especifique o local do cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-120">Specify the location of the HDInsight cluster.</span></span> <span data-ttu-id="85a53-121">O cluster deve ser criado no mesmo local que a conta de Armazenamento do Azure especificada.</span><span class="sxs-lookup"><span data-stu-id="85a53-121">The cluster must be created in the same location as the Azure Storage Account specified.</span></span>|  
|<span data-ttu-id="85a53-122">ClusterName</span><span class="sxs-lookup"><span data-stu-id="85a53-122">ClusterName</span></span>|<span data-ttu-id="85a53-123">Especifique um nome para o cluster HDInsight que será criado.</span><span class="sxs-lookup"><span data-stu-id="85a53-123">Specify a name for the HDInsight cluster to be created.</span></span>|  
|<span data-ttu-id="85a53-124">clusterSize</span><span class="sxs-lookup"><span data-stu-id="85a53-124">ClusterSize</span></span>|<span data-ttu-id="85a53-125">Especifique o número de nós a serem criados no cluster.</span><span class="sxs-lookup"><span data-stu-id="85a53-125">Specify the number of nodes to create in the cluster.</span></span>|  
|<span data-ttu-id="85a53-126">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="85a53-126">BlobContainer</span></span>|<span data-ttu-id="85a53-127">Especifique o nome do contêiner de armazenamento padrão a ser associado ao cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-127">Specify the name of the default storage container to be associated with the HDInsight cluster.</span></span>|  
|<span data-ttu-id="85a53-128">UserName</span><span class="sxs-lookup"><span data-stu-id="85a53-128">UserName</span></span>|<span data-ttu-id="85a53-129">Especifique o nome de usuário a ser usado para conectar-se ao cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-129">Specify the user name to be used for connecting to the HDInsight cluster.</span></span>|  
|<span data-ttu-id="85a53-130">Senha</span><span class="sxs-lookup"><span data-stu-id="85a53-130">Password</span></span>|<span data-ttu-id="85a53-131">Especifique a senha a ser usada para conectar-se ao cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="85a53-131">Specify the password to be used for connecting to the HDInsight cluster.</span></span>|
|<span data-ttu-id="85a53-132">SshUserName</span><span class="sxs-lookup"><span data-stu-id="85a53-132">SshUserName</span></span>|<span data-ttu-id="85a53-133">Especifique o nome de usuário usado para acessar remotamente o cluster HDInsight usando SSH.</span><span class="sxs-lookup"><span data-stu-id="85a53-133">Specify the user name used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="85a53-134">SshPassword</span><span class="sxs-lookup"><span data-stu-id="85a53-134">SshPassword</span></span>|<span data-ttu-id="85a53-135">Especifique a senha usada para acessar remotamente o cluster HDInsight usando SSH.</span><span class="sxs-lookup"><span data-stu-id="85a53-135">Specify the password used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="85a53-136">FailIfExists</span><span class="sxs-lookup"><span data-stu-id="85a53-136">FailIfExists</span></span>|<span data-ttu-id="85a53-137">Especifique se a tarefa deve falhar ou não caso o cluster já exista.</span><span class="sxs-lookup"><span data-stu-id="85a53-137">Specify whether the task should fail if the cluster already exists.</span></span>|  
  
> [!NOTE]  
> <span data-ttu-id="85a53-138">O local do cluster HDInsight e da conta de Armazenamento do Azure deve ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="85a53-138">The locations of the HDInsight cluster and the Azure Storage Account must be the same.</span></span>
