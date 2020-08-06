---
title: Conjunto de linhas LINKEDSERVERS (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
ms.assetid: 2633fd8a-65e7-498d-9aed-8e4b1cca2381
author: rothja
ms.author: jroth
ms.openlocfilehash: 80eded31ebae744e272757a53a7fd1f4b56bf358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570654"
---
# <a name="linkedservers-rowset-ole-db"></a><span data-ttu-id="0e0fd-102">Conjunto de linhas LINKEDSERVERS (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0e0fd-102">LINKEDSERVERS Rowset (OLE DB)</span></span>
  <span data-ttu-id="0e0fd-103">O conjunto de linhas **LINKEDSERVERS** enumera fontes de dados da organização que podem participar de consultas distribuídas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e0fd-103">The **LINKEDSERVERS** rowset enumerates organization data sources that can participate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="0e0fd-104">O conjunto de linhas **LINKEDSERVERS** contém as seguintes colunas.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-104">The **LINKEDSERVERS** rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="0e0fd-105">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="0e0fd-105">Column name</span></span>|<span data-ttu-id="0e0fd-106">Indicador de tipo</span><span class="sxs-lookup"><span data-stu-id="0e0fd-106">Type indicator</span></span>|<span data-ttu-id="0e0fd-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="0e0fd-107">Description</span></span>|  
|-----------------|--------------------|-----------------|  
|<span data-ttu-id="0e0fd-108">SVR_NAME</span><span class="sxs-lookup"><span data-stu-id="0e0fd-108">SVR_NAME</span></span>|<span data-ttu-id="0e0fd-109">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="0e0fd-109">DBTYPE_WSTR</span></span>|<span data-ttu-id="0e0fd-110">Nome de um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-110">Name of a linked server.</span></span>|  
|<span data-ttu-id="0e0fd-111">SVR_PRODUCT</span><span class="sxs-lookup"><span data-stu-id="0e0fd-111">SVR_PRODUCT</span></span>|<span data-ttu-id="0e0fd-112">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="0e0fd-112">DBTYPE_WSTR</span></span>|<span data-ttu-id="0e0fd-113">Fabricante ou outro nome que identifique o tipo de repositório de dados representado pelo nome do servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-113">Manufacturer or other name identifying the type of data store represented by the name of the linked server.</span></span>|  
|<span data-ttu-id="0e0fd-114">SVR_PROVIDERNAME</span><span class="sxs-lookup"><span data-stu-id="0e0fd-114">SVR_PROVIDERNAME</span></span>|<span data-ttu-id="0e0fd-115">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="0e0fd-115">DBTYPE_WSTR</span></span>|<span data-ttu-id="0e0fd-116">Nome amigável do provedor OLE DB usado para consumir dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-116">Friendly name of the OLE DB provider used to consume data from the server.</span></span>|  
|<span data-ttu-id="0e0fd-117">SVR_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="0e0fd-117">SVR_DATASOURCE</span></span>|<span data-ttu-id="0e0fd-118">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="0e0fd-118">DBTYPE_WSTR</span></span>|<span data-ttu-id="0e0fd-119">Cadeia de caracteres OLE DB DBPROP_INIT_DATASOURCE usada para adquirir uma fonte de dados do provedor.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-119">OLE DB DBPROP_INIT_DATASOURCE string used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="0e0fd-120">SVR_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="0e0fd-120">SVR_PROVIDERSTRING</span></span>|<span data-ttu-id="0e0fd-121">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="0e0fd-121">DBTYPE_WSTR</span></span>|<span data-ttu-id="0e0fd-122">Valor DBPROP_INIT_PROVIDERSTRING do OLE DB usado para adquirir uma fonte de dados do provedor.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-122">OLE DB DBPROP_INIT_PROVIDERSTRING value used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="0e0fd-123">SVR_LOCATION</span><span class="sxs-lookup"><span data-stu-id="0e0fd-123">SVR_LOCATION</span></span>|<span data-ttu-id="0e0fd-124">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="0e0fd-124">DBTYPE_WSTR</span></span>|<span data-ttu-id="0e0fd-125">Cadeia de caracteres de DBPROP_INIT_LOCATION do OLE DB usada para adquirir uma fonte de dados do provedor.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-125">OLE DB DBPROP_INIT_LOCATION string used to acquire a data source from the provider.</span></span>|  
  
 <span data-ttu-id="0e0fd-126">O conjunto de linhas é classificado em SRV_NAME, havendo suporte a uma única restrição em SRV_NAME.</span><span class="sxs-lookup"><span data-stu-id="0e0fd-126">The rowset is sorted on SRV_NAME and a single restriction is supported on SRV_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0fd-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e0fd-127">See Also</span></span>  
 [<span data-ttu-id="0e0fd-128">Suporte ao conjunto de linhas de esquema &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0e0fd-128">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
  
