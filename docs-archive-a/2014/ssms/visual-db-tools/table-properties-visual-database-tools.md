---
title: Propriedades da tabela (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.tabledesigner
- vdt.designers.properties.Table
ms.assetid: cc392987-1aab-45f5-b5af-a26be53409bf
author: stevestein
ms.author: sstein
ms.openlocfilehash: df4a0332ebc622b069c468e51c461b7cba20aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683270"
---
# <a name="table-properties-visual-database-tools"></a><span data-ttu-id="9be26-102">Propriedades da tabela (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9be26-102">Table Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="9be26-103">Essas propriedades aparecem na janela Propriedades quando você clicar em Designer de Tabela com o botão direito do mouse e selecionar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="9be26-103">These properties appear in the Properties window when you right click in Table Designer and select Properties.</span></span> <span data-ttu-id="9be26-104">A menos que seja indicado o contrário, é possível editar essas propriedades na janela Propriedades quando a tabela for selecionada.</span><span class="sxs-lookup"><span data-stu-id="9be26-104">Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9be26-105">Se a tabela for publicada para replicação, você precisará fazer alterações no esquema usando a instrução Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou o SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9be26-105">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="9be26-106">Ao fazer alterações no esquema com o Criador de Tabelas ou com o Criador do Diagrama de Banco de Dados, ele tenta descartar e recriar a tabela.</span><span class="sxs-lookup"><span data-stu-id="9be26-106">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="9be26-107">Não é possível descartar objetos publicados, portanto, haverá falha na alteração de esquema.</span><span class="sxs-lookup"><span data-stu-id="9be26-107">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="show-table-properties-in-table-designer"></a><span data-ttu-id="9be26-108">Mostrar propriedades da tabela no Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="9be26-108">Show Table Properties in Table Designer</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9be26-109">As propriedades desse tópico são classificadas por categoria e não em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="9be26-109">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
 <span data-ttu-id="9be26-110">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="9be26-110">**Identity Category**</span></span>  
 <span data-ttu-id="9be26-111">Expande para mostrar propriedades para **Nome**, **Descrição**e **Esquema**.</span><span class="sxs-lookup"><span data-stu-id="9be26-111">Expands to show properties for **Name**, **Description**, and **Schema**.</span></span>  
  
 <span data-ttu-id="9be26-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9be26-112">**Name**</span></span>  
 <span data-ttu-id="9be26-113">Exibe o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="9be26-113">Displays the name of the table.</span></span> <span data-ttu-id="9be26-114">Para editar o nome, digite-o na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="9be26-114">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9be26-115">Se as consultas, exibições, funções definidas pelo usuário, procedimentos armazenados ou programas existentes se referirem à tabela, a modificação do nome tornará esses objetivos inválidos.</span><span class="sxs-lookup"><span data-stu-id="9be26-115">If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="9be26-116">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="9be26-116">**Database Name**</span></span>  
 <span data-ttu-id="9be26-117">Mostra o nome da fonte dos dados para a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="9be26-117">Shows the name of the data source of the selected table.</span></span>  
  
 <span data-ttu-id="9be26-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9be26-118">**Description**</span></span>  
 <span data-ttu-id="9be26-119">Mostra uma descrição da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="9be26-119">Shows a description of the selected table.</span></span> <span data-ttu-id="9be26-120">Para ver a descrição inteira ou editá-la, clique nela e, em seguida, clique nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="9be26-120">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="9be26-121">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="9be26-121">**Schema**</span></span>  
 <span data-ttu-id="9be26-122">Mostra o nome do esquema ao qual essa tabela pertence.</span><span class="sxs-lookup"><span data-stu-id="9be26-122">Shows the name of the schema to which this table belongs.</span></span> <span data-ttu-id="9be26-123">(Aplica-se somente ao Microsoft SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9be26-123">(Applies only to Microsoft SQL Server.)</span></span>  
  
 <span data-ttu-id="9be26-124">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="9be26-124">**Server Name**</span></span>  
 <span data-ttu-id="9be26-125">Mostra o nome do servidor para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9be26-125">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="9be26-126">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="9be26-126">**Table Designer Category**</span></span>  
 <span data-ttu-id="9be26-127">Expande para mostrar propriedades para **Coluna de identidade**, **Indexável**e **É Replicado**.</span><span class="sxs-lookup"><span data-stu-id="9be26-127">Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.</span></span>  
  
 <span data-ttu-id="9be26-128">**Coluna de identidade**</span><span class="sxs-lookup"><span data-stu-id="9be26-128">**Identity Column**</span></span>  
 <span data-ttu-id="9be26-129">Mostra a coluna usada como a coluna de identidade da tabela.</span><span class="sxs-lookup"><span data-stu-id="9be26-129">Shows the column used as the table's identity column.</span></span> <span data-ttu-id="9be26-130">Para alterar a coluna de identidade, escolha a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9be26-130">To change the identity column, choose from the drop-down list.</span></span> <span data-ttu-id="9be26-131">Apenas colunas de um tipo de dados numérico serão exibidas na lista.</span><span class="sxs-lookup"><span data-stu-id="9be26-131">Only columns of a numeric data type will show in the list.</span></span>  
  
 <span data-ttu-id="9be26-132">**É Indexável**</span><span class="sxs-lookup"><span data-stu-id="9be26-132">**Is Indexable**</span></span>  
 <span data-ttu-id="9be26-133">Mostra se a tabela pode ser indexada.</span><span class="sxs-lookup"><span data-stu-id="9be26-133">Shows whether the table can be indexed.</span></span> <span data-ttu-id="9be26-134">Se a tabela não for indexável pode ser porque você não é o proprietário da tabela ou porque a tabela contém colunas com tipos de dados de texto, ntext ou imagem.</span><span class="sxs-lookup"><span data-stu-id="9be26-134">If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.</span></span>  
  
 <span data-ttu-id="9be26-135">**É Replicável**</span><span class="sxs-lookup"><span data-stu-id="9be26-135">**Is Replicated**</span></span>  
 <span data-ttu-id="9be26-136">Mostra se a tabela é replicada em outro local.</span><span class="sxs-lookup"><span data-stu-id="9be26-136">Shows whether the table is replicated in another location.</span></span>  
  
 <span data-ttu-id="9be26-137">**Categoria de especificação espaço de dados regular**</span><span class="sxs-lookup"><span data-stu-id="9be26-137">**Regular Data Space Specification Category**</span></span>  
 <span data-ttu-id="9be26-138">Expande para mostrar propriedades para **(Tipo de Espaço de Dados)** , **Grupo de Arquivos ou Nome do Esquema de Partição**e **Lista de Colunas de Partição**.</span><span class="sxs-lookup"><span data-stu-id="9be26-138">Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.</span></span>  
  
 <span data-ttu-id="9be26-139">**(Tipo de Espaço de Dados)**</span><span class="sxs-lookup"><span data-stu-id="9be26-139">**(Data Space Type)**</span></span>  
 <span data-ttu-id="9be26-140">Mostra se essa tabela é armazenada usando um grupo de arquivos ou esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="9be26-140">Shows whether this table is stored using a filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="9be26-141">**Grupo de arquivos ou Nome de esquema de partição**</span><span class="sxs-lookup"><span data-stu-id="9be26-141">**Filegroup or Partition Scheme Name**</span></span>  
 <span data-ttu-id="9be26-142">Mostra o nome do grupo de arquivos ou esquema de partição.</span><span class="sxs-lookup"><span data-stu-id="9be26-142">Shows the name of the filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="9be26-143">**Lista de Colunas da Partição**</span><span class="sxs-lookup"><span data-stu-id="9be26-143">**Partition Column List**</span></span>  
 <span data-ttu-id="9be26-144">Fornece acesso à caixa de diálogo **Lista de Colunas de Partição** .</span><span class="sxs-lookup"><span data-stu-id="9be26-144">Provides access to the **Partition Column List** dialog box.</span></span>  
  
 <span data-ttu-id="9be26-145">**Coluna GUID de Linha**</span><span class="sxs-lookup"><span data-stu-id="9be26-145">**Row GUID Column**</span></span>  
 <span data-ttu-id="9be26-146">Mostra a coluna usada pelo Microsoft SQL Server como a coluna ROWGUID da tabela.</span><span class="sxs-lookup"><span data-stu-id="9be26-146">Shows the column used by Microsoft SQL Server as the table's ROWGUID column.</span></span> <span data-ttu-id="9be26-147">Para alterar a coluna ROWGUID , escolha a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9be26-147">To change the ROWGUID column, choose from the drop-down list.</span></span> <span data-ttu-id="9be26-148">(Aplica-se apenas ao SQL Server 7.0 ou superior.)</span><span class="sxs-lookup"><span data-stu-id="9be26-148">(Applies only to SQL Server 7.0 or higher.)</span></span>  
  
 <span data-ttu-id="9be26-149">**Grupo de arquivos de Texto/Imagem**</span><span class="sxs-lookup"><span data-stu-id="9be26-149">**Text/Image Filegroup**</span></span>  
 <span data-ttu-id="9be26-150">Fornece uma lista suspensa da qual você pode escolher o grupo de arquivos para colunas que têm tipos de dados de texto ou de imagem.</span><span class="sxs-lookup"><span data-stu-id="9be26-150">Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types.</span></span> <span data-ttu-id="9be26-151">Se a tabela é armazenada usando-se um esquema de partição, deixe esse espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="9be26-151">If the table is stored using a partition scheme, leave this field blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be26-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9be26-152">See Also</span></span>  
 [<span data-ttu-id="9be26-153">Criar tabelas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9be26-153">Design Tables &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
