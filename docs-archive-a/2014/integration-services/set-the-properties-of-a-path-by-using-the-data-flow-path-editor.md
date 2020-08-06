---
title: Definir as propriedades de um caminho usando o editor de caminho de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 512249a4-83a6-4087-980d-a4344da48371
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e01565ef6cb70f3ac52187a6cc8d22d05508db4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685839"
---
# <a name="set-the-properties-of-a-path-by-using-the-data-flow-path-editor"></a><span data-ttu-id="fe552-102">Definir as propriedades de um caminho por meio do Editor de Caminho do Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="fe552-102">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>
  <span data-ttu-id="fe552-103">Os caminhos conectam dois componentes de fluxos de dados.</span><span class="sxs-lookup"><span data-stu-id="fe552-103">Paths connect two data flow components.</span></span> <span data-ttu-id="fe552-104">Antes de você poder definir as propriedades do caminho, o fluxo de dados deve conter pelo menos dois componentes de fluxo de dados conectados.</span><span class="sxs-lookup"><span data-stu-id="fe552-104">Before you can set path properties, the data flow must contain at least two connected data flow components.</span></span> <span data-ttu-id="fe552-105">Para obter mais informações, consulte [Adicionar ou excluir um componente em um fluxo de dados](data-flow/add-or-delete-a-component-in-a-data-flow.md) e [Conectar componentes em um fluxo de dados](data-flow/connect-components-in-a-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="fe552-105">For more information, see [Add or Delete a Component in a Data Flow](data-flow/add-or-delete-a-component-in-a-data-flow.md) and [Connect Components in a Data Flow](data-flow/connect-components-in-a-data-flow.md).</span></span>  
  
### <a name="to-set-path-properties"></a><span data-ttu-id="fe552-106">Para definir as propriedades do caminho</span><span class="sxs-lookup"><span data-stu-id="fe552-106">To set path properties</span></span>  
  
1.  <span data-ttu-id="fe552-107">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="fe552-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fe552-108">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="fe552-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fe552-109">Clique na guia **Fluxo de Dados** e clique duas vezes em um caminho.</span><span class="sxs-lookup"><span data-stu-id="fe552-109">Click the **Data Flow** tab, and then double-click a path.</span></span>  
  
4.  <span data-ttu-id="fe552-110">No **Editor de Caminho de Fluxo de Dado**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="fe552-110">In **Data Flow Path Editor**, click **General**.</span></span> <span data-ttu-id="fe552-111">É possível editar o nome padrão do caminho e fornecer uma descrição do caminho.</span><span class="sxs-lookup"><span data-stu-id="fe552-111">You can then edit the default name of the path and provide a description of the path.</span></span> <span data-ttu-id="fe552-112">É possível também modificar a propriedade PathAnnotation.</span><span class="sxs-lookup"><span data-stu-id="fe552-112">You can also modify the PathAnnotation property.</span></span>  
  
5.  <span data-ttu-id="fe552-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe552-113">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="fe552-114">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="fe552-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe552-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe552-115">See Also</span></span>  
 <span data-ttu-id="fe552-116">[Caminhos do Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="fe552-116">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="fe552-117">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="fe552-117">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
