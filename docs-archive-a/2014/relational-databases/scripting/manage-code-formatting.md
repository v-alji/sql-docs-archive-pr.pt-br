---
title: Gerenciar formatação de código
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- indenting code [SQL Server]
- displaying URLs
- code formatting [SQL Server Management Studio]
- collapsing text
- formats [SQL Server], code formatting in SQL Server Management Studio
- hiding text
- formats [SQL Server]
- text [SQL Server], code formats
- automatic indentation
- converting text to lower case
- Query Editor [SQL Server Management Studio], managing code formats
- URL displayed in code [SQL Server Management Studio]
- converting text to upper case
- text [SQL Server]
- unindenting code
ms.assetid: ddbac4d2-6bdc-4467-a352-e869ec880eed
author: rothja
ms.author: jroth
ms.openlocfilehash: 873848c8aee575b47f7a3d8c31d8392cba5ed12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583470"
---
# <a name="manage-code-formatting"></a><span data-ttu-id="1433b-102">Gerenciar formatação de código</span><span class="sxs-lookup"><span data-stu-id="1433b-102">Manage Code Formatting</span></span>
  <span data-ttu-id="1433b-103">Com o Editor, você pode formatar seu código com recuo, texto oculto, URLs etc.</span><span class="sxs-lookup"><span data-stu-id="1433b-103">With the Editor you can format your code with indenting, hidden text, URLs, and so forth.</span></span> <span data-ttu-id="1433b-104">Você também pode formatar o código automaticamente usando o Recuo Inteligente.</span><span class="sxs-lookup"><span data-stu-id="1433b-104">You can also auto-format your code as you type by using Smart Indenting.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="1433b-105">Recuo</span><span class="sxs-lookup"><span data-stu-id="1433b-105">Indenting</span></span>  
 <span data-ttu-id="1433b-106">Você pode escolher três estilos diferentes de recuo de texto.</span><span class="sxs-lookup"><span data-stu-id="1433b-106">You can choose three different styles of text indenting.</span></span> <span data-ttu-id="1433b-107">Você também pode especificar quantos espaços compõem um único recuo ou tabulação e se o editor usa tabulações ou caracteres de espaço quando estabelece o recuo.</span><span class="sxs-lookup"><span data-stu-id="1433b-107">You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.</span></span>  
  
#### <a name="to-choose-an-indenting-style"></a><span data-ttu-id="1433b-108">Para escolher um estilo de recuo</span><span class="sxs-lookup"><span data-stu-id="1433b-108">To choose an indenting style</span></span>  
  
1.  <span data-ttu-id="1433b-109">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="1433b-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1433b-110">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="1433b-110">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1433b-111">Clique na pasta e selecione **Todos os Idiomas** para definir o recuo para todos os idiomas.</span><span class="sxs-lookup"><span data-stu-id="1433b-111">Click the folder, and select **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="1433b-112">Clique em **Tabulações**.</span><span class="sxs-lookup"><span data-stu-id="1433b-112">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="1433b-113">Clique em uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="1433b-113">Click one of the following options:</span></span>  
  
    -   <span data-ttu-id="1433b-114">**None**.</span><span class="sxs-lookup"><span data-stu-id="1433b-114">**None**.</span></span> <span data-ttu-id="1433b-115">O cursor vai para o começo da próxima linha.</span><span class="sxs-lookup"><span data-stu-id="1433b-115">The cursor goes to the beginning of the next line.</span></span>  
  
    -   <span data-ttu-id="1433b-116">**Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="1433b-116">**Block**.</span></span> <span data-ttu-id="1433b-117">O cursor alinha a próxima linha com a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="1433b-117">The cursor aligns the next line with the previous line.</span></span>  
  
    -   <span data-ttu-id="1433b-118">**Inteligente** (Padrão).</span><span class="sxs-lookup"><span data-stu-id="1433b-118">**Smart** (Default).</span></span> <span data-ttu-id="1433b-119">O serviço de idiomas determina o estilo do recuo adequado.</span><span class="sxs-lookup"><span data-stu-id="1433b-119">The language service determines the appropriate indenting style to use.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1433b-120">Alguns idiomas não oferecem as três opções de recuo.</span><span class="sxs-lookup"><span data-stu-id="1433b-120">Some languages do not offer all three indenting options.</span></span>  
  
#### <a name="to-change-indent-tab-settings"></a><span data-ttu-id="1433b-121">Para alterar configurações tabulação de recuo</span><span class="sxs-lookup"><span data-stu-id="1433b-121">To change indent tab settings</span></span>  
  
