---
title: Criar InfoCube para os dados da transação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 673cea01-a260-4fce-a1a0-f73839289805
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a20fe051cfdd3e6afe285279996fcf696a83c21b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678902"
---
# <a name="create-infocube-for-transaction-data"></a><span data-ttu-id="c0070-102">Criar InfoCube para os dados da transação</span><span class="sxs-lookup"><span data-stu-id="c0070-102">Create InfoCube for Transaction Data</span></span>
  <span data-ttu-id="c0070-103">Use a caixa de diálogo **Criar InfoCube para os Dados da Transação** para criar um novo InfoCube para dados de transação no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="c0070-103">Use the **Create InfoCube for Transaction Data** dialog box to create a new InfoCube for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="c0070-104">Você pode abrir a caixa de diálogo **Criar InfoCube para os Dados da Transação** da página **Gerenciador de Conexões** do **Editor de Destino SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="c0070-104">You can open the **Create InfoCube for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="c0070-105">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c0070-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c0070-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="c0070-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="c0070-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="c0070-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="c0070-108">**Para abrir a caixa de diálogo Criar InfoCube para os Dados da Transação**</span><span class="sxs-lookup"><span data-stu-id="c0070-108">**To open the Create InfoCube for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="c0070-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c0070-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="c0070-110">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c0070-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="c0070-111">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="c0070-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="c0070-112">Na página **Gerenciador de Conexões** , na caixa de grupo **Criar Objetos SAP BW** , selecione **InfoCube**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c0070-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoCube**, and then click **Create**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="c0070-113">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="c0070-113">General Options</span></span>  
 <span data-ttu-id="c0070-114">**Nome do InfoCube**</span><span class="sxs-lookup"><span data-stu-id="c0070-114">**InfoCube name**</span></span>  
 <span data-ttu-id="c0070-115">Digite um nome para o novo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="c0070-115">Enter a name for the new InfoCube.</span></span>  
  
 <span data-ttu-id="c0070-116">**Descrição longa**</span><span class="sxs-lookup"><span data-stu-id="c0070-116">**Long description**</span></span>  
 <span data-ttu-id="c0070-117">Digite uma descrição para o novo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="c0070-117">Enter a description for the new InfoCube.</span></span>  
  
 <span data-ttu-id="c0070-118">**Salvar e Ativar**</span><span class="sxs-lookup"><span data-stu-id="c0070-118">**Save & Activate**</span></span>  
 <span data-ttu-id="c0070-119">Salvar e ativar o novo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="c0070-119">Save and activate the new InfoCube.</span></span>  
  
## <a name="infocube-transfer-structure-options"></a><span data-ttu-id="c0070-120">Opções da estrutura de transferência do InfoCube</span><span class="sxs-lookup"><span data-stu-id="c0070-120">InfoCube Transfer Structure Options</span></span>  
 <span data-ttu-id="c0070-121">A seção da estrutura de transferência do InfoCube permite associar colunas de fluxo de dados a InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="c0070-121">The InfoCube transfer structure section lets you associate data flow columns to InfoObjects.</span></span>  
  
 <span data-ttu-id="c0070-122">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="c0070-122">**PipelineElement**</span></span>  
 <span data-ttu-id="c0070-123">Exibe a coluna na saída do fluxo de dados que está conectado ao destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c0070-123">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="c0070-124">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="c0070-124">**PipelineDataType**</span></span>  
 <span data-ttu-id="c0070-125">Exibe o tipo de dados da coluna de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c0070-125">Displays the data type of the data flow column.</span></span>  
  
 <span data-ttu-id="c0070-126">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="c0070-126">**InfoObject**</span></span>  
 <span data-ttu-id="c0070-127">Exibe o nome do InfoObject associado à coluna de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c0070-127">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="c0070-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c0070-128">**Type**</span></span>  
 <span data-ttu-id="c0070-129">Exibe o tipo do InfoObject associado à coluna de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c0070-129">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="c0070-130">A tabela a seguir lista os valores possíveis do tipo.</span><span class="sxs-lookup"><span data-stu-id="c0070-130">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="c0070-131">Valor</span><span class="sxs-lookup"><span data-stu-id="c0070-131">Value</span></span>|<span data-ttu-id="c0070-132">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c0070-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c0070-133">CHA</span><span class="sxs-lookup"><span data-stu-id="c0070-133">CHA</span></span>|<span data-ttu-id="c0070-134">Características</span><span class="sxs-lookup"><span data-stu-id="c0070-134">Characteristics</span></span>|  
