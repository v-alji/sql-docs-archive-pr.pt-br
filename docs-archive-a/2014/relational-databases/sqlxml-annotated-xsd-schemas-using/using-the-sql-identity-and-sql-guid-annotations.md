---
title: 'Usando as anotações sql: Identity e SQL: GUID | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:guid
- annotated XSD schemas, IDENTITY-type columns
- annotated XSD schemas, GUID values
- DiffGrams [SQLXML], annotations
- identity annotation
- XSD schemas [SQLXML], GUID values
- GUIDs [SQLXML]
- guid annotation
- sql:identity
- IDENTITY-type column
- XSD schemas [SQLXML], IDENTITY-type columns
- updategrams [SQLXML], GUID values
ms.assetid: 7661dfd0-6573-4692-a8f1-3597adcd33c4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc5c08f158911edb0a1a0638fc4bcee1e05a248c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573908"
---
# <a name="using-the-sqlidentity-and-sqlguid-annotations"></a><span data-ttu-id="00a58-102">Usando as anotações sql:identity e sql:guid</span><span class="sxs-lookup"><span data-stu-id="00a58-102">Using the sql:identity and sql:guid Annotations</span></span>
  <span data-ttu-id="00a58-103">Você pode especificar as `sql:identity` `sql:guid` anotações e em um esquema XSD em qualquer nó que seja mapeado para uma coluna de banco de dados no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00a58-103">You can specify the `sql:identity` and `sql:guid` annotations in an XSD schema on any node that maps to a database column in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00a58-104">Enquanto o formato de diagrama de atualização dá suporte aos atributos `updg:at-identity` e `updg:guid`, isso não ocorre com o formato DiffGram.</span><span class="sxs-lookup"><span data-stu-id="00a58-104">Whereas the updategram format supports the `updg:at-identity` and `updg:guid` attributes, the DiffGram format does not.</span></span> <span data-ttu-id="00a58-105">O atributo `updg:at-identity` define o comportamento ao atualizar uma coluna do tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="00a58-105">The `updg:at-identity` attribute defines the behavior in updating an IDENTITY-type column.</span></span> <span data-ttu-id="00a58-106">O atributo `updg:guid` permite obter um valor de GUID do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o utilizar no diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="00a58-106">The `updg:guid` attribute allows you to obtain a GUID value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and use it in the updategram.</span></span> <span data-ttu-id="00a58-107">Para obter mais informações e exemplos de trabalho, consulte [inserindo dados usando UPDATEGRAMS XML &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="00a58-107">For more information and working samples, see [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="00a58-108">As anotações `sql:identity` e `sql:guid` estendem esta funcionalidade a DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="00a58-108">The `sql:identity` and `sql:guid` annotations extend this functionality to DiffGrams.</span></span>  
  
 <span data-ttu-id="00a58-109">Quando você executa um DiffGram, ele é primeiro convertido em um diagrama de atualização e, em seguida, o diagrama de atualização é executado.</span><span class="sxs-lookup"><span data-stu-id="00a58-109">When you execute a DiffGram, it is first converted to an updategram, and then the updategram is executed.</span></span> <span data-ttu-id="00a58-110">Ao especificar as anotações `sql:identity` e `sql:guid` no esquema XSD, você está na verdade definindo o comportamento de um diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="00a58-110">By specifying the `sql:identity` and `sql:guid` annotations in the XSD schema, you are in fact defining the behavior of an updategram.</span></span> <span data-ttu-id="00a58-111">Assim, todas as anotações são descritas no contexto de um diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="00a58-111">Therefore, all the annotations are described in the context of an updategram.</span></span> <span data-ttu-id="00a58-112">As anotações podem ser usadas para DiffGrams e diagramas de atualização; entretanto, os diagramas de atualização já fornecem um modo mais avançado de tratar valores de GUID e identidade.</span><span class="sxs-lookup"><span data-stu-id="00a58-112">The annotations can be used both for DiffGrams and updategrams; however, updategrams already provide a more powerful way of handling identity and GUID values.</span></span>  
  
 <span data-ttu-id="00a58-113">As anotações `sql:identity` e `sql:guid` podem ser definidas em um elemento de conteúdo complexo.</span><span class="sxs-lookup"><span data-stu-id="00a58-113">The `sql:identity` and `sql:guid` annotations can be defined on a complex content element.</span></span>  
  
## <a name="sqlidentity-annotation"></a><span data-ttu-id="00a58-114">Anotação sql:identity</span><span class="sxs-lookup"><span data-stu-id="00a58-114">sql:identity Annotation</span></span>  
 <span data-ttu-id="00a58-115">Você pode especificar a anotação `sql:identity` no esquema XSD em qualquer nó mapeado para uma coluna de banco de dados do tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="00a58-115">You can specify the `sql:identity` annotation in the XSD schema on any node that maps to an IDENTITY-type database column.</span></span> <span data-ttu-id="00a58-116">O valor especificado para essa anotação define como a coluna de tipo de identidade é atualizada (usando o valor fornecido no updategram para modificar a coluna ou ignorando o valor; nesse caso, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valor gerado por um é usado para essa coluna).</span><span class="sxs-lookup"><span data-stu-id="00a58-116">The value specified for this annotation defines how the IDENTITY-type column is updated (either by using the value provided in the updategram to modify the column or by ignoring the value, in which case a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-generated value is used for this column).</span></span>  
  
 <span data-ttu-id="00a58-117">É possível atribuir dois valores à anotação `sql:identity`:</span><span class="sxs-lookup"><span data-stu-id="00a58-117">The `sql:identity` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="00a58-118">ignore</span><span class="sxs-lookup"><span data-stu-id="00a58-118">ignore</span></span>  
 <span data-ttu-id="00a58-119">Direciona o diagrama de atualização para ignorar qualquer valor que seja fornecido no diagrama de atualização para essa coluna e para depender do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para gerar o valor da identidade.</span><span class="sxs-lookup"><span data-stu-id="00a58-119">Directs the updategram to ignore any value that is provided in the updategram for that column and to rely on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate the identity value.</span></span>  
  
 <span data-ttu-id="00a58-120">useValue</span><span class="sxs-lookup"><span data-stu-id="00a58-120">useValue</span></span>  
 <span data-ttu-id="00a58-121">Direciona o diagrama de atualização para usar o valor que é fornecido no diagrama de atualização para atualizar a coluna do tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="00a58-121">Directs the updategram to use the value that is provided in the updategram to update the IDENTITY-type column.</span></span> <span data-ttu-id="00a58-122">Um diagrama de atualização não verifica se a coluna é um valor de identidade ou não.</span><span class="sxs-lookup"><span data-stu-id="00a58-122">An updategram does not check whether the column is an identity value or not.</span></span>  
  
 <span data-ttu-id="00a58-123">Se o diagrama de atualização especificar um valor para a coluna do tipo IDENTITY, `sql:identity="useValue"` deve ser especificado no esquema.</span><span class="sxs-lookup"><span data-stu-id="00a58-123">If the updategram specifies a value for the IDENTITY-type column, the `sql:identity="useValue"` must be specified in the schema.</span></span>  
  
## <a name="sqlguid-annotation"></a><span data-ttu-id="00a58-124">Anotação sql:guid</span><span class="sxs-lookup"><span data-stu-id="00a58-124">sql:guid Annotation</span></span>  
 <span data-ttu-id="00a58-125">Um diagrama de atualização pode fazer o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerar um valor de GUID e então usar esse valor no diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="00a58-125">An updategram can have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generate a GUID value and then use this value in the updategram.</span></span> <span data-ttu-id="00a58-126">No contexto de DiffGrams, você pode usar a anotação `sql:guid` para especificar se deve ser usado um valor de GUID gerado pelo SQL Server ou um valor que é fornecido no diagrama de atualização para essa coluna.</span><span class="sxs-lookup"><span data-stu-id="00a58-126">In the context of DiffGrams, you can use the `sql:guid` annotation to specify whether to use a GUID value that is generated by SQL Server or use the value that is provided in the updategram for that column.</span></span>  
  
 <span data-ttu-id="00a58-127">É possível atribuir dois valores à anotação `sql:guid`:</span><span class="sxs-lookup"><span data-stu-id="00a58-127">The `sql:guid` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="00a58-128">generate</span><span class="sxs-lookup"><span data-stu-id="00a58-128">generate</span></span>  
 <span data-ttu-id="00a58-129">Especifica que o GUID gerado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seja usado para essa coluna na operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="00a58-129">Specifies that the GUID generated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] be used for that column in the update operation.</span></span>  
  
 <span data-ttu-id="00a58-130">useValue</span><span class="sxs-lookup"><span data-stu-id="00a58-130">useValue</span></span>  
 <span data-ttu-id="00a58-131">Especifica que o valor especificado no diagrama de atualização seja usado para a coluna.</span><span class="sxs-lookup"><span data-stu-id="00a58-131">Specifies that the value specified in the updategram be used for the column.</span></span> <span data-ttu-id="00a58-132">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="00a58-132">This is the default value.</span></span>  
  
  
