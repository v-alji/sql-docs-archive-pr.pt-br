---
title: Elemento Issue (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- issue element
- XML output file format [ssbdiagnose], issue element
- ssbdiagnose
ms.assetid: 2246a886-686b-44ca-9771-b155cedad8be
author: stevestein
ms.author: sstein
ms.openlocfilehash: a178c1323c1c20f84e67d4d7699fc313090a4c71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678381"
---
# <a name="issue-element-ssbdiagnose"></a><span data-ttu-id="c8c2a-102">Elemento Issue (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="c8c2a-102">Issue Element (ssbdiagnose)</span></span>
  <span data-ttu-id="c8c2a-103">Reporta um problema que foi encontrado pelo utilitário **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="c8c2a-103">Reports an issue that was found by the **ssbdiagnose** utility.</span></span> <span data-ttu-id="c8c2a-104">O arquivo de saída XML de **ssbdiagnose** tem um elemento Issue por problema reportado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-104">The **ssbdiagnose** XML output file has one Issue element per issue reported.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c2a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c8c2a-105">Syntax</span></span>  
  
```  
  
<Issue  
    type="..."   
    code="..."   
    server="..."   
    database="..."   
    object="...">   
    ...   
</Issue>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="c8c2a-106">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="c8c2a-106">Element Attributes</span></span>  
  
|<span data-ttu-id="c8c2a-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8c2a-107">Attribute</span></span>|<span data-ttu-id="c8c2a-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8c2a-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="c8c2a-109">Identifica qual categoria de problema o elemento Issue está reportando:</span><span class="sxs-lookup"><span data-stu-id="c8c2a-109">Identifies which category of problem the Issue element is reporting:</span></span><br /><br /> <span data-ttu-id="c8c2a-110">**"Diagnóstico"** reporta um problema de configuração encontrado durante a análise da configuração de um [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8c2a-110">**"Diagnosis"** Reports a configuration issue found when you analyze a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span><br /><br /> <span data-ttu-id="c8c2a-111">**"Problema"** reporta um problema que impediu o **ssbdiagnose** de concluir sua análise.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-111">**"Problem"** Reports an issue that has prevented **ssbdiagnose** from completing its analysis.</span></span> <span data-ttu-id="c8c2a-112">Corrija o problema e execute o **ssbdiagnose**novamente.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-112">Correct the problem and rerun **ssbdiagnose**.</span></span><br /><br /> <span data-ttu-id="c8c2a-113">**"Evento"** reporta um evento [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] encontrado quando você executa uma verificação de **-RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="c8c2a-113">**"Event"** Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event found when you run a **-RUNTIME** check.</span></span> <span data-ttu-id="c8c2a-114">Os eventos só serão reportados se **-SHOWEVENTS** for especificado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-114">Events are only reported if **-SHOWEVENTS** is specified.</span></span>|  
|`code`|<span data-ttu-id="c8c2a-115">Identifica o número de erro da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-115">Identifies the error number for the message.</span></span>|  
|`server`|<span data-ttu-id="c8c2a-116">Identifica a instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] na qual o problema foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-116">Identifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the problem was found.</span></span> <span data-ttu-id="c8c2a-117">Se o problema estava em uma instância padrão, o atributo de servidor só terá o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-117">If the problem was in a default instance, the server attribute only has the computer name.</span></span> <span data-ttu-id="c8c2a-118">Se o problema estava em uma instância nomeada, o atributo de servidor estará no formato NomedoComputador\NomedaInstância.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-118">If the problem was in a named instance, the server attribute is in the form ComputerName\InstanceName.</span></span>|  
|`database`|<span data-ttu-id="c8c2a-119">Identifica o nome do banco de dados no qual o problema foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-119">Identifies the name of the database in which the problem was found.</span></span>|  
|`object`|<span data-ttu-id="c8c2a-120">Identifica o nome do objeto no qual o problema foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-120">Identifies the name of the object in which the problem was found.</span></span> <span data-ttu-id="c8c2a-121">Se o problema ocorreu em um nível de instância ou banco de dados, o atributo de objeto repetirá o nome da instância ou do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-121">If the problem was an instance or database level issue, the object attribute repeats the instance or database name.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="c8c2a-122">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="c8c2a-122">Element Characteristics</span></span>  
  
|<span data-ttu-id="c8c2a-123">Característica</span><span class="sxs-lookup"><span data-stu-id="c8c2a-123">Characteristic</span></span>|<span data-ttu-id="c8c2a-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8c2a-124">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c8c2a-125">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c8c2a-125">**Data type and length**</span></span>|<span data-ttu-id="c8c2a-126">`string`, tamanho é ilimitado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-126">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="c8c2a-127">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c8c2a-127">**Value**</span></span>|<span data-ttu-id="c8c2a-128">Retorna o texto da mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-128">Returns the text of the error message.</span></span>|  
|<span data-ttu-id="c8c2a-129">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="c8c2a-129">**Occurrence**</span></span>|<span data-ttu-id="c8c2a-130">Uma vez por erro reportado.</span><span class="sxs-lookup"><span data-stu-id="c8c2a-130">Once per reported error.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c8c2a-131">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="c8c2a-131">Element Relationships</span></span>  
  
|<span data-ttu-id="c8c2a-132">Relação</span><span class="sxs-lookup"><span data-stu-id="c8c2a-132">Relationship</span></span>|<span data-ttu-id="c8c2a-133">Elementos</span><span class="sxs-lookup"><span data-stu-id="c8c2a-133">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c8c2a-134">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="c8c2a-134">**Parent element**</span></span>|[<span data-ttu-id="c8c2a-135">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c2a-135">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="c8c2a-136">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="c8c2a-136">**Child elements**</span></span>|<span data-ttu-id="c8c2a-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c8c2a-137">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8c2a-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c8c2a-138">Example</span></span>  
 <span data-ttu-id="c8c2a-139">Este elemento reporta um erro 1102 para um banco de dados que não tenha uma chave mestra e o erro foi encontrado durante a análise de uma configuração do [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8c2a-139">This element reports an 1102 error for a database that does not have a master key, where the error was found when you analyzed a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span>  
  
```  
<Issue type="Diagnosis" code="1102" server="TestComputer" database="TargetDB" object="TargetDB">The master key was not found</diagnostic>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8c2a-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8c2a-140">See Also</span></span>  
 [<span data-ttu-id="c8c2a-141">Utilitário ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c2a-141">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
