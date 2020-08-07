---
title: Desenhar relações reflexivas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- drawing reflexive relationships
- reflexive relationships
- database diagrams [SQL Server], relationships
ms.assetid: e218363f-faec-46d5-9904-a537fbcc994d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e5056b1a5d0d884edbc4fc818fe8c7ef5cc8ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575499"
---
# <a name="draw-reflexive-relationships-visual-database-tools"></a><span data-ttu-id="1d128-102">Desenhar relações reflexivas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1d128-102">Draw Reflexive Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="1d128-103">Você cria uma relação reflexiva para vincular uma coluna ou colunas em uma tabela com outra coluna ou colunas na mesma tabela.</span><span class="sxs-lookup"><span data-stu-id="1d128-103">You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table.</span></span> <span data-ttu-id="1d128-104">Por exemplo, suponha que a tabela `employee` tenha uma coluna `emp_id` e uma coluna `mgr_id` .</span><span class="sxs-lookup"><span data-stu-id="1d128-104">For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column.</span></span> <span data-ttu-id="1d128-105">Em razão de  cada administrador também ser um funcionário, você relaciona estas duas colunas desenhando uma relação da tabela para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="1d128-105">Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself.</span></span> <span data-ttu-id="1d128-106">Esta relação garante que cada ID de gerente ID acrescentada à tabela corresponda a uma ID de funcionário existente.</span><span class="sxs-lookup"><span data-stu-id="1d128-106">This relationship ensures each manager ID that is added to the table matches an existing employee ID.</span></span>  
  
 <span data-ttu-id="1d128-107">Antes de criar uma relação, você deve primeiro definir uma chave primária ou restrição exclusiva para sua tabela.</span><span class="sxs-lookup"><span data-stu-id="1d128-107">Before you create a relationship, you must first define a primary key or unique constraint for your table.</span></span> <span data-ttu-id="1d128-108">Você então relaciona a coluna de chave primária a uma coluna correspondente.</span><span class="sxs-lookup"><span data-stu-id="1d128-108">You then relate the primary key column to a matching column.</span></span> <span data-ttu-id="1d128-109">Quando você cria a relação, a coluna correspondente se torna uma chave estrangeira da tabela.</span><span class="sxs-lookup"><span data-stu-id="1d128-109">Once you create the relationship, the matching column becomes a foreign key of the table.</span></span>  
  
### <a name="to-draw-a-reflexive-relationship"></a><span data-ttu-id="1d128-110">Para desenhar uma relação reflexiva</span><span class="sxs-lookup"><span data-stu-id="1d128-110">To draw a reflexive relationship</span></span>  
  
1.  <span data-ttu-id="1d128-111">Em seu diagrama de banco de dados, clique no seletor de linhas para a coluna de banco de dados que você quer relacionar a outra coluna e arraste o ponteiro para fora da tabela até que uma linha apareça.</span><span class="sxs-lookup"><span data-stu-id="1d128-111">In your database diagram, click the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.</span></span>  
  
2.  <span data-ttu-id="1d128-112">Arraste a linha de volta à tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d128-112">Drag the line back to the selected table.</span></span>  
  
3.  <span data-ttu-id="1d128-113">Solte o botão do mouse.</span><span class="sxs-lookup"><span data-stu-id="1d128-113">Release the mouse button.</span></span> <span data-ttu-id="1d128-114">A caixa de diálogo **Tabelas e Colunas** aparece.</span><span class="sxs-lookup"><span data-stu-id="1d128-114">The **Tables and Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="1d128-115">Selecione a coluna de chave estrangeira e a tabela de chave primária e a coluna com a qual você quer formar uma relação.</span><span class="sxs-lookup"><span data-stu-id="1d128-115">Select the foreign key column and the primary key table and column with which you want form a relationship.</span></span>  
  
5.  <span data-ttu-id="1d128-116">Clique em **OK** duas vezes para criar a relação.</span><span class="sxs-lookup"><span data-stu-id="1d128-116">Choose **OK** twice to create the relationship.</span></span>  
  
 <span data-ttu-id="1d128-117">Quando você executar consultas em uma tabela, você pode usar uma relação reflexiva para criar uma autojunção.</span><span class="sxs-lookup"><span data-stu-id="1d128-117">When you run queries against a table, you can use a reflexive relationship to create a self-join.</span></span> <span data-ttu-id="1d128-118">Para obter informações sobre como consultar tabelas com junções, veja [Consultar com junções &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1d128-118">For information about querying tables with joins, see [Query with Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d128-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d128-119">See Also</span></span>  
 [<span data-ttu-id="1d128-120">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1d128-120">Query with Joins &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
