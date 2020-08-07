---
title: Definindo opções de ferramentas e layout | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 43e97ce0-97bc-4a27-9485-5bbeb7190b85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 96d853a85b8ee4d451c55d7ea59af3755887be22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682009"
---
# <a name="setting-tool-options-and-layout"></a><span data-ttu-id="0cd7c-102">Definindo o layout e opções de ferramentas</span><span class="sxs-lookup"><span data-stu-id="0cd7c-102">Setting Tool Options and Layout</span></span>
  <span data-ttu-id="0cd7c-103">É possível definir as opções que configuram o que a GUI (interface gráfica do usuário) do Orientador de Otimização do Mecanismo de Banco de Dados exibe na inicialização, quais fontes ela usa e outra ferramenta de funcionalidade para oferecer o melhor suporte na hora de usá-la.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-103">You can set options that configure what the Database Engine Tuning Advisor graphical user interface (GUI) displays on startup, the font it uses, and other tool functionality to best support how you use it.</span></span> <span data-ttu-id="0cd7c-104">As práticas nesta página irão familiarizá-lo com as opções de definição e como defini-las.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-104">The practices on this page familiarize you with the options you can set, and how to set them.</span></span>  
  
### <a name="set-the-tool-options"></a><span data-ttu-id="0cd7c-105">Definir as opções de ferramenta</span><span class="sxs-lookup"><span data-stu-id="0cd7c-105">Set the tool options</span></span>  
  
1.  <span data-ttu-id="0cd7c-106">Inicie o Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-106">Start the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="0cd7c-107">No menu **Iniciar** do Windows, aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Desempenho**e clique em **Orientador de Otimização do Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-107">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="0cd7c-108">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-108">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="0cd7c-109">Na caixa de diálogo **Opções** , exiba as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0cd7c-109">In the **Options** dialog box, view the following options:</span></span>  
  
    -   <span data-ttu-id="0cd7c-110">Expanda a lista **Na inicialização** para exibir o que o Orientador de Otimização do Mecanismo de Banco de Dados pode exibir ao ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-110">Expand the **On startup** list to view what Database Engine Tuning Advisor can display when it is started.</span></span> <span data-ttu-id="0cd7c-111">Por padrão, está selecionado **Mostrar uma nova sessão** .</span><span class="sxs-lookup"><span data-stu-id="0cd7c-111">By default, **Show a new session** is selected.</span></span>  
  
    -   <span data-ttu-id="0cd7c-112">Clique em **Alterar fonte** para ver quais fontes você pode escolher para as listas de bancos de dados e tabelas na guia **geral** . As fontes escolhidas para essa opção também são usadas em Orientador de Otimização do Mecanismo de Banco de Dados grades de recomendação e relatórios depois que você tiver executado o ajuste.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-112">Click **Change Font** to see what fonts you can choose for the lists of databases and tables on the **General** tab. The fonts you choose for this option also are used in Database Engine Tuning Advisor recommendation grids and reports after you have performed tuning.</span></span> <span data-ttu-id="0cd7c-113">Por padrão, o Orientador de Otimização do Mecanismo de Banco de Dados usa fontes de sistema.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-113">By default, Database Engine Tuning Advisor uses system fonts.</span></span>  
  
    -   <span data-ttu-id="0cd7c-114">O **Número de itens nas listas usadas mais recentemente** pode ser definido entre **1** e **10**.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-114">The **Number of items in most recently used lists** can be set between **1** and **10**.</span></span> <span data-ttu-id="0cd7c-115">Isso define o número máximo de itens nas listas exibidas ao se clicar em **Sessões Recentes** ou **Arquivos Recentes** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="0cd7c-115">This sets the maximum number of items in the lists displayed by clicking **Recent Sessions** or **Recent Files** on the **File** menu.</span></span> <span data-ttu-id="0cd7c-116">Por padrão, essa opção está definida como **4**.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-116">By default, this option is set to **4**.</span></span>  
  
    -   <span data-ttu-id="0cd7c-117">Quando **Lembrar minhas últimas opções de ajuste** está marcada, por padrão, o Orientador de Otimização do Mecanismo de Banco de Dados usa as opções de ajuste especificadas em sua última sessão de ajuste para a próxima sessão.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-117">When **Remember my last tuning options** is checked, by default Database Engine Tuning Advisor uses the tuning options you specified for your last tuning session for the next tuning session.</span></span> <span data-ttu-id="0cd7c-118">Desmarque essa caixa de seleção para usar as opções de ajuste padrão do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-118">Clear this check box to use Database Engine Tuning Advisor tuning option defaults.</span></span> <span data-ttu-id="0cd7c-119">Por padrão, essa opção é selecionada.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-119">By default, this option is selected.</span></span>  
  
    -   <span data-ttu-id="0cd7c-120">Por padrão, **Perguntar antes de excluir permanentemente as sessões** está marcada para evitar excluir sessões de ajuste acidentalmente.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-120">By default, **Ask before permanently deleting sessions** is checked to avoid accidentally deleting tuning sessions.</span></span>  
  
    -   <span data-ttu-id="0cd7c-121">Por padrão, **Perguntar antes de parar a análise da sessão** está marcada para evitar parar uma sessão de ajuste acidentalmente antes que o Orientador de Otimização do Mecanismo de Banco de Dados termine de analisar uma carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-121">By default, **Ask before stopping session analysis** is checked to avoid accidentally stopping a tuning session before Database Engine Tuning Advisor has finished analyzing a workload.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0cd7c-122">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="0cd7c-122">Next Lesson</span></span>  
 [<span data-ttu-id="0cd7c-123">Lição 2: Usando o Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="0cd7c-123">Lesson 2: Using Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
