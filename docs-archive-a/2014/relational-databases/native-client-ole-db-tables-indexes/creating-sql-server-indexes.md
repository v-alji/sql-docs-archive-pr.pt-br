---
title: Criar índices do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- CreateIndex function
- constraints [OLE DB]
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
- adding indexes
ms.assetid: 6239d440-2818-4b98-bb79-732dced41952
author: rothja
ms.author: jroth
ms.openlocfilehash: 3693355eec7a290c03658c10db500161aa52062d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684682"
---
# <a name="creating-sql-server-indexes"></a><span data-ttu-id="f0aff-102">Criando índices do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0aff-102">Creating SQL Server Indexes</span></span>
  <span data-ttu-id="f0aff-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe a função **IIndexDefinition:: CreateIndex** , permitindo que os consumidores definam novos índices em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelas.</span><span class="sxs-lookup"><span data-stu-id="f0aff-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::CreateIndex** function, allowing consumers to define new indexes on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="f0aff-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo cria índices de tabela como índices ou restrições.</span><span class="sxs-lookup"><span data-stu-id="f0aff-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates table indexes as either indexes or constraints.</span></span> <span data-ttu-id="f0aff-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concede privilégios para criação de restrições ao proprietário da tabela, ao proprietário do banco de dados e aos membros de determinadas funções administrativas.</span><span class="sxs-lookup"><span data-stu-id="f0aff-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gives constraint-creation privilege to the table owner, database owner, and members of certain administrative roles.</span></span> <span data-ttu-id="f0aff-106">Por padrão, apenas o proprietário da tabela pode criar um índice em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="f0aff-106">By default, only the table owner can create an index on a table.</span></span> <span data-ttu-id="f0aff-107">Portanto, o êxito ou a falha de **CreateIndex** depende não apenas dos direitos de acesso do usuário do aplicativo, mas também do tipo de índice criado.</span><span class="sxs-lookup"><span data-stu-id="f0aff-107">Therefore, the success or failure of **CreateIndex** depends not only on the application user's access rights but also on the type of index created.</span></span>  
  
 <span data-ttu-id="f0aff-108">Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no parâmetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="f0aff-108">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="f0aff-109">O membro *eKind* de *pTableID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="f0aff-109">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="f0aff-110">O parâmetro *pIndexID* pode ser nulo e, se for, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo criará um nome exclusivo para o índice.</span><span class="sxs-lookup"><span data-stu-id="f0aff-110">The *pIndexID* parameter can be NULL, and if it is, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates a unique name for the index.</span></span> <span data-ttu-id="f0aff-111">O consumidor pode capturar o nome do índice especificando um ponteiro válido para um DBID no parâmetro *ppIndexID*.</span><span class="sxs-lookup"><span data-stu-id="f0aff-111">The consumer can capture the name of the index by specifying a valid pointer to a DBID in the *ppIndexID* parameter.</span></span>  
  
 <span data-ttu-id="f0aff-112">O consumidor pode especificar o nome do índice como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* do parâmetro *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="f0aff-112">The consumer can specify the index name as a Unicode character string in the *pwszName* member of the *uName* union of the *pIndexID* parameter.</span></span> <span data-ttu-id="f0aff-113">O membro *eKind* de *pIndexID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="f0aff-113">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="f0aff-114">O consumidor especifica a coluna ou as colunas que participam do índice por nome.</span><span class="sxs-lookup"><span data-stu-id="f0aff-114">The consumer specifies the column or columns participating in the index by name.</span></span> <span data-ttu-id="f0aff-115">Para cada estrutura DBINDEXCOLUMNDESC usada em **CreateIndex**, o membro *eKind* da *pColumnID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="f0aff-115">For each DBINDEXCOLUMNDESC structure used in **CreateIndex**, the *eKind* member of the *pColumnID* must be DBKIND_NAME.</span></span> <span data-ttu-id="f0aff-116">O nome da coluna é especificado como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="f0aff-116">The name of the column is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *pColumnID*.</span></span>  
  
 <span data-ttu-id="f0aff-117">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a ordem crescente em valores no índice.</span><span class="sxs-lookup"><span data-stu-id="f0aff-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support ascending order on values in the index.</span></span> <span data-ttu-id="f0aff-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna E_INVALIDARG se o consumidor especifica DBINDEX_COL_ORDER_DESC em qualquer estrutura DBINDEXCOLUMNDESC.</span><span class="sxs-lookup"><span data-stu-id="f0aff-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns E_INVALIDARG if the consumer specifies DBINDEX_COL_ORDER_DESC in any DBINDEXCOLUMNDESC structure.</span></span>  
  
 <span data-ttu-id="f0aff-119">**CreateIndex** interpreta as propriedades de índice, conforme mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0aff-119">**CreateIndex** interprets index properties as follows.</span></span>  
  
