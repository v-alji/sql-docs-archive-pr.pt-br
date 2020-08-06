---
title: Gerenciador de Conexões do Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPHDICM.F1
- SQL11.DTS.DESIGNER.AFPHDICM.F1
ms.assetid: 850a978d-5dba-45b6-a10e-306aafbc353d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaf2f57fec50a58ad1b7e7578407fb6cf3fa0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678941"
---
# <a name="azure-hdinsight-connection-manager"></a><span data-ttu-id="cc587-102">Gerenciador de Conexões do Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="cc587-102">Azure HDInsight Connection Manager</span></span>
<span data-ttu-id="cc587-103">O **Gerenciador de Conexões do Azure HDInsight** permite que um pacote do SSIS se conecte a um cluster HDInsight do Azure.</span><span class="sxs-lookup"><span data-stu-id="cc587-103">The **Azure HDInsight Connection Manager** enables an SSIS package to connect to an Azure HDInsight cluster.</span></span>

<span data-ttu-id="cc587-104">Para criar e configurar um **Gerenciador de Conexões do Azure HDInsight**, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="cc587-104">To create and configure an **Azure HDInsight Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="cc587-105">Na caixa de diálogo **Adicionar Gerenciador de Conexões do SSIS**, selecione **AzureHDInsight** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc587-105">In the **Add SSIS Connection Manager** dialog box, select **AzureHDInsight**, and click **Add**.</span></span>
2. <span data-ttu-id="cc587-106">Na caixa de diálogo **Editor do Gerenciador de Conexões do Azure HDInsight**, especifique o **Nome DNS de Cluster** (sem o prefixo de protocolo), **Nome de usuário** e **Senha** para o cluster HDInsight ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="cc587-106">In the **Azure HDInsight Connection Manager Editor** dialog box, specify the **Cluster DNS name** (without the protocol prefix), **Username**, and **Password** for the HDInsight cluster to connect to.</span></span>
3. <span data-ttu-id="cc587-107">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cc587-107">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="cc587-108">Você pode ver as propriedades do gerenciador de conexões criado na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="cc587-108">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
