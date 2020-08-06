---
title: Criar InfoSource para dados mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b52a9a89-8380-4a02-8a83-dcfb46ae860e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bb90bc5cf27f37dc89df236b765db98088a5804a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678898"
---
# <a name="create-infosource-for-master-data"></a><span data-ttu-id="19e80-102">Criar InfoSource para Dados Mestres</span><span class="sxs-lookup"><span data-stu-id="19e80-102">Create InfoSource for Master Data</span></span>
  <span data-ttu-id="19e80-103">Use a caixa de diálogo **Criar InfoSource para os Dados Mestres** para criar um novo InfoSource para dados mestres no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="19e80-103">Use the **Create InfoSource for Master Data** dialog box to create a new InfoSource for master data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="19e80-104">Você pode abrir a caixa de diálogo **Criar InfoSource para os Dados Mestres** da página **Gerenciador de Conexões** do **Editor de Destino SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="19e80-104">You can open the **Create InfoSource for Master Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="19e80-105">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="19e80-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="19e80-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="19e80-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="19e80-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="19e80-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="19e80-108">**Para abrir a caixa de diálogo Criar InfoSource para os Dados Mestres**</span><span class="sxs-lookup"><span data-stu-id="19e80-108">**To open the Create InfoSource for Master Data dialog box**</span></span>  
  
1.  <span data-ttu-id="19e80-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="19e80-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="19e80-110">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="19e80-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="19e80-111">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="19e80-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="19e80-112">Na página **Gerenciador de Conexões** , na caixa de grupo **Criar Objetos SAP BW** , selecione **InfoSource**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="19e80-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="19e80-113">Na caixa de diálogo **Criar InfoSource** , selecione **Dados Mestres**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="19e80-113">In the **Create InfoSource** dialog box, select **Master data**, and then click **OK**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="19e80-114">Opções</span><span class="sxs-lookup"><span data-stu-id="19e80-114">Options</span></span>  
 <span data-ttu-id="19e80-115">**Nome do InfoObject**</span><span class="sxs-lookup"><span data-stu-id="19e80-115">**InfoObject name**</span></span>  
 <span data-ttu-id="19e80-116">Digite o nome do InfoObject no qual o novo InfoSource deve ser baseado.</span><span class="sxs-lookup"><span data-stu-id="19e80-116">Enter the name of the InfoObject on which the new InfoSource should be based.</span></span>  
  
 <span data-ttu-id="19e80-117">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="19e80-117">**Look up**</span></span>  
 <span data-ttu-id="19e80-118">Pesquisar InfoObject.</span><span class="sxs-lookup"><span data-stu-id="19e80-118">Look up the InfoObject.</span></span> <span data-ttu-id="19e80-119">Essa opção abre a caixa de diálogo **Pesquisar InfoObject** na qual é possível selecionar o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="19e80-119">This option opens the **Look Up InfoObject** dialog box in which you can select the InfoObject.</span></span> <span data-ttu-id="19e80-120">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="19e80-120">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="19e80-121">Depois de selecionar um InfoObject, o componente preenche a caixa de texto **Nome do InfoObject** com o nome do InfoObject selecionado.</span><span class="sxs-lookup"><span data-stu-id="19e80-121">After you select an InfoObject, the component populates the **InfoObject name** text box with the name of the selected InfoObject.</span></span>  
  
 <span data-ttu-id="19e80-122">**Novo**</span><span class="sxs-lookup"><span data-stu-id="19e80-122">**New**</span></span>  
 <span data-ttu-id="19e80-123">Criar um novo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="19e80-123">Create a new InfoObject.</span></span> <span data-ttu-id="19e80-124">Essa opção abre a caixa de diálogo **Criar Novo InfoObject** na qual é possível criar o novo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="19e80-124">This option opens the **Create New InfoObject** dialog box in which you can create the new InfoObject.</span></span> <span data-ttu-id="19e80-125">Para obter mais informações sobre essa caixa de diálogo, consulte [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="19e80-125">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="19e80-126">Depois de criar um InfoObject, o componente preenche a caixa de texto **Nome do InfoObject** com o nome do novo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="19e80-126">After you create an InfoObject, the component populates the **InfoObject name** text box with the name of the new InfoObject.</span></span>  
  
 <span data-ttu-id="19e80-127">**Descrição breve**</span><span class="sxs-lookup"><span data-stu-id="19e80-127">**Short description**</span></span>  
 <span data-ttu-id="19e80-128">Insira uma descrição curta para o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="19e80-128">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="19e80-129">**Descrição longa**</span><span class="sxs-lookup"><span data-stu-id="19e80-129">**Long description**</span></span>  
 <span data-ttu-id="19e80-130">Insira uma descrição longa para o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="19e80-130">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="19e80-131">**Sistema de origem**</span><span class="sxs-lookup"><span data-stu-id="19e80-131">**Source system**</span></span>  
 <span data-ttu-id="19e80-132">Selecione o sistema de origem a ser associado ao novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="19e80-132">Select the source system to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="19e80-133">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="19e80-133">**Application**</span></span>  
 <span data-ttu-id="19e80-134">Insira o nome do aplicativo cliente a ser associado ao novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="19e80-134">Enter the name of the application to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="19e80-135">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="19e80-135">**Attributes**</span></span>  
 <span data-ttu-id="19e80-136">Indica que os dados mestres consistem em atributos.</span><span class="sxs-lookup"><span data-stu-id="19e80-136">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="19e80-137">**Textos**</span><span class="sxs-lookup"><span data-stu-id="19e80-137">**Texts**</span></span>  
 <span data-ttu-id="19e80-138">Indica que os dados mestres consistem em atributos.</span><span class="sxs-lookup"><span data-stu-id="19e80-138">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="19e80-139">**Salvar e Ativar**</span><span class="sxs-lookup"><span data-stu-id="19e80-139">**Save & Activate**</span></span>  
 <span data-ttu-id="19e80-140">Salvar e ativar o novo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="19e80-140">Save and activate the new InfoSource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e80-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19e80-141">See Also</span></span>  
 <span data-ttu-id="19e80-142">[Criar InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="19e80-142">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="19e80-143">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="19e80-143">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
