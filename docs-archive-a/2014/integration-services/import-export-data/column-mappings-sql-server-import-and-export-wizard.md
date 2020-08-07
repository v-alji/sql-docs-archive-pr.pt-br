---
title: Mapeamentos de coluna (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.columnmapandtransform.f1
ms.assetid: eadc54a6-f936-4ffc-91d7-fbfd2bdcab93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7994de1292677421447d441c1ac5aeb2b6fbc618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575943"
---
# <a name="column-mappings-sql-server-import-and-export-wizard"></a><span data-ttu-id="51ab7-102">Mapeamentos de coluna (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="51ab7-102">Column Mappings (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="51ab7-103">Use a caixa de diálogo **mapeamentos de coluna** para editar parâmetros de transformação.</span><span class="sxs-lookup"><span data-stu-id="51ab7-103">Use the **Column Mappings** dialog box to edit transformation parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51ab7-104">Não é necessário copiar todas as colunas em uma tabela ao selecionar a opção Cópia de Tabela.</span><span class="sxs-lookup"><span data-stu-id="51ab7-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="51ab7-105">Selecione **\<ignore>** na coluna **destino** desta caixa de diálogo para as colunas que você deseja ignorar.</span><span class="sxs-lookup"><span data-stu-id="51ab7-105">Select **\<ignore>** in the **Destination** column of this dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="51ab7-106">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="51ab7-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="51ab7-107">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="51ab7-107">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="51ab7-108">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="51ab7-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="51ab7-109">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="51ab7-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="51ab7-110">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="51ab7-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="51ab7-111">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="51ab7-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="51ab7-112">Opções</span><span class="sxs-lookup"><span data-stu-id="51ab7-112">Options</span></span>  
 <span data-ttu-id="51ab7-113">**Origem**</span><span class="sxs-lookup"><span data-stu-id="51ab7-113">**Source**</span></span>  
 <span data-ttu-id="51ab7-114">Identifica a tabela, exibição ou consulta de origem selecionada.</span><span class="sxs-lookup"><span data-stu-id="51ab7-114">Identifies the selected source table, view, or query.</span></span>  
  
 <span data-ttu-id="51ab7-115">**Destino**</span><span class="sxs-lookup"><span data-stu-id="51ab7-115">**Destination**</span></span>  
 <span data-ttu-id="51ab7-116">Identifica a tabela, exibição ou consulta de destino selecionada.</span><span class="sxs-lookup"><span data-stu-id="51ab7-116">Identifies the selected destination table, view, or query.</span></span>  
  
 <span data-ttu-id="51ab7-117">**Criar tabela/arquivo de destino**</span><span class="sxs-lookup"><span data-stu-id="51ab7-117">**Create destination table/file**</span></span>  
 <span data-ttu-id="51ab7-118">Especifique se deseja criar a tabela de destino, se ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="51ab7-118">Specify whether to create the destination table if it does not already exist.</span></span>  
  
 <span data-ttu-id="51ab7-119">**Excluir linhas na tabela/arquivo de destino**</span><span class="sxs-lookup"><span data-stu-id="51ab7-119">**Delete rows in destination table/file**</span></span>  
 <span data-ttu-id="51ab7-120">Especifique se deseja limpar os dados de uma tabela existente antes de carregar dados novos.</span><span class="sxs-lookup"><span data-stu-id="51ab7-120">Specify whether to clear the data from an existing table before loading new data.</span></span>  
  
 <span data-ttu-id="51ab7-121">**Acrescentar linhas à tabela/arquivo de destino**</span><span class="sxs-lookup"><span data-stu-id="51ab7-121">**Append rows to destination table/file**</span></span>  
 <span data-ttu-id="51ab7-122">Especifique se deseja acrescentar os dados novos aos dados já presentes em uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="51ab7-122">Specify whether to append the new data to the data already present in an existing table.</span></span>  
  
 <span data-ttu-id="51ab7-123">**Editar SQL**</span><span class="sxs-lookup"><span data-stu-id="51ab7-123">**Edit SQL**</span></span>  
 <span data-ttu-id="51ab7-124">Use a instrução padrão na caixa de diálogo **instrução SQL CREATE TABLE** ou modifique-a para suas finalidades.</span><span class="sxs-lookup"><span data-stu-id="51ab7-124">Use the default statement in the **Create Table SQL Statement** dialog box, or modify it for your purposes.</span></span> <span data-ttu-id="51ab7-125">Se essa instrução for modificada, também será necessário fazer alterações associadas no mapeamento de tabela.</span><span class="sxs-lookup"><span data-stu-id="51ab7-125">If you modify this statement, you must also make associated changes to table mapping.</span></span>  
  
 <span data-ttu-id="51ab7-126">**Ignorar e recriar tabela de destino**</span><span class="sxs-lookup"><span data-stu-id="51ab7-126">**Drop and re-create destination table**</span></span>  
 <span data-ttu-id="51ab7-127">Escolha esta opção para substituir a tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="51ab7-127">Choose this option to overwrite the destination table.</span></span> <span data-ttu-id="51ab7-128">Esta opção só está disponível ao usar o assistente para criar a tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="51ab7-128">This option is only available when you use the wizard to create the destination table.</span></span> <span data-ttu-id="51ab7-129">A tabela de destino é ignorada e recriada somente se o pacote criado pelo assistente for salvo e o pacote for executado novamente.</span><span class="sxs-lookup"><span data-stu-id="51ab7-129">The destination table is only dropped and re-created if you save the package that the wizard creates, and then run the package again.</span></span>  
  
 <span data-ttu-id="51ab7-130">**Habilitar inserção de identidade**</span><span class="sxs-lookup"><span data-stu-id="51ab7-130">**Enable identity insert**</span></span>  
 <span data-ttu-id="51ab7-131">Escolha esta opção para permitir que valores de identidade existentes nos dados de origem sejam inseridos em uma coluna de identidade na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="51ab7-131">Choose this option to allow existing identity values in the source data to be inserted into an identity column in the destination table.</span></span> <span data-ttu-id="51ab7-132">Por padrão, a coluna de identidade de destino não permite isto.</span><span class="sxs-lookup"><span data-stu-id="51ab7-132">By default, the destination identity column does not allow this.</span></span>  
  
 <span data-ttu-id="51ab7-133">**Mapeamentos**</span><span class="sxs-lookup"><span data-stu-id="51ab7-133">**Mappings**</span></span>  
 <span data-ttu-id="51ab7-134">Exibe como cada coluna na fonte de dados mapeia para uma coluna no destino.</span><span class="sxs-lookup"><span data-stu-id="51ab7-134">Displays how each column in the data source maps to a column in the destination.</span></span>  
  
 <span data-ttu-id="51ab7-135">Esta lista tem as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="51ab7-135">This list has the following columns:</span></span>  
  
 <span data-ttu-id="51ab7-136">**Origem**</span><span class="sxs-lookup"><span data-stu-id="51ab7-136">**Source**</span></span>  
 <span data-ttu-id="51ab7-137">Exiba cada coluna de origem para a qual é possível definir parâmetros de transformação.</span><span class="sxs-lookup"><span data-stu-id="51ab7-137">View each source column for which you can set transformation parameters.</span></span>  
  
 <span data-ttu-id="51ab7-138">**Destino**</span><span class="sxs-lookup"><span data-stu-id="51ab7-138">**Destination**</span></span>  
 <span data-ttu-id="51ab7-139">Especifique se você deseja ignorar uma coluna durante a operação de cópia.</span><span class="sxs-lookup"><span data-stu-id="51ab7-139">Specify whether you want to ignore a column during the copy operation.</span></span> <span data-ttu-id="51ab7-140">Você pode copiar apenas um subconjunto de colunas selecionando **\<ignore>** nesta coluna as colunas que deseja ignorar.</span><span class="sxs-lookup"><span data-stu-id="51ab7-140">You can copy only a subset of columns by selecting **\<ignore>** in this column for columns that you want to skip.</span></span> <span data-ttu-id="51ab7-141">Antes de mapear colunas, é necessário ignorar todas as colunas que não serão mapeadas.</span><span class="sxs-lookup"><span data-stu-id="51ab7-141">Before you map columns, you must ignore all columns that will not be mapped.</span></span>  
  
 <span data-ttu-id="51ab7-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="51ab7-142">**Type**</span></span>  
 <span data-ttu-id="51ab7-143">Selecione um tipo de dados para a coluna.</span><span class="sxs-lookup"><span data-stu-id="51ab7-143">Select a data type for the column.</span></span>  
  
 <span data-ttu-id="51ab7-144">**Permite valor nulo**</span><span class="sxs-lookup"><span data-stu-id="51ab7-144">**Nullable**</span></span>  
 <span data-ttu-id="51ab7-145">Especifique se uma coluna permitirá um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="51ab7-145">Specify whether a column will allow a null value.</span></span>  
  
 <span data-ttu-id="51ab7-146">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="51ab7-146">**Size**</span></span>  
 <span data-ttu-id="51ab7-147">Especifique o número de caracteres na coluna.</span><span class="sxs-lookup"><span data-stu-id="51ab7-147">Specify the number of characters in the column.</span></span>  
  
 <span data-ttu-id="51ab7-148">**Precisão**</span><span class="sxs-lookup"><span data-stu-id="51ab7-148">**Precision**</span></span>  
 <span data-ttu-id="51ab7-149">Especifique a precisão de dados exibidos, com relação ao número de dígitos.</span><span class="sxs-lookup"><span data-stu-id="51ab7-149">Specify the precision of displayed data, referring to the number of digits.</span></span>  
  
 <span data-ttu-id="51ab7-150">**Escala**</span><span class="sxs-lookup"><span data-stu-id="51ab7-150">**Scale**</span></span>  
 <span data-ttu-id="51ab7-151">Especifique a escala de dados exibidos, com relação ao número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="51ab7-151">Specify the scale of displayed data, referring to the number of decimal places.</span></span>  
  
  
