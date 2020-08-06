---
title: Adicionar ou excluir um componente em um fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f041258d2b66e7b8da540a842848ebf70f4ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679453"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a><span data-ttu-id="29e53-102">Adicionar ou excluir um componente em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="29e53-102">Add or Delete a Component in a Data Flow</span></span>
  <span data-ttu-id="29e53-103">Os componentes de fluxo de dados são fontes, destinos e transformações em um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="29e53-103">Data flow components are sources, destinations, and transformations in a data flow.</span></span> <span data-ttu-id="29e53-104">Para adicionar componentes a um fluxo de dados, o fluxo de controle do pacote deve incluir uma tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="29e53-104">Before you can add components to a data flow, the control flow in the package must include a Data Flow task.</span></span>  
  
 <span data-ttu-id="29e53-105">Os procedimentos a seguir descrevem como adicionar ou excluir um componente no fluxo de dados de um pacote.</span><span class="sxs-lookup"><span data-stu-id="29e53-105">The following procedures describe how to add or delete a component in the data flow of a package.</span></span>  
  
### <a name="to-add-a-component-to-a-data-flow"></a><span data-ttu-id="29e53-106">Para adicionar um componente a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="29e53-106">To add a component to a data flow</span></span>  
  
1.  <span data-ttu-id="29e53-107">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="29e53-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="29e53-108">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="29e53-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="29e53-109">Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém o fluxo de dados ao qual você deseja adicionar um componente.</span><span class="sxs-lookup"><span data-stu-id="29e53-109">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow to which you want to add a component.</span></span>  
  
4.  <span data-ttu-id="29e53-110">Na Caixa de Ferramentas, expanda **Origens de Fluxos de Dados**, **Transformações de Fluxos de Dados**ou **Destinos de Fluxos de Dados**e arraste um item do fluxo de dados até a superfície de design da guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="29e53-110">In the Toolbox, expand **Data Flow Sources**, **Data Flow Transformations**, or **Data Flow Destinations**, and then drag a data flow item to the design surface of the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="29e53-111">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="29e53-111">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-component-from-a-data-flow"></a><span data-ttu-id="29e53-112">Para excluir um componente de um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="29e53-112">To delete a component from a data flow</span></span>  
  
1.  <span data-ttu-id="29e53-113">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="29e53-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="29e53-114">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="29e53-114">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="29e53-115">Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém o fluxo de dados do qual você deseja excluir um componente.</span><span class="sxs-lookup"><span data-stu-id="29e53-115">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow from which you want to delete a component.</span></span>  
  
4.  <span data-ttu-id="29e53-116">Clique com o botão direito do mouse no componente do fluxo de dados e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="29e53-116">Right-click the data flow component, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="29e53-117">Confirme a operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="29e53-117">Confirm the delete operation.</span></span>  
  
6.  <span data-ttu-id="29e53-118">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="29e53-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e53-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29e53-119">See Also</span></span>  
 <span data-ttu-id="29e53-120">[Conectar componentes em um fluxo de dados](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="29e53-120">[Connect Components in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="29e53-121">[Configurar uma saída de erro em um componente de fluxo de dados](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="29e53-121">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="29e53-122">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="29e53-122">Data Flow</span></span>](data-flow.md)  
  
  
