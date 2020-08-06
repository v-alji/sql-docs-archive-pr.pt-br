---
title: Opções (página Editor de texto – todos os idiomas – guias) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: bd715d6b-f873-41d4-aa10-57b7098b61cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 13f791e34b2099e8c0492c25886ee6b37ef1a1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582118"
---
# <a name="options-text-editor---all-languages--tabs-page"></a><span data-ttu-id="54308-102">Opções (página Editor de Texto – Todos os idiomas – Guias)</span><span class="sxs-lookup"><span data-stu-id="54308-102">Options (Text Editor - All Languages -Tabs Page)</span></span>
  <span data-ttu-id="54308-103">Use esta caixa de diálogo para definir o comportamento de tabulação nos cinco editores no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54308-103">Use this dialog box to set the tabbing behavior in all five of the editors in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="54308-104">Para exibir essas opções, clique em **Opções** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="54308-104">To display these options, click **Options** on the **Tools** menu.</span></span> <span data-ttu-id="54308-105">Selecione a pasta **Editor de Texto** , expanda a pasta **Todos os Idiomas** e clique em **Tabulações**.</span><span class="sxs-lookup"><span data-stu-id="54308-105">Select the **Text Editor** folder, expand the **All Languages** folder and then click **Tabs**.</span></span>  
  
