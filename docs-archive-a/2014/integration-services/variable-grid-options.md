---
title: Opções de grade variáveis | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variableoptionswindow.f1
helpviewer_keywords:
- Choose Variable Columns dialog box
ms.assetid: 7cccc230-3b20-4074-804f-3448d9616a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b90e1a3c69e4eaf1f123603e0082ecb1eda4e893
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570741"
---
# <a name="variable-grid-options"></a><span data-ttu-id="fab04-102">Opções de Grade Variáveis</span><span class="sxs-lookup"><span data-stu-id="fab04-102">Variable Grid Options</span></span>
  <span data-ttu-id="fab04-103">Use a caixa de diálogo **Opções de Grade Variáveis** para selecionar as colunas para serem exibidas na janela **Variáveis** e para selecionar os filtros para serem aplicados na lista de variáveis.</span><span class="sxs-lookup"><span data-stu-id="fab04-103">Use the **Variable Grid Options** dialog box to select the columns that will display in the **Variables** window and to select the filters to apply to the list of variables.</span></span> <span data-ttu-id="fab04-104">Para obter mais informações sobre as propriedades de variáveis correspondentes, consulte [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="fab04-104">For more information about the corresponding variable properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-filter"></a><span data-ttu-id="fab04-105">Opções para filtrar</span><span class="sxs-lookup"><span data-stu-id="fab04-105">Options for Filter</span></span>  
 <span data-ttu-id="fab04-106">**Mostrar variáveis de sistema**</span><span class="sxs-lookup"><span data-stu-id="fab04-106">**Show system variables**</span></span>  
 <span data-ttu-id="fab04-107">Selecione para listar variáveis de sistema na janela **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="fab04-107">Select to list system variables in the **Variables** window.</span></span> <span data-ttu-id="fab04-108">As variáveis de sistema são pré-definidas.</span><span class="sxs-lookup"><span data-stu-id="fab04-108">System variables are predefined.</span></span> <span data-ttu-id="fab04-109">Você não pode adicionar ou excluir as variáveis de sistema.</span><span class="sxs-lookup"><span data-stu-id="fab04-109">You cannot add or delete system variables.</span></span> <span data-ttu-id="fab04-110">É possível modificar as configurações da propriedade **RaiseChangedEvent** .</span><span class="sxs-lookup"><span data-stu-id="fab04-110">You can modify the **RaiseChangedEvent** property setting.</span></span>  
  
 <span data-ttu-id="fab04-111">Essa lista é codificada por cor.</span><span class="sxs-lookup"><span data-stu-id="fab04-111">This list is color coded.</span></span> <span data-ttu-id="fab04-112">As variáveis do sistema são cinza e as variáveis definidas pelo usuário são pretas.</span><span class="sxs-lookup"><span data-stu-id="fab04-112">System variables are gray, and user-defined variables are black.</span></span>  
  
 <span data-ttu-id="fab04-113">**Mostrar variáveis de todos os escopos**</span><span class="sxs-lookup"><span data-stu-id="fab04-113">**Show variables of all scopes**</span></span>  
 <span data-ttu-id="fab04-114">Selecione para mostrar variáveis dentro do escopo do pacote, e dentro do escopo de contêineres, tarefas ou manipuladores de eventos no pacote.</span><span class="sxs-lookup"><span data-stu-id="fab04-114">Select to show variables within the scope the package, and within the scope of containers, tasks, and event handlers in the package.</span></span> <span data-ttu-id="fab04-115">Marque essa opção para mostrar somente variáveis dentro do escopo do pacote e dentro do escopo de um contêiner, tarefa ou manipulador de eventos selecionado.</span><span class="sxs-lookup"><span data-stu-id="fab04-115">Clear this option to show only variables within the scope of the package and within the scope of a selected container, task, or event handler.</span></span>  
  
 <span data-ttu-id="fab04-116">Para obter mais informações sobre escopo variável, consulte [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="fab04-116">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-columns"></a><span data-ttu-id="fab04-117">Opções para colunas</span><span class="sxs-lookup"><span data-stu-id="fab04-117">Options for Columns</span></span>  
 <span data-ttu-id="fab04-118">Selecione as colunas que você quer que sejam exibidas na janela **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="fab04-118">Select the columns that you want to appear in the **Variables** window.</span></span>  
  
-   <span data-ttu-id="fab04-119">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="fab04-119">**Scope**</span></span>  
  
-   <span data-ttu-id="fab04-120">**Data type**</span><span class="sxs-lookup"><span data-stu-id="fab04-120">**Data type**</span></span>  
  
-   <span data-ttu-id="fab04-121">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fab04-121">**Value**</span></span>  
  
-   <span data-ttu-id="fab04-122">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="fab04-122">**Namespace**</span></span>  
  
-   <span data-ttu-id="fab04-123">**Levantar evento quando o valor da variável for alterado**</span><span class="sxs-lookup"><span data-stu-id="fab04-123">**Raise event when variable value changes**</span></span>  
  
-   <span data-ttu-id="fab04-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fab04-124">**Description**</span></span>  
  
-   <span data-ttu-id="fab04-125">**Expression**</span><span class="sxs-lookup"><span data-stu-id="fab04-125">**Expression**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab04-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fab04-126">See Also</span></span>  
 <span data-ttu-id="fab04-127">[Janela variáveis](../../2014/integration-services/variables-window.md) </span><span class="sxs-lookup"><span data-stu-id="fab04-127">[Variables Window](../../2014/integration-services/variables-window.md) </span></span>  
 <span data-ttu-id="fab04-128">[Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="fab04-128">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="fab04-129">[Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="fab04-129">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="fab04-130">Manipuladores de eventos do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fab04-130">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
