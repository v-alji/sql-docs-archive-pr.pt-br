---
title: Pesquisar InfoPackage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7c0cb7a4-cd07-44cc-85cb-eb1ad91f85fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e45477e8faeed07faa114850e10a3bc4bbcf170
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680578"
---
# <a name="look-up-infopackage"></a><span data-ttu-id="b78e7-102">Pesquisar InfoPackage</span><span class="sxs-lookup"><span data-stu-id="b78e7-102">Look Up InfoPackage</span></span>
  <span data-ttu-id="b78e7-103">Use a caixa de diálogo **Pesquisar InfoPackage** para pesquisar um InfoPackage definido no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b78e7-103">Use the **Look Up InfoPackage** dialog box to look up an InfoPackage that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="b78e7-104">Quando a lista de InfoPackages é exibida, selecione o InfoPackage que você quer e o destino preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="b78e7-104">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="b78e7-105">O destino SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW usa a caixa de diálogo **Pesquisar Cadeia de Processo** .</span><span class="sxs-lookup"><span data-stu-id="b78e7-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="b78e7-106">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b78e7-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b78e7-107">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b78e7-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="b78e7-108">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="b78e7-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="b78e7-109">**Para abrir a caixa de diálogo Pesquisar InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b78e7-109">**To open the Look Up InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="b78e7-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b78e7-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="b78e7-111">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b78e7-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="b78e7-112">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="b78e7-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="b78e7-113">Na página **Gerenciador de Conexões** , na caixa de grupo **InfoPackage/InfoSource** , clique em **Pesquisar** para exibir a caixa de diálogo **Pesquisar InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="b78e7-113">On the **Connection Manager** page, in the **InfoPackage/InfoSource** group box, click **Look up** to display the **Look Up InfoPackage** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="b78e7-114">Opções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b78e7-114">Lookup Options</span></span>  
 <span data-ttu-id="b78e7-115">Nos campos de pesquisa, você pode filtrar os resultados usando o caractere curinga asterisco (\*) ou usando uma cadeia de caracteres parcial em combinação com o caractere curinga asterisco.</span><span class="sxs-lookup"><span data-stu-id="b78e7-115">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="b78e7-116">No entanto, se você deixar um campo de pesquisa vazio, a operação de pesquisa corresponderá apenas a cadeias de caracteres vazias nesse campo.</span><span class="sxs-lookup"><span data-stu-id="b78e7-116">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="b78e7-117">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b78e7-117">**InfoPackage**</span></span>  
 <span data-ttu-id="b78e7-118">Digite o nome do InfoPackage que você deseja pesquisar ou um nome parcial com o caractere curinga asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="b78e7-118">Enter the name of the InfoPackage that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="b78e7-119">Ou use o caractere curinga asterisco sozinho para incluir todos os InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="b78e7-119">Or, use the asterisk wildcard character alone to include all InfoPackages.</span></span>  
  
 <span data-ttu-id="b78e7-120">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="b78e7-120">**InfoSource**</span></span>  
 <span data-ttu-id="b78e7-121">Digite o nome do InfoSource ou um nome parcial com o caractere curinga asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="b78e7-121">Enter the name of the InfoSource, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="b78e7-122">Ou use o caractere curinga asterisco sozinho para incluir todos os InfoPackages independentemente do InfoSource.</span><span class="sxs-lookup"><span data-stu-id="b78e7-122">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of InfoSource.</span></span>  
  
 <span data-ttu-id="b78e7-123">**Sistema de origem**</span><span class="sxs-lookup"><span data-stu-id="b78e7-123">**Source system**</span></span>  
 <span data-ttu-id="b78e7-124">Digite o nome do sistema de origem ou um nome parcial com o caractere curinga asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="b78e7-124">Enter the name of the source system, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="b78e7-125">Ou use o caractere curinga asterisco sozinho para incluir todos os InfoPackages independentemente dos sistemas de origem.</span><span class="sxs-lookup"><span data-stu-id="b78e7-125">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of source systems.</span></span>  
  
 <span data-ttu-id="b78e7-126">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="b78e7-126">**Look up**</span></span>  
 <span data-ttu-id="b78e7-127">Pesquisar InfoPackages compatíveis que sejam definidos no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b78e7-127">Look up matching InfoPackages that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="b78e7-128">Resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="b78e7-128">Lookup Results</span></span>  
 <span data-ttu-id="b78e7-129">Depois que você clicar no botão Pesquisar, uma lista de InfoPackages no sistema SAP Netweaver BW é exibido em uma tabela com os seguintes cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="b78e7-129">After you click the Look up button, a list of the InfoPackages in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="b78e7-130">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b78e7-130">**InfoPackage**</span></span>  
 <span data-ttu-id="b78e7-131">Exibe o nome do InfoPackage que está definido no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b78e7-131">Displays the name of the InfoPackage that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="b78e7-132">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b78e7-132">**Type**</span></span>  
 <span data-ttu-id="b78e7-133">Exibe o tipo do InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="b78e7-133">Displays the type of the InfoPackage.</span></span> <span data-ttu-id="b78e7-134">A tabela a seguir lista os valores possíveis do tipo.</span><span class="sxs-lookup"><span data-stu-id="b78e7-134">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="b78e7-135">Valor</span><span class="sxs-lookup"><span data-stu-id="b78e7-135">Value</span></span>|<span data-ttu-id="b78e7-136">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b78e7-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b78e7-137">Trans.</span><span class="sxs-lookup"><span data-stu-id="b78e7-137">Trans.</span></span>|<span data-ttu-id="b78e7-138">Dados da transação.</span><span class="sxs-lookup"><span data-stu-id="b78e7-138">Transaction data.</span></span>|  
|<span data-ttu-id="b78e7-139">Atr.</span><span class="sxs-lookup"><span data-stu-id="b78e7-139">Attr.</span></span>|<span data-ttu-id="b78e7-140">Dados de atributo</span><span class="sxs-lookup"><span data-stu-id="b78e7-140">Attribute data.</span></span>|  
|<span data-ttu-id="b78e7-141">Textos</span><span class="sxs-lookup"><span data-stu-id="b78e7-141">Texts</span></span>|<span data-ttu-id="b78e7-142">Textos.</span><span class="sxs-lookup"><span data-stu-id="b78e7-142">Texts.</span></span>|  
  
 <span data-ttu-id="b78e7-143">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b78e7-143">**Description**</span></span>  
 <span data-ttu-id="b78e7-144">Exibe a descrição do InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="b78e7-144">Displays the description of the InfoPackage.</span></span>  
  
 <span data-ttu-id="b78e7-145">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="b78e7-145">**InfoSource**</span></span>  
 <span data-ttu-id="b78e7-146">Exibe o nome do InfoSource, se houver, associado ao InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="b78e7-146">Displays the name of the InfoSource, if any, that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="b78e7-147">**Source System**</span><span class="sxs-lookup"><span data-stu-id="b78e7-147">**Source System**</span></span>  
 <span data-ttu-id="b78e7-148">Exibe o nome do sistema de origem.</span><span class="sxs-lookup"><span data-stu-id="b78e7-148">Displays the name of the source system.</span></span>  
  
 <span data-ttu-id="b78e7-149">Quando a lista de InfoPackages é exibida, selecione o InfoPackage que você quer e o destino preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="b78e7-149">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b78e7-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b78e7-150">See Also</span></span>  
 <span data-ttu-id="b78e7-151">[Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b78e7-151">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="b78e7-152">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="b78e7-152">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
