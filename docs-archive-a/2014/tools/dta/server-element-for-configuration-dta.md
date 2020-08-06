---
title: Elemento de servidor para configuração (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: da9ff870-9cfd-42fe-994b-7b9292681f7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88182cdad2e7313f0910a106ee37d727d840bfed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576094"
---
# <a name="server-element-for-configuration-dta"></a><span data-ttu-id="37527-102">Elemento de servidor para configuração (DTA)</span><span class="sxs-lookup"><span data-stu-id="37527-102">Server Element for Configuration (DTA)</span></span>
  <span data-ttu-id="37527-103">Contém as informações de identificação para o servidor onde você quer que o Orientador de Otimização do Mecanismo de Banco de Dados avalie uma configuração hipotética (especificada pelo elemento `Configuration` ).</span><span class="sxs-lookup"><span data-stu-id="37527-103">Contains the identifying information for the server where you want Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37527-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="37527-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    <Server>  
...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="37527-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="37527-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="37527-106">Característica</span><span class="sxs-lookup"><span data-stu-id="37527-106">Characteristic</span></span>|<span data-ttu-id="37527-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="37527-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="37527-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="37527-108">**Data type and length**</span></span>|<span data-ttu-id="37527-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="37527-109">None.</span></span>|  
|<span data-ttu-id="37527-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="37527-110">**Default value**</span></span>|<span data-ttu-id="37527-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="37527-111">None.</span></span>|  
|<span data-ttu-id="37527-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="37527-112">**Occurrence**</span></span>|<span data-ttu-id="37527-113">Obrigatório uma vez por elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="37527-113">Required once per `Configuration` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="37527-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="37527-114">Element Relationships</span></span>  
  
|<span data-ttu-id="37527-115">Relação</span><span class="sxs-lookup"><span data-stu-id="37527-115">Relationship</span></span>|<span data-ttu-id="37527-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="37527-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="37527-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="37527-117">**Parent element**</span></span>|[<span data-ttu-id="37527-118">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="37527-118">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
|<span data-ttu-id="37527-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="37527-119">**Child elements**</span></span>|[<span data-ttu-id="37527-120">Elemento Name para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="37527-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="37527-121">Elemento Database para Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="37527-121">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="37527-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="37527-122">Remarks</span></span>  
 <span data-ttu-id="37527-123">Você pode especificar apenas um `Server` elemento para o `Configuration` elemento.</span><span class="sxs-lookup"><span data-stu-id="37527-123">You can specify only one `Server` element for the `Configuration` element.</span></span> <span data-ttu-id="37527-124">Esse elemento tem o nome **ServerTypecomplexType** no [Esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="37527-124">This element is of the **ServerTypecomplexType** name in the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span> <span data-ttu-id="37527-125">Não confunda esse elemento `Server` com aquele que é o filho do elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="37527-125">Do not confuse this `Server` element with the one that is the child of the `DTAInput` element.</span></span> <span data-ttu-id="37527-126">Para obter mais informações, consulte [Elemento de servidor &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="37527-126">For more information, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37527-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="37527-127">Example</span></span>  
 <span data-ttu-id="37527-128">Para obter um exemplo de uso, consulte a [Amostra de arquivo de entrada XML com a configuração especificada pelo usuário &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="37527-128">For a usage example, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37527-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="37527-129">See Also</span></span>  
 [<span data-ttu-id="37527-130">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="37527-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
