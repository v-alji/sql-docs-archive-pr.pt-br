---
title: Elemento banner (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13238ac4ef1745dea4fbf3392484ac6137c09df1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686008"
---
# <a name="banner-element-ssbdiagnose"></a><span data-ttu-id="1ba07-102">Elemento Banner (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="1ba07-102">Banner Element (ssbdiagnose)</span></span>
  <span data-ttu-id="1ba07-103">Identifica qual utilitário gerou o arquivo XML de saída **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="1ba07-103">Identifies which utility generated the **ssbdiagnose** output XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba07-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1ba07-104">Syntax</span></span>  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="1ba07-105">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="1ba07-105">Element Attributes</span></span>  
  
|<span data-ttu-id="1ba07-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="1ba07-106">Attribute</span></span>|<span data-ttu-id="1ba07-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1ba07-107">Description</span></span>|  
|---------------|-----------------|  
|`title`|<span data-ttu-id="1ba07-108">Identifica qual utilitário gerou o arquivo de saída XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="1ba07-108">Identifies the utility that generated the **ssbdiagnose** XML output file.</span></span>|  
|`product`|<span data-ttu-id="1ba07-109">Identifica qual produto gerou o arquivo de saída XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="1ba07-109">Identifies the product that generated the **ssbdiagnose** XML output file.</span></span>|  
|`version`|<span data-ttu-id="1ba07-110">Identifica qual versão do utilitário gerou o arquivo de saída XML.</span><span class="sxs-lookup"><span data-stu-id="1ba07-110">Identifies which version of the utility generated the XML output file.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="1ba07-111">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="1ba07-111">Element Characteristics</span></span>  
  
|<span data-ttu-id="1ba07-112">Característica</span><span class="sxs-lookup"><span data-stu-id="1ba07-112">Characteristic</span></span>|<span data-ttu-id="1ba07-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="1ba07-113">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1ba07-114">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="1ba07-114">**Data type and length**</span></span>|<span data-ttu-id="1ba07-115">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1ba07-115">None.</span></span>|  
|<span data-ttu-id="1ba07-116">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="1ba07-116">**Default value**</span></span>|<span data-ttu-id="1ba07-117">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1ba07-117">None.</span></span>|  
|<span data-ttu-id="1ba07-118">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="1ba07-118">**Occurrence**</span></span>|<span data-ttu-id="1ba07-119">Ocorre uma vez por arquivo XML de saída **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="1ba07-119">Occurs once per **ssbdiagnose** output XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="1ba07-120">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="1ba07-120">Element Relationships</span></span>  
  
|<span data-ttu-id="1ba07-121">Relação</span><span class="sxs-lookup"><span data-stu-id="1ba07-121">Relationship</span></span>|<span data-ttu-id="1ba07-122">Elementos</span><span class="sxs-lookup"><span data-stu-id="1ba07-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="1ba07-123">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="1ba07-123">**Parent element**</span></span>|[<span data-ttu-id="1ba07-124">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="1ba07-124">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="1ba07-125">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="1ba07-125">**Child elements**</span></span>|<span data-ttu-id="1ba07-126">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1ba07-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ba07-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1ba07-127">Example</span></span>  
 <span data-ttu-id="1ba07-128">Este é um exemplo de um elemento Banner.</span><span class="sxs-lookup"><span data-stu-id="1ba07-128">This is an example of a banner element.</span></span>  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ba07-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ba07-129">See Also</span></span>  
 [<span data-ttu-id="1ba07-130">Utilitário ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="1ba07-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
