---
title: Editor de destino de SAP BW (página Saída de Erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a543d811-0bd2-4890-a0d3-f5fdcd4524b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ffd58580865a71626252aa2d177530e41156537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678887"
---
# <a name="sap-bw-destination-editor-error-output-page"></a><span data-ttu-id="ea179-102">Editor de Destino de SAP BW (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="ea179-102">SAP BW Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="ea179-103">Use a página **Saída de Erro** do **Editor de Destino SAP BW** para especificar opções de tratamento de erro.</span><span class="sxs-lookup"><span data-stu-id="ea179-103">Use the **Error Output** page of the **SAP BW Destination Editor** to specify error handling options.</span></span>  
  
 <span data-ttu-id="ea179-104">Para saber mais sobre o destino SAP BW do Connector 1.1 do [!INCLUDE[msCoName](../../includes/msconame-md.md)] para SAP BW, consulte [Destino SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ea179-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ea179-105">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ea179-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ea179-106">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="ea179-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="ea179-107">**Para abrir a página Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="ea179-107">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="ea179-108">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ea179-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="ea179-109">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ea179-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="ea179-110">No **Editor de Destino SAP BW**, clique em **Saída do Erro** para abrir a página **Saída do Erro** do editor.</span><span class="sxs-lookup"><span data-stu-id="ea179-110">In the **SAP BW Destination Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea179-111">Opções</span><span class="sxs-lookup"><span data-stu-id="ea179-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea179-112">Se você não souber todos os valores necessários para configurar o destino, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="ea179-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="ea179-113">**Entrada ou Saída**</span><span class="sxs-lookup"><span data-stu-id="ea179-113">**Input or Output**</span></span>  
 <span data-ttu-id="ea179-114">Visualize o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="ea179-114">View the name of the input.</span></span>  
  
 <span data-ttu-id="ea179-115">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ea179-115">**Column**</span></span>  
 <span data-ttu-id="ea179-116">Esta opção não é usada.</span><span class="sxs-lookup"><span data-stu-id="ea179-116">This option is not used.</span></span>  
  
 <span data-ttu-id="ea179-117">**Erro**</span><span class="sxs-lookup"><span data-stu-id="ea179-117">**Error**</span></span>  
 <span data-ttu-id="ea179-118">Especifique o que o destino deve fazer quando ocorrer um erro: ignorar a falha, redirecionar a linha ou falhar o componente.</span><span class="sxs-lookup"><span data-stu-id="ea179-118">Specify what the destination should do when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="ea179-119">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="ea179-119">**Truncation**</span></span>  
 <span data-ttu-id="ea179-120">Esta opção não é usada.</span><span class="sxs-lookup"><span data-stu-id="ea179-120">This option is not used.</span></span>  
  
 <span data-ttu-id="ea179-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ea179-121">**Description**</span></span>  
 <span data-ttu-id="ea179-122">Visualize a descrição da operação.</span><span class="sxs-lookup"><span data-stu-id="ea179-122">View the description of the operation.</span></span>  
  
 <span data-ttu-id="ea179-123">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="ea179-123">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="ea179-124">Especifique o que o destino deve fazer a todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="ea179-124">Specify what the destination should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="ea179-125">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="ea179-125">**Apply**</span></span>  
 <span data-ttu-id="ea179-126">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="ea179-126">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea179-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea179-127">See Also</span></span>  
 <span data-ttu-id="ea179-128">[Editor de Destino SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ea179-128">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ea179-129">[Editor de Destino SAP BW &#40;Página Mapeamentos&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="ea179-129">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="ea179-130">[Editor de Destino SAP BW &#40;Página Avançado&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="ea179-130">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="ea179-131">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="ea179-131">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
