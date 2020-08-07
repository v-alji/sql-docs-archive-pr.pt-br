---
title: Caixa de diálogo Índices XML (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.xmlindexes
ms.assetid: eef38310-4498-4ccc-bb77-5bbd1c7cc477
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1fb23a801a9129611c032fa1d659caf624088aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575491"
---
# <a name="xml-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="83230-102">Caixa de diálogo Índices XML (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="83230-102">XML Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="83230-103">Use a caixa de diálogo **Índices XML** para criar índices para colunas do tipo de dados XML, que não podem ser indexadas utilizando a caixa de diálogo **Índice/Chaves** .</span><span class="sxs-lookup"><span data-stu-id="83230-103">Use the **XML Indexes** dialog box to create indexes for columns of the data type XML, which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="83230-104">Cada coluna XML pode ter mais de um índice XML, mas o primeiro a ser criado (primário) será a base para os demais (secundários).</span><span class="sxs-lookup"><span data-stu-id="83230-104">Each XML column can have more than one XML Index, but the first one created (primary) will be the basis of the others (secondary).</span></span> <span data-ttu-id="83230-105">Se você excluir o índice XML primário, os índices secundários também serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="83230-105">If you delete the primary XML index, the secondary indexes will also be deleted.</span></span>  
  
## <a name="options"></a><span data-ttu-id="83230-106">Opções</span><span class="sxs-lookup"><span data-stu-id="83230-106">Options</span></span>  
 <span data-ttu-id="83230-107">**Índice XML selecionado**</span><span class="sxs-lookup"><span data-stu-id="83230-107">**Selected XML Index**</span></span>  
 <span data-ttu-id="83230-108">Lista os índices XML existentes.</span><span class="sxs-lookup"><span data-stu-id="83230-108">Lists existing XML indexes.</span></span> <span data-ttu-id="83230-109">Selecione para exibir suas propriedades na grade à direita.</span><span class="sxs-lookup"><span data-stu-id="83230-109">Select to show its properties in the grid to the right.</span></span> <span data-ttu-id="83230-110">Se a lista estiver vazia, nenhum terá sido definido para a tabela.</span><span class="sxs-lookup"><span data-stu-id="83230-110">If the list is empty, none have been defined for the table.</span></span>  
  
 <span data-ttu-id="83230-111">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="83230-111">**Add**</span></span>  
 <span data-ttu-id="83230-112">Cria um índice XML novo.</span><span class="sxs-lookup"><span data-stu-id="83230-112">Create a new XML index.</span></span>  
  
 <span data-ttu-id="83230-113">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="83230-113">**Delete**</span></span>  
 <span data-ttu-id="83230-114">Exclui um índice XML selecionado na lista **Índice XML selecionado** .</span><span class="sxs-lookup"><span data-stu-id="83230-114">Delete XML index selected in the **Selected XML Index** list.</span></span> <span data-ttu-id="83230-115">Se você excluir o índice XML primário, você será notificado que isso também excluirá todos os índices secundários e você pode continuar ou cancelar a ação.</span><span class="sxs-lookup"><span data-stu-id="83230-115">If you delete the primary XML index, you will be notified that this will delete all secondary ones as well, and you can either continue or cancel the action.</span></span>  
  
 <span data-ttu-id="83230-116">**Categoria Geral**</span><span class="sxs-lookup"><span data-stu-id="83230-116">**General Category**</span></span>  
 <span data-ttu-id="83230-117">Quando expandida, mostra os campos de propriedade para **Colunas**, **É primário**e **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="83230-117">When expanded, shows the property fields for **Columns**, **Is Primary**, and **Type**.</span></span>  
  
 <span data-ttu-id="83230-118">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="83230-118">**Columns**</span></span>  
 <span data-ttu-id="83230-119">Mostra que esse índice é classificado em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="83230-119">Shows that this index is sorted in ascending order.</span></span>  
  
 <span data-ttu-id="83230-120">**É primário**</span><span class="sxs-lookup"><span data-stu-id="83230-120">**Is Primary**</span></span>  
 <span data-ttu-id="83230-121">Indica se esse é o índice primário.</span><span class="sxs-lookup"><span data-stu-id="83230-121">Indicates whether this is the primary index.</span></span> <span data-ttu-id="83230-122">O primeiro índice XML criado na coluna será a base para os outros.</span><span class="sxs-lookup"><span data-stu-id="83230-122">The first XML index created on the column will be the basis of the others.</span></span>  
  
 <span data-ttu-id="83230-123">**Nome de referência primário**</span><span class="sxs-lookup"><span data-stu-id="83230-123">**Primary reference name**</span></span>  
 <span data-ttu-id="83230-124">Mostra o nome do índice primário se esse for um índice secundário.</span><span class="sxs-lookup"><span data-stu-id="83230-124">Shows the name of the primary index if this is a secondary index.</span></span> <span data-ttu-id="83230-125">Disponível apenas se este for um índice secundário.</span><span class="sxs-lookup"><span data-stu-id="83230-125">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="83230-126">**Tipo secundário**</span><span class="sxs-lookup"><span data-stu-id="83230-126">**Secondary type**</span></span>  
 <span data-ttu-id="83230-127">Mostra o tipo de índice secundário.</span><span class="sxs-lookup"><span data-stu-id="83230-127">Shows the type of secondary index.</span></span> <span data-ttu-id="83230-128">Disponível apenas se este for um índice secundário.</span><span class="sxs-lookup"><span data-stu-id="83230-128">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="83230-129">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="83230-129">**Type**</span></span>  
 <span data-ttu-id="83230-130">Mostra que esse é um índice XML.</span><span class="sxs-lookup"><span data-stu-id="83230-130">Shows that this is an XML index.</span></span>  
  
 <span data-ttu-id="83230-131">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="83230-131">**Identity Category**</span></span>  
 <span data-ttu-id="83230-132">Quando expandida, mostra os campos de propriedade **Nome** e **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="83230-132">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="83230-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="83230-133">**Name**</span></span>  
 <span data-ttu-id="83230-134">Mostra o nome do índice XML.</span><span class="sxs-lookup"><span data-stu-id="83230-134">Shows the name of the XML index.</span></span> <span data-ttu-id="83230-135">Quando um novo índice é criado ele recebe um nome padrão com base na tabela da janela ativa no Designer de tabelas.</span><span class="sxs-lookup"><span data-stu-id="83230-135">When a new one is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="83230-136">É possível alterar o nome a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="83230-136">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="83230-137">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="83230-137">**Description**</span></span>  
 <span data-ttu-id="83230-138">Descreve o índice.</span><span class="sxs-lookup"><span data-stu-id="83230-138">Describe the index.</span></span> <span data-ttu-id="83230-139">Para escrever uma descrição mais detalhada, clique em **Descrição** e, em seguida, clique no botão de reticências ( **…** ) que aparece à direita do campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="83230-139">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="83230-140">Isso criará uma área maior para a redação do texto.</span><span class="sxs-lookup"><span data-stu-id="83230-140">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="83230-141">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="83230-141">**Table Designer Category**</span></span>  
 <span data-ttu-id="83230-142">Quando expandida, mostra informações sobre as propriedades desse índice XML.</span><span class="sxs-lookup"><span data-stu-id="83230-142">When expanded, shows information about the properties of this XML index.</span></span>  
  
 <span data-ttu-id="83230-143">**Especificação de preenchimento**</span><span class="sxs-lookup"><span data-stu-id="83230-143">**Fill Specification**</span></span>  
 <span data-ttu-id="83230-144">Quando expandido, mostra informações de **Fator de Preenchimento** e **Preenchimento de índice**.</span><span class="sxs-lookup"><span data-stu-id="83230-144">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="83230-145">**Fator de Preenchimento**</span><span class="sxs-lookup"><span data-stu-id="83230-145">**Fill Factor**</span></span>  
 <span data-ttu-id="83230-146">Especifica a porcentagem da página de índice que o sistema poderá preencher.</span><span class="sxs-lookup"><span data-stu-id="83230-146">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="83230-147">Após o preenchimento da página, o sistema precisa dividir a página se forem adicionados novos dados, o que compromete o desempenho.</span><span class="sxs-lookup"><span data-stu-id="83230-147">Once a page is full, the system must split the page if new data is added, which impairs performance.</span></span>  
  
-   <span data-ttu-id="83230-148">Um valor de 100 significa que as páginas serão preenchidas; isso exige o espaço mínimo de armazenamento mas é o menos eficaz.</span><span class="sxs-lookup"><span data-stu-id="83230-148">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="83230-149">Essa configuração só deverá usada quando não houver alterações de dados; por exemplo, em uma tabela somente leitura.</span><span class="sxs-lookup"><span data-stu-id="83230-149">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="83230-150">Um valor inferior propicia mais espaço vazio nas páginas de dados, o que reduz a necessidade de dividir as páginas de dados à medida que os índices aumentam.</span><span class="sxs-lookup"><span data-stu-id="83230-150">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="83230-151">Porém, isso requer mais espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="83230-151">However, it requires more storage space.</span></span> <span data-ttu-id="83230-152">Essa configuração é mais adequada quando houver alterações nos dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="83230-152">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="83230-153">**Preenchimento de índice**</span><span class="sxs-lookup"><span data-stu-id="83230-153">**Pad Index**</span></span>  
 <span data-ttu-id="83230-154">Fornece páginas nesse índice com a mesmo percentual de espaço vazio (preenchimento) especificado em **Fator de Preenchimento**.</span><span class="sxs-lookup"><span data-stu-id="83230-154">Provide pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="83230-155">**Está Desabilitado**</span><span class="sxs-lookup"><span data-stu-id="83230-155">**Is Disabled**</span></span>  
 <span data-ttu-id="83230-156">Especifica se esse índice está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="83230-156">Specify whether this index is disabled.</span></span> <span data-ttu-id="83230-157">Índices desabilitados não oferecem suporte para pesquisas, nem são atualizados quando são adicionados itens novos à tabela.</span><span class="sxs-lookup"><span data-stu-id="83230-157">Disabled indexes do not support searches, nor do they get updated when new items are added to the table.</span></span> <span data-ttu-id="83230-158">Você pode melhorar o desempenho para inserções em massa e atualizações desabilitando um índice.</span><span class="sxs-lookup"><span data-stu-id="83230-158">You can improve performance for bulk inserts and updates by disabling an index.</span></span>  
  
 <span data-ttu-id="83230-159">**Bloqueios de página permitidos**</span><span class="sxs-lookup"><span data-stu-id="83230-159">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="83230-160">Especifica se o bloqueio de página é permitido no índice.</span><span class="sxs-lookup"><span data-stu-id="83230-160">Specify whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="83230-161">A permissão ou não dos bloqueios de página afeta o desempenho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="83230-161">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="83230-162">**Recalcular estatísticas**</span><span class="sxs-lookup"><span data-stu-id="83230-162">**Re-compute Statistics**</span></span>  
 <span data-ttu-id="83230-163">Calcula estatísticas novas quando o índice é criado.</span><span class="sxs-lookup"><span data-stu-id="83230-163">Compute new statistics when the index is created.</span></span> <span data-ttu-id="83230-164">Ao se recalcular estatísticas retarda-se a criação dos índices, mas em geral melhora-se o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="83230-164">Re-computing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="83230-165">**Bloqueios de Linha Permitidos**</span><span class="sxs-lookup"><span data-stu-id="83230-165">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="83230-166">Especifica se o bloqueio de linha é permitido no índice.</span><span class="sxs-lookup"><span data-stu-id="83230-166">Specify whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="83230-167">A permissão ou não dos bloqueios de linha afeta o desempenho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="83230-167">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83230-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83230-168">See Also</span></span>  
 [<span data-ttu-id="83230-169">Criar índices XML</span><span class="sxs-lookup"><span data-stu-id="83230-169">Create XML Indexes</span></span>](../../relational-databases/xml/create-xml-indexes.md)  
  
  
