---
title: Página validação (assistentes do grupo de disponibilidade AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f2010074a357932f8af7358a05ee6ed16f5c0881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569666"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a><span data-ttu-id="0ad59-102">Página de Validação (Assistentes de Grupo de Disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="0ad59-102">Validation Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="0ad59-103">Este tópico da ajuda descreve as opções da página **Validação** .</span><span class="sxs-lookup"><span data-stu-id="0ad59-103">This help topic describes the options of the **Validation** page.</span></span> <span data-ttu-id="0ad59-104">Este tópico aplica-se ao [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], ao [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)]e ao [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ad59-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="0ad59-105">Use esta página para validar se o ambiente dá suporte a todas as opções de configuração feitas nas páginas anteriores do assistente.</span><span class="sxs-lookup"><span data-stu-id="0ad59-105">Use this page to validate that your environment supports all the configuration choices you made on previous pages of the wizard.</span></span>  
  
##  <a name="validation-page-options"></a><a name="PageOptions"></a><span data-ttu-id="0ad59-106">Opções de página de validação</span><span class="sxs-lookup"><span data-stu-id="0ad59-106">Validation Page Options</span></span>  
 <span data-ttu-id="0ad59-107">**Resultados da validação de grupo de disponibilidade.**</span><span class="sxs-lookup"><span data-stu-id="0ad59-107">**Results of availability group validation.**</span></span>  
 <span data-ttu-id="0ad59-108">Esta grade exibe os resultados de cada etapa de validação concluída.</span><span class="sxs-lookup"><span data-stu-id="0ad59-108">This grid displays the results of each completed validation step.</span></span> <span data-ttu-id="0ad59-109">As colunas da grade são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="0ad59-109">The grid columns are as follows:</span></span>  
  
 <span data-ttu-id="0ad59-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0ad59-110">**Name**</span></span>  
 <span data-ttu-id="0ad59-111">Exibe uma frase que descreve uma etapa específica.</span><span class="sxs-lookup"><span data-stu-id="0ad59-111">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="0ad59-112">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="0ad59-112">**Result**</span></span>  
 <span data-ttu-id="0ad59-113">Exibe um dos seguintes textos de hiperlink.</span><span class="sxs-lookup"><span data-stu-id="0ad59-113">Displays one of the following hyperlink texts.</span></span> <span data-ttu-id="0ad59-114">Para obter mais informações sobre o resultado de determinada etapa de validação, clique no hiperlink.</span><span class="sxs-lookup"><span data-stu-id="0ad59-114">For more information about the result of given validation step, click the hyperlink.</span></span>  
  
|<span data-ttu-id="0ad59-115">Result</span><span class="sxs-lookup"><span data-stu-id="0ad59-115">Result</span></span>|<span data-ttu-id="0ad59-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ad59-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0ad59-117">**Erro**</span><span class="sxs-lookup"><span data-stu-id="0ad59-117">**Error**</span></span>|<span data-ttu-id="0ad59-118">Indica se houve falha na etapa de validação.</span><span class="sxs-lookup"><span data-stu-id="0ad59-118">Indicates that the validation step failed.</span></span> <span data-ttu-id="0ad59-119">Clique no link para exibir a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="0ad59-119">Click the link to view the error message.</span></span>|  
|<span data-ttu-id="0ad59-120">**Ignorado**</span><span class="sxs-lookup"><span data-stu-id="0ad59-120">**Skipped**</span></span>|<span data-ttu-id="0ad59-121">Indica que a etapa de validação foi ignorada porque não é necessária por suas seleções.</span><span class="sxs-lookup"><span data-stu-id="0ad59-121">Indicates that the validation step was skipped because it is not required by your selections.</span></span> <span data-ttu-id="0ad59-122">Clique no link para exibir o motivo pelo qual uma etapa foi ignorada.</span><span class="sxs-lookup"><span data-stu-id="0ad59-122">Click the link to view the reason that a step was skipped.</span></span>|  
|<span data-ttu-id="0ad59-123">**Êxito**</span><span class="sxs-lookup"><span data-stu-id="0ad59-123">**Success**</span></span>|<span data-ttu-id="0ad59-124">Indica que a etapa de validação foi concluída com êxito</span><span class="sxs-lookup"><span data-stu-id="0ad59-124">Indicates that the validation step completed successfully</span></span>|  
|<span data-ttu-id="0ad59-125">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="0ad59-125">**Warning**</span></span>|<span data-ttu-id="0ad59-126">Indica um problema potencial com a configuração do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="0ad59-126">Indicates a potential issue with the availability group configuration.</span></span>  <span data-ttu-id="0ad59-127">Clique no link para exibir a mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="0ad59-127">Click the link to view the warning message.</span></span>|  
  
 <span data-ttu-id="0ad59-128">**Executar Novamente a Validação**</span><span class="sxs-lookup"><span data-stu-id="0ad59-128">**Re-run Validation**</span></span>  
 <span data-ttu-id="0ad59-129">Clique para repetir as etapas da validação se você fizer uma alteração fora do assistente em resposta a um erro de validação.</span><span class="sxs-lookup"><span data-stu-id="0ad59-129">Click to repeat the validation steps if you make a change outside of the wizard in response to a validation error.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0ad59-130">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0ad59-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0ad59-131">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0ad59-131">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0ad59-132">Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0ad59-132">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0ad59-133">Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0ad59-133">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="0ad59-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ad59-134">See Also</span></span>  
 [<span data-ttu-id="0ad59-135">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ad59-135">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
