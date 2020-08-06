---
title: Gerenciador de Conexões do Azure Resource Manager | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPARMCM.F1
- SQL11.DTS.DESIGNER.AFPARMCM.F1
ms.assetid: a2380258-0418-4a8c-a731-5071a44ddf1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1dce4def11f14072295dbf3cde9d5ab77304fe74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574880"
---
# <a name="azure-resource-manager-connection-manager"></a><span data-ttu-id="ffb06-102">Gerenciador de Conexões do Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="ffb06-102">Azure Resource Manager Connection Manager</span></span>
<span data-ttu-id="ffb06-103">O **Gerenciador de Conexões do Azure Resource Manager** permite que um pacote do SSIS gerencie recursos do Azure usando uma [entidade de serviço](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="ffb06-103">The **Azure Resource Manager Connection Manager** enables an SSIS package to manage Azure resources using a [service principal](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>

<span data-ttu-id="ffb06-104">Para criar e configurar um **gerenciador de conexões do Azure Resource Manager**, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="ffb06-104">To create and configure an **Azure Resource Manager Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="ffb06-105">Na caixa de diálogo **Adicionar gerenciador de conexões do SSIS**, selecione **AzureResourceManager** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ffb06-105">In the **Add SSIS Connection Manager** dialog box, select **AzureResourceManager**, and click **Add**.</span></span>
2. <span data-ttu-id="ffb06-106">Na caixa de diálogo **Editor do gerenciador de conexões do Azure Resource Manager**, especifique a **ID do Aplicativo**, a **Chave do Aplicativo** e a **ID do Locatário** da entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="ffb06-106">In the **Azure Resource Manager Connection Manager Editor** dialog box, specify the **Application ID**, **Application Key**, and **Tenant ID** for the service principal.</span></span> <span data-ttu-id="ffb06-107">Para obter detalhes sobre essas propriedades, consulte [este](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) artigo.</span><span class="sxs-lookup"><span data-stu-id="ffb06-107">For details about these properties, please refer to [this](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) article.</span></span>
3. <span data-ttu-id="ffb06-108">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ffb06-108">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="ffb06-109">Você pode ver as propriedades do gerenciador de conexões criado na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="ffb06-109">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
