---
title: Caixa de diálogo Índices Espaciais (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.spatialindexes
ms.assetid: 4d84239a-68c7-4aa2-8602-2b51dd07260f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e401b7f93a8376b1c6dc0c75ca29cbdc8a39863d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573358"
---
# <a name="spatial-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="bc54e-102">Caixa de diálogo Índices Espaciais (Ferramentas de Banco de Dados Visual)</span><span class="sxs-lookup"><span data-stu-id="bc54e-102">Spatial Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="bc54e-103">Use a caixa de diálogo **Índices Espaciais** em colunas de tipo de dados de **geometria** ou **geografia** (*colunas espaciais*), que não podem ser indexadas usando a caixa de diálogo **Índice/Chaves** .</span><span class="sxs-lookup"><span data-stu-id="bc54e-103">Use the **Spatial Indexes** dialog box to create indexes for columns of the **geometry** or **geography** data type (*spatial columns*), which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="bc54e-104">Cada coluna espacial pode ter mais de um índice espacial, mas eles devem ser criados um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="bc54e-104">Each spatial column can have more than one spatial index, but they must be created one at a time.</span></span>  
  
 <span data-ttu-id="bc54e-105">Para obter informações sobre restrições de criação de índices espaciais, consulte [Visão geral de índices espaciais](../../relational-databases/spatial/spatial-indexes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc54e-105">For information about restrictions on spatial index creation, see [Spatial Indexes Overview](../../relational-databases/spatial/spatial-indexes-overview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc54e-106">Opções</span><span class="sxs-lookup"><span data-stu-id="bc54e-106">Options</span></span>  
 <span data-ttu-id="bc54e-107">**Índice Espacial Selecionado**</span><span class="sxs-lookup"><span data-stu-id="bc54e-107">**Selected Spatial Index**</span></span>  
 <span data-ttu-id="bc54e-108">Lista os índices espaciais existentes.</span><span class="sxs-lookup"><span data-stu-id="bc54e-108">Lists existing spatial indexes.</span></span> <span data-ttu-id="bc54e-109">Selecione um índice para mostrar suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="bc54e-109">Select an index to show its properties.</span></span> <span data-ttu-id="bc54e-110">Se a lista estiver vazia, nenhum índice espacial foi definido para a tabela.</span><span class="sxs-lookup"><span data-stu-id="bc54e-110">If the list is empty, no spatial indexes have been defined for the table.</span></span>  
  
 <span data-ttu-id="bc54e-111">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="bc54e-111">**Add**</span></span>  
 <span data-ttu-id="bc54e-112">Cria um novo índice espacial.</span><span class="sxs-lookup"><span data-stu-id="bc54e-112">Creates a new spatial index.</span></span>  
  
 <span data-ttu-id="bc54e-113">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="bc54e-113">**Delete**</span></span>  
 <span data-ttu-id="bc54e-114">Exclui o índice espacial selecionado na lista **Índice Espacial Selecionado** .</span><span class="sxs-lookup"><span data-stu-id="bc54e-114">Deletes the spatial index selected in the **Selected Spatial Index** list.</span></span>  
  
 <span data-ttu-id="bc54e-115">**Células por Objeto**</span><span class="sxs-lookup"><span data-stu-id="bc54e-115">**Cells Per Object**</span></span>  
 <span data-ttu-id="bc54e-116">Indica o número de células por objeto do mosaico que pode ser usado para um único objeto espacial no índice.</span><span class="sxs-lookup"><span data-stu-id="bc54e-116">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="bc54e-117">Esse número pode ser qualquer inteiro entre 1 e 8.192, inclusive.</span><span class="sxs-lookup"><span data-stu-id="bc54e-117">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="bc54e-118">O padrão é 16.</span><span class="sxs-lookup"><span data-stu-id="bc54e-118">The default is 16.</span></span>  
  
 <span data-ttu-id="bc54e-119">Se um objeto abranger mais células do que o especificado por *n*, a indexação usará tantas células quantas forem necessárias para fornecer um mosaico de nível superior completo.</span><span class="sxs-lookup"><span data-stu-id="bc54e-119">If an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="bc54e-120">Nesses casos, um objeto poderia receber mais que o número de células especificado.</span><span class="sxs-lookup"><span data-stu-id="bc54e-120">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="bc54e-121">Nesse caso, o número máximo de células geradas pela grade de nível superior, que depende da densidade **Nível 1** .</span><span class="sxs-lookup"><span data-stu-id="bc54e-121">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
 <span data-ttu-id="bc54e-122">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="bc54e-122">**Columns**</span></span>  
 <span data-ttu-id="bc54e-123">Indica o nome de coluna e a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="bc54e-123">Indicates the column name and sort order.</span></span>  
  
 <span data-ttu-id="bc54e-124">**IsSpatialIndex**</span><span class="sxs-lookup"><span data-stu-id="bc54e-124">**IsSpatialIndex**</span></span>  
 <span data-ttu-id="bc54e-125">Indica que um índice espacial está selecionado.</span><span class="sxs-lookup"><span data-stu-id="bc54e-125">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="bc54e-126">**Nível 1**</span><span class="sxs-lookup"><span data-stu-id="bc54e-126">**Level 1**</span></span>  
 <span data-ttu-id="bc54e-127">Indica a densidade da grade de primeiro nível (superior).</span><span class="sxs-lookup"><span data-stu-id="bc54e-127">Indicates the density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="bc54e-128">**Nível 2**</span><span class="sxs-lookup"><span data-stu-id="bc54e-128">**Level 2**</span></span>  
 <span data-ttu-id="bc54e-129">Indica a densidade da grade de segundo nível.</span><span class="sxs-lookup"><span data-stu-id="bc54e-129">Indicates the density of the second-level grid.</span></span>  
  
 <span data-ttu-id="bc54e-130">**Nível 3**</span><span class="sxs-lookup"><span data-stu-id="bc54e-130">**Level 3**</span></span>  
 <span data-ttu-id="bc54e-131">Indica a densidade da grade de terceiro nível.</span><span class="sxs-lookup"><span data-stu-id="bc54e-131">Indicates the density of the third-level grid.</span></span>  
  
 <span data-ttu-id="bc54e-132">**Nível 4**</span><span class="sxs-lookup"><span data-stu-id="bc54e-132">**Level 4**</span></span>  
 <span data-ttu-id="bc54e-133">Indica a densidade da grade de quarto nível.</span><span class="sxs-lookup"><span data-stu-id="bc54e-133">Indicates the density of the fourth-level grid.</span></span>  
  
 <span data-ttu-id="bc54e-134">**Esquema de Mosaico**</span><span class="sxs-lookup"><span data-stu-id="bc54e-134">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="bc54e-135">Indica o esquema de mosaico do índice:</span><span class="sxs-lookup"><span data-stu-id="bc54e-135">Indicates the tessellation scheme:</span></span>  
  
 <span data-ttu-id="bc54e-136">Opções da coluna**Geometria** :</span><span class="sxs-lookup"><span data-stu-id="bc54e-136">**Geometry** column options:</span></span>  
  
-   <span data-ttu-id="bc54e-137">**Grade geométrica** para uma coluna de geometria</span><span class="sxs-lookup"><span data-stu-id="bc54e-137">**Geometry grid** for a geometry column</span></span>  
  
-   <span data-ttu-id="bc54e-138">**Grade geográfica** para uma coluna de geografia</span><span class="sxs-lookup"><span data-stu-id="bc54e-138">**Geography grid** for a geography column</span></span>  
  
 <span data-ttu-id="bc54e-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bc54e-139">**Type**</span></span>  
 <span data-ttu-id="bc54e-140">Indica que um índice espacial está selecionado.</span><span class="sxs-lookup"><span data-stu-id="bc54e-140">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="bc54e-141">**X-max**</span><span class="sxs-lookup"><span data-stu-id="bc54e-141">**X-max**</span></span>  
 <span data-ttu-id="bc54e-142">Especifica a coordenada x do canto superior direito da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="bc54e-142">Specifies the x-coordinate of the upper-right corner of the bounding box.</span></span> <span data-ttu-id="bc54e-143">Esta propriedade ficará esmaecida se o **Esquema de Mosaico** for **Grade geográfica**.</span><span class="sxs-lookup"><span data-stu-id="bc54e-143">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="bc54e-144">**X-min**</span><span class="sxs-lookup"><span data-stu-id="bc54e-144">**X-min**</span></span>  
 <span data-ttu-id="bc54e-145">Especifica a coordenada x do canto inferior esquerdo da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="bc54e-145">Specifies the x-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="bc54e-146">Esta propriedade ficará esmaecida se o **Esquema de Mosaico** for **Grade geográfica**.</span><span class="sxs-lookup"><span data-stu-id="bc54e-146">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="bc54e-147">**Y-max**</span><span class="sxs-lookup"><span data-stu-id="bc54e-147">**Y-max**</span></span>  
 <span data-ttu-id="bc54e-148">Especifica a coordenada y do canto superior direito da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="bc54e-148">Specifies the y-coordinate of upper-right corner of the bounding box.</span></span> <span data-ttu-id="bc54e-149">Esta propriedade ficará esmaecida se o **Esquema de Mosaico** for **Grade geográfica**.</span><span class="sxs-lookup"><span data-stu-id="bc54e-149">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="bc54e-150">**Y-min**</span><span class="sxs-lookup"><span data-stu-id="bc54e-150">**Y-min**</span></span>  
 <span data-ttu-id="bc54e-151">Especifica a coordenada y do canto inferior esquerdo da caixa delimitadora.</span><span class="sxs-lookup"><span data-stu-id="bc54e-151">Specifies the y-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="bc54e-152">Esta propriedade ficará esmaecida se o **Esquema de Mosaico** for **Grade geográfica**.</span><span class="sxs-lookup"><span data-stu-id="bc54e-152">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="bc54e-153">**Identidade**</span><span class="sxs-lookup"><span data-stu-id="bc54e-153">**Identity**</span></span>  
 <span data-ttu-id="bc54e-154">Quando expandida, mostra os campos de propriedade **Nome** e **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="bc54e-154">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="bc54e-155">**(Nome)**</span><span class="sxs-lookup"><span data-stu-id="bc54e-155">**(Name)**</span></span>  
 <span data-ttu-id="bc54e-156">Mostra o nome do índice espacial.</span><span class="sxs-lookup"><span data-stu-id="bc54e-156">Shows the name of the spatial index.</span></span> <span data-ttu-id="bc54e-157">Quando um novo índice é criado, é dado um nome padrão baseado na tabela da janela ativa no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="bc54e-157">When a new index is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="bc54e-158">É possível alterar o nome a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="bc54e-158">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="bc54e-159">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bc54e-159">**Description**</span></span>  
 <span data-ttu-id="bc54e-160">Descreve o índice.</span><span class="sxs-lookup"><span data-stu-id="bc54e-160">Describes the index.</span></span> <span data-ttu-id="bc54e-161">Para escrever uma descrição mais detalhada, clique em **Descrição** e, em seguida, clique no botão de reticências ( **…** ) que aparece à direita do campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="bc54e-161">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="bc54e-162">Isso criará uma área maior para a redação do texto.</span><span class="sxs-lookup"><span data-stu-id="bc54e-162">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="bc54e-163">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="bc54e-163">**Table Designer Category**</span></span>  
 <span data-ttu-id="bc54e-164">Quando expandida, mostra informações sobre as propriedades desse índice espacial.</span><span class="sxs-lookup"><span data-stu-id="bc54e-164">When expanded, shows information about the properties of this spatial index.</span></span>  
  
 <span data-ttu-id="bc54e-165">**Especificação de preenchimento**</span><span class="sxs-lookup"><span data-stu-id="bc54e-165">**Fill Specification**</span></span>  
 <span data-ttu-id="bc54e-166">Quando expandido, mostra informações de **Fator de Preenchimento** e **Preenchimento de índice**.</span><span class="sxs-lookup"><span data-stu-id="bc54e-166">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="bc54e-167">**Fator de Preenchimento**</span><span class="sxs-lookup"><span data-stu-id="bc54e-167">**Fill Factor**</span></span>  
 <span data-ttu-id="bc54e-168">Especifica a porcentagem da página de índice que o sistema poderá preencher.</span><span class="sxs-lookup"><span data-stu-id="bc54e-168">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="bc54e-169">Quando a página estiver preenchida, se novos dados forem adicionados, o sistema precisará dividir a página, o que compromete o desempenho.</span><span class="sxs-lookup"><span data-stu-id="bc54e-169">When a page is full, if new data is added, the system must split the page, which impairs performance.</span></span>  
  
-   <span data-ttu-id="bc54e-170">Um valor de 100 significa que as páginas serão preenchidas; isso exige o espaço mínimo de armazenamento mas é o menos eficaz.</span><span class="sxs-lookup"><span data-stu-id="bc54e-170">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="bc54e-171">Essa configuração só deverá usada quando não houver alterações de dados; por exemplo, em uma tabela somente leitura.</span><span class="sxs-lookup"><span data-stu-id="bc54e-171">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="bc54e-172">Um valor inferior propicia mais espaço vazio nas páginas de dados, o que reduz a necessidade de dividir as páginas de dados à medida que os índices aumentam.</span><span class="sxs-lookup"><span data-stu-id="bc54e-172">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="bc54e-173">Porém, isso requer mais espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="bc54e-173">However, it requires more storage space.</span></span> <span data-ttu-id="bc54e-174">Essa configuração é mais adequada quando houver alterações nos dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="bc54e-174">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="bc54e-175">**Preenchimento de índice**</span><span class="sxs-lookup"><span data-stu-id="bc54e-175">**Pad Index**</span></span>  
 <span data-ttu-id="bc54e-176">Fornece páginas nesse índice com o mesmo percentual de espaço vazio (preenchimento) especificado em **Fator de Preenchimento**.</span><span class="sxs-lookup"><span data-stu-id="bc54e-176">Provides pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="bc54e-177">**Bloqueios de página permitidos**</span><span class="sxs-lookup"><span data-stu-id="bc54e-177">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="bc54e-178">Especifica se o bloqueio de página é permitido no índice.</span><span class="sxs-lookup"><span data-stu-id="bc54e-178">Specifies whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="bc54e-179">A permissão ou não dos bloqueios de página afeta o desempenho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc54e-179">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="bc54e-180">**Recalcular estatísticas**</span><span class="sxs-lookup"><span data-stu-id="bc54e-180">**Re-compute  Statistics**</span></span>  
 <span data-ttu-id="bc54e-181">Especifica se as novas estatísticas deverão ser recalculadas quando o índice for criado.</span><span class="sxs-lookup"><span data-stu-id="bc54e-181">Specifies whether to compute new statistics when the index is created.</span></span> <span data-ttu-id="bc54e-182">Ao se recalcular estatísticas retarda-se a criação dos índices, mas em geral melhora-se o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="bc54e-182">Recomputing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="bc54e-183">**Bloqueios de Linha Permitidos**</span><span class="sxs-lookup"><span data-stu-id="bc54e-183">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="bc54e-184">Especifica se o bloqueio de linha é permitido no índice.</span><span class="sxs-lookup"><span data-stu-id="bc54e-184">Specifies whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="bc54e-185">A permissão ou não dos bloqueios de linha afeta o desempenho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc54e-185">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc54e-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc54e-186">See Also</span></span>  
 [<span data-ttu-id="bc54e-187">Visão geral de índices espaciais</span><span class="sxs-lookup"><span data-stu-id="bc54e-187">Spatial Indexes Overview</span></span>](../../relational-databases/spatial/spatial-indexes-overview.md)  
  
  
