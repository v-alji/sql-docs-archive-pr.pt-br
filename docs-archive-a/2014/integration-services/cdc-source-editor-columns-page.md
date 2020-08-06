---
title: Editor de origem CDC (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa30defb5e6873ea05e8e41c733477cf50d0dc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582575"
---
# <a name="cdc-source-editor-columns-page"></a><span data-ttu-id="c2868-102">Editor de Origem CDC (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="c2868-102">CDC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="c2868-103">Use a página **Colunas** da caixa de diálogo do **Editor de Origem CDC** para mapear uma coluna de saída em cada coluna externa (origem).</span><span class="sxs-lookup"><span data-stu-id="c2868-103">Use the **Columns** page of the **CDC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="c2868-104">Para obter mais informações sobre a origem CDC, consulte [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="c2868-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="c2868-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="c2868-105">Task List</span></span>  
 <span data-ttu-id="c2868-106">**Para abrir a página Colunas do Editor de Origem CDC**</span><span class="sxs-lookup"><span data-stu-id="c2868-106">**To open the CDC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="c2868-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem a origem CDC.</span><span class="sxs-lookup"><span data-stu-id="c2868-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="c2868-108">Na guia **Fluxo de Dados** , clique duas vezes na origem CDC.</span><span class="sxs-lookup"><span data-stu-id="c2868-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="c2868-109">No **Editor de Origem CDC**, clique em **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="c2868-109">In the **CDC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c2868-110">Opções</span><span class="sxs-lookup"><span data-stu-id="c2868-110">Options</span></span>  
 <span data-ttu-id="c2868-111">**Colunas Externas Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="c2868-111">**Available External Columns**</span></span>  
 <span data-ttu-id="c2868-112">A lista de colunas externas disponíveis na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c2868-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="c2868-113">Você não pode usar esta tabela para adicionar ou excluir colunas.</span><span class="sxs-lookup"><span data-stu-id="c2868-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="c2868-114">Selecione as colunas a serem usadas na origem.</span><span class="sxs-lookup"><span data-stu-id="c2868-114">Select the columns to use in the source.</span></span> <span data-ttu-id="c2868-115">As colunas selecionadas são adicionadas à lista **Coluna Externa** na ordem em que são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c2868-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="c2868-116">**Coluna Externa**</span><span class="sxs-lookup"><span data-stu-id="c2868-116">**External Column**</span></span>  
 <span data-ttu-id="c2868-117">Uma exibição das colunas externas (origem) na ordem em que serão exibidas ao configurar os componentes que consomem os dados da origem CDC.</span><span class="sxs-lookup"><span data-stu-id="c2868-117">A view of the external (source) columns in the order that you see them when configuring components that consume data from the CDC source.</span></span> <span data-ttu-id="c2868-118">Para alterar essa ordem, primeiro limpe as colunas selecionadas na lista **Colunas Externas Disponíveis** e depois selecione colunas externas na lista em uma ordem diferente.</span><span class="sxs-lookup"><span data-stu-id="c2868-118">To change this order, first clear the selected columns in the **Available External Columns** list, and then select external columns from the list in a different order.</span></span> <span data-ttu-id="c2868-119">As colunas selecionadas são adicionadas à lista **Coluna Externa** na ordem em que são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c2868-119">The selected columns are added to the **External Column** list in the order you select them.</span></span>  
  
 <span data-ttu-id="c2868-120">**Coluna de Saída**</span><span class="sxs-lookup"><span data-stu-id="c2868-120">**Output Column**</span></span>  
 <span data-ttu-id="c2868-121">Insira um nome exclusivo para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="c2868-121">Enter a unique name for each output column.</span></span> <span data-ttu-id="c2868-122">O padrão é o nome da coluna externa (origem) selecionada; porém, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c2868-122">The default is the name of the selected external (source) column, however you can choose any unique, descriptive name.</span></span> <span data-ttu-id="c2868-123">O nome inserido é exibido no Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="c2868-123">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2868-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2868-124">See Also</span></span>  
 <span data-ttu-id="c2868-125">[Editor de Origem CDC &#40;Página Gerenciador de Conexões&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c2868-125">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="c2868-126">Editor de Origem CDC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="c2868-126">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
