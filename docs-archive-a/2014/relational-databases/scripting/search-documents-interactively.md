---
title: Pesquisar documentos interativamente
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- interactive searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], interactive
- Query Editor [SQL Server Management Studio], interactive search
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
author: rothja
ms.author: jroth
ms.openlocfilehash: 5603db77ea4f58d4bb036635a23ec3cfa400a818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582956"
---
# <a name="search-documents-interactively"></a><span data-ttu-id="46714-102">Pesquisar documentos interativamente</span><span class="sxs-lookup"><span data-stu-id="46714-102">Search Documents Interactively</span></span>
  <span data-ttu-id="46714-103">Usando a caixa de diálogo **Localizar e Substituir** , você pode pesquisar um ou mais arquivos ou janelas abertas, e navegar pelos resultados da pesquisa um a um.</span><span class="sxs-lookup"><span data-stu-id="46714-103">Using the **Find and Replace** dialog box, you can search one or more open files or windows and move through the search matches one by one.</span></span> <span data-ttu-id="46714-104">Essa técnica permite a revisão de cada correspondência individual da pesquisa no contexto do texto da correspondência.</span><span class="sxs-lookup"><span data-stu-id="46714-104">This technique allows you to review each individual search match in the context of the text around the match.</span></span> <span data-ttu-id="46714-105">Você também tem a opção de executar operações de localização em massa e revisar correspondências da pesquisa no formato de relatório usando a caixa de diálogo **Localizar e Substituir** .</span><span class="sxs-lookup"><span data-stu-id="46714-105">You also have the option of performing bulk find operations and reviewing search matches in report format using the **Find and Replace** dialog box.</span></span>  
  
### <a name="to-search-all-open-documents"></a><span data-ttu-id="46714-106">Para pesquisar todos os documentos abertos</span><span class="sxs-lookup"><span data-stu-id="46714-106">To search all open documents</span></span>  
  
1.  <span data-ttu-id="46714-107">Abra os itens que você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="46714-107">Open the items you wish to search.</span></span>  
  
2.  <span data-ttu-id="46714-108">No menu **Editar** , aponte para **Localizar e Substituir** e depois clique em **QuickFind**.</span><span class="sxs-lookup"><span data-stu-id="46714-108">On the **Edit** menu, point to **Find and Replace,** and then click **QuickFind**.</span></span>  
  
3.  <span data-ttu-id="46714-109">Na caixa de texto **Localizar e Substituir** , digite o texto da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46714-109">In the **Find and Replace** text box, enter the text to search for.</span></span>  
  
4.  <span data-ttu-id="46714-110">Na lista **Examinar** , selecione **Todos os Documentos Abertos**.</span><span class="sxs-lookup"><span data-stu-id="46714-110">In the **Look in** list, select **All Open Documents**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="46714-111">Alguns arquivos abertos talvez não sejam pesquisados quando a opção **Todos os Documentos Abertos** for selecionada.</span><span class="sxs-lookup"><span data-stu-id="46714-111">Certain open files might not be searched when **All Open Documents** is selected.</span></span> <span data-ttu-id="46714-112">Somente os arquivos abertos atualmente em uma exibição textual, como exibição de Código, são incluídos nas pesquisas.</span><span class="sxs-lookup"><span data-stu-id="46714-112">Only files currently open in a textual view, such as Code view, are included in searches.</span></span> <span data-ttu-id="46714-113">Os arquivos na exibição de designer não são incluídos nas pesquisas.</span><span class="sxs-lookup"><span data-stu-id="46714-113">Files in Designer view are not included in searches.</span></span>  
  
