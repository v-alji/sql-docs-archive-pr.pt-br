---
title: Compreendendo a geração incremental | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- incremental generation [Analysis Services]
- Schema Generation Wizard, incremental generation
- relational schema [Analysis Services], incremental generation
ms.assetid: 3ca0aa63-3eb5-4fe9-934f-8e96dee84eaa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7a3bfef76d45d1d015e6f8a258b8df8b2ae639e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575405"
---
# <a name="understanding-incremental-generation"></a><span data-ttu-id="9bfa9-102">Entendendo a geração com incremento</span><span class="sxs-lookup"><span data-stu-id="9bfa9-102">Understanding Incremental Generation</span></span>
  <span data-ttu-id="9bfa9-103">Após a geração de esquema inicial, você pode alterar as definições do cubo e das dimensões usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]e, em seguida, executar novamente o Assistente de Geração de Esquema.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-103">Following the initial schema generation, you can change cube and dimension definitions by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then rerun the Schema Generation Wizard.</span></span> <span data-ttu-id="9bfa9-104">O assistente atualiza o esquema do banco de dados da área de assunto e da exibição da fonte de dados associada para refletir as mudanças, mantendo, na medida do possível, os dados que já existem nas tabelas que serão geradas novamente.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-104">The wizard updates the schema in the subject area database and in the associated data source view to reflect the changes, and retaining the data that currently exists in the tables to be regenerated, to the extent possible.</span></span> <span data-ttu-id="9bfa9-105">Se você alterou as tabelas depois da geração inicial, o Assistente de Geração de Esquema preservará essas alterações sempre que possível usando as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="9bfa9-105">If you changed the tables after the initial generation, the Schema Generation Wizard preserves those changes when possible by using the following rules:</span></span>  
  
