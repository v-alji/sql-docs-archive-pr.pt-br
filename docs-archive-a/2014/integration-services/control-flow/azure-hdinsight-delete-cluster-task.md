---
title: Tarefa Excluir Cluster do Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpdelcltask.f1
- sql11.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: chugugrace
ms.author: chugu
ms.openlocfilehash: db0a15aaea37c6d18c1d3c2136e0fd0c94eb7506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582080"
---
# <a name="azure-hdinsight-delete-cluster-task"></a><span data-ttu-id="24668-102">Tarefa Excluir Cluster do Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="24668-102">Azure HDInsight Delete Cluster Task</span></span>
<span data-ttu-id="24668-103">A **Tarefa Excluir Cluster do Azure HDInsight** permite que um pacote do SSIS exclua um cluster do Azure HDInsight na assinatura e grupo de recursos do Azure especificados.</span><span class="sxs-lookup"><span data-stu-id="24668-103">The **Azure HDInsight Delete Cluster Task** enables an SSIS package to delete an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24668-104">Excluir um cluster HDInsight pode levar entre 10 e 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="24668-104">Deleting an HDInsight cluster may take 10~20 minutes.</span></span>  
  
<span data-ttu-id="24668-105">Para adicionar uma **Tarefa Excluir Cluster do Azure HDInsight**, arraste e solte-a no Designer SSIS e clique duas vezes ou com o botão direito do mouse e clique em **Editar** para ver a caixa de diálogo **Editor de Tarefa Excluir Cluster do Azure HDInsight** a seguir.</span><span class="sxs-lookup"><span data-stu-id="24668-105">To add an **Azure HDInsight Delete Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Delete Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="24668-106">A tabela a seguir fornece uma descrição dos campos nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="24668-106">The following table provides a description for the fields in the dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24668-107">**Campo**</span><span class="sxs-lookup"><span data-stu-id="24668-107">**Field**</span></span>|<span data-ttu-id="24668-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="24668-108">**Description**</span></span>|  
|<span data-ttu-id="24668-109">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="24668-109">AzureResourceManagerConnection</span></span>|<span data-ttu-id="24668-110">Selecione um gerenciador de conexões do Azure Resource Manager existente ou crie um novo que será usado para excluir o cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="24668-110">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to delete the HDInsight cluster.</span></span>|
|<span data-ttu-id="24668-111">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="24668-111">SubscriptionId</span></span>|<span data-ttu-id="24668-112">Especifique a ID da assinatura na qual o cluster HDInsight está.</span><span class="sxs-lookup"><span data-stu-id="24668-112">Specify the ID of the subscription the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="24668-113">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="24668-113">ResourceGroup</span></span>|<span data-ttu-id="24668-114">Especifique o grupo de recursos do Azure no qual o cluster HDInsight está.</span><span class="sxs-lookup"><span data-stu-id="24668-114">Specify the Azure resource group the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="24668-115">ClusterName</span><span class="sxs-lookup"><span data-stu-id="24668-115">ClusterName</span></span>|<span data-ttu-id="24668-116">Especifique o nome do cluster a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="24668-116">Specify the name of the cluster to be deleted.</span></span>|  
|<span data-ttu-id="24668-117">FailIfNotExists</span><span class="sxs-lookup"><span data-stu-id="24668-117">FailIfNotExists</span></span>|<span data-ttu-id="24668-118">Especifique se a tarefa deve falhar ou não caso o cluster não exista.</span><span class="sxs-lookup"><span data-stu-id="24668-118">Specify whether the task should fail if the cluster does not exist.</span></span>|
