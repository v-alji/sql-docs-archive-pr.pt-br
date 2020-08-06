---
title: Criar InfoSource | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7db233b-5464-43de-9d26-6dd24c7ac1b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9620d3170310322c79679e8298ffe465067ae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678892"
---
# <a name="create-infosource"></a><span data-ttu-id="84159-102">Criar InfoSource</span><span class="sxs-lookup"><span data-stu-id="84159-102">Create InfoSource</span></span>
  <span data-ttu-id="84159-103">Use a caixa de diálogo **Criar InfoSource** para criar um novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84159-103">Use the **Create InfoSource** dialog box to create a new InfoSource.</span></span> <span data-ttu-id="84159-104">Para criar o novo InfoSource, use a caixa de diálogo **Criar InfoSource para os Dados da Transação** ou **Criar InfoSource para Dados Mestres** .</span><span class="sxs-lookup"><span data-stu-id="84159-104">To create the new InfoSource, you use either the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span>  
  
 <span data-ttu-id="84159-105">Você pode abrir a caixa de diálogo **Criar InfoSource** da página **Gerenciador de Conexões** do **Editor de Destino SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="84159-105">You can open the **Create InfoSource** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="84159-106">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="84159-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="84159-107">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="84159-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="84159-108">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="84159-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="84159-109">**Para abrir a caixa de diálogo Criar InfoSource**</span><span class="sxs-lookup"><span data-stu-id="84159-109">**To open the Create InfoSource dialog box**</span></span>  
  
1.  <span data-ttu-id="84159-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="84159-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="84159-111">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="84159-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="84159-112">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="84159-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="84159-113">Na página **Gerenciador de Conexões** , na caixa de grupo **Criar Objetos SAP BW** , selecione **InfoSource**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="84159-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="84159-114">Opções</span><span class="sxs-lookup"><span data-stu-id="84159-114">Options</span></span>  
 <span data-ttu-id="84159-115">**Dados da transação**</span><span class="sxs-lookup"><span data-stu-id="84159-115">**Transaction data**</span></span>  
 <span data-ttu-id="84159-116">Crie um novo InfoSource para os dados da transação.</span><span class="sxs-lookup"><span data-stu-id="84159-116">Create a new InfoSource for transaction data.</span></span>  
  
 <span data-ttu-id="84159-117">Se você selecionar essa opção, a caixa de diálogo **Criar InfoSource para os Dados da Transação** será aberta.</span><span class="sxs-lookup"><span data-stu-id="84159-117">If you select this option, the **Create InfoSource for Transaction Data** dialog box opens.</span></span> <span data-ttu-id="84159-118">Você usa a caixa de diálogo **Criar InfoSource para os Dados da Transação** para criar o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84159-118">You use the **Create InfoSource for Transaction Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="84159-119">Para obter mais informações sobre essa caixa de diálogo, consulte [Criar InfoSource para os dados da transação](create-infosource-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="84159-119">For more information about this dialog box, see [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span></span>  
  
 <span data-ttu-id="84159-120">**Dados mestres**</span><span class="sxs-lookup"><span data-stu-id="84159-120">**Master data**</span></span>  
 <span data-ttu-id="84159-121">Crie um novo InfoSource para os dados mestres.</span><span class="sxs-lookup"><span data-stu-id="84159-121">Create a new InfoSource for master data.</span></span>  
  
 <span data-ttu-id="84159-122">Se você selecionar essa opção, a caixa de diálogo **Criar InfoSource para os Dados Mestres** será aberta.</span><span class="sxs-lookup"><span data-stu-id="84159-122">If you select this option, the **Create InfoSource for Master Data** dialog box opens.</span></span> <span data-ttu-id="84159-123">Você usa a caixa de diálogo **Criar InfoSource para os Dados Mestres** para criar o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84159-123">You use the **Create InfoSource for Master Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="84159-124">Para obter mais informações sobre essa caixa de diálogo, consulte [Criar InfoSource para os dados mestres](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="84159-124">For more information about this dialog box, see [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84159-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84159-125">See Also</span></span>  
 [<span data-ttu-id="84159-126">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="84159-126">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
