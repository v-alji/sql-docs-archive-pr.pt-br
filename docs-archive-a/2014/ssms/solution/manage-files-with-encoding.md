---
title: Gerenciar arquivos com codificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- files [SQL Server Management Studio]
- encoding [SQL Server Management Studio]
- files [SQL Server Management Studio], encoding
ms.assetid: 919544c9-59f0-4cc6-bb2a-f1ad671eb74b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9b0aaa123001fed3f6ad42ea9d642e4007e2640f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583941"
---
# <a name="manage-files-with-encoding"></a><span data-ttu-id="451d1-102">Gerenciar arquivos com codificação</span><span class="sxs-lookup"><span data-stu-id="451d1-102">Manage Files with Encoding</span></span>
  <span data-ttu-id="451d1-103">Para facilitar a exibição de seu código em uma determinada linguagem ou plataforma, você pode associar uma codificação de caracteres em particular a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="451d1-103">To facilitate the display of your code in a particular language and on a particular platform, you can associate a particular character encoding with a file.</span></span>  
  
## <a name="opening-files"></a><span data-ttu-id="451d1-104">Abrindo arquivos</span><span class="sxs-lookup"><span data-stu-id="451d1-104">Opening Files</span></span>  
 <span data-ttu-id="451d1-105">Você pode escolher o editor que deseja usar para editar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="451d1-105">You can choose the editor you want to use to edit the file.</span></span>  
  
#### <a name="to-open-a-file-with-a-specific-editor"></a><span data-ttu-id="451d1-106">Para abrir um arquivo com um editor específico</span><span class="sxs-lookup"><span data-stu-id="451d1-106">To open a file with a specific editor</span></span>  
  
1.  <span data-ttu-id="451d1-107">No menu **Arquivo** , aponte para **Abrir**e clique em **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="451d1-107">On the **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="451d1-108">Na caixa de diálogo **Abrir arquivo** , selecione o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="451d1-108">In the **Open File** dialog box, select the file name.</span></span>  
  
3.  <span data-ttu-id="451d1-109">Clique na seta próxima ao botão **Abrir** e clique em**Abrir com** no menu exibido.</span><span class="sxs-lookup"><span data-stu-id="451d1-109">Click the arrow next to the **Open** button, and then click**Open With** from the menu that appears.</span></span>  
  
4.  <span data-ttu-id="451d1-110">Na lista **Selecione um programa para abrir** , selecione um editor e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="451d1-110">In the **Select a program to open** list, select an editor, and then click **Open**.</span></span> <span data-ttu-id="451d1-111">Para abrir o arquivo com uma codificação em particular, selecione um editor com suporte a codificação, como o SQL Query Editor With Encoding ou o XML Editor With Encoding.</span><span class="sxs-lookup"><span data-stu-id="451d1-111">To open the file with a particular encoding, select an editor with encoding support, such as SQL Query Editor with Encoding or XML Editor with Encoding.</span></span>  
  
## <a name="saving-files"></a><span data-ttu-id="451d1-112">Salvando arquivos</span><span class="sxs-lookup"><span data-stu-id="451d1-112">Saving Files</span></span>  
 <span data-ttu-id="451d1-113">Você também pode salvar seu código com uma codificação Unicode em uma página de código diferente para dar suporte a vários idiomas, como Europeu Ocidental ou Europeu Oriental.</span><span class="sxs-lookup"><span data-stu-id="451d1-113">You can also save your code with a Unicode encoding or a different code page to support various languages, such as Western European or Eastern European.</span></span> <span data-ttu-id="451d1-114">É possível associar uma codificação de caracteres em particular a um arquivo para facilitar a exibição do código naquela linguagem, além de um tipo de fim de linha que dê suporte a um determinado sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="451d1-114">You can associate a particular character encoding with a file to facilitate the display of your code in that language, as well as a line-ending type to support a particular operating system.</span></span> <span data-ttu-id="451d1-115">Além disso, alguns caracteres, quando usados em nomes de arquivo, não podem ser salvos a menos que sejam salvos com codificação Unicode.</span><span class="sxs-lookup"><span data-stu-id="451d1-115">Also, some characters, when used in file names, cannot be saved unless they are saved with Unicode encoding.</span></span>  
  
