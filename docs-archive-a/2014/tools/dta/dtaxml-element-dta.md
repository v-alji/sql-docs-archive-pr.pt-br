---
title: Elemento DTAXML (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9f428cf996bb819ece74c13226fcd5116a19142b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682017"
---
# <a name="dtaxml-element-dta"></a><span data-ttu-id="3d0be-102">Elemento DTAXML (DTA)</span><span class="sxs-lookup"><span data-stu-id="3d0be-102">DTAXML Element (DTA)</span></span>
  <span data-ttu-id="3d0be-103">O elemento raiz de um arquivo de entrada ou saída XML do Orientador de Otimização do Mecanismo de Banco de Dados, **DTAXML** , contém todos os elementos que descrevem a entrada e a saída de ajuste geradas pelo Orientador.</span><span class="sxs-lookup"><span data-stu-id="3d0be-103">The root element of a Database Engine Tuning Advisor XML input or output file, **DTAXML** contains all elements that describe tuning input and the tuning output that Database Engine Tuning Advisor generates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d0be-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d0be-104">Syntax</span></span>  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="3d0be-105">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="3d0be-105">Element Attributes</span></span>  
  
|<span data-ttu-id="3d0be-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d0be-106">Attribute</span></span>|<span data-ttu-id="3d0be-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d0be-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns:xsi`|<span data-ttu-id="3d0be-108">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="3d0be-108">Required.</span></span> <span data-ttu-id="3d0be-109">Identifica o namespace da instância do esquema XML.</span><span class="sxs-lookup"><span data-stu-id="3d0be-109">Identifies the XML Schema Instance namespace.</span></span> <span data-ttu-id="3d0be-110">Os atributos deste espaço para namespace são usados como referência ao esquema que é utilizado para validar o arquivo XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="3d0be-110">Attributes from this namespace are used to reference the schema that is used to validate the Database Engine Tuning Advisor XML file.</span></span><br /><br /> <span data-ttu-id="3d0be-111">Valor obrigatório: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span><span class="sxs-lookup"><span data-stu-id="3d0be-111">Required value: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span></span>|  
|`xmlns`|<span data-ttu-id="3d0be-112">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="3d0be-112">Required.</span></span> <span data-ttu-id="3d0be-113">Identifica o namespace do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="3d0be-113">Identifies the Database Engine Tuning Advisor namespace.</span></span><br /><br /> <span data-ttu-id="3d0be-114">Se você editar o arquivo XML do Orientador de Otimização do Mecanismo de Banco de Dados usando o editor de XML no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], esse valor será usado pela Ajuda de F1 e pela Ajuda Dinâmica para localizar possíveis tópicos de referência nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d0be-114">If you edit the Database Engine Tuning Advisor XML file using the XML editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this value is used by F1 Help and Dynamic Help to locate possible reference topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span><br /><br /> <span data-ttu-id="3d0be-115">Valor obrigatório:</span><span class="sxs-lookup"><span data-stu-id="3d0be-115">Required value:</span></span><br /><br /> <span data-ttu-id="3d0be-116">do[Esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?LinkId=43100)</span><span class="sxs-lookup"><span data-stu-id="3d0be-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="3d0be-117">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="3d0be-117">Element Characteristics</span></span>  
  
|<span data-ttu-id="3d0be-118">Característica</span><span class="sxs-lookup"><span data-stu-id="3d0be-118">Characteristic</span></span>|<span data-ttu-id="3d0be-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d0be-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3d0be-120">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3d0be-120">**Data type and length**</span></span>|<span data-ttu-id="3d0be-121">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d0be-121">None.</span></span>|  
|<span data-ttu-id="3d0be-122">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="3d0be-122">**Default value**</span></span>|<span data-ttu-id="3d0be-123">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d0be-123">None.</span></span>|  
|<span data-ttu-id="3d0be-124">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="3d0be-124">**Occurrence**</span></span>|<span data-ttu-id="3d0be-125">Obrigatória uma vez por arquivo XML DTA.</span><span class="sxs-lookup"><span data-stu-id="3d0be-125">Required once per DTA XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3d0be-126">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="3d0be-126">Element Relationships</span></span>  
  
|<span data-ttu-id="3d0be-127">Relação</span><span class="sxs-lookup"><span data-stu-id="3d0be-127">Relationship</span></span>|<span data-ttu-id="3d0be-128">Elementos</span><span class="sxs-lookup"><span data-stu-id="3d0be-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3d0be-129">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="3d0be-129">**Parent element**</span></span>|<span data-ttu-id="3d0be-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3d0be-130">None</span></span>|  
|<span data-ttu-id="3d0be-131">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="3d0be-131">**Child elements**</span></span>|[<span data-ttu-id="3d0be-132">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3d0be-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)<br /><br /> <span data-ttu-id="3d0be-133">`DTAOutput`Elemento (consulte [Orientador de otimização do mecanismo de banco de dados esquema XML](https://schemas.microsoft.com/sqlserver/) para obter informações)</span><span class="sxs-lookup"><span data-stu-id="3d0be-133">`DTAOutput` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d0be-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="3d0be-134">Remarks</span></span>  
 <span data-ttu-id="3d0be-135">Para obter mais informações sobre namespaces XML, consulte [Namespaces em um documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) na Biblioteca MSDN do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d0be-135">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d0be-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3d0be-136">Example</span></span>  
 <span data-ttu-id="3d0be-137">Para obter exemplos de elementos **DTAXML** típicos, consulte [Exemplos de arquivo de entrada XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3d0be-137">For examples of typical **DTAXML** elements, see [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d0be-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d0be-138">See Also</span></span>  
 <span data-ttu-id="3d0be-139">[Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="3d0be-139">[XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="3d0be-140">Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="3d0be-140">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
