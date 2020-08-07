---
title: Propriedades da autostoplist de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplistproperties.general.f1
- sql12.swb.fulltextsearch.ftstoplistproperties.schedule.f1
ms.assetid: 2e907f5b-0cf9-484a-afcf-a4e7f1e2f87f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ff27a1258d5164e3e93d34b6ff757993d6f6363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583779"
---
# <a name="full-text-stoplist-properties"></a><span data-ttu-id="6526d-102">Propriedades da lista de palavras irrelevantes (stoplist) de texto completo</span><span class="sxs-lookup"><span data-stu-id="6526d-102">Full-Text Stoplist Properties</span></span>
  <span data-ttu-id="6526d-103">Use esta caixa de diálogo para adicionar ou excluir palavras irrelevantes individuais, para excluir todas as palavras irrelevantes em um idioma específico ou para limpar a lista de palavras irrelevantes atual.</span><span class="sxs-lookup"><span data-stu-id="6526d-103">Use this dialog box to add or delete individual stopwords, delete all stopwords for a specific language, or clear the current stoplist.</span></span> <span data-ttu-id="6526d-104">Uma palavra irrelevante é uma palavra usada comumente que é incluída em uma lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="6526d-104">A stopword is a commonly used word that is included in a stoplist.</span></span> <span data-ttu-id="6526d-105">As palavras irrelevantes são omitidas da indexação de texto completo para tabelas que usam a lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="6526d-105">The stopwords in a stoplist are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="6526d-106">Para obter mais informações, veja [Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes para pesquisa de texto completo](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="6526d-106">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="6526d-107">**Para usar o SQL Server Management Studio para alterar propriedades da lista de palavras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="6526d-107">**To use SQL Server Management Studio to change stoplist properties**</span></span>  
  
-   [<span data-ttu-id="6526d-108">Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes (stoplists) para pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="6526d-108">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="6526d-109">Opções</span><span class="sxs-lookup"><span data-stu-id="6526d-109">Options</span></span>  
 <span data-ttu-id="6526d-110">**Ação**</span><span class="sxs-lookup"><span data-stu-id="6526d-110">**Action**</span></span>  
 <span data-ttu-id="6526d-111">Especifica a ação que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="6526d-111">Specifies the action that you want to perform.</span></span>  
  
 <span data-ttu-id="6526d-112">**Adicionar palavra irrelevante**</span><span class="sxs-lookup"><span data-stu-id="6526d-112">**Add stopword**</span></span>  
 <span data-ttu-id="6526d-113">Adicione uma palavra comumente usada à lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="6526d-113">Add a commonly used word to the stoplist.</span></span>  
  
 <span data-ttu-id="6526d-114">**Excluir palavra irrelevante**</span><span class="sxs-lookup"><span data-stu-id="6526d-114">**Delete stopword**</span></span>  
 <span data-ttu-id="6526d-115">Exclua uma palavra irrelevante da lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="6526d-115">Delete a stopword from the stoplist.</span></span>  
  
 <span data-ttu-id="6526d-116">**Excluir todas as palavras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="6526d-116">**Delete all stopwords**</span></span>  
 <span data-ttu-id="6526d-117">Exclua todas as palavras irrelevantes para um idioma específico.</span><span class="sxs-lookup"><span data-stu-id="6526d-117">Delete all the stopwords for a specific language.</span></span>  
  
 <span data-ttu-id="6526d-118">**Limpar lista de palavras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="6526d-118">**Clear stoplist**</span></span>  
 <span data-ttu-id="6526d-119">Limpe a lista de palavras irrelevantes, excluindo todas as palavras irrelevantes para todos os idiomas.</span><span class="sxs-lookup"><span data-stu-id="6526d-119">Clear the stoplist by deleting all the stopwords for all languages.</span></span>  
  
 <span data-ttu-id="6526d-120">**Palavra irrelevante**</span><span class="sxs-lookup"><span data-stu-id="6526d-120">**Stopword**</span></span>  
 <span data-ttu-id="6526d-121">Se você selecionou **Adicionar palavra irrelevante** ou **Excluir palavra irrelevante**, insira a palavra irrelevante no campo **Palavra irrelevante** .</span><span class="sxs-lookup"><span data-stu-id="6526d-121">If you selected **Add stopword** or **Delete stopword**, enter the stopword in the **Stopword** field.</span></span> <span data-ttu-id="6526d-122">Uma nova palavra irrelevante deve ser exclusiva; ou seja, ainda não deve estar na lista de palavras irrelevantes para o idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="6526d-122">A new stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
 <span data-ttu-id="6526d-123">**Idioma de texto completo**</span><span class="sxs-lookup"><span data-stu-id="6526d-123">**Full-text language**</span></span>  
 <span data-ttu-id="6526d-124">Se você selecionou **Adicionar palavra irrelevante**, **Excluir palavra irrelevante**, ou **Excluir todas as palavras irrelevantes**, selecione o idioma da palavra irrelevante ou palavras irrelevantes na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="6526d-124">If you selected **Add stopword**, **Delete stopword**, or **Delete all stopwords**, select the language of the stopword or stopwords from the list box.</span></span> <span data-ttu-id="6526d-125">Isso lista todos os idiomas de texto completo que têm suporte na instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="6526d-125">This lists all the full-text languages that are supported by the server instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6526d-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6526d-126">See Also</span></span>  
 <span data-ttu-id="6526d-127">[sys. fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6526d-127">[sys.fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span></span>  
 <span data-ttu-id="6526d-128">[sys. fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6526d-128">[sys.fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span></span>  
 <span data-ttu-id="6526d-129">[Configurar e gerenciar palavras irrelevantes e palavras irrelevantes para pesquisa de texto completo](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="6526d-129">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="6526d-130">[ALTER FULLTEXT STOPlist &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6526d-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="6526d-131">[CRIAR ponto de interrupção de texto completo &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6526d-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 [<span data-ttu-id="6526d-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6526d-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
