---
title: Pesquisar cadeia de processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f6303ea4-fbbf-4cba-bc60-828df62be8c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e0d3743071d018a8a82f60eeaf04fd86dec3e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680577"
---
# <a name="look-up-process-chain"></a><span data-ttu-id="a29d3-102">Pesquisar cadeia de processo</span><span class="sxs-lookup"><span data-stu-id="a29d3-102">Look Up Process Chain</span></span>
  <span data-ttu-id="a29d3-103">Use a caixa de diálogo **Pesquisar Cadeia de Processo** para pesquisar uma cadeia de processo definida no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a29d3-103">Use the **Look Up Process Chain** dialog box to look up a process chain that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="a29d3-104">Quando a lista de cadeias de processo disponível é exibida, selecione a cadeia que você quer e a origem preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="a29d3-104">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="a29d3-105">A origem SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW usa a caixa de diálogo **Pesquisar Cadeia de Processo** .</span><span class="sxs-lookup"><span data-stu-id="a29d3-105">The SAP BW source of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="a29d3-106">Para saber mais sobre a origem de SAP BW, consulte [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="a29d3-106">To learn more about the SAP BW source, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a29d3-107">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a29d3-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a29d3-108">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="a29d3-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a29d3-109">**Para abrir a caixa de diálogo Pesquisar Cadeia de Processo**</span><span class="sxs-lookup"><span data-stu-id="a29d3-109">**To open the Look Up Process Chain dialog box**</span></span>  
  
1.  <span data-ttu-id="a29d3-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a29d3-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="a29d3-111">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a29d3-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="a29d3-112">No **Editor de Origem SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="a29d3-112">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="a29d3-113">Na caixa de grupo **Cadeia de processo** , clique em **Pesquisar** para exibir a caixa de diálogo **Pesquisar Cadeia de Processo** .</span><span class="sxs-lookup"><span data-stu-id="a29d3-113">In the **Process Chain** group box, click **Look up** to display the **Look Up Process Chain** dialog box.</span></span>  
  
     <span data-ttu-id="a29d3-114">A caixa de grupo **Cadeia de processo** aparecerá apenas se o valor de **Modo de Execução** for **P – Disparar Cadeia de Processo**.</span><span class="sxs-lookup"><span data-stu-id="a29d3-114">The **Process Chain** group box appears only if the value for **Execution mode** is **P - Trigger process chain**.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="a29d3-115">Opções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="a29d3-115">Lookup Options</span></span>  
 <span data-ttu-id="a29d3-116">Nos campos de pesquisa, você pode filtrar os resultados usando o caractere curinga asterisco (\*) ou usando uma cadeia de caracteres parcial em combinação com o caractere curinga asterisco.</span><span class="sxs-lookup"><span data-stu-id="a29d3-116">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="a29d3-117">No entanto, se você deixar um campo de pesquisa vazio, a operação de pesquisa corresponderá apenas a cadeias de caracteres vazias nesse campo.</span><span class="sxs-lookup"><span data-stu-id="a29d3-117">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="a29d3-118">**Cadeia de processo**</span><span class="sxs-lookup"><span data-stu-id="a29d3-118">**Process chain**</span></span>  
 <span data-ttu-id="a29d3-119">Digite o nome da cadeia de processo que você deseja pesquisar ou insira um nome parcial com o caractere curinga asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="a29d3-119">Enter the name of the process chain that you want to look up, or enter a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="a29d3-120">Ou use o caractere curinga asterisco sozinho para incluir todas as cadeias de processo.</span><span class="sxs-lookup"><span data-stu-id="a29d3-120">Or, use the asterisk wildcard character alone to include all process chains.</span></span>  
  
 <span data-ttu-id="a29d3-121">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="a29d3-121">**Look up**</span></span>  
 <span data-ttu-id="a29d3-122">Pesquisar cadeias de processo compatíveis que sejam definidos no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a29d3-122">Look up matching process chains that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="a29d3-123">Resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="a29d3-123">Lookup Results</span></span>  
 <span data-ttu-id="a29d3-124">Depois que você clicar no botão Pesquisar, uma lista de cadeias de processo no sistema SAP Netweaver BW é exibido em uma tabela com os seguintes cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="a29d3-124">After you click the Look up button, a list of the process chains in the SAP Netweaver BW system appears in a table with the following column headings:</span></span>  
  
 <span data-ttu-id="a29d3-125">**Cadeia de processo**</span><span class="sxs-lookup"><span data-stu-id="a29d3-125">**Process Chain**</span></span>  
 <span data-ttu-id="a29d3-126">Exibe o nome da cadeia de processo que está definida no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a29d3-126">Displays the name of the process chain that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="a29d3-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a29d3-127">**Description**</span></span>  
 <span data-ttu-id="a29d3-128">Exibe a descrição da cadeia de processo.</span><span class="sxs-lookup"><span data-stu-id="a29d3-128">Displays the description of the process chain.</span></span>  
  
 <span data-ttu-id="a29d3-129">Quando a lista de cadeias de processo disponível é exibida, selecione a cadeia que você quer e a origem preencherá as opções associadas com os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="a29d3-129">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29d3-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a29d3-130">See Also</span></span>  
 <span data-ttu-id="a29d3-131">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a29d3-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a29d3-132">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a29d3-132">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