|<span data-ttu-id="c0070-135">UNI</span><span class="sxs-lookup"><span data-stu-id="c0070-135">UNI</span></span>|<span data-ttu-id="c0070-136">Unidades</span><span class="sxs-lookup"><span data-stu-id="c0070-136">Units</span></span>|  
|<span data-ttu-id="c0070-137">KYF</span><span class="sxs-lookup"><span data-stu-id="c0070-137">KYF</span></span>|<span data-ttu-id="c0070-138">Valores-chave</span><span class="sxs-lookup"><span data-stu-id="c0070-138">Key figures</span></span>|  
|<span data-ttu-id="c0070-139">TIM</span><span class="sxs-lookup"><span data-stu-id="c0070-139">TIM</span></span>|<span data-ttu-id="c0070-140">Características de hora</span><span class="sxs-lookup"><span data-stu-id="c0070-140">Time characteristics</span></span>|  
  
 <span data-ttu-id="c0070-141">**Iobject - Pesquisa**</span><span class="sxs-lookup"><span data-stu-id="c0070-141">**Iobject - Search**</span></span>  
 <span data-ttu-id="c0070-142">Associar um InfoObject existente à coluna de fluxo de dados para a linha atual.</span><span class="sxs-lookup"><span data-stu-id="c0070-142">Associate an existing InfoObject to the data flow column for the current row.</span></span> <span data-ttu-id="c0070-143">Para fazer essa associação, clique em **Pesquisar** e use a caixa de diálogo **Pesquisar InfoObject** para selecionar o InfoObject existente.</span><span class="sxs-lookup"><span data-stu-id="c0070-143">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="c0070-144">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="c0070-144">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="c0070-145">Depois de selecionar um InfoObject existente, o componente preenche as colunas **InfoObject** e **Tipo** com os valores selecionados.</span><span class="sxs-lookup"><span data-stu-id="c0070-145">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="c0070-146">**Iobject - Novo**</span><span class="sxs-lookup"><span data-stu-id="c0070-146">**Iobject - New**</span></span>  
 <span data-ttu-id="c0070-147">Crie um novo InfoObject e associe esse novo InfoObject à coluna de fluxo de dados na linha atual.</span><span class="sxs-lookup"><span data-stu-id="c0070-147">Create a new InfoObject and associate this new InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="c0070-148">Para criar o novo InfoObject, clique em **Novo**e use a caixa de diálogo **Criar Novo InfoObject** para criar o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="c0070-148">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="c0070-149">Para obter mais informações sobre essa caixa de diálogo, consulte [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="c0070-149">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="c0070-150">Depois de criar um novo InfoObject, o componente preenche as colunas **InfoObject** e **Tipo** com os novos valores.</span><span class="sxs-lookup"><span data-stu-id="c0070-150">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="c0070-151">**Iobject - Remover**</span><span class="sxs-lookup"><span data-stu-id="c0070-151">**Iobject - Remove**</span></span>  
 <span data-ttu-id="c0070-152">Remover a associação entre o InfoObject e a coluna de fluxo de dados para a linha atual.</span><span class="sxs-lookup"><span data-stu-id="c0070-152">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="c0070-153">Para remover essa associação, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c0070-153">To remove this association, click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0070-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0070-154">See Also</span></span>  
 [<span data-ttu-id="c0070-155">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="c0070-155">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
