---
title: Opções (ambiente – página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.SQLEnvironmentOptions
ms.assetid: c32ccdb8-2cf8-4c78-b474-a3abd3dbbd13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7712c568b478bd2ba958237ba3204246657b3a72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583957"
---
# <a name="options-environment-general-page"></a><span data-ttu-id="9dc5e-102">Opções (página Ambiente-Geral)</span><span class="sxs-lookup"><span data-stu-id="9dc5e-102">Options (Environment-General Page)</span></span>
  <span data-ttu-id="9dc5e-103">Use a caixa de diálogo **Opções** para configurar ações de inicialização do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], opções gerais de gerenciamento de janelas e outras configurações gerais.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-103">Use the **Options** dialog box to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] startup actions, general window management options, and other general settings.</span></span> <span data-ttu-id="9dc5e-104">No menu **Ferramentas** , clique em **Opções**, expanda a pasta **Ambiente** e clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-104">On the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="9dc5e-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="9dc5e-105">UI element list</span></span>  
 <span data-ttu-id="9dc5e-106">**Na inicialização**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-106">**At startup**</span></span>  
 <span data-ttu-id="9dc5e-107">Selecione a ação a ser executada pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quando for iniciado.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-107">Select the action for [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to perform when it is started.</span></span> <span data-ttu-id="9dc5e-108">As opções são:</span><span class="sxs-lookup"><span data-stu-id="9dc5e-108">The options are:</span></span>  
  
-   <span data-ttu-id="9dc5e-109">**Abrir Pesquisador de Objetos** solicita uma conexão e abre o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-109">**Open Object Explorer** prompts for a connection and then opens Object Explorer.</span></span>  
  
-   <span data-ttu-id="9dc5e-110">**Abrir nova janela de consulta** solicita uma conexão e abre o Editor de Consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-110">**Open new query window** prompts for a connection and then opens SQL Query Editor.</span></span>  
  
-   <span data-ttu-id="9dc5e-111">**Abrir Pesquisador de Objetos e nova consulta** solicita uma conexão e, depois, abre o Pesquisador de Objetos e o Editor de Consultas SQL com essa conexão.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-111">**Open Object Explorer and new query** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.</span></span>  
  
-   <span data-ttu-id="9dc5e-112">**Abrir ambiente vazio** abre o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sem uma janela do Editor de Consultas SQL e sem conectar o Pesquisador de Objetos com um servidor.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-112">**Open empty environment** opens [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] without a SQL Query editor window and without connecting Object Explorer to a server.</span></span>  
  
 <span data-ttu-id="9dc5e-113">**Ocultar objetos do sistema no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-113">**Hide system objects in Object Explorer**</span></span>  
 <span data-ttu-id="9dc5e-114">Marque essa caixa de seleção para remover os bancos de dados, tabelas e exibições do sistema e os procedimentos armazenados do sistema da exibição em árvore no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-114">Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer.</span></span> <span data-ttu-id="9dc5e-115">As funções e tipos de dados do sistema não são ocultos.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-115">System functions and system data types are not hidden.</span></span> <span data-ttu-id="9dc5e-116">Essa opção só se aplica a instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não afeta servidores já conectados no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-116">This option only applies to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and does not affect servers already connected in Object Explorer.</span></span>  
  
