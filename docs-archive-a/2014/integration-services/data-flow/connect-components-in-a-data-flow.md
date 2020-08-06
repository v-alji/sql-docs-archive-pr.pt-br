---
title: Conectar componentes em um fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8fc4a2fa81e9b110c27ea63b16d835d069bf12cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678903"
---
# <a name="connect-components-in-a-data-flow"></a><span data-ttu-id="c6e62-102">Conectar componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="c6e62-102">Connect Components in a Data Flow</span></span>
  <span data-ttu-id="c6e62-103">Este procedimento descreve como conectar a saída dos componentes em um fluxo de dados para outros componentes dentro do mesmo fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c6e62-103">This procedure describes how to connect the output of components in a data flow to other components within the same data flow.</span></span>  
  
### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="c6e62-104">Para conectar os componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="c6e62-104">To connect components in a data flow</span></span>  
  
1.  <span data-ttu-id="c6e62-105">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="c6e62-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c6e62-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="c6e62-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="c6e62-107">Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém o fluxo de dados no qual você deseja conectar componentes.</span><span class="sxs-lookup"><span data-stu-id="c6e62-107">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow in which you want to connect components.</span></span>  
  
4.  <span data-ttu-id="c6e62-108">Na superfície de design da guia **Fluxo de Dados** , selecione a transformação ou fonte que você quer conectar.</span><span class="sxs-lookup"><span data-stu-id="c6e62-108">On the design surface of the **Data Flow** tab, select the transformation or source that you want to connect.</span></span>  
  
5.  <span data-ttu-id="c6e62-109">Arraste a seta de saída verde de uma transformação ou uma fonte para uma transformação ou para um destino.</span><span class="sxs-lookup"><span data-stu-id="c6e62-109">Drag the green output arrow of a transformation or a source to a transformation or to a destination.</span></span> <span data-ttu-id="c6e62-110">Alguns componentes de fluxo de dados têm saídas de erro, que você pode conectar da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="c6e62-110">Some data flow components have error outputs that you can connect in the same way.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6e62-111">Alguns componentes de fluxo de dados podem ter múltiplas saídas, sendo possível conectar cada saída para uma transformação ou destino diferentes.</span><span class="sxs-lookup"><span data-stu-id="c6e62-111">Some data flow components can have multiple outputs and you can connect each output to a different transformation or destination.</span></span>  
  
6.  <span data-ttu-id="c6e62-112">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="c6e62-112">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e62-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6e62-113">See Also</span></span>  
 <span data-ttu-id="c6e62-114">[Adicionar ou excluir um componente em um fluxo de dados](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="c6e62-114">[Add or Delete a Component in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="c6e62-115">[Configurar uma saída de erro em um componente de fluxo de dados](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="c6e62-115">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="c6e62-116">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="c6e62-116">Data Flow</span></span>](data-flow.md)  
  
  
