---
title: Editor de Origem SAP BW (página Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c78d40555a30031bf39abda18048fda9c648d01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684819"
---
# <a name="sap-bw-source-editor-advanced-page"></a><span data-ttu-id="ccf00-102">Editor de Origem de SAP BW (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="ccf00-102">SAP BW Source Editor (Advanced Page)</span></span>
  <span data-ttu-id="ccf00-103">Use a página **Avançado** do **Editor de Fonte SAP BW** para especificar a regra de conversão de cadeia de caracteres e o período de tempo limite, e também para redefinir o status de uma ID de Solicitação específica.</span><span class="sxs-lookup"><span data-stu-id="ccf00-103">Use the **Advanced** page of the **SAP BW Source Editor** to specify the string conversion rule and the time-out period, and also to reset the status of a particular Request ID.</span></span>  
  
 <span data-ttu-id="ccf00-104">Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="ccf00-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ccf00-105">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ccf00-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ccf00-106">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="ccf00-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ccf00-107">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="ccf00-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="ccf00-108">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="ccf00-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="ccf00-109">**Para abrir a página Gerenciador de Conexões**</span><span class="sxs-lookup"><span data-stu-id="ccf00-109">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="ccf00-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ccf00-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="ccf00-111">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ccf00-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="ccf00-112">No **Editor de Origem SAP BW**, clique em **Avançado** para abrir a página **Avançada** do editor.</span><span class="sxs-lookup"><span data-stu-id="ccf00-112">In the **SAP BW Source Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ccf00-113">Opções</span><span class="sxs-lookup"><span data-stu-id="ccf00-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccf00-114">Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="ccf00-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="ccf00-115">**Conversão da cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="ccf00-115">**String Conversion**</span></span>  
 <span data-ttu-id="ccf00-116">Especifique a regra para aplicar à conversão de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ccf00-116">Specify the rule to apply for string conversion.</span></span>  
  
|<span data-ttu-id="ccf00-117">Opção</span><span class="sxs-lookup"><span data-stu-id="ccf00-117">Option</span></span>|<span data-ttu-id="ccf00-118">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ccf00-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ccf00-119">**Conversão automática de cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="ccf00-119">**Automatic string conversion**</span></span>|<span data-ttu-id="ccf00-120">Converta todas as cadeias de caracteres para `nvarchar` quando o sistema SAP Netweaver BW for um sistema Unicode.</span><span class="sxs-lookup"><span data-stu-id="ccf00-120">Convert all strings to `nvarchar` when the SAP Netweaver BW system is a Unicode system.</span></span> <span data-ttu-id="ccf00-121">Caso contrário, converta todas as cadeias de caracteres para `varchar`.</span><span class="sxs-lookup"><span data-stu-id="ccf00-121">Otherwise, convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="ccf00-122">**Converter cadeias de caracteres em varchar**</span><span class="sxs-lookup"><span data-stu-id="ccf00-122">**Convert strings to varchar**</span></span>|<span data-ttu-id="ccf00-123">Converta todas as cadeias de caracteres para `varchar`.</span><span class="sxs-lookup"><span data-stu-id="ccf00-123">Convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="ccf00-124">**Converter cadeias de caracteres em nvarchar**</span><span class="sxs-lookup"><span data-stu-id="ccf00-124">**Convert strings to nvarchar**</span></span>|<span data-ttu-id="ccf00-125">Converta todas as cadeias de caracteres para `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="ccf00-125">Convert all strings to `nvarchar`.</span></span>|  
  
 <span data-ttu-id="ccf00-126">**Tempo Limite (segundos)**</span><span class="sxs-lookup"><span data-stu-id="ccf00-126">**Timeout (seconds)**</span></span>  
 <span data-ttu-id="ccf00-127">Especifique o número máximo de segundos que a origem deve esperar.</span><span class="sxs-lookup"><span data-stu-id="ccf00-127">Specify the maximum number of seconds that the source should wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccf00-128">Esta opção só será válida se você tiver selecionado **A – Aguardar Notificação** como o valor de **Modo de Execução** na página do **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="ccf00-128">This option is only valid if you have selected **W - Wait for Notify** as the value of **Execution Mode** on the **Connection Manager** page of the editor.</span></span> <span data-ttu-id="ccf00-129">Para obter mais informações, consulte [Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="ccf00-129">For more information, see [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).</span></span>  
  
 <span data-ttu-id="ccf00-130">**Request ID**</span><span class="sxs-lookup"><span data-stu-id="ccf00-130">**Request ID**</span></span>  
 <span data-ttu-id="ccf00-131">Especifique a ID da Solicitação cujo status você quer redefinir para “V – Verde” quando clicar em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="ccf00-131">Specify the Request ID whose status you want to reset to "G - Green" when you click **Reset**.</span></span>  
  
 <span data-ttu-id="ccf00-132">**Redefinir**</span><span class="sxs-lookup"><span data-stu-id="ccf00-132">**Reset**</span></span>  
 <span data-ttu-id="ccf00-133">Permite redefinir o status da ID da solicitação para “V - Verde”, depois de ter solicitado a sua confirmação.</span><span class="sxs-lookup"><span data-stu-id="ccf00-133">Lets you reset the status of the specified Request ID to "G - Green", after prompting you for confirmation.</span></span> <span data-ttu-id="ccf00-134">Isso pode ser útil quando um problema tiver ocorrido e o sistema SAP Netweaver BW tiver marcado a solicitação com um status amarelo ou vermelho.</span><span class="sxs-lookup"><span data-stu-id="ccf00-134">This can be useful when a problem has occurred, and the SAP Netweaver BW system has flagged the request with a yellow or red status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf00-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ccf00-135">See Also</span></span>  
 <span data-ttu-id="ccf00-136">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ccf00-136">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ccf00-137">[Editor de Origem SAP BW &#40;Página Colunas&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ccf00-137">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="ccf00-138">[Editor de Origem SAP BW &#40;Página Saída de Erro&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="ccf00-138">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="ccf00-139">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="ccf00-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
