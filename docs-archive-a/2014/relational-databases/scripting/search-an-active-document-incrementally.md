---
title: Pesquisar um documento ativo de forma incremental
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], incremental
- Query Editor [SQL Server Management Studio], incremental search
- incremental searches [SQL Server Management Studio]
ms.assetid: 490bb36c-dd43-4219-9e2a-ff27046b9395
author: rothja
ms.author: jroth
ms.openlocfilehash: aefc2f0b7abff5992a8f4f7817e564ef1b72009d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570598"
---
# <a name="search-an-active-document-incrementally"></a><span data-ttu-id="e2d7d-102">Pesquisar um documento ativo de forma incremental</span><span class="sxs-lookup"><span data-stu-id="e2d7d-102">Search an Active Document Incrementally</span></span>
  <span data-ttu-id="e2d7d-103">É possível pesquisar um único documento ou janela de forma incremental digitando texto.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-103">You can search a single document or window incrementally by entering text.</span></span> <span data-ttu-id="e2d7d-104">A operação de pesquisa realça o primeiro conjunto de caracteres que corresponde aos caracteres digitados durante a pesquisa incremental no documento ou na janela.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-104">The search operation highlights the first set of characters that matches the characters entered during the incremental search in the document or window.</span></span> <span data-ttu-id="e2d7d-105">A pesquisa incremental pesquisa automaticamente todo o texto dentro de um documento ou de uma janela, com exceção de texto oculto.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-105">Incremental search automatically searches all of the text within a document or window except for text that has been hidden.</span></span>  
  
 <span data-ttu-id="e2d7d-106">Na opção **Diferenciar Maiúsculas de Minúsculas** , a pesquisa incremental usa os critérios de sua pesquisa anterior.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-106">For the **Match case** option, incremental search uses the criteria from your previous search.</span></span> <span data-ttu-id="e2d7d-107">Por exemplo, se você pesquisou vários arquivos usando a caixa de diálogo **Localizar nos Arquivos** e selecionou **Distinguir Maiúsculas de Minúsculas**, se uma nova pesquisa for incremental, a pesquisa considerará maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-107">For example, if you searched across multiple files using the **Find in Files** dialog box and select **Match Case**, and you next search incrementally, the search will be case-sensitive.</span></span>  
  
### <a name="to-search-incrementally"></a><span data-ttu-id="e2d7d-108">Para pesquisar incrementalmente</span><span class="sxs-lookup"><span data-stu-id="e2d7d-108">To search incrementally</span></span>  
  
1.  <span data-ttu-id="e2d7d-109">Abra o arquivo ou a janela que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-109">Open the file or window to you want to search.</span></span>  
  
2.  <span data-ttu-id="e2d7d-110">No menu **Editar** , aponte para **Avançado**e clique em **Pesquisa Incremental**.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-110">On the **Edit** menu, point to **Advanced**, and then click **Incremental Search**.</span></span>  
  
     <span data-ttu-id="e2d7d-111">O ícone de cursor muda para um binóculo com uma seta, indicando a direção de pesquisa e a barra de status exibe "Pesquisa Incremental".</span><span class="sxs-lookup"><span data-stu-id="e2d7d-111">The cursor icon changes to a binocular with an arrow, indicating the search direction, and the status bar displays "Incremental Search."</span></span>  
  
3.  <span data-ttu-id="e2d7d-112">Comece a digitar a cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-112">Begin typing the text string.</span></span>  
  
     <span data-ttu-id="e2d7d-113">A barra de status exibe o texto que você está digitando, enquanto o editor realça a primeira ocorrência que corresponde ao texto.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-113">The status bar displays the text you are entering while the editor highlights the first occurrence that matches the text.</span></span> <span data-ttu-id="e2d7d-114">Enquanto você continua a digitação, o editor se move para a próxima correspondência e a destaca.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-114">As you continue typing, the editor moves to the next match and highlights it.</span></span> <span data-ttu-id="e2d7d-115">Se não houver correspondências disponíveis, a barra de status exibirá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2d7d-115">If no matches are available, the status bar displays the following.</span></span>  
  
    ```  
    Incremental Search: <text> (not found)  
    ```  
  
 <span data-ttu-id="e2d7d-116">As pesquisas incrementais são executadas no local atual, para baixo e da esquerda para a direita no documento.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-116">Incremental searches are performed from the current location in the document downwards from left to right.</span></span> <span data-ttu-id="e2d7d-117">As pesquisas incrementais podem ser feitas usando teclas de atalho do teclado.</span><span class="sxs-lookup"><span data-stu-id="e2d7d-117">Incremental searches can be done using keyboard shortcut keys.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2d7d-118">Para obter uma lista completa de teclas de atalho do teclado, consulte [Atalhos de teclado do SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="e2d7d-118">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d7d-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2d7d-119">See Also</span></span>  
 <span data-ttu-id="e2d7d-120">[Pesquisar e substituir](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="e2d7d-120">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="e2d7d-121">[Pesquisar documentos interativamente](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="e2d7d-121">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="e2d7d-122">[Pesquisar documentos usando listas de resultados](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="e2d7d-122">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="e2d7d-123">[Pesquisar texto com curingas](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="e2d7d-123">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="e2d7d-124">Pesquisar texto com expressões regulares</span><span class="sxs-lookup"><span data-stu-id="e2d7d-124">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
