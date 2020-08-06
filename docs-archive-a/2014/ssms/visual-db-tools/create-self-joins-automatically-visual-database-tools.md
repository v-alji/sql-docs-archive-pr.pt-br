---
title: Criar autojunções automaticamente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a428a44d33b5990e849772b43841df472ca7f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569001"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a><span data-ttu-id="f9c38-102">Criar autojunções automaticamente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f9c38-102">Create Self-Joins Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="f9c38-103">Se uma tabela tiver uma relação reflexiva no banco de dados, a autojunção poderá ocorrer automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f9c38-103">If a table has a reflexive relationship in the database, you can join it to itself automatically.</span></span>  
  
### <a name="to-create-a-self-join-automatically"></a><span data-ttu-id="f9c38-104">Para criar uma autojunção automaticamente</span><span class="sxs-lookup"><span data-stu-id="f9c38-104">To create a self-join automatically</span></span>  
  
1.  <span data-ttu-id="f9c38-105">Adicione ao [painel Diagrama](visual-database-tools.md) a tabela com a qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="f9c38-105">Add to the [Diagram pane](visual-database-tools.md) the table you want to work with.</span></span>  
  
2.  <span data-ttu-id="f9c38-106">Adicione a mesma tabela novamente, de forma que seja exibida a mesma tabela duas vezes no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="f9c38-106">Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="f9c38-107">O [Designer de Consulta e Exibição](query-and-view-designer-tools-visual-database-tools.md) atribui um alias à segunda instância adicionando um número sequencial ao nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="f9c38-107">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="f9c38-108">Além disso, o Designer de Consulta e Exibição cria uma linha de junção entre os dois retângulos representando dois modos diferentes de participação da tabela na consulta.</span><span class="sxs-lookup"><span data-stu-id="f9c38-108">In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c38-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9c38-109">See Also</span></span>  
 [<span data-ttu-id="f9c38-110">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f9c38-110">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
