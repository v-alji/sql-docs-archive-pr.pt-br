---
title: Editor da tarefa Executar SQL (página conjunto de resultados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.resultset.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: d27000c8-8d91-4e1c-b45e-bca9a3c12f6d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 027f3c77e84b47958e9fb6567acdb308c14eb1e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572126"
---
# <a name="execute-sql-task-editor-result-set-page"></a><span data-ttu-id="01f58-102">Editor da Tarefa Executar SQL (página Conjunto de Resultados)</span><span class="sxs-lookup"><span data-stu-id="01f58-102">Execute SQL Task Editor (Result Set Page)</span></span>
  <span data-ttu-id="01f58-103">Use a página **Conjunto de Resultados** da caixa de diálogo **Editor da Tarefa Executar SQL** para mapear o resultado da instrução SQL para variáveis novas ou já existentes.</span><span class="sxs-lookup"><span data-stu-id="01f58-103">Use the **Result Set** page of the **Execute SQL Task Editor** dialog to map the result of the SQL statement to new or existing variables.</span></span> <span data-ttu-id="01f58-104">As opções dessa caixa de diálogo serão desabilitadas se o **ResultSet** na página Geral for definido como **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="01f58-104">The options in this dialog box are disabled if **ResultSet** on the General page is set to **None**.</span></span>  
  
 <span data-ttu-id="01f58-105">Para obter mais informações, consulte [Tarefa Executar SQL](control-flow/execute-sql-task.md) e [Conjuntos de resultados na tarefa Executar SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="01f58-105">For more information about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="01f58-106">Opções</span><span class="sxs-lookup"><span data-stu-id="01f58-106">Options</span></span>  
 <span data-ttu-id="01f58-107">**Nome do Resultado**</span><span class="sxs-lookup"><span data-stu-id="01f58-107">**Result Name**</span></span>  
 <span data-ttu-id="01f58-108">Depois que você adicionar um conjunto de resultados de conjunto de mapeamento clicando em **Adicionar**, forneça um nome exclusivo para o resultado.</span><span class="sxs-lookup"><span data-stu-id="01f58-108">After you have added a result set mapping set by clicking **Add**, provide a name for the result.</span></span> <span data-ttu-id="01f58-109">Dependendo do tipo de conjunto de resultados, é necessário usar nomes de resultado específicos.</span><span class="sxs-lookup"><span data-stu-id="01f58-109">Depending on the result set type, you must use specific result names.</span></span>  
  
 <span data-ttu-id="01f58-110">Se o tipo de conjunto de resultados for **Linha única**, será possível usar o nome de uma coluna retornado pela consulta ou o número que representam a posição de uma coluna na lista de colunas de uma coluna retornada pela consulta.</span><span class="sxs-lookup"><span data-stu-id="01f58-110">If the result set type is **Single row**, you can use either the name of a column returned by the query or the number that represents the position of a column in the column list of a column returned by the query.</span></span>  
  
 <span data-ttu-id="01f58-111">Se o tipo de conjunto de resultados for **Conjunto de resultados completo** ou **XML**, será necessário usar 0 como o nome de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="01f58-111">If the result set type is **Full result set** or **XML**, you must use 0 as the result set name.</span></span>  
  
 <span data-ttu-id="01f58-112">**Tópicos Relacionados**: [Conjuntos de resultados na tarefa Executar SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="01f58-112">**Related Topics**: [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="01f58-113">**Nome da Variável**</span><span class="sxs-lookup"><span data-stu-id="01f58-113">**Variable Name**</span></span>  
 <span data-ttu-id="01f58-114">Mapeie o conjunto de resultados para uma variável selecionando uma variável ou clique em \<**New variable...**> para adicionar uma nova variável usando a caixa de diálogo **Adicionar Variável**.</span><span class="sxs-lookup"><span data-stu-id="01f58-114">Map the result set to a variable by selecting a variable or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="01f58-115">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="01f58-115">**Add**</span></span>  
 <span data-ttu-id="01f58-116">Clique para adicionar um mapeamento de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="01f58-116">Click to add a result set mapping.</span></span>  
  
 <span data-ttu-id="01f58-117">**Remover**</span><span class="sxs-lookup"><span data-stu-id="01f58-117">**Remove**</span></span>  
 <span data-ttu-id="01f58-118">Selecione um mapeamento de conjunto de resultados na lista e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="01f58-118">Select a result set mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f58-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01f58-119">See Also</span></span>  
 <span data-ttu-id="01f58-120">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="01f58-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="01f58-121">[Editor da tarefa Executar SQL &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="01f58-121">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="01f58-122">[Editor da tarefa Executar SQL &#40;página mapeamento de parâmetro&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span><span class="sxs-lookup"><span data-stu-id="01f58-122">[Execute SQL Task Editor &#40;Parameter Mapping Page&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span></span>  
 [<span data-ttu-id="01f58-123">Referência do Transact-SQL &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="01f58-123">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
