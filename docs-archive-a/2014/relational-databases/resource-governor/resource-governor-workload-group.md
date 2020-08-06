---
title: Grupo de carga de trabalho do Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group
- workload groups [SQL Server]
- workload groups [SQL Server], overview
ms.assetid: a84c3c3f-55b6-4a30-9c42-13f082d9281e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c6fa8f6fe960571f10d6a8505329fbe8f400e6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680345"
---
# <a name="resource-governor-workload-group"></a><span data-ttu-id="0aaaf-102">Grupos de carga de trabalho do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="0aaaf-102">Resource Governor Workload Group</span></span>
  <span data-ttu-id="0aaaf-103">No Administrador de Recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o grupo de carga de trabalho funciona como um contêiner para as solicitações de sessão que têm critérios de classificação similares.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-103">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resource Governor, a workload group serves as a container for session requests that have similar classification criteria.</span></span> <span data-ttu-id="0aaaf-104">Uma carga de trabalho permite o monitoramento de agregação de sessões e define políticas para as sessões.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-104">A workload allows for aggregate monitoring of the sessions, and defines policies for the sessions.</span></span> <span data-ttu-id="0aaaf-105">Cada grupo de carga de trabalho está em um pool de recursos, que representa um subconjunto dos recursos físicos de uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0aaaf-105">Each workload group is in a resource pool, which represents a subset of the physical resources of an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="0aaaf-106">Quando uma sessão é iniciada, o classificador do Administrador de Recursos atribui a sessão a um grupo de carga de trabalho específico e a sessão deve ser executada, usando as políticas atribuídas ao grupo de carga de trabalho e os recursos definidos para o pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-106">When a session is started, the Resource Governor classifier assigns the session to a specific workload group, and the session must run using the policies assigned to the workload group and the resources defined for the resource pool.</span></span>  
  
## <a name="workload-group-concepts"></a><span data-ttu-id="0aaaf-107">Conceitos do grupo de cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="0aaaf-107">Workload Group Concepts</span></span>  
 <span data-ttu-id="0aaaf-108">O grupo de cargas de trabalho funciona como um contêiner para as solicitações de sessão similares, de acordo com os critérios de classificação aplicados a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-108">A workload group serves as a container for session requests that are similar according to the classification criteria that are applied to each request.</span></span> <span data-ttu-id="0aaaf-109">O grupo de carga de trabalho permite o monitoramento agregado do consumo de recursos e a aplicação de uma política uniforme para todas as solicitações no grupo.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-109">A workload group allows the aggregate monitoring of resource consumption and the application of a uniform policy to all the requests in the group.</span></span> <span data-ttu-id="0aaaf-110">Um grupo define as políticas para seus membros.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-110">A group defines the policies for its members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0aaaf-111">Os grupos de carga de trabalho definidos pelo usuário podem ser movidos de um pool de recursos para outro.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-111">User-defined workload groups can be moved from one resource pool to another.</span></span>  
  
 <span data-ttu-id="0aaaf-112">O Administrador de Recursos predefine dois grupos de carga de trabalho: o grupo interno e o padrão.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-112">Resource Governor predefines two workload groups: the internal group and the default group.</span></span> <span data-ttu-id="0aaaf-113">Um usuário não pode alterar nada que esteja classificado como grupo interno, mas pode fazer o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-113">A user cannot change anything classified as an internal group, but can monitor it.</span></span> <span data-ttu-id="0aaaf-114">As solicitações são classificadas no grupo padrão quando existem as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="0aaaf-114">Requests are classified into the default group when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="0aaaf-115">Não há nenhum critério para classificar uma solicitação.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-115">There are no criteria to classify a request.</span></span>  
  
-   <span data-ttu-id="0aaaf-116">Há uma tentativa de classificar a solicitação em um grupo inexistente.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-116">There is an attempt to classify the request into a non-existent group.</span></span>  
  
-   <span data-ttu-id="0aaaf-117">Há uma falha de classificação geral.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-117">There is a general classification failure.</span></span>  
  
 <span data-ttu-id="0aaaf-118">O Administrador de Recursos também fornece instruções DDL para criar, alterar e descartar grupos de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-118">Resource Governor also provides DDL statements for creating, changing, and dropping workload groups.</span></span>  
  
## <a name="workload-group-tasks"></a><span data-ttu-id="0aaaf-119">Tarefas do grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="0aaaf-119">Workload Group Tasks</span></span>  
  
|<span data-ttu-id="0aaaf-120">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="0aaaf-120">Task Description</span></span>|<span data-ttu-id="0aaaf-121">Tópico</span><span class="sxs-lookup"><span data-stu-id="0aaaf-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="0aaaf-122">Descreve como criar um grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-122">Describes how to create a workload group.</span></span>|[<span data-ttu-id="0aaaf-123">Criar um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="0aaaf-123">Create a Workload Group</span></span>](create-a-workload-group.md)|  
|<span data-ttu-id="0aaaf-124">Descreve como alterar as configurações de um grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-124">Describes how to change workload group settings.</span></span>|[<span data-ttu-id="0aaaf-125">Alterar as configurações do grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="0aaaf-125">Change Workload Group Settings</span></span>](change-workload-group-settings.md)|  
|<span data-ttu-id="0aaaf-126">Descreve como excluir um grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0aaaf-126">Describes how to delete a workload group.</span></span>|[<span data-ttu-id="0aaaf-127">Excluir um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="0aaaf-127">Delete a Workload Group</span></span>](delete-a-workload-group.md)|  
  
## <a name="see-also"></a><span data-ttu-id="0aaaf-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0aaaf-128">See Also</span></span>  
 <span data-ttu-id="0aaaf-129">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="0aaaf-129">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="0aaaf-130">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="0aaaf-130">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="0aaaf-131">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="0aaaf-131">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="0aaaf-132">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="0aaaf-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="0aaaf-133">[Configurar o administrador de recursos usando um modelo](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="0aaaf-133">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="0aaaf-134">Exibir Propriedades do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="0aaaf-134">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
