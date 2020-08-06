---
title: Pesquisar documentos usando listas de resultados
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], result lists
- result list searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], multiple files
- Query Editor [SQL Server Management Studio], search multiple files
ms.assetid: 275e1b6c-fbd0-4408-af77-35903f90657c
author: rothja
ms.author: jroth
ms.openlocfilehash: 58ff3754bc1667de75426e52b3ddd855e7d1a348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582951"
---
# <a name="search-documents-using-results-lists"></a><span data-ttu-id="63e67-102">Pesquisar documentos usando listas de resultados</span><span class="sxs-lookup"><span data-stu-id="63e67-102">Search Documents Using Results Lists</span></span>
  <span data-ttu-id="63e67-103">Usando a caixa de diálogo **Localizar e Substituir** , você pode pesquisar e substituir texto em todos os arquivos de um projeto ou solução, ou em uma pasta do sistema de arquivos, mesmo quando eles não estiverem abertos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63e67-103">Using the **Find and Replace** dialog box, you can search and replace text in all files in a project or solution or in a file system folder, even when they are not open in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="63e67-104">Correspondências de pesquisas executadas com a caixa de diálogo **Localizar e Substituir** são exibidas nas janelas Localizar Resultados 1 e Localizar Resultados 2, que permitem a exibição do texto exato da linha que contém a correspondência.</span><span class="sxs-lookup"><span data-stu-id="63e67-104">Matches from searches that were performed with the **Find and Replace** dialog box appear in the Find Results 1 and Find Results 2 windows, which allows you to view the exact text from the line containing the match.</span></span>  
  
### <a name="to-search-in-multiple-files"></a><span data-ttu-id="63e67-105">Para executar pesquisas em vários arquivos</span><span class="sxs-lookup"><span data-stu-id="63e67-105">To search in multiple files</span></span>  
  
1.  <span data-ttu-id="63e67-106">No menu **Editar** , aponte para **Localizar e Substituir** e depois clique em **Localizar nos Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="63e67-106">On the **Edit** menu, point to **Find and Replace,** and then click **Find in Files**.</span></span>  
  
2.  <span data-ttu-id="63e67-107">Na caixa de texto **Localizar** , digite o texto da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63e67-107">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="63e67-108">Na lista **Examinar** , clique em **Todos os Documentos Abertos**, **Projeto Atual**, **Solução Inteira**ou digite um caminho de diretório.</span><span class="sxs-lookup"><span data-stu-id="63e67-108">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
4.  <span data-ttu-id="63e67-109">Na lista **Tipos de arquivo** , selecione um dos conjuntos relacionados de extensões de arquivo ou digite as extensões dos tipos de arquivo a serem pesquisados, separados por ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="63e67-109">In the **File types** list, select one of the listed sets of file extensions or enter the extensions for the types of files to be searched, separated by semicolons.</span></span> <span data-ttu-id="63e67-110">Use \*.\* para pesquisar todos os arquivos no diretório relacionados na lista suspensa **Examinar** .</span><span class="sxs-lookup"><span data-stu-id="63e67-110">Use \*.\* to search all files in the directory listed in the **Look in** drop-down list.</span></span>  
  
5.  <span data-ttu-id="63e67-111">Selecione uma opção dentre as opções restantes para melhorar a precisão da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63e67-111">Select from the remaining search options to improve the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="63e67-112">Clique em **Localizar** para começar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63e67-112">Click **Find** to begin the search.</span></span>  
  
 <span data-ttu-id="63e67-113">As correspondências da pesquisa são exibidas na janela Localizar Resultados 1 por padrão.</span><span class="sxs-lookup"><span data-stu-id="63e67-113">The matches for the search appear in the Find Results 1 window by default.</span></span> <span data-ttu-id="63e67-114">Você pode navegar pelos resultados da pesquisa clicando duas vezes em cada entrada na janela Localizar Resultados 1.</span><span class="sxs-lookup"><span data-stu-id="63e67-114">You can browse the search matches by double-clicking each entry in the Find Results 1 window.</span></span> <span data-ttu-id="63e67-115">Para exibir os resultados da pesquisa em uma janela nova, selecione **Exibir em Localizar 2.**</span><span class="sxs-lookup"><span data-stu-id="63e67-115">To view the search results in a new window, select **Display in Find 2**.</span></span>  
  
