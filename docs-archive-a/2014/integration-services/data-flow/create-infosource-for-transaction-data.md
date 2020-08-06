---
title: Criar InfoSource para os dados da transação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e3a60bb93da17e79087982473e92c35fa0856d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678894"
---
# <a name="create-infosource-for-transaction-data"></a><span data-ttu-id="971cb-102">Criar InfoSource para os dados da transação</span><span class="sxs-lookup"><span data-stu-id="971cb-102">Create InfoSource for Transaction Data</span></span>
  <span data-ttu-id="971cb-103">Use a caixa de diálogo **Criar InfoSource para os Dados da Transação** para criar um novo InfoSource para dados de transação no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="971cb-103">Use the **Create InfoSource for Transaction Data** dialog box to create a new InfoSource for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="971cb-104">Você pode abrir a caixa de diálogo **Criar InfoSource para os Dados da Transação** da página **Gerenciador de Conexões** do **Editor de Destino SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="971cb-104">You can open the **Create InfoSource for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="971cb-105">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="971cb-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="971cb-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="971cb-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="971cb-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="971cb-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="971cb-108">**Para abrir a caixa de diálogo Criar InfoSource para os Dados da Transação**</span><span class="sxs-lookup"><span data-stu-id="971cb-108">**To open the Create InfoSource for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="971cb-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="971cb-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="971cb-110">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="971cb-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="971cb-111">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="971cb-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="971cb-112">Na página **Gerenciador de Conexões** , na caixa de grupo **Criar Objetos SAP BW** , selecione **InfoSource**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="971cb-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="971cb-113">Na caixa de diálogo **Criar InfoSource** , selecione **Dados da Transação**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="971cb-113">In the **Create InfoSource** dialog box, select **Transaction data**, and then click **OK**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="971cb-114">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="971cb-114">General Options</span></span>  
 <span data-ttu-id="971cb-115">**Nome do InfoSource**</span><span class="sxs-lookup"><span data-stu-id="971cb-115">**InfoSource name**</span></span>  
 <span data-ttu-id="971cb-116">Digite um nome para o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="971cb-116">Enter a name for the new InfoSource.</span></span>  
  
 <span data-ttu-id="971cb-117">**Descrição breve**</span><span class="sxs-lookup"><span data-stu-id="971cb-117">**Short description**</span></span>  
 <span data-ttu-id="971cb-118">Insira uma descrição curta para o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="971cb-118">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="971cb-119">**Descrição longa**</span><span class="sxs-lookup"><span data-stu-id="971cb-119">**Long description**</span></span>  
 <span data-ttu-id="971cb-120">Insira uma descrição longa para o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="971cb-120">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="971cb-121">**Sistema de origem**</span><span class="sxs-lookup"><span data-stu-id="971cb-121">**Source system**</span></span>  
 <span data-ttu-id="971cb-122">Selecione o sistema de origem associado ao InfoSource.</span><span class="sxs-lookup"><span data-stu-id="971cb-122">Select the source system associated with the InfoSource.</span></span>  
  
 <span data-ttu-id="971cb-123">**Salvar e Ativar**</span><span class="sxs-lookup"><span data-stu-id="971cb-123">**Save & Activate**</span></span>  
 <span data-ttu-id="971cb-124">Salvar e ativar o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="971cb-124">Save and activate the new InfoSource.</span></span>  
  
