---
title: Editor de origem ADO NET (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.columns.f1
ms.assetid: fbc205b9-2001-4737-a76b-1ba777344bd9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d89f8c926761b9149f19269bc2519c12bcf130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574238"
---
# <a name="ado-net-source-editor-columns-page"></a><span data-ttu-id="d0185-102">Editor de Origem ADO NET (Página Colunas)</span><span class="sxs-lookup"><span data-stu-id="d0185-102">ADO NET Source Editor (Columns Page)</span></span>
  <span data-ttu-id="d0185-103">Use a página **Colunas** da caixa de diálogo do **Editor de Origem ADO NET** para mapear uma coluna de saída em cada coluna externa (origem).</span><span class="sxs-lookup"><span data-stu-id="d0185-103">Use the **Columns** page of the **ADO NET Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="d0185-104">Para obter mais informações sobre a origem ADO NET, consulte [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="d0185-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="d0185-105">**Para abrir a página Colunas**</span><span class="sxs-lookup"><span data-stu-id="d0185-105">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="d0185-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tenha a origem ADO NET.</span><span class="sxs-lookup"><span data-stu-id="d0185-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="d0185-107">Na guia **Fluxo de Dados** , clique duas vezes na origem ADO NET.</span><span class="sxs-lookup"><span data-stu-id="d0185-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="d0185-108">No **Editor de Origem ADO NET**, clique em **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="d0185-108">In the **ADO NET Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0185-109">Opções</span><span class="sxs-lookup"><span data-stu-id="d0185-109">Options</span></span>  
 <span data-ttu-id="d0185-110">**Colunas Externas Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="d0185-110">**Available External Columns**</span></span>  
 <span data-ttu-id="d0185-111">Exiba a lista de colunas externas disponíveis na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d0185-111">View the list of available external columns in the data source.</span></span> <span data-ttu-id="d0185-112">Você não pode usar esta tabela para adicionar ou excluir colunas.</span><span class="sxs-lookup"><span data-stu-id="d0185-112">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="d0185-113">**Coluna Externa**</span><span class="sxs-lookup"><span data-stu-id="d0185-113">**External Column**</span></span>  
 <span data-ttu-id="d0185-114">Exiba as colunas externas (origem) na ordem em que serão exibidas ao configurar os componentes que consomem os dados dessa origem.</span><span class="sxs-lookup"><span data-stu-id="d0185-114">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span>  
  
 <span data-ttu-id="d0185-115">**Coluna de Saída**</span><span class="sxs-lookup"><span data-stu-id="d0185-115">**Output Column**</span></span>  
 <span data-ttu-id="d0185-116">Forneça um nome exclusivo para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="d0185-116">Provide a unique name for each output column.</span></span> <span data-ttu-id="d0185-117">O padrão é o nome da coluna externa (origem) selecionada; porém, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d0185-117">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="d0185-118">O nome fornecido será exibido no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0185-118">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0185-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0185-119">See Also</span></span>  
 <span data-ttu-id="d0185-120">[Editor de origem ADO NET &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0185-120">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d0185-121">[Editor de origem ADO NET &#40;página saída de erro&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0185-121">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d0185-122">Gerenciador de conexões ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d0185-122">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
