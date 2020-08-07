---
title: Mapear relações muitos para muitos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbcbdbdf8d8371baa2a817e43b831535723be7ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582746"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a><span data-ttu-id="82bc4-102">Mapear relações muitos para muitos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="82bc4-102">Map Many-to-Many Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="82bc4-103">Relações muitos para muitos permitem relacionar cada linha em uma tabela a muitas linhas em outra tabela e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="82bc4-103">Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa.</span></span> <span data-ttu-id="82bc4-104">Por exemplo, você pode criar uma relação muitos para muitos entre a tabela `authors` e a tabela `titles` para corresponder cada autor a todos os seus livros e corresponder cada livro a todos seus autores.</span><span class="sxs-lookup"><span data-stu-id="82bc4-104">For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of his or her books and to match each book to all of its authors.</span></span> <span data-ttu-id="82bc4-105">Criar uma relação um para muitos de qualquer tabela indicaria incorretamente que cada livro pode ter somente um autor, ou que cada autor pode escrever somente um livro.</span><span class="sxs-lookup"><span data-stu-id="82bc4-105">Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.</span></span>  
  
 <span data-ttu-id="82bc4-106">Relações muitos para muitos entre tabelas são acomodadas em bancos de dados por meio de tabelas de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-106">Many-to-many relationships between tables are accommodated in databases by means of junction tables.</span></span> <span data-ttu-id="82bc4-107">Uma tabela de junção contém as colunas de chave primária das duas tabelas que você deseja relacionar.</span><span class="sxs-lookup"><span data-stu-id="82bc4-107">A junction table contains the primary key columns of the two tables you want to relate.</span></span> <span data-ttu-id="82bc4-108">Em seguida, você cria uma relação das colunas de chave primária de cada uma dessas duas tabelas para as colunas correspondentes na tabela de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-108">You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table.</span></span> <span data-ttu-id="82bc4-109">No banco de dados pubs, a tabela `titleauthor` é a tabela de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-109">In the pubs database, the `titleauthor` table is a junction table.</span></span>  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a><span data-ttu-id="82bc4-110">Para criar uma relação de muitos para muitos entre tabelas</span><span class="sxs-lookup"><span data-stu-id="82bc4-110">To create a many-to-many relationship between tables</span></span>  
  
1.  <span data-ttu-id="82bc4-111">No seu diagrama de banco de dados, adicione as tabelas que você deseja para criar uma relação muitos para muitos entre elas.</span><span class="sxs-lookup"><span data-stu-id="82bc4-111">In your database diagram, add the tables that you want to create a many-to-many relationship between.</span></span>  
  
2.  <span data-ttu-id="82bc4-112">Crie uma terceira tabela clicando com o botão direito do mouse no diagrama e escolhendo **Nova Tabela** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="82bc4-112">Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu.</span></span> <span data-ttu-id="82bc4-113">Essa se tornará a tabela de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-113">This will become the junction table.</span></span>  
  
3.  <span data-ttu-id="82bc4-114">Na caixa de diálogo **Escolher Nome** , altere o nome da tabela atribuído pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="82bc4-114">In the **Choose Name** dialog box, change the system-assigned table name.</span></span> <span data-ttu-id="82bc4-115">Por exemplo, a tabela de junção entre a tabela `titles` e a tabela `authors` é agora nomeada `titleauthors`.</span><span class="sxs-lookup"><span data-stu-id="82bc4-115">For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.</span></span>  
  
4.  <span data-ttu-id="82bc4-116">Copie as colunas de chave primária de cada uma das duas outras tabelas para a tabela de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-116">Copy the primary key columns from each of the other two tables to the junction table.</span></span> <span data-ttu-id="82bc4-117">Você pode adicionar outras colunas a esta tabela, da mesma maneira que pode adicionar a qualquer outra tabela.</span><span class="sxs-lookup"><span data-stu-id="82bc4-117">You can add other columns to this table, just as you can to any other table.</span></span>  
  
5.  <span data-ttu-id="82bc4-118">Na tabela de junção, defina a chave primária para incluir todas as colunas de chave primária das duas outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="82bc4-118">In the junction table, set the primary key to include all the primary key columns from the other two tables.</span></span> <span data-ttu-id="82bc4-119">Para obter detalhes, consulte [criar chaves primárias](../../relational-databases/tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="82bc4-119">For details, see [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span></span>  
  
6.  <span data-ttu-id="82bc4-120">Defina uma relação um para muitos entre cada uma das duas tabelas primárias e a tabela de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-120">Define a one-to-many relationship between each of the two primary tables and the junction table.</span></span> <span data-ttu-id="82bc4-121">A tabela de junção deve estar no lado "muitos" de ambas as relações que você criar.</span><span class="sxs-lookup"><span data-stu-id="82bc4-121">The junction table should be at the "many" side of both of the relationships you create.</span></span> <span data-ttu-id="82bc4-122">Para obter detalhes, consulte [criar relações de chave estrangeira](../../relational-databases/tables/create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="82bc4-122">For details, see [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82bc4-123">A criação de uma tabela de junção em um diagrama de banco de dados não insere dados das tabelas relacionadas na tabela de junção.</span><span class="sxs-lookup"><span data-stu-id="82bc4-123">The creation of a junction table in a database diagram does not insert data from the related tables into the junction table.</span></span> <span data-ttu-id="82bc4-124">Para obter informações sobre como inserir dados em uma tabela, veja [Criar consultas Inserir Resultados &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="82bc4-124">For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82bc4-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82bc4-125">See Also</span></span>  
 [<span data-ttu-id="82bc4-126">Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="82bc4-126">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](work-with-database-diagrams-visual-database-tools.md)  
  
  