1.  <span data-ttu-id="1433b-122">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="1433b-122">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1433b-123">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="1433b-123">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1433b-124">Selecione a pasta de **Todos os Idiomas** para definir recuo para todos os idiomas.</span><span class="sxs-lookup"><span data-stu-id="1433b-124">Select the folder for **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="1433b-125">Clique em **Tabulações**.</span><span class="sxs-lookup"><span data-stu-id="1433b-125">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="1433b-126">Para especificar caracteres de tabulação para operações de recuo e tabulação, clique em **Manter tabulações**.</span><span class="sxs-lookup"><span data-stu-id="1433b-126">To specify tab characters for tab and indent operations, click **Keep tabs**.</span></span> <span data-ttu-id="1433b-127">Para especificar caracteres de espaço, selecione **Inserir espaços**.</span><span class="sxs-lookup"><span data-stu-id="1433b-127">To specify space characters, select **Insert spaces**.</span></span>  
  
     <span data-ttu-id="1433b-128">Se você selecionar **Inserir espaços**, digite o número de caracteres de espaço que cada tabulação ou recuo representa em **Tamanho da Tabulação** ou **Tamanho do Recuo**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1433b-128">If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.</span></span>  
  
#### <a name="to-indent-code"></a><span data-ttu-id="1433b-129">Para recuar código</span><span class="sxs-lookup"><span data-stu-id="1433b-129">To indent code</span></span>  
  
1.  <span data-ttu-id="1433b-130">Selecione o texto que você deseja recuar.</span><span class="sxs-lookup"><span data-stu-id="1433b-130">Select the text you want to indent.</span></span>  
  
2.  <span data-ttu-id="1433b-131">Pressione TAB ou clique no botão **Recuar** na barra de ferramentas Padrão.</span><span class="sxs-lookup"><span data-stu-id="1433b-131">Press TAB, or click the **Indent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-unindent-code"></a><span data-ttu-id="1433b-132">Para remover o recuo de código</span><span class="sxs-lookup"><span data-stu-id="1433b-132">To unindent code</span></span>  
  
1.  <span data-ttu-id="1433b-133">Selecione o texto em que você deseja remover o recuo.</span><span class="sxs-lookup"><span data-stu-id="1433b-133">Select the text you want to unindent.</span></span>  
  
2.  <span data-ttu-id="1433b-134">Pressione SHIFT+TAB ou clique no botão **Desfazer recuo** na barra de ferramentas Padrão.</span><span class="sxs-lookup"><span data-stu-id="1433b-134">Press SHIFT+TAB, or click the **Unindent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-automatically-indent-all-of-your-code"></a><span data-ttu-id="1433b-135">Para recuar todo o código automaticamente</span><span class="sxs-lookup"><span data-stu-id="1433b-135">To automatically indent all of your code</span></span>  
  
1.  <span data-ttu-id="1433b-136">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="1433b-136">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1433b-137">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="1433b-137">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1433b-138">Clique em **Todos os Idiomas**.</span><span class="sxs-lookup"><span data-stu-id="1433b-138">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="1433b-139">Clique em **Tabulações**.</span><span class="sxs-lookup"><span data-stu-id="1433b-139">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="1433b-140">Clique em **Inteligente**.</span><span class="sxs-lookup"><span data-stu-id="1433b-140">Click **Smart**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1433b-141">A opção **Inteligente** não está disponível para alguns idiomas.</span><span class="sxs-lookup"><span data-stu-id="1433b-141">The **Smart** option is not available for some languages.</span></span>  
  
#### <a name="to-convert-white-space-to-tabs"></a><span data-ttu-id="1433b-142">Para converter espaços vazios em tabulações</span><span class="sxs-lookup"><span data-stu-id="1433b-142">To convert white space to tabs</span></span>  
  
1.  <span data-ttu-id="1433b-143">Selecione o texto cujo espaço em branco que você deseja converter em tabulações.</span><span class="sxs-lookup"><span data-stu-id="1433b-143">Select the text whose white space you want to convert to tabs.</span></span>  
  
2.  <span data-ttu-id="1433b-144">No menu **Editar** , aponte para **Avançado**e clique em **Tabular Seleção**.</span><span class="sxs-lookup"><span data-stu-id="1433b-144">On the **Edit** menu, point to **Advanced**, and click **Tabify Selection**.</span></span>  
  
#### <a name="to-convert-tabs-to-spaces"></a><span data-ttu-id="1433b-145">Para converter tabulações em espaços</span><span class="sxs-lookup"><span data-stu-id="1433b-145">To convert tabs to spaces</span></span>  
  
1.  <span data-ttu-id="1433b-146">Selecione o texto cujas tabulações você deseja converter em espaços.</span><span class="sxs-lookup"><span data-stu-id="1433b-146">Select the text whose tabs you want to convert to spaces.</span></span>  
  
