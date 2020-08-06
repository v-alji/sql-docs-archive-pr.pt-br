---
title: Transformação Multicast | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686359"
---
# <a name="multicast-transformation"></a><span data-ttu-id="8ee61-102">Transformação Difusão Seletiva</span><span class="sxs-lookup"><span data-stu-id="8ee61-102">Multicast Transformation</span></span>
  <span data-ttu-id="8ee61-103">A transformação Multicast distribui sua entrada em uma ou mais saídas.</span><span class="sxs-lookup"><span data-stu-id="8ee61-103">The Multicast transformation distributes its input to one or more outputs.</span></span> <span data-ttu-id="8ee61-104">Essa transformação é semelhante à transformação de divisão condicional.</span><span class="sxs-lookup"><span data-stu-id="8ee61-104">This transformation is similar to the Conditional Split transformation.</span></span> <span data-ttu-id="8ee61-105">Ambas as transformações dirigem uma entrada para saídas múltiplas.</span><span class="sxs-lookup"><span data-stu-id="8ee61-105">Both transformations direct an input to multiple outputs.</span></span> <span data-ttu-id="8ee61-106">A diferença entre as duas é que a transformação de difusão seletiva dirige todas as linhas para todas as saídas e a divisão condicional dirige uma linha para uma única saída.</span><span class="sxs-lookup"><span data-stu-id="8ee61-106">The difference between the two is that the Multicast transformation directs every row to every output, and the Conditional Split directs a row to a single output.</span></span> <span data-ttu-id="8ee61-107">Para obter mais informações, consulte [Conditional Split Transformation](conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8ee61-107">For more information, see [Conditional Split Transformation](conditional-split-transformation.md).</span></span>  
  
 <span data-ttu-id="8ee61-108">Configura-se a transformação de difusão seletiva adicionando saídas.</span><span class="sxs-lookup"><span data-stu-id="8ee61-108">You configure the Multicast transformation by adding outputs.</span></span>  
  
 <span data-ttu-id="8ee61-109">Usando a transformação de difusão seletiva, um pacote pode criar cópias lógicas de dados.</span><span class="sxs-lookup"><span data-stu-id="8ee61-109">Using the Multicast transformation, a package can create logical copies of data.</span></span> <span data-ttu-id="8ee61-110">Essa capacidade é útil quando o pacote precisar aplicar vários conjuntos de transformações aos mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="8ee61-110">This capability is useful when the package needs to apply multiple sets of transformations to the same data.</span></span> <span data-ttu-id="8ee61-111">Por exemplo, uma cópia dos dados é agregada e somente o resumo informativo é carregado em seu destino, enquanto outra cópia dos dados é estendida com valores de pesquisa e colunas derivadas antes que seja carregada em seu destino.</span><span class="sxs-lookup"><span data-stu-id="8ee61-111">For example, one copy of the data is aggregated and only the summary information is loaded into its destination, while another copy of the data is extended with lookup values and derived columns before it is loaded into its destination.</span></span>  
  
 <span data-ttu-id="8ee61-112">Essa transformação tem uma entrada e múltiplas saídas.</span><span class="sxs-lookup"><span data-stu-id="8ee61-112">This transformation has one input and multiple outputs.</span></span> <span data-ttu-id="8ee61-113">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="8ee61-113">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-multicast-transformation"></a><span data-ttu-id="8ee61-114">Configuração da transformação Multicast</span><span class="sxs-lookup"><span data-stu-id="8ee61-114">Configuration of the Multicast Transformation</span></span>  
 <span data-ttu-id="8ee61-115">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="8ee61-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8ee61-116">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Multicast** , consulte [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8ee61-116">For information about the properties that you can set in the **Multicast Transformation Editor** dialog box, see [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="8ee61-117">Para obter informações sobre as propriedades que podem ser definidas programaticamente, consulte [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8ee61-117">For information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8ee61-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8ee61-118">Related Tasks</span></span>  
 <span data-ttu-id="8ee61-119">Para obter informações sobre como definir as propriedades deste componente, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="8ee61-119">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee61-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ee61-120">See Also</span></span>  
 <span data-ttu-id="8ee61-121">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8ee61-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="8ee61-122">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="8ee61-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