## <a name="tabbing-options-by-editor"></a><span data-ttu-id="54308-106">Opções de tabulação pelo editor</span><span class="sxs-lookup"><span data-stu-id="54308-106">Tabbing Options by Editor</span></span>  
 <span data-ttu-id="54308-107">Use a caixa de diálogo **Todos os Idiomas** para definir opções para os editores DMX, MDX e SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="54308-107">You must use the **All Languages** dialogs to set options for the DMX, MDX, and SQL Server Compact editors.</span></span> <span data-ttu-id="54308-108">As opções definidas aqui também são aplicadas aos editores de Texto sem formatação, de Transact-SQL e de XML, mas você pode definir opções separadamente para esses editores, expandindo as subpastas para esses idiomas e selecionando as respectivas páginas de opção.</span><span class="sxs-lookup"><span data-stu-id="54308-108">Options set here are also applied to the Plain Text, Transact-SQL, and XML editors, but you can set options separately for those editors by expanding the subfolders for those languages and selecting their option pages.</span></span> <span data-ttu-id="54308-109">Alguns idiomas não dão suporte a todas as opções de tabulação.</span><span class="sxs-lookup"><span data-stu-id="54308-109">Some languages do not support all of the tabbing options.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="54308-110">Se você definir uma opção que use essa caixa de diálogo, mas desejar uma configuração diferente para o editor de Texto sem Formatação, de Transact-SQL ou de XML, defina as opções para esses editores depois de aplicar suas seleções na caixa de diálogo **Todos os Idiomas**.</span><span class="sxs-lookup"><span data-stu-id="54308-110">If you set an option using this dialog, but want a different setting for the Plain Text, Transact-SQL, or XML editors, you must set the options for those editors after applying your selections in the **All Languages** dialog.</span></span>  
  
 <span data-ttu-id="54308-111">A mensagem "As configurações de recuo (ou guia) para formatos de texto individuais estão em conflito entre si" é exibida quando configurações diferentes são selecionadas para editores específicos.</span><span class="sxs-lookup"><span data-stu-id="54308-111">The message "The indentation (or tab) settings for individual text formats conflict with each other" is displayed when different settings have been selected for particular editors.</span></span> <span data-ttu-id="54308-112">Por exemplo, esse lembrete é exibido se a opção **Recuo do bloco** estiver selecionada para **Texto Sem-Formatação**, mas **Nenhum** estiver selecionada para **XML**.</span><span class="sxs-lookup"><span data-stu-id="54308-112">For example, this reminder is displayed if the **Block indenting** option is selected for **Plain Text**, but **None** is selected for **XML**.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="54308-113">Recuo</span><span class="sxs-lookup"><span data-stu-id="54308-113">Indenting</span></span>  
 <span data-ttu-id="54308-114">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="54308-114">**None**</span></span>  
 <span data-ttu-id="54308-115">Quando essa opção estiver selecionada, a nova linha criada ao se pressionar ENTER não ficará recuada.</span><span class="sxs-lookup"><span data-stu-id="54308-115">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="54308-116">O cursor é colocado na primeira coluna da nova linha.</span><span class="sxs-lookup"><span data-stu-id="54308-116">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="54308-117">**Bloquear**</span><span class="sxs-lookup"><span data-stu-id="54308-117">**Block**</span></span>  
 <span data-ttu-id="54308-118">Quando essa opção é selecionada, a nova linha criada ao se pressionar ENTER é recuada automaticamente com a mesma distância em que a linha anterior foi recuada.</span><span class="sxs-lookup"><span data-stu-id="54308-118">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line was indented.</span></span>  
  
 <span data-ttu-id="54308-119">**Inteligente**</span><span class="sxs-lookup"><span data-stu-id="54308-119">**Smart**</span></span>  
 <span data-ttu-id="54308-120">Quando essa opção é selecionada, a nova linha criada ao se pressionar ENTER é posicionada de acordo com o contexto.</span><span class="sxs-lookup"><span data-stu-id="54308-120">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="54308-121">Guias</span><span class="sxs-lookup"><span data-stu-id="54308-121">Tabs</span></span>  
 <span data-ttu-id="54308-122">**Tamanho da tabulação**</span><span class="sxs-lookup"><span data-stu-id="54308-122">**Tab size**</span></span>  
 <span data-ttu-id="54308-123">Define a distância em espaços entre paradas de tabulação.</span><span class="sxs-lookup"><span data-stu-id="54308-123">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="54308-124">O padrão é quatro espaços.</span><span class="sxs-lookup"><span data-stu-id="54308-124">The default is four spaces.</span></span>  
  
 <span data-ttu-id="54308-125">**Tamanho do recuo**</span><span class="sxs-lookup"><span data-stu-id="54308-125">**Indent size**</span></span>  
 <span data-ttu-id="54308-126">Define o tamanho em espaços de um recuo automático.</span><span class="sxs-lookup"><span data-stu-id="54308-126">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="54308-127">O padrão é quatro espaços.</span><span class="sxs-lookup"><span data-stu-id="54308-127">The default is four spaces.</span></span> <span data-ttu-id="54308-128">Caracteres de tabulação, caracteres de espaço ou ambos serão inseridos para preencher o tamanho especificado.</span><span class="sxs-lookup"><span data-stu-id="54308-128">Tab characters, space characters, or both will be inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="54308-129">**Inserir espaços**</span><span class="sxs-lookup"><span data-stu-id="54308-129">**Insert spaces**</span></span>  
 <span data-ttu-id="54308-130">Quando essa opção é selecionada, as operações de recuo inserem apenas caracteres de espaço, não caracteres de tabulação.</span><span class="sxs-lookup"><span data-stu-id="54308-130">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="54308-131">Se o **Tamanho do recuo** for definido para 5, por exemplo, então cinco caracteres de espaço são inseridos sempre que se pressionar a tecla TAB ou se clicar no botão **Aumentar Recuo** na barra de ferramentas da janela principal do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54308-131">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] main window.</span></span>  
  
 <span data-ttu-id="54308-132">**Manter tabulações**</span><span class="sxs-lookup"><span data-stu-id="54308-132">**Keep tabs**</span></span>  
 <span data-ttu-id="54308-133">Quando essa opção é selecionada, as operações de recuo inserem tantos caracteres de tabulação quantos forem possíveis.</span><span class="sxs-lookup"><span data-stu-id="54308-133">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="54308-134">Cada caractere de tabulação preenche o número de espaços especificado em **Tamanho da tabulação**.</span><span class="sxs-lookup"><span data-stu-id="54308-134">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="54308-135">Se o **Tamanho do recuo** não for um múltiplo par do **Tamanho da tabulação**, caracteres de espaço serão adicionados para preencher a diferença.</span><span class="sxs-lookup"><span data-stu-id="54308-135">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
