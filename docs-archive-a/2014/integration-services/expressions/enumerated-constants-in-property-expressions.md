---
title: Constantes enumeradas em expressões de propriedade | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], expressions
- dynamic properties
- updating package properties
- enumerated constants [Integration Services]
- property expressions [Integration Services]
ms.assetid: a4418315-38e2-4ad3-8784-576163b25d6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cb4ae32bf564e98d8cfc843e9497b15222fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681047"
---
# <a name="enumerated-constants-in-property-expressions"></a><span data-ttu-id="87d03-102">Constantes enumeradas em expressões de propriedade</span><span class="sxs-lookup"><span data-stu-id="87d03-102">Enumerated Constants in Property Expressions</span></span>
  <span data-ttu-id="87d03-103">Se as expressões de propriedade incluírem valores de uma lista de membros de enumerador, a expressão deverá usar o valor numérico do membro de enumerador em vez do nome amigável do membro.</span><span class="sxs-lookup"><span data-stu-id="87d03-103">If property expressions include values from an enumerator member list, the expression must use the numeric value of the enumerator member instead of the friendly name of the member.</span></span> <span data-ttu-id="87d03-104">Por exemplo, se uma expressão definir a propriedade `LoggingMode`, use o valor numérico 2 em vez do nome amigável Desabilitada.</span><span class="sxs-lookup"><span data-stu-id="87d03-104">For example, if an expression sets the `LoggingMode` property then you must use the numeric value 2 instead of the friendly name Disabled.</span></span>  
  
 <span data-ttu-id="87d03-105">Este tópico relaciona apenas os valores numéricos equivalentes a nomes amigáveis de enumeradores cujos membros são usados normalmente em expressões de propriedade.</span><span class="sxs-lookup"><span data-stu-id="87d03-105">This topic lists only the numeric values equivalent to friendly names of enumerators whose members are commonly used in property expressions.</span></span> <span data-ttu-id="87d03-106">O modelo de objeto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui muitos enumeradores adicionais que podem ser usados quando você programa o modelo de objeto para criar pacotes programaticamente ou codifica elementos personalizados de pacote como tarefas e componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="87d03-106">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model includes many additional enumerators that you use when you program the object model to build packages programmatically or code custom package elements such as tasks and data flow components.</span></span>  
  
 <span data-ttu-id="87d03-107">Além das propriedades personalizadas para pacotes e objetos de pacote, a janela Propriedades do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] inclui um conjunto de propriedades disponíveis para pacotes, tarefas e os contêineres Loop Foreach, Loop For e Sequência.</span><span class="sxs-lookup"><span data-stu-id="87d03-107">In addition to the custom properties for packages and package objects, the Properties window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a set of properties that are available to packages, tasks, and the Foreach Loop, For Loop, and Sequence containers.</span></span> <span data-ttu-id="87d03-108">As propriedades comuns que são definidas por valores de enumeradores- `ForceExecutionResult` , `LoggingMode` , `IsolationLevel` e `Transaction Option` -são listadas na seção Propriedades comuns.</span><span class="sxs-lookup"><span data-stu-id="87d03-108">The common properties that are set by values from enumerators-`ForceExecutionResult`, `LoggingMode`, `IsolationLevel`, and `Transaction Option`-are listed in Common Properties section.</span></span>  
  
 <span data-ttu-id="87d03-109">As seções a seguir fornecem informações sobre constantes enumeradas:</span><span class="sxs-lookup"><span data-stu-id="87d03-109">The following sections provide information about enumerated constants:</span></span>  
  
 [<span data-ttu-id="87d03-110">Pacote</span><span class="sxs-lookup"><span data-stu-id="87d03-110">Package</span></span>](#Package)  
  
 [<span data-ttu-id="87d03-111">Enumeradores de Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="87d03-111">Foreach Loop Enumerators</span></span>](#Foreach)  
  
 [<span data-ttu-id="87d03-112">Tarefas</span><span class="sxs-lookup"><span data-stu-id="87d03-112">Tasks</span></span>](#Tasks)  
  
 [<span data-ttu-id="87d03-113">Tarefas do Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="87d03-113">Maintenance Plan Tasks</span></span>](#MaintenancePlanTasks)  
  
 [<span data-ttu-id="87d03-114">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="87d03-114">Common Properties</span></span>](#CommonProperties)  
  
##  <a name="package"></a><a name="Package"></a> <span data-ttu-id="87d03-115">Pacote</span><span class="sxs-lookup"><span data-stu-id="87d03-115">Package</span></span>  
 <span data-ttu-id="87d03-116">As tabelas a seguir relacionam os nomes amigáveis e os equivalentes em valor numérico para propriedades de pacotes definidas por você usando valores de um enumerador.</span><span class="sxs-lookup"><span data-stu-id="87d03-116">The following tables lists the friendly names and the numeric value equivalents for properties of packages that you set by using values from an enumerator.</span></span>  
  
 <span data-ttu-id="87d03-117">`PackageType`Propriedade-definido usando valores da `DTSPackageType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-117">`PackageType` property-Set by using values from the `DTSPackageType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-118">Nome amigável em DTSPackageType</span><span class="sxs-lookup"><span data-stu-id="87d03-118">Friendly name in DTSPackageType</span></span>|<span data-ttu-id="87d03-119">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-119">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-120">Padrão</span><span class="sxs-lookup"><span data-stu-id="87d03-120">Default</span></span>|<span data-ttu-id="87d03-121">0</span><span class="sxs-lookup"><span data-stu-id="87d03-121">0</span></span>|  
|<span data-ttu-id="87d03-122">DTSWizard</span><span class="sxs-lookup"><span data-stu-id="87d03-122">DTSWizard</span></span>|<span data-ttu-id="87d03-123">1</span><span class="sxs-lookup"><span data-stu-id="87d03-123">1</span></span>|  
|<span data-ttu-id="87d03-124">DTSDesigner</span><span class="sxs-lookup"><span data-stu-id="87d03-124">DTSDesigner</span></span>|<span data-ttu-id="87d03-125">2</span><span class="sxs-lookup"><span data-stu-id="87d03-125">2</span></span>|  
|<span data-ttu-id="87d03-126">SQLReplication</span><span class="sxs-lookup"><span data-stu-id="87d03-126">SQLReplication</span></span>|<span data-ttu-id="87d03-127">3</span><span class="sxs-lookup"><span data-stu-id="87d03-127">3</span></span>|  
|<span data-ttu-id="87d03-128">DTSDesigner100</span><span class="sxs-lookup"><span data-stu-id="87d03-128">DTSDesigner100</span></span>|<span data-ttu-id="87d03-129">5</span><span class="sxs-lookup"><span data-stu-id="87d03-129">5</span></span>|  
|<span data-ttu-id="87d03-130">SQLDBMaint</span><span class="sxs-lookup"><span data-stu-id="87d03-130">SQLDBMaint</span></span>|<span data-ttu-id="87d03-131">6</span><span class="sxs-lookup"><span data-stu-id="87d03-131">6</span></span>|  
  
 <span data-ttu-id="87d03-132">`CheckpointUsage`Propriedade-definido usando valores da `DTSCheckpointUsage` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-132">`CheckpointUsage` property-Set by using values from the `DTSCheckpointUsage` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-133">Nome amigável em DTSCheckpointUsage</span><span class="sxs-lookup"><span data-stu-id="87d03-133">Friendly name in DTSCheckpointUsage</span></span>|<span data-ttu-id="87d03-134">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-134">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="87d03-135">Never</span><span class="sxs-lookup"><span data-stu-id="87d03-135">Never</span></span>|<span data-ttu-id="87d03-136">0</span><span class="sxs-lookup"><span data-stu-id="87d03-136">0</span></span>|  
|<span data-ttu-id="87d03-137">IfExists</span><span class="sxs-lookup"><span data-stu-id="87d03-137">IfExists</span></span>|<span data-ttu-id="87d03-138">1</span><span class="sxs-lookup"><span data-stu-id="87d03-138">1</span></span>|  
|<span data-ttu-id="87d03-139">Sempre</span><span class="sxs-lookup"><span data-stu-id="87d03-139">Always</span></span>|<span data-ttu-id="87d03-140">2</span><span class="sxs-lookup"><span data-stu-id="87d03-140">2</span></span>|  
  
 <span data-ttu-id="87d03-141">`PackagePriorityClass`Propriedade-definido usando valores da `DTSPriorityClass` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-141">`PackagePriorityClass` property-Set by using values from the `DTSPriorityClass` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-142">Nome amigável em DTSPriorityClass</span><span class="sxs-lookup"><span data-stu-id="87d03-142">Friendly name in DTSPriorityClass</span></span>|<span data-ttu-id="87d03-143">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-143">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="87d03-144">Padrão</span><span class="sxs-lookup"><span data-stu-id="87d03-144">Default</span></span>|<span data-ttu-id="87d03-145">0</span><span class="sxs-lookup"><span data-stu-id="87d03-145">0</span></span>|  
|<span data-ttu-id="87d03-146">AboveNormal</span><span class="sxs-lookup"><span data-stu-id="87d03-146">AboveNormal</span></span>|<span data-ttu-id="87d03-147">1</span><span class="sxs-lookup"><span data-stu-id="87d03-147">1</span></span>|  
|<span data-ttu-id="87d03-148">Normal</span><span class="sxs-lookup"><span data-stu-id="87d03-148">Normal</span></span>|<span data-ttu-id="87d03-149">2</span><span class="sxs-lookup"><span data-stu-id="87d03-149">2</span></span>|  
|<span data-ttu-id="87d03-150">BelowNormal</span><span class="sxs-lookup"><span data-stu-id="87d03-150">BelowNormal</span></span>|<span data-ttu-id="87d03-151">3</span><span class="sxs-lookup"><span data-stu-id="87d03-151">3</span></span>|  
|<span data-ttu-id="87d03-152">Idle</span><span class="sxs-lookup"><span data-stu-id="87d03-152">Idle</span></span>|<span data-ttu-id="87d03-153">4</span><span class="sxs-lookup"><span data-stu-id="87d03-153">4</span></span>|  
  
 <span data-ttu-id="87d03-154">`ProtectionLevel`Propriedade-definido usando valores da `DTSProtectionLevel` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-154">`ProtectionLevel` property-Set by using values from the `DTSProtectionLevel` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-155">Nome amigável em DTSProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="87d03-155">Friendly name in DTSProtectionLevel</span></span>|<span data-ttu-id="87d03-156">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-156">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="87d03-157">DontSaveSensitive</span><span class="sxs-lookup"><span data-stu-id="87d03-157">DontSaveSensitive</span></span>|<span data-ttu-id="87d03-158">0</span><span class="sxs-lookup"><span data-stu-id="87d03-158">0</span></span>|  
|<span data-ttu-id="87d03-159">EncryptSensitiveWithUserKey</span><span class="sxs-lookup"><span data-stu-id="87d03-159">EncryptSensitiveWithUserKey</span></span>|<span data-ttu-id="87d03-160">1</span><span class="sxs-lookup"><span data-stu-id="87d03-160">1</span></span>|  
|<span data-ttu-id="87d03-161">EncryptSensitiveWithPassword</span><span class="sxs-lookup"><span data-stu-id="87d03-161">EncryptSensitiveWithPassword</span></span>|<span data-ttu-id="87d03-162">2</span><span class="sxs-lookup"><span data-stu-id="87d03-162">2</span></span>|  
|<span data-ttu-id="87d03-163">EncryptAllWithPassword</span><span class="sxs-lookup"><span data-stu-id="87d03-163">EncryptAllWithPassword</span></span>|<span data-ttu-id="87d03-164">3</span><span class="sxs-lookup"><span data-stu-id="87d03-164">3</span></span>|  
|<span data-ttu-id="87d03-165">EncryptAllWithUserKey</span><span class="sxs-lookup"><span data-stu-id="87d03-165">EncryptAllWithUserKey</span></span>|<span data-ttu-id="87d03-166">4</span><span class="sxs-lookup"><span data-stu-id="87d03-166">4</span></span>|  
|<span data-ttu-id="87d03-167">ServerStorage</span><span class="sxs-lookup"><span data-stu-id="87d03-167">ServerStorage</span></span>|<span data-ttu-id="87d03-168">5</span><span class="sxs-lookup"><span data-stu-id="87d03-168">5</span></span>|  
  
##  <a name="precedence-constraints"></a><a name="PrecedenceConstraints"></a> <span data-ttu-id="87d03-169">Restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="87d03-169">Precedence Constraints</span></span>  
 <span data-ttu-id="87d03-170">`EvalOp`Propriedade-definido usando valores da `DTSPrecedenceEvalOp` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-170">`EvalOp` property-Set by using values from the `DTSPrecedenceEvalOp` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-171">Nome amigável em DTSPrecedenceEvalOp</span><span class="sxs-lookup"><span data-stu-id="87d03-171">Friendly name in DTSPrecedenceEvalOp</span></span>|<span data-ttu-id="87d03-172">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-172">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-173">Expression</span><span class="sxs-lookup"><span data-stu-id="87d03-173">Expression</span></span>|<span data-ttu-id="87d03-174">1</span><span class="sxs-lookup"><span data-stu-id="87d03-174">1</span></span>|  
|<span data-ttu-id="87d03-175">Constraint</span><span class="sxs-lookup"><span data-stu-id="87d03-175">Constraint</span></span>|<span data-ttu-id="87d03-176">2</span><span class="sxs-lookup"><span data-stu-id="87d03-176">2</span></span>|  
|<span data-ttu-id="87d03-177">ExpressionAndConstraint</span><span class="sxs-lookup"><span data-stu-id="87d03-177">ExpressionAndConstraint</span></span>|<span data-ttu-id="87d03-178">3</span><span class="sxs-lookup"><span data-stu-id="87d03-178">3</span></span>|  
|<span data-ttu-id="87d03-179">ExpressionOrConstraint</span><span class="sxs-lookup"><span data-stu-id="87d03-179">ExpressionOrConstraint</span></span>|<span data-ttu-id="87d03-180">4</span><span class="sxs-lookup"><span data-stu-id="87d03-180">4</span></span>|  
  
 <span data-ttu-id="87d03-181">`Value`Propriedade-definido usando valores da `DTSExecResult` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-181">`Value` property-Set by using values from the `DTSExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-182">Nome amigável</span><span class="sxs-lookup"><span data-stu-id="87d03-182">Friendly Name</span></span>|<span data-ttu-id="87d03-183">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-183">Numeric Value</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="87d03-184">Sucesso</span><span class="sxs-lookup"><span data-stu-id="87d03-184">Success</span></span>|<span data-ttu-id="87d03-185">0</span><span class="sxs-lookup"><span data-stu-id="87d03-185">0</span></span>|  
|<span data-ttu-id="87d03-186">Falha</span><span class="sxs-lookup"><span data-stu-id="87d03-186">Failure</span></span>|<span data-ttu-id="87d03-187">1</span><span class="sxs-lookup"><span data-stu-id="87d03-187">1</span></span>|  
|<span data-ttu-id="87d03-188">Completion</span><span class="sxs-lookup"><span data-stu-id="87d03-188">Completion</span></span>|<span data-ttu-id="87d03-189">2</span><span class="sxs-lookup"><span data-stu-id="87d03-189">2</span></span>|  
|<span data-ttu-id="87d03-190">Canceled</span><span class="sxs-lookup"><span data-stu-id="87d03-190">Canceled</span></span>|<span data-ttu-id="87d03-191">3</span><span class="sxs-lookup"><span data-stu-id="87d03-191">3</span></span>|  
  
##  <a name="foreach-loop-enumerators"></a><a name="Foreach"></a> <span data-ttu-id="87d03-192">Enumeradores de Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="87d03-192">Foreach Loop Enumerators</span></span>  
 <span data-ttu-id="87d03-193">O Loop Foreach inclui um conjunto de enumeradores com propriedades que podem ser definidas por expressões de propriedade.</span><span class="sxs-lookup"><span data-stu-id="87d03-193">The Foreach Loop includes a set of enumerators with properties that can be set by property expressions.</span></span>  
  
### <a name="foreach-ado-enumerator"></a><span data-ttu-id="87d03-194">Enumerador ADO Foreach</span><span class="sxs-lookup"><span data-stu-id="87d03-194">Foreach ADO Enumerator</span></span>  
 <span data-ttu-id="87d03-195">`Type`Propriedade-definido usando valores da `ADOEnumerationType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-195">`Type` property-Set by using values from the `ADOEnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-196">Nome amigável em ADOEnumerationType</span><span class="sxs-lookup"><span data-stu-id="87d03-196">Friendly name in ADOEnumerationType</span></span>|<span data-ttu-id="87d03-197">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-197">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="87d03-198">EnumerateTables</span><span class="sxs-lookup"><span data-stu-id="87d03-198">EnumerateTables</span></span>|<span data-ttu-id="87d03-199">0</span><span class="sxs-lookup"><span data-stu-id="87d03-199">0</span></span>|  
|<span data-ttu-id="87d03-200">EnumerateAllRows</span><span class="sxs-lookup"><span data-stu-id="87d03-200">EnumerateAllRows</span></span>|<span data-ttu-id="87d03-201">1</span><span class="sxs-lookup"><span data-stu-id="87d03-201">1</span></span>|  
|<span data-ttu-id="87d03-202">EnumerateRowsInFirstTable</span><span class="sxs-lookup"><span data-stu-id="87d03-202">EnumerateRowsInFirstTable</span></span>|<span data-ttu-id="87d03-203">2</span><span class="sxs-lookup"><span data-stu-id="87d03-203">2</span></span>|  
  
### <a name="foreach-nodelist-enumerator"></a><span data-ttu-id="87d03-204">Enumerador Nodelist Foreach</span><span class="sxs-lookup"><span data-stu-id="87d03-204">Foreach Nodelist Enumerator</span></span>  
 <span data-ttu-id="87d03-205">`SourceDocumentType`, `InnerXPathStringSourceType` e **OuterXPathStringSourceType** propriedades – definidas usando valores da `SourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-205">`SourceDocumentType`, `InnerXPathStringSourceType`, and **OuterXPathStringSourceType** properties-Set by using values from the `SourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-206">Nome amigável em SourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-206">Friendly name in SourceType</span></span>|<span data-ttu-id="87d03-207">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-207">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="87d03-208">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-208">FileConnection</span></span>|<span data-ttu-id="87d03-209">0</span><span class="sxs-lookup"><span data-stu-id="87d03-209">0</span></span>|  
|<span data-ttu-id="87d03-210">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-210">Variable</span></span>|<span data-ttu-id="87d03-211">1</span><span class="sxs-lookup"><span data-stu-id="87d03-211">1</span></span>|  
|<span data-ttu-id="87d03-212">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-212">DirectInput</span></span>|<span data-ttu-id="87d03-213">2</span><span class="sxs-lookup"><span data-stu-id="87d03-213">2</span></span>|  
  
 <span data-ttu-id="87d03-214">`EnumerationType`Propriedade-definido usando valores da `EnumerationType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-214">`EnumerationType` property-Set by using values from the `EnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-215">Nome amigável em EnumerationType</span><span class="sxs-lookup"><span data-stu-id="87d03-215">Friendly name in EnumerationType</span></span>|<span data-ttu-id="87d03-216">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-216">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-217">Navegador</span><span class="sxs-lookup"><span data-stu-id="87d03-217">Navigator</span></span>|<span data-ttu-id="87d03-218">0</span><span class="sxs-lookup"><span data-stu-id="87d03-218">0</span></span>|  
|<span data-ttu-id="87d03-219">Nó</span><span class="sxs-lookup"><span data-stu-id="87d03-219">Node</span></span>|<span data-ttu-id="87d03-220">1</span><span class="sxs-lookup"><span data-stu-id="87d03-220">1</span></span>|  
|<span data-ttu-id="87d03-221">NodeText</span><span class="sxs-lookup"><span data-stu-id="87d03-221">NodeText</span></span>|<span data-ttu-id="87d03-222">2</span><span class="sxs-lookup"><span data-stu-id="87d03-222">2</span></span>|  
|<span data-ttu-id="87d03-223">ElementCollection</span><span class="sxs-lookup"><span data-stu-id="87d03-223">ElementCollection</span></span>|<span data-ttu-id="87d03-224">3</span><span class="sxs-lookup"><span data-stu-id="87d03-224">3</span></span>|  
  
 <span data-ttu-id="87d03-225">`InnerElementType`Propriedade-definido usando valores da `InnerElementType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-225">`InnerElementType` property-Set by using values from the `InnerElementType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-226">Nome amigável em InnerElementType</span><span class="sxs-lookup"><span data-stu-id="87d03-226">Friendly name in InnerElementType</span></span>|<span data-ttu-id="87d03-227">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-227">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="87d03-228">Navegador</span><span class="sxs-lookup"><span data-stu-id="87d03-228">Navigator</span></span>|<span data-ttu-id="87d03-229">0</span><span class="sxs-lookup"><span data-stu-id="87d03-229">0</span></span>|  
|<span data-ttu-id="87d03-230">Nó</span><span class="sxs-lookup"><span data-stu-id="87d03-230">Node</span></span>|<span data-ttu-id="87d03-231">1</span><span class="sxs-lookup"><span data-stu-id="87d03-231">1</span></span>|  
|<span data-ttu-id="87d03-232">NodeText</span><span class="sxs-lookup"><span data-stu-id="87d03-232">NodeText</span></span>|<span data-ttu-id="87d03-233">2</span><span class="sxs-lookup"><span data-stu-id="87d03-233">2</span></span>|  
  
##  <a name="tasks"></a><a name="Tasks"></a> <span data-ttu-id="87d03-234">Tarefas</span><span class="sxs-lookup"><span data-stu-id="87d03-234">Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="87d03-235">inclui várias tarefas com propriedades que podem ser definidas por expressões de propriedade.</span><span class="sxs-lookup"><span data-stu-id="87d03-235">includes numerous tasks with properties that can be set by property expressions.</span></span>  
  
### <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="87d03-236">Tarefa Executar DDL do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="87d03-236">Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="87d03-237">`SourceType`Propriedade-definido usando valores da `DDLSourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-237">`SourceType` property-Set by using values from the `DDLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-238">Nome amigável em DDLSourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-238">Friendly name in DDLSourceType</span></span>|<span data-ttu-id="87d03-239">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-239">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="87d03-240">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-240">DirectInput</span></span>|<span data-ttu-id="87d03-241">0</span><span class="sxs-lookup"><span data-stu-id="87d03-241">0</span></span>|  
|<span data-ttu-id="87d03-242">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-242">FileConnection</span></span>|<span data-ttu-id="87d03-243">1</span><span class="sxs-lookup"><span data-stu-id="87d03-243">1</span></span>|  
|<span data-ttu-id="87d03-244">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-244">Variable</span></span>|<span data-ttu-id="87d03-245">2</span><span class="sxs-lookup"><span data-stu-id="87d03-245">2</span></span>|  
  
### <a name="bulk-insert-task"></a><span data-ttu-id="87d03-246">Tarefa Inserção em Massa</span><span class="sxs-lookup"><span data-stu-id="87d03-246">Bulk Insert Task</span></span>  
 <span data-ttu-id="87d03-247">`DataFileType`Propriedade-definido usando valores da `DTSBulkInsert_DataFileType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-247">`DataFileType` property-Set by using values from the `DTSBulkInsert_DataFileType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-248">Nome amigável em DTSBulkInsert_DataFileType</span><span class="sxs-lookup"><span data-stu-id="87d03-248">Friendly name in DTSBulkInsert_DataFileType</span></span>|<span data-ttu-id="87d03-249">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-249">Numeric value</span></span>|  
|--------------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-250">DTSBulkInsert_DataFileType_Char</span><span class="sxs-lookup"><span data-stu-id="87d03-250">DTSBulkInsert_DataFileType_Char</span></span>|<span data-ttu-id="87d03-251">0</span><span class="sxs-lookup"><span data-stu-id="87d03-251">0</span></span>|  
|<span data-ttu-id="87d03-252">DTSBulkInsert_DataFileType_Native</span><span class="sxs-lookup"><span data-stu-id="87d03-252">DTSBulkInsert_DataFileType_Native</span></span>|<span data-ttu-id="87d03-253">1</span><span class="sxs-lookup"><span data-stu-id="87d03-253">1</span></span>|  
|<span data-ttu-id="87d03-254">DTSBulkInsert_DataFileType_WideChar</span><span class="sxs-lookup"><span data-stu-id="87d03-254">DTSBulkInsert_DataFileType_WideChar</span></span>|<span data-ttu-id="87d03-255">2</span><span class="sxs-lookup"><span data-stu-id="87d03-255">2</span></span>|  
|<span data-ttu-id="87d03-256">DTSBulkInsert_DataFileType_WideNative</span><span class="sxs-lookup"><span data-stu-id="87d03-256">DTSBulkInsert_DataFileType_WideNative</span></span>|<span data-ttu-id="87d03-257">3</span><span class="sxs-lookup"><span data-stu-id="87d03-257">3</span></span>|  
  
### <a name="execute-sql-task"></a><span data-ttu-id="87d03-258">Tarefa Executar SQL</span><span class="sxs-lookup"><span data-stu-id="87d03-258">Execute SQL Task</span></span>  
 <span data-ttu-id="87d03-259">`ResultSetType`Propriedade-definido usando valores da `ResultSetType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-259">`ResultSetType` property-Set by using values from the `ResultSetType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-260">Nome amigável em ResultSetType</span><span class="sxs-lookup"><span data-stu-id="87d03-260">Friendly name in ResultSetType</span></span>|<span data-ttu-id="87d03-261">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-261">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="87d03-262">ResultSetType_None</span><span class="sxs-lookup"><span data-stu-id="87d03-262">ResultSetType_None</span></span>|<span data-ttu-id="87d03-263">1</span><span class="sxs-lookup"><span data-stu-id="87d03-263">1</span></span>|  
|<span data-ttu-id="87d03-264">ResultSetType_SingleRow</span><span class="sxs-lookup"><span data-stu-id="87d03-264">ResultSetType_SingleRow</span></span>|<span data-ttu-id="87d03-265">2</span><span class="sxs-lookup"><span data-stu-id="87d03-265">2</span></span>|  
|<span data-ttu-id="87d03-266">ResultSetType_Rowset</span><span class="sxs-lookup"><span data-stu-id="87d03-266">ResultSetType_Rowset</span></span>|<span data-ttu-id="87d03-267">3</span><span class="sxs-lookup"><span data-stu-id="87d03-267">3</span></span>|  
|<span data-ttu-id="87d03-268">ResultSetType_XML</span><span class="sxs-lookup"><span data-stu-id="87d03-268">ResultSetType_XML</span></span>|<span data-ttu-id="87d03-269">4</span><span class="sxs-lookup"><span data-stu-id="87d03-269">4</span></span>|  
  
 <span data-ttu-id="87d03-270">`SqlStatementSourceType`Propriedade-definido usando valores da `SqlStatementSourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-270">`SqlStatementSourceType` property-Set by using values from the `SqlStatementSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-271">Nome amigável em SqlStatementSourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-271">Friendly name in SqlStatementSourceType</span></span>|<span data-ttu-id="87d03-272">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-272">Numeric Value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-273">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-273">DirectInput</span></span>|<span data-ttu-id="87d03-274">1</span><span class="sxs-lookup"><span data-stu-id="87d03-274">1</span></span>|  
|<span data-ttu-id="87d03-275">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-275">FileConnection</span></span>|<span data-ttu-id="87d03-276">2</span><span class="sxs-lookup"><span data-stu-id="87d03-276">2</span></span>|  
|<span data-ttu-id="87d03-277">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-277">Variable</span></span>|<span data-ttu-id="87d03-278">3</span><span class="sxs-lookup"><span data-stu-id="87d03-278">3</span></span>|  
  
### <a name="file-system-task"></a><span data-ttu-id="87d03-279">Tarefa Sistema de Arquivos</span><span class="sxs-lookup"><span data-stu-id="87d03-279">File System Task</span></span>  
 <span data-ttu-id="87d03-280">`Operation`Propriedade-definido usando valores da `DTSFileSystemOperation` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-280">`Operation` property-Set by using values from the `DTSFileSystemOperation` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-281">Nome amigável em DTSFileSystemOperation</span><span class="sxs-lookup"><span data-stu-id="87d03-281">Friendly name in DTSFileSystemOperation</span></span>|<span data-ttu-id="87d03-282">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-282">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-283">CopyFile</span><span class="sxs-lookup"><span data-stu-id="87d03-283">CopyFile</span></span>|<span data-ttu-id="87d03-284">0</span><span class="sxs-lookup"><span data-stu-id="87d03-284">0</span></span>|  
|<span data-ttu-id="87d03-285">MoveFile</span><span class="sxs-lookup"><span data-stu-id="87d03-285">MoveFile</span></span>|<span data-ttu-id="87d03-286">1</span><span class="sxs-lookup"><span data-stu-id="87d03-286">1</span></span>|  
|<span data-ttu-id="87d03-287">DeleteFile</span><span class="sxs-lookup"><span data-stu-id="87d03-287">DeleteFile</span></span>|<span data-ttu-id="87d03-288">2</span><span class="sxs-lookup"><span data-stu-id="87d03-288">2</span></span>|  
|<span data-ttu-id="87d03-289">RenameFile</span><span class="sxs-lookup"><span data-stu-id="87d03-289">RenameFile</span></span>|<span data-ttu-id="87d03-290">3</span><span class="sxs-lookup"><span data-stu-id="87d03-290">3</span></span>|  
|<span data-ttu-id="87d03-291">SetAttributes</span><span class="sxs-lookup"><span data-stu-id="87d03-291">SetAttributes</span></span>|<span data-ttu-id="87d03-292">4</span><span class="sxs-lookup"><span data-stu-id="87d03-292">4</span></span>|  
|<span data-ttu-id="87d03-293">CreateDirectory</span><span class="sxs-lookup"><span data-stu-id="87d03-293">CreateDirectory</span></span>|<span data-ttu-id="87d03-294">5</span><span class="sxs-lookup"><span data-stu-id="87d03-294">5</span></span>|  
|<span data-ttu-id="87d03-295">CopyDirectory</span><span class="sxs-lookup"><span data-stu-id="87d03-295">CopyDirectory</span></span>|<span data-ttu-id="87d03-296">6</span><span class="sxs-lookup"><span data-stu-id="87d03-296">6</span></span>|  
|<span data-ttu-id="87d03-297">MoveDirectory</span><span class="sxs-lookup"><span data-stu-id="87d03-297">MoveDirectory</span></span>|<span data-ttu-id="87d03-298">7</span><span class="sxs-lookup"><span data-stu-id="87d03-298">7</span></span>|  
|<span data-ttu-id="87d03-299">DeleteDirectory</span><span class="sxs-lookup"><span data-stu-id="87d03-299">DeleteDirectory</span></span>|<span data-ttu-id="87d03-300">8</span><span class="sxs-lookup"><span data-stu-id="87d03-300">8</span></span>|  
|<span data-ttu-id="87d03-301">DeleteDirectoryContent</span><span class="sxs-lookup"><span data-stu-id="87d03-301">DeleteDirectoryContent</span></span>|<span data-ttu-id="87d03-302">9</span><span class="sxs-lookup"><span data-stu-id="87d03-302">9</span></span>|  
  
 <span data-ttu-id="87d03-303">`Attributes`Propriedade-definido usando valores da `DTSFileSystemAttributes` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-303">`Attributes` property-Set by using values from the `DTSFileSystemAttributes` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-304">Nome amigável em DTSFileSystemAttributes</span><span class="sxs-lookup"><span data-stu-id="87d03-304">Friendly name in DTSFileSystemAttributes</span></span>|<span data-ttu-id="87d03-305">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-305">Numeric value</span></span>|  
|----------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-306">Normal</span><span class="sxs-lookup"><span data-stu-id="87d03-306">Normal</span></span>|<span data-ttu-id="87d03-307">0</span><span class="sxs-lookup"><span data-stu-id="87d03-307">0</span></span>|  
|<span data-ttu-id="87d03-308">Archive</span><span class="sxs-lookup"><span data-stu-id="87d03-308">Archive</span></span>|<span data-ttu-id="87d03-309">1</span><span class="sxs-lookup"><span data-stu-id="87d03-309">1</span></span>|  
|<span data-ttu-id="87d03-310">Hidden</span><span class="sxs-lookup"><span data-stu-id="87d03-310">Hidden</span></span>|<span data-ttu-id="87d03-311">2</span><span class="sxs-lookup"><span data-stu-id="87d03-311">2</span></span>|  
|<span data-ttu-id="87d03-312">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="87d03-312">ReadOnly</span></span>|<span data-ttu-id="87d03-313">4</span><span class="sxs-lookup"><span data-stu-id="87d03-313">4</span></span>|  
|<span data-ttu-id="87d03-314">Sistema</span><span class="sxs-lookup"><span data-stu-id="87d03-314">System</span></span>|<span data-ttu-id="87d03-315">8</span><span class="sxs-lookup"><span data-stu-id="87d03-315">8</span></span>|  
  
### <a name="ftp-task"></a><span data-ttu-id="87d03-316">Tarefa FTP</span><span class="sxs-lookup"><span data-stu-id="87d03-316">FTP Task</span></span>  
 <span data-ttu-id="87d03-317">`Operation`Propriedade-definido usando valores da `DTSFTPOp` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-317">`Operation` property-Set by using values from the `DTSFTPOp` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-318">Nome amigável em DTSFTPOp</span><span class="sxs-lookup"><span data-stu-id="87d03-318">Friendly name in DTSFTPOp</span></span>|<span data-ttu-id="87d03-319">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-319">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="87d03-320">Enviar</span><span class="sxs-lookup"><span data-stu-id="87d03-320">Send</span></span>|<span data-ttu-id="87d03-321">0</span><span class="sxs-lookup"><span data-stu-id="87d03-321">0</span></span>|  
|<span data-ttu-id="87d03-322">Receber</span><span class="sxs-lookup"><span data-stu-id="87d03-322">Receive</span></span>|<span data-ttu-id="87d03-323">1</span><span class="sxs-lookup"><span data-stu-id="87d03-323">1</span></span>|  
|<span data-ttu-id="87d03-324">DeleteLocal</span><span class="sxs-lookup"><span data-stu-id="87d03-324">DeleteLocal</span></span>|<span data-ttu-id="87d03-325">2</span><span class="sxs-lookup"><span data-stu-id="87d03-325">2</span></span>|  
|<span data-ttu-id="87d03-326">DeleteRemote</span><span class="sxs-lookup"><span data-stu-id="87d03-326">DeleteRemote</span></span>|<span data-ttu-id="87d03-327">3</span><span class="sxs-lookup"><span data-stu-id="87d03-327">3</span></span>|  
|<span data-ttu-id="87d03-328">MakeDirLocal</span><span class="sxs-lookup"><span data-stu-id="87d03-328">MakeDirLocal</span></span>|<span data-ttu-id="87d03-329">4</span><span class="sxs-lookup"><span data-stu-id="87d03-329">4</span></span>|  
|<span data-ttu-id="87d03-330">MakeDirRemote</span><span class="sxs-lookup"><span data-stu-id="87d03-330">MakeDirRemote</span></span>|<span data-ttu-id="87d03-331">5</span><span class="sxs-lookup"><span data-stu-id="87d03-331">5</span></span>|  
|<span data-ttu-id="87d03-332">RemoveDirLocal</span><span class="sxs-lookup"><span data-stu-id="87d03-332">RemoveDirLocal</span></span>|<span data-ttu-id="87d03-333">6</span><span class="sxs-lookup"><span data-stu-id="87d03-333">6</span></span>|  
|<span data-ttu-id="87d03-334">RemoveDirRemote</span><span class="sxs-lookup"><span data-stu-id="87d03-334">RemoveDirRemote</span></span>|<span data-ttu-id="87d03-335">7</span><span class="sxs-lookup"><span data-stu-id="87d03-335">7</span></span>|  
  
### <a name="message-queue-task"></a><span data-ttu-id="87d03-336">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="87d03-336">Message Queue Task</span></span>  
 <span data-ttu-id="87d03-337">`MessageType`Propriedade-definido usando valores da `MQMessageType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-337">`MessageType` property-Set by using values from the `MQMessageType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-338">Nome amigável em MQMessageType</span><span class="sxs-lookup"><span data-stu-id="87d03-338">Friendly name in MQMessageType</span></span>|<span data-ttu-id="87d03-339">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-339">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="87d03-340">DTSMQMessageType_String</span><span class="sxs-lookup"><span data-stu-id="87d03-340">DTSMQMessageType_String</span></span>|<span data-ttu-id="87d03-341">0</span><span class="sxs-lookup"><span data-stu-id="87d03-341">0</span></span>|  
|<span data-ttu-id="87d03-342">DTSMQMessageType_DataFile</span><span class="sxs-lookup"><span data-stu-id="87d03-342">DTSMQMessageType_DataFile</span></span>|<span data-ttu-id="87d03-343">1</span><span class="sxs-lookup"><span data-stu-id="87d03-343">1</span></span>|  
|<span data-ttu-id="87d03-344">DTSMQMessageType_Variables</span><span class="sxs-lookup"><span data-stu-id="87d03-344">DTSMQMessageType_Variables</span></span>|<span data-ttu-id="87d03-345">2</span><span class="sxs-lookup"><span data-stu-id="87d03-345">2</span></span>|  
|<span data-ttu-id="87d03-346">DTSMQMessagType_StringMessageToVariable</span><span class="sxs-lookup"><span data-stu-id="87d03-346">DTSMQMessagType_StringMessageToVariable</span></span>|<span data-ttu-id="87d03-347">3</span><span class="sxs-lookup"><span data-stu-id="87d03-347">3</span></span>|  
  
 <span data-ttu-id="87d03-348">`StringCompareType`Propriedade-definido usando valores da `MQStringMessageCompare` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-348">`StringCompareType` property-Set by using values from the `MQStringMessageCompare` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-349">Nome amigável em MQStringMessageCompare</span><span class="sxs-lookup"><span data-stu-id="87d03-349">Friendly name in MQStringMessageCompare</span></span>|<span data-ttu-id="87d03-350">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-350">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-351">DTSMQStringMessageCompare_None</span><span class="sxs-lookup"><span data-stu-id="87d03-351">DTSMQStringMessageCompare_None</span></span>|<span data-ttu-id="87d03-352">0</span><span class="sxs-lookup"><span data-stu-id="87d03-352">0</span></span>|  
|<span data-ttu-id="87d03-353">DTSMQStringMessageCompare_Exact</span><span class="sxs-lookup"><span data-stu-id="87d03-353">DTSMQStringMessageCompare_Exact</span></span>|<span data-ttu-id="87d03-354">1</span><span class="sxs-lookup"><span data-stu-id="87d03-354">1</span></span>|  
|<span data-ttu-id="87d03-355">DTSMQStringMessageCompare_IgnoreCase</span><span class="sxs-lookup"><span data-stu-id="87d03-355">DTSMQStringMessageCompare_IgnoreCase</span></span>|<span data-ttu-id="87d03-356">2</span><span class="sxs-lookup"><span data-stu-id="87d03-356">2</span></span>|  
|<span data-ttu-id="87d03-357">DTSMQStringMessageCompare_Contains</span><span class="sxs-lookup"><span data-stu-id="87d03-357">DTSMQStringMessageCompare_Contains</span></span>|<span data-ttu-id="87d03-358">3</span><span class="sxs-lookup"><span data-stu-id="87d03-358">3</span></span>|  
  
 <span data-ttu-id="87d03-359">`TaskType`Propriedade-definido usando valores da `MQType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-359">`TaskType` property-Set by using values from the `MQType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-360">Nome amigável em MQType</span><span class="sxs-lookup"><span data-stu-id="87d03-360">Friendly name in MQType</span></span>|<span data-ttu-id="87d03-361">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-361">Numeric value</span></span>|  
|-----------------------------|-------------------|  
|<span data-ttu-id="87d03-362">DTSMQType_Sender</span><span class="sxs-lookup"><span data-stu-id="87d03-362">DTSMQType_Sender</span></span>|<span data-ttu-id="87d03-363">0</span><span class="sxs-lookup"><span data-stu-id="87d03-363">0</span></span>|  
|<span data-ttu-id="87d03-364">DTSMQType_Receiver</span><span class="sxs-lookup"><span data-stu-id="87d03-364">DTSMQType_Receiver</span></span>|<span data-ttu-id="87d03-365">1</span><span class="sxs-lookup"><span data-stu-id="87d03-365">1</span></span>|  
  
### <a name="send-mail-task"></a><span data-ttu-id="87d03-366">Tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="87d03-366">Send Mail Task</span></span>  
 <span data-ttu-id="87d03-367">`MessageSourceType`Propriedade-definido usando valores da `SendMailMessageSourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-367">`MessageSourceType` property-Set by using values from the `SendMailMessageSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-368">Nome amigável em SendMailMessageSourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-368">Friendly Name in SendMailMessageSourceType</span></span>|<span data-ttu-id="87d03-369">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-369">Numeric Value</span></span>|  
|------------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-370">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-370">DirectInput</span></span>|<span data-ttu-id="87d03-371">0</span><span class="sxs-lookup"><span data-stu-id="87d03-371">0</span></span>|  
|<span data-ttu-id="87d03-372">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-372">FileConnection</span></span>|<span data-ttu-id="87d03-373">1</span><span class="sxs-lookup"><span data-stu-id="87d03-373">1</span></span>|  
|<span data-ttu-id="87d03-374">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-374">Variable</span></span>|<span data-ttu-id="87d03-375">2</span><span class="sxs-lookup"><span data-stu-id="87d03-375">2</span></span>|  
  
 <span data-ttu-id="87d03-376">`Priority`Propriedade-definido usando valores da `MailPriority` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-376">`Priority` property-Set by using values from the `MailPriority` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-377">Nome amigável em MailPriority</span><span class="sxs-lookup"><span data-stu-id="87d03-377">Friendly Name in MailPriority</span></span>|<span data-ttu-id="87d03-378">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-378">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="87d03-379">Alta</span><span class="sxs-lookup"><span data-stu-id="87d03-379">High</span></span>|<span data-ttu-id="87d03-380">1</span><span class="sxs-lookup"><span data-stu-id="87d03-380">1</span></span>|  
|<span data-ttu-id="87d03-381">Normal</span><span class="sxs-lookup"><span data-stu-id="87d03-381">Normal</span></span>|<span data-ttu-id="87d03-382">3</span><span class="sxs-lookup"><span data-stu-id="87d03-382">3</span></span>|  
|<span data-ttu-id="87d03-383">Baixo</span><span class="sxs-lookup"><span data-stu-id="87d03-383">Low</span></span>|<span data-ttu-id="87d03-384">5</span><span class="sxs-lookup"><span data-stu-id="87d03-384">5</span></span>|  
  
### <a name="transfer-database-task"></a><span data-ttu-id="87d03-385">Tarefa Transferir Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="87d03-385">Transfer Database Task</span></span>  
 <span data-ttu-id="87d03-386">`Action`Propriedade-definido usando valores da `TransferAction` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-386">`Action` property-Set by using values from the `TransferAction` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-387">Nome amigável em TransferAction</span><span class="sxs-lookup"><span data-stu-id="87d03-387">Friendly name in TransferAction</span></span>|<span data-ttu-id="87d03-388">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-388">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-389">Cópia</span><span class="sxs-lookup"><span data-stu-id="87d03-389">Copy</span></span>|<span data-ttu-id="87d03-390">0</span><span class="sxs-lookup"><span data-stu-id="87d03-390">0</span></span>|  
|<span data-ttu-id="87d03-391">Mover</span><span class="sxs-lookup"><span data-stu-id="87d03-391">Move</span></span>|<span data-ttu-id="87d03-392">1</span><span class="sxs-lookup"><span data-stu-id="87d03-392">1</span></span>|  
  
 <span data-ttu-id="87d03-393">`Method`Propriedade-definido usando valores da `TransferMethod` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-393">`Method` property-Set by using values from the `TransferMethod` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-394">Nome amigável em TransferMethod</span><span class="sxs-lookup"><span data-stu-id="87d03-394">Friendly name in TransferMethod</span></span>|<span data-ttu-id="87d03-395">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-395">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-396">DatabaseOffline</span><span class="sxs-lookup"><span data-stu-id="87d03-396">DatabaseOffline</span></span>|<span data-ttu-id="87d03-397">0</span><span class="sxs-lookup"><span data-stu-id="87d03-397">0</span></span>|  
|<span data-ttu-id="87d03-398">DatabaseOnline</span><span class="sxs-lookup"><span data-stu-id="87d03-398">DatabaseOnline</span></span>|<span data-ttu-id="87d03-399">1</span><span class="sxs-lookup"><span data-stu-id="87d03-399">1</span></span>|  
  
### <a name="transfer-error-messages-task"></a><span data-ttu-id="87d03-400">Tarefa Transferir Mensagens de Erro</span><span class="sxs-lookup"><span data-stu-id="87d03-400">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="87d03-401">`IfObjectExists`Propriedade-definido usando valores da `IfObjectExists` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-401">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-402">Nome amigável em IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="87d03-402">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="87d03-403">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-403">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-404">FailTask</span><span class="sxs-lookup"><span data-stu-id="87d03-404">FailTask</span></span>|<span data-ttu-id="87d03-405">0</span><span class="sxs-lookup"><span data-stu-id="87d03-405">0</span></span>|  
|<span data-ttu-id="87d03-406">Overwrite</span><span class="sxs-lookup"><span data-stu-id="87d03-406">Overwrite</span></span>|<span data-ttu-id="87d03-407">1</span><span class="sxs-lookup"><span data-stu-id="87d03-407">1</span></span>|  
|<span data-ttu-id="87d03-408">Skip</span><span class="sxs-lookup"><span data-stu-id="87d03-408">Skip</span></span>|<span data-ttu-id="87d03-409">2</span><span class="sxs-lookup"><span data-stu-id="87d03-409">2</span></span>|  
  
### <a name="transfer-jobs-task"></a><span data-ttu-id="87d03-410">Tarefa Transferir Trabalhos</span><span class="sxs-lookup"><span data-stu-id="87d03-410">Transfer Jobs Task</span></span>  
 <span data-ttu-id="87d03-411">`IfObjectExists`Propriedade-definido usando valores da `IfObjectExists` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-411">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-412">Nome amigável em IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="87d03-412">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="87d03-413">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-413">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-414">FailTask</span><span class="sxs-lookup"><span data-stu-id="87d03-414">FailTask</span></span>|<span data-ttu-id="87d03-415">0</span><span class="sxs-lookup"><span data-stu-id="87d03-415">0</span></span>|  
|<span data-ttu-id="87d03-416">Overwrite</span><span class="sxs-lookup"><span data-stu-id="87d03-416">Overwrite</span></span>|<span data-ttu-id="87d03-417">1</span><span class="sxs-lookup"><span data-stu-id="87d03-417">1</span></span>|  
|<span data-ttu-id="87d03-418">Skip</span><span class="sxs-lookup"><span data-stu-id="87d03-418">Skip</span></span>|<span data-ttu-id="87d03-419">2</span><span class="sxs-lookup"><span data-stu-id="87d03-419">2</span></span>|  
  
### <a name="transfer-logins-task"></a><span data-ttu-id="87d03-420">Tarefa Transferir Logons</span><span class="sxs-lookup"><span data-stu-id="87d03-420">Transfer Logins Task</span></span>  
 <span data-ttu-id="87d03-421">`IfObjectExists`Propriedade-definido usando valores da `IfObjectExists` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-421">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-422">Nome amigável em IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="87d03-422">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="87d03-423">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-423">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-424">FailTask</span><span class="sxs-lookup"><span data-stu-id="87d03-424">FailTask</span></span>|<span data-ttu-id="87d03-425">0</span><span class="sxs-lookup"><span data-stu-id="87d03-425">0</span></span>|  
|<span data-ttu-id="87d03-426">Overwrite</span><span class="sxs-lookup"><span data-stu-id="87d03-426">Overwrite</span></span>|<span data-ttu-id="87d03-427">1</span><span class="sxs-lookup"><span data-stu-id="87d03-427">1</span></span>|  
|<span data-ttu-id="87d03-428">Skip</span><span class="sxs-lookup"><span data-stu-id="87d03-428">Skip</span></span>|<span data-ttu-id="87d03-429">2</span><span class="sxs-lookup"><span data-stu-id="87d03-429">2</span></span>|  
  
 <span data-ttu-id="87d03-430">`LoginsToTransfer`Propriedade-definido usando valores da `LoginsToTransfer` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-430">`LoginsToTransfer` property-Set by using values from the `LoginsToTransfer` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-431">Nome amigável em LoginsToTransfer</span><span class="sxs-lookup"><span data-stu-id="87d03-431">Friendly name in LoginsToTransfer</span></span>|<span data-ttu-id="87d03-432">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-432">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="87d03-433">AllLogins</span><span class="sxs-lookup"><span data-stu-id="87d03-433">AllLogins</span></span>|<span data-ttu-id="87d03-434">0</span><span class="sxs-lookup"><span data-stu-id="87d03-434">0</span></span>|  
|<span data-ttu-id="87d03-435">SelectedLogins</span><span class="sxs-lookup"><span data-stu-id="87d03-435">SelectedLogins</span></span>|<span data-ttu-id="87d03-436">1</span><span class="sxs-lookup"><span data-stu-id="87d03-436">1</span></span>|  
|<span data-ttu-id="87d03-437">AllLoginsFromSelectedDatabases</span><span class="sxs-lookup"><span data-stu-id="87d03-437">AllLoginsFromSelectedDatabases</span></span>|<span data-ttu-id="87d03-438">2</span><span class="sxs-lookup"><span data-stu-id="87d03-438">2</span></span>|  
  
### <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="87d03-439">Tarefa Transferir Procedimentos Armazenados Mestres</span><span class="sxs-lookup"><span data-stu-id="87d03-439">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="87d03-440">`IfObjectExists`Propriedade-definido usando valores da `IfObjectExists` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-440">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-441">Nome amigável em IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="87d03-441">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="87d03-442">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-442">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-443">FailTask</span><span class="sxs-lookup"><span data-stu-id="87d03-443">FailTask</span></span>|<span data-ttu-id="87d03-444">0</span><span class="sxs-lookup"><span data-stu-id="87d03-444">0</span></span>|  
|<span data-ttu-id="87d03-445">Overwrite</span><span class="sxs-lookup"><span data-stu-id="87d03-445">Overwrite</span></span>|<span data-ttu-id="87d03-446">1</span><span class="sxs-lookup"><span data-stu-id="87d03-446">1</span></span>|  
|<span data-ttu-id="87d03-447">Skip</span><span class="sxs-lookup"><span data-stu-id="87d03-447">Skip</span></span>|<span data-ttu-id="87d03-448">2</span><span class="sxs-lookup"><span data-stu-id="87d03-448">2</span></span>|  
  
### <a name="transfer-sql-server-objects-task"></a><span data-ttu-id="87d03-449">Tarefa Transferir Objetos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="87d03-449">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="87d03-450">`ExistingData`Propriedade-definido usando valores da `ExistingData` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-450">`ExistingData` property-Set by using values from the `ExistingData` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-451">Nome amigável em ExistingData</span><span class="sxs-lookup"><span data-stu-id="87d03-451">Friendly name in ExistingData</span></span>|<span data-ttu-id="87d03-452">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-452">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="87d03-453">Substitua</span><span class="sxs-lookup"><span data-stu-id="87d03-453">Replace</span></span>|<span data-ttu-id="87d03-454">0</span><span class="sxs-lookup"><span data-stu-id="87d03-454">0</span></span>|  
|<span data-ttu-id="87d03-455">Acrescentar</span><span class="sxs-lookup"><span data-stu-id="87d03-455">Append</span></span>|<span data-ttu-id="87d03-456">1</span><span class="sxs-lookup"><span data-stu-id="87d03-456">1</span></span>|  
  
### <a name="web-service-task"></a><span data-ttu-id="87d03-457">Tarefa Serviços Web</span><span class="sxs-lookup"><span data-stu-id="87d03-457">Web Service Task</span></span>  
 <span data-ttu-id="87d03-458">`OutputType`Propriedade-definido usando valores da `DTSOutputType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-458">`OutputType` property-Set by using values from the `DTSOutputType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-459">Nome amigável em DTSOutputType</span><span class="sxs-lookup"><span data-stu-id="87d03-459">Friendly name in DTSOutputType</span></span>|<span data-ttu-id="87d03-460">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-460">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="87d03-461">Arquivo</span><span class="sxs-lookup"><span data-stu-id="87d03-461">File</span></span>|<span data-ttu-id="87d03-462">0</span><span class="sxs-lookup"><span data-stu-id="87d03-462">0</span></span>|  
|<span data-ttu-id="87d03-463">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-463">Variable</span></span>|<span data-ttu-id="87d03-464">1</span><span class="sxs-lookup"><span data-stu-id="87d03-464">1</span></span>|  
  
### <a name="wmi-data-reader-task"></a><span data-ttu-id="87d03-465">Tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="87d03-465">WMI Data Reader Task</span></span>  
 <span data-ttu-id="87d03-466">`OverwriteDestination`Propriedade-definido usando valores da `OverwriteDestination` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-466">`OverwriteDestination` property-Set by using values from the `OverwriteDestination` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-467">Nome amigável em OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="87d03-467">Friendly name in OverwriteDestination</span></span>|<span data-ttu-id="87d03-468">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-468">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-469">OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="87d03-469">OverwriteDestination</span></span>|<span data-ttu-id="87d03-470">0</span><span class="sxs-lookup"><span data-stu-id="87d03-470">0</span></span>|  
|<span data-ttu-id="87d03-471">AppendToDestination</span><span class="sxs-lookup"><span data-stu-id="87d03-471">AppendToDestination</span></span>|<span data-ttu-id="87d03-472">1</span><span class="sxs-lookup"><span data-stu-id="87d03-472">1</span></span>|  
|<span data-ttu-id="87d03-473">KeepOriginal</span><span class="sxs-lookup"><span data-stu-id="87d03-473">KeepOriginal</span></span>|<span data-ttu-id="87d03-474">2</span><span class="sxs-lookup"><span data-stu-id="87d03-474">2</span></span>|  
  
 <span data-ttu-id="87d03-475">`OutputType`Propriedade-definido usando valores da `OutputType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-475">`OutputType` property-Set by using values from the `OutputType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-476">Nome amigável em OutputType</span><span class="sxs-lookup"><span data-stu-id="87d03-476">Friendly name in OutputType</span></span>|<span data-ttu-id="87d03-477">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-477">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="87d03-478">DataTable</span><span class="sxs-lookup"><span data-stu-id="87d03-478">DataTable</span></span>|<span data-ttu-id="87d03-479">0</span><span class="sxs-lookup"><span data-stu-id="87d03-479">0</span></span>|  
|<span data-ttu-id="87d03-480">PropertyValue</span><span class="sxs-lookup"><span data-stu-id="87d03-480">PropertyValue</span></span>|<span data-ttu-id="87d03-481">1</span><span class="sxs-lookup"><span data-stu-id="87d03-481">1</span></span>|  
|<span data-ttu-id="87d03-482">PropertyNameAndValue</span><span class="sxs-lookup"><span data-stu-id="87d03-482">PropertyNameAndValue</span></span>|<span data-ttu-id="87d03-483">2</span><span class="sxs-lookup"><span data-stu-id="87d03-483">2</span></span>|  
  
 <span data-ttu-id="87d03-484">`DestinationType`Propriedade-definido usando valores da `DestinationType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-484">`DestinationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-485">Nome amigável em DestinationType</span><span class="sxs-lookup"><span data-stu-id="87d03-485">Friendly name in DestinationType</span></span>|<span data-ttu-id="87d03-486">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-486">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-487">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-487">FileConnection</span></span>|<span data-ttu-id="87d03-488">0</span><span class="sxs-lookup"><span data-stu-id="87d03-488">0</span></span>|  
|<span data-ttu-id="87d03-489">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-489">Variable</span></span>|<span data-ttu-id="87d03-490">1</span><span class="sxs-lookup"><span data-stu-id="87d03-490">1</span></span>|  
  
 <span data-ttu-id="87d03-491">`WqlQuerySourceType`Propriedade-definido usando valores da `QuerySourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-491">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-492">Nome amigável em QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-492">Friendly Name in QuerySourceType</span></span>|<span data-ttu-id="87d03-493">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-493">Numeric Value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-494">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-494">FileConnection</span></span>|<span data-ttu-id="87d03-495">0</span><span class="sxs-lookup"><span data-stu-id="87d03-495">0</span></span>|  
|<span data-ttu-id="87d03-496">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-496">DirectInput</span></span>|<span data-ttu-id="87d03-497">1</span><span class="sxs-lookup"><span data-stu-id="87d03-497">1</span></span>|  
|<span data-ttu-id="87d03-498">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-498">Variable</span></span>|<span data-ttu-id="87d03-499">2</span><span class="sxs-lookup"><span data-stu-id="87d03-499">2</span></span>|  
  
 <span data-ttu-id="87d03-500">Propriedade do Inspetor de eventos `ActionAtEvent` do WMI – definida usando valores da `ActionAtEvent` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-500">WMI Event Watcher `ActionAtEvent` property-Set by using values from the `ActionAtEvent` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-501">Nome amigável em ActionAtEvent</span><span class="sxs-lookup"><span data-stu-id="87d03-501">Friendly Name in ActionAtEvent</span></span>|<span data-ttu-id="87d03-502">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-502">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="87d03-503">LogTheEventAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="87d03-503">LogTheEventAndFireDTSEvent</span></span>|<span data-ttu-id="87d03-504">0</span><span class="sxs-lookup"><span data-stu-id="87d03-504">0</span></span>|  
|<span data-ttu-id="87d03-505">LogTheEvent</span><span class="sxs-lookup"><span data-stu-id="87d03-505">LogTheEvent</span></span>|<span data-ttu-id="87d03-506">1</span><span class="sxs-lookup"><span data-stu-id="87d03-506">1</span></span>|  
  
 <span data-ttu-id="87d03-507">`ActionAtTimeout`Propriedade-definido usando valores da `ActionAtTimeout` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-507">`ActionAtTimeout` property-Set by using values from the `ActionAtTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-508">Nome amigável em ActionAtTimeout</span><span class="sxs-lookup"><span data-stu-id="87d03-508">Friendly name in ActionAtTimeout</span></span>|<span data-ttu-id="87d03-509">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-509">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-510">LogTimeoutAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="87d03-510">LogTimeoutAndFireDTSEvent</span></span>|<span data-ttu-id="87d03-511">0</span><span class="sxs-lookup"><span data-stu-id="87d03-511">0</span></span>|  
|<span data-ttu-id="87d03-512">LogTimeout</span><span class="sxs-lookup"><span data-stu-id="87d03-512">LogTimeout</span></span>|<span data-ttu-id="87d03-513">1</span><span class="sxs-lookup"><span data-stu-id="87d03-513">1</span></span>|  
  
 <span data-ttu-id="87d03-514">`AfterEvent`Propriedade-definido usando valores da `AfterEvent` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-514">`AfterEvent` property-Set by using values from the `AfterEvent` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-515">Nome amigável em AfterEvent</span><span class="sxs-lookup"><span data-stu-id="87d03-515">Friendly name in AfterEvent</span></span>|<span data-ttu-id="87d03-516">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-516">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="87d03-517">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="87d03-517">ReturnWithSuccess</span></span>|<span data-ttu-id="87d03-518">0</span><span class="sxs-lookup"><span data-stu-id="87d03-518">0</span></span>|  
|<span data-ttu-id="87d03-519">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="87d03-519">ReturnWithFailure</span></span>|<span data-ttu-id="87d03-520">1</span><span class="sxs-lookup"><span data-stu-id="87d03-520">1</span></span>|  
|<span data-ttu-id="87d03-521">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="87d03-521">WatchfortheEventAgain</span></span>|<span data-ttu-id="87d03-522">2</span><span class="sxs-lookup"><span data-stu-id="87d03-522">2</span></span>|  
  
 <span data-ttu-id="87d03-523">`AfterTimeout`Propriedade-definido usando valores da `AfterTimeout` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-523">`AfterTimeout` property-Set by using values from the `AfterTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-524">Nome amigável em AfterTimeout</span><span class="sxs-lookup"><span data-stu-id="87d03-524">Friendly name in AfterTimeout</span></span>|<span data-ttu-id="87d03-525">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-525">Numeric value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="87d03-526">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="87d03-526">ReturnWithSuccess</span></span>|<span data-ttu-id="87d03-527">0</span><span class="sxs-lookup"><span data-stu-id="87d03-527">0</span></span>|  
|<span data-ttu-id="87d03-528">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="87d03-528">ReturnWithFailure</span></span>|<span data-ttu-id="87d03-529">1</span><span class="sxs-lookup"><span data-stu-id="87d03-529">1</span></span>|  
|<span data-ttu-id="87d03-530">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="87d03-530">WatchfortheEventAgain</span></span>|<span data-ttu-id="87d03-531">2</span><span class="sxs-lookup"><span data-stu-id="87d03-531">2</span></span>|  
  
 <span data-ttu-id="87d03-532">`WqlQuerySourceType`Propriedade-definido usando valores da `QuerySourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-532">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-533">Nome amigável em QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-533">Friendly name in QuerySourceType</span></span>|<span data-ttu-id="87d03-534">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-534">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-535">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-535">FileConnection</span></span>|<span data-ttu-id="87d03-536">0</span><span class="sxs-lookup"><span data-stu-id="87d03-536">0</span></span>|  
|<span data-ttu-id="87d03-537">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-537">DirectInput</span></span>|<span data-ttu-id="87d03-538">1</span><span class="sxs-lookup"><span data-stu-id="87d03-538">1</span></span>|  
|<span data-ttu-id="87d03-539">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-539">Variable</span></span>|<span data-ttu-id="87d03-540">2</span><span class="sxs-lookup"><span data-stu-id="87d03-540">2</span></span>|  
  
### <a name="xml-task"></a><span data-ttu-id="87d03-541">XML Task</span><span class="sxs-lookup"><span data-stu-id="87d03-541">XML Task</span></span>  
 <span data-ttu-id="87d03-542">`OperationType`Propriedade-definido usando valores da `DTSXMLOperation` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-542">`OperationType` property-Set by using values from the `DTSXMLOperation` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-543">Nome amigável em DTSXMLOperation</span><span class="sxs-lookup"><span data-stu-id="87d03-543">Friendly name in DTSXMLOperation</span></span>|<span data-ttu-id="87d03-544">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-544">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-545">Validar</span><span class="sxs-lookup"><span data-stu-id="87d03-545">Validate</span></span>|<span data-ttu-id="87d03-546">0</span><span class="sxs-lookup"><span data-stu-id="87d03-546">0</span></span>|  
|<span data-ttu-id="87d03-547">XSLT</span><span class="sxs-lookup"><span data-stu-id="87d03-547">XSLT</span></span>|<span data-ttu-id="87d03-548">1</span><span class="sxs-lookup"><span data-stu-id="87d03-548">1</span></span>|  
|<span data-ttu-id="87d03-549">XPATH</span><span class="sxs-lookup"><span data-stu-id="87d03-549">XPATH</span></span>|<span data-ttu-id="87d03-550">2</span><span class="sxs-lookup"><span data-stu-id="87d03-550">2</span></span>|  
|<span data-ttu-id="87d03-551">Mesclar</span><span class="sxs-lookup"><span data-stu-id="87d03-551">Merge</span></span>|<span data-ttu-id="87d03-552">3</span><span class="sxs-lookup"><span data-stu-id="87d03-552">3</span></span>|  
|<span data-ttu-id="87d03-553">Diff</span><span class="sxs-lookup"><span data-stu-id="87d03-553">Diff</span></span>|<span data-ttu-id="87d03-554">4</span><span class="sxs-lookup"><span data-stu-id="87d03-554">4</span></span>|  
|<span data-ttu-id="87d03-555">Patch</span><span class="sxs-lookup"><span data-stu-id="87d03-555">Patch</span></span>|<span data-ttu-id="87d03-556">5</span><span class="sxs-lookup"><span data-stu-id="87d03-556">5</span></span>|  
  
 <span data-ttu-id="87d03-557">`SourceType``SecondOperandType`Propriedades, e `XPathSourceType` -define usando valores da `DTSXMLSourceType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-557">`SourceType`, `SecondOperandType`, and `XPathSourceType` properties-Set by using values from the `DTSXMLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-558">Nome amigável em DTSXMLSourceType</span><span class="sxs-lookup"><span data-stu-id="87d03-558">Friendly name in DTSXMLSourceType</span></span>|<span data-ttu-id="87d03-559">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-559">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="87d03-560">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-560">FileConnection</span></span>|<span data-ttu-id="87d03-561">0</span><span class="sxs-lookup"><span data-stu-id="87d03-561">0</span></span>|  
|<span data-ttu-id="87d03-562">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-562">Variable</span></span>|<span data-ttu-id="87d03-563">1</span><span class="sxs-lookup"><span data-stu-id="87d03-563">1</span></span>|  
|<span data-ttu-id="87d03-564">DirectInput</span><span class="sxs-lookup"><span data-stu-id="87d03-564">DirectInput</span></span>|<span data-ttu-id="87d03-565">2</span><span class="sxs-lookup"><span data-stu-id="87d03-565">2</span></span>|  
  
 <span data-ttu-id="87d03-566">`DestinationType`e propriedades de **DiffGramDestinationType** – definidas usando valores da `DTSXMLSaveResultTo` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-566">`DestinationType` and **DiffGramDestinationType** properties-Set by using values from the `DTSXMLSaveResultTo` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-567">Nome amigável em DTSXMLSaveResultTo</span><span class="sxs-lookup"><span data-stu-id="87d03-567">Friendly name in DTSXMLSaveResultTo</span></span>|<span data-ttu-id="87d03-568">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-568">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="87d03-569">FileConnection</span><span class="sxs-lookup"><span data-stu-id="87d03-569">FileConnection</span></span>|<span data-ttu-id="87d03-570">0</span><span class="sxs-lookup"><span data-stu-id="87d03-570">0</span></span>|  
|<span data-ttu-id="87d03-571">Variável</span><span class="sxs-lookup"><span data-stu-id="87d03-571">Variable</span></span>|<span data-ttu-id="87d03-572">1</span><span class="sxs-lookup"><span data-stu-id="87d03-572">1</span></span>|  
  
 <span data-ttu-id="87d03-573">`ValidationType`Propriedade-definido usando valores da `DTSXMLValidationType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-573">`ValidationType` property-Set by using values from the `DTSXMLValidationType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-574">Nome amigável em DTSXMLValidationType</span><span class="sxs-lookup"><span data-stu-id="87d03-574">Friendly name in DTSXMLValidationType</span></span>|<span data-ttu-id="87d03-575">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-575">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-576">DTD</span><span class="sxs-lookup"><span data-stu-id="87d03-576">DTD</span></span>|<span data-ttu-id="87d03-577">0</span><span class="sxs-lookup"><span data-stu-id="87d03-577">0</span></span>|  
|<span data-ttu-id="87d03-578">XSD</span><span class="sxs-lookup"><span data-stu-id="87d03-578">XSD</span></span>|<span data-ttu-id="87d03-579">1</span><span class="sxs-lookup"><span data-stu-id="87d03-579">1</span></span>|  
  
 <span data-ttu-id="87d03-580">`XPathOperation`Propriedade-definido usando valores da `DTSXMLXPathOperation` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-580">`XPathOperation` property-Set by using values from the `DTSXMLXPathOperation` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-581">Nome amigável em DTSXMLXPathOperation</span><span class="sxs-lookup"><span data-stu-id="87d03-581">Friendly name in DTSXMLXPathOperation</span></span>|<span data-ttu-id="87d03-582">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-582">Numeric Value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-583">Avaliação</span><span class="sxs-lookup"><span data-stu-id="87d03-583">Evaluation</span></span>|<span data-ttu-id="87d03-584">0</span><span class="sxs-lookup"><span data-stu-id="87d03-584">0</span></span>|  
|<span data-ttu-id="87d03-585">Valores</span><span class="sxs-lookup"><span data-stu-id="87d03-585">Values</span></span>|<span data-ttu-id="87d03-586">1</span><span class="sxs-lookup"><span data-stu-id="87d03-586">1</span></span>|  
|<span data-ttu-id="87d03-587">NodeList</span><span class="sxs-lookup"><span data-stu-id="87d03-587">NodeList</span></span>|<span data-ttu-id="87d03-588">2</span><span class="sxs-lookup"><span data-stu-id="87d03-588">2</span></span>|  
  
 <span data-ttu-id="87d03-589">`DiffOptions`Propriedade-definido usando valores da `DTSXMLDiffOptions` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-589">`DiffOptions` property-Set by using values from the `DTSXMLDiffOptions` enumeration.</span></span> <span data-ttu-id="87d03-590">As opções deste enumerador não são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="87d03-590">The options in this enumerator are not mutually exclusive.</span></span> <span data-ttu-id="87d03-591">Para usar várias opções, forneça uma lista separada por vírgulas das opções a serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="87d03-591">To use multiple options, provide a comma-separated list of the options to apply.</span></span>  
  
|<span data-ttu-id="87d03-592">Nome amigável em DTSXMLDiffOptions</span><span class="sxs-lookup"><span data-stu-id="87d03-592">Friendly name in DTSXMLDiffOptions</span></span>|<span data-ttu-id="87d03-593">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-593">Numeric Value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="87d03-594">Nenhum</span><span class="sxs-lookup"><span data-stu-id="87d03-594">None</span></span>|<span data-ttu-id="87d03-595">0</span><span class="sxs-lookup"><span data-stu-id="87d03-595">0</span></span>|  
|<span data-ttu-id="87d03-596">IgnoreChildOrder</span><span class="sxs-lookup"><span data-stu-id="87d03-596">IgnoreChildOrder</span></span>|<span data-ttu-id="87d03-597">1</span><span class="sxs-lookup"><span data-stu-id="87d03-597">1</span></span>|  
|<span data-ttu-id="87d03-598">IgnoreComments</span><span class="sxs-lookup"><span data-stu-id="87d03-598">IgnoreComments</span></span>|<span data-ttu-id="87d03-599">2</span><span class="sxs-lookup"><span data-stu-id="87d03-599">2</span></span>|  
|<span data-ttu-id="87d03-600">IgnorePI</span><span class="sxs-lookup"><span data-stu-id="87d03-600">IgnorePI</span></span>|<span data-ttu-id="87d03-601">4</span><span class="sxs-lookup"><span data-stu-id="87d03-601">4</span></span>|  
|<span data-ttu-id="87d03-602">IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="87d03-602">IgnoreWhitespace</span></span>|<span data-ttu-id="87d03-603">8</span><span class="sxs-lookup"><span data-stu-id="87d03-603">8</span></span>|  
|<span data-ttu-id="87d03-604">IgnoreNamespaces</span><span class="sxs-lookup"><span data-stu-id="87d03-604">IgnoreNamespaces</span></span>|<span data-ttu-id="87d03-605">16</span><span class="sxs-lookup"><span data-stu-id="87d03-605">16</span></span>|  
|<span data-ttu-id="87d03-606">IgnorePrefixes</span><span class="sxs-lookup"><span data-stu-id="87d03-606">IgnorePrefixes</span></span>|<span data-ttu-id="87d03-607">32</span><span class="sxs-lookup"><span data-stu-id="87d03-607">32</span></span>|  
|<span data-ttu-id="87d03-608">IgnoreXmlDecl</span><span class="sxs-lookup"><span data-stu-id="87d03-608">IgnoreXmlDecl</span></span>|<span data-ttu-id="87d03-609">64</span><span class="sxs-lookup"><span data-stu-id="87d03-609">64</span></span>|  
|<span data-ttu-id="87d03-610">IgnoreDtd</span><span class="sxs-lookup"><span data-stu-id="87d03-610">IgnoreDtd</span></span>|<span data-ttu-id="87d03-611">128</span><span class="sxs-lookup"><span data-stu-id="87d03-611">128</span></span>|  
  
 <span data-ttu-id="87d03-612">`DiffAlgorithm`Propriedade-definido usando valores da `DTSXMLDiffAlgorithm` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-612">`DiffAlgorithm` property-Set by using values from the `DTSXMLDiffAlgorithm` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-613">Nome amigável em DTSXMLDiffAlgorithm</span><span class="sxs-lookup"><span data-stu-id="87d03-613">Friendly name in DTSXMLDiffAlgorithm</span></span>|<span data-ttu-id="87d03-614">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-614">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-615">Auto</span><span class="sxs-lookup"><span data-stu-id="87d03-615">Auto</span></span>|<span data-ttu-id="87d03-616">0</span><span class="sxs-lookup"><span data-stu-id="87d03-616">0</span></span>|  
|<span data-ttu-id="87d03-617">Rápido</span><span class="sxs-lookup"><span data-stu-id="87d03-617">Fast</span></span>|<span data-ttu-id="87d03-618">1</span><span class="sxs-lookup"><span data-stu-id="87d03-618">1</span></span>|  
|<span data-ttu-id="87d03-619">Preciso</span><span class="sxs-lookup"><span data-stu-id="87d03-619">Precise</span></span>|<span data-ttu-id="87d03-620">2</span><span class="sxs-lookup"><span data-stu-id="87d03-620">2</span></span>|  
  
##  <a name="maintenance-plan-tasks"></a><a name="MaintenancePlanTasks"></a> <span data-ttu-id="87d03-621">Tarefas do Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="87d03-621">Maintenance Plan Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="87d03-622">inclui um conjunto de tarefas que executam tarefas do SQL Server para uso em planos de manutenção e pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87d03-622">includes a set of tasks that perform SQL Server tasks for use in maintenance plans and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="87d03-623">não dá suporte ao trabalho programático com essas tarefas e a documentação de referência de programação não inclui documentação da API dessas tarefas e seus enumeradores.</span><span class="sxs-lookup"><span data-stu-id="87d03-623">does not support working with these tasks programmatically and programming reference documentation does not include API documentation of these tasks and their enumerators.</span></span>  
  
### <a name="all-maintenance-tasks"></a><span data-ttu-id="87d03-624">Todas as Tarefas de Manutenção</span><span class="sxs-lookup"><span data-stu-id="87d03-624">All Maintenance Tasks</span></span>  
 <span data-ttu-id="87d03-625">Todas as tarefas de manutenção usam as enumerações a seguir para definir as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="87d03-625">All maintenance tasks use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="87d03-626">`DatabaseSelectionType`Propriedade-definido usando valores da `DatabaseSelection` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-626">`DatabaseSelectionType` property-Set by using values from the `DatabaseSelection` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-627">Nome amigável em DatabaseSelection</span><span class="sxs-lookup"><span data-stu-id="87d03-627">Friendly name in DatabaseSelection</span></span>|<span data-ttu-id="87d03-628">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-628">Numeric value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="87d03-629">Nenhum</span><span class="sxs-lookup"><span data-stu-id="87d03-629">None</span></span>|<span data-ttu-id="87d03-630">0</span><span class="sxs-lookup"><span data-stu-id="87d03-630">0</span></span>|  
|<span data-ttu-id="87d03-631">Todos</span><span class="sxs-lookup"><span data-stu-id="87d03-631">All</span></span>|<span data-ttu-id="87d03-632">1</span><span class="sxs-lookup"><span data-stu-id="87d03-632">1</span></span>|  
|<span data-ttu-id="87d03-633">Sistema</span><span class="sxs-lookup"><span data-stu-id="87d03-633">System</span></span>|<span data-ttu-id="87d03-634">2</span><span class="sxs-lookup"><span data-stu-id="87d03-634">2</span></span>|  
|<span data-ttu-id="87d03-635">Usuário</span><span class="sxs-lookup"><span data-stu-id="87d03-635">User</span></span>|<span data-ttu-id="87d03-636">3</span><span class="sxs-lookup"><span data-stu-id="87d03-636">3</span></span>|  
|<span data-ttu-id="87d03-637">Específicas</span><span class="sxs-lookup"><span data-stu-id="87d03-637">Specific</span></span>|<span data-ttu-id="87d03-638">4</span><span class="sxs-lookup"><span data-stu-id="87d03-638">4</span></span>|  
  
 <span data-ttu-id="87d03-639">`TableSelectionType`Propriedade-definido usando valores da `TableSelection` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-639">`TableSelectionType` property-Set by using values from the `TableSelection` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-640">Nome amigável em TableSelection</span><span class="sxs-lookup"><span data-stu-id="87d03-640">Friendly name in TableSelection</span></span>|<span data-ttu-id="87d03-641">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-641">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-642">Nenhum</span><span class="sxs-lookup"><span data-stu-id="87d03-642">None</span></span>|<span data-ttu-id="87d03-643">0</span><span class="sxs-lookup"><span data-stu-id="87d03-643">0</span></span>|  
|<span data-ttu-id="87d03-644">Todos</span><span class="sxs-lookup"><span data-stu-id="87d03-644">All</span></span>|<span data-ttu-id="87d03-645">1</span><span class="sxs-lookup"><span data-stu-id="87d03-645">1</span></span>|  
|<span data-ttu-id="87d03-646">Específicas</span><span class="sxs-lookup"><span data-stu-id="87d03-646">Specific</span></span>|<span data-ttu-id="87d03-647">2</span><span class="sxs-lookup"><span data-stu-id="87d03-647">2</span></span>|  
  
 <span data-ttu-id="87d03-648">`ObjectTypeSelection`Propriedade-definido usando valores da `ObjectType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-648">`ObjectTypeSelection` property-Set by using values from the `ObjectType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-649">Nome amigável em ObjectType</span><span class="sxs-lookup"><span data-stu-id="87d03-649">Friendly name in ObjectType</span></span>|<span data-ttu-id="87d03-650">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-650">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="87d03-651">Tabela</span><span class="sxs-lookup"><span data-stu-id="87d03-651">Table</span></span>|<span data-ttu-id="87d03-652">0</span><span class="sxs-lookup"><span data-stu-id="87d03-652">0</span></span>|  
|<span data-ttu-id="87d03-653">Visualizar</span><span class="sxs-lookup"><span data-stu-id="87d03-653">View</span></span>|<span data-ttu-id="87d03-654">1</span><span class="sxs-lookup"><span data-stu-id="87d03-654">1</span></span>|  
|<span data-ttu-id="87d03-655">TableView</span><span class="sxs-lookup"><span data-stu-id="87d03-655">TableView</span></span>|<span data-ttu-id="87d03-656">2</span><span class="sxs-lookup"><span data-stu-id="87d03-656">2</span></span>|  
  
### <a name="back-up-database-task"></a><span data-ttu-id="87d03-657">Tarefa de Backup de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="87d03-657">Back Up Database Task</span></span>  
 <span data-ttu-id="87d03-658">`DestinationCreationType`Propriedade-definido usando valores da `DestinationType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-658">`DestinationCreationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-659">Nome amigável em DestinationType</span><span class="sxs-lookup"><span data-stu-id="87d03-659">Friendly name in DestinationType</span></span>|<span data-ttu-id="87d03-660">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-660">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="87d03-661">Auto</span><span class="sxs-lookup"><span data-stu-id="87d03-661">Auto</span></span>|<span data-ttu-id="87d03-662">0</span><span class="sxs-lookup"><span data-stu-id="87d03-662">0</span></span>|  
|<span data-ttu-id="87d03-663">Manual</span><span class="sxs-lookup"><span data-stu-id="87d03-663">Manual</span></span>|<span data-ttu-id="87d03-664">1</span><span class="sxs-lookup"><span data-stu-id="87d03-664">1</span></span>|  
  
 <span data-ttu-id="87d03-665">`ExistingBackupsAction`Propriedade-definido usando valores da `ActionForExistingBackups` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-665">`ExistingBackupsAction` property-Set by using values from the `ActionForExistingBackups` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-666">Nome amigável em ActionForExistingBackups</span><span class="sxs-lookup"><span data-stu-id="87d03-666">Friendly name in ActionForExistingBackups</span></span>|<span data-ttu-id="87d03-667">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-667">Numeric value</span></span>|  
|-----------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-668">Acrescentar</span><span class="sxs-lookup"><span data-stu-id="87d03-668">Append</span></span>|<span data-ttu-id="87d03-669">0</span><span class="sxs-lookup"><span data-stu-id="87d03-669">0</span></span>|  
|<span data-ttu-id="87d03-670">Overwrite</span><span class="sxs-lookup"><span data-stu-id="87d03-670">Overwrite</span></span>|<span data-ttu-id="87d03-671">1</span><span class="sxs-lookup"><span data-stu-id="87d03-671">1</span></span>|  
  
 <span data-ttu-id="87d03-672">`BackupAction`Propriedade-definido usando valores da `BackupTaskType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-672">`BackupAction` property-Set by using values from the `BackupTaskType` enumeration.</span></span> <span data-ttu-id="87d03-673">Esta propriedade trabalha com a propriedade `BackupIsIncremental` para definir o tipo de backup que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="87d03-673">This property works with the `BackupIsIncremental` property to define the type of backup that the task performs.</span></span>  
  
|<span data-ttu-id="87d03-674">Nome amigável em BackupTaskType</span><span class="sxs-lookup"><span data-stu-id="87d03-674">Friendly name in BackupTaskType</span></span>|<span data-ttu-id="87d03-675">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-675">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-676">Banco de dados</span><span class="sxs-lookup"><span data-stu-id="87d03-676">Database</span></span>|<span data-ttu-id="87d03-677">0</span><span class="sxs-lookup"><span data-stu-id="87d03-677">0</span></span>|  
|<span data-ttu-id="87d03-678">Arquivos</span><span class="sxs-lookup"><span data-stu-id="87d03-678">Files</span></span>|<span data-ttu-id="87d03-679">1</span><span class="sxs-lookup"><span data-stu-id="87d03-679">1</span></span>|  
|<span data-ttu-id="87d03-680">Log</span><span class="sxs-lookup"><span data-stu-id="87d03-680">Log</span></span>|<span data-ttu-id="87d03-681">2</span><span class="sxs-lookup"><span data-stu-id="87d03-681">2</span></span>|  
  
 <span data-ttu-id="87d03-682">`BackupDevice`Propriedade-definido usando valores da enumeração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Smo (Management Objects) `DeviceType` .</span><span class="sxs-lookup"><span data-stu-id="87d03-682">`BackupDevice` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `DeviceType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-683">Nome amigável em DeviceType</span><span class="sxs-lookup"><span data-stu-id="87d03-683">Friendly name in DeviceType</span></span>|<span data-ttu-id="87d03-684">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-684">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="87d03-685">LogicalDevice</span><span class="sxs-lookup"><span data-stu-id="87d03-685">LogicalDevice</span></span>|<span data-ttu-id="87d03-686">0</span><span class="sxs-lookup"><span data-stu-id="87d03-686">0</span></span>|  
|<span data-ttu-id="87d03-687">Tape</span><span class="sxs-lookup"><span data-stu-id="87d03-687">Tape</span></span>|<span data-ttu-id="87d03-688">1</span><span class="sxs-lookup"><span data-stu-id="87d03-688">1</span></span>|  
|<span data-ttu-id="87d03-689">Arquivo</span><span class="sxs-lookup"><span data-stu-id="87d03-689">File</span></span>|<span data-ttu-id="87d03-690">2</span><span class="sxs-lookup"><span data-stu-id="87d03-690">2</span></span>|  
|<span data-ttu-id="87d03-691">Pipe</span><span class="sxs-lookup"><span data-stu-id="87d03-691">Pipe</span></span>|<span data-ttu-id="87d03-692">3</span><span class="sxs-lookup"><span data-stu-id="87d03-692">3</span></span>|  
|<span data-ttu-id="87d03-693">VirtualDevice</span><span class="sxs-lookup"><span data-stu-id="87d03-693">VirtualDevice</span></span>|<span data-ttu-id="87d03-694">4</span><span class="sxs-lookup"><span data-stu-id="87d03-694">4</span></span>|  
  
### <a name="maintenance-cleanup-task"></a><span data-ttu-id="87d03-695">Tarefa Limpeza de Manutenção</span><span class="sxs-lookup"><span data-stu-id="87d03-695">Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="87d03-696">`FileTypeSelected`Propriedade-definido usando valores da `FileType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-696">`FileTypeSelected` property-Set by using values from the `FileType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-697">Nome amigável em FileType</span><span class="sxs-lookup"><span data-stu-id="87d03-697">Friendly name in FileType</span></span>|<span data-ttu-id="87d03-698">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-698">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="87d03-699">FileBackup</span><span class="sxs-lookup"><span data-stu-id="87d03-699">FileBackup</span></span>|<span data-ttu-id="87d03-700">0</span><span class="sxs-lookup"><span data-stu-id="87d03-700">0</span></span>|  
|<span data-ttu-id="87d03-701">FileReport</span><span class="sxs-lookup"><span data-stu-id="87d03-701">FileReport</span></span>|<span data-ttu-id="87d03-702">1</span><span class="sxs-lookup"><span data-stu-id="87d03-702">1</span></span>|  
  
 <span data-ttu-id="87d03-703">`OlderThanTimeUnitType`Propriedade-definido usando valores da `TimeUnitType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-703">`OlderThanTimeUnitType` property-Set by using values from the `TimeUnitType` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-704">Nome amigável em TimeUnitType</span><span class="sxs-lookup"><span data-stu-id="87d03-704">Friendly Name in TimeUnitType</span></span>|<span data-ttu-id="87d03-705">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-705">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="87d03-706">Dia</span><span class="sxs-lookup"><span data-stu-id="87d03-706">Day</span></span>|<span data-ttu-id="87d03-707">0</span><span class="sxs-lookup"><span data-stu-id="87d03-707">0</span></span>|  
|<span data-ttu-id="87d03-708">Semana</span><span class="sxs-lookup"><span data-stu-id="87d03-708">Week</span></span>|<span data-ttu-id="87d03-709">1</span><span class="sxs-lookup"><span data-stu-id="87d03-709">1</span></span>|  
|<span data-ttu-id="87d03-710">Month</span><span class="sxs-lookup"><span data-stu-id="87d03-710">Month</span></span>|<span data-ttu-id="87d03-711">2</span><span class="sxs-lookup"><span data-stu-id="87d03-711">2</span></span>|  
|<span data-ttu-id="87d03-712">Ano</span><span class="sxs-lookup"><span data-stu-id="87d03-712">Year</span></span>|<span data-ttu-id="87d03-713">3</span><span class="sxs-lookup"><span data-stu-id="87d03-713">3</span></span>|  
  
### <a name="update-statistics-task"></a><span data-ttu-id="87d03-714">Tarefa Atualizar Estatísticas</span><span class="sxs-lookup"><span data-stu-id="87d03-714">Update Statistics Task</span></span>  
 <span data-ttu-id="87d03-715">`UpdateType`Propriedade-definido usando valores da enumeração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Smo (Management Objects) `StatisticsTarget` .</span><span class="sxs-lookup"><span data-stu-id="87d03-715">`UpdateType` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `StatisticsTarget` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-716">Nome amigável em StatisticsTarget</span><span class="sxs-lookup"><span data-stu-id="87d03-716">Friendly name in StatisticsTarget</span></span>|<span data-ttu-id="87d03-717">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-717">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="87d03-718">Coluna</span><span class="sxs-lookup"><span data-stu-id="87d03-718">Column</span></span>|<span data-ttu-id="87d03-719">1</span><span class="sxs-lookup"><span data-stu-id="87d03-719">1</span></span>|  
|<span data-ttu-id="87d03-720">Índice</span><span class="sxs-lookup"><span data-stu-id="87d03-720">Index</span></span>|<span data-ttu-id="87d03-721">2</span><span class="sxs-lookup"><span data-stu-id="87d03-721">2</span></span>|  
|<span data-ttu-id="87d03-722">Todos</span><span class="sxs-lookup"><span data-stu-id="87d03-722">All</span></span>|<span data-ttu-id="87d03-723">3</span><span class="sxs-lookup"><span data-stu-id="87d03-723">3</span></span>|  
  
##  <a name="common-properties"></a><a name="CommonProperties"></a> <span data-ttu-id="87d03-724">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="87d03-724">Common Properties</span></span>  
 <span data-ttu-id="87d03-725">Pacotes, tarefas e os contêineres Loop Foreach, Loop For e Sequência podem usar as enumerações a seguir para definir as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="87d03-725">Packages, tasks, and the Foreach Loop, For Loop, and Sequence containers can use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="87d03-726">`ForceExecutionResult`Propriedade-definido usando valores da `DTSForcedExecResult` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-726">`ForceExecutionResult` property-Set by using values from the `DTSForcedExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-727">Nome amigável em DTSForcedExecResult</span><span class="sxs-lookup"><span data-stu-id="87d03-727">Friendly name in DTSForcedExecResult</span></span>|<span data-ttu-id="87d03-728">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-728">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-729">Nenhum</span><span class="sxs-lookup"><span data-stu-id="87d03-729">None</span></span>|<span data-ttu-id="87d03-730">-1</span><span class="sxs-lookup"><span data-stu-id="87d03-730">-1</span></span>|  
|<span data-ttu-id="87d03-731">Sucesso</span><span class="sxs-lookup"><span data-stu-id="87d03-731">Success</span></span>|<span data-ttu-id="87d03-732">0</span><span class="sxs-lookup"><span data-stu-id="87d03-732">0</span></span>|  
|<span data-ttu-id="87d03-733">Falha</span><span class="sxs-lookup"><span data-stu-id="87d03-733">Failure</span></span>|<span data-ttu-id="87d03-734">1</span><span class="sxs-lookup"><span data-stu-id="87d03-734">1</span></span>|  
|<span data-ttu-id="87d03-735">Completion</span><span class="sxs-lookup"><span data-stu-id="87d03-735">Completion</span></span>|<span data-ttu-id="87d03-736">2</span><span class="sxs-lookup"><span data-stu-id="87d03-736">2</span></span>|  
  
 <span data-ttu-id="87d03-737">`IsolationLevel`Propriedade-definida pela enumeração de .NET Framework `IsolationLevel` .</span><span class="sxs-lookup"><span data-stu-id="87d03-737">`IsolationLevel` property-Set by the .NET Framework `IsolationLevel` enumeration.</span></span> <span data-ttu-id="87d03-738">Para obter mais informações, consulte a Biblioteca de Classes do .NET Framework em [Biblioteca MSDN](https://go.microsoft.com/fwlink?LinkId=17313).</span><span class="sxs-lookup"><span data-stu-id="87d03-738">For more information, see the .NET Framework Class Library in the [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span></span>  
  
 <span data-ttu-id="87d03-739">`LoggingMode`Propriedade-definido usando valores da `DTSLoggingMode` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-739">`LoggingMode` property-Set by using values from the `DTSLoggingMode` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-740">Nome amigável em DTSLoggingMode</span><span class="sxs-lookup"><span data-stu-id="87d03-740">Friendly name in DTSLoggingMode</span></span>|<span data-ttu-id="87d03-741">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-741">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="87d03-742">UseParentSetting</span><span class="sxs-lookup"><span data-stu-id="87d03-742">UseParentSetting</span></span>|<span data-ttu-id="87d03-743">0</span><span class="sxs-lookup"><span data-stu-id="87d03-743">0</span></span>|  
|<span data-ttu-id="87d03-744">habilitado</span><span class="sxs-lookup"><span data-stu-id="87d03-744">Enabled</span></span>|<span data-ttu-id="87d03-745">1</span><span class="sxs-lookup"><span data-stu-id="87d03-745">1</span></span>|  
|<span data-ttu-id="87d03-746">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="87d03-746">Disabled</span></span>|<span data-ttu-id="87d03-747">2</span><span class="sxs-lookup"><span data-stu-id="87d03-747">2</span></span>|  
  
 <span data-ttu-id="87d03-748">`TransactionOption`Propriedade-definido usando valores da `DTSTransactionOption` enumeração.</span><span class="sxs-lookup"><span data-stu-id="87d03-748">`TransactionOption` property-Set by using values from the `DTSTransactionOption` enumeration.</span></span>  
  
|<span data-ttu-id="87d03-749">Nome amigável em DTSTransactionOption</span><span class="sxs-lookup"><span data-stu-id="87d03-749">Friendly name in DTSTransactionOption</span></span>|<span data-ttu-id="87d03-750">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="87d03-750">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="87d03-751">NotSupported</span><span class="sxs-lookup"><span data-stu-id="87d03-751">NotSupported</span></span>|<span data-ttu-id="87d03-752">0</span><span class="sxs-lookup"><span data-stu-id="87d03-752">0</span></span>|  
|<span data-ttu-id="87d03-753">Suportado</span><span class="sxs-lookup"><span data-stu-id="87d03-753">Supported</span></span>|<span data-ttu-id="87d03-754">1</span><span class="sxs-lookup"><span data-stu-id="87d03-754">1</span></span>|  
|<span data-ttu-id="87d03-755">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="87d03-755">Required</span></span>|<span data-ttu-id="87d03-756">2</span><span class="sxs-lookup"><span data-stu-id="87d03-756">2</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="87d03-757">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="87d03-757">Related Tasks</span></span>  
 [<span data-ttu-id="87d03-758">Adicionar ou alterar uma expressão de propriedade</span><span class="sxs-lookup"><span data-stu-id="87d03-758">Add or Change a Property Expression</span></span>](add-or-change-a-property-expression.md)  
  
## <a name="see-also"></a><span data-ttu-id="87d03-759">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87d03-759">See Also</span></span>  
 <span data-ttu-id="87d03-760">[Usar expressões de propriedade em pacotes](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="87d03-760">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="87d03-761">[Pacotes do Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="87d03-761">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="87d03-762">[Contêineres do Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="87d03-762">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="87d03-763">[Tarefas do Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="87d03-763">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="87d03-764">Restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="87d03-764">Precedence Constraints</span></span>](../control-flow/precedence-constraints.md)  
  
  
