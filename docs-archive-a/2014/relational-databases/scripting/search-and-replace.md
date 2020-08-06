---
title: Pesquisar e substituir
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: rothja
ms.author: jroth
ms.openlocfilehash: 55422fa7201213477426c7bc25c45ff05acf8945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570595"
---
# <a name="search-and-replace"></a><span data-ttu-id="31b97-102">Pesquisar e substituir</span><span class="sxs-lookup"><span data-stu-id="31b97-102">Search and Replace</span></span>
  <span data-ttu-id="31b97-103">Há vários modos diferentes de localizar e substituir texto.</span><span class="sxs-lookup"><span data-stu-id="31b97-103">There are several different ways to find and replace text.</span></span> <span data-ttu-id="31b97-104">No menu **Editar** , **Localizar e Substituir** oferece quatro opções: **Localização Rápida**, **Substituição Rápida**, **Localizar nos Arquivos**ou **Substituir nos Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="31b97-104">On the **Edit** menu, **Find and Replace** offers four choices: **Quick Find**, **Quick Replace**, **Find in Files**, or **Replace in Files**.</span></span> <span data-ttu-id="31b97-105">Cada uma dessas opções abre versões da caixa de diálogo **Localizar e Substituir** .</span><span class="sxs-lookup"><span data-stu-id="31b97-105">Each of these opens versions of the **Find and Replace** dialog box.</span></span> <span data-ttu-id="31b97-106">Você também pode pesquisar sem uma caixa de diálogo usando teclas de atalho de teclado de pesquisa incremental.</span><span class="sxs-lookup"><span data-stu-id="31b97-106">You can also search without a dialog box by using incremental search keyboard shortcut keys.</span></span> <span data-ttu-id="31b97-107">Essas técnicas permitem que você controle o escopo de localização e substituição, e escolha o método de revisão de correspondências e substituições.</span><span class="sxs-lookup"><span data-stu-id="31b97-107">These techniques allow you to control the scope of find and replace, and choose the method of reviewing search matches and replacements.</span></span>  
  
 <span data-ttu-id="31b97-108">Você deve considerar os itens a seguir ao localizar e substituir texto:</span><span class="sxs-lookup"><span data-stu-id="31b97-108">You should consider the following when you search and replace text:</span></span>  
  
-   <span data-ttu-id="31b97-109">As opções definidas na caixa de diálogo **Localizar e Substituir** afetam todas as pesquisas.</span><span class="sxs-lookup"><span data-stu-id="31b97-109">Options set in the **Find and Replace** dialog box affect all the searches.</span></span> <span data-ttu-id="31b97-110">Essas opções incluem **Corresponder Maiúsculas e Minúsculas**, **Coincidir palavra inteira**, **Pesquisar para cima**, **Pesquisar texto oculto**, **Curingas**, **Expressões Regulares**, **Procurar em Todos os Documentos Abertos**e **Procurar no Projeto Atual**.</span><span class="sxs-lookup"><span data-stu-id="31b97-110">These options include **Match case**, **Match whole word**, **Search up**, **Search hidden text**, **Wildcards**, **Regular Expressions**, **Look in All Open Documents**, and **Look in Current Project**.</span></span> <span data-ttu-id="31b97-111">Nem todas as opções estão disponíveis em todas as versões da caixa de diálogo **Localizar e Substituir** .</span><span class="sxs-lookup"><span data-stu-id="31b97-111">All options are not available in all versions of the **Find and Replace** dialog box.</span></span>  
  
-   <span data-ttu-id="31b97-112">**Desfazer** só está disponível para documentos deixados abertos após uma operação de substituição.</span><span class="sxs-lookup"><span data-stu-id="31b97-112">**Undo** is available only for documents left open after a replace operation.</span></span>  
  
-   <span data-ttu-id="31b97-113">**Desfazer** para uma operação **Substituir Tudo** que englobe mais de um arquivo é considerada uma ação única em massa em todos os arquivos afetados.</span><span class="sxs-lookup"><span data-stu-id="31b97-113">**Undo** for a **Replace All** operation that spans more than one file is considered a single, bulk action across all the affected files.</span></span> <span data-ttu-id="31b97-114">Isto é, você não pode desfazer a alteração em alguns arquivos e mantê-la em outros.</span><span class="sxs-lookup"><span data-stu-id="31b97-114">That is, you cannot undo the change in some files while retaining the change in other files.</span></span>  
  
 <span data-ttu-id="31b97-115">Em geral, não é possível pesquisar itens com exibições gráficas.</span><span class="sxs-lookup"><span data-stu-id="31b97-115">Generally, you cannot search items with graphical views.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b97-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31b97-116">See Also</span></span>  
 <span data-ttu-id="31b97-117">[Pesquisar um documento ativo de forma incremental](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="31b97-117">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="31b97-118">[Pesquisar documentos interativamente](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="31b97-118">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="31b97-119">[Pesquisar documentos usando listas de resultados](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="31b97-119">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="31b97-120">[Pesquisar texto com curingas](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="31b97-120">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="31b97-121">Pesquisar texto com expressões regulares</span><span class="sxs-lookup"><span data-stu-id="31b97-121">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
