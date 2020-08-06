---
title: Copiar objetos de pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], copying objects
- copying package objects [Integration Services]
- data flow [Integration Services], copying objects
- connection managers [Integration Services], copying
ms.assetid: 99b85e5c-d6bd-4e7c-afe4-51f6ce151c2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3219f0023c9a28ed270adeb6fd2b795e3459c3e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571503"
---
# <a name="copy-package-objects"></a><span data-ttu-id="c0510-102">Copiar objetos de pacote</span><span class="sxs-lookup"><span data-stu-id="c0510-102">Copy Package Objects</span></span>
  <span data-ttu-id="c0510-103">Este tópico descreve como copiar os itens de fluxo de controle, itens de fluxo de dados e gerenciadores de conexões dentro de um pacote ou entre pacotes.</span><span class="sxs-lookup"><span data-stu-id="c0510-103">This topic describes how to copy control flow items, data flow items, and connection managers within a package or between packages.</span></span>  
  
### <a name="to-copy-control-and-data-flow-items"></a><span data-ttu-id="c0510-104">Copiar itens de fluxo de controle e fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="c0510-104">To copy control and data flow items</span></span>  
  
1.  <span data-ttu-id="c0510-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém os pacotes com os quais deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="c0510-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the packages that you want work with.</span></span>  
  
2.  <span data-ttu-id="c0510-106">No Gerenciador de Soluções, clique duas vezes nos pacotes que deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="c0510-106">In Solution Explorer, double-click the packages that you want to copy between.</span></span>  
  
3.  <span data-ttu-id="c0510-107">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique na guia do pacote que contém os itens a serem copiados e clique na guia **Fluxo de Controle**, **Fluxo de Dados**ou **Manipulador de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="c0510-107">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the tab for the package that contains the items to copy and click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="c0510-108">Selecione os itens de fluxo de controle ou de dados que deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="c0510-108">Select the control flow or data flow items to copy.</span></span> <span data-ttu-id="c0510-109">Para selecionar vários itens de uma vez, pressione a tecla Shift e clique no item ou selecione os itens como um grupo, arrastando o ponteiro pelos itens que deseja selecionar.</span><span class="sxs-lookup"><span data-stu-id="c0510-109">You can either select items one at a time by pressing the Shift key and clicking the item or select items as a group by dragging the pointer across the items you want to select.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c0510-110">As restrições de precedência e caminhos que conectam itens não são selecionadas automaticamente quando você seleciona dois itens que elas conectam.</span><span class="sxs-lookup"><span data-stu-id="c0510-110">The precedence constraints and paths that connect items are not selected automatically when you select the two items that they connect.</span></span> <span data-ttu-id="c0510-111">Para copiar um fluxo de trabalho ordenado – um segmento do fluxo de controle ou do fluxo de dados – certifique-se de que tenha copiado também as restrições de precedência e os caminhos.</span><span class="sxs-lookup"><span data-stu-id="c0510-111">To copy an ordered workflow-a segment of control flow or data flow-make sure to also copy the precedence constrains and the paths.</span></span>  
  
5.  <span data-ttu-id="c0510-112">Clique com o botão direito do mouse em um item selecionado e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="c0510-112">Right-click a selected item and click **Copy**.</span></span>  
  
6.  <span data-ttu-id="c0510-113">Se quiser copiar os itens para um pacote diferente, clique no pacote para o qual deseja copiar e, em seguida, clique na guia apropriada para o tipo de item.</span><span class="sxs-lookup"><span data-stu-id="c0510-113">If copying items to a different package, click the package that you want to copy to, and then click the appropriate tab for the item type.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c0510-114">Você não pode copiar um fluxo de dados em um pacote a menos que o pacote contenha pelo menos uma tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="c0510-114">You cannot copy a data flow to a package unless the package contains at least one Data Flow task.</span></span>  
  
7.  <span data-ttu-id="c0510-115">Clique com o botão direito do mouse e clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="c0510-115">Right-click and click **Paste**.</span></span>  
  
### <a name="to-copy-connection-managers"></a><span data-ttu-id="c0510-116">Copiar gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="c0510-116">To copy connection managers</span></span>  
  
1.  <span data-ttu-id="c0510-117">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="c0510-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to work with.</span></span>  
  
2.  <span data-ttu-id="c0510-118">No Gerenciador de Soluções, clique duas vezes no pacote.</span><span class="sxs-lookup"><span data-stu-id="c0510-118">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="c0510-119">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique na guia **Fluxo de Controle**, **Fluxo de Dados**ou **Manipulador de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="c0510-119">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
4.  <span data-ttu-id="c0510-120">Na área **Gerenciadores de Conexões** , clique com o botão direito do mouse no gerenciador de conexões e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="c0510-120">In the **Connection Managers** area, right-click the connection manager, and then click **Copy**.</span></span> <span data-ttu-id="c0510-121">Você pode copiar apenas um gerenciador de conexões por vez.</span><span class="sxs-lookup"><span data-stu-id="c0510-121">You can copy only one connection manager at a time.</span></span>  
  
5.  <span data-ttu-id="c0510-122">Se quiser copiar os itens para um pacote diferente, clique no pacote para o qual deseja copiar e, em seguida, clique na guia **Fluxo de Controle**, **Fluxo de Dados**ou **Manipulador de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="c0510-122">If you are copying items to a different package, click the package that you want to copy to and then click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
6.  <span data-ttu-id="c0510-123">Clique com o botão direito do mouse na área **Gerenciadores de Conexões** e clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="c0510-123">Right-click in the **Connection Managers** area and click **Paste**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0510-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0510-124">See Also</span></span>  
 <span data-ttu-id="c0510-125">[Fluxo de Controle](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="c0510-125">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="c0510-126">[Fluxo de Dados](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="c0510-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 <span data-ttu-id="c0510-127">[Conexões do SSIS &#40;Integration Services&#41;](connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="c0510-127">[Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="c0510-128">Copiar itens do projeto</span><span class="sxs-lookup"><span data-stu-id="c0510-128">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
  
