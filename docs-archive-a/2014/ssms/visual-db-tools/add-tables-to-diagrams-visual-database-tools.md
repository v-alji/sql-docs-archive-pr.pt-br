---
title: Adicionar tabelas a diagramas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe5c1274ac390f4834bd8ac1088258061fc0406d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574439"
---
# <a name="add-tables-to-diagrams-visual-database-tools"></a><span data-ttu-id="e3884-102">Adicionar tabelas a diagramas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e3884-102">Add Tables to Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="e3884-103">Você pode adicionar uma tabela a seu diagrama de banco de dados para editar sua estrutura ou relacioná-la a outras tabelas no diagrama.</span><span class="sxs-lookup"><span data-stu-id="e3884-103">You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram.</span></span> <span data-ttu-id="e3884-104">Você pode adicionar tabelas de banco de dados existentes a um diagrama ou inserir uma tabela nova que ainda não foi definida no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e3884-104">You can either add existing database tables to a diagram or insert a new table that has not yet been defined in the database.</span></span>  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a><span data-ttu-id="e3884-105">Para inserir uma tabela nova em um diagrama</span><span class="sxs-lookup"><span data-stu-id="e3884-105">To insert a new table into a diagram</span></span>  
  
1.  <span data-ttu-id="e3884-106">Verifique se você está conectado ao banco de dados em que deseja criar a tabela.</span><span class="sxs-lookup"><span data-stu-id="e3884-106">Make sure you are connected to the database in which you want to create the table.</span></span>  
  
     <span data-ttu-id="e3884-107">Para criar uma tabela em seu diagrama atual, clique no botão **Nova Tabela** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e3884-107">To create a table in your current diagram, click the **New Table** button on the toolbar.</span></span>  
  
     <span data-ttu-id="e3884-108">-ou-</span><span class="sxs-lookup"><span data-stu-id="e3884-108">-or-</span></span>  
  
     <span data-ttu-id="e3884-109">Clique com o botão direito do mouse no diagrama e selecione **Nova Tabela**.</span><span class="sxs-lookup"><span data-stu-id="e3884-109">Right-click in the diagram and select **New Table**.</span></span>  
  
2.  <span data-ttu-id="e3884-110">Altere ou aceite o nome de tabela atribuído pelo sistema, na caixa de diálogo **Escolher Nome** e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3884-110">Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.</span></span>  
  
     <span data-ttu-id="e3884-111">Uma nova tabela será exibida no diagrama na exibição Padrão.</span><span class="sxs-lookup"><span data-stu-id="e3884-111">A new table appears in the diagram in Standard view.</span></span>  
  
3.  <span data-ttu-id="e3884-112">Na primeira célula da nova tabela, digite um nome de coluna.</span><span class="sxs-lookup"><span data-stu-id="e3884-112">In the first cell of the new table, type a column name.</span></span> <span data-ttu-id="e3884-113">Depois, pressione a tecla TAB para ir para a próxima célula.</span><span class="sxs-lookup"><span data-stu-id="e3884-113">Then press the TAB key to move to the next cell.</span></span>  
  
4.  <span data-ttu-id="e3884-114">Em **Tipo de Dados**, selecione um tipo de dados para a coluna.</span><span class="sxs-lookup"><span data-stu-id="e3884-114">Under **Data Type**, select a data type for the column.</span></span> <span data-ttu-id="e3884-115">Cada coluna deve ter um nome e um tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="e3884-115">Each column must have a name and data type.</span></span>  
  
     <span data-ttu-id="e3884-116">Você pode definir as outras propriedades da coluna no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="e3884-116">You can set the column's other properties in Table Designer.</span></span>  
  
5.  <span data-ttu-id="e3884-117">Repita as etapas 3 e 4 para cada coluna que deseja adicionar à tabela.</span><span class="sxs-lookup"><span data-stu-id="e3884-117">Repeat steps 3 and 4 for each column you want to add to the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3884-118">Quando você salvar o diagrama de banco de dados, a nova tabela será adicionada ao seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e3884-118">When you save your database diagram, the new table will be added to your database.</span></span>  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a><span data-ttu-id="e3884-119">Para adicionar uma tabela existente a um diagrama</span><span class="sxs-lookup"><span data-stu-id="e3884-119">To add an existing table to a diagram</span></span>  
  
1.  <span data-ttu-id="e3884-120">Verifique se você está conectado ao banco de dados cujas tabelas deseja editar.</span><span class="sxs-lookup"><span data-stu-id="e3884-120">Make sure you are connected to the database whose tables you want to edit.</span></span>  
  
2.  <span data-ttu-id="e3884-121">Selecione uma tabela na pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="e3884-121">Select a table in the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e3884-122">Arraste a tabela para seu diagrama de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e3884-122">Drag the table into your database diagram.</span></span>  
  
4.  <span data-ttu-id="e3884-123">Solte o botão do mouse.</span><span class="sxs-lookup"><span data-stu-id="e3884-123">Release the mouse button.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3884-124">Se existirem relações entre a tabela escolhida e as outras tabelas de seu diagrama, as linhas de relação serão desenhadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e3884-124">If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.</span></span>  
  
### <a name="to-add-related-tables-to-a-diagram"></a><span data-ttu-id="e3884-125">Para adicionar tabelas relacionadas a um diagrama</span><span class="sxs-lookup"><span data-stu-id="e3884-125">To add related tables to a diagram</span></span>  
  
1.  <span data-ttu-id="e3884-126">Selecione uma ou mais tabelas com restrições de chave estrangeira no diagrama de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e3884-126">Select one or more tables with foreign key constraints in the database diagram.</span></span>  
  
2.  <span data-ttu-id="e3884-127">Clique com o botão direito do mouse em qualquer tabela selecionada e escolha **Adicionar Tabelas Relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="e3884-127">Right-click any of the selected tables and choose **Add Related Tables**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3884-128">As duas tabelas referenciadas por uma restrição de chave estrangeira da tabela selecionada e aquelas que referenciam a tabela selecionada com uma restrição de chave estrangeira são adicionadas ao diagrama.</span><span class="sxs-lookup"><span data-stu-id="e3884-128">Both those tables referenced by a foreign key constraint from the selected table(s) and those referencing the selected table(s) with a foreign key constraint are added to the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3884-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3884-129">See Also</span></span>  
 <span data-ttu-id="e3884-130">[Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e3884-130">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e3884-131">Trabalhar com tabelas no diagrama de banco de dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3884-131">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
