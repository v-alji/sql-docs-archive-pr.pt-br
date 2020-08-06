---
title: Caixa de diálogo Adicionar tabela (designers de consulta e exibição) (ferramentas de banco de dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.query.addtable
- vdtsql.chm:65565
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d7bf30cbdd37927735c36f184208a1ded957763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571758"
---
# <a name="add-table-dialog-box-query-and-view-designers-visual-database-tools"></a><span data-ttu-id="9eeb9-102">Caixa de diálogo Adicionar Tabela (Designers de Consulta e Exibição) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9eeb9-102">Add Table Dialog Box (Query and View Designers) (Visual Database Tools)</span></span>
  <span data-ttu-id="9eeb9-103">Essa caixa de diálogo permite que você adicione tabelas, exibições, funções definidas pelo usuário ou sinônimos a uma consulta ou exibição.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-103">This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9eeb9-104">Se a tabela for publicada para replicação, você precisará fazer alterações no esquema usando a instrução Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou o SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9eeb9-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="9eeb9-105">Ao fazer alterações no esquema com o Criador de Tabelas ou com o Criador do Diagrama de Banco de Dados, ele tenta descartar e recriar a tabela.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="9eeb9-106">Não é possível descartar objetos publicados, portanto, haverá falha na alteração de esquema.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9eeb9-107">Opções</span><span class="sxs-lookup"><span data-stu-id="9eeb9-107">Options</span></span>  
 <span data-ttu-id="9eeb9-108">**Tabelas**</span><span class="sxs-lookup"><span data-stu-id="9eeb9-108">**Tables**</span></span>  
 <span data-ttu-id="9eeb9-109">Lista as tabelas que você pode adicionar ao painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="9eeb9-109">Lists the tables you can add to the **Diagram** pane.</span></span> <span data-ttu-id="9eeb9-110">Para adicionar uma tabela, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-110">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="9eeb9-111">Para adicionar várias tabelas de uma vez, selecione-as e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-111">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="9eeb9-112">**Exibições**</span><span class="sxs-lookup"><span data-stu-id="9eeb9-112">**Views**</span></span>  
 <span data-ttu-id="9eeb9-113">Lista os modos de exibição que você pode adicionar ao painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="9eeb9-113">Lists the views you can add to the **Diagram** pane.</span></span> <span data-ttu-id="9eeb9-114">Para adicionar um modo de exibição, selecione-o e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-114">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="9eeb9-115">Para adicionar vários modos de exibição de uma vez, selecione-os e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-115">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="9eeb9-116">**Funções**</span><span class="sxs-lookup"><span data-stu-id="9eeb9-116">**Functions**</span></span>  
 <span data-ttu-id="9eeb9-117">Lista as funções definidas pelo usuário que você pode adicionar ao painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="9eeb9-117">Lists the user-defined functions you can add to the **Diagram** pane.</span></span> <span data-ttu-id="9eeb9-118">Para adicionar uma função, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-118">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="9eeb9-119">Para adicionar várias funções de uma vez, selecione-as em clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-119">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="9eeb9-120">**Sinônimos**</span><span class="sxs-lookup"><span data-stu-id="9eeb9-120">**Synonyms**</span></span>  
 <span data-ttu-id="9eeb9-121">Lista os sinônimos que você pode adicionar ao painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="9eeb9-121">Lists the synonyms you can add to the **Diagram** pane.</span></span> <span data-ttu-id="9eeb9-122">Para adicionar um sinônimo, selecione-o e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-122">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="9eeb9-123">Para adicionar vários sinônimos de uma vez, selecione-os em clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-123">To add several synonyms at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="9eeb9-124">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="9eeb9-124">**Refresh**</span></span>  
 <span data-ttu-id="9eeb9-125">Atualiza a lista para incluir qualquer alteração feita ao banco de dados desde que a lista foi recuperada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-125">Update the list to include any changes made to the database since the list was last retrieved.</span></span>  
  
 <span data-ttu-id="9eeb9-126">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="9eeb9-126">**Add**</span></span>  
 <span data-ttu-id="9eeb9-127">Adiciona o item ou itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="9eeb9-127">Add the selected item or items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eeb9-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9eeb9-128">See Also</span></span>  
 [<span data-ttu-id="9eeb9-129">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9eeb9-129">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
