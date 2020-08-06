---
title: Propriedade SqlServiceType (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681478"
---
# <a name="sqlservicetype-property-sqlservice-class"></a><span data-ttu-id="c5d1a-102">Propriedade SqlServiceType (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="c5d1a-102">SqlServiceType Property (SqlService Class)</span></span>
  <span data-ttu-id="c5d1a-103">Obtém o tipo do serviço gerenciado.</span><span class="sxs-lookup"><span data-stu-id="c5d1a-103">Gets the type of the managed service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5d1a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c5d1a-104">Syntax</span></span>  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c5d1a-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c5d1a-105">Parts</span></span>  
 <span data-ttu-id="c5d1a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-106">*object*</span></span>  
 <span data-ttu-id="c5d1a-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="c5d1a-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c5d1a-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="c5d1a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c5d1a-109">Um valor uint32 que especifica o tipo de serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5d1a-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="c5d1a-110">Remarks</span></span>  
 <span data-ttu-id="c5d1a-111">Os valores retornados podem ser um destes</span><span class="sxs-lookup"><span data-stu-id="c5d1a-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="c5d1a-112">Type</span><span class="sxs-lookup"><span data-stu-id="c5d1a-112">Type</span></span>|<span data-ttu-id="c5d1a-113">Definição</span><span class="sxs-lookup"><span data-stu-id="c5d1a-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="c5d1a-114">*1*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-114">*1*</span></span>|<span data-ttu-id="c5d1a-115">MSSQLSERVER é o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="c5d1a-116">*2*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-116">*2*</span></span>|<span data-ttu-id="c5d1a-117">SQLSERVERAGENT é o serviço de Agente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="c5d1a-118">*3*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-118">*3*</span></span>|<span data-ttu-id="c5d1a-119">MSFTESQL é o serviço do Mecanismo de Pesquisa de Texto Completo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="c5d1a-120">*4*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-120">*4*</span></span>|<span data-ttu-id="c5d1a-121">MsDtsServer é o serviço do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="c5d1a-122">*5*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-122">*5*</span></span>|<span data-ttu-id="c5d1a-123">MSSQLServerOLAPService é o serviço do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="c5d1a-124">*6*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-124">*6*</span></span>|<span data-ttu-id="c5d1a-125">ReportServer é o serviço do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="c5d1a-126">*7*</span><span class="sxs-lookup"><span data-stu-id="c5d1a-126">*7*</span></span>|<span data-ttu-id="c5d1a-127">SQLBrowser é o serviço do Navegador do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5d1a-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5d1a-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5d1a-128">See Also</span></span>  
 <span data-ttu-id="c5d1a-129">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d1a-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