5.  <span data-ttu-id="46714-114">Selecione opções adicionais de pesquisa para melhorar a precisão da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46714-114">Select additional search options to increase the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="46714-115">Clique em **Localizar Próximo** para iniciar a pesquisa e continue clicando em **Localizar Próximo** até o último arquivo ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="46714-115">Click **Find Next** to start the search, and continue clicking **Find Next** until the last file has been searched.</span></span>  
  
 <span data-ttu-id="46714-116">Quando a pesquisa passar do começo ou fim do documento, uma mensagem será exibida na barra de status.</span><span class="sxs-lookup"><span data-stu-id="46714-116">When the search passes the beginning or end of the document, a message is displayed in the status bar.</span></span> <span data-ttu-id="46714-117">Uma caixa de mensagem será exibida quando a pesquisa alcançar o ponto de partida da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46714-117">A message box appears when the search reaches the starting point of the search.</span></span>  
  
#### <a name="to-replace-in-all-active-files-interactively"></a><span data-ttu-id="46714-118">Para substituir todos os arquivos ativos interativamente</span><span class="sxs-lookup"><span data-stu-id="46714-118">To replace in all active files interactively</span></span>  
  
1.  <span data-ttu-id="46714-119">No menu **Editar** , aponte para **Localizar e Substituir**e clique em **QuickReplace**.</span><span class="sxs-lookup"><span data-stu-id="46714-119">On the **Edit** menu, point to **Find and Replace**, and then click **QuickReplace**.</span></span>  
  
2.  <span data-ttu-id="46714-120">Na caixa **Localizar** , digite o texto da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46714-120">In the **Find what** box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="46714-121">Na caixa **Substituir por** , digite o texto para substituir o texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46714-121">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="46714-122">Na lista **Examinar** , selecione **Todos os Documentos Abertos**.</span><span class="sxs-lookup"><span data-stu-id="46714-122">In the **Look in** list, select **All Open Documents**.</span></span>  
  
5.  <span data-ttu-id="46714-123">Clique em **Substituir**e continue clicando em **Substituir** até a última correspondência no último arquivo ser substituída.</span><span class="sxs-lookup"><span data-stu-id="46714-123">Click **Replace**, and continue clicking **Replace** until the last match in the last file has been replaced.</span></span> <span data-ttu-id="46714-124">Clique em **Localizar Próximo** para ignorar uma correspondência que você não deseja substituir.</span><span class="sxs-lookup"><span data-stu-id="46714-124">Click **Find Next** to skip a match you do not want to replace.</span></span>  
  
     <span data-ttu-id="46714-125">-ou-</span><span class="sxs-lookup"><span data-stu-id="46714-125">-or-</span></span>  
  
     <span data-ttu-id="46714-126">Escolha **Substituir Tudo** para substituir todas as correspondências.</span><span class="sxs-lookup"><span data-stu-id="46714-126">Choose **Replace All** to replace all matches.</span></span> <span data-ttu-id="46714-127">Uma caixa de mensagem é exibida, relacionando o número total de substituições.</span><span class="sxs-lookup"><span data-stu-id="46714-127">A message box appears, listing the total number of replacements.</span></span>  
  
 <span data-ttu-id="46714-128">O comando **Substituir Tudo** substitui todas as correspondências da pesquisa, inclusive aquelas ignoradas com o botão **Localizar Próximo** .</span><span class="sxs-lookup"><span data-stu-id="46714-128">The **Replace All** command replaces all search matches, including those you have skipped with the **Find Next** button.</span></span> <span data-ttu-id="46714-129">Para cancelar **Substituir Tudo**, clique em **Desfazer** no menu **Editar** antes de fechar qualquer arquivo.</span><span class="sxs-lookup"><span data-stu-id="46714-129">To cancel **Replace All**, click **Undo** from the **Edit** menu before closing any of the files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46714-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46714-130">See Also</span></span>  
 <span data-ttu-id="46714-131">[Pesquisar um documento ativo de forma incremental](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="46714-131">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="46714-132">[Pesquisar e substituir](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="46714-132">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="46714-133">[Pesquisar documentos usando listas de resultados](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="46714-133">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="46714-134">[Pesquisar texto com curingas](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="46714-134">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="46714-135">Pesquisar texto com expressões regulares</span><span class="sxs-lookup"><span data-stu-id="46714-135">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
