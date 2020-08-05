---
title: Elemento de carga de trabalho (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Workload element
ms.assetid: 68ffd473-6546-4015-98d0-3763165de65c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20184760c3fcb5eed6c02b8f8fd9b63f5586c9af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572888"
---
# <a name="workload-element-dta"></a><span data-ttu-id="d11cf-102">Elemento de carga de trabalho (DTA)</span><span class="sxs-lookup"><span data-stu-id="d11cf-102">Workload Element (DTA)</span></span>
  <span data-ttu-id="d11cf-103">Especifica a carga de trabalho a ser usada em uma sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="d11cf-103">Specifies the workload to be used for a tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11cf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d11cf-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d11cf-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="d11cf-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d11cf-106">Característica</span><span class="sxs-lookup"><span data-stu-id="d11cf-106">Characteristic</span></span>|<span data-ttu-id="d11cf-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="d11cf-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d11cf-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d11cf-108">**Data type and length**</span></span>|<span data-ttu-id="d11cf-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d11cf-109">None.</span></span>|  
|<span data-ttu-id="d11cf-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="d11cf-110">**Default value**</span></span>|<span data-ttu-id="d11cf-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d11cf-111">None.</span></span>|  
|<span data-ttu-id="d11cf-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="d11cf-112">**Occurrence**</span></span>|<span data-ttu-id="d11cf-113">Necessário uma vez para cada elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="d11cf-113">Required once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d11cf-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="d11cf-114">Element Relationships</span></span>  
  
|<span data-ttu-id="d11cf-115">Relação</span><span class="sxs-lookup"><span data-stu-id="d11cf-115">Relationship</span></span>|<span data-ttu-id="d11cf-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="d11cf-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d11cf-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="d11cf-117">**Parent element**</span></span>|[<span data-ttu-id="d11cf-118">Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="d11cf-118">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)|  
|<span data-ttu-id="d11cf-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="d11cf-119">**Child elements**</span></span>|[<span data-ttu-id="d11cf-120">Elemento File &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d11cf-120">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)<br /><br /> [<span data-ttu-id="d11cf-121">Elemento Database para Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d11cf-121">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)<br /><br /> [<span data-ttu-id="d11cf-122">Elemento EventString &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d11cf-122">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="d11cf-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="d11cf-123">Remarks</span></span>  
 <span data-ttu-id="d11cf-124">A carga de trabalho é um conjunto de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas em um ou mais bancos de dados a serem ajustados.</span><span class="sxs-lookup"><span data-stu-id="d11cf-124">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="d11cf-125">O Orientador de Otimização do Mecanismo de Banco de Dados pode usar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , arquivos de rastreamento e tabelas de rastreamento como cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d11cf-125">The Database Engine Tuning Advisor can use [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, trace files, and trace tables as workloads.</span></span>  
  
 <span data-ttu-id="d11cf-126">Se você especificar uma carga de trabalho em arquivo de entrada XML e uma carga de trabalho na linha de comando com a ferramenta **dta** , a carga de trabalho especificada na linha de comando será usada para ajuste.</span><span class="sxs-lookup"><span data-stu-id="d11cf-126">If you specify a workload in an XML input file and a workload on the command line with the **dta** tool, the workload specified on the command line will be used for tuning.</span></span> <span data-ttu-id="d11cf-127">Todas as opções de ajuste especificadas na linha de comando substituem as que foram especificadas no arquivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="d11cf-127">All tuning options specified on the command line override those that are specified in an XML input file.</span></span> <span data-ttu-id="d11cf-128">A única exceção será se uma configuração especificada pelo usuário for digitada dentro do modo de avaliação no arquivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="d11cf-128">The only exception is if a user-specified configuration is entered in the evaluate mode in the XML input file.</span></span> <span data-ttu-id="d11cf-129">Por exemplo, se a configuração digitada no elemento `Configuration` do arquivo de entrada XML do elemento `EvaluateConfiguration` também for especificada como uma das opções de ajuste, as opções de ajuste especificadas no arquivo de entrada XML substituirão todas as opções de ajuste da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d11cf-129">For example, if a configuration is entered in the `Configuration` element of the XML input file and the `EvaluateConfiguration` element is also specified as one of the tuning options, the tuning options specified in the XML input file will override any tuning options entered at the command line.</span></span>  
  
 <span data-ttu-id="d11cf-130">É preciso especificar uma carga de trabalho para cada sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="d11cf-130">One workload must be specified for each tuning session.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d11cf-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d11cf-131">Example</span></span>  
 <span data-ttu-id="d11cf-132">O exemplo de código a seguir especifica a tabela de rastreamento **MyDatabase. MyDBOwner. TuningTable001** para o `Workload` elemento.</span><span class="sxs-lookup"><span data-stu-id="d11cf-132">The following code example specifies the **MyDatabase.MyDBOwner.TuningTable001** trace table for the `Workload` element.</span></span> <span data-ttu-id="d11cf-133">A **TuningTable001** foi criada usando-se do modelo de ajuste com o SQL Server Profiler e salvando a saída do rastreamento como tabela.</span><span class="sxs-lookup"><span data-stu-id="d11cf-133">The **TuningTable001** was created by using the Tuning template with SQL Server Profiler and saving the trace output as a table.</span></span>  
  
```  
<DTAXML ...>  
  <DTAInput>  
    <Server>  
...code removed here...  
    </Server>  
    <Workload>  
      <Database>  
        <Name>MyDatabase</Name>  
        <Schema>  
          <Name>MyDBOwner</Name>  
            <Table>  
              <Name>TuningTable001</Name>  
            </Table>  
        </Schema>  
      </Database>  
    </Workload>  
...code removed here...  
  </DTAInput>  
</DTAXML>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d11cf-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d11cf-134">See Also</span></span>  
 [<span data-ttu-id="d11cf-135">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="d11cf-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
