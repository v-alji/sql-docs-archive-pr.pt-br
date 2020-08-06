---
title: Editor de fonte de arquivo simples (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570151"
---
# <a name="flat-file-source-editor-columns-page"></a><span data-ttu-id="3aa4e-102">Editor de Fonte de Arquivo Simples (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="3aa4e-102">Flat File Source Editor (Columns Page)</span></span>
  <span data-ttu-id="3aa4e-103">Use o nó **Colunas** da caixa de diálogo **Editor de Fonte de Arquivo Simples** para mapear uma coluna de saída para cada coluna externa (fonte).</span><span class="sxs-lookup"><span data-stu-id="3aa4e-103">Use the **Columns** node of the **Flat File Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3aa4e-104">A `FileNameColumnName` propriedade da fonte de arquivo simples e a `FastParse` propriedade de suas colunas de saída não estão disponíveis no **Editor de fonte de arquivo simples**, mas podem ser definidas usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-104">The `FileNameColumnName` property of the Flat File source and the `FastParse` property of its output columns are not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="3aa4e-105">Para obter mais informações sobre estas propriedades, consulte a seção Fonte de Arquivo Simples em [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3aa4e-105">For more information on these properties, see the Flat File Source section of [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="3aa4e-106">Para saber mais sobre a fonte de Arquivo Simples, consulte [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="3aa4e-106">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3aa4e-107">Opções</span><span class="sxs-lookup"><span data-stu-id="3aa4e-107">Options</span></span>  
 <span data-ttu-id="3aa4e-108">**Colunas Externas Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="3aa4e-108">**Available External Columns**</span></span>  
 <span data-ttu-id="3aa4e-109">Exiba a lista de colunas externas disponíveis na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-109">View the list of available external columns in the data source.</span></span> <span data-ttu-id="3aa4e-110">Você não pode usar esta tabela para adicionar ou excluir colunas.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-110">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="3aa4e-111">**Coluna Externa**</span><span class="sxs-lookup"><span data-stu-id="3aa4e-111">**External Column**</span></span>  
 <span data-ttu-id="3aa4e-112">Exiba as colunas externas (fonte) na ordem em que serão lidas pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-112">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="3aa4e-113">É possível alterar esta ordem desmarcando as colunas selecionadas na tabela e selecionando as colunas externas da lista em uma ordem diferente.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-113">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="3aa4e-114">**Coluna de Saída**</span><span class="sxs-lookup"><span data-stu-id="3aa4e-114">**Output Column**</span></span>  
 <span data-ttu-id="3aa4e-115">Forneça um nome exclusivo para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-115">Provide a unique name for each output column.</span></span> <span data-ttu-id="3aa4e-116">O padrão é o nome da coluna externa (origem) selecionada; porém, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-116">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="3aa4e-117">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3aa4e-117">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa4e-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3aa4e-118">See Also</span></span>  
 <span data-ttu-id="3aa4e-119">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3aa4e-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="3aa4e-120">[Editor de fonte de arquivo simples &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3aa4e-120">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="3aa4e-121">[Editor de fonte de arquivo simples &#40;página saída de erro&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="3aa4e-121">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="3aa4e-122">Gerenciador de Conexões de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="3aa4e-122">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
