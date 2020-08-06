---
title: Propriedades de informações da fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- information properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 7fd80e47-5bd9-41e2-a3d3-091a7c8c5f2b
author: rothja
ms.author: jroth
ms.openlocfilehash: c10a4e762bbe3421e720753941f5e0a5702832ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685085"
---
# <a name="data-source-information-properties"></a><span data-ttu-id="1858e-102">Propriedades de informações da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="1858e-102">Data Source Information Properties</span></span>
  <span data-ttu-id="1858e-103">No conjunto de propriedades específico do provedor DBPROPSET_SQLSERVERDATASOURCEINFO, o provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define as seguintes propriedades de informações da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1858e-103">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCEINFO, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information properties.</span></span>  
  
|<span data-ttu-id="1858e-104">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="1858e-104">Property ID</span></span>|<span data-ttu-id="1858e-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="1858e-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1858e-106">SSPROP_COLUMNLEVELCOLLATION</span><span class="sxs-lookup"><span data-stu-id="1858e-106">SSPROP_COLUMNLEVELCOLLATION</span></span>|<span data-ttu-id="1858e-107">Tipo: VT_BOOL</span><span class="sxs-lookup"><span data-stu-id="1858e-107">Type: VT_BOOL</span></span><br /><br /> <span data-ttu-id="1858e-108">Leitura/gravação: leitura</span><span class="sxs-lookup"><span data-stu-id="1858e-108">R/W: Read</span></span><br /><br /> <span data-ttu-id="1858e-109">Padrão: VARIANT_TRUE</span><span class="sxs-lookup"><span data-stu-id="1858e-109">Default: VARIANT_TRUE</span></span><br /><br /> <span data-ttu-id="1858e-110">Descrição: usado para determinar se há suporte para a ordenação de coluna.</span><span class="sxs-lookup"><span data-stu-id="1858e-110">Description: Used to determine if column collation is supported.</span></span><br /><br /> <span data-ttu-id="1858e-111">VARIANT_TRUE: há suporte à ordenação em nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="1858e-111">VARIANT_TRUE: Column level collation is supported.</span></span><br /><br /> <span data-ttu-id="1858e-112">VARIANT_FALSE: não há suporte para a ordenação em nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="1858e-112">VARIANT_FALSE: Column level collation is not supported.</span></span>|  
|<span data-ttu-id="1858e-113">SSPROP_UNICODELCID</span><span class="sxs-lookup"><span data-stu-id="1858e-113">SSPROP_UNICODELCID</span></span>|<span data-ttu-id="1858e-114">Tipo: VT_I4 Leitura/gravação: leitura</span><span class="sxs-lookup"><span data-stu-id="1858e-114">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="1858e-115">Descrição: ID da localidade Unicode.</span><span class="sxs-lookup"><span data-stu-id="1858e-115">Description: Unicode locale ID.</span></span><br /><br /> <span data-ttu-id="1858e-116">Esta é a localidade usada para classificação de dados Unicode.</span><span class="sxs-lookup"><span data-stu-id="1858e-116">This is the locale used for Unicode data sorting.</span></span>|  
|<span data-ttu-id="1858e-117">SSPROP_UNICODECOMPARISONSTYLE</span><span class="sxs-lookup"><span data-stu-id="1858e-117">SSPROP_UNICODECOMPARISONSTYLE</span></span>|<span data-ttu-id="1858e-118">Tipo: VT_I4 Leitura/gravação: leitura</span><span class="sxs-lookup"><span data-stu-id="1858e-118">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="1858e-119">Descrição: estilo de comparação Unicode.</span><span class="sxs-lookup"><span data-stu-id="1858e-119">Description: Unicode comparison style.</span></span><br /><br /> <span data-ttu-id="1858e-120">As opções de classificação usadas para a classificação de dados Unicode.</span><span class="sxs-lookup"><span data-stu-id="1858e-120">The sorting options used for Unicode data sorting.</span></span>|  
  
 <span data-ttu-id="1858e-121">No conjunto de propriedades específico do provedor DBPROPSET_SQLSERVERSTREAM, o provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define a seguinte propriedade adicional.</span><span class="sxs-lookup"><span data-stu-id="1858e-121">In the provider-specific property set DBPROPSET_SQLSERVERSTREAM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional property.</span></span>  
  
|<span data-ttu-id="1858e-122">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="1858e-122">Property ID</span></span>|<span data-ttu-id="1858e-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="1858e-123">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1858e-124">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="1858e-124">SSPROP_STREAM_XMLROOT</span></span>|<span data-ttu-id="1858e-125">Tipo: VT_BSTR Leitura/gravação: leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="1858e-125">Type: VT_BSTR R/W: Read/Write</span></span><br /><br /> <span data-ttu-id="1858e-126">Descrição: o resultado de uma consulta XML FOR pode não ser um documento bem formado.</span><span class="sxs-lookup"><span data-stu-id="1858e-126">Description: The result of a FOR XML query may not be a well-formed document.</span></span> <span data-ttu-id="1858e-127">Quando esta propriedade é especificada, o resultado de uma consulta ‘select ... for XML' é quebrado na marca raiz fornecida por essa propriedade para retornar um documento XML bem formado.</span><span class="sxs-lookup"><span data-stu-id="1858e-127">When this property is specified, the result of a 'select ... for XML' query is wrapped in the root tag provided by this property to return a well formed XML document.</span></span> <span data-ttu-id="1858e-128">Se a consulta for executada no navegador, ela pode fazer o navegador exibir erros de analisador ao carregar o resultado.</span><span class="sxs-lookup"><span data-stu-id="1858e-128">If the query is executed in the browser it may cause the browser to display parser errors when loading the result.</span></span> <span data-ttu-id="1858e-129">Para evitar o erro, o SQL ISAPI dá suporte à palavra-chave ROOT.</span><span class="sxs-lookup"><span data-stu-id="1858e-129">To avoid the error, SQL ISAPI supports the keyword ROOT.</span></span> <span data-ttu-id="1858e-130">Essa palavra-chave é mapeada para a propriedade SSPROP_STREAM_XMLROOT.</span><span class="sxs-lookup"><span data-stu-id="1858e-130">This keyword maps to SSPROP_STREAM_XMLROOT property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1858e-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1858e-131">See Also</span></span>  
 [<span data-ttu-id="1858e-132">Objetos de fonte de dados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1858e-132">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
