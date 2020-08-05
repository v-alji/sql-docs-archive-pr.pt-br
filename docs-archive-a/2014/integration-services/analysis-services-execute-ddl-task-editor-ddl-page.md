---
title: Editor da tarefa Executar DDL do Analysis Services (página DDL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571526"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a><span data-ttu-id="3f665-102">Editor da Tarefa Executar DDL do Analysis Services (Página DDL)</span><span class="sxs-lookup"><span data-stu-id="3f665-102">Analysis Services Execute DDL Task Editor (DDL Page)</span></span>
  <span data-ttu-id="3f665-103">Use a página **DDL** da caixa de diálogo **Editor da Tarefa Executar DDL do Analysis Services** para especificar uma conexão com um projeto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou um banco de dados [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e para fornecer informações sobre a origem das instruções DDL (linguagem de definição de dados).</span><span class="sxs-lookup"><span data-stu-id="3f665-103">Use the **DDL** page of the **Analysis Services Execute DDL Task Editor** dialog box to specify a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and to provide information about the source of data definition language (DDL) statements.</span></span>  
  
 <span data-ttu-id="3f665-104">Para saber mais sobre essa tarefa, consulte [Tarefa Executar DDL do Analysis Services](control-flow/analysis-services-execute-ddl-task.md).</span><span class="sxs-lookup"><span data-stu-id="3f665-104">To learn about this task, see [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="3f665-105">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="3f665-105">Static Options</span></span>  
 <span data-ttu-id="3f665-106">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="3f665-106">**Connection**</span></span>  
 <span data-ttu-id="3f665-107">Selecione um projeto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou um gerenciador de conexões [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] na lista ou clique em \<**New connection...**> e use a caixa de diálogo **Adicionar Gerenciador de Conexões do Analysis Services** para criar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="3f665-107">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list, or click \<**New connection...**> and use the **Add Analysis Services Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="3f665-108">**Tópicos relacionados:** [Referência da interface do usuário da caixa de diálogo Adicionar Gerenciador de Conexões do Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Gerenciador de Conexão do Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="3f665-108">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="3f665-109">**SourceType**</span><span class="sxs-lookup"><span data-stu-id="3f665-109">**SourceType**</span></span>  
 <span data-ttu-id="3f665-110">Especifique a origem da instrução DDL.</span><span class="sxs-lookup"><span data-stu-id="3f665-110">Specify the source type of the DDL statements.</span></span> <span data-ttu-id="3f665-111">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="3f665-111">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="3f665-112">Valor</span><span class="sxs-lookup"><span data-stu-id="3f665-112">Value</span></span>|<span data-ttu-id="3f665-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f665-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f665-114">**Direct Input**</span><span class="sxs-lookup"><span data-stu-id="3f665-114">**Direct Input**</span></span>|<span data-ttu-id="3f665-115">Define a origem da instrução DDL armazenada na caixa de texto **SourceDirect** .</span><span class="sxs-lookup"><span data-stu-id="3f665-115">Set the source to the DDL statement stored in the **SourceDirect** text box.</span></span> <span data-ttu-id="3f665-116">A seleção deste valor exibe as opções dinâmicas na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f665-116">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="3f665-117">**File Connection**</span><span class="sxs-lookup"><span data-stu-id="3f665-117">**File Connection**</span></span>|<span data-ttu-id="3f665-118">Define a origem para um arquivo que contém a instrução DDL.</span><span class="sxs-lookup"><span data-stu-id="3f665-118">Set the source to a file that contains the DDL statement.</span></span> <span data-ttu-id="3f665-119">A seleção deste valor exibe as opções dinâmicas na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f665-119">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="3f665-120">**Variável**</span><span class="sxs-lookup"><span data-stu-id="3f665-120">**Variable**</span></span>|<span data-ttu-id="3f665-121">Define a origem para uma variável.</span><span class="sxs-lookup"><span data-stu-id="3f665-121">Set the source to a variable.</span></span> <span data-ttu-id="3f665-122">A seleção deste valor exibe as opções dinâmicas na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f665-122">Selecting this value displays the dynamic options in the following section.</span></span>|  
  
## <a name="dynamic-options"></a><span data-ttu-id="3f665-123">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="3f665-123">Dynamic Options</span></span>  
  
### <a name="sourcetype--direct-input"></a><span data-ttu-id="3f665-124">SourceType = Entrada Direta</span><span class="sxs-lookup"><span data-stu-id="3f665-124">SourceType = Direct Input</span></span>  
 <span data-ttu-id="3f665-125">**Origem**</span><span class="sxs-lookup"><span data-stu-id="3f665-125">**Source**</span></span>  
 <span data-ttu-id="3f665-126">Digite as instruções DDL ou clique nas reticências **(...)** e digite as instruções na caixa de diálogo **Instruções DDL**.</span><span class="sxs-lookup"><span data-stu-id="3f665-126">Type the DDL statements or click the ellipsis **(...)** and then type the statements in the **DDL Statements** dialog box.</span></span>  
  
### <a name="sourcetype--file-connection"></a><span data-ttu-id="3f665-127">SourceType = File Connection</span><span class="sxs-lookup"><span data-stu-id="3f665-127">SourceType = File Connection</span></span>  
 <span data-ttu-id="3f665-128">**Origem**</span><span class="sxs-lookup"><span data-stu-id="3f665-128">**Source**</span></span>  
 <span data-ttu-id="3f665-129">Selecione uma conexão de Arquivo na lista ou clique em \<**New connection...**> e use a caixa de diálogo **Adicionar Gerenciador de Conexões de Arquivos** para criar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="3f665-129">Select a File connection in the list, or click \<**New connection...**> and use the **File Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="3f665-130">**Tópicos relacionados:** [Gerenciador de Conexão de Arquivo](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="3f665-130">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
### <a name="sourcetype--variable"></a><span data-ttu-id="3f665-131">SourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="3f665-131">SourceType = Variable</span></span>  
 <span data-ttu-id="3f665-132">**Origem**</span><span class="sxs-lookup"><span data-stu-id="3f665-132">**Source**</span></span>  
 <span data-ttu-id="3f665-133">Selecione uma variável na lista ou clique em \<**New variable...**> e use a caixa de diálogo **Adicionar Variável** para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="3f665-133">Select a variable in the list, or click \<**New variable...**> and use the **Add Variable** dialog box to create a new variable.</span></span>  
  
 <span data-ttu-id="3f665-134">**Tópicos relacionados:** [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="3f665-134">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f665-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f665-135">See Also</span></span>  
 <span data-ttu-id="3f665-136">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3f665-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="3f665-137">[Analysis Services executar o editor da tarefa DDL &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="3f665-137">[Analysis Services Execute DDL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="3f665-138">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="3f665-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="3f665-139">[Fluxo de Controle](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="3f665-139">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="3f665-140">[Analysis Services linguagem de script &#40;referência de&#41; do ASSL](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="3f665-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="3f665-141">Referência de XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="3f665-141">XML for Analysis  &#40;XMLA&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