-   <span data-ttu-id="9bfa9-106">Se uma tabela foi previamente gerada pelo assistente, ela será substituída.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-106">If a table was previously generated by the wizard, the table is overwritten.</span></span> <span data-ttu-id="9bfa9-107">Você pode evitar que a tabela gerada pelo assistente seja substituída alterando a propriedade `AllowChangesDuringGeneration` da tabela da exibição da fonte de dados para `false`.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-107">You can prevent a table that was generated by the wizard from being overwritten by changing the `AllowChangesDuringGeneration` property for the table in the data source view to `false`.</span></span> <span data-ttu-id="9bfa9-108">Quando você assume o controle de uma tabela, ela passa a ser tratada como qualquer outra tabela definida pelo usuário e não é afetada durante a nova geração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-108">When you take control of a table, the table is treated like any other user-defined table and is not affected during regeneration.</span></span> <span data-ttu-id="9bfa9-109">Depois de remover uma tabela da nova geração, você pode alterar a propriedade `AllowChangesDuringGeneration` da tabela da exibição da fonte de dados para `true` e reabri-la para fazer as alterações do assistente.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-109">After you remove a table from generation, you can later change the `AllowChangesDuringGeneration` property for the table in the data source view to `true` and reopen the table for changes by the wizard.</span></span> <span data-ttu-id="9bfa9-110">Para obter mais informações, consulte [Alterar propriedades em uma exibição da fonte de dados &#40;Analysis Services&#41;](change-properties-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="9bfa9-110">For more information, see [Change Properties in a Data Source View &#40;Analysis Services&#41;](change-properties-in-a-data-source-view-analysis-services.md).</span></span>  
  
-   <span data-ttu-id="9bfa9-111">Se a tabela foi adicionada à exibição da fonte de dados ou ao banco de dados subjacente de outra forma que não pelo assistente, ela não será substituída.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-111">If a table was added to the data source view or to the underlying database by something other than the wizard, the table is not overwritten.</span></span>  
  
 <span data-ttu-id="9bfa9-112">Quando o Assistente de Geração de Esquema gerar novamente as tabelas que antes eram geradas no banco de dados da área de assunto, pode ser preferível que o assistente preserve os dados existentes nessas tabelas.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-112">When the Schema Generation Wizard regenerates tables that were previously generated in the subject area database, you can choose to have the wizard preserve existing data in those tables.</span></span>  
  
## <a name="supporting-data-preservation"></a><span data-ttu-id="9bfa9-113">Oferecendo suporte a preservação dos dados</span><span class="sxs-lookup"><span data-stu-id="9bfa9-113">Supporting Data Preservation</span></span>  
 <span data-ttu-id="9bfa9-114">Como regra geral, o Assistente de Geração de Esquema preserva os dados que estão armazenados nas tabelas por ele geradas.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-114">As a general rule, the Schema Generation Wizard preserves data that is stored in the tables that it generated.</span></span> <span data-ttu-id="9bfa9-115">Além disso, se você adicionar colunas a tabelas que o assistente gerou, este preservará também os dados.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-115">In addition, if you add columns to tables that the wizard generated, the wizard preserves that data as well.</span></span> <span data-ttu-id="9bfa9-116">Você pode usar esse recurso para adicionar ou modificar dimensões e cubos e, em seguida, gerar novamente os objetos subjacentes sem precisar recarregar os dados armazenados nas tabelas subjacentes.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-116">You can use this capability to add or modify your dimensions and cubes and then regenerate the underlying objects without having to reload the data stored in the underlying tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bfa9-117">Se você estiver carregando dados de arquivos de texto delimitados, poderá também decidir se o Assistente de Geração de Esquema substituirá esses arquivos e os dados neles contidos durante a nova geração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-117">If you are loading data from delimited text files, you can also choose whether the Schema Generation Wizard overwrites these files and the data contained in them during regeneration.</span></span> <span data-ttu-id="9bfa9-118">Os arquivos de texto podem ser totalmente substituídos ou não.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-118">Text files are either overwritten completely or not at all.</span></span> <span data-ttu-id="9bfa9-119">O Assistente de Geração de Esquema não substitui os arquivos parcialmente.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-119">The Schema Generation Wizard does not partially overwrite these files.</span></span> <span data-ttu-id="9bfa9-120">Por padrão, esses arquivos não são substituídos.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-120">By default, these files are not overwritten.</span></span>  
  
### <a name="partial-preservation"></a><span data-ttu-id="9bfa9-121">Preservação parcial</span><span class="sxs-lookup"><span data-stu-id="9bfa9-121">Partial Preservation</span></span>  
 <span data-ttu-id="9bfa9-122">O Assistente de Geração de Esquema não pode preservar os dados existentes em algumas situações.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-122">The Schema Generation Wizard cannot preserve existing data under some circumstances.</span></span> <span data-ttu-id="9bfa9-123">A tabela a seguir fornece exemplos de situações em que o assistente não é capaz de preservar todos os dados existentes nas tabelas subjacentes durante a nova geração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-123">The following table provides examples of situations in which the wizard cannot preserve all the existing data in the underlying tables during regeneration.</span></span>  
  
|<span data-ttu-id="9bfa9-124">Alteração do tipo de dados</span><span class="sxs-lookup"><span data-stu-id="9bfa9-124">Type of data change</span></span>|<span data-ttu-id="9bfa9-125">Tratamento</span><span class="sxs-lookup"><span data-stu-id="9bfa9-125">Treatment</span></span>|  
|-------------------------|---------------|  
|<span data-ttu-id="9bfa9-126">Alteração de tipo de dados incompatível</span><span class="sxs-lookup"><span data-stu-id="9bfa9-126">Incompatible data type change</span></span>|<span data-ttu-id="9bfa9-127">Sempre que possível, o Assistente de Geração de Esquema utiliza conversões do tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] padrão para converter os dados existentes de um tipo de dados para outro.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-127">The Schema Generation Wizard uses standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type conversions, whenever possible, to convert existing data from one data type to another.</span></span> <span data-ttu-id="9bfa9-128">No entanto, quando você altera o tipo de dados de um atributo para um tipo incompatível com os dados existentes, o assistente descarta os dados da coluna afetada.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-128">However, when you change an attribute's data type to a type that is incompatible with the existing data, the wizard drops the data for the affected column.</span></span>|  
|<span data-ttu-id="9bfa9-129">Erros de integridade referencial</span><span class="sxs-lookup"><span data-stu-id="9bfa9-129">Referential integrity errors</span></span>|<span data-ttu-id="9bfa9-130">Se você alterar uma dimensão ou um cubo que contém dados e a alteração causar um erro de integridade referencial durante a nova geração, o Assistente de Geração de Esquema descartará todos os dados da tabela de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-130">If you change a dimension or cube that contains data and the change causes a referential integrity error during regeneration, the Schema Generation Wizard drops all data in the foreign key table.</span></span> <span data-ttu-id="9bfa9-131">Os dados que são descartados não se limitam à coluna que causou a violação de restrição da chave estrangeira nem às linhas que contêm os erros de integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-131">The data that is dropped is not limited to the column that caused the foreign key constraint violation or to the rows that contain the referential integrity errors.</span></span> <span data-ttu-id="9bfa9-132">Por exemplo, se você alterar a chave da dimensão para um atributo que possui dados nulos ou não exclusivos, todos os dados existentes na tabela de chave estrangeira serão descartados.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-132">For example, if you change the dimension key to an attribute that has non-unique or null data, all existing data in the foreign key table is dropped.</span></span> <span data-ttu-id="9bfa9-133">Além disso, o descarte de todos os dados de uma tabela pode ter um efeito dominó e causar outras violações de integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-133">Furthermore, dropping all the data in one table can have a cascading effect and can cause other referential integrity violations.</span></span>|  
|<span data-ttu-id="9bfa9-134">Atributo ou dimensão excluído(a)</span><span class="sxs-lookup"><span data-stu-id="9bfa9-134">Deleted attribute or dimension</span></span>|<span data-ttu-id="9bfa9-135">Se você excluir um atributo de uma dimensão, o Assistente de Geração de Esquema excluirá a coluna que está mapeada para o atributo excluído.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-135">If you delete an attribute from a dimension, the Schema Generation Wizard deletes the column that is mapped to the deleted attribute.</span></span> <span data-ttu-id="9bfa9-136">Se você excluir uma dimensão, o assistente excluirá a tabela mapeada para a dimensão excluída.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-136">If you delete a dimension, the wizard deletes the table that is mapped to the deleted dimension.</span></span> <span data-ttu-id="9bfa9-137">Nesses casos, o assistente descartará os dados contidos na coluna ou tabela excluída.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-137">In these cases, the wizard drops the data that is contained in the deleted column or table.</span></span>|  
  
 <span data-ttu-id="9bfa9-138">O Assistente de Geração de Esquema emite um aviso antes de descartar os dados, de modo que é possível cancelar o assistente sem perder dados.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-138">The Schema Generation Wizard issues a warning before it drops any data so that you can cancel the wizard without losing any data.</span></span> <span data-ttu-id="9bfa9-139">No entanto, o Assistente de Geração de Esquema não consegue diferenciar entre a perda de dados prevista e a perda de dados imprevista.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-139">However, the Schema Generation Wizard is not able to differentiate between anticipated data loss and unanticipated data loss.</span></span> <span data-ttu-id="9bfa9-140">Quando você executa o assistente, uma caixa de diálogo lista as tabelas e colunas que contêm dados que serão descartados.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-140">When you run the wizard, a dialog box lists the tables and columns that contain data that will be dropped.</span></span> <span data-ttu-id="9bfa9-141">Você pode deixar o assistente prosseguir e descartar os dados ou cancelá-lo e revisar as alterações feitas nas tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-141">You can either have the wizard continue and drop the data, or you can cancel the wizard and revise the changes you made to the tables and columns.</span></span>  
  
