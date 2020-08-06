---
title: Elemento de servidor (DTA) | Microsoft Docs
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
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576097"
---
# <a name="server-element-dta"></a><span data-ttu-id="307d7-102">Elemento de servidor (DTA)</span><span class="sxs-lookup"><span data-stu-id="307d7-102">Server Element (DTA)</span></span>
  <span data-ttu-id="307d7-103">Contém a informações de identificação do servidor no qual residem os bancos de dados a serem ajustados.</span><span class="sxs-lookup"><span data-stu-id="307d7-103">Contains the identifying information for the server on which the databases reside that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307d7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="307d7-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="307d7-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="307d7-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="307d7-106">Característica</span><span class="sxs-lookup"><span data-stu-id="307d7-106">Characteristic</span></span>|<span data-ttu-id="307d7-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="307d7-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="307d7-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="307d7-108">**Data type and length**</span></span>|<span data-ttu-id="307d7-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="307d7-109">None.</span></span>|  
|<span data-ttu-id="307d7-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="307d7-110">**Default value**</span></span>|<span data-ttu-id="307d7-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="307d7-111">None.</span></span>|  
|<span data-ttu-id="307d7-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="307d7-112">**Occurrence**</span></span>|<span data-ttu-id="307d7-113">Obrigatório uma vez por elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="307d7-113">Required once per `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="307d7-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="307d7-114">Element Relationships</span></span>  
  
|<span data-ttu-id="307d7-115">Relação</span><span class="sxs-lookup"><span data-stu-id="307d7-115">Relationship</span></span>|<span data-ttu-id="307d7-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="307d7-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="307d7-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="307d7-117">**Parent element**</span></span>|[<span data-ttu-id="307d7-118">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="307d7-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="307d7-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="307d7-119">**Child elements**</span></span>|[<span data-ttu-id="307d7-120">Elemento Name para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="307d7-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="307d7-121">Elemento Database para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="307d7-121">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="307d7-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="307d7-122">Remarks</span></span>  
 <span data-ttu-id="307d7-123">Você pode especificar apenas um `Server` elemento para o `DTAInput` elemento.</span><span class="sxs-lookup"><span data-stu-id="307d7-123">You can specify only one `Server` element for the `DTAInput` element.</span></span> <span data-ttu-id="307d7-124">Esse elemento é chamado **ServerDetailsTypecomplexType** no esquema XML do DTA.</span><span class="sxs-lookup"><span data-stu-id="307d7-124">This element is of the **ServerDetailsTypecomplexType** name in the DTA XML schema.</span></span> <span data-ttu-id="307d7-125">Não confunda esse elemento `Server` com aquele que é o filho do elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="307d7-125">Do not confuse this `Server` element with the one that is the child of the `Configuration` element.</span></span> <span data-ttu-id="307d7-126">Para obter mais informações, veja [Elemento Server para configuração &#40;DTA&#41;](server-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="307d7-126">For more information, see [Server Element for Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="307d7-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="307d7-127">Example</span></span>  
 <span data-ttu-id="307d7-128">O exemplo a seguir mostra como especificar a tabela **Sales.SalesPerson** no banco de dados **AdventureWorks** no SERVER001:</span><span class="sxs-lookup"><span data-stu-id="307d7-128">The following example shows how to specify the **Sales.SalesPerson** table in the **AdventureWorks** database on SERVER001:</span></span>  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a><span data-ttu-id="307d7-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="307d7-129">See Also</span></span>  
 [<span data-ttu-id="307d7-130">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="307d7-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
