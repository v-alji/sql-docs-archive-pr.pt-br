---
title: Pesquisar destino RFC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db9404d8-4c42-45e5-a100-c7a84b056109
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 397298fce16509e667aa4baccaee62c6ff0f5cca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685221"
---
# <a name="look-up-rfc-destination"></a><span data-ttu-id="43e5f-102">Pesquisar destino RFC</span><span class="sxs-lookup"><span data-stu-id="43e5f-102">Look Up RFC Destination</span></span>
  <span data-ttu-id="43e5f-103">Use a caixa de diálogo **Pesquisar Destino RFC** para pesquisar um Destino RFC definido no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="43e5f-103">Use the **Look Up RFC Destination** dialog box to look up an RFC destination that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="43e5f-104">Quando a lista de Destino RFC disponível é exibida, selecione o destino que você quer e o componente preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="43e5f-104">When the list of available RFC destinations appears, select the destination that you want, and the component will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="43e5f-105">A origem SAP BW e o destino SAP BW usam a caixa de diálogo **Pesquisar Destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="43e5f-105">Both the SAP BW source and the SAP BW destination use the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="43e5f-106">Para obter mais informações sobre esses componentes do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Fonte SAP BW](sap-bw-source.md) e [Destino SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="43e5f-106">For more information about these components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md) and [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="43e5f-107">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="43e5f-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="43e5f-108">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="43e5f-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="43e5f-109">**Para abrir a caixa de diálogo Pesquisar Destino RFC**</span><span class="sxs-lookup"><span data-stu-id="43e5f-109">**To open the Look Up RFC Destination dialog box**</span></span>  
  
1.  <span data-ttu-id="43e5f-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem ou destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="43e5f-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source or destination.</span></span>  
  
2.  <span data-ttu-id="43e5f-111">Na guia **Fluxo de Dados** , clique duas vezes na origem ou destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="43e5f-111">On the **Data Flow** tab, double-click the SAP BW source or destination.</span></span>  
  
3.  <span data-ttu-id="43e5f-112">No **Editor de Origem SAP BW** ou **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="43e5f-112">In the **SAP BW Source Editor** or the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="43e5f-113">Na página **Gerenciador de Conexões** , na caixa de grupo **Destino RFC** , clique em **Pesquisar** para exibir a caixa de diálogo **Pesquisar Destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="43e5f-113">On the **Connection Manager** page, in the **RFC Destination** group box, click **Look up** to display the **Look Up RFC Destination** dialog box.</span></span>  
  
     <span data-ttu-id="43e5f-114">No **Editor de Origem SAP BW**, a caixa de grupo **Destino RFC** aparecerá apenas se o valor do **Modo de Execução** for **P - Disparar Cadeia de Processo** ou **A - Aguardar Notificação**.</span><span class="sxs-lookup"><span data-stu-id="43e5f-114">In the **SAP BW Source Editor**, the **RFC Destination** group box appears only if the value for **Execution mode** is **P - Trigger process chain** or **W - Wait for notify**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="43e5f-115">Opções</span><span class="sxs-lookup"><span data-stu-id="43e5f-115">Options</span></span>  
 <span data-ttu-id="43e5f-116">**Destino**</span><span class="sxs-lookup"><span data-stu-id="43e5f-116">**Destination**</span></span>  
 <span data-ttu-id="43e5f-117">Exibe o nome do destino RFC que está definido no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="43e5f-117">View the name of the RFC destination that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="43e5f-118">**Host do Gateway**</span><span class="sxs-lookup"><span data-stu-id="43e5f-118">**Gateway Host**</span></span>  
 <span data-ttu-id="43e5f-119">Exiba o nome do servidor ou endereço IP do host do gateway.</span><span class="sxs-lookup"><span data-stu-id="43e5f-119">View the server name or IP address of the gateway host.</span></span> <span data-ttu-id="43e5f-120">Em geral, o nome ou o endereço IP é o mesmo que o servidor de aplicativos do SAP.</span><span class="sxs-lookup"><span data-stu-id="43e5f-120">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="43e5f-121">**Serviço de gateway**</span><span class="sxs-lookup"><span data-stu-id="43e5f-121">**Gateway Service**</span></span>  
 <span data-ttu-id="43e5f-122">Exiba o nome do serviço de gateway, no formato `sapgwNN`, em que `NN` é o número do sistema.</span><span class="sxs-lookup"><span data-stu-id="43e5f-122">View the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="43e5f-123">**ID do Programa**</span><span class="sxs-lookup"><span data-stu-id="43e5f-123">**Program ID**</span></span>  
 <span data-ttu-id="43e5f-124">Exiba a ID do programa que está associada ao destino RFC.</span><span class="sxs-lookup"><span data-stu-id="43e5f-124">View the Program ID that is associated with the RFC destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e5f-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="43e5f-125">See Also</span></span>  
 <span data-ttu-id="43e5f-126">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="43e5f-126">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="43e5f-127">[Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="43e5f-127">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="43e5f-128">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="43e5f-128">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
