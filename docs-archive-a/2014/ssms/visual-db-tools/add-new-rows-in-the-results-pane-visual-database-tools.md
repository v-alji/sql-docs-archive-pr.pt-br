---
title: Adicionar linhas novas ao painel Resultados (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- inserting rows
- Query Designer [SQL Server], Results pane
- Results pane
- adding rows
- row additions [SQL Server], Results pane
ms.assetid: 59891c84-3f54-4ab9-8b86-72c59627b480
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3137da106279e09305261c6c7cb7fd06d254b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571767"
---
# <a name="add-new-rows-in-the-results-pane-visual-database-tools"></a><span data-ttu-id="fff4e-102">Adicionar linhas novas ao painel Resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fff4e-102">Add New Rows in the Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="fff4e-103">Você pode adicionar dados novos digitando-os ou colando-os a partir de outro programa como o Bloco de Notas ou o Excel.</span><span class="sxs-lookup"><span data-stu-id="fff4e-103">You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel.</span></span> <span data-ttu-id="fff4e-104">Uma linha a ser colada deve ter exatamente o mesmo número e tipos de colunas que a tabela em que você está colando.</span><span class="sxs-lookup"><span data-stu-id="fff4e-104">A row to be pasted must have exactly the same number and types of columns as the table into which you are pasting.</span></span> <span data-ttu-id="fff4e-105">Você pode colar várias linhas de uma vez no painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="fff4e-105">You can paste multiple rows into the Results pane at once.</span></span>  
  
 <span data-ttu-id="fff4e-106">Para obter informações sobre como inserir dados, consulte [Regras para atualizar resultados &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fff4e-106">For information about how to enter data see [Rules for Updating Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-add-a-new-data-row"></a><span data-ttu-id="fff4e-107">Para adicionar uma nova linha de dados</span><span class="sxs-lookup"><span data-stu-id="fff4e-107">To add a new data row</span></span>  
  
1.  <span data-ttu-id="fff4e-108">Navegue até a parte inferior do painel Resultados, onde tiver uma linha em branco disponível para adicionar uma nova linha de dados.</span><span class="sxs-lookup"><span data-stu-id="fff4e-108">Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.</span></span>  
  
     <span data-ttu-id="fff4e-109">Os valores iniciais para todas as colunas serão *NULL*.</span><span class="sxs-lookup"><span data-stu-id="fff4e-109">The initial values for all columns will be *NULL*.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fff4e-110">Para ir diretamente para a primeira linha em branco utilize a barra de navegação na parte inferior do painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="fff4e-110">To go directly to the first empty row use the navigation bar at the bottom of the Results pane.</span></span>  
  
2.  <span data-ttu-id="fff4e-111">Se você estiver colando linhas a partir da Área de Transferência, selecione a nova linha clicando no botão à sua esquerda.</span><span class="sxs-lookup"><span data-stu-id="fff4e-111">If you are pasting rows from the Clipboard, select the new row by clicking the button to its left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fff4e-112">Se uma ou mais linhas que você estiver colando não puderem ser confirmadas no banco de dados, você receberá uma mensagem indicando quais linhas não puderam ser confirmadas.</span><span class="sxs-lookup"><span data-stu-id="fff4e-112">If one or more of the rows you're pasting can't be committed to the database you will receive a message telling you which row(s) couldn't be committed.</span></span>  
  
3.  <span data-ttu-id="fff4e-113">Insira os dados da linha nova.</span><span class="sxs-lookup"><span data-stu-id="fff4e-113">Enter the data for the new row.</span></span> <span data-ttu-id="fff4e-114">Se estiver colando, escolha **Colar** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="fff4e-114">If you are pasting, choose **Paste** from the **Edit** menu.</span></span>  
  
4.  <span data-ttu-id="fff4e-115">Deixe essa linha para confirmá-la no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fff4e-115">Leave that row to commit it to the database.</span></span>  
  
 <span data-ttu-id="fff4e-116">Se ocorrer um erro quando você salvar a linha, o Designer de Consulta e Exibição exibirá uma mensagem e o levará à linha que você estava editando.</span><span class="sxs-lookup"><span data-stu-id="fff4e-116">If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing.</span></span> <span data-ttu-id="fff4e-117">Em seguida, você pode:</span><span class="sxs-lookup"><span data-stu-id="fff4e-117">You can then:</span></span>  
  
-   <span data-ttu-id="fff4e-118">Resolver o erro fazendo mais edições na linha.</span><span class="sxs-lookup"><span data-stu-id="fff4e-118">Resolve the error by making further edits in the row.</span></span>  
  
-   <span data-ttu-id="fff4e-119">Cancelar a edição pressionando ESC.</span><span class="sxs-lookup"><span data-stu-id="fff4e-119">Cancel the edit by pressing ESC.</span></span> <span data-ttu-id="fff4e-120">Se você pressionar ESC enquanto estiver em uma célula alterada, as alterações daquela célula serão canceladas.</span><span class="sxs-lookup"><span data-stu-id="fff4e-120">If you press ESC while in a cell that you changed, the changes for that cell are canceled.</span></span> <span data-ttu-id="fff4e-121">Se você pressionar ESC enquanto estiver em uma célula que ainda não foi alterada, as alterações de toda a linha serão canceladas.</span><span class="sxs-lookup"><span data-stu-id="fff4e-121">If you press ESC while in a cell you have not changed, the changes for the entire row are canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff4e-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fff4e-122">See Also</span></span>  
 <span data-ttu-id="fff4e-123">[Trabalhar com dados no painel de resultados &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fff4e-123">[Work with Data in the Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fff4e-124">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fff4e-124">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
