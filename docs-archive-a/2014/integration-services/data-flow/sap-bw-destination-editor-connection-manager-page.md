---
title: Editor de destino SAP BW (página Gerenciador de Conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 04ae38f8-5287-45a3-826a-8aac5dd15a91
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd628f1a0fec09490e0d3720610d1232882ed92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678891"
---
# <a name="sap-bw-destination-editor-connection-manager-page"></a><span data-ttu-id="aa628-102">Editor de Destino SAP BW (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="aa628-102">SAP BW Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="aa628-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Destino SAP BW** para selecionar o gerenciador de conexões do SAP BW que o destino de SAP BW usará.</span><span class="sxs-lookup"><span data-stu-id="aa628-103">Use the **Connection Manager** page of the **SAP BW Destination Editor** to select the SAP BW connection manager that the SAP BW destination will use.</span></span> <span data-ttu-id="aa628-104">Nesta página, você também seleciona os parâmetros para carregar os dados no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="aa628-104">On this page, you also select the parameters for loading the data into the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="aa628-105">Para saber mais sobre o destino SAP BW do Connector 1.1 do [!INCLUDE[msCoName](../../includes/msconame-md.md)] para SAP BW, consulte [Destino SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-105">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa628-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="aa628-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="aa628-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="aa628-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="aa628-108">**Para abrir a página Gerenciador de Conexões**</span><span class="sxs-lookup"><span data-stu-id="aa628-108">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="aa628-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="aa628-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="aa628-110">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="aa628-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="aa628-111">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="aa628-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa628-112">Opções</span><span class="sxs-lookup"><span data-stu-id="aa628-112">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa628-113">Se você não souber todos os valores necessários para configurar o destino, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="aa628-113">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="aa628-114">**Gerenciador de conexões SAP BW**</span><span class="sxs-lookup"><span data-stu-id="aa628-114">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="aa628-115">Selecione um gerenciador de conexões existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="aa628-115">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="aa628-116">**Novo**</span><span class="sxs-lookup"><span data-stu-id="aa628-116">**New**</span></span>  
 <span data-ttu-id="aa628-117">Crie um novo gerenciador de conexões, usando a caixa de diálogo **Gerenciador de Conexões SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="aa628-117">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="aa628-118">**Testar carga**</span><span class="sxs-lookup"><span data-stu-id="aa628-118">**Test Load**</span></span>  
 <span data-ttu-id="aa628-119">Execute um teste do processo de carga que usa as configurações selecionadas e não carrega nenhuma linha.</span><span class="sxs-lookup"><span data-stu-id="aa628-119">Perform a test of the loading process that uses the settings that you have selected and loads zero rows.</span></span>  
  
### <a name="infopackageinfosource-options"></a><span data-ttu-id="aa628-120">Opções do InfoPackage/InfoSource</span><span class="sxs-lookup"><span data-stu-id="aa628-120">InfoPackage/InfoSource Options</span></span>  
 <span data-ttu-id="aa628-121">Você não precisa saber e inserir esses valores com antecedência.</span><span class="sxs-lookup"><span data-stu-id="aa628-121">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="aa628-122">Use o botão **Pesquisar** para localizar e selecionar o InfoPackage apropriado.</span><span class="sxs-lookup"><span data-stu-id="aa628-122">Use the **Look up** button to find and select the appropriate InfoPackage.</span></span> <span data-ttu-id="aa628-123">Depois de selecionar um InfoPackage, o componente insere os valores apropriados para essas opções.</span><span class="sxs-lookup"><span data-stu-id="aa628-123">After you select an InfoPackage, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="aa628-124">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="aa628-124">**InfoPackage**</span></span>  
 <span data-ttu-id="aa628-125">Digite o nome do InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="aa628-125">Enter the name of the InfoPackage.</span></span>  
  
 <span data-ttu-id="aa628-126">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="aa628-126">**InfoSource**</span></span>  
 <span data-ttu-id="aa628-127">Digite o nome do InfoSource.</span><span class="sxs-lookup"><span data-stu-id="aa628-127">Enter the name of the InfoSource.</span></span>  
  
 <span data-ttu-id="aa628-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="aa628-128">**Type**</span></span>  
 <span data-ttu-id="aa628-129">Digite o caractere único que identifica o tipo do InfoSource.</span><span class="sxs-lookup"><span data-stu-id="aa628-129">Enter the single-character that identifies the type of the InfoSource.</span></span> <span data-ttu-id="aa628-130">A tabela a seguir lista os valores aceitáveis de caractere único.</span><span class="sxs-lookup"><span data-stu-id="aa628-130">The following table lists the acceptable single-character values.</span></span>  
  
|<span data-ttu-id="aa628-131">Valor</span><span class="sxs-lookup"><span data-stu-id="aa628-131">Value</span></span>|<span data-ttu-id="aa628-132">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa628-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aa628-133">**D**</span><span class="sxs-lookup"><span data-stu-id="aa628-133">**D**</span></span>|<span data-ttu-id="aa628-134">Dados da transação</span><span class="sxs-lookup"><span data-stu-id="aa628-134">Transaction data</span></span>|  
|<span data-ttu-id="aa628-135">**M**</span><span class="sxs-lookup"><span data-stu-id="aa628-135">**M**</span></span>|<span data-ttu-id="aa628-136">Dados mestres</span><span class="sxs-lookup"><span data-stu-id="aa628-136">Master data</span></span>|  
|<span data-ttu-id="aa628-137">**T**</span><span class="sxs-lookup"><span data-stu-id="aa628-137">**T**</span></span>|<span data-ttu-id="aa628-138">Textos</span><span class="sxs-lookup"><span data-stu-id="aa628-138">Texts</span></span>|  
|<span data-ttu-id="aa628-139">**H**</span><span class="sxs-lookup"><span data-stu-id="aa628-139">**H**</span></span>|<span data-ttu-id="aa628-140">Dados da hierarquia</span><span class="sxs-lookup"><span data-stu-id="aa628-140">Hierarchy data</span></span>|  
  
 <span data-ttu-id="aa628-141">**Sistema lógico**</span><span class="sxs-lookup"><span data-stu-id="aa628-141">**Logical system**</span></span>  
 <span data-ttu-id="aa628-142">Insira o nome do sistema lógico que está associado ao InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="aa628-142">Enter the name of the logical system that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="aa628-143">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="aa628-143">**Look up**</span></span>  
 <span data-ttu-id="aa628-144">Pesquisar o InfoPackage usando a caixa de diálogo **Pesquisar InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="aa628-144">Look up the InfoPackage by using the **Look Up InfoPackage** dialog box.</span></span> <span data-ttu-id="aa628-145">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up InfoPackage](look-up-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-145">For more information about this dialog box, see [Look Up InfoPackage](look-up-infopackage.md).</span></span>  
  
### <a name="rfc-destination-options"></a><span data-ttu-id="aa628-146">Opções de destino RFC</span><span class="sxs-lookup"><span data-stu-id="aa628-146">RFC Destination Options</span></span>  
 <span data-ttu-id="aa628-147">Você não precisa saber e inserir esses valores com antecedência.</span><span class="sxs-lookup"><span data-stu-id="aa628-147">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="aa628-148">Use o botão **Pesquisar** para localizar e selecionar o destino RFC apropriado.</span><span class="sxs-lookup"><span data-stu-id="aa628-148">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="aa628-149">Depois de selecionar um destino RFC, o componente insere os valores apropriados para essas opções.</span><span class="sxs-lookup"><span data-stu-id="aa628-149">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="aa628-150">**Host do gateway**</span><span class="sxs-lookup"><span data-stu-id="aa628-150">**Gateway host**</span></span>  
 <span data-ttu-id="aa628-151">Digite o nome do servidor ou endereço IP do host do gateway.</span><span class="sxs-lookup"><span data-stu-id="aa628-151">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="aa628-152">Em geral, o nome ou o endereço IP é o mesmo que o servidor de aplicativos do SAP.</span><span class="sxs-lookup"><span data-stu-id="aa628-152">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="aa628-153">**Serviço do gateway**</span><span class="sxs-lookup"><span data-stu-id="aa628-153">**Gateway service**</span></span>  
 <span data-ttu-id="aa628-154">Digite o nome do serviço de gateway, no formato `sapgwNN`, em que `NN` é o número do sistema.</span><span class="sxs-lookup"><span data-stu-id="aa628-154">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="aa628-155">**ID do Programa**</span><span class="sxs-lookup"><span data-stu-id="aa628-155">**Program ID**</span></span>  
 <span data-ttu-id="aa628-156">Insira a ID do programa que está associada ao destino RFC.</span><span class="sxs-lookup"><span data-stu-id="aa628-156">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="aa628-157">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="aa628-157">**Look up**</span></span>  
 <span data-ttu-id="aa628-158">Pesquisar o destino RFC usando a caixa de diálogo **Pesquisar Destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="aa628-158">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="aa628-159">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-159">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="create-sap-bw-objects-options"></a><span data-ttu-id="aa628-160">Criar opções de objetos SAP BW</span><span class="sxs-lookup"><span data-stu-id="aa628-160">Create SAP BW Objects Options</span></span>  
 <span data-ttu-id="aa628-161">**Selecionar tipo de objeto**</span><span class="sxs-lookup"><span data-stu-id="aa628-161">**Select object type**</span></span>  
 <span data-ttu-id="aa628-162">Selecione o tipo de objeto SAP Netweaver BW que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="aa628-162">Select the type of SAP Netweaver BW object that you want to create.</span></span> <span data-ttu-id="aa628-163">Você pode selecionar um dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="aa628-163">You can select one of the following types:</span></span>  
  
-   <span data-ttu-id="aa628-164">InfoObject</span><span class="sxs-lookup"><span data-stu-id="aa628-164">InfoObject</span></span>  
  
-   <span data-ttu-id="aa628-165">InfoCube</span><span class="sxs-lookup"><span data-stu-id="aa628-165">InfoCube</span></span>  
  
-   <span data-ttu-id="aa628-166">InfoSource</span><span class="sxs-lookup"><span data-stu-id="aa628-166">InfoSource</span></span>  
  
-   <span data-ttu-id="aa628-167">InfoPackage</span><span class="sxs-lookup"><span data-stu-id="aa628-167">InfoPackage</span></span>  
  
 <span data-ttu-id="aa628-168">**Criar**</span><span class="sxs-lookup"><span data-stu-id="aa628-168">**Create**</span></span>  
 <span data-ttu-id="aa628-169">Crie o tipo selecionado de objeto do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="aa628-169">Create the selected type of SAP Netweaver BW object.</span></span>  
  
|<span data-ttu-id="aa628-170">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="aa628-170">Object Type</span></span>|<span data-ttu-id="aa628-171">Result</span><span class="sxs-lookup"><span data-stu-id="aa628-171">Result</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="aa628-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="aa628-172">**InfoObject**</span></span>|<span data-ttu-id="aa628-173">Crie um novo InfoObject usando a caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="aa628-173">Create a new InfoObject by using the **Create New InfoObject** dialog box.</span></span> <span data-ttu-id="aa628-174">Para obter mais informações sobre essa caixa de diálogo, consulte [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-174">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>|  
|<span data-ttu-id="aa628-175">**InfoCube**</span><span class="sxs-lookup"><span data-stu-id="aa628-175">**InfoCube**</span></span>|<span data-ttu-id="aa628-176">Crie um novo InfoCube usando a caixa de diálogo **Criar InfoCube para os Dados da Transação** .</span><span class="sxs-lookup"><span data-stu-id="aa628-176">Create a new InfoCube by using the **Create InfoCube for Transaction Data** dialog box.</span></span> <span data-ttu-id="aa628-177">Para obter mais informações sobre essa caixa de diálogo, consulte [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-177">For more information about this dialog box, see [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span></span>|  
|<span data-ttu-id="aa628-178">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="aa628-178">**InfoSource**</span></span>|<span data-ttu-id="aa628-179">Crie um novo InfoSource usando a caixa de diálogo **Criar InfoSource** e, em seguida, **Criar InfoSource para os Dados da Transação** ou **Criar InfoSource para Dados Mestres** .</span><span class="sxs-lookup"><span data-stu-id="aa628-179">Create a new InfoSource by using the **Create InfoSource** dialog box, and then by using the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span> <span data-ttu-id="aa628-180">Para obter mais informações sobre essas caixas de diálogo, consulte [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) e [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-180">For more information about these dialog boxes, see [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) and [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>|  
|<span data-ttu-id="aa628-181">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="aa628-181">**InfoPackage**</span></span>|<span data-ttu-id="aa628-182">Crie um novo InfoPackage usando a caixa de diálogo **Criar InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="aa628-182">Create a new InfoPackage by using the **Create InfoPackage** dialog box.</span></span> <span data-ttu-id="aa628-183">Para obter mais informações sobre essa caixa de diálogo, consulte [Create InfoPackage](create-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="aa628-183">For more information about this dialog box, see [Create InfoPackage](create-infopackage.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa628-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa628-184">See Also</span></span>  
 <span data-ttu-id="aa628-185">[Editor de Destino SAP BW &#40;Página Mapeamentos&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="aa628-185">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="aa628-186">[Editor de Destino SAP BW &#40;Página Saída de Erro&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="aa628-186">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="aa628-187">[Editor de Destino SAP BW &#40;Página Avançado&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="aa628-187">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="aa628-188">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="aa628-188">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
