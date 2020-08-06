---
title: Destino SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a612ed91-b89b-4173-a0b1-0bce381e1e28
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a0d7c5b75da89e665dbe60bbd7e29ce74da67db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575984"
---
# <a name="sap-bw-destination"></a><span data-ttu-id="a5755-102">Destino SAP BW</span><span class="sxs-lookup"><span data-stu-id="a5755-102">SAP BW Destination</span></span>
  <span data-ttu-id="a5755-103">O destino SAP BW é o componente de destino do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-103">The SAP BW destination is the destination component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="a5755-104">Portanto, o destino do SAP BW carrega dados do fluxo de dados em um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em um sistema SAP Netweaver BW versão 7.</span><span class="sxs-lookup"><span data-stu-id="a5755-104">Thus, the SAP BW destination loads data from the data flow in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package into an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="a5755-105">Esse destinos tem uma entrada e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="a5755-105">This destination has one input and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5755-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a5755-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="a5755-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a5755-108">Para usar o destino SAP BW, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5755-108">To use the SAP BW destination, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="a5755-109">Prepare os objetos do SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="a5755-109">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="a5755-110">Conecte-se ao sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="a5755-110">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="a5755-111">Configure o destino SAP BW</span><span class="sxs-lookup"><span data-stu-id="a5755-111">Configure the SAP BW destination</span></span>](#bkmk_Configure_Destination)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-destination-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="a5755-112">Preparando os objetos do SAP Netweaver BW que o destino exige</span><span class="sxs-lookup"><span data-stu-id="a5755-112">Preparing the SAP Netweaver BW Objects That the Destination Requires</span></span>  
 <span data-ttu-id="a5755-113">O destino SAP BW exige que determinados objetos estejam no sistema SAP Netweaver BW antes que o destino possa funcionar.</span><span class="sxs-lookup"><span data-stu-id="a5755-113">The SAP BW destination requires that certain objects are in the SAP Netweaver BW system before the destination can function.</span></span> <span data-ttu-id="a5755-114">Se esses objetos ainda não existirem, siga estas etapas para criar e configurar esses objetos do sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-114">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5755-115">Para obter detalhes adicionais sobre esses objetos e essas etapas de configuração, consulte a documentação do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-115">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="a5755-116">Criar um novo sistema de origem:</span><span class="sxs-lookup"><span data-stu-id="a5755-116">Create a new Source System:</span></span>  
  
    1.  <span data-ttu-id="a5755-117">Selecione o tipo, **"Third Party/Staging BAPIs" (Terceiros/BAPIs de preparo)** .</span><span class="sxs-lookup"><span data-stu-id="a5755-117">Select the type, **"Third Party/Staging BAPIs"**.</span></span>  
  
    2.  <span data-ttu-id="a5755-118">Para **Communication Type with Target System (Tipo de Comunicação com o Sistema de Destino)** , selecione **Non-Unicode (Inactive MDMP Settings) (Não Unicode (configurações de MDMP inativo))** .</span><span class="sxs-lookup"><span data-stu-id="a5755-118">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    3.  <span data-ttu-id="a5755-119">Atribuir uma ID de programa apropriada</span><span class="sxs-lookup"><span data-stu-id="a5755-119">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="a5755-120">Atribua o sistema de origem a um InfoSource.</span><span class="sxs-lookup"><span data-stu-id="a5755-120">Assign the Source System to an InfoSource.</span></span>  
  
3.  <span data-ttu-id="a5755-121">Crie um InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="a5755-121">Create an InfoPackage.</span></span>  
  
     <span data-ttu-id="a5755-122">O InfoPackage é o objeto mais importante que é exigido pelo destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-122">The InfoPackage is the most important object that is required by the SAP BW destination.</span></span>  
  
 <span data-ttu-id="a5755-123">Você também pode criar InfoObjects, InfoCubes, InfoSources e InfoPackages adicionais que são necessários para oferecer suporte ao carregamento de dados no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-123">You can also create additional InfoObjects, InfoCubes, InfoSources, and InfoPackages that are required to support loading data into the SAP Netweaver BW system.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="a5755-124">Conectando-se ao sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="a5755-124">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="a5755-125">Para conectar-se ao sistema SAP Netweaver BW versão 7, o destino do SAP BW usará o gerenciador de conexões do SAP BW que faz parte do pacote do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-125">To connect to the SAP Netweaver BW version 7 system, the SAP BW destination uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="a5755-126">O gerenciador de conexões do SAP BW é o único gerenciador de conexões do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que o destino do SAP BW pode usar.</span><span class="sxs-lookup"><span data-stu-id="a5755-126">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW destination can use.</span></span>  
  
 <span data-ttu-id="a5755-127">Para obter mais informações sobre o gerenciador de conexões do SAP BW, consulte [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a5755-127">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-destination"></a><a name="bkmk_Configure_Destination"></a> <span data-ttu-id="a5755-128">Configurando o destino SAP BW</span><span class="sxs-lookup"><span data-stu-id="a5755-128">Configuring the SAP BW Destination</span></span>  
 <span data-ttu-id="a5755-129">É possível configurar o destino do SAP BW das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="a5755-129">You can configure the SAP BW destination in the following ways:</span></span>  
  
-   <span data-ttu-id="a5755-130">Pesquise e selecione o InfoPackage a ser usado para carregar dados.</span><span class="sxs-lookup"><span data-stu-id="a5755-130">Look up and select the InfoPackage to use to load data.</span></span>  
  
-   <span data-ttu-id="a5755-131">Mapeie cada coluna no fluxo de dados para o InfoObject apropriado no InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="a5755-131">Map each column in the data flow to the appropriate InfoObject in the InfoPackage.</span></span>  
  
-   <span data-ttu-id="a5755-132">Especifique quantas linhas de dados serão transferidas de cada vez configurando a propriedade `PackageSize`.</span><span class="sxs-lookup"><span data-stu-id="a5755-132">Specify how many rows of data will be transferred at a time by configuring the `PackageSize` property.</span></span>  
  
-   <span data-ttu-id="a5755-133">Escolha para aguardar até que o carregamento dos dados esteja concluído pelo sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-133">Choose to wait until the loading of data is completed by the SAP Netweaver BW system.</span></span>  
  
-   <span data-ttu-id="a5755-134">Escolha não acionar o InfoPackage, mas aguardar a notificação que o sistema SAP Netweaver BW iniciou o carregamento dos dados.</span><span class="sxs-lookup"><span data-stu-id="a5755-134">Choose not to trigger the InfoPackage, but to wait for notification that the SAP Netweaver BW system has started the loading of data.</span></span>  
  
-   <span data-ttu-id="a5755-135">Opcionalmente, acione uma outra cadeia de processo depois que o carregamento dos dados estiver concluído.</span><span class="sxs-lookup"><span data-stu-id="a5755-135">Optionally, trigger another process chain after the loading of data is completed.</span></span>  
  
-   <span data-ttu-id="a5755-136">Opcionalmente, crie os objetos do SAP Netweaver BW exigidos pelo destino.</span><span class="sxs-lookup"><span data-stu-id="a5755-136">Optionally, create the SAP Netweaver BW objects that are required by the destination.</span></span> <span data-ttu-id="a5755-137">Isso inclui a criação de InfoObjects, InfoCubes, InfoSources e InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="a5755-137">This includes creating InfoObjects, InfoCubes, InfoSources, and InfoPackages.</span></span>  
  
-   <span data-ttu-id="a5755-138">Teste o carregamento de dados com as opções que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="a5755-138">Test the loading of data with the options that you have selected.</span></span>  
  
 <span data-ttu-id="a5755-139">Você também pode habilitar o log das chamadas de função de RFC pelo destino.</span><span class="sxs-lookup"><span data-stu-id="a5755-139">You can also enable logging of RFC function calls by the destination.</span></span> <span data-ttu-id="a5755-140">(Esse log é separado do log opcional que você pode habilitar em pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Você habilita o log das chamadas de função de RFC quando configura o gerenciador de conexões do SAP BW que o destino usará.</span><span class="sxs-lookup"><span data-stu-id="a5755-140">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the destination will use.</span></span> <span data-ttu-id="a5755-141">Para obter mais informações sobre como configurar o gerenciador de conexões do SAP BW, consulte [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a5755-141">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="a5755-142">Se você não souber todos os valores necessários para configurar o destino, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="a5755-142">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a5755-143">Para obter um passo a passo que demonstre como configurar e usar o gerenciador de conexões do SAP BW, a origem e o destino, consulte o white paper [Usando o SQL Server 2008 Integration Services com SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="a5755-143">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="a5755-144">Este white paper também mostra como configurar os objetos necessários no SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-144">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-destination"></a><span data-ttu-id="a5755-145">Usando o Designer SSIS para configurar o destino</span><span class="sxs-lookup"><span data-stu-id="a5755-145">Using the SSIS Designer to Configure the Destination</span></span>  
 <span data-ttu-id="a5755-146">Para obter mais informações sobre as propriedades do destino do SAP BW que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="a5755-146">For more information about the properties of the SAP BW destination that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a5755-147">Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="a5755-147">SAP BW Destination Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="a5755-148">Editor de Destino SAP BW &#40;Página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="a5755-148">SAP BW Destination Editor &#40;Mappings Page&#41;</span></span>](sap-bw-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="a5755-149">Editor de Destino SAP BW &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="a5755-149">SAP BW Destination Editor &#40;Error Output Page&#41;</span></span>](sap-bw-destination-editor-error-output-page.md)  
  
-   [<span data-ttu-id="a5755-150">Editor de Destino SAP BW &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="a5755-150">SAP BW Destination Editor &#40;Advanced Page&#41;</span></span>](sap-bw-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="a5755-151">Quando você estiver configurando o destino do SAP BW, também poderá usar várias caixas de diálogo para pesquisar ou criar objetos do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a5755-151">While you are configuring the SAP BW destination, you can also use various dialog boxes to look up or to create SAP Netweaver BW objects.</span></span> <span data-ttu-id="a5755-152">Para obter mais informações sobre essas caixas de diálogo, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a5755-152">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a5755-153">Pesquisar InfoPackage</span><span class="sxs-lookup"><span data-stu-id="a5755-153">Look Up InfoPackage</span></span>](look-up-infopackage.md)  
  
-   [<span data-ttu-id="a5755-154">Criar novo InfoObject</span><span class="sxs-lookup"><span data-stu-id="a5755-154">Create New InfoObject</span></span>](create-new-infoobject.md)  
  
-   [<span data-ttu-id="a5755-155">Criar InfoCube para os dados da transação</span><span class="sxs-lookup"><span data-stu-id="a5755-155">Create InfoCube for Transaction Data</span></span>](create-infocube-for-transaction-data.md)  
  
-   [<span data-ttu-id="a5755-156">Pesquisar InfoObject</span><span class="sxs-lookup"><span data-stu-id="a5755-156">Look Up InfoObject</span></span>](look-up-infoobject.md)  
  
-   [<span data-ttu-id="a5755-157">Criar InfoSource</span><span class="sxs-lookup"><span data-stu-id="a5755-157">Create InfoSource</span></span>](create-infosource.md)  
  
-   [<span data-ttu-id="a5755-158">Criar InfoSource para os dados da transação</span><span class="sxs-lookup"><span data-stu-id="a5755-158">Create InfoSource for Transaction Data</span></span>](create-infosource-for-transaction-data.md)  
  
-   [<span data-ttu-id="a5755-159">Criar InfoSource para dados mestre</span><span class="sxs-lookup"><span data-stu-id="a5755-159">Create InfoSource for Master Data</span></span>](create-infosource-for-master-data.md)  
  
-   [<span data-ttu-id="a5755-160">Criar InfoPackage</span><span class="sxs-lookup"><span data-stu-id="a5755-160">Create InfoPackage</span></span>](create-infopackage.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5755-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5755-161">See Also</span></span>  
 [<span data-ttu-id="a5755-162">Componentes do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a5755-162">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