2.  <span data-ttu-id="1433b-147">No menu **Editar** , aponte para **Avançado**e clique em **Destabular Seleção**.</span><span class="sxs-lookup"><span data-stu-id="1433b-147">On the **Edit** menu, point to **Advanced**, and click **Untabify Selection**.</span></span>  
  
 <span data-ttu-id="1433b-148">O comportamento desses comandos depende das configurações de tabulação da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="1433b-148">The behavior of these commands depends on the tab settings in the **Options** dialog box.</span></span> <span data-ttu-id="1433b-149">Por exemplo, se a configuração de tabulação for 4, **Tabular Seleção** criará uma tabulação a cada 4 espaços contíguos e **Destabular Seleção** criará 4 espaços a cada tabulação.</span><span class="sxs-lookup"><span data-stu-id="1433b-149">For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.</span></span>  
  
## <a name="converting-text-to-upper-and-lower-case"></a><span data-ttu-id="1433b-150">Convertendo texto em maiúsculas ou minúsculas</span><span class="sxs-lookup"><span data-stu-id="1433b-150">Converting Text to Upper and Lower Case</span></span>  
 <span data-ttu-id="1433b-151">Você pode usar comandos para converter texto em maiúsculas ou minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1433b-151">You can use commands to convert text to all uppercase or lower case.</span></span>  
  
#### <a name="to-switch-text-to-upper-or-lower-case"></a><span data-ttu-id="1433b-152">Para alternar texto entre maiúsculas ou minúsculas</span><span class="sxs-lookup"><span data-stu-id="1433b-152">To switch text to upper or lower case</span></span>  
  
1.  <span data-ttu-id="1433b-153">Selecione o texto que você deseja converter.</span><span class="sxs-lookup"><span data-stu-id="1433b-153">Select the text you want to convert.</span></span>  
  
2.  <span data-ttu-id="1433b-154">Para converter texto para maiúsculas, pressione CTRL+SHIFT+U ou clique em **Colocar em Maiúsculas** no submenu **Avançado** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="1433b-154">To convert text to uppercase, press CTRL+SHIFT+U, or click **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
3.  <span data-ttu-id="1433b-155">Para converter texto para maiúsculas, pressione CTRL+SHIFT+L ou clique em **Colocar em Minúsculas** no submenu **Avançado** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="1433b-155">To convert text to lowercase, press CTRL+SHIFT+L, or click **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1433b-156">Para obter uma lista completa de teclas de atalho do teclado, consulte [Atalhos de teclado do SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="1433b-156">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="displaying-and-linking-to-urls"></a><span data-ttu-id="1433b-157">Exibindo e vinculando a URLs</span><span class="sxs-lookup"><span data-stu-id="1433b-157">Displaying and Linking to URLs</span></span>  
 <span data-ttu-id="1433b-158">Você pode criar e exibir URLs clicáveis em seu código.</span><span class="sxs-lookup"><span data-stu-id="1433b-158">You can create and display clickable URLs in your code.</span></span> <span data-ttu-id="1433b-159">Por padrão, as URLs:</span><span class="sxs-lookup"><span data-stu-id="1433b-159">By default, the URLs:</span></span>  
  
-   <span data-ttu-id="1433b-160">São sublinhadas.</span><span class="sxs-lookup"><span data-stu-id="1433b-160">Are underlined.</span></span>  
  
-   <span data-ttu-id="1433b-161">Mudam o ponteiro de mouse para uma mão quando você passa por cima delas.</span><span class="sxs-lookup"><span data-stu-id="1433b-161">Change the mouse pointer to a hand when you move over them.</span></span>  
  
-   <span data-ttu-id="1433b-162">Abrem a URL quando clicada, se a URL é válida.</span><span class="sxs-lookup"><span data-stu-id="1433b-162">Open the URL when clicked, if the URL is valid.</span></span>  
  
#### <a name="to-display-a-clickable-url"></a><span data-ttu-id="1433b-163">Para exibir uma URL clicável</span><span class="sxs-lookup"><span data-stu-id="1433b-163">To display a clickable URL</span></span>  
  
1.  <span data-ttu-id="1433b-164">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="1433b-164">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1433b-165">Clique em **Editor de Texto**.</span><span class="sxs-lookup"><span data-stu-id="1433b-165">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1433b-166">Para alterar a opção para apenas um idioma, clique nessa pasta do idioma e clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="1433b-166">To change the option for only one language, click that language folder and then click **General**.</span></span> <span data-ttu-id="1433b-167">Para alterar a opção para todos os idiomas, clique em **Todos os Idiomas** e clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="1433b-167">To change the option for all languages, click **All Languages** and then click **General**.</span></span>  
  
4.  <span data-ttu-id="1433b-168">Selecione **Habilitar navegação de URL com um só clique**.</span><span class="sxs-lookup"><span data-stu-id="1433b-168">Select **Enable single-click URL navigation**.</span></span>  
  
  
