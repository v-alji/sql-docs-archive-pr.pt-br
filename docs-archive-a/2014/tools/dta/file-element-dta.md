---
title: Elemento File (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0eeb2bdcc9513ca6283447daca63c8bbc4fa1726
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683257"
---
# <a name="file-element-dta"></a><span data-ttu-id="1779b-102">Elemento de arquivo (DTA)</span><span class="sxs-lookup"><span data-stu-id="1779b-102">File Element (DTA)</span></span>
  <span data-ttu-id="1779b-103">Especifica o arquivo da carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1779b-103">Specifies the workload file.</span></span> <span data-ttu-id="1779b-104">A carga de trabalho é um conjunto de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas em um ou mais bancos de dados a serem ajustados.</span><span class="sxs-lookup"><span data-stu-id="1779b-104">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="1779b-105">Os arquivos de carga de trabalho podem ser scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] (.sql) ou arquivos de rastreamento (.trc).</span><span class="sxs-lookup"><span data-stu-id="1779b-105">Workload files can be [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts (.sql) or trace files (.trc).</span></span> <span data-ttu-id="1779b-106">Para obter mais informações, consulte [Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="1779b-106">For more information, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1779b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1779b-107">Syntax</span></span>  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="1779b-108">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="1779b-108">Element Characteristics</span></span>  
  
|<span data-ttu-id="1779b-109">Característica</span><span class="sxs-lookup"><span data-stu-id="1779b-109">Characteristic</span></span>|<span data-ttu-id="1779b-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="1779b-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1779b-111">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="1779b-111">**Data type and length**</span></span>|<span data-ttu-id="1779b-112">Use o tipo de dados `string` para especificar o caminho de diretório para o arquivo de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1779b-112">Use the `string` data type to specify the directory path to your workload file.</span></span> <span data-ttu-id="1779b-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1779b-113">For example:</span></span><br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> <span data-ttu-id="1779b-114">O limite de comprimento é aplicado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="1779b-114">Length limit is enforced by the server.</span></span>|  
|<span data-ttu-id="1779b-115">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="1779b-115">**Default value**</span></span>|<span data-ttu-id="1779b-116">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1779b-116">None.</span></span>|  
|<span data-ttu-id="1779b-117">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="1779b-117">**Occurrence**</span></span>|<span data-ttu-id="1779b-118">Exigido uma vez se não houver outro tipo de carga de trabalho especificada.</span><span class="sxs-lookup"><span data-stu-id="1779b-118">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="1779b-119">É preciso especificar um elemento filho **EventString**, **File**ou **Database** para o pai **Workload** , mas só pode ser usado um tipo.</span><span class="sxs-lookup"><span data-stu-id="1779b-119">You must specify an **EventString**, a **File**, or a **Database** child element for the **Workload** parent, but only one type can be used.</span></span> <span data-ttu-id="1779b-120">Por exemplo, se uma carga de trabalho com o elemento **File** for especificada, não será possível especificar uma carga de trabalho com o elemento **Database** no mesmo arquivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="1779b-120">For example, if you specify a workload with the **File** element, then you cannot also specify a workload with the **Database** element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="1779b-121">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="1779b-121">Element Relationships</span></span>  
  
|<span data-ttu-id="1779b-122">Relação</span><span class="sxs-lookup"><span data-stu-id="1779b-122">Relationship</span></span>|<span data-ttu-id="1779b-123">Elementos</span><span class="sxs-lookup"><span data-stu-id="1779b-123">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="1779b-124">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="1779b-124">**Parent element**</span></span>|[<span data-ttu-id="1779b-125">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="1779b-125">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="1779b-126">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="1779b-126">**Child elements**</span></span>|<span data-ttu-id="1779b-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1779b-127">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1779b-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1779b-128">Example</span></span>  
 <span data-ttu-id="1779b-129">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivos de entrada XML simples &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="1779b-129">For a usage example of this element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1779b-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1779b-130">See Also</span></span>  
 [<span data-ttu-id="1779b-131">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1779b-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
