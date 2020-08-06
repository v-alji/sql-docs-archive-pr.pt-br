---
title: Criar InfoPackage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9cd4a848-409f-4681-a390-1c49a2aadbd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95f6ddce4e97c0c21d9f77c432231d414770dbce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678900"
---
# <a name="create-infopackage"></a><span data-ttu-id="72b85-102">Criar InfoPackage</span><span class="sxs-lookup"><span data-stu-id="72b85-102">Create InfoPackage</span></span>
  <span data-ttu-id="72b85-103">Use a caixa de diálogo **Criar Novo InfoPackage** para criar um novo InfoPackage no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="72b85-103">Use the **Create InfoPackage** dialog box to create a new InfoPackage in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="72b85-104">Você pode abrir a caixa de diálogo **Criar InfoPackage** da página **Gerenciador de Conexões** do **Editor de Destino SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="72b85-104">You can open the **Create InfoPackage** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="72b85-105">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="72b85-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="72b85-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="72b85-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="72b85-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="72b85-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="72b85-108">**Para abrir a caixa de diálogo Criar InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="72b85-108">**To open the Create InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="72b85-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="72b85-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="72b85-110">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="72b85-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="72b85-111">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="72b85-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="72b85-112">Na página **Gerenciador de Conexões** , na caixa de grupo **Criar Objetos SAP BW** , selecione **InfoPackage**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="72b85-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoPackage**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="72b85-113">Opções</span><span class="sxs-lookup"><span data-stu-id="72b85-113">Options</span></span>  
 <span data-ttu-id="72b85-114">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="72b85-114">**InfoSource**</span></span>  
 <span data-ttu-id="72b85-115">Digite o nome do InfoSource no qual o novo InfoPackage deve ser baseado.</span><span class="sxs-lookup"><span data-stu-id="72b85-115">Enter the name of the InfoSource on which the new InfoPackage should be based.</span></span>  
  
 <span data-ttu-id="72b85-116">**Descrição breve**</span><span class="sxs-lookup"><span data-stu-id="72b85-116">**Short description**</span></span>  
 <span data-ttu-id="72b85-117">Digite uma descrição para o novo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="72b85-117">Enter a description for the new InfoPackage.</span></span>  
  
 <span data-ttu-id="72b85-118">**Sistema de origem**</span><span class="sxs-lookup"><span data-stu-id="72b85-118">**Source system**</span></span>  
 <span data-ttu-id="72b85-119">Selecione o sistema de dados com o qual o novo InfoPackage deve ser associado.</span><span class="sxs-lookup"><span data-stu-id="72b85-119">Select the source system with which the new InfoPackage should be associated.</span></span>  
  
 <span data-ttu-id="72b85-120">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="72b85-120">**Attributes**</span></span>  
 <span data-ttu-id="72b85-121">Indica que o InfoPackage carregará dados de atributo.</span><span class="sxs-lookup"><span data-stu-id="72b85-121">Indicates that the InfoPackage will load attribute data.</span></span>  
  
 <span data-ttu-id="72b85-122">**Textos**</span><span class="sxs-lookup"><span data-stu-id="72b85-122">**Texts**</span></span>  
 <span data-ttu-id="72b85-123">Indica que o InfoPackage carregará dados de texto.</span><span class="sxs-lookup"><span data-stu-id="72b85-123">Indicates that the InfoPackage will load text data.</span></span>  
  
 <span data-ttu-id="72b85-124">**Transação**</span><span class="sxs-lookup"><span data-stu-id="72b85-124">**Transaction**</span></span>  
 <span data-ttu-id="72b85-125">Indica que o InfoPackage carregará dados de transação.</span><span class="sxs-lookup"><span data-stu-id="72b85-125">Indicates that the InfoPackage will load transaction data.</span></span>  
  
 <span data-ttu-id="72b85-126">**Salvar e Ativar**</span><span class="sxs-lookup"><span data-stu-id="72b85-126">**Save & Activate**</span></span>  
 <span data-ttu-id="72b85-127">Salvar e ativar o novo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="72b85-127">Save and activate the new InfoPackage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b85-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72b85-128">See Also</span></span>  
 [<span data-ttu-id="72b85-129">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="72b85-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