## <a name="environment-layout"></a><span data-ttu-id="9dc5e-117">Layout do Ambiente</span><span class="sxs-lookup"><span data-stu-id="9dc5e-117">Environment Layout</span></span>  
 <span data-ttu-id="9dc5e-118">Você deve fechar e reabrir o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para alternar entre os modos de ambiente de documentos com guias e de ambiente MDI.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-118">You must close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change between tabbed document and multiple-document interface (MDI) environment mode.</span></span>  
  
 <span data-ttu-id="9dc5e-119">**Documentos com guias**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-119">**Tabbed documents**</span></span>  
 <span data-ttu-id="9dc5e-120">Selecione esta opção para exibir janelas de documentos com guias em editores.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-120">Select this option to display document windows that are tabbed together within editors.</span></span> <span data-ttu-id="9dc5e-121">Janelas de documentos com guias são úteis para organizar e alternar entre vários documentos abertos.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-121">Tabbed document windows are useful for organizing and switching between multiple open documents.</span></span>  
  
 <span data-ttu-id="9dc5e-122">**Ambiente MDI**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-122">**MDI environment**</span></span>  
 <span data-ttu-id="9dc5e-123">Selecione esta opção para abrir documentos em um ambiente MDI.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-123">Select this option to open documents in a MDI environment.</span></span> <span data-ttu-id="9dc5e-124">Janelas de documentos MDI são úteis para garantir o espaço na tela que, de outra forma, seria ocupado pelas guias no ambiente de documentos com guias.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-124">MDI document windows are useful for gaining the screen space that is otherwise taken up by the tabs in the tabbed documents environment.</span></span> <span data-ttu-id="9dc5e-125">Ao trabalhar no modo MDI, você pode alternar entre os documentos pressionando CTRL+TAB ou usar as opções lado a lado localizadas no menu **Janela** .</span><span class="sxs-lookup"><span data-stu-id="9dc5e-125">When working in MDI mode, you can switch between documents by pressing CTRL+TAB, or you can use the tile options located on the **Window** menu.</span></span>  
  
## <a name="docked-tool-window-behavior"></a><span data-ttu-id="9dc5e-126">Comportamento da Janela de Ferramentas Encaixada</span><span class="sxs-lookup"><span data-stu-id="9dc5e-126">Docked Tool Window Behavior</span></span>  
 <span data-ttu-id="9dc5e-127">**O botão Fechar afeta somente a guia ativa**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-127">**Close button affects active tab only**</span></span>  
 <span data-ttu-id="9dc5e-128">Especifica que, quando essa caixa de seleção for marcada, somente a janela de ferramentas exibida no momento será fechada e não todas as janelas de ferramentas do conjunto encaixado.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-128">Specifies that when this check box is selected, only the tool window that has focus currently is closed and not all of the tool windows in the docked set.</span></span> <span data-ttu-id="9dc5e-129">Por padrão, esta caixa é selecionada.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-129">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="9dc5e-130">**O botão Ocultar Automaticamente afeta somente a guia ativa**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-130">**Auto Hide button affects active tab only**</span></span>  
 <span data-ttu-id="9dc5e-131">Especifica que, quando essa caixa de seleção for marcada, somente a janela de ferramentas exibida no momento será oculta automaticamente e não todas as janelas de ferramentas do conjunto encaixado.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-131">Specifies that when this check box is selected, only the tool window that has focus currently is hidden automatically, not all of the tool windows in the docked set.</span></span> <span data-ttu-id="9dc5e-132">Por padrão, essa caixa de seleção é desmarcada.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-132">By default, this check box is cleared.</span></span>  
  
## <a name="display"></a><span data-ttu-id="9dc5e-133">Monitor</span><span class="sxs-lookup"><span data-stu-id="9dc5e-133">Display</span></span>  
 <span data-ttu-id="9dc5e-134">**Exibir n arquivos na lista dos usados recentemente**</span><span class="sxs-lookup"><span data-stu-id="9dc5e-134">**Display n files in recently used list**</span></span>  
 <span data-ttu-id="9dc5e-135">Personaliza o número de projetos e arquivos recentes exibidos no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="9dc5e-135">Customizes the number of recent projects and recent files that appear on the **File** menu.</span></span> <span data-ttu-id="9dc5e-136">Digite um número entre 1 e 24.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-136">Type a number between 1 and 24.</span></span> <span data-ttu-id="9dc5e-137">O padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-137">The default is 4.</span></span> <span data-ttu-id="9dc5e-138">Esse é um modo fácil de recuperar projetos de script e projetos de arquivos e script recentemente usados.</span><span class="sxs-lookup"><span data-stu-id="9dc5e-138">This is an easy way to retrieve recently used script projects and files and script projects.</span></span>  
  
  
