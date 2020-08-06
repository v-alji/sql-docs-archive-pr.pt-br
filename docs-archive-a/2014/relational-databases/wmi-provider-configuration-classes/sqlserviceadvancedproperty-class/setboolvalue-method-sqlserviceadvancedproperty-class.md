---
title: Definir pontos de interrupção | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684125"
---
# <a name="set-breakpoints"></a><span data-ttu-id="1ecb1-102">Definir Pontos de Interrupção</span><span class="sxs-lookup"><span data-stu-id="1ecb1-102">Set Breakpoints</span></span>
  <span data-ttu-id="1ecb1-103">Use a caixa de diálogo **Definir Pontos de Interrupção** para especificar os eventos nos quais habilitar pontos de interrupção e para controlar o comportamento do ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-103">Use the **Set Breakpoints** dialog box to specify the events on which to enable breakpoints and to control the behavior of the breakpoint.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1ecb1-104">Opções</span><span class="sxs-lookup"><span data-stu-id="1ecb1-104">Options</span></span>  
 <span data-ttu-id="1ecb1-105">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-105">**Enabled**</span></span>  
 <span data-ttu-id="1ecb1-106">Selecione para habilitar um ponto de interrupção em um evento.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-106">Select to enable a breakpoint on an event.</span></span>  
  
 <span data-ttu-id="1ecb1-107">**Break Condition**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-107">**Break Condition**</span></span>  
 <span data-ttu-id="1ecb1-108">Exiba uma lista de eventos disponíveis nos quais definir pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-108">View a list of available events on which to set breakpoints.</span></span>  
  
 <span data-ttu-id="1ecb1-109">**Hit Count Type**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-109">**Hit Count Type**</span></span>  
 <span data-ttu-id="1ecb1-110">Especifique quando o ponto de interrupção entra em vigor.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-110">Specify when the breakpoint takes effect.</span></span>  
  
|<span data-ttu-id="1ecb1-111">Valor</span><span class="sxs-lookup"><span data-stu-id="1ecb1-111">Value</span></span>|<span data-ttu-id="1ecb1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1ecb1-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ecb1-113">**Always**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-113">**Always**</span></span>|<span data-ttu-id="1ecb1-114">A execução será sempre suspensa quando ocorrer o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-114">Execution is always suspended when the breakpoint is hit.</span></span>|  
|<span data-ttu-id="1ecb1-115">**Contagem de ocorrências igual a**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-115">**Hit count equals**</span></span>|<span data-ttu-id="1ecb1-116">A execução será suspensa quando o número de vezes que o ponto de interrupção ocorreu for igual à contagem de ocorrências.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-116">Execution is suspended when the number of times the breakpoint has occurred is equal to the hit count.</span></span>|  
|<span data-ttu-id="1ecb1-117">**Ocorrência maior ou igual**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-117">**Hit greater or equal**</span></span>|<span data-ttu-id="1ecb1-118">A execução será suspensa quando o número de vezes que o ponto de interrupção ocorreu for igual ou maior que a contagem de ocorrências.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-118">Execution is suspended when the number of times the breakpoint has occurred is equal to or greater than the hit count.</span></span>|  
|<span data-ttu-id="1ecb1-119">**Várias contagens de ocorrências**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-119">**Hit count multiple**</span></span>|<span data-ttu-id="1ecb1-120">A execução será suspensa quando ocorrerem várias contagens de ocorrências.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-120">Execution is suspended when a multiple of the hit count occurs.</span></span> <span data-ttu-id="1ecb1-121">Por exemplo, se você definir esta opção como 5, a execução será suspensa a cada quinta vez.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-121">For example, if you set this option to 5, execution is suspended every fifth time.</span></span>|  
  
 <span data-ttu-id="1ecb1-122">**Contagem de Ocorrências**</span><span class="sxs-lookup"><span data-stu-id="1ecb1-122">**Hit Count**</span></span>  
 <span data-ttu-id="1ecb1-123">Especifique o número de ocorrências no qual engatilhe uma interrupção.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-123">Specify the number of hits at which to trigger a break.</span></span> <span data-ttu-id="1ecb1-124">Esta opção não estará disponível se o ponto de interrupção estiver sempre ativado.</span><span class="sxs-lookup"><span data-stu-id="1ecb1-124">This option is not available if the breakpoint is always in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ecb1-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ecb1-125">See Also</span></span>  
 [<span data-ttu-id="1ecb1-126">Depurando o fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="1ecb1-126">Debugging Control Flow</span></span>](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