|<span data-ttu-id="f0aff-120">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="f0aff-120">Property ID</span></span>|<span data-ttu-id="f0aff-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0aff-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f0aff-122">DBPROP_INDEX_AUTOUPDATE</span><span class="sxs-lookup"><span data-stu-id="f0aff-122">DBPROP_INDEX_AUTOUPDATE</span></span>|<span data-ttu-id="f0aff-123">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-123">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-124">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-124">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-125">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-125">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-126">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-126">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-127">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-127">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-128">DBPROP_INDEX_CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="f0aff-128">DBPROP_INDEX_CLUSTERED</span></span>|<span data-ttu-id="f0aff-129">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-129">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-130">Padrão: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="f0aff-130">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="f0aff-131">Descrição: controla o clustering de índice.</span><span class="sxs-lookup"><span data-stu-id="f0aff-131">Description: Controls index clustering.</span></span><br /><br /> <span data-ttu-id="f0aff-132">VARIANT_TRUE: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo tenta criar um índice clusterizado na [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela.</span><span class="sxs-lookup"><span data-stu-id="f0aff-132">VARIANT_TRUE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a clustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="f0aff-133">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a no máximo um índice clusterizado em qualquer tabela.</span><span class="sxs-lookup"><span data-stu-id="f0aff-133">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports at most one clustered index on any table.</span></span><br /><br /> <span data-ttu-id="f0aff-134">VARIANT_FALSE: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo tenta criar um índice não clusterizado na [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela.</span><span class="sxs-lookup"><span data-stu-id="f0aff-134">VARIANT_FALSE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a nonclustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|<span data-ttu-id="f0aff-135">DBPROP_INDEX_FILLFACTOR</span><span class="sxs-lookup"><span data-stu-id="f0aff-135">DBPROP_INDEX_FILLFACTOR</span></span>|<span data-ttu-id="f0aff-136">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-136">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-137">Padrão: 0</span><span class="sxs-lookup"><span data-stu-id="f0aff-137">Default: 0</span></span><br /><br /> <span data-ttu-id="f0aff-138">Descrição: especifica a porcentagem de uma página de índice usada para armazenamento.</span><span class="sxs-lookup"><span data-stu-id="f0aff-138">Description: Specifies the percentage of an index page used for storage.</span></span> <span data-ttu-id="f0aff-139">Para obter mais informações, confira [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0aff-139">For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span></span><br /><br /> <span data-ttu-id="f0aff-140">O tipo da variante é VT_I4.</span><span class="sxs-lookup"><span data-stu-id="f0aff-140">The type of the variant is VT_I4.</span></span> <span data-ttu-id="f0aff-141">O valor deve ser maior ou igual a 1 e menor ou igual a 100.</span><span class="sxs-lookup"><span data-stu-id="f0aff-141">The value must be greater than or equal to 1 and less than or equal to 100.</span></span>|  
|<span data-ttu-id="f0aff-142">DBPROP_INDEX_INITIALIZE</span><span class="sxs-lookup"><span data-stu-id="f0aff-142">DBPROP_INDEX_INITIALIZE</span></span>|<span data-ttu-id="f0aff-143">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-143">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-144">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-144">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-145">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-145">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-146">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-146">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-147">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-147">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-148">DBPROP_INDEX_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="f0aff-148">DBPROP_INDEX_NULLCOLLATION</span></span>|<span data-ttu-id="f0aff-149">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-149">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-150">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-150">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-151">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-151">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-152">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-152">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-153">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-153">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-154">DBPROP_INDEX_NULLS</span><span class="sxs-lookup"><span data-stu-id="f0aff-154">DBPROP_INDEX_NULLS</span></span>|<span data-ttu-id="f0aff-155">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-155">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-156">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-156">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-157">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-157">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-158">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-158">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-159">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-159">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-160">DBPROP_INDEX_PRIMARYKEY</span><span class="sxs-lookup"><span data-stu-id="f0aff-160">DBPROP_INDEX_PRIMARYKEY</span></span>|<span data-ttu-id="f0aff-161">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-161">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-162">Padrão: VARIANT_FALSE Descrição: cria o índice como uma integridade referencial, restrição PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="f0aff-162">Default: VARIANT_FALSE Description: Creates the index as a referential integrity, PRIMARY KEY constraint.</span></span><br /><br /> <span data-ttu-id="f0aff-163">VARIANT_TRUE: o índice é criado para dar suporte à restrição PRIMARY KEY da tabela.</span><span class="sxs-lookup"><span data-stu-id="f0aff-163">VARIANT_TRUE: The index is created to support the PRIMARY KEY constraint of the table.</span></span> <span data-ttu-id="f0aff-164">As colunas devem ser não nulas.</span><span class="sxs-lookup"><span data-stu-id="f0aff-164">The columns must be nonnullable.</span></span><br /><br /> <span data-ttu-id="f0aff-165">VARIANT_FALSE: o índice não é usado como uma restrição PRIMARY KEY para valores de linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="f0aff-165">VARIANT_FALSE: The index is not used as a PRIMARY KEY constraint for row values in the table.</span></span>|  
|<span data-ttu-id="f0aff-166">DBPROP_INDEX_SORTBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="f0aff-166">DBPROP_INDEX_SORTBOOKMARKS</span></span>|<span data-ttu-id="f0aff-167">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-167">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-168">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-168">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-169">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-169">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-170">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-170">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-171">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-171">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-172">DBPROP_INDEX_TEMPINDEX</span><span class="sxs-lookup"><span data-stu-id="f0aff-172">DBPROP_INDEX_TEMPINDEX</span></span>|<span data-ttu-id="f0aff-173">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-173">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-174">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-174">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-175">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-175">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-176">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-176">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-177">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-177">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-178">DBPROP_INDEX_TYPE</span><span class="sxs-lookup"><span data-stu-id="f0aff-178">DBPROP_INDEX_TYPE</span></span>|<span data-ttu-id="f0aff-179">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-179">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-180">Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="f0aff-180">Default: None</span></span><br /><br /> <span data-ttu-id="f0aff-181">Descrição: o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não oferece suporte a essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f0aff-181">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="f0aff-182">As tentativas de definir a propriedade em **CreateIndex** geram um valor retornado DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="f0aff-182">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="f0aff-183">O membro *dwStatus* da estrutura de propriedade indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="f0aff-183">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="f0aff-184">DBPROP_INDEX_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="f0aff-184">DBPROP_INDEX_UNIQUE</span></span>|<span data-ttu-id="f0aff-185">L/G: Leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f0aff-185">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="f0aff-186">Padrão: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="f0aff-186">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="f0aff-187">Descrição: cria o índice como uma restrição UNIQUE na coluna ou nas colunas participantes.</span><span class="sxs-lookup"><span data-stu-id="f0aff-187">Description: Creates the index as a UNIQUE constraint on the participating column or columns.</span></span><br /><br /> <span data-ttu-id="f0aff-188">VARIANT_TRUE: o índice é usado para restringir valores de linha na tabela de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="f0aff-188">VARIANT_TRUE: The index is used to uniquely constrain row values in the table.</span></span><br /><br /> <span data-ttu-id="f0aff-189">VARIANT_FALSE: o índice não restringe valores de linha de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="f0aff-189">VARIANT_FALSE: The index does not uniquely constrain row values.</span></span>|  
  
 <span data-ttu-id="f0aff-190">No conjunto de propriedades específico do provedor DBPROPSET_SQLSERVERINDEX, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo define a propriedade de informações da fonte de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0aff-190">In the provider-specific property set DBPROPSET_SQLSERVERINDEX, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information property.</span></span>  
  
|<span data-ttu-id="f0aff-191">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="f0aff-191">Property ID</span></span>|<span data-ttu-id="f0aff-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0aff-192">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f0aff-193">SSPROP_INDEX_XML</span><span class="sxs-lookup"><span data-stu-id="f0aff-193">SSPROP_INDEX_XML</span></span>|<span data-ttu-id="f0aff-194">Tipo: VT_BOOL (leitura/gravação)</span><span class="sxs-lookup"><span data-stu-id="f0aff-194">Type: VT_BOOL (R/W)</span></span><br /><br /> <span data-ttu-id="f0aff-195">Padrão: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="f0aff-195">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="f0aff-196">Descrição: quando esta propriedade é especificada com um valor VARIANT_TRUE com IIndexDefinition::CreateIndex, ela resulta na criação de um índice xml principal correspondente à coluna que está sendo indexada.</span><span class="sxs-lookup"><span data-stu-id="f0aff-196">Description: When this property is specified with a value of VARIANT_TRUE with IIndexDefinition::CreateIndex, it results in a primary xml index being created corresponding to the column being indexed.</span></span> <span data-ttu-id="f0aff-197">Se essa propriedade for VARIANT_TRUE, cIndexColumnDescs deverá ser 1, caso contrário, será um erro.</span><span class="sxs-lookup"><span data-stu-id="f0aff-197">If this property is VARIANT_TRUE, cIndexColumnDescs should be 1, otherwise it is an error.</span></span>|  
  
 <span data-ttu-id="f0aff-198">Este exemplo cria um índice de chave primária:</span><span class="sxs-lookup"><span data-stu-id="f0aff-198">This example creates a primary key index:</span></span>  
  
```  
// This CREATE TABLE statement shows the referential integrity and   
// PRIMARY KEY constraint on the OrderDetails table that will be created   
// by the following example code.  
//  
// CREATE TABLE OrderDetails  
// (  
//    OrderID      int      NOT NULL  
//    ProductID   int      NOT NULL  
//        CONSTRAINT PK_OrderDetails  
//        PRIMARY KEY CLUSTERED (OrderID, ProductID),  
//    UnitPrice   money      NOT NULL,  
//    Quantity   int      NOT NULL,  
//    Discount   decimal(2,2)   NOT NULL  
//        DEFAULT 0  
// )  
//  
HRESULT CreatePrimaryKey  
    (  
    IIndexDefinition* pIIndexDefinition  
    )  
    {  
    HRESULT             hr = S_OK;  
  
    DBID                dbidTable;  
    DBID                dbidIndex;  
    const ULONG         nCols = 2;  
    ULONG               nCol;  
    const ULONG         nProps = 2;  
    ULONG               nProp;  
  
    DBINDEXCOLUMNDESC   dbidxcoldesc[nCols];  
    DBPROP              dbpropIndex[nProps];  
    DBPROPSET           dbpropset;  
  
    DBID*               pdbidIndexOut = NULL;  
  
    // Set up identifiers for the table and index.  
    dbidTable.eKind = DBKIND_NAME;  
    dbidTable.uName.pwszName = L"OrderDetails";  
  
    dbidIndex.eKind = DBKIND_NAME;  
    dbidIndex.uName.pwszName = L"PK_OrderDetails";  
  
    // Set up column identifiers.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        dbidxcoldesc[nCol].pColumnID = new DBID;  
        dbidxcoldesc[nCol].pColumnID->eKind = DBKIND_NAME;  
  
        dbidxcoldesc[nCol].eIndexColOrder = DBINDEX_COL_ORDER_ASC;  
        }  
    dbidxcoldesc[0].pColumnID->uName.pwszName = L"OrderID";  
    dbidxcoldesc[1].pColumnID->uName.pwszName = L"ProductID";  
  
    // Set properties for the index. The index is clustered,  
    // PRIMARY KEY.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        dbpropIndex[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        dbpropIndex[nProp].colid = DB_NULLID;  
  
        VariantInit(&(dbpropIndex[nProp].vValue));  
  
        dbpropIndex[nProp].vValue.vt = VT_BOOL;  
        }  
    dbpropIndex[0].dwPropertyID = DBPROP_INDEX_CLUSTERED;  
    dbpropIndex[0].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropIndex[1].dwPropertyID = DBPROP_INDEX_PRIMARYKEY;  
    dbpropIndex[1].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropset.rgProperties = dbpropIndex;  
    dbpropset.cProperties = nProps;  
    dbpropset.guidPropertySet = DBPROPSET_INDEX;  
  
    hr = pIIndexDefinition->CreateIndex(&dbidTable, &dbidIndex, nCols,  
        dbidxcoldesc, 1, &dbpropset, &pdbidIndexOut);  
  
    // Clean up dynamically allocated DBIDs.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        delete dbidxcoldesc[nCol].pColumnID;  
        }  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0aff-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0aff-199">See Also</span></span>  
 [<span data-ttu-id="f0aff-200">Tabelas e índices</span><span class="sxs-lookup"><span data-stu-id="f0aff-200">Tables and Indexes</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
  
