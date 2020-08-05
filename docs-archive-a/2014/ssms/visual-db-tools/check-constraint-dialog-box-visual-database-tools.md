---
title: Caixa de diálogo Verificar Restrição (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7244984b869a1c68e597984a1cd03e16e53d0306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568296"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a><span data-ttu-id="b0dbe-102">Caixa de diálogo Verificar Restrição (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b0dbe-102">Check Constraint Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="b0dbe-103">Essa caixa de diálogo aparece quando você clica com o botão direito do mouse em uma grade de definição de tabela no Designer de Tabela e clica em **Verificar Restrições**.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-103">This dialog box appears when you right-click a table definition grid in Table Designer and click **Check Constraints**.</span></span> <span data-ttu-id="b0dbe-104">A caixa de diálogo contém um conjunto de propriedades para restrições não exclusivas anexadas às tabelas em seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-104">The dialog box contains a set of properties for non-unique constraints attached to the tables in your database.</span></span> <span data-ttu-id="b0dbe-105">As propriedades que se aplicam a restrições exclusivas aparecem na caixa de diálogo **Índices/Chaves** .</span><span class="sxs-lookup"><span data-stu-id="b0dbe-105">Properties applying to unique constraints appear in the **Indexes/Keys** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0dbe-106">Se a tabela for publicada para replicação, você precisará fazer alterações no esquema usando a instrução Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou o SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="b0dbe-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="b0dbe-107">Ao fazer alterações no esquema com o Criador de Tabelas ou com o Criador do Diagrama de Banco de Dados, ele tenta descartar e recriar a tabela.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="b0dbe-108">Não é possível descartar objetos publicados, portanto, haverá falha na alteração de esquema.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0dbe-109">Opções</span><span class="sxs-lookup"><span data-stu-id="b0dbe-109">Options</span></span>  
 <span data-ttu-id="b0dbe-110">**Restrições de Verificação Selecionadas**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-110">**Selected Check Constraints**</span></span>  
 <span data-ttu-id="b0dbe-111">Lista as restrições de verificação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-111">Lists available check constraints.</span></span> <span data-ttu-id="b0dbe-112">Para exibir as propriedades de uma restrição, selecione-a na lista.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-112">To view the properties of a constraint, select it in the list.</span></span>  
  
 <span data-ttu-id="b0dbe-113">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-113">**Add**</span></span>  
 <span data-ttu-id="b0dbe-114">Cria uma nova restrição para a tabela de banco de dados selecionada e fornece um nome padrão e outros valores para a restrição.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-114">Create a new constraint for the selected database table and provide a default name and other values for the constraint.</span></span> <span data-ttu-id="b0dbe-115">A restrição não será válida até que uma expressão é digitada para a restrição.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-115">The constraint will not become valid until an expression is entered for the constraint.</span></span>  
  
 <span data-ttu-id="b0dbe-116">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-116">**Delete**</span></span>  
 <span data-ttu-id="b0dbe-117">Remova a restrição selecionada da tabela.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-117">Remove the selected constraint from the table.</span></span> <span data-ttu-id="b0dbe-118">Para cancelar a adição de uma restrição de verificação, use esse botão para remover a restrição.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-118">To cancel the addition of a check constraint, use this button to remove the constraint.</span></span>  
  
 <span data-ttu-id="b0dbe-119">**Categoria Geral**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-119">**General Category**</span></span>  
 <span data-ttu-id="b0dbe-120">Expanda para mostrar o campo de propriedade **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="b0dbe-120">Expand to show the **Expression** property field.</span></span>  
  
 <span data-ttu-id="b0dbe-121">**Expression**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-121">**Expression**</span></span>  
 <span data-ttu-id="b0dbe-122">Exibe a expressão para a restrição de verificação selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-122">Displays the expression for the selected check constraint.</span></span> <span data-ttu-id="b0dbe-123">Para nova restrições, você deve digitar a expressão antes de sair dessa caixa.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-123">For new constraints, you must enter the expression before exiting this box.</span></span> <span data-ttu-id="b0dbe-124">Você também pode editar restrições de verificação existentes.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-124">You can also edit existing check constraints.</span></span> <span data-ttu-id="b0dbe-125">Para obter mais informações, consulte [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="b0dbe-125">For more information, see [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="b0dbe-126">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-126">**Identity Category**</span></span>  
 <span data-ttu-id="b0dbe-127">Expanda para mostrar propriedades para **Nome** e **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-127">Expand to show properties for **Name** and **Description**.</span></span>  
  
 <span data-ttu-id="b0dbe-128">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-128">**Name**</span></span>  
 <span data-ttu-id="b0dbe-129">Mostra o nome da restrição de verificação selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-129">Shows the name of the selected check constraint.</span></span> <span data-ttu-id="b0dbe-130">Para alterar o nome dessa restrição, digite o texto diretamente no campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-130">To change the name of this constraint, type the text directly in the property field.</span></span>  
  
 <span data-ttu-id="b0dbe-131">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-131">**Description**</span></span>  
 <span data-ttu-id="b0dbe-132">Descrevendo a restrição de verificação.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-132">Describing this check constraint.</span></span> <span data-ttu-id="b0dbe-133">Você pode editar a descrição digitando no campo de propriedade ou clicar no botão de reticências ( **…** ), que aparece à direita do campo de propriedade, bem como editar a descrição na caixa de diálogo **Propriedade de Descrição**.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-133">You can edit the description by typing into the property field or you can click the ellipsis button (**...**) that appears to the right of the property field and edit the description in the **Description Property** dialog box.</span></span>  
  
 <span data-ttu-id="b0dbe-134">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-134">**Table Designer Category**</span></span>  
 <span data-ttu-id="b0dbe-135">Expanda para mostrar as propriedades de **Verificar Dados Existentes ao Criar ou Habilitar Novamente**, **Impor para Inserir e Atualizar**e **Impor Replicação**.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-135">Expand to show properties for **Check Existing Data on Creation or Re-enabling**, **Enforce For Inserts And Updates**, and **Enforce Replication**.</span></span>  
  
 <span data-ttu-id="b0dbe-136">**Check Existing Data On Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-136">**Check Existing Data On Creation or Re-Enabling**</span></span>  
 <span data-ttu-id="b0dbe-137">Especifica se todos os dados preexistentes (dados existentes na tabela antes de a restrição ser criada) são verificados em relação à restrição.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-137">Specify whether all pre-existing data (data existing in the table before the constraint is created) is verified against the constraint.</span></span>  
  
 <span data-ttu-id="b0dbe-138">**Impor para Inserir e Atualizar**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-138">**Enforce For Inserts And Updates**</span></span>  
 <span data-ttu-id="b0dbe-139">Especifica se a restrição é imposta quando os dados são inseridos ou atualizados na tabela.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-139">Specify whether the constraint is enforced when data is inserted into or updated in the table.</span></span>  
  
 <span data-ttu-id="b0dbe-140">**Impor para Replicação**</span><span class="sxs-lookup"><span data-stu-id="b0dbe-140">**Enforce For Replication**</span></span>  
 <span data-ttu-id="b0dbe-141">Indica se é para impor a restrição quando um agente de replicação executar uma inserção ou atualização nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="b0dbe-141">Indicates whether to enforce the constraint when a replication agent performs an insert or update on this table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0dbe-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0dbe-142">See Also</span></span>  
 <span data-ttu-id="b0dbe-143">[Restrições exclusivas e restrições de verificação](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="b0dbe-143">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="b0dbe-144">Caixa de diálogo índices e chaves &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b0dbe-144">Indexes and Keys Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
