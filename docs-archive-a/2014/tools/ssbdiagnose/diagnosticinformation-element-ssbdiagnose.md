---
title: Elemento DiagnosticInformation (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92d76a065c24ddc1fc8d85989ed3202308571951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571257"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a><span data-ttu-id="9b727-102">Elemento DiagnosticInformation (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="9b727-102">DiagnosticInformation Element (ssbdiagnose)</span></span>
  <span data-ttu-id="9b727-103">O elemento **DiagnosticInformation** contém todos os elementos que reportam as informações de diagnóstico encontradas pelo utilitário.</span><span class="sxs-lookup"><span data-stu-id="9b727-103">The **DiagnosticInformation** element contains all elements that report the diagnostic information found by the utility.</span></span> <span data-ttu-id="9b727-104">**DiagnosticInformation** é o elemento raiz de um arquivo de saída XML **ssbdiagnostic** .</span><span class="sxs-lookup"><span data-stu-id="9b727-104">**DiagnosticInformation** is the root element of a **ssbdiagnostic** XML output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b727-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b727-105">Syntax</span></span>  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="9b727-106">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="9b727-106">Element Attributes</span></span>  
  
|<span data-ttu-id="9b727-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="9b727-107">Attribute</span></span>|<span data-ttu-id="9b727-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b727-108">Description</span></span>|  
|---------------|-----------------|  
|`None`|<span data-ttu-id="9b727-109">N/D</span><span class="sxs-lookup"><span data-stu-id="9b727-109">N/A</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="9b727-110">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="9b727-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="9b727-111">Característica</span><span class="sxs-lookup"><span data-stu-id="9b727-111">Characteristic</span></span>|<span data-ttu-id="9b727-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b727-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9b727-113">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9b727-113">**Data type and length**</span></span>|<span data-ttu-id="9b727-114">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9b727-114">None.</span></span>|  
|<span data-ttu-id="9b727-115">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="9b727-115">**Default value**</span></span>|<span data-ttu-id="9b727-116">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9b727-116">None.</span></span>|  
|<span data-ttu-id="9b727-117">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="9b727-117">**Occurrence**</span></span>|<span data-ttu-id="9b727-118">Uma vez por arquivo de saída XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="9b727-118">Once per **ssbdiagnose** XML output file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="9b727-119">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="9b727-119">Element Relationships</span></span>  
  
|<span data-ttu-id="9b727-120">Relação</span><span class="sxs-lookup"><span data-stu-id="9b727-120">Relationship</span></span>|<span data-ttu-id="9b727-121">Elementos</span><span class="sxs-lookup"><span data-stu-id="9b727-121">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="9b727-122">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="9b727-122">**Parent element**</span></span>|<span data-ttu-id="9b727-123">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9b727-123">None.</span></span>|  
|<span data-ttu-id="9b727-124">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="9b727-124">**Child elements**</span></span>|[<span data-ttu-id="9b727-125">Elemento Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9b727-125">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)<br /><br /> [<span data-ttu-id="9b727-126">Elemento Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9b727-126">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a><span data-ttu-id="9b727-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b727-127">Remarks</span></span>  
 <span data-ttu-id="9b727-128">Para obter mais informações sobre namespaces XML, consulte [Namespaces em um documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) na Biblioteca MSDN do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b727-128">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b727-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b727-129">See Also</span></span>  
 [<span data-ttu-id="9b727-130">Utilitário ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="9b727-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
