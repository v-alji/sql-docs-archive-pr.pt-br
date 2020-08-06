---
title: Elemento DatabaseToConnect (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DatabaseToConnect element
ms.assetid: 65153a66-3aee-4429-99b7-0816ac23c285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c21b36319e4007264677d499b84964c7cb5ea7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678440"
---
# <a name="databasetoconnect-element-dta"></a><span data-ttu-id="110e2-102">Elemento DatabaseToConnect (DTA)</span><span class="sxs-lookup"><span data-stu-id="110e2-102">DatabaseToConnect Element (DTA)</span></span>
  <span data-ttu-id="110e2-103">Especifica o primeiro banco de dados que o Orientador de Otimização do Mecanismo de Banco de Dados conecta ao ajustar uma carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="110e2-103">Specifies the first database to which Database Engine Tuning Advisor connects when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="110e2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="110e2-104">Syntax</span></span>  
  
```  
  
    <TuningOptions>  
...code removed here...  
      <DatabaseToConnect>...</DatabaseToConnect>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="110e2-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="110e2-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="110e2-106">Característica</span><span class="sxs-lookup"><span data-stu-id="110e2-106">Characteristic</span></span>|<span data-ttu-id="110e2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="110e2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="110e2-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="110e2-108">**Data type and length**</span></span>|<span data-ttu-id="110e2-109">`string`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="110e2-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="110e2-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="110e2-110">**Default value**</span></span>|<span data-ttu-id="110e2-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="110e2-111">None.</span></span>|  
|<span data-ttu-id="110e2-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="110e2-112">**Occurrence**</span></span>|<span data-ttu-id="110e2-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="110e2-113">Optional.</span></span> <span data-ttu-id="110e2-114">Pode ser usado uma vez para cada elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="110e2-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="110e2-115">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="110e2-115">Element Relationships</span></span>  
  
|<span data-ttu-id="110e2-116">Relação</span><span class="sxs-lookup"><span data-stu-id="110e2-116">Relationship</span></span>|<span data-ttu-id="110e2-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="110e2-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="110e2-118">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="110e2-118">**Parent element**</span></span>|[<span data-ttu-id="110e2-119">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="110e2-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="110e2-120">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="110e2-120">**Child elements**</span></span>|<span data-ttu-id="110e2-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="110e2-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="110e2-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="110e2-122">Remarks</span></span>  
 <span data-ttu-id="110e2-123">Use o `DatabaseToConnect` para especificar o nome do primeiro banco de dados que o Orientador de Otimização do Mecanismo de Banco de Dados conectará quando iniciar a sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="110e2-123">Use `DatabaseToConnect` to specify the name of the first database to which you want Database Engine Tuning Advisor to connect when it starts the tuning session.</span></span> <span data-ttu-id="110e2-124">Você pode especificar apenas um banco de dados com esse elemento.</span><span class="sxs-lookup"><span data-stu-id="110e2-124">You can specify only one database with this element.</span></span> <span data-ttu-id="110e2-125">Se forem especificados vários nomes de banco de dados, o Orientador de Otimização do Mecanismo de Banco de Dados retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="110e2-125">If multiple database names are specified, Database Engine Tuning Advisor returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="110e2-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="110e2-126">Example</span></span>  
 <span data-ttu-id="110e2-127">Para obter um exemplo de uso, veja a [Amostra do arquivo de entrada XML com carga de trabalho embutida &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="110e2-127">For a usage example, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110e2-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="110e2-128">See Also</span></span>  
 [<span data-ttu-id="110e2-129">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="110e2-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
