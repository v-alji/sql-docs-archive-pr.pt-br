---
title: Editor de origem ODBC (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.columns.f1
ms.assetid: 565984eb-8318-4be7-bebc-262209cf5065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a11ab6a86978366d07fbe63362f1702310b5d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681795"
---
# <a name="odbc-source-editor-columns-page"></a><span data-ttu-id="d8b50-102">Editor de Origem ODBC (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="d8b50-102">ODBC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="d8b50-103">Use a página **Colunas** da caixa de diálogo do **Editor de Origem ODBC** para mapear uma coluna de saída em cada coluna externa (origem).</span><span class="sxs-lookup"><span data-stu-id="d8b50-103">Use the **Columns** page of the **ODBC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="d8b50-104">Para obter mais informações sobre a origem ODBC, consulte [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="d8b50-104">To learn more about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d8b50-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="d8b50-105">Task List</span></span>  
 <span data-ttu-id="d8b50-106">**Para abrir a página Colunas do Editor de Origem ODBC**</span><span class="sxs-lookup"><span data-stu-id="d8b50-106">**To open the ODBC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="d8b50-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem a fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="d8b50-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
2.  <span data-ttu-id="d8b50-108">Na guia **Fluxo de Dados** , clique duas vezes na fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="d8b50-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
3.  <span data-ttu-id="d8b50-109">No **Editor de Origem ODBC**, clique em **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="d8b50-109">In the **ODBC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8b50-110">Opções</span><span class="sxs-lookup"><span data-stu-id="d8b50-110">Options</span></span>  
  
### <a name="available-external-columns"></a><span data-ttu-id="d8b50-111">Colunas Externas Disponíveis</span><span class="sxs-lookup"><span data-stu-id="d8b50-111">Available External Columns</span></span>  
 <span data-ttu-id="d8b50-112">A lista de colunas externas disponíveis na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b50-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="d8b50-113">Você não pode usar esta tabela para adicionar ou excluir colunas.</span><span class="sxs-lookup"><span data-stu-id="d8b50-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="d8b50-114">Selecionar as colunas a serem usadas da origem.</span><span class="sxs-lookup"><span data-stu-id="d8b50-114">Select the columns to use from the source.</span></span> <span data-ttu-id="d8b50-115">As colunas selecionadas são adicionadas à lista **Coluna Externa** na ordem em que são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d8b50-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="d8b50-116">Marque essa caixa de seleção **Selecionar Tudo** para selecionar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="d8b50-116">Select the **Select All** check box to select all of the columns.</span></span>  
  
### <a name="external-column"></a><span data-ttu-id="d8b50-117">Coluna Externa</span><span class="sxs-lookup"><span data-stu-id="d8b50-117">External Column</span></span>  
 <span data-ttu-id="d8b50-118">Uma exibição das colunas externas (origem) na ordem em que serão exibidas ao configurar os componentes que consomem os dados da origem ODBC.</span><span class="sxs-lookup"><span data-stu-id="d8b50-118">A view of the external (source) columns in the order that you see them when configuring components that consume data from the ODBC source.</span></span>  
  
### <a name="output-column"></a><span data-ttu-id="d8b50-119">Coluna de Saída</span><span class="sxs-lookup"><span data-stu-id="d8b50-119">Output Column</span></span>  
 <span data-ttu-id="d8b50-120">Insira um nome exclusivo para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="d8b50-120">Enter a unique name for each output column.</span></span> <span data-ttu-id="d8b50-121">O padrão é o nome da coluna externa (origem) selecionada; porém, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d8b50-121">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="d8b50-122">O nome inserido é exibido no Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="d8b50-122">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b50-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8b50-123">See Also</span></span>  
 <span data-ttu-id="d8b50-124">[Editor de origem ODBC &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d8b50-124">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="d8b50-125">Editor de Fonte ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b50-125">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