## <a name="supporting-cube-and-dimension-changes"></a><span data-ttu-id="9bfa9-142">Suporte para alterações em cubos e dimensões</span><span class="sxs-lookup"><span data-stu-id="9bfa9-142">Supporting Cube and Dimension Changes</span></span>  
 <span data-ttu-id="9bfa9-143">Quando você altera as propriedades de dimensões e cubos, o Assistente de Geração de Esquema gera novamente os objetos apropriados no banco de dados da área de assunto subjacente, bem como da exibição da fonte de dados relacionada, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-143">When you change the properties of dimensions and cubes, the Schema Generation Wizard regenerates the appropriate objects in the underlying subject area database, as well as in the related data source view, as described in the following table.</span></span>  
  
 <span data-ttu-id="9bfa9-144">Excluindo um objeto, como uma dimensão, cubo ou atributo.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-144">Deleting an object, such as a dimension, cube, or attribute.</span></span>  
 <span data-ttu-id="9bfa9-145">O Assistente de Geração de Esquema exclui os objetos subjacentes para os quais o objeto excluído está mapeado.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-145">The Schema Generation Wizard deletes the underlying objects to which the deleted object is mapped.</span></span> <span data-ttu-id="9bfa9-146">Se você adicionar colunas a uma tabela que o assistente gerou, as novas colunas não impedirão a exclusão da tabela.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-146">If you add columns to a table that the wizard generated, the new columns do not prevent that table from being deleted.</span></span> <span data-ttu-id="9bfa9-147">A exclusão de um objeto faz com que os dados armazenados nos objetos subjacentes sejam descartados e também pode fazer com outros dados sejam descartados se ocorrerem erros de integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-147">Deleting an object causes the data stored in the underlying objects to be dropped, and may also cause other data to be dropped if referential integrity errors occur.</span></span>  
  
 <span data-ttu-id="9bfa9-148">Renomeando um objeto, como uma dimensão, cubo ou atributo.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-148">Renaming an object, such as a dimension, cube, or attribute.</span></span>  
 <span data-ttu-id="9bfa9-149">O Assistente de Geração de Esquema renomeia os objetos subjacentes para os quais o objeto renomeado está mapeado.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-149">The Schema Generation Wizard renames the underlying objects to which the renamed object is mapped.</span></span> <span data-ttu-id="9bfa9-150">O assistente também renomeia todos os objetos afetados, como as chaves primárias.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-150">The wizard also renames all affected objects, such as primary keys.</span></span> <span data-ttu-id="9bfa9-151">Os dados existentes armazenados nos objetos subjacentes são preservados.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-151">Existing data stored in the underlying objects is preserved.</span></span>  
  
 <span data-ttu-id="9bfa9-152">Modificando um objeto, como a alteração de seu tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-152">Modifying an object, such as changing its data type.</span></span>  
 <span data-ttu-id="9bfa9-153">O Assistente de Geração de Esquema modifica os objetos subjacentes para os quais o objeto modificado está mapeado.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-153">The Schema Generation Wizard modifies the underlying objects to which the changed object is mapped.</span></span> <span data-ttu-id="9bfa9-154">Os dados existentes armazenados nos objetos subjacentes dos bancos de dados são preservados, exceto se o novo tipo de dados for incompatível com os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-154">Existing data stored in the underlying objects in the databases is preserved, unless the new data type is incompatible with the existing data.</span></span>  
  
 <span data-ttu-id="9bfa9-155">Adicionando um novo objeto, como uma dimensão, cubo ou atributo.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-155">Adding a new object, such as a dimension, cube, or attribute.</span></span>  
 <span data-ttu-id="9bfa9-156">O Assistente de Geração de Esquema adiciona objetos subjacentes para os quais o novo objeto está mapeado.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-156">The Schema Generation Wizard adds underlying objects to which the new object is mapped.</span></span>  
  
 <span data-ttu-id="9bfa9-157">Se o Assistente de Geração de Esquema não puder fazer a alteração necessária porque existe um objeto de usuário no banco de dados da área de assunto (porque o Database Engine retorna um erro), ocorrerá uma falha do Assistente de Geração de Esquema e ele exibirá o erro retornado pelo Database Engine.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-157">If the Schema Generation Wizard cannot make the required change because of the presence of a user object in the subject area database (because the Database Engine returns an error), the Schema Generation Wizard fails and displays the error returned by the Database Engine.</span></span> <span data-ttu-id="9bfa9-158">Por exemplo, se você criar uma restrição de chave primária ou um índice não clusterizado em uma tabela depois que o assistente gerar a tabela, o assistente de geração de esquema não descartará essa tabela porque ela não criou a restrição ou o índice.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-158">For example, if you create a primary key constraint or a nonclustered index on a table after the wizard generated the table, the Schema Generation Wizard does not drop that table because it did not create the constraint or the index.</span></span>  
  
