---
title: Questões do Database Evolution (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80daa694cd015a83657368902b07da254e6196ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684974"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a><span data-ttu-id="c2723-102">Questões do Database Evolution (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c2723-102">Issues of Database Evolution (Visual Database Tools)</span></span>
  <span data-ttu-id="c2723-103">Se você alterar a estrutura de um banco de dados implantado, tenha atenção especial para que sua alteração seja compatível com os dados e a estrutura de banco de dados existentes.</span><span class="sxs-lookup"><span data-stu-id="c2723-103">If you change the structure of a deployed database, you must take special care that your alteration is compatible with the existing data and database structure.</span></span> <span data-ttu-id="c2723-104">Você pode precisar executar etapas especiais ao fazer as seguintes modificações:</span><span class="sxs-lookup"><span data-stu-id="c2723-104">You might need to take special steps when you make the following modifications:</span></span>  
  
-   <span data-ttu-id="c2723-105">**Adicionar uma Restrição** Se você adicionar uma restrição, o banco de dados poderá já conter dados que não atendem às exigências.</span><span class="sxs-lookup"><span data-stu-id="c2723-105">**Adding a Constraint** If you add a constraint, the database might already contain data that does not satisfy it.</span></span> <span data-ttu-id="c2723-106">Quando você tentar salvar a nova restrição, a [Caixa de diálogo Notificações Pós-salvamento &#40;Visual Database Tools&#41;](visual-database-tools.md) o informará que o servidor de banco de dados não pode criar a restrição.</span><span class="sxs-lookup"><span data-stu-id="c2723-106">When you try to save the new constraint, the [Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not create the constraint.</span></span> <span data-ttu-id="c2723-107">Para forçar o banco de dados a aceitar a nova restrição, você pode desmarcar a caixa de seleção **Verificar dados existentes na criação**.</span><span class="sxs-lookup"><span data-stu-id="c2723-107">To force the database to accept the new constraint, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="c2723-108">**Adicionar uma Relação** Se você adicionar uma relação, o banco de dados poderá já conter linhas da tabela de chave estrangeira que não têm linhas correspondentes na tabela de chave primária.</span><span class="sxs-lookup"><span data-stu-id="c2723-108">**Adding a Relationship** If you add a relationship, the database might already contain rows of the foreign-key table that do not have corresponding rows in the primary-key table.</span></span> <span data-ttu-id="c2723-109">Isto é, os dados existentes podem não satisfazer a integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="c2723-109">That is, the existing data might not satisfy referential integrity.</span></span> <span data-ttu-id="c2723-110">Quando você tentar salvar a nova relação, a [Caixa de diálogo Notificações Pós-salvamento &#40;Visual Database Tools&#41;](visual-database-tools.md) o informará que o servidor de banco de dados não pode salvar a tabela de chave estrangeira revisada.</span><span class="sxs-lookup"><span data-stu-id="c2723-110">When you try to save the new relationship, the[Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not save the revised foreign-key table.</span></span> <span data-ttu-id="c2723-111">Para forçar o banco de dados a aceitar a modificação, você pode desmarcar a caixa de seleção **Verificar dados existentes na criação**.</span><span class="sxs-lookup"><span data-stu-id="c2723-111">To force the database to accept the modification, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="c2723-112">**Modificar uma Tabela que Contribui para uma Exibição Indexada** Se você modificar uma tabela que contribui para uma exibição indexada do Microsoft SQL Server, os índices serão perdidos na exibição.</span><span class="sxs-lookup"><span data-stu-id="c2723-112">**Modifying a Table Contributing to an Indexed View** If you modify a table that contributes to a Microsoft SQL Server indexed view, the indexes on the view will be lost.</span></span> <span data-ttu-id="c2723-113">Consulte os Manuais Online do SQL Server para obter informações sobre como recriar índices.</span><span class="sxs-lookup"><span data-stu-id="c2723-113">See the SQL Server Books Online for information on recreating indexes.</span></span>  
  
-   <span data-ttu-id="c2723-114">**Excluir um Objeto** Se você excluir um objeto, como uma coluna, tabela ou exibição, verifique primeiro se o objeto não representa uma referência para outro objeto no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c2723-114">**Deleting an Object** If you delete an object, such as a column, table, or view, check first to be sure that the object is not referenced by another object in the database.</span></span>  
  
 <span data-ttu-id="c2723-115">Você deve manter um histórico das alterações independentemente de como o design do banco de dados é alterado.</span><span class="sxs-lookup"><span data-stu-id="c2723-115">No matter how you alter the database design, you should retain a history of the alterations.</span></span> <span data-ttu-id="c2723-116">Uma opção é manter os scripts SQL de todas as modificações que você já fez em seu banco de dados de produção.</span><span class="sxs-lookup"><span data-stu-id="c2723-116">One approach is to retain SQL scripts for all modifications that you ever make to your production database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2723-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2723-117">See Also</span></span>  
 <span data-ttu-id="c2723-118">[Restrições exclusivas e restrições de verificação](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="c2723-118">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="c2723-119">Ambientes multiusuários &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c2723-119">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
