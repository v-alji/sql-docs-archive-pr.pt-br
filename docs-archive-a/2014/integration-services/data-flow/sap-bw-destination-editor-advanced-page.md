---
title: Editor de destino SAP BW (página Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 862957db-bbc6-4dda-bc0e-591457f1baa7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c5ca943b804ad39cc391cb1cf7f06e056ddbe56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574820"
---
# <a name="sap-bw-destination-editor-advanced-page"></a><span data-ttu-id="d9f6c-102">Editor de Destino SAP BW (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="d9f6c-102">SAP BW Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="d9f6c-103">Use a página **Avançado** do **Editor de Destino SAP BW** para definir as configurações avançadas como o tamanho do pacote e informações de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-103">Use the **Advanced** page of the **SAP BW Destination Editor** to set advanced settings such as package size and time-out information.</span></span>  
  
 <span data-ttu-id="d9f6c-104">Para saber mais sobre o destino SAP BW do Connector 1.1 do [!INCLUDE[msCoName](../../includes/msconame-md.md)] para SAP BW, consulte [Destino SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d9f6c-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d9f6c-105">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d9f6c-106">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d9f6c-107">**Para abrir a página Avançado**</span><span class="sxs-lookup"><span data-stu-id="d9f6c-107">**To open the Advanced page**</span></span>  
  
1.  <span data-ttu-id="d9f6c-108">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d9f6c-109">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d9f6c-110">No **Editor de Destino SAP BW**, clique em **Avançado** para abrir a página **Avançada** do editor.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-110">In the **SAP BW Destination Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d9f6c-111">Opções</span><span class="sxs-lookup"><span data-stu-id="d9f6c-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9f6c-112">Se você não souber todos os valores necessários para configurar o destino, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d9f6c-113">**Tamanho do pacote**</span><span class="sxs-lookup"><span data-stu-id="d9f6c-113">**Package size**</span></span>  
 <span data-ttu-id="d9f6c-114">Especifique quantas linhas de dados serão transferidas de cada vez.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-114">Specify how many rows of data will be transferred at a time.</span></span> <span data-ttu-id="d9f6c-115">O valor ideal para esse parâmetro depende do sistema SAP Netweaver BW e do processamento adicional dos dados que podem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-115">The optimal value for this parameter depends on the SAP Netweaver BW system and on additional processing of the data that might occur.</span></span> <span data-ttu-id="d9f6c-116">Normalmente, os valores entre 2000 e 20000 oferecem o melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-116">Typically, values between 2000 and 20000 offer the best performance.</span></span>  
  
 <span data-ttu-id="d9f6c-117">**Disparar cadeia de processo**</span><span class="sxs-lookup"><span data-stu-id="d9f6c-117">**Trigger process chain**</span></span>  
 <span data-ttu-id="d9f6c-118">(Opcional) Especifique o nome de uma cadeia do processo a ser acionada depois que o carregamento dos dados for concluído.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-118">(Optional) Specify the name of a process chain to be triggered after the loading of data is completed.</span></span>  
  
 <span data-ttu-id="d9f6c-119">**Tempo limite de espera pelo InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d9f6c-119">**Timeout for waiting InfoPackage**</span></span>  
 <span data-ttu-id="d9f6c-120">Especifique o número máximo de segundos que o destino deve aguardar o InfoPackage concluir.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-120">Specify the maximum number of seconds that the destination should wait for the InfoPackage to finish.</span></span>  
  
 <span data-ttu-id="d9f6c-121">**Aguardar a conclusão da transferência de dados**</span><span class="sxs-lookup"><span data-stu-id="d9f6c-121">**Wait for data transfer to finish**</span></span>  
 <span data-ttu-id="d9f6c-122">Especifique se o destino deve aguardar até que o sistema SAP Netweaver BW termine de carregar os dados.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-122">Specify whether the destination should wait until the SAP Netweaver BW system has finished loading the data.</span></span>  
  
 <span data-ttu-id="d9f6c-123">**Não Iniciar InfoPackage (aguardar apenas)**</span><span class="sxs-lookup"><span data-stu-id="d9f6c-123">**No InfoPackage Start (Only Wait)**</span></span>  
 <span data-ttu-id="d9f6c-124">Especifique que o destino não aciona um InfoPackage, mas apenas aguarda a notificação que o sistema SAP Netweaver BW iniciou o carregamento dos dados.</span><span class="sxs-lookup"><span data-stu-id="d9f6c-124">Specify that the destination does not trigger an InfoPackage, but just waits for notification that the SAP Netweaver BW system has started loading the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f6c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9f6c-125">See Also</span></span>  
 <span data-ttu-id="d9f6c-126">[Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d9f6c-126">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d9f6c-127">[Editor de Destino SAP BW &#40;Página Mapeamentos&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d9f6c-127">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d9f6c-128">[Editor de Destino SAP BW &#40;Página Saída de Erro&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d9f6c-128">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d9f6c-129">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d9f6c-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
