---
title: Editor de lista de propriedades de pesquisa | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.spl.searchpropertylisteditor.f1
ms.assetid: 0f3ced6e-0dfd-49fc-b175-82378c3d668e
author: rothja
ms.author: jroth
ms.openlocfilehash: 6c68ec986e2c6f4f53dfec7f188ba2a120532ae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572673"
---
# <a name="search-property-list-editor"></a><span data-ttu-id="4c231-102">Editor da Lista de Propriedades de Pesquisa</span><span class="sxs-lookup"><span data-stu-id="4c231-102">Search Property List Editor</span></span>
  <span data-ttu-id="4c231-103">Use esta caixa de diálogo para adicionar ou excluir propriedades em uma lista de propriedades de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4c231-103">Use this dialog box to add or delete search properties in a search property list.</span></span>  
  
## <a name="to-use-sql-server-management-studio-to-manage-search-property-lists"></a><span data-ttu-id="4c231-104">Para usar o SQL Server Management Studio para gerenciar listas de propriedades de pesquisa</span><span class="sxs-lookup"><span data-stu-id="4c231-104">To Use SQL Server Management Studio to Manage Search Property Lists</span></span>  
 <span data-ttu-id="4c231-105">Para obter informações sobre como criar, exibir ou excluir uma lista de propriedades de pesquisa e sobre como configurar um índice de texto completo para pesquisa de propriedades, consulte [Pesquisar Propriedades de documentos com listas de propriedades de pesquisa](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="4c231-105">For information about how to create, view, or delete a search property list, and about how to configure a full-text index for property searching, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c231-106">Opções</span><span class="sxs-lookup"><span data-stu-id="4c231-106">Options</span></span>  
 <span data-ttu-id="4c231-107">**Nome da propriedade**</span><span class="sxs-lookup"><span data-stu-id="4c231-107">**Property Name**</span></span>  
 <span data-ttu-id="4c231-108">Especifique o nome a ser usado para identificar a propriedade em consultas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4c231-108">Specify the name to be used to identify the property in full-text queries.</span></span> <span data-ttu-id="4c231-109">Um nome de propriedade pode conter espaços internos.</span><span class="sxs-lookup"><span data-stu-id="4c231-109">A property name can contain internal spaces.</span></span> <span data-ttu-id="4c231-110">O tamanho máximo do **Nome da Propriedade** é de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="4c231-110">The maximum length of **Property Name** is 256 characters.</span></span> <span data-ttu-id="4c231-111">Esse nome pode ser um nome amigável, como "Autor" ou "Endereço Residencial" ou pode ser o nome canônico do Windows da propriedade, como `System.Author` ou `System.Contact.HomeAddress`.</span><span class="sxs-lookup"><span data-stu-id="4c231-111">This name can be a user-friendly name, such as "Author" or "Home Address", or it can be the Windows canonical name of the property, such as `System.Author` or `System.Contact.HomeAddress`.</span></span> <span data-ttu-id="4c231-112">O**Nome da Propriedade** deve identificar a propriedade exclusivamente dentro do conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="4c231-112">**Property Name** must uniquely identify the property within the property set.</span></span>  
  
 <span data-ttu-id="4c231-113">Os desenvolvedores usam o nome da propriedade para identificar a propriedade no predicado [CONTAINS](/sql/t-sql/queries/contains-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4c231-113">Developers use the property name to identify the property in the [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate.</span></span> <span data-ttu-id="4c231-114">Portanto, ao adicionar uma propriedade, é importante especificar um valor que represente significativamente a propriedade.</span><span class="sxs-lookup"><span data-stu-id="4c231-114">Therefore, when adding a property it is important to specify a value that meaningfully represents the property.</span></span>  
  
 <span data-ttu-id="4c231-115">**GUID do conjunto de propriedades**</span><span class="sxs-lookup"><span data-stu-id="4c231-115">**Property Set GUID**</span></span>  
 <span data-ttu-id="4c231-116">Especifique o identificador do conjunto de propriedades ao qual a propriedade pertence.</span><span class="sxs-lookup"><span data-stu-id="4c231-116">Specify the identifier of the property set to which the property belongs.</span></span> <span data-ttu-id="4c231-117">Esse é um GUID (identificador global exclusivo).</span><span class="sxs-lookup"><span data-stu-id="4c231-117">This is a globally unique identifier (GUID).</span></span> <span data-ttu-id="4c231-118">Um conjunto de propriedades é um grupo de propriedades logicamente relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4c231-118">A property set is a group of logically related properties.</span></span> <span data-ttu-id="4c231-119">Para obter informações sobre como obter esse valor, consulte “Comentários”, posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4c231-119">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
 <span data-ttu-id="4c231-120">**ID Int de Propriedade**</span><span class="sxs-lookup"><span data-stu-id="4c231-120">**Property Int ID**</span></span>  
 <span data-ttu-id="4c231-121">Especifique o identificador inteiro da propriedade.</span><span class="sxs-lookup"><span data-stu-id="4c231-121">Specify the property integer identifier of the property.</span></span> <span data-ttu-id="4c231-122">Esse valor pré-atribuído é um inteiro positivo que é exclusivo dentro do conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="4c231-122">This pre-assigned value is a positive integer that is unique within the property set.</span></span> <span data-ttu-id="4c231-123">Para obter informações sobre como obter esse valor, consulte “Comentários”, posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4c231-123">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c231-124">Propriedades de documento que usam identificadores de cadeia de caracteres não têm suporte da pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4c231-124">Document properties that use string identifiers are not supported by full-text search.</span></span>  
  
 <span data-ttu-id="4c231-125">**Descrição da Propriedade**</span><span class="sxs-lookup"><span data-stu-id="4c231-125">**Property Description**</span></span>  
 <span data-ttu-id="4c231-126">Opcionalmente, especifique uma descrição da propriedade.</span><span class="sxs-lookup"><span data-stu-id="4c231-126">Optionally, specify a description of the property.</span></span> <span data-ttu-id="4c231-127">Esta é uma cadeia de caracteres de até 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="4c231-127">This is a string of up to 512 characters.</span></span> <span data-ttu-id="4c231-128">Por exemplo, uma descrição pode conter informações sobre o conjunto de propriedades da propriedade ou informações sobre uma propriedade que não é evidente a partir de seu nome.</span><span class="sxs-lookup"><span data-stu-id="4c231-128">For example, a description could contain information about the property set of the property or information about a property that is not evident from its name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c231-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="4c231-129">Remarks</span></span>  
 <span data-ttu-id="4c231-130">Para adicionar uma propriedade de pesquisa a uma lista de propriedades de pesquisa, você deve especificar o GUID (identificador global exclusivo) do conjunto de propriedades ao qual a propriedade pertence e o identificador inteiro da propriedade.</span><span class="sxs-lookup"><span data-stu-id="4c231-130">To add a search property to a search property list, you must specify the globally unique identifier (GUID) of the property set to which the property belongs and the property integer identifier of the property.</span></span> <span data-ttu-id="4c231-131">Uma determinada combinação disso deve ser exclusiva em uma determinada lista de propriedades de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4c231-131">A given combination of these must be unique in a given search property list.</span></span> <span data-ttu-id="4c231-132">Se você tentar adicionar uma combinação existente, haverá falha na operação e um erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="4c231-132">If you try to add an existing combination, the operation fails and issues an error.</span></span> <span data-ttu-id="4c231-133">Isso significa que você pode configurar apenas um nome para uma determinada propriedade.</span><span class="sxs-lookup"><span data-stu-id="4c231-133">This means that you can configure only one name for a given property.</span></span>  
  
 <span data-ttu-id="4c231-134">A descrição da propriedade é opcional.</span><span class="sxs-lookup"><span data-stu-id="4c231-134">The property description is optional.</span></span>  
  
 <span data-ttu-id="4c231-135">**Para configurar uma lista de propriedades de pesquisa para um índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="4c231-135">**To configure a search property list for a full-text index**</span></span>  
  
-   [<span data-ttu-id="4c231-136">Pesquisar propriedades de documento com listas de propriedades de pesquisa</span><span class="sxs-lookup"><span data-stu-id="4c231-136">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
## <a name="permissions"></a><span data-ttu-id="4c231-137">Permissões</span><span class="sxs-lookup"><span data-stu-id="4c231-137">Permissions</span></span>  
 <span data-ttu-id="4c231-138">Consulte [ALTER Search Property LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4c231-138">See [ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c231-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c231-139">See Also</span></span>  
 <span data-ttu-id="4c231-140">[ALTERAR lista de propriedades de pesquisa &#40;&#41;Transact-SQL](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c231-140">[ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span></span>  
 <span data-ttu-id="4c231-141">[Pesquisar Propriedades do documento com listas de propriedades de pesquisa](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span><span class="sxs-lookup"><span data-stu-id="4c231-141">[Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span></span>  
 [<span data-ttu-id="4c231-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c231-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
  
