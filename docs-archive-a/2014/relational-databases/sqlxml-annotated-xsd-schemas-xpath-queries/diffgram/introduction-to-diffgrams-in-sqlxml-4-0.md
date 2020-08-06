---
title: Introdução a DiffGrams no SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotations [SQLXML]
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: 1902d67f-baf3-46e6-a36c-b24b5ba6f8ea
author: rothja
ms.author: jroth
ms.openlocfilehash: e57d87d064ace47247f342ed002b162b920e627f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574594"
---
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a><span data-ttu-id="c7813-102">Introdução a DiffGrams em SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c7813-102">Introduction to DiffGrams in SQLXML 4.0</span></span>
  <span data-ttu-id="c7813-103">Este tópico fornece uma breve introdução a DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="c7813-103">This topic provides a brief introduction to DiffGrams.</span></span>  
  
## <a name="diffgram-format"></a><span data-ttu-id="c7813-104">Formato DiffGram</span><span class="sxs-lookup"><span data-stu-id="c7813-104">DiffGram Format</span></span>  
 <span data-ttu-id="c7813-105">Este é o formato geral de DiffGram:</span><span class="sxs-lookup"><span data-stu-id="c7813-105">This is the general DiffGram format:</span></span>  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
   <DataInstance>  
      ...  
   </DataInstance>  
   [<diffgr:before>  
        ...  
   </diffgr:before>]  
  
   [<diffgr:errors>  
        ...  
   </diffgr:errors>]  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="c7813-106">O formato DiffGram consiste nestes blocos:</span><span class="sxs-lookup"><span data-stu-id="c7813-106">The DiffGram format consists of these blocks:</span></span>  
  
 **\<DataInstance>**  
 <span data-ttu-id="c7813-107">O nome desse elemento, **DataInstance**, é usado para fins explicativos nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="c7813-107">The name of this element, **DataInstance**, is used for explanation purposes in this documentation.</span></span> <span data-ttu-id="c7813-108">Por exemplo, se o DiffGram foi gerado a partir de um conjunto de um DataSet no .NET Framework, o valor da propriedade **Name** do conjunto de valores seria usado como o nome desse elemento.</span><span class="sxs-lookup"><span data-stu-id="c7813-108">For example, if the DiffGram were generated from a dataset in the .NET Framework, the value of the **Name** property of the dataset would be used as the name of this element.</span></span> <span data-ttu-id="c7813-109">Esse bloco contém todos os dados relevantes depois da alteração, possivelmente incluindo dados que não foram modificados.</span><span class="sxs-lookup"><span data-stu-id="c7813-109">This block contains all relevant data after the change, possibly including data that has not been modified.</span></span> <span data-ttu-id="c7813-110">A lógica de processamento de DiffGram ignora os elementos neste bloco para os quais o atributo **diffgr: hasChanges** não está especificado.</span><span class="sxs-lookup"><span data-stu-id="c7813-110">The DiffGram processing logic ignores the elements in this block for which the **diffgr:hasChanges** attribute is not specified.</span></span>  
  
 **\<diffgr:before>**  
 <span data-ttu-id="c7813-111">Este bloco opcional contém as instâncias do registro original (elementos) que devem ser atualizadas ou excluídas.</span><span class="sxs-lookup"><span data-stu-id="c7813-111">This optional block contains the original record instances (elements) that must be updated or deleted.</span></span> <span data-ttu-id="c7813-112">Todas as tabelas de banco de dados que estão sendo modificadas (atualizadas ou excluídas) pelo DiffGram devem aparecer como elementos de nível superior no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="c7813-112">All the database tables being modified (updated or deleted) by the DiffGram must appear as top-level elements in the **\<before>** block.</span></span>  
  
 **\<diffgr:errors>**  
 <span data-ttu-id="c7813-113">Este bloco opcional é ignorado lógica de processamento de DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c7813-113">This optional block is ignored by the DiffGram processing logic.</span></span>  
  