#### <a name="to-save-a-file-with-a-different-encoding-or-line-ending-type"></a><span data-ttu-id="451d1-116">Para salvar um arquivo com codificação ou tipo de fim de linha diferente</span><span class="sxs-lookup"><span data-stu-id="451d1-116">To save a file with a different encoding or line ending type</span></span>  
  
1.  <span data-ttu-id="451d1-117">No menu **Arquivo** , clique em **Salvar \<filename> como**.</span><span class="sxs-lookup"><span data-stu-id="451d1-117">On the **File** menu, click **Save \<filename> As**.</span></span>  
  
2.  <span data-ttu-id="451d1-118">Na caixa de diálogo **Salvar Arquivo Como** , expanda o botão **Salvar** e clique em **Salvar com Codificação**.</span><span class="sxs-lookup"><span data-stu-id="451d1-118">In the **Save File As** dialog, expand the **Save** button, and then click **Save with Encoding**.</span></span>  
  
3.  <span data-ttu-id="451d1-119">Na caixa de diálogo **Opções Avançadas de Gravação** , selecione a codificação desejada na lista **Codificação** .</span><span class="sxs-lookup"><span data-stu-id="451d1-119">In the **Advanced Save Options** dialog box, select the encoding you want from the **Encoding** list.</span></span>  
  
4.  <span data-ttu-id="451d1-120">Na lista **Finais de Linha**, selecione o tipo de final de linha desejado.</span><span class="sxs-lookup"><span data-stu-id="451d1-120">From the **Line Endings**list, select the type of line ending you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="451d1-121">Se você salvar seu arquivo com codificação Unicode, o arquivo deverá ter feito check-in no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe como um arquivo binário porque o Visual SourceSafe não dá suporte à mesclagem, comparação e exibição de diferenças entre arquivos salvos como Unicode.</span><span class="sxs-lookup"><span data-stu-id="451d1-121">If you save your file your file with Unicode encoding, the file should be checked into [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe as a binary file because Visual SourceSafe does not support merging, comparing, and showing differences between files that are saved as Unicode.</span></span>  
  
 <span data-ttu-id="451d1-122">Se você estiver usando o Visual SourceSafe para armazenar arquivos com ANSI, UTF8 ou Unicode, observe as seguintes limitações para cada uma das opções:</span><span class="sxs-lookup"><span data-stu-id="451d1-122">If you are using Visual SourceSafe to store files with ANSI, UTF8, or Unicode, be aware of the following limitations for each:</span></span>  
  
-   <span data-ttu-id="451d1-123">Arquivos ANSI só permitem caracteres suportados pela página de código atual, o que limita o uso internacional.</span><span class="sxs-lookup"><span data-stu-id="451d1-123">ANSI files allow only characters that are supported in the current code page, which limits international use.</span></span>  
  
-   <span data-ttu-id="451d1-124">Arquivos Unicode não podem usar check-out compartilhado, verificação de diferenças ou funcionalidade de mesclagem porque são tratados como arquivos binários.</span><span class="sxs-lookup"><span data-stu-id="451d1-124">Unicode files cannot use shared checkout, difference checking, or merging functionality because they are handled as binary files.</span></span> <span data-ttu-id="451d1-125">Você pode usar esse formato em arquivos internacionais.</span><span class="sxs-lookup"><span data-stu-id="451d1-125">You can use this format in international files.</span></span>  
  
-   <span data-ttu-id="451d1-126">Arquivos UTF8 não funcionam bem com o Visual SourceSafe porque as alterações que criam problemas para editores UTF8 são feitas durante o check-in, o check-out, a verificação de diferenças e a mesclagem.</span><span class="sxs-lookup"><span data-stu-id="451d1-126">UTF8 files do not work safely with Visual SourceSafe because changes that cause problems for UTF8 file editors are made during check in, check out, difference checking, and merging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451d1-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="451d1-127">See Also</span></span>  
 <span data-ttu-id="451d1-128">[Arquivos que gerenciam soluções e projetos](files-that-manage-solutions-and-projects.md) </span><span class="sxs-lookup"><span data-stu-id="451d1-128">[Files That Manage Solutions and Projects](files-that-manage-solutions-and-projects.md) </span></span>  
 [<span data-ttu-id="451d1-129">Associar extensões de arquivo a um Editor de Códigos</span><span class="sxs-lookup"><span data-stu-id="451d1-129">Associate File Extensions to a Code Editor</span></span>](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md)  
  
  
