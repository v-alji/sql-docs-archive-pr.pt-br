---
title: Elemento DTAInput (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679114"
---
# <a name="dtainput-element-dta"></a><span data-ttu-id="b83fe-102">Elemento DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="b83fe-102">DTAInput Element (DTA)</span></span>
  <span data-ttu-id="b83fe-103">Contém a definição de entrada XML para o Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="b83fe-103">Contains the definition of XML input for Database Engine Tuning Advisor.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b83fe-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b83fe-104">Syntax</span></span>  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b83fe-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="b83fe-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b83fe-106">Características</span><span class="sxs-lookup"><span data-stu-id="b83fe-106">Characteristics</span></span>|<span data-ttu-id="b83fe-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b83fe-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="b83fe-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b83fe-108">**Data type and length**</span></span>|<span data-ttu-id="b83fe-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b83fe-109">None.</span></span>|  
|<span data-ttu-id="b83fe-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="b83fe-110">**Default value**</span></span>|<span data-ttu-id="b83fe-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b83fe-111">None.</span></span>|  
|<span data-ttu-id="b83fe-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="b83fe-112">**Occurrence**</span></span>|<span data-ttu-id="b83fe-113">Opcional uma vez por elemento **DTAXML** .</span><span class="sxs-lookup"><span data-stu-id="b83fe-113">Optional once per **DTAXML** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b83fe-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="b83fe-114">Element Relationships</span></span>  
  
|<span data-ttu-id="b83fe-115">Relação</span><span class="sxs-lookup"><span data-stu-id="b83fe-115">Relationship</span></span>|<span data-ttu-id="b83fe-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="b83fe-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b83fe-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="b83fe-117">**Parent element**</span></span>|[<span data-ttu-id="b83fe-118">Elemento DTAXML &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b83fe-118">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)|  
|<span data-ttu-id="b83fe-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="b83fe-119">**Child elements**</span></span>|[<span data-ttu-id="b83fe-120">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b83fe-120">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="b83fe-121">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b83fe-121">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)<br /><br /> [<span data-ttu-id="b83fe-122">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b83fe-122">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)<br /><br /> [<span data-ttu-id="b83fe-123">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b83fe-123">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="b83fe-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="b83fe-124">Remarks</span></span>  
 <span data-ttu-id="b83fe-125">Esse elemento é a raiz da hierarquia de esquema de entrada do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="b83fe-125">This element is the root of the Database Engine Tuning Advisor input schema hierarchy.</span></span> <span data-ttu-id="b83fe-126">Uma entrada para o Orientador de Otimização do Mecanismo de Banco de Dados pode consistir em argumentos que especificam os servidores cujo banco de dados serão ajustados, cargas de trabalho, opções de ajuste ou configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b83fe-126">Input to Database Engine Tuning Advisor can be arguments that specify the servers whose databases you want to tune, workloads, tuning options, or a user-specified configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b83fe-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b83fe-127">Example</span></span>  
 <span data-ttu-id="b83fe-128">Para obter um exemplo do elemento **DTAInput**, veja [Exemplo de arquivos de entrada XML simples &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b83fe-128">For a usage example of the **DTAInput** element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83fe-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b83fe-129">See Also</span></span>  
 [<span data-ttu-id="b83fe-130">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b83fe-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
