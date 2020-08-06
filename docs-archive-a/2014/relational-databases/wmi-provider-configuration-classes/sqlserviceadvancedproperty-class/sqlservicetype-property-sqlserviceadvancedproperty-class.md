---
title: Propriedade SqlServiceType (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: 20f1663a-9a14-4f14-8c1b-8aa133e272c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 774c8599fd21e330fa3228336ab1ed3c73d65c85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583408"
---
# <a name="sqlservicetype-property-sqlserviceadvancedproperty-class"></a><span data-ttu-id="83d84-102">Propriedade SqlServiceType (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="83d84-102">SqlServiceType Property (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="83d84-103">Obtém o tipo do serviço gerenciado associado com a propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="83d84-103">Gets the type of the managed service associated with the advanced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d84-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="83d84-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="83d84-105">Partes</span><span class="sxs-lookup"><span data-stu-id="83d84-105">Parts</span></span>  
 <span data-ttu-id="83d84-106">*object*</span><span class="sxs-lookup"><span data-stu-id="83d84-106">*object*</span></span>  
 <span data-ttu-id="83d84-107">Um objeto da [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa uma propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="83d84-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="83d84-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="83d84-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="83d84-109">Um valor uint32 que especifica o tipo de serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83d84-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83d84-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="83d84-110">Remarks</span></span>  
 <span data-ttu-id="83d84-111">Os valores retornados podem ser um destes</span><span class="sxs-lookup"><span data-stu-id="83d84-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="83d84-112">Type</span><span class="sxs-lookup"><span data-stu-id="83d84-112">Type</span></span>|<span data-ttu-id="83d84-113">Definição</span><span class="sxs-lookup"><span data-stu-id="83d84-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="83d84-114">*1*</span><span class="sxs-lookup"><span data-stu-id="83d84-114">*1*</span></span>|<span data-ttu-id="83d84-115">MSSQLSERVER é o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="83d84-116">*2*</span><span class="sxs-lookup"><span data-stu-id="83d84-116">*2*</span></span>|<span data-ttu-id="83d84-117">SQLSERVERAGENT é o serviço de Agente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="83d84-118">*3*</span><span class="sxs-lookup"><span data-stu-id="83d84-118">*3*</span></span>|<span data-ttu-id="83d84-119">MSFTESQL é o serviço do Mecanismo de Pesquisa de Texto Completo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="83d84-120">*4*</span><span class="sxs-lookup"><span data-stu-id="83d84-120">*4*</span></span>|<span data-ttu-id="83d84-121">MsDtsServer é o serviço do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="83d84-122">*5*</span><span class="sxs-lookup"><span data-stu-id="83d84-122">*5*</span></span>|<span data-ttu-id="83d84-123">MSSQLServerOLAPService é o serviço do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="83d84-124">*6*</span><span class="sxs-lookup"><span data-stu-id="83d84-124">*6*</span></span>|<span data-ttu-id="83d84-125">ReportServer é o serviço do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="83d84-126">*7*</span><span class="sxs-lookup"><span data-stu-id="83d84-126">*7*</span></span>|<span data-ttu-id="83d84-127">SQLBrowser é o serviço do Navegador do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83d84-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83d84-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83d84-128">See Also</span></span>  
 <span data-ttu-id="83d84-129">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="83d84-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
