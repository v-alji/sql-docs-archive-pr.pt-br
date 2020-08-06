---
title: Transformação Auditoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittrans.f1
helpviewer_keywords:
- environment data in packages [Integration Services]
- Audit transformation
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8e302f6dd1dc5666ae65af2eb9705a4922915c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678872"
---
# <a name="audit-transformation"></a><span data-ttu-id="fcfec-102">Transformação Auditoria</span><span class="sxs-lookup"><span data-stu-id="fcfec-102">Audit Transformation</span></span>
  <span data-ttu-id="fcfec-103">A opção Auditar Transformação permite ao fluxo de dados de um pacote incluir dados sobre o ambiente em que o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="fcfec-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="fcfec-104">Por exemplo, o nome do pacote, o computador e o operador podem ser adicionados ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="fcfec-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="fcfec-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui variáveis do sistema que fornecem essas informações.</span><span class="sxs-lookup"><span data-stu-id="fcfec-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes system variables that provide this information.</span></span>  
  
## <a name="system-variables"></a><span data-ttu-id="fcfec-106">Variáveis do sistema</span><span class="sxs-lookup"><span data-stu-id="fcfec-106">System Variables</span></span>  
 <span data-ttu-id="fcfec-107">A tabela a seguir descreve as variáveis do sistema que podem ser usadas por Auditar Transformação.</span><span class="sxs-lookup"><span data-stu-id="fcfec-107">The following table describes the system variables that the Audit transformation can use.</span></span>  
  
|<span data-ttu-id="fcfec-108">Variável do sistema</span><span class="sxs-lookup"><span data-stu-id="fcfec-108">System variable</span></span>|<span data-ttu-id="fcfec-109">Índice</span><span class="sxs-lookup"><span data-stu-id="fcfec-109">Index</span></span>|<span data-ttu-id="fcfec-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="fcfec-110">Description</span></span>|  
|---------------------|-----------|-----------------|  
|`ExecutionInstanceGUID`|<span data-ttu-id="fcfec-111">0</span><span class="sxs-lookup"><span data-stu-id="fcfec-111">0</span></span>|<span data-ttu-id="fcfec-112">O GUID que identifica a instância de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="fcfec-112">The GUID that identifies the execution instance of the package.</span></span>|  
|`PackageID`|<span data-ttu-id="fcfec-113">1</span><span class="sxs-lookup"><span data-stu-id="fcfec-113">1</span></span>|<span data-ttu-id="fcfec-114">O identificador exclusivo do pacote.</span><span class="sxs-lookup"><span data-stu-id="fcfec-114">The unique identifier of the package.</span></span>|  
|`PackageName`|<span data-ttu-id="fcfec-115">2</span><span class="sxs-lookup"><span data-stu-id="fcfec-115">2</span></span>|<span data-ttu-id="fcfec-116">O nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="fcfec-116">The package name.</span></span>|  
|`VersionID`|<span data-ttu-id="fcfec-117">3</span><span class="sxs-lookup"><span data-stu-id="fcfec-117">3</span></span>|<span data-ttu-id="fcfec-118">A versão do pacote.</span><span class="sxs-lookup"><span data-stu-id="fcfec-118">The version of the package.</span></span>|  
|`ExecutionStartTime`|<span data-ttu-id="fcfec-119">4</span><span class="sxs-lookup"><span data-stu-id="fcfec-119">4</span></span>|<span data-ttu-id="fcfec-120">A hora de início da execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="fcfec-120">The time the package started to run.</span></span>|  
|`MachineName`|<span data-ttu-id="fcfec-121">5</span><span class="sxs-lookup"><span data-stu-id="fcfec-121">5</span></span>|<span data-ttu-id="fcfec-122">O nome do computador.</span><span class="sxs-lookup"><span data-stu-id="fcfec-122">The computer name.</span></span>|  
|`UserName`|<span data-ttu-id="fcfec-123">6</span><span class="sxs-lookup"><span data-stu-id="fcfec-123">6</span></span>|<span data-ttu-id="fcfec-124">O nome de logon da pessoa que iniciou o pacote.</span><span class="sxs-lookup"><span data-stu-id="fcfec-124">The login name of the person who started the package.</span></span>|  
|`TaskName`|<span data-ttu-id="fcfec-125">7</span><span class="sxs-lookup"><span data-stu-id="fcfec-125">7</span></span>|<span data-ttu-id="fcfec-126">O nome da tarefa Fluxo de Dados à qual Auditar Transformação está associada.</span><span class="sxs-lookup"><span data-stu-id="fcfec-126">The name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="fcfec-127">**TaskId**</span><span class="sxs-lookup"><span data-stu-id="fcfec-127">**TaskId**</span></span>|<span data-ttu-id="fcfec-128">8</span><span class="sxs-lookup"><span data-stu-id="fcfec-128">8</span></span>|<span data-ttu-id="fcfec-129">O identificador exclusivo da tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="fcfec-129">The unique identifier of the Data Flow task.</span></span>|  
  
## <a name="configuration-of-the-audit-transformation"></a><span data-ttu-id="fcfec-130">Configuração da Transformação Auditoria</span><span class="sxs-lookup"><span data-stu-id="fcfec-130">Configuration of the Audit Transformation</span></span>  
 <span data-ttu-id="fcfec-131">Para configurar a opção Auditar Transformação, forneça o nome de uma nova coluna de saída a ser adicionada à saída da transformação e, em seguida, mapeie a variável do sistema para a coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="fcfec-131">You configure the Audit transformation by providing the name of a new output column to add to the transformation output, and then mapping the system variable to the output column.</span></span> <span data-ttu-id="fcfec-132">Você pode mapear uma única variável do sistema para várias colunas.</span><span class="sxs-lookup"><span data-stu-id="fcfec-132">You can map a single system variable to multiple columns.</span></span>  
  
 <span data-ttu-id="fcfec-133">Essa transformação tem uma entrada e uma saída.</span><span class="sxs-lookup"><span data-stu-id="fcfec-133">This transformation has one input and one output.</span></span> <span data-ttu-id="fcfec-134">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="fcfec-134">It does not support an error output.</span></span>  
  
 <span data-ttu-id="fcfec-135">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="fcfec-135">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fcfec-136">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Auditar Editor de Transformação** , consulte [Audit Transformation Editor](../../audit-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="fcfec-136">For more information about the properties that you can set in the **Audit Transformation Editor** dialog box, see [Audit Transformation Editor](../../audit-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="fcfec-137">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="fcfec-137">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="fcfec-138">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="fcfec-138">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fcfec-139">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="fcfec-139">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="fcfec-140">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="fcfec-140">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="fcfec-141">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fcfec-141">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
