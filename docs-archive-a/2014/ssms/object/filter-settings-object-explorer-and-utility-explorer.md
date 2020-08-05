---
title: Configurações de Filtro (Pesquisador de Objetos e Gerenciador do Utilitário) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.filtersettings.f1
- sql12.swb.common.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c31fbcbef9cbab86a7bd3ab7b2fae21e626aaa59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568305"
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a><span data-ttu-id="729a3-102">Configurações de Filtro (Pesquisador de Objetos e Gerenciador do Utilitário)</span><span class="sxs-lookup"><span data-stu-id="729a3-102">Filter Settings (Object Explorer and Utility Explorer)</span></span>
  <span data-ttu-id="729a3-103">Use essa caixa de diálogo para especificar um filtro.</span><span class="sxs-lookup"><span data-stu-id="729a3-103">Use this dialog box to specify a filter.</span></span> <span data-ttu-id="729a3-104">Um filtro permite que você configure o Pesquisador de Objetos e o Gerenciador do Utilitário para exibir apenas os itens que atendam aos critérios específicos.</span><span class="sxs-lookup"><span data-stu-id="729a3-104">A filter allows you to configure Object Explorer and Utility Explorer to display only items that meet specific criteria.</span></span> <span data-ttu-id="729a3-105">Por exemplo, você pode usar um filtro para mostrar apenas os trabalhos com nomes que contêm a palavra "Manutenção".</span><span class="sxs-lookup"><span data-stu-id="729a3-105">For example, you can use a filter to show only jobs with names that contain the word "Maintenance."</span></span> <span data-ttu-id="729a3-106">O cabeçalho da caixa de diálogo **Configurações de Filtro** contém o nome do servidor e pode conter o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="729a3-106">The header for the **Filter Settings** dialog box contains the name of the server, and it may contain the name of the database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="729a3-107">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="729a3-107">UI element list</span></span>  
 <span data-ttu-id="729a3-108">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="729a3-108">**Property**</span></span>  
 <span data-ttu-id="729a3-109">Exibe a propriedade a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="729a3-109">Displays the property to filter on.</span></span>  
  
 <span data-ttu-id="729a3-110">**Operador**</span><span class="sxs-lookup"><span data-stu-id="729a3-110">**Operator**</span></span>  
 <span data-ttu-id="729a3-111">Seleciona o modo que o filtro aplica o valor à propriedade.</span><span class="sxs-lookup"><span data-stu-id="729a3-111">Select the way that the filter applies the value to the property.</span></span> <span data-ttu-id="729a3-112">Existem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="729a3-112">There are the following options:</span></span>  
  
-   <span data-ttu-id="729a3-113">**Igual a**</span><span class="sxs-lookup"><span data-stu-id="729a3-113">**Equals**</span></span>  
  
     <span data-ttu-id="729a3-114">O filtro mostra os itens onde a propriedade e o valor têm uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="729a3-114">The filter shows items where the property and the value are an exact match.</span></span>  
  
-   <span data-ttu-id="729a3-115">**Contém**</span><span class="sxs-lookup"><span data-stu-id="729a3-115">**Contains**</span></span>  
  
     <span data-ttu-id="729a3-116">O filtro mostra os itens onde a propriedade contém o valor.</span><span class="sxs-lookup"><span data-stu-id="729a3-116">The filter shows items where the property contains the value.</span></span> <span data-ttu-id="729a3-117">A propriedade pode conter outro texto.</span><span class="sxs-lookup"><span data-stu-id="729a3-117">The property may contain other text.</span></span>  
  
-   <span data-ttu-id="729a3-118">**Não contém**</span><span class="sxs-lookup"><span data-stu-id="729a3-118">**Does not contain**</span></span>  
  
     <span data-ttu-id="729a3-119">O filtro mostra os itens onde a propriedade não contém o valor.</span><span class="sxs-lookup"><span data-stu-id="729a3-119">The filter shows items that where the property does not contain the value.</span></span>  
  
-   <span data-ttu-id="729a3-120">**Menor que**</span><span class="sxs-lookup"><span data-stu-id="729a3-120">**Less than**</span></span>  
  
     <span data-ttu-id="729a3-121">Disponível para datas, esse filtro mostra os itens cuja data está antes do valor fornecido.</span><span class="sxs-lookup"><span data-stu-id="729a3-121">Available for dates, this filter shows items whose date is before the value provided.</span></span>  
  
