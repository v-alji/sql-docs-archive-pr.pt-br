---
title: NovaList de palavras irrelevantes de texto completo (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplist.general.f1
ms.assetid: 97f8e82d-82ab-4525-91c9-1ee3ae217309
author: rothja
ms.author: jroth
ms.openlocfilehash: a6272fb570b85989f38c8187e29712966862710d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582614"
---
# <a name="new-full-text-stoplist-general-page"></a><span data-ttu-id="22041-102">Nova Lista de Palavras Irrelevantes de Texto Completo (página Geral)</span><span class="sxs-lookup"><span data-stu-id="22041-102">New Full-Text Stoplist (General Page)</span></span>
  <span data-ttu-id="22041-103">Use esta caixa de diálogo para criar uma lista de palavras irrelevantes (stoplist) de texto completo.</span><span class="sxs-lookup"><span data-stu-id="22041-103">Use this dialog box to create a full-text stoplist.</span></span> <span data-ttu-id="22041-104">Uma *lista de palavras irrelevantes* é um conjunto de palavras usadas com frequência, chamadas *palavras irrelevantes*, que são omitidas da indexação de texto completo de tabelas que usam a lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="22041-104">A *stoplist* is a set of commonly used words, called *stopwords*, that are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="22041-105">Para obter mais informações, veja [Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes para pesquisa de texto completo](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="22041-105">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="22041-106">**Para usar o SQL Server Management Studio para criar uma lista de palavras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="22041-106">**To use SQL Server Management Studio to create a stoplist**</span></span>  
  
-   [<span data-ttu-id="22041-107">Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes (stoplists) para pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="22041-107">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="22041-108">Opções</span><span class="sxs-lookup"><span data-stu-id="22041-108">Options</span></span>  
 <span data-ttu-id="22041-109">**Nome da lista de palavras irrelevantes de texto completo**</span><span class="sxs-lookup"><span data-stu-id="22041-109">**Full-text stoplist name**</span></span>  
 <span data-ttu-id="22041-110">Digite o nome da lista de palavras irrelevantes de texto completo.</span><span class="sxs-lookup"><span data-stu-id="22041-110">Enter the name of the full-text stoplist.</span></span>  
  
 <span data-ttu-id="22041-111">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="22041-111">**Owner**</span></span>  
 <span data-ttu-id="22041-112">Especifique o proprietário da lista de palavras irrelevantes de texto completo.</span><span class="sxs-lookup"><span data-stu-id="22041-112">Specify the owner of the full-text stoplist.</span></span> <span data-ttu-id="22041-113">Para atribuir a propriedade a você, ou seja, para o usuário atual, deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="22041-113">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span>  
  
 <span data-ttu-id="22041-114">Para especificar um usuário diferente, clique no botão Procurar.</span><span class="sxs-lookup"><span data-stu-id="22041-114">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-stoplist-options"></a><span data-ttu-id="22041-115">Opções para criar listas de palavras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="22041-115">Create stoplist options</span></span>  
 <span data-ttu-id="22041-116">Clique em uma destas opções de criação:</span><span class="sxs-lookup"><span data-stu-id="22041-116">Click one of the following create options:</span></span>  
  
 <span data-ttu-id="22041-117">**Criar uma lista de palavras irrelevantes vazia**</span><span class="sxs-lookup"><span data-stu-id="22041-117">**Create an empty stoplist**</span></span>  
 <span data-ttu-id="22041-118">A nova lista de palavras irrelevantes não conterá nenhuma palavra irrelevante.</span><span class="sxs-lookup"><span data-stu-id="22041-118">The new stoplist will not contain any stopwords.</span></span>  
  
 <span data-ttu-id="22041-119">**Criar com base na lista de palavras irrelevantes do sistema**</span><span class="sxs-lookup"><span data-stu-id="22041-119">**Create from the system stoplist**</span></span>  
 <span data-ttu-id="22041-120">A nova lista de palavras irrelevantes será criada a partir da lista de palavras irrelevantes existente por padrão no [Banco de dados de recursos](../relational-databases/databases/resource-database.md).</span><span class="sxs-lookup"><span data-stu-id="22041-120">The new stoplist is created from the stoplist that exists by default in the [Resource database](../relational-databases/databases/resource-database.md).</span></span>  
  
 <span data-ttu-id="22041-121">**Criar com base em uma lista de palavras irrelevantes existente**</span><span class="sxs-lookup"><span data-stu-id="22041-121">**Create from an existing full-text stoplist**</span></span>  
 <span data-ttu-id="22041-122">A nova lista de palavras irrelevantes será criada a partir da cópia de uma lista de palavras irrelevantes existente.</span><span class="sxs-lookup"><span data-stu-id="22041-122">The new stoplist is created by copying an existing stoplist.</span></span>  
  
 <span data-ttu-id="22041-123">**Banco de dados de origem**</span><span class="sxs-lookup"><span data-stu-id="22041-123">**Source database**</span></span>  
 <span data-ttu-id="22041-124">Especifica o nome do banco de dados ao qual a lista de palavras irrelevantes existente pertence.</span><span class="sxs-lookup"><span data-stu-id="22041-124">Specifies the name of the database to which the existing stoplist belongs.</span></span> <span data-ttu-id="22041-125">Por padrão, o banco de dados atual é selecionado.</span><span class="sxs-lookup"><span data-stu-id="22041-125">The current database is selected by default.</span></span> <span data-ttu-id="22041-126">Você tem a opção de selecionar um outro banco de dados na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="22041-126">Optionally, select a different database from the list box.</span></span>  
  
 <span data-ttu-id="22041-127">**Lista de palavras irrelevantes de origem**</span><span class="sxs-lookup"><span data-stu-id="22041-127">**Source stoplist**</span></span>  
 <span data-ttu-id="22041-128">Especifica o nome de um lista de palavras irrelevantes existente.</span><span class="sxs-lookup"><span data-stu-id="22041-128">Specifies the name of an existing stoplist.</span></span> <span data-ttu-id="22041-129">Na relação de listas de palavras irrelevantes disponíveis, selecione uma para usar como origem.</span><span class="sxs-lookup"><span data-stu-id="22041-129">From the list of available stoplists, select the one to use as the source.</span></span> <span data-ttu-id="22041-130">As listas de palavras irrelevantes disponíveis são relacionadas na ordem em aparecem no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="22041-130">The available stoplists are listed in the order in which they appear in Object Explorer.</span></span>  
  
 <span data-ttu-id="22041-131">Se qualquer idioma especificado nas palavras irrelevantes da lista de palavras irrelevantes de origem não estiver registrado no banco de dados atual, CREATE FULLTEXT STOPLIST terá êxito, mas serão retornados avisos e as palavras irrelevantes correspondentes não serão adicionadas.</span><span class="sxs-lookup"><span data-stu-id="22041-131">If any languages specified in the stop words of the source stoplist are not registered in the current database, CREATE FULLTEXT STOPLIST succeeds, but warning(s) are returned and the corresponding stop words are not added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22041-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22041-132">See Also</span></span>  
 <span data-ttu-id="22041-133">[ALTER FULLTEXT STOPlist &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22041-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="22041-134">[CRIAR ponto de interrupção de texto completo &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22041-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="22041-135">[Remover texto completo de lista de palavras irrelevantes &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22041-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="22041-136">[Configurar e gerenciar palavras irrelevantes e palavras irrelevantes para pesquisa de texto completo](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="22041-136">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 [<span data-ttu-id="22041-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="22041-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
  
