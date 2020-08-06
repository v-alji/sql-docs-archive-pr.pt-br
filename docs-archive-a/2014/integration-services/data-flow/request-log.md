---
title: Log de solicitações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 024012878ae94c5ba6276648e289e6e6f7c93d7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571461"
---
# <a name="request-log"></a><span data-ttu-id="965f6-102">Log de solicitações</span><span class="sxs-lookup"><span data-stu-id="965f6-102">Request Log</span></span>
  <span data-ttu-id="965f6-103">Use a caixa de diálogo **Log de Solicitações** para exibir os eventos que são registrados em log durante a solicitação que é feita no sistema SAP Netweaver BW para dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="965f6-103">Use the **Request Log** dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="965f6-104">Essas informações podem ser úteis se você precisar solucionar problemas da configuração da origem do SAP BW.</span><span class="sxs-lookup"><span data-stu-id="965f6-104">This information can be useful if you have to troubleshoot your configuration of the SAP BW source.</span></span>  
  
 <span data-ttu-id="965f6-105">Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="965f6-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="965f6-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="965f6-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="965f6-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="965f6-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="965f6-108">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="965f6-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="965f6-109">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="965f6-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="965f6-110">**Para abrir a caixa de diálogo Log de Solicitações**</span><span class="sxs-lookup"><span data-stu-id="965f6-110">**To open the Request Log dialog box**</span></span>  
  
1.  <span data-ttu-id="965f6-111">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="965f6-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="965f6-112">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="965f6-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="965f6-113">No **Editor de Origem SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="965f6-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="965f6-114">Depois de configurar a origem do SAP BW, clique em **Visualizar** para visualizar os eventos na caixa de diálogo **Log de Solicitações** .</span><span class="sxs-lookup"><span data-stu-id="965f6-114">After you configure the SAP BW source, click **Preview** to preview the events in the **Request Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="965f6-115">Clicar em **Visualizar** também abre a caixa de diálogo **Visualizar** .</span><span class="sxs-lookup"><span data-stu-id="965f6-115">Clicking **Preview** also opens the **Preview** dialog box.</span></span> <span data-ttu-id="965f6-116">Para obter mais informações sobre essa caixa de diálogo, consulte [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="965f6-116">For more information about this dialog box, see [Preview](preview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="965f6-117">Opções</span><span class="sxs-lookup"><span data-stu-id="965f6-117">Options</span></span>  
 <span data-ttu-id="965f6-118">**Hora**</span><span class="sxs-lookup"><span data-stu-id="965f6-118">**Time**</span></span>  
 <span data-ttu-id="965f6-119">Exibe a hora em que o evento foi registrado em log.</span><span class="sxs-lookup"><span data-stu-id="965f6-119">Displays the time that the event that was logged.</span></span>  
  
 <span data-ttu-id="965f6-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="965f6-120">**Type**</span></span>  
 <span data-ttu-id="965f6-121">Exibe o tipo do evento que foi registrado em log.</span><span class="sxs-lookup"><span data-stu-id="965f6-121">Displays the type of the event that was logged.</span></span> <span data-ttu-id="965f6-122">A tabela seguinte lista os possíveis tipos de evento.</span><span class="sxs-lookup"><span data-stu-id="965f6-122">The following table lists the possible event types.</span></span>  
  
|<span data-ttu-id="965f6-123">Valor</span><span class="sxs-lookup"><span data-stu-id="965f6-123">Value</span></span>|<span data-ttu-id="965f6-124">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="965f6-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="965f6-125">S</span><span class="sxs-lookup"><span data-stu-id="965f6-125">S</span></span>|<span data-ttu-id="965f6-126">Mensagem de êxito.</span><span class="sxs-lookup"><span data-stu-id="965f6-126">Success message.</span></span>|  
|<span data-ttu-id="965f6-127">E</span><span class="sxs-lookup"><span data-stu-id="965f6-127">E</span></span>|<span data-ttu-id="965f6-128">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="965f6-128">Error message</span></span>|  
|<span data-ttu-id="965f6-129">W</span><span class="sxs-lookup"><span data-stu-id="965f6-129">W</span></span>|<span data-ttu-id="965f6-130">Mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="965f6-130">Warning message.</span></span>|  
|<span data-ttu-id="965f6-131">I</span><span class="sxs-lookup"><span data-stu-id="965f6-131">I</span></span>|<span data-ttu-id="965f6-132">Mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="965f6-132">Informational message.</span></span>|  
|<span data-ttu-id="965f6-133">Um</span><span class="sxs-lookup"><span data-stu-id="965f6-133">A</span></span>|<span data-ttu-id="965f6-134">A operação foi anulada.</span><span class="sxs-lookup"><span data-stu-id="965f6-134">The operation was aborted.</span></span>|  
  
 <span data-ttu-id="965f6-135">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="965f6-135">**Message**</span></span>  
 <span data-ttu-id="965f6-136">Exibe o texto da mensagem associada ao evento de log.</span><span class="sxs-lookup"><span data-stu-id="965f6-136">Displays the message text that is associated with the logged event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="965f6-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="965f6-137">See Also</span></span>  
 <span data-ttu-id="965f6-138">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="965f6-138">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="965f6-139">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="965f6-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