-   <span data-ttu-id="729a3-122">**Menor ou igual a**</span><span class="sxs-lookup"><span data-stu-id="729a3-122">**Less than or equal**</span></span>  
  
     <span data-ttu-id="729a3-123">Disponível para datas, esse filtro mostra os itens cuja data contém ou está antes do valor fornecido.</span><span class="sxs-lookup"><span data-stu-id="729a3-123">Available for dates, this filter shows items whose date contains or is before the value provided.</span></span>  
  
-   <span data-ttu-id="729a3-124">**Maior que**</span><span class="sxs-lookup"><span data-stu-id="729a3-124">**Greater than**</span></span>  
  
     <span data-ttu-id="729a3-125">Disponível para datas, esse filtro mostra os itens cuja data está depois do valor fornecido.</span><span class="sxs-lookup"><span data-stu-id="729a3-125">Available for dates, this filter shows items whose date is after the value provided.</span></span>  
  
-   <span data-ttu-id="729a3-126">**Maior ou igual a**</span><span class="sxs-lookup"><span data-stu-id="729a3-126">**Greater than or equal**</span></span>  
  
     <span data-ttu-id="729a3-127">Disponível para datas, esse filtro mostra os itens cuja data contém ou está depois do valor fornecido.</span><span class="sxs-lookup"><span data-stu-id="729a3-127">Available for dates, this filter shows items whose date contains or is after the value provided.</span></span>  
  
-   <span data-ttu-id="729a3-128">**Entre**</span><span class="sxs-lookup"><span data-stu-id="729a3-128">**Between**</span></span>  
  
     <span data-ttu-id="729a3-129">Disponível para datas, este filtro mostra os itens cuja data está entre duas datas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="729a3-129">Available for dates, this filter shows items whose date is between two dates provided.</span></span> <span data-ttu-id="729a3-130">Selecione **Entre** e pressione TAB para adicionar outra linha permitindo a entrada da segunda data.</span><span class="sxs-lookup"><span data-stu-id="729a3-130">Select **Between** and press TAB to add another row allowing entry of the second date.</span></span>  
  
-   <span data-ttu-id="729a3-131">**Não entre**</span><span class="sxs-lookup"><span data-stu-id="729a3-131">**Not between**</span></span>  
  
     <span data-ttu-id="729a3-132">Disponível para datas, esse filtro mostra os itens cuja data está antes ou depois das duas datas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="729a3-132">Available for dates, this filter shows items whose date is before or after two dates provided.</span></span> <span data-ttu-id="729a3-133">Selecione **Não entre** e saia da coluna **Operador** para adicionar outra linha permitindo a entrada da segunda data.</span><span class="sxs-lookup"><span data-stu-id="729a3-133">Select **Not Between** and tab out of the **Operator** column to add another row allowing entry of the second date.</span></span>  
  
 <span data-ttu-id="729a3-134">**Valor**</span><span class="sxs-lookup"><span data-stu-id="729a3-134">**Value**</span></span>  
 <span data-ttu-id="729a3-135">Digite o valor para comparar à propriedade.</span><span class="sxs-lookup"><span data-stu-id="729a3-135">Type the value to compare to the property.</span></span> <span data-ttu-id="729a3-136">Para datas, clique na seta para baixo para mostrar um calendário para selecionar a data.</span><span class="sxs-lookup"><span data-stu-id="729a3-136">For dates, click the down arrow to show a calendar for selecting the date.</span></span>  
  
 <span data-ttu-id="729a3-137">**Limpar Filtro**</span><span class="sxs-lookup"><span data-stu-id="729a3-137">**Clear Filter**</span></span>  
 <span data-ttu-id="729a3-138">Remove todas as configurações de filtro atuais.</span><span class="sxs-lookup"><span data-stu-id="729a3-138">Removes all current filter settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729a3-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="729a3-139">See Also</span></span>  
 <span data-ttu-id="729a3-140">[Usar SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="729a3-140">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="729a3-141">Recursos e tarefas do utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="729a3-141">SQL Server Utility Features and Tasks</span></span>](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