## <a name="diffgram-annotations"></a><span data-ttu-id="c7813-114">Anotações de DiffGram</span><span class="sxs-lookup"><span data-stu-id="c7813-114">DiffGram Annotations</span></span>  
 <span data-ttu-id="c7813-115">Essas anotações são definidas no namespace DiffGram **"urn: schemas-microsoft-com: XML-DiffGram-01"**:</span><span class="sxs-lookup"><span data-stu-id="c7813-115">These annotations are defined in the DiffGram namespace **"urn:schemas-microsoft-com:xml-diffgram-01"**:</span></span>  
  
 <span data-ttu-id="c7813-116">**id**</span><span class="sxs-lookup"><span data-stu-id="c7813-116">**id**</span></span>  
 <span data-ttu-id="c7813-117">Esse atributo é usado para emparelhar os elementos nos **\<before>** blocos e **\<DataInstance>** .</span><span class="sxs-lookup"><span data-stu-id="c7813-117">This attribute is used to pair the elements in the **\<before>** and the **\<DataInstance>** blocks.</span></span>  
  
 <span data-ttu-id="c7813-118">**hasChanges**</span><span class="sxs-lookup"><span data-stu-id="c7813-118">**hasChanges**</span></span>  
 <span data-ttu-id="c7813-119">Para uma operação de inserção ou de atualização, o DiffGram deve especificar esse atributo com o valor **inserido** ou **modificado**.</span><span class="sxs-lookup"><span data-stu-id="c7813-119">For an insert or an update operation, the DiffGram must specify this attribute with the value **inserted** or **modified**.</span></span> <span data-ttu-id="c7813-120">Se esse atributo não estiver presente, o elemento correspondente no **\<DataInstance>** será ignorado pela lógica de processamento e nenhuma atualização será executada.</span><span class="sxs-lookup"><span data-stu-id="c7813-120">If this attribute is not present, the corresponding element in the **\<DataInstance>** is ignored by the processing logic and no updates are performed.</span></span> <span data-ttu-id="c7813-121">Para obter exemplos de trabalho, consulte [exemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c7813-121">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="c7813-122">**parentID**</span><span class="sxs-lookup"><span data-stu-id="c7813-122">**parentID**</span></span>  
 <span data-ttu-id="c7813-123">Este atributo é usado para especificar relações pai/filho entre os elementos em DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c7813-123">This attribute is used to specify parent-child relationships among the elements in the DiffGram.</span></span> <span data-ttu-id="c7813-124">Esse atributo aparece apenas no \<before> bloco.</span><span class="sxs-lookup"><span data-stu-id="c7813-124">This attribute appears only in the \<before> block.</span></span> <span data-ttu-id="c7813-125">Ele é usado pelo SQLXML durante a aplicação das atualizações.</span><span class="sxs-lookup"><span data-stu-id="c7813-125">It is used by SQLXML when applying updates.</span></span> <span data-ttu-id="c7813-126">A relação pai/filho é usada para determinar a ordem na qual os elementos de DiffGram são processados.</span><span class="sxs-lookup"><span data-stu-id="c7813-126">The parent-child relationship is used in determining the order in which the elements in the DiffGram are processed.</span></span>  
  
## <a name="understanding-the-diffgram-processing-logic"></a><span data-ttu-id="c7813-127">Compreendendo a lógica de processamento de DiffGram</span><span class="sxs-lookup"><span data-stu-id="c7813-127">Understanding the DiffGram Processing Logic</span></span>  
 <span data-ttu-id="c7813-128">A lógica de processamento de DiffGram usa regras específicas para determinar se uma operação é de inserção, atualização ou exclusão.</span><span class="sxs-lookup"><span data-stu-id="c7813-128">The DiffGram processing logic uses certain rules to determine whether an operation is an insert, update, or delete operation.</span></span> <span data-ttu-id="c7813-129">Essas regras são descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c7813-129">These rules are described in the following table.</span></span>  
  
|<span data-ttu-id="c7813-130">Operação</span><span class="sxs-lookup"><span data-stu-id="c7813-130">Operation</span></span>|<span data-ttu-id="c7813-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7813-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7813-132">Inserir</span><span class="sxs-lookup"><span data-stu-id="c7813-132">Insert</span></span>|<span data-ttu-id="c7813-133">Um DiffGram indica uma operação de inserção quando um elemento é exibido no **\<DataInstance>** bloco, mas não no **\<before>** bloco correspondente, e o atributo **diffgr: hasChanges** é especificado (**diffgr: hasChanges = inserted**) no elemento.</span><span class="sxs-lookup"><span data-stu-id="c7813-133">A DiffGram indicates an insert operation when an element appears in the **\<DataInstance>** block but not in the corresponding **\<before>** block, and the **diffgr:hasChanges** attribute is specified (**diffgr:hasChanges=inserted**) on the element.</span></span> <span data-ttu-id="c7813-134">Nesse caso, o DiffGram insere a instância de registro especificada no **\<DataInstance>** bloco no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7813-134">In this case, the DiffGram inserts the record instance that is specified in the **\<DataInstance>** block into the database.</span></span><br /><br /> <span data-ttu-id="c7813-135">Se o atributo **diffgr: hasChanges** não for especificado, o elemento será ignorado pela lógica de processamento e nenhuma inserção será executada.</span><span class="sxs-lookup"><span data-stu-id="c7813-135">If the **diffgr:hasChanges** attribute is not specified, the element is ignored by the processing logic and no insert is performed.</span></span> <span data-ttu-id="c7813-136">Para obter exemplos de trabalho, consulte [exemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c7813-136">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>|  
|<span data-ttu-id="c7813-137">Atualização</span><span class="sxs-lookup"><span data-stu-id="c7813-137">Update</span></span>|<span data-ttu-id="c7813-138">O DiffGram indica uma operação de atualização quando há um elemento no \<before> bloco para o qual há um elemento correspondente no **\<DataInstance>** bloco (ou seja, ambos os elementos têm um atributo **diffgr: ID** com o mesmo valor) e o atributo **diffgr: hasChanges** é especificado com o valor **modificado** no elemento no **\<DataInstance>** bloco.</span><span class="sxs-lookup"><span data-stu-id="c7813-138">The DiffGram indicates an update operation when there is an element in the \<before> block for which there is a corresponding element in the **\<DataInstance>** block (that is, both elements have a **diffgr:id** attribute with same value) and the **diffgr:hasChanges** attribute is specified with the value **modified** on the element in the **\<DataInstance>** block.</span></span><br /><br /> <span data-ttu-id="c7813-139">Se o atributo **diffgr: hasChanges** não for especificado no elemento no **\<DataInstance>** bloco, um erro será retornado pela lógica de processamento.</span><span class="sxs-lookup"><span data-stu-id="c7813-139">If the **diffgr:hasChanges** attribute is not specified on the element in the **\<DataInstance>** block, an error is returned by the processing logic.</span></span> <span data-ttu-id="c7813-140">Para obter exemplos de trabalho, consulte [exemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c7813-140">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="c7813-141">Se **diffgr: parentID** for especificado no **\<before>** bloco, a relação pai-filho dos elementos especificados por **parentID** será usada para determinar a ordem na qual os registros são atualizados.</span><span class="sxs-lookup"><span data-stu-id="c7813-141">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are updated.</span></span>|  
|<span data-ttu-id="c7813-142">Excluir</span><span class="sxs-lookup"><span data-stu-id="c7813-142">Delete</span></span>|<span data-ttu-id="c7813-143">Um DiffGram indica uma operação de exclusão quando um elemento é exibido no **\<before>** bloco, mas não no **\<DataInstance>** bloco correspondente.</span><span class="sxs-lookup"><span data-stu-id="c7813-143">A DiffGram indicates a delete operation when an element appears in the **\<before>** block but not in the corresponding **\<DataInstance>** block.</span></span> <span data-ttu-id="c7813-144">Nesse caso, o DiffGram exclui a instância de registro especificada no **\<before>** bloco do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7813-144">In this case, the DiffGram deletes the record instance that is specified in the **\<before>** block from the database.</span></span> <span data-ttu-id="c7813-145">Para obter exemplos de trabalho, consulte [exemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c7813-145">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="c7813-146">Se **diffgr: parentID** for especificado no **\<before>** bloco, a relação pai-filho dos elementos especificados por **parentID** será usada para determinar a ordem na qual os registros são excluídos.</span><span class="sxs-lookup"><span data-stu-id="c7813-146">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are deleted.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="c7813-147">Parâmetros não podem ser passados para DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="c7813-147">Parameters cannot be passed to DiffGrams.</span></span>  
  
  
