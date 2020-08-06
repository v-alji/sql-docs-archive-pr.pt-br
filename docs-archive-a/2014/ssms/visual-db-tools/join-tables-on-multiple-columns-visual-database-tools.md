---
title: Unir tabelas em várias colunas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiple column joins
- joins [SQL Server], multiple columns
ms.assetid: 56a158bc-a42a-4b78-baad-4721d2d22cd3
author: stevestein
ms.author: sstein
ms.openlocfilehash: dda52fe27b2034242c8cbf458dd010240c792146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574426"
---
# <a name="join-tables-on-multiple-columns-visual-database-tools"></a><span data-ttu-id="79557-102">Unir tabelas em várias colunas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="79557-102">Join Tables on Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="79557-103">Você pode unir tabelas em várias colunas.</span><span class="sxs-lookup"><span data-stu-id="79557-103">You can join tables with multiple columns.</span></span> <span data-ttu-id="79557-104">Quer dizer, você poderá criar uma consulta que corresponde às linhas de duas tabelas apenas se elas satisfizerem várias condições.</span><span class="sxs-lookup"><span data-stu-id="79557-104">That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions.</span></span> <span data-ttu-id="79557-105">Se o banco de dados contiver uma relação, que corresponda a várias colunas de chave estrangeira, em uma tabela para uma chave primária de multicolunas na outra tabela, você poderá usar esta relação para criar uma junção de multicolunas.</span><span class="sxs-lookup"><span data-stu-id="79557-105">If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join.</span></span> <span data-ttu-id="79557-106">Para obter detalhes, consulte [Unir tabelas automaticamente &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="79557-106">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="79557-107">Mesmo que o banco de dados não contenha nenhuma relação de chave estrangeira de multicolunas, você poderá criar a junção manualmente.</span><span class="sxs-lookup"><span data-stu-id="79557-107">Even if the database contains no multi-column foreign-key relationship, you can create the join manually.</span></span>  
  
### <a name="to-manually-create-a-multicolumn-join"></a><span data-ttu-id="79557-108">Para criar uma junção de multicolunas manualmente</span><span class="sxs-lookup"><span data-stu-id="79557-108">To manually create a multicolumn join</span></span>  
  
1.  <span data-ttu-id="79557-109">Adicione ao [Painel de Diagrama](diagram-pane-visual-database-tools.md) as tabelas que deseja unir.</span><span class="sxs-lookup"><span data-stu-id="79557-109">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.</span></span>  
  
2.  <span data-ttu-id="79557-110">Arraste o nome da primeira coluna de junção, na janela da primeira tabela, e solte sobre a coluna relacionada, na janela da segunda tabela.</span><span class="sxs-lookup"><span data-stu-id="79557-110">Drag the name of the first join column in the first table window and drop it onto the related column in the second table window.</span></span> <span data-ttu-id="79557-111">Você não pode basear uma junção em texto, ntext ou colunas de imagem.</span><span class="sxs-lookup"><span data-stu-id="79557-111">You cannot base a join on text, ntext, or image columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79557-112">Em geral, as colunas de junção devem ser com os mesmos tipos de dados (ou compatíveis).</span><span class="sxs-lookup"><span data-stu-id="79557-112">In general, the join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="79557-113">Por exemplo, se a coluna de junção na primeira tabela for uma data, você deve relacionar isto a uma coluna de data na segunda tabela.</span><span class="sxs-lookup"><span data-stu-id="79557-113">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="79557-114">Por outro lado, se a primeira coluna de junção for um inteiro, a coluna de junção relacionada também deverá ser do tipo de dados inteiro, mas poderá ser de um tamanho diferente.</span><span class="sxs-lookup"><span data-stu-id="79557-114">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="79557-115">Entretanto, podem haver casos onde as conversões de tipos de dados implícitos poderão unir colunas aparentemente incompatíveis, que funcionarão.</span><span class="sxs-lookup"><span data-stu-id="79557-115">However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.</span></span>  
    >   
    >  <span data-ttu-id="79557-116">O [Designer de Consulta e Exibição](query-and-view-designer-tools-visual-database-tools.md) não verificará os tipos de dados das colunas que você usa para criar uma junção, mas, quando você executar a consulta, o banco de dados exibirá um erro se os tipos de dados não forem compatíveis.</span><span class="sxs-lookup"><span data-stu-id="79557-116">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="79557-117">Arraste o nome da segunda coluna de junção na janela da primeira tabela e solte sobre a coluna relacionada na janela da segunda tabela.</span><span class="sxs-lookup"><span data-stu-id="79557-117">Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.</span></span>  
  
4.  <span data-ttu-id="79557-118">Repita a etapa 3 para cada par adicional de colunas de junção, nas duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="79557-118">Repeat step 3 for each additional pair of join columns in the two tables.</span></span>  
  
5.  <span data-ttu-id="79557-119">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="79557-119">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79557-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79557-120">See Also</span></span>  
 [<span data-ttu-id="79557-121">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="79557-121">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