## <a name="supporting-schema-changes"></a><span data-ttu-id="9bfa9-159">Suporte a alterações de esquema</span><span class="sxs-lookup"><span data-stu-id="9bfa9-159">Supporting Schema Changes</span></span>  
 <span data-ttu-id="9bfa9-160">Quando você alterar as propriedades de tabelas ou colunas do banco de dados da área de assunto ou da exibição da fonte de dados associada, o Assistente de Geração de Esquema tratará as alterações conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-160">When you change the properties of the tables or columns in the subject area database or in the associated data source view, the Schema Generation Wizard treats the changes as described in the following table.</span></span>  
  
 <span data-ttu-id="9bfa9-161">Exclusão de uma tabela ou uma coluna gerada pelo Assistente de Geração de Esquema.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-161">Deleting a table or a column generated by the Schema Generation Wizard.</span></span>  
 <span data-ttu-id="9bfa9-162">Se você excluir uma tabela ou coluna gerada pelo Assistente de Geração de Esquema, o assistente gerará novamente tabela excluída.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-162">If you delete a table or a column generated by the Schema Generation Wizard, the wizard regenerates the deleted table.</span></span> <span data-ttu-id="9bfa9-163">O assistente não fornece nenhum aviso de que a tabela ou coluna excluída será gerada novamente.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-163">The wizard provides no warning that the deleted table or column will be regenerated.</span></span>  
  
 <span data-ttu-id="9bfa9-164">Alteração das propriedades de uma tabela ou coluna gerada pelo Assistente de Geração de Esquema.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-164">Changing the properties of a table or column generated by the Schema Generation Wizard.</span></span>  
 <span data-ttu-id="9bfa9-165">Se você modificar as propriedades de uma tabela ou coluna gerada pelo Assistente de Geração de Esquema, o assistente gerará a tabela alterada sem a alteração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-165">If you modify the properties of a table or a column generated by the Schema Generation Wizard, the wizard regenerates the changed table without the change.</span></span> <span data-ttu-id="9bfa9-166">Por exemplo, se você alterar o tipo de dados, a nulidade de uma coluna ou o grupo de arquivos de uma tabela gerada pelo Assistente de Geração de Esquema, a alteração não será preservada após a nova geração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-166">For example, if you change the data type or nullability of a column, or the filegroup of a table generated by the Schema Generation Wizard, the change does not survive the regeneration.</span></span> <span data-ttu-id="9bfa9-167">O assistente não fornece nenhum aviso de que o objeto alterado será gerado novamente sem a alteração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-167">The wizard provides no warning that the changed object will be regenerated without the change.</span></span>  
  
 <span data-ttu-id="9bfa9-168">Adição de uma coluna a uma tabela gerada pelo Assistente de Geração de Esquema ou de uma tabela ao banco de dados da área de assunto ou ao banco de dados da área de preparação.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-168">Adding a column to a table generated by the Schema Generation Wizard or adding a table to the subject area database or staging area database.</span></span>  
 <span data-ttu-id="9bfa9-169">Se você adicionar uma coluna a uma tabela gerada pelo Assistente de Geração de Esquema, o assistente preservará a coluna adicional além de todos os dados armazenados nela durante a nova geração.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-169">If you add a column to a table generated by the Schema Generation Wizard, the wizard preserves the additional column, along with any data stored in it, during regeneration.</span></span> <span data-ttu-id="9bfa9-170">No entanto, se você adicionar uma tabela gerada ao banco de dados da área de assunto ou ao banco de dados da área de preparação, o Assistente de Geração de Esquema não incorporará a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-170">However, if you add a table to the subject area database or the staging area database, the Schema Generation Wizard does not incorporate the new table.</span></span> <span data-ttu-id="9bfa9-171">A coluna, ou tabela, adicionada não aparecerá no projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , no banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , nos pacotes DTS, na exibição da fonte de dados ou em nenhum outro ponto do esquema que é gerado.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-171">The added column, or the added table, is not reflected in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, the DTS packages, the data source view, or any other place in the schema that is generated.</span></span>  
  
