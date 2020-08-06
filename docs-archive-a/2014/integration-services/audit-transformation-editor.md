---
title: Editor de transformação Auditoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684834"
---
# <a name="audit-transformation-editor"></a><span data-ttu-id="3ceda-102">Editor de Transformação Auditoria</span><span class="sxs-lookup"><span data-stu-id="3ceda-102">Audit Transformation Editor</span></span>
  <span data-ttu-id="3ceda-103">A opção Auditar Transformação permite ao fluxo de dados de um pacote incluir dados sobre o ambiente em que o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="3ceda-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="3ceda-104">Por exemplo, o nome do pacote, o computador e o operador podem ser adicionados ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="3ceda-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="3ceda-105">inclui variáveis do sistema que fornecem essas informações.</span><span class="sxs-lookup"><span data-stu-id="3ceda-105">includes system variables that provide this information.</span></span>  
  
 <span data-ttu-id="3ceda-106">Para saber mais sobre Auditar Transformação, consulte [Audit Transformation](data-flow/transformations/audit-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3ceda-106">To learn more about the Audit transformation, see [Audit Transformation](data-flow/transformations/audit-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3ceda-107">Opções</span><span class="sxs-lookup"><span data-stu-id="3ceda-107">Options</span></span>  
 <span data-ttu-id="3ceda-108">**Nome da coluna de saída**</span><span class="sxs-lookup"><span data-stu-id="3ceda-108">**Output column name**</span></span>  
 <span data-ttu-id="3ceda-109">Forneça um nome para a nova coluna de saída que conterá as informações de auditoria.</span><span class="sxs-lookup"><span data-stu-id="3ceda-109">Provide the name for a new output column that will contain the audit information.</span></span>  
  
 <span data-ttu-id="3ceda-110">**Tipo de auditoria**</span><span class="sxs-lookup"><span data-stu-id="3ceda-110">**Audit type**</span></span>  
 <span data-ttu-id="3ceda-111">Selecione uma variável de sistema disponível para fornecer as informações de auditoria.</span><span class="sxs-lookup"><span data-stu-id="3ceda-111">Select an available system variable to supply the audit information.</span></span>  
  
|<span data-ttu-id="3ceda-112">Valor</span><span class="sxs-lookup"><span data-stu-id="3ceda-112">Value</span></span>|<span data-ttu-id="3ceda-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3ceda-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ceda-114">**GUID de instância de execução**</span><span class="sxs-lookup"><span data-stu-id="3ceda-114">**Execution instance GUID**</span></span>|<span data-ttu-id="3ceda-115">Insira o GUID que identifica com exclusividade a instância de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="3ceda-115">Insert the GUID that uniquely identifies the execution instance of the package.</span></span>|  
|<span data-ttu-id="3ceda-116">**ID do Pacote**</span><span class="sxs-lookup"><span data-stu-id="3ceda-116">**Package ID**</span></span>|<span data-ttu-id="3ceda-117">Insira o GUID que identifica com exclusividade o pacote.</span><span class="sxs-lookup"><span data-stu-id="3ceda-117">Insert the GUID that uniquely identifies the package.</span></span>|  
|<span data-ttu-id="3ceda-118">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="3ceda-118">**Package name**</span></span>|<span data-ttu-id="3ceda-119">Insira o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="3ceda-119">Insert the package name.</span></span>|  
|<span data-ttu-id="3ceda-120">**ID da Versão**</span><span class="sxs-lookup"><span data-stu-id="3ceda-120">**Version ID**</span></span>|<span data-ttu-id="3ceda-121">Insira o GUID que identifica com exclusividade a versão do pacote.</span><span class="sxs-lookup"><span data-stu-id="3ceda-121">Insert the GUID that uniquely identifies the version of the package.</span></span>|  
|<span data-ttu-id="3ceda-122">**Hora de início de execução**</span><span class="sxs-lookup"><span data-stu-id="3ceda-122">**Execution start time**</span></span>|<span data-ttu-id="3ceda-123">Insira a hora de início de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="3ceda-123">Insert the time at which package execution started.</span></span>|  
|<span data-ttu-id="3ceda-124">**Nome do computador**</span><span class="sxs-lookup"><span data-stu-id="3ceda-124">**Machine name**</span></span>|<span data-ttu-id="3ceda-125">Insira o nome do computador no qual o pacote foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="3ceda-125">Insert the name of the computer on which the package was launched.</span></span>|  
|<span data-ttu-id="3ceda-126">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="3ceda-126">**User name**</span></span>|<span data-ttu-id="3ceda-127">Insira o nome de logon do usuário que inicializou o pacote.</span><span class="sxs-lookup"><span data-stu-id="3ceda-127">Insert the login name of the user who launched the package.</span></span>|  
|<span data-ttu-id="3ceda-128">**Nome da tarefa**</span><span class="sxs-lookup"><span data-stu-id="3ceda-128">**Task name**</span></span>|<span data-ttu-id="3ceda-129">Insira o nome da tarefa de Fluxo de Dados com a qual Auditar Transformação está associada.</span><span class="sxs-lookup"><span data-stu-id="3ceda-129">Insert the name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="3ceda-130">**ID da Tarefa**</span><span class="sxs-lookup"><span data-stu-id="3ceda-130">**Task ID**</span></span>|<span data-ttu-id="3ceda-131">Insira o GUID que identifica com exclusividade a tarefa de Fluxo de Dados com a qual Auditar Transformação está associada.</span><span class="sxs-lookup"><span data-stu-id="3ceda-131">Insert the GUID that uniquely identifies the Data Flow task with which the Audit transformation is associated.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ceda-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ceda-132">See Also</span></span>  
 [<span data-ttu-id="3ceda-133">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="3ceda-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
