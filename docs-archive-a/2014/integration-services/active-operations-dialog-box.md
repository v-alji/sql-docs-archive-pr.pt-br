---
title: Caixa de diálogo operações ativas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isoperations.executions.f1
- sql12.ssis.ssms.isoperations.general.f1
ms.assetid: 5bb0fcd6-0ce9-488a-85b8-25dddaa03cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49861de7be207875c554e02d3f3b1b2f941fff64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570828"
---
# <a name="active-operations-dialog-box"></a><span data-ttu-id="0d3a7-102">Caixa de diálogo Operações Ativas</span><span class="sxs-lookup"><span data-stu-id="0d3a7-102">Active Operations Dialog Box</span></span>
  <span data-ttu-id="0d3a7-103">Use a caixa de diálogo **Operações Ativas** para exibir o status de operações do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] em execução no momento no servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , como implantação, validação e execução de pacotes.</span><span class="sxs-lookup"><span data-stu-id="0d3a7-103">Use the **Active Operations** dialog box to view the status of currently running [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, such as deployment, validation, and package execution.</span></span> <span data-ttu-id="0d3a7-104">Esses dados são armazenados no catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="0d3a7-104">This data is stored in the SSISDB catalog.</span></span>  
  
 <span data-ttu-id="0d3a7-105">Para obter mais informações sobre modos de exibição do [!INCLUDE[tsql](../includes/tsql-md.md)] relacionados, consulte [catalog.operations &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), e [catalog.executions &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span><span class="sxs-lookup"><span data-stu-id="0d3a7-105">For more information about related [!INCLUDE[tsql](../includes/tsql-md.md)] views, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), and [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span></span>  
  
 <span data-ttu-id="0d3a7-106">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="0d3a7-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="0d3a7-107">Abrir a caixa de diálogo operações ativas</span><span class="sxs-lookup"><span data-stu-id="0d3a7-107">Open the Active Operations Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="0d3a7-108">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="0d3a7-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-active-operations-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="0d3a7-109">Abrir a caixa de diálogo Operações Ativas</span><span class="sxs-lookup"><span data-stu-id="0d3a7-109">Open the Active Operations Dialog Box</span></span>  
  
1.  <span data-ttu-id="0d3a7-110">Abra [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d3a7-110">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="0d3a7-111">Conectar-se ao Mecanismo de Banco de Dados do Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="0d3a7-111">Connect Microsoft SQL Server Database Engine</span></span>  
  
3.  <span data-ttu-id="0d3a7-112">No Pesquisador de Objetos, expanda o nó **Integration Services** , clique com o botão direito do mouse em **SSISDB**e clique em **Operações Ativas**.</span><span class="sxs-lookup"><span data-stu-id="0d3a7-112">In Object Explorer, expand the **Integration Services** node, right-click **SSISDB**, and then click **Active Operations**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="0d3a7-113">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="0d3a7-113">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="0d3a7-114">Opções</span><span class="sxs-lookup"><span data-stu-id="0d3a7-114">Options</span></span>  
 <span data-ttu-id="0d3a7-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0d3a7-115">**Type**</span></span>  
 <span data-ttu-id="0d3a7-116">Especifica o tipo de operação.</span><span class="sxs-lookup"><span data-stu-id="0d3a7-116">Specifies the type of operation.</span></span> <span data-ttu-id="0d3a7-117">A seguir estão os valores possíveis para o campo **Type** e os valores correspondentes na coluna operations_type da exibição TRANSACT-SQL `catalog.operations` .</span><span class="sxs-lookup"><span data-stu-id="0d3a7-117">The following are the possible values for the **Type** field and the corresponding values in the operations_type column of the Transact-SQL `catalog.operations` view.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d3a7-118">Inicialização do Integration Services</span><span class="sxs-lookup"><span data-stu-id="0d3a7-118">Integration Services initialization</span></span>|<span data-ttu-id="0d3a7-119">1</span><span class="sxs-lookup"><span data-stu-id="0d3a7-119">1</span></span>|  
|<span data-ttu-id="0d3a7-120">Limpeza de operações (trabalho do SQL Agent)</span><span class="sxs-lookup"><span data-stu-id="0d3a7-120">Operations cleanup (SQL Agent job)</span></span>|<span data-ttu-id="0d3a7-121">2</span><span class="sxs-lookup"><span data-stu-id="0d3a7-121">2</span></span>|  
|<span data-ttu-id="0d3a7-122">Limpeza de versões do projeto (trabalho do SQL Agent)</span><span class="sxs-lookup"><span data-stu-id="0d3a7-122">Project versions cleanup (SQL Agent job)</span></span>|<span data-ttu-id="0d3a7-123">3</span><span class="sxs-lookup"><span data-stu-id="0d3a7-123">3</span></span>|  
|<span data-ttu-id="0d3a7-124">Implantar projeto</span><span class="sxs-lookup"><span data-stu-id="0d3a7-124">Deploy project</span></span>|<span data-ttu-id="0d3a7-125">101</span><span class="sxs-lookup"><span data-stu-id="0d3a7-125">101</span></span>|  
|<span data-ttu-id="0d3a7-126">Restaurar projeto</span><span class="sxs-lookup"><span data-stu-id="0d3a7-126">Restore project</span></span>|<span data-ttu-id="0d3a7-127">106</span><span class="sxs-lookup"><span data-stu-id="0d3a7-127">106</span></span>|  
|<span data-ttu-id="0d3a7-128">Criar e iniciar execução de pacote</span><span class="sxs-lookup"><span data-stu-id="0d3a7-128">Create and start package execution</span></span>|<span data-ttu-id="0d3a7-129">200</span><span class="sxs-lookup"><span data-stu-id="0d3a7-129">200</span></span>|  
|<span data-ttu-id="0d3a7-130">Parar operação (parando uma validação ou execução</span><span class="sxs-lookup"><span data-stu-id="0d3a7-130">Stop operation (stopping a validation or execution</span></span>|<span data-ttu-id="0d3a7-131">202</span><span class="sxs-lookup"><span data-stu-id="0d3a7-131">202</span></span>|  
|<span data-ttu-id="0d3a7-132">Validar projeto</span><span class="sxs-lookup"><span data-stu-id="0d3a7-132">Validate project</span></span>|<span data-ttu-id="0d3a7-133">300</span><span class="sxs-lookup"><span data-stu-id="0d3a7-133">300</span></span>|  
|<span data-ttu-id="0d3a7-134">Validar pacote</span><span class="sxs-lookup"><span data-stu-id="0d3a7-134">Validate package</span></span>|<span data-ttu-id="0d3a7-135">301</span><span class="sxs-lookup"><span data-stu-id="0d3a7-135">301</span></span>|  
|<span data-ttu-id="0d3a7-136">Configurar catálogo</span><span class="sxs-lookup"><span data-stu-id="0d3a7-136">Configure catalog</span></span>|<span data-ttu-id="0d3a7-137">1000</span><span class="sxs-lookup"><span data-stu-id="0d3a7-137">1000</span></span>|  
  
 <span data-ttu-id="0d3a7-138">**Parar**</span><span class="sxs-lookup"><span data-stu-id="0d3a7-138">**Stop**</span></span>  
 <span data-ttu-id="0d3a7-139">Clique para parar uma operação em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="0d3a7-139">Click to stop a currently running operation.</span></span>  
  
  
