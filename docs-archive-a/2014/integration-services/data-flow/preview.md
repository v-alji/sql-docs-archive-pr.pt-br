---
title: Visualizar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a795338122c1e7a37a23fdb6af6153f74b927e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571471"
---
# <a name="preview"></a><span data-ttu-id="2d4a3-102">Visualização</span><span class="sxs-lookup"><span data-stu-id="2d4a3-102">Preview</span></span>
  <span data-ttu-id="2d4a3-103">Use a caixa de diálogo **Visualizar** para visualizar os dados que a origem do SAP BW extrairá.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-103">Use the **Preview** dialog box to preview the data that the SAP BW source will extract.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d4a3-104">A opção **Visualizar** , que está disponível na página **Gerenciador de Conexões** do **Editor de origem SAP BW**, extrai dados de fato.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-104">The **Preview** option, that is available on the **Connection Manager** page of the **SAP BW Source Editor**, actually extracts data.</span></span> <span data-ttu-id="2d4a3-105">Se você configurou o SAP Netweaver BW para extrair apenas os dados que foram alterados desde a extração anterior, selecionar **Visualizar** excluirá os dados visualizados da próxima extração.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-105">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="2d4a3-106">Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="2d4a3-106">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d4a3-107">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="2d4a3-108">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d4a3-109">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-109">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="2d4a3-110">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-110">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="2d4a3-111">**Para abrir a caixa de diálogo Visualizar**</span><span class="sxs-lookup"><span data-stu-id="2d4a3-111">**To open the Preview dialog box**</span></span>  
  
1.  <span data-ttu-id="2d4a3-112">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="2d4a3-113">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-113">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="2d4a3-114">No **Editor de Origem SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-114">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="2d4a3-115">Configure a origem do SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-115">Configure the SAP BW source.</span></span>  
  
5.  <span data-ttu-id="2d4a3-116">Depois de configurar a origem do SAP BW, na página **Gerenciador de Conexões** , clique em **Visualizar** para visualizar os dados na caixa de diálogo **Visualizar** .</span><span class="sxs-lookup"><span data-stu-id="2d4a3-116">After you configure the SAP BW source, on the **Connection Manager** page, click **Preview** to preview the data in the **Preview** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d4a3-117">Clicar em **Visualizar** também abre a caixa de diálogo **Log de Solicitações** .</span><span class="sxs-lookup"><span data-stu-id="2d4a3-117">Clicking **Preview** also opens the **Request Log** dialog box.</span></span> <span data-ttu-id="2d4a3-118">Para obter mais informações sobre essa caixa de diálogo, consulte [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="2d4a3-118">For more information about this dialog box, see [Request Log](request-log.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d4a3-119">Opções</span><span class="sxs-lookup"><span data-stu-id="2d4a3-119">Options</span></span>  
 <span data-ttu-id="2d4a3-120">A caixa de diálogo **Visualizar** exibe as linhas que são solicitadas do sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-120">The **Preview** dialog box displays the rows that are requested from the SAP Netweaver BW system.</span></span> <span data-ttu-id="2d4a3-121">As colunas que são exibidas são as colunas definidas nos dados da origem.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-121">The columns that are displayed are the columns that are defined in the source data.</span></span>  
  
 <span data-ttu-id="2d4a3-122">Não há nenhuma outra opção nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d4a3-122">There are no other options in this dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d4a3-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d4a3-123">See Also</span></span>  
 <span data-ttu-id="2d4a3-124">[Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="2d4a3-124">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="2d4a3-125">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="2d4a3-125">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
