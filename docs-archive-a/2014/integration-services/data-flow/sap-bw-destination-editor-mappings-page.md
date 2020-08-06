---
title: Editor de destino SAP BW (página Mapeamentos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dfa1f1d6-6b64-4331-bdc5-eaa8b7aa41a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c4c2803be3e2649f7425a2974dae8ac0a80fae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678886"
---
# <a name="sap-bw-destination-editor-mappings-page"></a><span data-ttu-id="bd3d3-102">Editor de Destino de SAP BW (página Mapeamentos)</span><span class="sxs-lookup"><span data-stu-id="bd3d3-102">SAP BW Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="bd3d3-103">Use a página **Mapeamentos** do **Editor de Destino SAP BW** para mapear colunas de entrada para colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-103">Use the **Mappings** page of the **SAP BW Destination Editor** to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="bd3d3-104">Para saber mais sobre o destino SAP BW do Connector 1.1 do [!INCLUDE[msCoName](../../includes/msconame-md.md)] para SAP BW, consulte [Destino SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="bd3d3-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd3d3-105">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="bd3d3-106">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="bd3d3-107">**Para abrir a página Mapeamentos**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-107">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="bd3d3-108">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="bd3d3-109">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="bd3d3-110">No **Editor de Destino SAP BW**, clique em **Mapeamentos** para abrir a página **Mapeamentos** do editor.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-110">In the **SAP BW Destination Editor**, click **Mappings** to open the **Mappings** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bd3d3-111">Opções</span><span class="sxs-lookup"><span data-stu-id="bd3d3-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd3d3-112">Se você não souber todos os valores necessários para configurar o destino, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="bd3d3-113">A página **Mapeamentos** do **Editor de destino SAP BW consiste** em duas seções:</span><span class="sxs-lookup"><span data-stu-id="bd3d3-113">The **Mappings** page of the **SAP BW Destination Editor consists** of two sections:</span></span>  
  
-   <span data-ttu-id="bd3d3-114">A seção superior mostra as colunas de entrada e destino disponíveis e permite criar mapeamentos entre esses dois tipos de colunas.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-114">The upper section shows the available input and destination columns and lets you create mappings between these two types of columns.</span></span>  
  
-   <span data-ttu-id="bd3d3-115">A seção inferior é uma tabela que listas quais colunas de entrada foram mapeadas para quais colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-115">The lower section is a table that lists which input columns have been mapped to which output columns.</span></span>  
  
### <a name="upper-section-options"></a><span data-ttu-id="bd3d3-116">Opções da seção superior</span><span class="sxs-lookup"><span data-stu-id="bd3d3-116">Upper Section Options</span></span>  
 <span data-ttu-id="bd3d3-117">A seção superior tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bd3d3-117">The upper section has the following options:</span></span>  
  
 <span data-ttu-id="bd3d3-118">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-118">**Available Input Columns**</span></span>  
 <span data-ttu-id="bd3d3-119">Exiba a lista das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-119">View the list of available input columns.</span></span>  
  
 <span data-ttu-id="bd3d3-120">Para mapear uma coluna de entrada para uma coluna de destino, arraste uma coluna da lista **Colunas de Entrada Disponíveis** e solte essa coluna em uma coluna na lista **Colunas de Destino Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="bd3d3-120">To map an input column to a destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="bd3d3-121">**Colunas de Destino Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-121">**Available Destination Columns**</span></span>  
 <span data-ttu-id="bd3d3-122">Exiba a lista de colunas de destino disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-122">View the list of available destination columns.</span></span>  
  
 <span data-ttu-id="bd3d3-123">Para mapear uma coluna de entrada para uma coluna de destino, arraste uma coluna da lista **Colunas de Entrada Disponíveis** e solte essa coluna em uma coluna na lista **Colunas de Destino Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="bd3d3-123">To map an input column to destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="bd3d3-124">A seção superior também tem um menu de contexto que você pode abrir clicando com o botão direito do mouse no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-124">The upper section also has a context menu that you can open by right-clicking on the background.</span></span> <span data-ttu-id="bd3d3-125">Esse menu de contexto contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bd3d3-125">This context menu contains the following options:</span></span>  
  
-   <span data-ttu-id="bd3d3-126">**Selecionar Todos os Mapeamentos**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-126">**Select All Mappings**</span></span>  
  
-   <span data-ttu-id="bd3d3-127">**Excluir Mapeamentos Selecionados**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-127">**Delete Selected Mappings**</span></span>  
  
-   <span data-ttu-id="bd3d3-128">**Mapear Itens Correspondendo Nomes**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-128">**Map Items by Matching Names**</span></span>  
  
### <a name="lower-section-columns"></a><span data-ttu-id="bd3d3-129">Colunas da seção inferior</span><span class="sxs-lookup"><span data-stu-id="bd3d3-129">Lower Section Columns</span></span>  
 <span data-ttu-id="bd3d3-130">A seção inferior é uma tabela de mapeamentos, e tem as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="bd3d3-130">The lower section is a table of the mappings, and has the following columns:</span></span>  
  
 <span data-ttu-id="bd3d3-131">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-131">**Input Column**</span></span>  
 <span data-ttu-id="bd3d3-132">Visualize as colunas de entrada que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-132">View the input columns that you have selected.</span></span>  
  
 <span data-ttu-id="bd3d3-133">Para mapear uma coluna de entrada diferente para a mesma coluna de destino, selecione uma coluna diferente de entrada na lista.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-133">To map a different input column to the same destination column, select a different input column in the list.</span></span> <span data-ttu-id="bd3d3-134">Para remover um mapeamento, selecione **\<ignore>** para excluir a coluna de entrada da saída.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-134">To remove a mapping, select **\<ignore>** to exclude the input column from the output.</span></span>  
  
 <span data-ttu-id="bd3d3-135">**Coluna de Destino**</span><span class="sxs-lookup"><span data-stu-id="bd3d3-135">**Destination Column**</span></span>  
 <span data-ttu-id="bd3d3-136">Visualize cada coluna de destino disponível, esteja essa coluna mapeada ou não.</span><span class="sxs-lookup"><span data-stu-id="bd3d3-136">View each available destination column, regardless of whether that column is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3d3-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bd3d3-137">See Also</span></span>  
 <span data-ttu-id="bd3d3-138">[Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="bd3d3-138">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="bd3d3-139">[Editor de Destino SAP BW &#40;Página Saída de Erro&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="bd3d3-139">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="bd3d3-140">[Editor de Destino SAP BW &#40;Página Avançado&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="bd3d3-140">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="bd3d3-141">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="bd3d3-141">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
