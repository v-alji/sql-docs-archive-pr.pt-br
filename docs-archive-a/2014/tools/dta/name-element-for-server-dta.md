---
title: Elemento de nome para o servidor (DTA) | Microsoft Docs
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
ms.assetid: 4c94754d-6d62-4357-8ce7-f107ebf90c71
author: stevestein
ms.author: sstein
ms.openlocfilehash: 202258c3c87f8a35d1ee30b19880f5e9423fa394
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576105"
---
# <a name="name-element-for-server-dta"></a><span data-ttu-id="b463d-102">Elemento Nome do servidor (DTA)</span><span class="sxs-lookup"><span data-stu-id="b463d-102">Name Element for Server (DTA)</span></span>
  <span data-ttu-id="b463d-103">Contém o nome do servidor em que residem os bancos de dados que você deseja ajustar.</span><span class="sxs-lookup"><span data-stu-id="b463d-103">Contains the name of the server where the databases you want to tune reside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b463d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b463d-104">Syntax</span></span>  
  
```  
  
...code removed here...  
<Server>  
    <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b463d-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="b463d-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b463d-106">Característica</span><span class="sxs-lookup"><span data-stu-id="b463d-106">Characteristic</span></span>|<span data-ttu-id="b463d-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b463d-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b463d-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b463d-108">**Data type and length**</span></span>|<span data-ttu-id="b463d-109">`string`, entre 1 e 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b463d-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="b463d-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="b463d-110">**Default value**</span></span>|<span data-ttu-id="b463d-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b463d-111">None.</span></span>|  
|<span data-ttu-id="b463d-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="b463d-112">**Occurrence**</span></span>|<span data-ttu-id="b463d-113">Exigido uma vez por elemento de **Servidor** .</span><span class="sxs-lookup"><span data-stu-id="b463d-113">Required once per **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b463d-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="b463d-114">Element Relationships</span></span>  
  
|<span data-ttu-id="b463d-115">Relação</span><span class="sxs-lookup"><span data-stu-id="b463d-115">Relationship</span></span>|<span data-ttu-id="b463d-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="b463d-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b463d-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="b463d-117">**Parent element**</span></span>|[<span data-ttu-id="b463d-118">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b463d-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="b463d-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="b463d-119">**Child elements**</span></span>|<span data-ttu-id="b463d-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b463d-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b463d-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b463d-121">Example</span></span>  
 <span data-ttu-id="b463d-122">Para obter um exemplo de como esse elemento **Name** é usado, consulte [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b463d-122">For an example of how this **Name** element is used, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b463d-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b463d-123">See Also</span></span>  
 [<span data-ttu-id="b463d-124">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b463d-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
