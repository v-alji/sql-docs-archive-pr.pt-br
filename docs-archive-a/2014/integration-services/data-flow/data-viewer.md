---
title: Visualizador de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc576981e875eade84dd3576f4ed93b66784411f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574825"
---
# <a name="data-viewer"></a><span data-ttu-id="b5520-102">Visualizador de Dados</span><span class="sxs-lookup"><span data-stu-id="b5520-102">Data Viewer</span></span>
  <span data-ttu-id="b5520-103">Se um caminho for configurado para usar um visualizador de dados, o Visualizador de Dados exibirá o buffer de dados por buffer à medida que os dados se movimentarem entre dois componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="b5520-103">If a path is configured to use a data viewer, the Data Viewer displays the data buffer by buffer as data moves between two data flow components.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5520-104">Opções</span><span class="sxs-lookup"><span data-stu-id="b5520-104">Options</span></span>  
 <span data-ttu-id="b5520-105">**Seta Verde**</span><span class="sxs-lookup"><span data-stu-id="b5520-105">**Green arrow**</span></span>  
 <span data-ttu-id="b5520-106">Clique para exibir os dados do próximo buffer.</span><span class="sxs-lookup"><span data-stu-id="b5520-106">Click to display the data in the next buffer.</span></span> <span data-ttu-id="b5520-107">Se os dados puderem ser movidos em um único buffer, esta opção não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="b5520-107">If the data can be moved in a single buffer, this option is not available.</span></span>  
  
 <span data-ttu-id="b5520-108">**Desanexar**</span><span class="sxs-lookup"><span data-stu-id="b5520-108">**Detach**</span></span>  
 <span data-ttu-id="b5520-109">Desanexe o visualizador de dados.</span><span class="sxs-lookup"><span data-stu-id="b5520-109">Detach the data viewer.</span></span>  
  
 <span data-ttu-id="b5520-110">**Observação** Desanexar um visualizador de dados não exclui o visualizador de dados.</span><span class="sxs-lookup"><span data-stu-id="b5520-110">**Note** Detaching a data viewer does not delete the data viewer.</span></span> <span data-ttu-id="b5520-111">Se o visualizador de dados foi desanexado, os dados continuarão fluindo pelo caminho, mas os dados no visualizador não são atualizados para corresponder aos dados em cada buffer.</span><span class="sxs-lookup"><span data-stu-id="b5520-111">If the data viewer has been detached, data continues to flow through the path, but the data in the viewer is not updated to match the data in each buffer.</span></span>  
  
 <span data-ttu-id="b5520-112">**Anexar**</span><span class="sxs-lookup"><span data-stu-id="b5520-112">**Attach**</span></span>  
 <span data-ttu-id="b5520-113">Anexe um visualizador de dados.</span><span class="sxs-lookup"><span data-stu-id="b5520-113">Attach a data viewer.</span></span>  
  
 <span data-ttu-id="b5520-114">**Observação** Quando o visualizador de dados é anexado, ele exibe informações de cada buffer no fluxo de dados e, em seguida, pausa.</span><span class="sxs-lookup"><span data-stu-id="b5520-114">**Note** When the data viewer is attached, it displays information from each buffer in the data flow and then pauses.</span></span> <span data-ttu-id="b5520-115">Você pode avançar pelos buffers usando a seta verde.</span><span class="sxs-lookup"><span data-stu-id="b5520-115">You can advance through the buffers by using the green arrow.</span></span>  
  
 <span data-ttu-id="b5520-116">**Copiar Dados**</span><span class="sxs-lookup"><span data-stu-id="b5520-116">**Copy Data**</span></span>  
 <span data-ttu-id="b5520-117">Copie os dados no buffer atual para a Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="b5520-117">Copy data in the current buffer to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5520-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5520-118">See Also</span></span>  
 [<span data-ttu-id="b5520-119">Depurar o fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="b5520-119">Debugging Data Flow</span></span>](../troubleshooting/debugging-data-flow.md)  
  
  
