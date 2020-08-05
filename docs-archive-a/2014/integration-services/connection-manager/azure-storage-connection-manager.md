---
title: Gerenciador de Conexões do Armazenamento do Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpstorageconn.f1
- sql11.dts.designer.afpstorageconn.f1
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47580d8d1d961df9fbcbed0bd7164f1c54792b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574232"
---
# <a name="azure-storage-connection-manager"></a><span data-ttu-id="b85b6-102">Gerenciador de conexões do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="b85b6-102">Azure Storage Connection Manager</span></span>
  <span data-ttu-id="b85b6-103">O gerenciador de conexões do Armazenamento do Azure permite que um pacote SSIS se conecte a uma conta do Armazenamento do Azure usando os valores especificados para as propriedades: Nome da Conta de Armazenamento e Chave de Conta.</span><span class="sxs-lookup"><span data-stu-id="b85b6-103">The Azure Storage connection manager enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.</span></span>  
  
1.  <span data-ttu-id="b85b6-104">Na caixa de diálogo **Adicionar gerenciador de conexões do SSIS** , selecione **AzureStorage**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b85b6-104">In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="b85b6-105">Na caixa de diálogo Editor do Gerenciador de Conexão do Armazenamento do Azure, escolha **Usar conta do Azure** para se conectar a um Serviço de Armazenamento do Azure por meio da Internet ou escolha **Usar conta de desenvolvedor local** para se conectar ao serviço local hospedado pelo Emulador de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b85b6-105">In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.</span></span>  
  
3.  <span data-ttu-id="b85b6-106">Se você tiver escolhido a opção **Usar conta do Azure** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b85b6-106">If you selected **Use Azure account** option, do the following:</span></span>  
  
    1.  <span data-ttu-id="b85b6-107">Especifique valores para os campos **Nome da conta de armazenamento** e **Chave de conta** .</span><span class="sxs-lookup"><span data-stu-id="b85b6-107">Specify values for the **Storage account name** and **Account key** field.</span></span> <span data-ttu-id="b85b6-108">Esses valores serão armazenados como dados confidenciais no pacote SSIS.</span><span class="sxs-lookup"><span data-stu-id="b85b6-108">These values will be stored as sensitive data in SSIS package.</span></span>  
  
    2.  <span data-ttu-id="b85b6-109">Escolha **Usar HTTPS** se quiser usar HTTPS em vez de HTTP para se conectar ao Serviço de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b85b6-109">Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.</span></span>  
  
4.  <span data-ttu-id="b85b6-110">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b85b6-110">Click **OK** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="b85b6-111">Você pode ver as propriedades do gerenciador de conexões criado na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="b85b6-111">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
