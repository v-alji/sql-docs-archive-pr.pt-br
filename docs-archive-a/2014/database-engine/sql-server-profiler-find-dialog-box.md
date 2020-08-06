---
title: Caixa de diálogo SQL Server Profiler-localizar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.find.f1
helpviewer_keywords:
- Find dialog box
ms.assetid: dfaeec04-93d3-4214-9fc1-38b80179b36b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cedf50930c06d211ebcee0c45a249667219f392c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683662"
---
# <a name="sql-server-profiler---find-dialog-box"></a><span data-ttu-id="7515f-102">SQL Server Profiler - Caixa de diálogo Localizar</span><span class="sxs-lookup"><span data-stu-id="7515f-102">SQL Server Profiler - Find Dialog Box</span></span>
  <span data-ttu-id="7515f-103">Use a caixa de diálogo **Localizar** para pesquisar um rastreamento para caracteres ou palavras específicos.</span><span class="sxs-lookup"><span data-stu-id="7515f-103">Use the **Find** dialog box to search a trace for specific characters or words.</span></span> <span data-ttu-id="7515f-104">Para cancelar uma pesquisa em andamento, pressione ESC.</span><span class="sxs-lookup"><span data-stu-id="7515f-104">To cancel a search in progress, press ESC.</span></span>  
  
 <span data-ttu-id="7515f-105">Para abrir essa caixa de diálogo no [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], no menu **Editar** , clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="7515f-105">To open this dialog box in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], on the **Edit** menu, click **Find**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7515f-106">Opções</span><span class="sxs-lookup"><span data-stu-id="7515f-106">Options</span></span>  
 <span data-ttu-id="7515f-107">**Localizar**</span><span class="sxs-lookup"><span data-stu-id="7515f-107">**Find what**</span></span>  
 <span data-ttu-id="7515f-108">Insira o texto que deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="7515f-108">Enter the text that you want to search for.</span></span> <span data-ttu-id="7515f-109">A pesquisa corresponde a qualquer cadeia de caracteres que contenha a cadeia especificada.</span><span class="sxs-lookup"><span data-stu-id="7515f-109">The search matches any string containing the specified string.</span></span> <span data-ttu-id="7515f-110">Por exemplo, a pesquisa por "Concluído" corresponde a "SQL:LoteConcluído".</span><span class="sxs-lookup"><span data-stu-id="7515f-110">For example, searching for "Completed" matches "SQL:BatchCompleted."</span></span> <span data-ttu-id="7515f-111">Caracteres curinga (\*, ?, etc.) não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="7515f-111">Wild card characters (\*, ?, etc.) are not supported.</span></span>  
  
 <span data-ttu-id="7515f-112">**Pesquisar na coluna**</span><span class="sxs-lookup"><span data-stu-id="7515f-112">**Search in column**</span></span>  
 <span data-ttu-id="7515f-113">Clique em uma coluna de dados para pesquisar ou clique **\<All columns>** para pesquisar todas as colunas de dados no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="7515f-113">Click a data column to search, or click **\<All columns>** to search all the data columns in the trace.</span></span>  
  
 <span data-ttu-id="7515f-114">**Diferenciar caso**</span><span class="sxs-lookup"><span data-stu-id="7515f-114">**Match case**</span></span>  
 <span data-ttu-id="7515f-115">Localiza texto que tem maiúsculas e minúsculas iguais às da caixa **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="7515f-115">Finds text that has the same case as the **Find what** box.</span></span> <span data-ttu-id="7515f-116">Desmarque essa caixa de seleção para localizar exemplos no rastreamento que tenham caracteres de texto tanto com letras maiúsculas como com minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7515f-116">Clear this check box to find examples in the trace that are in both uppercase and lowercase text characters.</span></span>  
  
 <span data-ttu-id="7515f-117">**Coincidir palavra inteira**</span><span class="sxs-lookup"><span data-stu-id="7515f-117">**Match whole word**</span></span>  
 <span data-ttu-id="7515f-118">Restringe a pesquisa a palavras inteiras.</span><span class="sxs-lookup"><span data-stu-id="7515f-118">Restricts the search to entire words.</span></span> <span data-ttu-id="7515f-119">Desmarque a caixa de seleção **Coincidir palavra inteira** para pesquisar caracteres em uma palavra.</span><span class="sxs-lookup"><span data-stu-id="7515f-119">Clear the **Match whole word** check box to search for characters within a word.</span></span>  
  
 <span data-ttu-id="7515f-120">**Localizar Próximo**</span><span class="sxs-lookup"><span data-stu-id="7515f-120">**Find Next**</span></span>  
 <span data-ttu-id="7515f-121">Localiza o próximo exemplo dos caracteres na caixa **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="7515f-121">Finds the next example of the characters in the **Find what** box.</span></span>  
  
 <span data-ttu-id="7515f-122">**Localizar Anterior**</span><span class="sxs-lookup"><span data-stu-id="7515f-122">**Find Previous**</span></span>  
 <span data-ttu-id="7515f-123">Pesquisa para trás no rastreamento, para localizar o exemplo anterior dos caracteres na caixa **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="7515f-123">Searches backwards in the trace, to find the previous example of the characters in the **Find what** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7515f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7515f-124">See Also</span></span>  
 <span data-ttu-id="7515f-125">[Localizar um valor ou coluna de dados ao rastrear &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7515f-125">[Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7515f-126">[Criar um &#40;de rastreamento SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7515f-126">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7515f-127">[Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7515f-127">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7515f-128">[Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7515f-128">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7515f-129">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="7515f-129">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="7515f-130">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7515f-130">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
