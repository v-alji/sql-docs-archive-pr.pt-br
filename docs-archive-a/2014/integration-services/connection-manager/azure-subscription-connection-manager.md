---
title: Gerenciador de Conexões da Assinatura do Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpsubscrconn.f1
- sql11.dts.designer.afpsubscrconn.f1
ms.assetid: e1225327-c308-4c50-8f44-c411f52ef378
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bff1286525983b32c2191f1f8864a0f2bef0e6b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574227"
---
# <a name="azure-subscription-connection-manager"></a><span data-ttu-id="4f279-102">Gerenciador de Conexões da Assinatura do Azure</span><span class="sxs-lookup"><span data-stu-id="4f279-102">Azure Subscription Connection Manager</span></span>
  <span data-ttu-id="4f279-103">O Gerenciador de Conexões do Azure HDInsight permite que um pacote do SSIS se conecte a uma assinatura do Azure usando os valores especificados para as propriedades: ID da Assinatura do Azure e Certificado de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="4f279-103">The Azure HDInsight connection manager enables an SSIS package to connect to an Azure subscription by using the values you specify for the properties: Azure Subscription ID and Management Certificate.</span></span>

1.  <span data-ttu-id="4f279-104">Na caixa de diálogo **Adicionar Gerenciador de Conexões SSIS** mostrada acima, escolha **Assinatura do Azure**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4f279-104">In the **Add SSIS Connection Manager** dialog box shown above, you select **Azure Subscription**, and click **Add**.</span></span>  <span data-ttu-id="4f279-105">Você deve ver a caixa de diálogo **Editor do Gerenciador de Conexões da Assinatura do Azure** a seguir.</span><span class="sxs-lookup"><span data-stu-id="4f279-105">You should see the following **Azure Subscription Connection Manager Editor** dialog box.</span></span>

     <span data-ttu-id="4f279-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span><span class="sxs-lookup"><span data-stu-id="4f279-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span></span>

2.  <span data-ttu-id="4f279-107">Insira sua ID de assinatura do Azure, que identifica exclusivamente uma assinatura do Azure, em **ID da assinatura do Azure**.</span><span class="sxs-lookup"><span data-stu-id="4f279-107">Enter your Azure subscription ID, which uniquely identifies an Azure subscription, for the **Azure subscription ID**.</span></span>  <span data-ttu-id="4f279-108">O valor pode ser encontrado no [Portal de Gerenciamento do Azure](https://manage.windowsazure.com) na página **Configurações** :</span><span class="sxs-lookup"><span data-stu-id="4f279-108">The value can be found on the [Azure Management Portal](https://manage.windowsazure.com) under **Settings** page:</span></span>

     <span data-ttu-id="4f279-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span><span class="sxs-lookup"><span data-stu-id="4f279-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span></span>

3.  <span data-ttu-id="4f279-110">Escolha **Local do repositório de certificados de gerenciamento** e **Nome do repositório de certificados de gerenciamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="4f279-110">Choose **Management certificate store location** and **Management certificate store name** from the drop-down lists.</span></span>

4.  <span data-ttu-id="4f279-111">Insira **Impressão digital do certificado de gerenciamento** ou clique em **Procurar...** para escolher um certificado no repositório selecionado.</span><span class="sxs-lookup"><span data-stu-id="4f279-111">Enter **Management certificate thumbprint** or click the **Browse...** to choose a certificate from the selected store.</span></span> <span data-ttu-id="4f279-112">O certificado deve ser carregado como um certificado de gerenciamento para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="4f279-112">The certificate must be uploaded as a management certificate for the subscription.</span></span> <span data-ttu-id="4f279-113">Para fazer isso, clique em **Carregar** na página a seguir do Portal do Azure (confira esta [postagem do MSDN](https://msdn.microsoft.com/library/azure/gg551722.aspx) para obter mais detalhes).</span><span class="sxs-lookup"><span data-stu-id="4f279-113">To do so, click **Upload** on the following page of the Azure Portal (see this [MSDN post](https://msdn.microsoft.com/library/azure/gg551722.aspx) for more detail).</span></span>

     <span data-ttu-id="4f279-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span><span class="sxs-lookup"><span data-stu-id="4f279-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span></span>

5.  <span data-ttu-id="4f279-115">Clique em **testar conexão** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="4f279-115">Click **Test Connection** to test the connection.</span></span>

6.  <span data-ttu-id="4f279-116">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4f279-116">Click **OK** to close the dialog box.</span></span>