## <a name="infosource-transfer-structure-options"></a><span data-ttu-id="971cb-125">Opções da estrutura de transferência do InfoSource</span><span class="sxs-lookup"><span data-stu-id="971cb-125">InfoSource Transfer Structure Options</span></span>  
 <span data-ttu-id="971cb-126">A estrutura de transferência do InfoSource permite associar colunas de fluxo de dados a InfoSources.</span><span class="sxs-lookup"><span data-stu-id="971cb-126">The InfoSource transfer structure lets you associate data flow columns to InfoSources.</span></span>  
  
 <span data-ttu-id="971cb-127">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="971cb-127">**PipelineElement**</span></span>  
 <span data-ttu-id="971cb-128">Exibe a coluna na saída do fluxo de dados que está conectado ao destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="971cb-128">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="971cb-129">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="971cb-129">**PipelineDataType**</span></span>  
 <span data-ttu-id="971cb-130">Exibe o tipo de dados [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] da coluna de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="971cb-130">Displays the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type of the data flow column.</span></span>  
  
 <span data-ttu-id="971cb-131">**Iobject - Pesquisa**</span><span class="sxs-lookup"><span data-stu-id="971cb-131">**Iobject - Search**</span></span>  
 <span data-ttu-id="971cb-132">Associar um InfoObject existente à coluna de fluxo de dados na linha atual.</span><span class="sxs-lookup"><span data-stu-id="971cb-132">Associate an existing InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="971cb-133">Para fazer essa associação, clique em **Pesquisar** e use a caixa de diálogo **Pesquisar InfoObject** para selecionar o InfoObject existente.</span><span class="sxs-lookup"><span data-stu-id="971cb-133">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="971cb-134">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="971cb-134">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="971cb-135">Depois de selecionar um InfoObject existente, o componente preenche as colunas **InfoObject** e **Tipo** com os valores selecionados.</span><span class="sxs-lookup"><span data-stu-id="971cb-135">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="971cb-136">**Iobject - Novo**</span><span class="sxs-lookup"><span data-stu-id="971cb-136">**Iobject - New**</span></span>  
 <span data-ttu-id="971cb-137">Crie um novo InfoObject e associe esse novo InfoObject à coluna de fluxo de dados na linha atual.</span><span class="sxs-lookup"><span data-stu-id="971cb-137">Create a new InfoObject and associate this new InfoObect to the data flow column in the current row.</span></span> <span data-ttu-id="971cb-138">Para criar o novo InfoObject, clique em **Novo**e use a caixa de diálogo **Criar Novo InfoObject** para criar o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="971cb-138">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="971cb-139">Para obter mais informações sobre essa caixa de diálogo, consulte [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="971cb-139">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="971cb-140">Depois de criar um novo InfoObject, o componente preenche as colunas **InfoObject** e **Tipo** com os novos valores.</span><span class="sxs-lookup"><span data-stu-id="971cb-140">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="971cb-141">**Iobject - Remover**</span><span class="sxs-lookup"><span data-stu-id="971cb-141">**Iobject - Remove**</span></span>  
 <span data-ttu-id="971cb-142">Remover a associação entre o InfoObject e a coluna de fluxo de dados para a linha atual.</span><span class="sxs-lookup"><span data-stu-id="971cb-142">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="971cb-143">Para remover essa associação, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="971cb-143">To remove this association, click **Remove**.</span></span>  
  
 <span data-ttu-id="971cb-144">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="971cb-144">**InfoObject**</span></span>  
 <span data-ttu-id="971cb-145">Exibe o nome do InfoObject associado à coluna de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="971cb-145">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="971cb-146">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="971cb-146">**Type**</span></span>  
 <span data-ttu-id="971cb-147">Exibe o tipo do InfoObject associado à coluna de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="971cb-147">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="971cb-148">A tabela a seguir lista os valores possíveis do tipo.</span><span class="sxs-lookup"><span data-stu-id="971cb-148">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="971cb-149">Valor</span><span class="sxs-lookup"><span data-stu-id="971cb-149">Value</span></span>|<span data-ttu-id="971cb-150">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="971cb-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="971cb-151">CHA</span><span class="sxs-lookup"><span data-stu-id="971cb-151">CHA</span></span>|<span data-ttu-id="971cb-152">Características</span><span class="sxs-lookup"><span data-stu-id="971cb-152">Characteristics</span></span>|  
|<span data-ttu-id="971cb-153">UNI</span><span class="sxs-lookup"><span data-stu-id="971cb-153">UNI</span></span>|<span data-ttu-id="971cb-154">Unidades</span><span class="sxs-lookup"><span data-stu-id="971cb-154">Units</span></span>|  
|<span data-ttu-id="971cb-155">KYF</span><span class="sxs-lookup"><span data-stu-id="971cb-155">KYF</span></span>|<span data-ttu-id="971cb-156">Valores-chave</span><span class="sxs-lookup"><span data-stu-id="971cb-156">Key figures</span></span>|  
|<span data-ttu-id="971cb-157">TIM</span><span class="sxs-lookup"><span data-stu-id="971cb-157">TIM</span></span>|<span data-ttu-id="971cb-158">Características de hora</span><span class="sxs-lookup"><span data-stu-id="971cb-158">Time characteristics</span></span>|  
  
 <span data-ttu-id="971cb-159">**Campo unidade**</span><span class="sxs-lookup"><span data-stu-id="971cb-159">**Unit Field**</span></span>  
 <span data-ttu-id="971cb-160">Especifique as unidades que o InfoObject usará.</span><span class="sxs-lookup"><span data-stu-id="971cb-160">Specify the units that the InfoObject will use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971cb-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="971cb-161">See Also</span></span>  
 <span data-ttu-id="971cb-162">[Criar InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="971cb-162">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="971cb-163">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="971cb-163">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
