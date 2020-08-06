---
title: Editor de Origem SAP BW (página Colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c2ec8bb7-be9b-4783-ad88-32512de784b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba605360d01abc520cedfbc457dd89319ed83c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684271"
---
# <a name="sap-bw-source-editor-columns-page"></a><span data-ttu-id="c17a6-102">Editor de Origem de SAP BW (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="c17a6-102">SAP BW Source Editor (Columns Page)</span></span>
  <span data-ttu-id="c17a6-103">Use a página **Colunas** do **Editor de Origem SAP BW** para mapear uma coluna de saída em cada coluna externa (origem).</span><span class="sxs-lookup"><span data-stu-id="c17a6-103">Use the **Columns** page of the **SAP BW Source Editor** to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="c17a6-104">Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="c17a6-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c17a6-105">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="c17a6-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="c17a6-106">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="c17a6-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c17a6-107">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="c17a6-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="c17a6-108">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="c17a6-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="c17a6-109">**Para abrir a página Colunas**</span><span class="sxs-lookup"><span data-stu-id="c17a6-109">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="c17a6-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c17a6-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="c17a6-111">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c17a6-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="c17a6-112">No **Editor de Origem SAP BW**, clique em **Colunas** para abrir a página **Colunas** do editor.</span><span class="sxs-lookup"><span data-stu-id="c17a6-112">In the **SAP BW Source Editor**, click **Columns** to open the **Columns** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c17a6-113">Opções</span><span class="sxs-lookup"><span data-stu-id="c17a6-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c17a6-114">Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="c17a6-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="c17a6-115">**Colunas Externas Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="c17a6-115">**Available External Columns**</span></span>  
 <span data-ttu-id="c17a6-116">Exiba a lista de colunas externas disponíveis na fonte de dados, e selecione as colunas a serem incluídas no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c17a6-116">View the list of available external columns in the data source, and then select the columns to be included in the data flow.</span></span>  
  
 <span data-ttu-id="c17a6-117">Para incluir uma coluna no fluxo de dados, marque a caixa de seleção que corresponde a essa coluna.</span><span class="sxs-lookup"><span data-stu-id="c17a6-117">To include a column in the data flow, select the check box that corresponds to that column.</span></span> <span data-ttu-id="c17a6-118">A ordem na qual você seleciona as caixas de seleção determina a ordem na qual as colunas serão geradas.</span><span class="sxs-lookup"><span data-stu-id="c17a6-118">The order in which you select the check boxes determines the order in which columns will be output.</span></span> <span data-ttu-id="c17a6-119">Ou seja a primeira caixa de seleção que você selecionar será a primeira coluna gerada, a segunda caixa de seleção será a segunda e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c17a6-119">That is, the first check box that you select will be the first output column, the second check box will be the second output columns, and so on.</span></span>  
  
 <span data-ttu-id="c17a6-120">**Coluna Externa**</span><span class="sxs-lookup"><span data-stu-id="c17a6-120">**External Column**</span></span>  
 <span data-ttu-id="c17a6-121">Visualize as colunas externas (origem) selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c17a6-121">View the selected external (source) columns.</span></span> <span data-ttu-id="c17a6-122">As colunas selecionadas aparecem na ordem na que você verá suas colunas geradas correspondentes ao configurar os componentes downstream que consomem os dados dessa fonte.</span><span class="sxs-lookup"><span data-stu-id="c17a6-122">The selected columns appear in the order in which you will see their corresponding output columns when you configure downstream components that consume data from this source.</span></span>  
  
 <span data-ttu-id="c17a6-123">Para alterar a ordem das colunas, na lista **Colunas Externas Disponíveis** , desmarque as caixas de seleção para todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="c17a6-123">To change the order of the columns, in the **Available External Columns** list, clear the check boxes for all columns.</span></span> <span data-ttu-id="c17a6-124">Em seguida, selecione as colunas na ordem que você quer que elas apareçam.</span><span class="sxs-lookup"><span data-stu-id="c17a6-124">Then, select the columns in the order that you want them to appear.</span></span>  
  
 <span data-ttu-id="c17a6-125">**Coluna de Saída**</span><span class="sxs-lookup"><span data-stu-id="c17a6-125">**Output Column**</span></span>  
 <span data-ttu-id="c17a6-126">Forneça um nome exclusivo para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="c17a6-126">Provide a unique name for each output column.</span></span> <span data-ttu-id="c17a6-127">O padrão é o nome da coluna externa (origem) selecionada.</span><span class="sxs-lookup"><span data-stu-id="c17a6-127">The default is the name of the selected external (source) column.</span></span> <span data-ttu-id="c17a6-128">No entanto, você pode inserir qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c17a6-128">However, you can enter any unique, descriptive name.</span></span> [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="c17a6-129">exibirá os nomes de **Coluna de Saída** para as colunas ao configurar os componentes downstream que consomem os dados dessa fonte.</span><span class="sxs-lookup"><span data-stu-id="c17a6-129">Designer will display the **Output Column** names for the columns when you configure downstream components that consume data from this source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17a6-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c17a6-130">See Also</span></span>  
 <span data-ttu-id="c17a6-131">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c17a6-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="c17a6-132">[Editor de Origem SAP BW &#40;Página Saída de Erro&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c17a6-132">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="c17a6-133">[Editor de Origem SAP BW &#40;Página Avançado&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c17a6-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="c17a6-134">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="c17a6-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
