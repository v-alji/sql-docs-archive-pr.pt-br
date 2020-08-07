---
title: Propriedades do índice de texto completo (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.columns.f1
ms.assetid: 75e52edb-0d07-4393-9345-8b5af4561e35
author: rothja
ms.author: jroth
ms.openlocfilehash: f947af04463948ef551c6df866d5a306c248c6b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583790"
---
# <a name="full-text-index-properties-columns-page"></a><span data-ttu-id="0fcde-102">Propriedades do Índice de Texto Completo (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="0fcde-102">Full-Text Index Properties (Columns Page)</span></span>
  <span data-ttu-id="0fcde-103">**Para exibir ou alterar as propriedades de um índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="0fcde-103">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="0fcde-104">Gerenciar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="0fcde-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="0fcde-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="0fcde-105">UI element list</span></span>  
 <span data-ttu-id="0fcde-106">**Índice exclusivo**</span><span class="sxs-lookup"><span data-stu-id="0fcde-106">**Unique index**</span></span>  
 <span data-ttu-id="0fcde-107">Selecione um índice na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="0fcde-107">Select an index from the drop down list.</span></span> <span data-ttu-id="0fcde-108">O índice deve ser um índice não nulo, exclusivo e de coluna de chave única.</span><span class="sxs-lookup"><span data-stu-id="0fcde-108">The index must be a single-key-column, unique, non-nullable index.</span></span>  
  
 <span data-ttu-id="0fcde-109">**Selecione as colunas qualificadas que serão indexadas com texto completo.**</span><span class="sxs-lookup"><span data-stu-id="0fcde-109">**Select the eligible columns that will be full-text indexed**</span></span>  
 <span data-ttu-id="0fcde-110">A grade exibe as colunas da tabela que estão disponíveis para esse índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="0fcde-110">The grid displays the table columns that are available for this full-text index.</span></span> <span data-ttu-id="0fcde-111">As colunas indexadas atualmente com texto completo são verificadas.</span><span class="sxs-lookup"><span data-stu-id="0fcde-111">Columns that are currently full-text indexed are checked.</span></span> <span data-ttu-id="0fcde-112">Opcionalmente, você pode verificar colunas adicionais que deseja que sejam indexadas com texto completo.</span><span class="sxs-lookup"><span data-stu-id="0fcde-112">Optionally, you can check additional columns that you want to be full-text indexed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0fcde-113">Verifique se pelo menos uma coluna está verificada antes de clicar em OK.</span><span class="sxs-lookup"><span data-stu-id="0fcde-113">Ensure that at least one column is checked before you click OK.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fcde-114">**Colunas disponíveis**</span><span class="sxs-lookup"><span data-stu-id="0fcde-114">**Available Columns**</span></span>|<span data-ttu-id="0fcde-115">O nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="0fcde-115">The column name.</span></span>|  
|<span data-ttu-id="0fcde-116">**Idioma do separador de palavras**</span><span class="sxs-lookup"><span data-stu-id="0fcde-116">**Language for Word Breaker**</span></span>|<span data-ttu-id="0fcde-117">O idioma cujos separadores de palavras e lematizadores executam a análise linguística em todos os dados indexados com texto completo.</span><span class="sxs-lookup"><span data-stu-id="0fcde-117">The language whose word breakers and stemmers perform linguistic analysis on all full-text indexed data.</span></span><br /><br /> <span data-ttu-id="0fcde-118">Para obter mais informações, consulte [configurar e gerenciar separadores de palavras e lematizadores para pesquisa](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) e [escolha um idioma ao criar um índice de texto completo](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span><span class="sxs-lookup"><span data-stu-id="0fcde-118">For more information, see [Configure and Manage Word Breakers and Stemmers for Search](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) and [Choose a Language When Creating a Full-Text Index](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span></span>|  
|<span data-ttu-id="0fcde-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0fcde-119">**Type**</span></span>|<span data-ttu-id="0fcde-120">O nome da coluna da tabela que mantém o tipo de documento da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="0fcde-120">The name of the table column that holds the document type of the selected column.</span></span> <span data-ttu-id="0fcde-121">Trata-se de uma propriedade somente leitura.</span><span class="sxs-lookup"><span data-stu-id="0fcde-121">This is a read-only property.</span></span>|  
|<span data-ttu-id="0fcde-122">**Semântica Estatística**</span><span class="sxs-lookup"><span data-stu-id="0fcde-122">**Statistical Semantics**</span></span>|<span data-ttu-id="0fcde-123">Especifique se habilitará a indexação semântica da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="0fcde-123">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="0fcde-124">Para obter mais informações, veja [Pesquisa semântica &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0fcde-124">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="0fcde-125">Se você selecionar um **Idioma** antes de selecionar **Semântica Estatística**, e o idioma selecionado não tiver um Modelo de Idioma Semântico associado, a caixa de seleção **Semântica Estatística** será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="0fcde-125">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="0fcde-126">Se você selecionar **Semântica Estatística** antes de selecionar um **Idioma**, os idiomas disponíveis na caixa de combinação suspensa serão restringidos a esses para os quais o Modelo de Idioma Semântico dá suporte.</span><span class="sxs-lookup"><span data-stu-id="0fcde-126">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fcde-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0fcde-127">See Also</span></span>  
 [<span data-ttu-id="0fcde-128">Popular índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="0fcde-128">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