## <a name="supporting-data-source-and-data-source-view-changes"></a><span data-ttu-id="9bfa9-172">Suporte a alterações em fontes de dados e em exibições da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="9bfa9-172">Supporting Data Source and Data Source View Changes</span></span>  
 <span data-ttu-id="9bfa9-173">Quando o Assistente de Geração de Esquema é executado novamente, ele reutiliza a fonte de dados e a exibição da fonte de dados usadas na geração original.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-173">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="9bfa9-174">Se você adicionar uma fonte de dados ou uma exibição da fonte de dados, o assistente não a usará.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-174">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="9bfa9-175">Se você excluir a fonte de dados ou a exibição da fonte de dados original depois da geração inicial, execute o assistente desde o início.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-175">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="9bfa9-176">Também são excluídas todas as configurações anteriores do assistente.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-176">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="9bfa9-177">Todos os objetos existentes em um banco de dados subjacente que estavam vinculados a uma fonte de dados ou exibição de fonte de dados excluída serão tratados como objetos criados pelo usuário na próxima vez que você executar o Assistente de Geração de Esquema.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-177">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="9bfa9-178">Se a exibição da fonte de dados não refletir o estado real do banco de dados subjacente no momento da geração, o Assistente de Geração de Esquema pode encontrar erros ao gerar esquemas para o banco de dados da área de assunto ou da área de preparação.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-178">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schemas for the subject area database and the staging area database.</span></span> <span data-ttu-id="9bfa9-179">Por exemplo, se a exibição da fonte de dados especificar que o tipo de dados de uma coluna deve ser configurado como `int`, mas, na verdade, o tipo de dados da coluna estiver configurado como `string`, o Assistente de Geração de Esquema definirá o tipo de dados da chave estrangeira como `int` de acordo com a exibição da fonte de dados e, em seguida, não conseguirá criar a relação pois o tipo de dados real é `string`.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-179">For example, if the data source view specifies that the data type for a column is set to `int`, but the data type for the column is actually set to `string`, the Schema Generation Wizard sets the data type for the foreign key to `int` to match the data source view and then fails when it creates the relationship because the actual data type is `string`.</span></span>  
  
 <span data-ttu-id="9bfa9-180">Por outro lado, se você alterar a cadeia de conexão da fonte de dados para um banco de dados diferente daquele usado na geração anterior, nenhum erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-180">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="9bfa9-181">O novo banco de dados será usado e nenhuma alteração será feita no banco de dados anterior.</span><span class="sxs-lookup"><span data-stu-id="9bfa9-181">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfa9-182">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9bfa9-182">See Also</span></span>  
 <span data-ttu-id="9bfa9-183">[Gerenciar alterações em fontes de dados e exibições de fonte de dados](manage-changes-to-data-source-views-and-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="9bfa9-183">[Manage Changes to Data Source Views and Data Sources](manage-changes-to-data-source-views-and-data-sources.md) </span></span>  
 [<span data-ttu-id="9bfa9-184">Assistente de Geração de Esquema &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9bfa9-184">Schema Generation Wizard &#40;Analysis Services&#41;</span></span>](schema-generation-wizard-analysis-services.md)  
  
  