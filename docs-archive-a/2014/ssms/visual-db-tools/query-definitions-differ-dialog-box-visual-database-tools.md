---
title: Caixa de diálogo Definições de Consulta Diferem (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69639
- vdtsql.chm:69640
- vdt.dlgbox.querydefinitionsdiffer
ms.assetid: 90383473-2922-40e5-9682-3850849aa856
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9a39d5d6b739fa4ab1a96ea95b513ecb7f6682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683292"
---
# <a name="query-definitions-differ-dialog-box-visual-database-tools"></a><span data-ttu-id="7e8c9-102">Caixa de diálogo Definições de Consulta Diferem (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7e8c9-102">Query Definitions Differ Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="7e8c9-103">A caixa de diálogo notifica que a consulta não pode ser representada graficamente nos painéis de Diagrama e de Critério e que será possível editar a consulta apenas no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-103">This dialog box notifies you that your query cannot be represented graphically in the Diagram and Criteria panes, and that you can edit your query only in the SQL pane.</span></span>  
  
 <span data-ttu-id="7e8c9-104">A caixa de diálogo pode aparecer ao digitar ou editar uma instrução SQL no painel SQL; depois você irá para outro painel, verificará a consulta ou tentará executar a consulta, e uma das seguintes condições é aplicada:</span><span class="sxs-lookup"><span data-stu-id="7e8c9-104">This dialog box may appear when you enter or edit an SQL statement in the SQL pane; you then move to another pane, verify the query, or attempt to execute the query; and one of the following conditions applies:</span></span>  
  
-   <span data-ttu-id="7e8c9-105">A instrução SQL está incompleta ou contém um ou mais erros de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-105">The SQL statement is incomplete or contains one or more syntax errors.</span></span>  
  
-   <span data-ttu-id="7e8c9-106">A instrução SQL é válida mas não tem suporte nos painéis gráficos (por exemplo, uma consulta de União).</span><span class="sxs-lookup"><span data-stu-id="7e8c9-106">The SQL statement is valid but is not supported in the graphical panes (for example, a Union query).</span></span>  
  
-   <span data-ttu-id="7e8c9-107">A instrução SQL é válida mas contém sintaxe específica para a conexão de dados que você está usando.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-107">The SQL statement is valid but contains syntax specific to the data connection you are using.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7e8c9-108">É possível verificar se uma instrução é válida, usando o botão **Verificar Instrução SQL** na barra de ferramentas **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="7e8c9-108">You can check whether a statement is valid using the **Verify SQL Statement** button on the **Query** toolbar.</span></span>  
  
 <span data-ttu-id="7e8c9-109">A caixa de diálogo exibe uma mensagem com o motivo pelo qual a instrução SQL não pôde ser representada e, em seguida, pergunta como você deseja proceder.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-109">The dialog box displays a message with the reason that the SQL statement cannot be represented, and then asks how you want to proceed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e8c9-110">A caixa de diálogo **Definições de Consulta Diferem** não aparecerá se os painéis de Diagrama e de Critérios estiverem ocultos.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-110">The **Query Definitions Differ** dialog box does not appear if you have hidden the Diagram and Criteria panes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7e8c9-111">Opções</span><span class="sxs-lookup"><span data-stu-id="7e8c9-111">Options</span></span>  
 <span data-ttu-id="7e8c9-112">**Botão Ignorar**</span><span class="sxs-lookup"><span data-stu-id="7e8c9-112">**Ignore Button**</span></span>  
 <span data-ttu-id="7e8c9-113">Escolha esse botão para especificar se deseja aceitar a instrução SQL para editá-la ou executá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-113">Choose this button to specify that you want to accept the SQL statement, either to edit it further or to execute it.</span></span> <span data-ttu-id="7e8c9-114">Se você aceitar a instrução, os painéis de Diagrama e de Critério aparecerão para indicar que eles não representam a instrução no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-114">If you accept the statement, the Diagram and Criteria panes appear dimmed to indicate that they do not represent the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="7e8c9-115">**Botão Desfazer**</span><span class="sxs-lookup"><span data-stu-id="7e8c9-115">**Undo Button**</span></span>  
 <span data-ttu-id="7e8c9-116">Escolha esse botão para descartar as alterações feitas para o painel SQL.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-116">Choose this button to discard your changes to the SQL pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e8c9-117">Se a instrução estiver correta mas não tiver suporte gráfico pelo Designer de Consulta e Exibição, será possível executá-la mesmo que não esteja representada nos painéis de Diagrama e de Critério.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-117">If the statement is correct but not supported graphically by the Query and View Designer, you can execute it even though it cannot be represented in the Diagram and Criteria panes.</span></span> <span data-ttu-id="7e8c9-118">Por exemplo, se você inserir uma consulta de União, a instrução pode ser executada mas não representada nos outros painéis.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-118">For example, if you enter a Union query, the statement can be executed but not represented in the other panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8c9-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e8c9-119">See Also</span></span>  
 [<span data-ttu-id="7e8c9-120">Ferramentas do Designer de Consulta e Exibição &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7e8c9-120">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
