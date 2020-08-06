---
title: Elemento EventString (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 981cd0be06fd0972426fcb2fa67b0c4143cf9178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683859"
---
# <a name="eventstring-element-dta"></a><span data-ttu-id="70b87-102">Elemento EventString (DTA)</span><span class="sxs-lookup"><span data-stu-id="70b87-102">EventString Element (DTA)</span></span>
  <span data-ttu-id="70b87-103">Especifica uma carga de trabalho de script do [!INCLUDE[tsql](../../includes/tsql-md.md)] diretamente no arquivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="70b87-103">Specifies a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload directly in the XML input file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b87-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="70b87-104">Syntax</span></span>  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="70b87-105">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="70b87-105">Element Attributes</span></span>  
  
|<span data-ttu-id="70b87-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="70b87-106">Attribute</span></span>|<span data-ttu-id="70b87-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="70b87-107">Description</span></span>|  
|---------------|-----------------|  
|`Weight`|<span data-ttu-id="70b87-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="70b87-108">Optional.</span></span> <span data-ttu-id="70b87-109">Especifica o fator de peso da consulta (um fator de importância) para o evento especificado.</span><span class="sxs-lookup"><span data-stu-id="70b87-109">Specifies the query weight factor (a factor of importance) for the specified event.</span></span> <span data-ttu-id="70b87-110">Use um tipo de dados `float` para especificar o peso.</span><span class="sxs-lookup"><span data-stu-id="70b87-110">Use a `float` data type to specify the weight.</span></span> <span data-ttu-id="70b87-111">Por exemplo, `Weight`="100.01".</span><span class="sxs-lookup"><span data-stu-id="70b87-111">For example, `Weight`="100.01".</span></span> <span data-ttu-id="70b87-112">O valor mínimo que você pode especificar para `Weight` é "0."</span><span class="sxs-lookup"><span data-stu-id="70b87-112">The minimum value you can specify for `Weight` is "0".</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="70b87-113">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="70b87-113">Element Characteristics</span></span>  
  
|<span data-ttu-id="70b87-114">Característica</span><span class="sxs-lookup"><span data-stu-id="70b87-114">Characteristic</span></span>|<span data-ttu-id="70b87-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="70b87-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="70b87-116">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="70b87-116">**Data type and length**</span></span>|<span data-ttu-id="70b87-117">`string`, tamanho é ilimitado.</span><span class="sxs-lookup"><span data-stu-id="70b87-117">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="70b87-118">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="70b87-118">**Default value**</span></span>|<span data-ttu-id="70b87-119">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="70b87-119">None.</span></span>|  
|<span data-ttu-id="70b87-120">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="70b87-120">**Occurrence**</span></span>|<span data-ttu-id="70b87-121">Exigido uma vez se não houver outro tipo de carga de trabalho especificada.</span><span class="sxs-lookup"><span data-stu-id="70b87-121">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="70b87-122">É preciso especificar um elemento filho `EventString`, `File` ou  `Database` para o pai `Workload`, mas só pode ser usado um tipo.</span><span class="sxs-lookup"><span data-stu-id="70b87-122">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="70b87-123">Por exemplo, se for especificada uma carga de trabalho com o elemento `EventString`, não será possível especificar uma carga de trabalho com o elemento `File` no mesmo arquivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="70b87-123">For example, if you specify a workload with the `EventString` element, then you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="70b87-124">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="70b87-124">Element Relationships</span></span>  
  
|<span data-ttu-id="70b87-125">Relação</span><span class="sxs-lookup"><span data-stu-id="70b87-125">Relationship</span></span>|<span data-ttu-id="70b87-126">Elementos</span><span class="sxs-lookup"><span data-stu-id="70b87-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="70b87-127">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="70b87-127">**Parent element**</span></span>|[<span data-ttu-id="70b87-128">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="70b87-128">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="70b87-129">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="70b87-129">**Child elements**</span></span>|<span data-ttu-id="70b87-130">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="70b87-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="70b87-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="70b87-131">Example</span></span>  
 <span data-ttu-id="70b87-132">Para obter um exemplo de uso deste elemento, consulte [Amostra do arquivo de entrada XML com carga de trabalho embutida &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="70b87-132">For a usage example of this element, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b87-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70b87-133">See Also</span></span>  
 [<span data-ttu-id="70b87-134">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="70b87-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
