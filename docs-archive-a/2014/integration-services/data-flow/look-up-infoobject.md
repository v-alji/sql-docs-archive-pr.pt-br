---
title: Pesquisar InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7f4c132-a5ec-49d8-a964-45775432731f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1616b4fcb368afc9e3f1157a3fc2511d4a7e8cce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680579"
---
# <a name="look-up-infoobject"></a><span data-ttu-id="8f90b-102">Pesquisar InfoObject</span><span class="sxs-lookup"><span data-stu-id="8f90b-102">Look Up InfoObject</span></span>
  <span data-ttu-id="8f90b-103">Use a caixa de diálogo **Pesquisar InfoObject** para pesquisar um InfoObject definido no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8f90b-103">Use the **Look Up InfoObject** dialog box to look up an InfoObject that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="8f90b-104">Quando a lista de InfoObjects disponível é exibida, selecione o InfoObject que você quer e o destino do SAP BW preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="8f90b-104">When the list of available InfoObjects appears, select the InfoObject that you want, and the SAP BW destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="8f90b-105">O destino SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW usa a caixa de diálogo **Pesquisar InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8f90b-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up InfoObject** dialog box.</span></span> <span data-ttu-id="8f90b-106">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8f90b-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f90b-107">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8f90b-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="8f90b-108">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="8f90b-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="8f90b-109">**Para abrir a caixa de diálogo Pesquisar InfoObject**</span><span class="sxs-lookup"><span data-stu-id="8f90b-109">**To open the Look Up InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="8f90b-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f90b-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="8f90b-111">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f90b-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="8f90b-112">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="8f90b-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="8f90b-113">Na página **Gerenciador de Conexões** , na caixa do grupo **Criar Objetos SAP BW** , selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="8f90b-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select one of the following options:</span></span>  
  
    1.  <span data-ttu-id="8f90b-114">Selecione **InfoCube**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-114">Select **InfoCube**.</span></span> <span data-ttu-id="8f90b-115">Em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-115">Then, click **Create**.</span></span> <span data-ttu-id="8f90b-116">Na caixa de diálogo **Criar InfoCube para os Dados da Transação** , clique em **Pesquisar** na coluna **IObject** para uma das linhas na lista.</span><span class="sxs-lookup"><span data-stu-id="8f90b-116">In the **Create InfoCube for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="8f90b-117">Cada linha representa uma coluna no fluxo de dados do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f90b-117">Each row represents a column in the data flow of the package.</span></span>  
  
    2.  <span data-ttu-id="8f90b-118">Selecione **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-118">Select **InfoSource**.</span></span> <span data-ttu-id="8f90b-119">Em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-119">Then click **Create**.</span></span> <span data-ttu-id="8f90b-120">Na caixa de diálogo **Criar InfoSource** , selecione **Dados da Transação**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-120">In the **Create InfoSource** dialog box, select **Transaction data**.</span></span> <span data-ttu-id="8f90b-121">Na caixa de diálogo **Criar InfoSource para os Dados da Transação** , clique em **Pesquisar** na coluna **IObject** para uma das linhas na lista.</span><span class="sxs-lookup"><span data-stu-id="8f90b-121">In the **Create InfoSource for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="8f90b-122">Cada linha representa uma coluna no fluxo de dados do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f90b-122">Each row represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="8f90b-123">Selecione **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-123">Select **InfoSource**.</span></span> <span data-ttu-id="8f90b-124">Em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-124">Then click **Create**.</span></span> <span data-ttu-id="8f90b-125">Na caixa de diálogo **Criar InfoSource** , selecione **Dados mestres**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-125">In the **Create InfoSource** dialog box, select **Master data**.</span></span> <span data-ttu-id="8f90b-126">Na caixa de diálogo **Criar InfoSource para Dados Mestres** , clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="8f90b-126">In the **Create InfoSource for Master Data** dialog box, click **Look up**.</span></span>  
  
 <span data-ttu-id="8f90b-127">Você também pode abrir a caixa de diálogo **Pesquisar InfoObject** clicando em **Adicionar** na seção **Atributos** da caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8f90b-127">You can also open the **Look Up InfoObject** dialog box by clicking **Add** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="8f90b-128">Opções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="8f90b-128">Lookup Options</span></span>  
 <span data-ttu-id="8f90b-129">Nas caixas de texto do campo de pesquisa, você pode filtrar os resultados usando o caractere curinga asterisco (\*) ou usando uma cadeia de caracteres parcial em combinação com o caractere curinga asterisco.</span><span class="sxs-lookup"><span data-stu-id="8f90b-129">In the lookup field text boxes, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="8f90b-130">No entanto, se você deixar um campo de pesquisa vazio, o processo de pesquisa corresponderá apenas a cadeias de caracteres vazias nesse campo.</span><span class="sxs-lookup"><span data-stu-id="8f90b-130">However, if you leave a lookup field empty, the lookup process will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="8f90b-131">**Características**</span><span class="sxs-lookup"><span data-stu-id="8f90b-131">**Characteristics**</span></span>  
 <span data-ttu-id="8f90b-132">Pesquisar InfoObjects que representam as características.</span><span class="sxs-lookup"><span data-stu-id="8f90b-132">Look up InfoObjects that represent characteristics.</span></span>  
  
 <span data-ttu-id="8f90b-133">**Unidades**</span><span class="sxs-lookup"><span data-stu-id="8f90b-133">**Units**</span></span>  
 <span data-ttu-id="8f90b-134">Pesquisar InfoObjects que representam as unidades.</span><span class="sxs-lookup"><span data-stu-id="8f90b-134">Look up InfoObjects that represent units.</span></span>  
  
 <span data-ttu-id="8f90b-135">**Valores-chave**</span><span class="sxs-lookup"><span data-stu-id="8f90b-135">**Key figures**</span></span>  
 <span data-ttu-id="8f90b-136">Pesquisar InfoObjects que representam as imagens chave.</span><span class="sxs-lookup"><span data-stu-id="8f90b-136">Look up InfoObjects that represent key figures.</span></span>  
  
 <span data-ttu-id="8f90b-137">**Características de hora**</span><span class="sxs-lookup"><span data-stu-id="8f90b-137">**Time characteristics**</span></span>  
 <span data-ttu-id="8f90b-138">Pesquisar InfoObjects que representam as características de hora.</span><span class="sxs-lookup"><span data-stu-id="8f90b-138">Look up InfoObjects that represent time characteristics.</span></span>  
  
 <span data-ttu-id="8f90b-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8f90b-139">**Name**</span></span>  
 <span data-ttu-id="8f90b-140">Digite o nome do InfoObject que você deseja pesquisar ou um nome parcial com o caractere curinga asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="8f90b-140">Enter the name of the InfoObject that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="8f90b-141">Ou use o caractere curinga asterisco sozinho para incluir todos os InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="8f90b-141">Or, use the asterisk wildcard character alone to include all InfoObjects.</span></span>  
  
 <span data-ttu-id="8f90b-142">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8f90b-142">**Description**</span></span>  
 <span data-ttu-id="8f90b-143">Insira a descrição ou uma descrição parcial com o caractere curinga asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="8f90b-143">Enter the description, or a partial description with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="8f90b-144">Ou use o caractere curinga asterisco sozinho para incluir todos os InfoObjects independentemente da descrição.</span><span class="sxs-lookup"><span data-stu-id="8f90b-144">Or, use the asterisk wildcard character alone to include all InfoObjects regardless of description.</span></span>  
  
 <span data-ttu-id="8f90b-145">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="8f90b-145">**Look up**</span></span>  
 <span data-ttu-id="8f90b-146">Pesquisar InfoObjects compatíveis que sejam definidos no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8f90b-146">Look up matching InfoObjects that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="8f90b-147">Resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="8f90b-147">Lookup Results</span></span>  
 <span data-ttu-id="8f90b-148">Depois que você clicar no botão Pesquisar, uma lista de InfoObjects no sistema SAP Netweaver BW é exibido em uma tabela com os seguintes cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="8f90b-148">After you click the Look up button, a list of the InfoObjects in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="8f90b-149">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="8f90b-149">**InfoObject**</span></span>  
 <span data-ttu-id="8f90b-150">Exibe o nome do InfoObject que está definido no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8f90b-150">Displays the name of the InfoObject that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="8f90b-151">**Texto (curto)**</span><span class="sxs-lookup"><span data-stu-id="8f90b-151">**Text (short)**</span></span>  
 <span data-ttu-id="8f90b-152">Exibe o texto curto associado ao InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8f90b-152">Displays the short text that is associated with the InfoObject.</span></span>  
  
 <span data-ttu-id="8f90b-153">Quando a lista de InfoObjects disponível é exibida, selecione o InfoObject que você quer e o destino preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="8f90b-153">When the list of available InfoObjects appears, select the InfoObject that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f90b-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f90b-154">See Also</span></span>  
 <span data-ttu-id="8f90b-155">[Criar InfoCube para os Dados da Transação](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="8f90b-155">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="8f90b-156">[Criar InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="8f90b-156">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="8f90b-157">[Criar InfoSource para os dados da transação](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="8f90b-157">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="8f90b-158">[Criar InfoSource para dados mestre](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="8f90b-158">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 <span data-ttu-id="8f90b-159">[Criar novo InfoObject](create-new-infoobject.md) </span><span class="sxs-lookup"><span data-stu-id="8f90b-159">[Create New InfoObject](create-new-infoobject.md) </span></span>  
 <span data-ttu-id="8f90b-160">[Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8f90b-160">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="8f90b-161">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="8f90b-161">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
