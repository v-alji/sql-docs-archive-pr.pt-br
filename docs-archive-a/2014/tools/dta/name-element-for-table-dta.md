---
title: Elemento de nome para a tabela (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 422a755f-ee52-4863-b1aa-f4ef1b8fd0bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fa8481cf8990fb63995abcb6300cd9a352c859a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576102"
---
# <a name="name-element-for-table-dta"></a><span data-ttu-id="3947c-102">Elemento de nome de tabela (DTA)</span><span class="sxs-lookup"><span data-stu-id="3947c-102">Name Element for Table (DTA)</span></span>
  <span data-ttu-id="3947c-103">Especifica um nome de tabela para ajuste.</span><span class="sxs-lookup"><span data-stu-id="3947c-103">Specifies a table name for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3947c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3947c-104">Syntax</span></span>  
  
```  
  
<Schema>  
    <Table>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3947c-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="3947c-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3947c-106">Característica</span><span class="sxs-lookup"><span data-stu-id="3947c-106">Characteristic</span></span>|<span data-ttu-id="3947c-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="3947c-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3947c-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3947c-108">**Data type and length**</span></span>|<span data-ttu-id="3947c-109">`string`, entre 1 e 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3947c-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="3947c-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="3947c-110">**Default value**</span></span>|<span data-ttu-id="3947c-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3947c-111">None.</span></span>|  
|<span data-ttu-id="3947c-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="3947c-112">**Occurrence**</span></span>|<span data-ttu-id="3947c-113">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="3947c-113">Required.</span></span> <span data-ttu-id="3947c-114">Uma vez para cada elemento de `Table`.</span><span class="sxs-lookup"><span data-stu-id="3947c-114">Once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3947c-115">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="3947c-115">Element Relationships</span></span>  
  
|<span data-ttu-id="3947c-116">Relação</span><span class="sxs-lookup"><span data-stu-id="3947c-116">Relationship</span></span>|<span data-ttu-id="3947c-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="3947c-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3947c-118">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="3947c-118">**Parent element**</span></span>|[<span data-ttu-id="3947c-119">Elemento Table para Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3947c-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="3947c-120">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="3947c-120">**Child elements**</span></span>|<span data-ttu-id="3947c-121">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3947c-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3947c-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3947c-122">Example</span></span>  
 <span data-ttu-id="3947c-123">Para obter um exemplo de uso, veja [Elemento Server&#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3947c-123">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3947c-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3947c-124">See Also</span></span>  
 [<span data-ttu-id="3947c-125">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="3947c-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
