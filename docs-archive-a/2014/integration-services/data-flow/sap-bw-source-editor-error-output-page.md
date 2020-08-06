---
title: Editor de Origem SAP BW (página Saída de Erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6e23b0c-949a-46d1-8424-4dc3d9035e79
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a4ad2d02d3f5ec5c1a786019e18fa01665fdc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678883"
---
# <a name="sap-bw-source-editor-error-output-page"></a><span data-ttu-id="6ca22-102">Editor de Origem de SAP BW (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="6ca22-102">SAP BW Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="6ca22-103">Use a página **Saída de Erro** do **Editor de Origem SAP BW** , para selecionar opções de tratamento de erro e definir propriedades em colunas de saída de erros.</span><span class="sxs-lookup"><span data-stu-id="6ca22-103">Use the **Error Output** page of the **SAP BW Source Editor** to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="6ca22-104">Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="6ca22-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ca22-105">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="6ca22-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="6ca22-106">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="6ca22-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ca22-107">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="6ca22-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="6ca22-108">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="6ca22-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="6ca22-109">**Para abrir a página Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="6ca22-109">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="6ca22-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="6ca22-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="6ca22-111">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="6ca22-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="6ca22-112">No **Editor de Origem SAP BW**, clique em **Saída do Erro** para abrir a página **Saída do Erro** do editor.</span><span class="sxs-lookup"><span data-stu-id="6ca22-112">In the **SAP BW Source Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ca22-113">Opções</span><span class="sxs-lookup"><span data-stu-id="6ca22-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ca22-114">Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="6ca22-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="6ca22-115">**Entrada ou Saída**</span><span class="sxs-lookup"><span data-stu-id="6ca22-115">**Input or Output**</span></span>  
 <span data-ttu-id="6ca22-116">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6ca22-116">View the name of the data source.</span></span>  
  
 <span data-ttu-id="6ca22-117">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6ca22-117">**Column**</span></span>  
 <span data-ttu-id="6ca22-118">Exiba as colunas externas (origem) selecionadas na página **Colunas** da caixa de diálogo **Editor de Origem SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="6ca22-118">View the external (source) columns that you selected on the **Columns** page of the **SAP BW Source Editor** dialog box.</span></span> <span data-ttu-id="6ca22-119">Para obter mais informações sobre essa caixa de diálogo, consulte [Editor de Origem SAP BW &#40;Página Colunas&#41;](sap-bw-source-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="6ca22-119">For more information about this dialog box, see [SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="6ca22-120">**Erro**</span><span class="sxs-lookup"><span data-stu-id="6ca22-120">**Error**</span></span>  
 <span data-ttu-id="6ca22-121">Especifique o que o componente de origem SAP BW deve fazer quando há um erro: ignorar a falha, redirecionar a linha ou falhar o componente.</span><span class="sxs-lookup"><span data-stu-id="6ca22-121">Specify what the SAP BW source component should do when there is an error: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="6ca22-122">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="6ca22-122">**Truncation**</span></span>  
 <span data-ttu-id="6ca22-123">Especifique o que o componente de origem SAP BW deve fazer quando ocorre um truncamento: ignorar a falha, redirecionar a linha ou falhar o componente.</span><span class="sxs-lookup"><span data-stu-id="6ca22-123">Specify what the SAP BW source component should do when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="6ca22-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6ca22-124">**Description**</span></span>  
 <span data-ttu-id="6ca22-125">Exiba a descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="6ca22-125">View the description of the error.</span></span>  
  
 <span data-ttu-id="6ca22-126">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="6ca22-126">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="6ca22-127">Especifique o que o componente de origem SAB BW deve fazer a todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="6ca22-127">Specify what the SAP BW source component should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="6ca22-128">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="6ca22-128">**Apply**</span></span>  
 <span data-ttu-id="6ca22-129">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6ca22-129">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca22-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ca22-130">See Also</span></span>  
 <span data-ttu-id="6ca22-131">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="6ca22-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="6ca22-132">[Editor de Origem SAP BW &#40;Página Colunas&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="6ca22-132">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="6ca22-133">[Editor de Origem SAP BW &#40;Página Avançado&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="6ca22-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="6ca22-134">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="6ca22-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
