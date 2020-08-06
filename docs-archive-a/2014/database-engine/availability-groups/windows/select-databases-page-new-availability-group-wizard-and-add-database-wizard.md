---
title: Página Selecionar bancos de dados (Assistente de novo grupo de disponibilidade-assistente para adicionar banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c626b8f0953f18a6dd4661124a09b7f542caeb82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684912"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a><span data-ttu-id="47769-102">Página Selecionar bancos de dados (Assistente de novo grupo de disponibilidade-assistente para adicionar banco de dados)</span><span class="sxs-lookup"><span data-stu-id="47769-102">Select Databases Page (New Availability Group Wizard-Add Database Wizard)</span></span>
  <span data-ttu-id="47769-103"> Este tópico descreve as opções da página **Especificar Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="47769-103">This help topic describes the options of the **Specify Databases** page.</span></span> <span data-ttu-id="47769-104">Este tópico aplica-se ao [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] e ao [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47769-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="select-databases-options"></a><a name="PageOptions"></a> <span data-ttu-id="47769-105">Selecionar opções de bancos de dados</span><span class="sxs-lookup"><span data-stu-id="47769-105">Select Databases Options</span></span>  
 <span data-ttu-id="47769-106">A grade **Bancos de dados de usuário nesta instância do SQL Server** lista todos os bancos de dados de usuário locais.</span><span class="sxs-lookup"><span data-stu-id="47769-106">The **User databases on this instance of SQL Server** grid lists every local user database.</span></span> <span data-ttu-id="47769-107">As colunas são apresentadas assim:</span><span class="sxs-lookup"><span data-stu-id="47769-107">The columns are as follows:</span></span>  
  
 <span data-ttu-id="47769-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="47769-108">**Name**</span></span>  
 <span data-ttu-id="47769-109">Exibe o nome do banco de dados de usuário local.</span><span class="sxs-lookup"><span data-stu-id="47769-109">Displays the name of a local user database.</span></span>  
  
 <span data-ttu-id="47769-110">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="47769-110">**Size**</span></span>  
 <span data-ttu-id="47769-111">Exibe o tamanho do banco de dados, se o tamanho estiver disponível para o assistente.</span><span class="sxs-lookup"><span data-stu-id="47769-111">Displays the database size, if the size is available to the wizard.</span></span>  
  
 <span data-ttu-id="47769-112">**Status**</span><span class="sxs-lookup"><span data-stu-id="47769-112">**Status**</span></span>  
 <span data-ttu-id="47769-113">Exibe um hiperlink cujo texto indica se um determinado banco de dados atende aos pré-requisitos para ser adicionado a um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="47769-113">Displays a hyperlink whose text that indicates whether a given database meets the prerequisites for being added to an availability group.</span></span> <span data-ttu-id="47769-114">Se o status for "**Atende pré-requisitos**" você poderá adicionar o banco de dados ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="47769-114">If the status is "**Meets prerequisites**" you can add the database to the availability group.</span></span> <span data-ttu-id="47769-115">Se um banco de dados não atender a todos os pré-requisitos, o hiperlink **Status** fornecerá uma breve explicação de por que o banco de dados não está qualificado.</span><span class="sxs-lookup"><span data-stu-id="47769-115">If a database does not meet all of the prerequisites, the **Status** hyperlink provides a brief explanation of why the database is ineligible.</span></span> <span data-ttu-id="47769-116">Para obter mais informações, clique no hiperlink.</span><span class="sxs-lookup"><span data-stu-id="47769-116">For more information, click the hyperlink.</span></span>  
  
 <span data-ttu-id="47769-117">Você pode deixar o assistente na página **Selecionar Banco de Dados** enquanto executa ações em um banco de dados para atender a um pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="47769-117">You can leave the wizard on the **Select Database** page while you take action on a database to meet a prerequisite.</span></span> <span data-ttu-id="47769-118">Ao retornar à página **Selecionar Bancos de Dados** , clique em **Atualizar** para atualizar a grade.</span><span class="sxs-lookup"><span data-stu-id="47769-118">When you return to the **Select Databases** page, click **Refresh** to update the grid.</span></span>  
  
 <span data-ttu-id="47769-119">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="47769-119">**Refresh**</span></span>  
 <span data-ttu-id="47769-120">Clique para atualizar a grade.</span><span class="sxs-lookup"><span data-stu-id="47769-120">Click to refresh the grid.</span></span> <span data-ttu-id="47769-121">Isso é útil depois que você executa uma ação em um banco de dados para atender a um pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="47769-121">This is useful after you take action on a database to meet a prerequisite.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="47769-122">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="47769-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="47769-123">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="47769-123">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="47769-124">Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="47769-124">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="47769-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47769-125">See Also</span></span>  
 <span data-ttu-id="47769-126">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="47769-126">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="47769-127">Pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="47769-127">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
