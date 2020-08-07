---
title: Caixa de diálogo Atualizar Tabela (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.updatetable
- vdtsql.chm:69643
ms.assetid: 174c7275-5b15-42a9-b172-5ff30de575a1
author: stevestein
ms.author: sstein
ms.openlocfilehash: 426c842b85d6404ba101b57a9b572107dbc76bb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575493"
---
# <a name="update-table-dialog-box-visual-database-tools"></a><span data-ttu-id="d3167-102">Caixa de diálogo Atualizar Tabela (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d3167-102">Update Table Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="d3167-103">Essa caixa de diálogo lhe permite especificar a tabela a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="d3167-103">This dialog box allows you to specify the table to be updated.</span></span>  
  
 <span data-ttu-id="d3167-104">Essa caixa de diálogo aparece se mais de uma tabela forem exibidas no painel Diagrama quando o tipo de consulta é mudado para consulta Update.</span><span class="sxs-lookup"><span data-stu-id="d3167-104">This dialog box appears if more than one table is displayed in the Diagram pane when you change a query's type to be an Update query.</span></span>  
  
 <span data-ttu-id="d3167-105">Selecione a tabela a ser atualizada e escolha **OK**. </span><span class="sxs-lookup"><span data-stu-id="d3167-105">Select the table to update, and then choose **OK**.</span></span>\  
  
> [!NOTE]  
>  <span data-ttu-id="d3167-106">Se a tabela for publicada para replicação, você precisará fazer alterações no esquema usando a instrução Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou o SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="d3167-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="d3167-107">Ao fazer alterações no esquema com o Criador de Tabelas ou com o Criador do Diagrama de Banco de Dados, ele tenta descartar e recriar a tabela.</span><span class="sxs-lookup"><span data-stu-id="d3167-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="d3167-108">Não é possível descartar objetos publicados, portanto, haverá falha na alteração de esquema.</span><span class="sxs-lookup"><span data-stu-id="d3167-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3167-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3167-109">See Also</span></span>  
 [<span data-ttu-id="d3167-110">Criar consultas Atualização &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d3167-110">Create Update Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
