---
title: Propriedades personalizadas da origem XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eb29b28c-3159-41ec-b3d7-fce5b2f2be55
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e152b23b4f59ca46cb8272ca677dc1161b3efec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582018"
---
# <a name="xml-source-custom-properties"></a><span data-ttu-id="aa18d-102">Propriedades personalizadas da origem XML</span><span class="sxs-lookup"><span data-stu-id="aa18d-102">XML Source Custom Properties</span></span>
  <span data-ttu-id="aa18d-103">A origem XML contém propriedades personalizadas e as propriedades comuns a todos os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="aa18d-103">The XML source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="aa18d-104">A tabela a seguir descreve as propriedades personalizadas da origem XML.</span><span class="sxs-lookup"><span data-stu-id="aa18d-104">The following table describes the custom properties of the XML source.</span></span> <span data-ttu-id="aa18d-105">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="aa18d-105">All properties are read/write.</span></span>  
  
|<span data-ttu-id="aa18d-106">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="aa18d-106">Property name</span></span>|<span data-ttu-id="aa18d-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="aa18d-107">Data Type</span></span>|<span data-ttu-id="aa18d-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa18d-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="aa18d-109">AccessMode</span><span class="sxs-lookup"><span data-stu-id="aa18d-109">AccessMode</span></span>|<span data-ttu-id="aa18d-110">Integer</span><span class="sxs-lookup"><span data-stu-id="aa18d-110">Integer</span></span>|<span data-ttu-id="aa18d-111">O modo usado para acessar os dados XML.</span><span class="sxs-lookup"><span data-stu-id="aa18d-111">The mode used to access the XML data.</span></span>|  
|<span data-ttu-id="aa18d-112">UseInlineSchema</span><span class="sxs-lookup"><span data-stu-id="aa18d-112">UseInlineSchema</span></span>|<span data-ttu-id="aa18d-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="aa18d-113">Boolean</span></span>|<span data-ttu-id="aa18d-114">Um valor que indica se deve ser usada uma definição de esquema embutido dentro da origem XML.</span><span class="sxs-lookup"><span data-stu-id="aa18d-114">A value that indicates whether to use an inline schema definition within the XML source.</span></span> <span data-ttu-id="aa18d-115">O valor padrão dessa propriedade é `False`.</span><span class="sxs-lookup"><span data-stu-id="aa18d-115">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="aa18d-116">XMLData</span><span class="sxs-lookup"><span data-stu-id="aa18d-116">XMLData</span></span>|<span data-ttu-id="aa18d-117">String</span><span class="sxs-lookup"><span data-stu-id="aa18d-117">String</span></span>|<span data-ttu-id="aa18d-118">O arquivo ou variáveis dos quais é possível recuperar os dados XML.</span><span class="sxs-lookup"><span data-stu-id="aa18d-118">The file or variables from which to retrieve the XML data.</span></span><br /><br /> <span data-ttu-id="aa18d-119">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="aa18d-119">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="aa18d-120">XMLSchemaDefinition</span><span class="sxs-lookup"><span data-stu-id="aa18d-120">XMLSchemaDefinition</span></span>|<span data-ttu-id="aa18d-121">String</span><span class="sxs-lookup"><span data-stu-id="aa18d-121">String</span></span>|<span data-ttu-id="aa18d-122">O caminho e nome de arquivo do arquivo de definição de esquema (.xsd).</span><span class="sxs-lookup"><span data-stu-id="aa18d-122">The path and file name of the schema definition file (.xsd).</span></span><br /><br /> <span data-ttu-id="aa18d-123">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="aa18d-123">The value of this property can be specified by using a property expression.</span></span>|  
  
 <span data-ttu-id="aa18d-124">A tabela a seguir descreve as propriedades personalizadas da saída da origem XML.</span><span class="sxs-lookup"><span data-stu-id="aa18d-124">The following table describes the custom properties of the output of the XML source.</span></span> <span data-ttu-id="aa18d-125">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="aa18d-125">All properties are read/write.</span></span>  
  
|<span data-ttu-id="aa18d-126">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="aa18d-126">Property name</span></span>|<span data-ttu-id="aa18d-127">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="aa18d-127">Data Type</span></span>|<span data-ttu-id="aa18d-128">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa18d-128">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="aa18d-129">RowsetID</span><span class="sxs-lookup"><span data-stu-id="aa18d-129">RowsetID</span></span>|<span data-ttu-id="aa18d-130">String</span><span class="sxs-lookup"><span data-stu-id="aa18d-130">String</span></span>|<span data-ttu-id="aa18d-131">Um valor que identifica o conjunto de linhas associado à saída.</span><span class="sxs-lookup"><span data-stu-id="aa18d-131">A value that identifies the rowset associated with the output.</span></span>|  
  
 <span data-ttu-id="aa18d-132">As colunas de saída da origem XML não têm nenhuma propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="aa18d-132">The output columns of the XML source have no custom properties.</span></span>  
  
 <span data-ttu-id="aa18d-133">Para obter mais informações, consulte [XML Source](xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="aa18d-133">For more information, see [XML Source](xml-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa18d-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa18d-134">See Also</span></span>  
 [<span data-ttu-id="aa18d-135">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="aa18d-135">Common Properties</span></span>](../common-properties.md)  
  
  