#### <a name="to-replace-across-multiple-files-or-folders"></a><span data-ttu-id="63e67-116">Para efetuar uma substituição em vários arquivos ou pastas</span><span class="sxs-lookup"><span data-stu-id="63e67-116">To replace across multiple files or folders</span></span>  
  
1.  <span data-ttu-id="63e67-117">No menu **Editar** , aponte para **Localizar e Substituir** e depois clique em **Substituir nos Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="63e67-117">On the **Edit** menu, point to **Find and Replace,** and then click **Replace in Files**.</span></span>  
  
2.  <span data-ttu-id="63e67-118">Na caixa de texto **Localizar** , digite o texto da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63e67-118">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="63e67-119">Na caixa **Substituir por** , digite o texto para substituir o texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63e67-119">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="63e67-120">Na lista **Examinar** , clique em **Todos os Documentos Abertos**, **Projeto Atual**, **Solução Inteira**ou digite um caminho de diretório.</span><span class="sxs-lookup"><span data-stu-id="63e67-120">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
5.  <span data-ttu-id="63e67-121">Clique em **Substituir** para substituir a correspondência da pesquisa atual pelo texto da caixa **Substituir por** .</span><span class="sxs-lookup"><span data-stu-id="63e67-121">Click **Replace** to replace the current search match with the text in the **Replace with** box.</span></span> <span data-ttu-id="63e67-122">Você pode passar para a próxima correspondência clicando em **Localizar Próximo** ou passar para o próximo arquivo clicando em **Ignorar Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="63e67-122">You can skip a single match by clicking **Find Next** or skip an entire file clicking **Skip File**.</span></span>  
  
     <span data-ttu-id="63e67-123">\- ou –</span><span class="sxs-lookup"><span data-stu-id="63e67-123">\- or -</span></span>  
  
     <span data-ttu-id="63e67-124">Selecione **Substituir tudo** para substituir todas as correspondências pelo texto da caixa **Substituir por** .</span><span class="sxs-lookup"><span data-stu-id="63e67-124">Choose **Replace all** to replace all search matches with the text in the **Replace with** box.</span></span> <span data-ttu-id="63e67-125">Selecione **Manter arquivos modificados abertos após Substituir Tudo** se você quiser desfazer algumas das substituições em outro momento.</span><span class="sxs-lookup"><span data-stu-id="63e67-125">Select **Keep modified files open after Replace All** if you want to undo some of the replacements at another time.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63e67-126">**Substituir tudo** substitui todas as correspondências da pesquisa, inclusive aquelas nos arquivos ignorados com **Ignorar Arquivo** ou **Localizar Próximo**.</span><span class="sxs-lookup"><span data-stu-id="63e67-126">**Replace all** replaces all search matches, including those in files you have skipped with **Skip File** or **Find Next**.</span></span> <span data-ttu-id="63e67-127">Você só pode usar **Desfazer** para substituições feitas em arquivos que tenham permanecido abertos depois da operação de substituição.</span><span class="sxs-lookup"><span data-stu-id="63e67-127">You can only use **Undo** for replacements made in files that remain open after the replacement operation.</span></span>  
  
 <span data-ttu-id="63e67-128">As informações de substituição são exibidas na janela Localizar Resultados 1 por padrão.</span><span class="sxs-lookup"><span data-stu-id="63e67-128">Replacement information appears in the Find Results 1 window by default.</span></span> <span data-ttu-id="63e67-129">Você pode navegar pelas substituições clicando duas vezes em cada entrada na janela Localizar Resultados 1.</span><span class="sxs-lookup"><span data-stu-id="63e67-129">You can browse replacements by double-clicking each entry in the Find Results 1 window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e67-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63e67-130">See Also</span></span>  
 <span data-ttu-id="63e67-131">[Pesquisar e substituir](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="63e67-131">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="63e67-132">[Pesquisar documentos interativamente](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="63e67-132">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="63e67-133">[Pesquisar texto com curingas](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="63e67-133">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="63e67-134">Pesquisar texto com expressões regulares</span><span class="sxs-lookup"><span data-stu-id="63e67-134">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
