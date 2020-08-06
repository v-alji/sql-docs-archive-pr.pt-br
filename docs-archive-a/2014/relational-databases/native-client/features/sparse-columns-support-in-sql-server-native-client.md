---
title: Suporte a colunas esparsas no SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- sparse columns, ODBC
- sparse columns, SQL Server Native Client
- sparse columns, OLE DB
ms.assetid: aee5ed81-7e23-42e4-92d3-2da7844d9bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5c53210088f184ad4c56b71c03954b39fd83a497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570666"
---
# <a name="sparse-columns-support-in-sql-server-native-client"></a><span data-ttu-id="302e0-102">Suporte a colunas esparsas no SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="302e0-102">Sparse Columns Support in SQL Server Native Client</span></span>
  <span data-ttu-id="302e0-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client suporta colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="302e0-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports sparse columns.</span></span> <span data-ttu-id="302e0-104">Para obter mais informações sobre colunas esparsas no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], confira [Usar colunas esparsas](../../tables/use-sparse-columns.md) e [Usar conjuntos de colunas](../../tables/use-column-sets.md).</span><span class="sxs-lookup"><span data-stu-id="302e0-104">For more information about sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Use Sparse Columns](../../tables/use-sparse-columns.md) and [Use Column Sets](../../tables/use-column-sets.md).</span></span>  
  
 <span data-ttu-id="302e0-105">Para obter mais informações sobre o suporte a colunas esparsas no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, consulte [suporte a colunas esparsas &#40;&#41;ODBC](../odbc/sparse-columns-support-odbc.md) e [colunas esparsas dão suporte a &#40;OLE DB&#41;](../ole-db/sparse-columns-support-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="302e0-105">For more information about sparse column support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Sparse Columns Support &#40;ODBC&#41;](../odbc/sparse-columns-support-odbc.md) and [Sparse Columns Support &#40;OLE DB&#41;](../ole-db/sparse-columns-support-ole-db.md).</span></span>  
  
 <span data-ttu-id="302e0-106">Para obter informações sobre aplicativos de exemplo que demonstram esse recurso, confira [Amostras de programação do SQL Server Data](https://msftdpprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="302e0-106">For information about sample applications that demonstrate this feature, see [SQL Server Data Programming Samples](https://msftdpprodsamples.codeplex.com/).</span></span>  
  
## <a name="user-scenarios-for-sparse-columns-and-sql-server-native-client"></a><span data-ttu-id="302e0-107">Cenários de usuário para colunas esparsas e o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="302e0-107">User Scenarios for Sparse Columns and SQL Server Native Client</span></span>  
 <span data-ttu-id="302e0-108">A tabela a seguir resume os cenários comuns para usuários do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client com colunas esparsas:</span><span class="sxs-lookup"><span data-stu-id="302e0-108">The following table summarizes the common user scenarios for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client users with sparse columns:</span></span>  
  
|<span data-ttu-id="302e0-109">Cenário</span><span class="sxs-lookup"><span data-stu-id="302e0-109">Scenario</span></span>|<span data-ttu-id="302e0-110">Comportamento</span><span class="sxs-lookup"><span data-stu-id="302e0-110">Behavior</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="302e0-111">**select \* from table** ou IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="302e0-111">**select \* from table** or IOpenRowset::OpenRowset.</span></span>|<span data-ttu-id="302e0-112">Retorna todas as colunas que não são membros do `column_set` esparso, além de uma coluna XML que contém os valores de todas as colunas não nulas membros do `column_set` esparso.</span><span class="sxs-lookup"><span data-stu-id="302e0-112">Returns all columns that are not members of the sparse `column_set`, plus an XML column that contains the values of all non-null columns that are members of the sparse `column_set`.</span></span>|  
|<span data-ttu-id="302e0-113">Referenciar uma coluna por nome.</span><span class="sxs-lookup"><span data-stu-id="302e0-113">Reference a column by name.</span></span>|<span data-ttu-id="302e0-114">A coluna pode ser referenciada independentemente de seu status de coluna esparsa ou associação do `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-114">The column can be referenced regardless of its sparse column status or `column_set` membership.</span></span>|  
|<span data-ttu-id="302e0-115">Acessar colunas de membro do `column_set` através de uma coluna de XML computada.</span><span class="sxs-lookup"><span data-stu-id="302e0-115">Access `column_set` member columns through a computed XML column.</span></span>|<span data-ttu-id="302e0-116">As colunas que são membros do `column_set` esparso podem ser acessadas selecionando o `column_set` por nome e podem ter valores inseridos e atualizados atualizando o XML na coluna `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-116">Columns that are members of the sparse `column_set` can be accessed by selecting the `column_set` by name and can have values inserted and updated by updating the XML in the `column_set` column.</span></span><br /><br /> <span data-ttu-id="302e0-117">O valor precisa estar de acordo com o esquema para colunas `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-117">The value must conform to the schema for `column_set` columns.</span></span>|  
|<span data-ttu-id="302e0-118">Recuperar metadados de todas as colunas em uma tabela por meio de SQLColumns com um padrão de pesquisa de coluna de nulo ou '% ' (ODBC); ou por meio do conjunto de linhas de esquema DBSCHEMA_COLUMNS sem restrição de coluna (OLE DB).</span><span class="sxs-lookup"><span data-stu-id="302e0-118">Retrieve metadata for all columns in a table through SQLColumns with a column search pattern of NULL or '%' (ODBC); or through the DBSCHEMA_COLUMNS schema rowset with no column restriction (OLE DB).</span></span>|<span data-ttu-id="302e0-119">Retorna uma linha para todas as colunas que não são membros de um `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-119">Returns a row for all columns that are not members of a `column_set`.</span></span> <span data-ttu-id="302e0-120">Se a tabela tiver um `column_set` esparso, uma linha será retornada para ela.</span><span class="sxs-lookup"><span data-stu-id="302e0-120">If the table has a sparse `column_set`, a row will be returned for it.</span></span><br /><br /> <span data-ttu-id="302e0-121">Observe que essa ação não retorna metadados para colunas que são membros de um `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-121">Note that this does not return metadata for columns that are members of a `column_set`.</span></span>|  
|<span data-ttu-id="302e0-122">Recuperar metadados para todas as colunas, independentemente de dispersão ou associação em um `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-122">Retrieve metadata for all columns, regardless of sparseness or membership in a `column_set`.</span></span> <span data-ttu-id="302e0-123">Essa ação pode retornar um número muito grande de linhas.</span><span class="sxs-lookup"><span data-stu-id="302e0-123">This might return a very large number of rows.</span></span>|<span data-ttu-id="302e0-124">Defina o campo de descritor SQL_SOPT_SS_NAME_SCOPE como SQL_SS_NAME_SCOPE_EXTENDED e chamar [SQLColumns](../../native-client-odbc-api/sqlcolumns.md) (ODBC).</span><span class="sxs-lookup"><span data-stu-id="302e0-124">Set the descriptor field SQL_SOPT_SS_NAME_SCOPE to SQL_SS_NAME_SCOPE_EXTENDED and call [SQLColumns](../../native-client-odbc-api/sqlcolumns.md) (ODBC).</span></span><br /><br /> <span data-ttu-id="302e0-125">Chame IDBSchemaRowset:: GetRowset para o conjunto de linhas de esquema de DBSCHEMA_COLUMNS_EXTENDED (OLE DB).</span><span class="sxs-lookup"><span data-stu-id="302e0-125">Call IDBSchemaRowset::GetRowset for the DBSCHEMA_COLUMNS_EXTENDED schema rowset (OLE DB).</span></span><br /><br /> <span data-ttu-id="302e0-126">Esse cenário não é possível com um aplicativo que usa o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client de uma versão anterior ao [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302e0-126">This scenario is not possible from an application that uses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client from a release earlier than [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="302e0-127">Entretanto, esse aplicativo poderia consultar exibições de sistema diretamente.</span><span class="sxs-lookup"><span data-stu-id="302e0-127">However, such an application could query system views directly.</span></span>|  
|<span data-ttu-id="302e0-128">Recuperar metadados somente para colunas que são membros de um `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-128">Retrieve metadata only for columns that are members of a `column_set`.</span></span> <span data-ttu-id="302e0-129">Essa ação pode retornar um número muito grande de linhas.</span><span class="sxs-lookup"><span data-stu-id="302e0-129">This might return a very large number of rows.</span></span>|<span data-ttu-id="302e0-130">Defina o campo de descritor SQL_SOPT_SS_NAME_SCOPE como SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET e chamar SQLColumns (ODBC).</span><span class="sxs-lookup"><span data-stu-id="302e0-130">Set the descriptor field SQL_SOPT_SS_NAME_SCOPE to SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET and call SQLColumns (ODBC).</span></span><br /><br /> <span data-ttu-id="302e0-131">Chame IDBSchemaRowset:: GetRowset para o conjunto de linhas de esquema de DBSCHEMA_SPARSE_COLUMN_SET (OLE DB).</span><span class="sxs-lookup"><span data-stu-id="302e0-131">Call IDBSchemaRowset::GetRowset for the DBSCHEMA_SPARSE_COLUMN_SET schema rowset (OLE DB).</span></span><br /><br /> <span data-ttu-id="302e0-132">Esse cenário não é possível com um aplicativo que usa o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client de uma versão anterior ao [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302e0-132">This scenario is not possible from an application that uses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client from a release earlier than [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="302e0-133">Entretanto, esse aplicativo poderia consultar exibições de sistema.</span><span class="sxs-lookup"><span data-stu-id="302e0-133">However, such an application could query system views.</span></span>|  
|<span data-ttu-id="302e0-134">Determinar se uma coluna está esparsa.</span><span class="sxs-lookup"><span data-stu-id="302e0-134">Determine whether a column is sparse.</span></span>|<span data-ttu-id="302e0-135">Consulte a coluna SS_IS_SPARSE do conjunto de resultados SQLColumns (ODBC).</span><span class="sxs-lookup"><span data-stu-id="302e0-135">Consult the SS_IS_SPARSE column of the SQLColumns result set (ODBC).</span></span><br /><br /> <span data-ttu-id="302e0-136">Consulte a coluna SS_IS_SPARSE do conjunto de linhas de esquema de DBSCHEMA_COLUMNS (OLE DB).</span><span class="sxs-lookup"><span data-stu-id="302e0-136">Consult the SS_IS_SPARSE column of the DBSCHEMA_COLUMNS schema rowset (OLE DB).</span></span><br /><br /> <span data-ttu-id="302e0-137">Esse cenário não é possível com um aplicativo que usa o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client de uma versão anterior ao [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302e0-137">This scenario is not possible from an application that uses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client from a release earlier than [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="302e0-138">Entretanto, esse aplicativo poderia consultar exibições de sistema.</span><span class="sxs-lookup"><span data-stu-id="302e0-138">However, such an application could query system views.</span></span>|  
|<span data-ttu-id="302e0-139">Determinar se uma coluna é um `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-139">Determine if a column is a `column_set`.</span></span>|<span data-ttu-id="302e0-140">Consulte a coluna SS_IS_COLUMN_SET do conjunto de resultados SQLColumns.</span><span class="sxs-lookup"><span data-stu-id="302e0-140">Consult the SS_IS_COLUMN_SET column of the SQLColumns result set.</span></span> <span data-ttu-id="302e0-141">Ou então, consulte o atributo de coluna específico do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], SQL_CA_SS_IS_COLUMN_SET (ODBC).</span><span class="sxs-lookup"><span data-stu-id="302e0-141">Or, consult the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific column attribute SQL_CA_SS_IS_COLUMN_SET (ODBC).</span></span><br /><br /> <span data-ttu-id="302e0-142">Consulte a coluna SS_IS_COLUMN_SET do conjunto de linhas de esquema de DBSCHEMA_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="302e0-142">Consult the SS_IS_COLUMN_SET column of the DBSCHEMA_COLUMNS schema rowset.</span></span> <span data-ttu-id="302e0-143">Ou então, confira *dwFlags* retornado por IColumnsinfo::GetColumnInfo ou DBCOLUMNFLAGS no conjunto de linhas retornado por IColumnsRowset::GetColumnsRowset.</span><span class="sxs-lookup"><span data-stu-id="302e0-143">Or, consult *dwFlags* returned by IColumnsinfo::GetColumnInfo or DBCOLUMNFLAGS in the rowset returned by IColumnsRowset::GetColumnsRowset.</span></span> <span data-ttu-id="302e0-144">Para colunas `column_set`, DBCOLUMNFLAGS_SS_ISCOLUMNSET será definido (OLE DB).</span><span class="sxs-lookup"><span data-stu-id="302e0-144">For `column_set` columns, DBCOLUMNFLAGS_SS_ISCOLUMNSET will be set (OLE DB).</span></span><br /><br /> <span data-ttu-id="302e0-145">Esse cenário não é possível com um aplicativo que usa o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client de uma versão anterior ao [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302e0-145">This scenario is not possible from an application that uses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client from a release earlier than [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="302e0-146">Entretanto, esse aplicativo poderia consultar exibições de sistema.</span><span class="sxs-lookup"><span data-stu-id="302e0-146">However, such an application could query system views.</span></span>|  
|<span data-ttu-id="302e0-147">Importar e exportar colunas esparsas por BCP para uma tabela sem `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-147">Import and export of sparse columns by BCP for a table with no `column_set`.</span></span>|<span data-ttu-id="302e0-148">Nenhuma alteração em comportamento de versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="302e0-148">No change in behavior from previous versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>|  
|<span data-ttu-id="302e0-149">Importar e exportar colunas esparsas por BCP para uma tabela com `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-149">Import and export of sparse columns by BCP for a table with a `column_set`.</span></span>|<span data-ttu-id="302e0-150">O `column_set` é importado e exportado da mesma maneira que o XML; ou seja, como `varbinary(max)` se fosse associado como um tipo binário, ou como `nvarchar(max)` se fosse associado como um `char` tipo ou **WCHAR** .</span><span class="sxs-lookup"><span data-stu-id="302e0-150">The `column_set` is imported and exported in the same way as XML; that is, as `varbinary(max)` if bound as a binary type, or as `nvarchar(max)` if bound as a `char` or **wchar** type.</span></span><br /><br /> <span data-ttu-id="302e0-151">Colunas que são membros do `column_set` esparso não são exportadas como colunas distintas; elas só são exportadas no valor do `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-151">Columns that are members of the sparse `column_set` are not exported as distinct columns; they are only exported in the value of the `column_set`.</span></span>|  
|<span data-ttu-id="302e0-152">Comportamento de `queryout` para BCP.</span><span class="sxs-lookup"><span data-stu-id="302e0-152">`queryout` behavior for BCP.</span></span>|<span data-ttu-id="302e0-153">Nenhuma alteração na manipulação de colunas nomeadas explicitamente de versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="302e0-153">No change in the handling of explicitly named columns from previous versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span><br /><br /> <span data-ttu-id="302e0-154">Cenários que envolvem importação e exportação entre tabelas com esquemas diferentes podem exigir manipulação especial.</span><span class="sxs-lookup"><span data-stu-id="302e0-154">Scenarios involving import and export between tables with different schemas may require special handling.</span></span><br /><br /> <span data-ttu-id="302e0-155">Para obter mais informações sobre BCP, consulte Suporte de BCP (cópia em massa) a colunas esparsas, mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="302e0-155">For more information about BCP, see Bulk Copy (BCP) Support for Sparse Columns, later in this topic.</span></span>|  
  
## <a name="down-level-client-behavior"></a><span data-ttu-id="302e0-156">Comportamento do cliente de versão anterior</span><span class="sxs-lookup"><span data-stu-id="302e0-156">Down-Level Client Behavior</span></span>  
 <span data-ttu-id="302e0-157">Os clientes de nível inferior retornarão metadados somente para colunas que não sejam membros do esparso `column_set` para SQLColumns e DBSCHMA_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="302e0-157">Down-level clients will return metadata only for columns that are not members of the sparse `column_set` for SQLColumns and DBSCHMA_COLUMNS.</span></span> <span data-ttu-id="302e0-158">Os conjuntos de linhas de esquema OLE DB adicionais introduzidos no [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] Native Client não estarão disponíveis, nem as modificações em SQLColumns no ODBC via SQL_SOPT_SS_NAME_SCOPE.</span><span class="sxs-lookup"><span data-stu-id="302e0-158">The additional OLE DB schema rowsets introduced in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] Native Client will not be available, nor will the modifications to SQLColumns in ODBC via SQL_SOPT_SS_NAME_SCOPE.</span></span>  
  
 <span data-ttu-id="302e0-159">Os clientes de nível inferior podem acessar as colunas que são membros do `column_set` esparso por nome, e a coluna `column_set` poderá ser acessada como uma coluna XML por clientes do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302e0-159">Down-level clients can access columns that are members of the sparse `column_set` by name, and the `column_set` column will be accessible as an XML column to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] clients.</span></span>  
  
## <a name="bulk-copy-bcp-support-for-sparse-columns"></a><span data-ttu-id="302e0-160">Suporte de BCP (cópia em massa) a colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="302e0-160">Bulk Copy (BCP) Support for Sparse Columns</span></span>  
 <span data-ttu-id="302e0-161">Não há nenhuma alteração à API de BCP em ODBC ou OLE DB para as colunas esparsas ou os recursos de `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-161">There are no changes to the BCP API in either ODBC or OLE DB for the sparse columns or `column_set` features.</span></span>  
  
 <span data-ttu-id="302e0-162">Se uma tabela tiver um `column_set`, as colunas esparsas não serão tratadas como colunas distintas.</span><span class="sxs-lookup"><span data-stu-id="302e0-162">If a table has a `column_set`, sparse columns are not handled as distinct columns.</span></span> <span data-ttu-id="302e0-163">Os valores de todas as colunas esparsas são incluídos no valor de `column_set` , que é exportado da mesma maneira que uma coluna XML; ou seja, como `varbinary(max)` se estiver associado como um tipo binário, ou como `nvarchar(max)` se estiver associado como um `char` ou um tipo **WCHAR** ).</span><span class="sxs-lookup"><span data-stu-id="302e0-163">The values of all sparse columns are included in the value of the `column_set`, which is exported in the same way as an XML column; that is, as `varbinary(max)` if bound as a binary type, or as `nvarchar(max)` if bound as a `char` or **wchar** type).</span></span> <span data-ttu-id="302e0-164">Na importação, o valor de `column_set` deve estar de acordo com o esquema do `column_set`.</span><span class="sxs-lookup"><span data-stu-id="302e0-164">On import, the `column_set` value must conform to the schema of the `column_set`.</span></span>  
  
 <span data-ttu-id="302e0-165">Para operações de `queryout`, não há alterações na maneira como são tratadas as colunas referenciadas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="302e0-165">For `queryout` operations, there is no change to the way explicitly referenced columns are handled.</span></span> <span data-ttu-id="302e0-166">As colunas de `column_set` têm o mesmo comportamento das colunas XML e a dispersão não tem efeito sobre o tratamento de colunas esparsas nomeadas.</span><span class="sxs-lookup"><span data-stu-id="302e0-166">`column_set` columns have the same behavior as XML columns and sparseness has no effect on the handling of named sparse columns.</span></span>  
  
 <span data-ttu-id="302e0-167">Entretanto, se `queryout` for usado para exportação e você referenciar colunas esparsas que são membros do conjunto de colunas esparsas por nome, não será possível executar uma importação direta para uma tabela de estrutura semelhante.</span><span class="sxs-lookup"><span data-stu-id="302e0-167">However, if `queryout` is used for export and you reference sparse columns that are members of the sparse column set by name, you cannot perform a direct import into a similarly structured table.</span></span> <span data-ttu-id="302e0-168">Isso ocorre porque o BCP usa metadados consistentes com uma operação \*\*Select \* \*\* para a importação e não pode corresponder `column_set` colunas de membros a esses metadados.</span><span class="sxs-lookup"><span data-stu-id="302e0-168">This is because BCP uses metadata consistent with a **select \*** operation for the import and is unable to match `column_set` member columns with this metadata.</span></span> <span data-ttu-id="302e0-169">Para importar as colunas de membro de `column_set` individualmente, você precisa definir uma exibição na tabela que referencia as colunas de `column_set` desejadas, além de executar a operação de importação usando a exibição.</span><span class="sxs-lookup"><span data-stu-id="302e0-169">To import `column_set` member columns individually, you must define a view on the table that references the desired `column_set` columns, and you must perform the import operation using the view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302e0-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="302e0-170">See Also</span></span>  
 [<span data-ttu-id="302e0-171">Programação do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="302e0-171">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  