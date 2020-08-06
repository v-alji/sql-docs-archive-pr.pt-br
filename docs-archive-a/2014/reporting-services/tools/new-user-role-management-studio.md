---
title: Nova Função de Usuário (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newrole.f1
ms.assetid: 9f76a235-0b58-479c-8e5b-50588091b71c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 78201c5ebedd0cdb7f8108b9e6effcaa7fbe87b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680783"
---
# <a name="new-user-role-management-studio"></a><span data-ttu-id="3b188-102">Nova função do usuário (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3b188-102">New User Role (Management Studio)</span></span>
  <span data-ttu-id="3b188-103">Use essa página para criar uma definição de função de nível de item.</span><span class="sxs-lookup"><span data-stu-id="3b188-103">Use this page to create an item-level role definition.</span></span> <span data-ttu-id="3b188-104">Uma definição de função de nível é uma coleção nomeada de tarefas que enumera as tarefas que um usuário pode executar em relação a pastas, relatórios, modelos, recursos e fontes de dados compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="3b188-104">An item-level role definition is a named collection of tasks that enumerate the tasks a user can perform in relation to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="3b188-105">Um exemplo de uma definição de função de nível de item é uma função de navegador predefinida que identifica os tipos de ações que um usuário final de relatório pode necessitar para navegar pelas pastas e exibir relatórios.</span><span class="sxs-lookup"><span data-stu-id="3b188-105">An example of an item-level role definition is the predefined Browser role that identifies the kinds of actions a report end user might require for navigating folders and viewing reports.</span></span>  
  
 <span data-ttu-id="3b188-106">As definições de função devem ser em baixo número.</span><span class="sxs-lookup"><span data-stu-id="3b188-106">Role definitions are intended to be few in number.</span></span> <span data-ttu-id="3b188-107">A maioria das organizações só requer algumas definições de função.</span><span class="sxs-lookup"><span data-stu-id="3b188-107">Most organizations only require a few role definitions.</span></span> <span data-ttu-id="3b188-108">Porém, se as definições de função predefinidas forem insuficientes, você poderá variá-las ou criar novas definições.</span><span class="sxs-lookup"><span data-stu-id="3b188-108">However, if the predefined role definitions are insufficient, you can vary them or create new ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b188-109">Definições de função só são usadas em um servidor de relatório que executa em modo nativo.</span><span class="sxs-lookup"><span data-stu-id="3b188-109">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="3b188-110">Se o servidor de relatório for configurado para integração do SharePoint, essa página não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="3b188-110">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b188-111">Opções</span><span class="sxs-lookup"><span data-stu-id="3b188-111">Options</span></span>  
 <span data-ttu-id="3b188-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3b188-112">**Name**</span></span>  
 <span data-ttu-id="3b188-113">Digite o nome da definição da função.</span><span class="sxs-lookup"><span data-stu-id="3b188-113">Type the name of the role definition.</span></span> <span data-ttu-id="3b188-114">O nome de definição de função deve ser exclusivo no namespace do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b188-114">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="3b188-115">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="3b188-115">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="3b188-116">Também pode conter espaços e alguns símbolos.</span><span class="sxs-lookup"><span data-stu-id="3b188-116">It can also include spaces and some symbols.</span></span> <span data-ttu-id="3b188-117">Não use os seguintes caracteres ao especificar um nome:</span><span class="sxs-lookup"><span data-stu-id="3b188-117">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="3b188-118">; ?</span><span class="sxs-lookup"><span data-stu-id="3b188-118">; ?</span></span> <span data-ttu-id="3b188-119">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="3b188-119">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="3b188-120">" /</span><span class="sxs-lookup"><span data-stu-id="3b188-120">" /</span></span>  
  
 <span data-ttu-id="3b188-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3b188-121">**Description**</span></span>  
 <span data-ttu-id="3b188-122">Digite uma descrição que explica como usar a função e enumera ao que ela oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="3b188-122">Type a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="3b188-123">**Tarefa**</span><span class="sxs-lookup"><span data-stu-id="3b188-123">**Task**</span></span>  
 <span data-ttu-id="3b188-124">Selecione as tarefas que podem ser executadas por essa função.</span><span class="sxs-lookup"><span data-stu-id="3b188-124">Select the tasks that can be performed through this role.</span></span> <span data-ttu-id="3b188-125">Você não pode criar tarefas novas ou modificar as tarefas existentes compatíveis com o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b188-125">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3b188-126">Somente tarefas do nível de item podem ser usadas em uma definição de função de nível de item.</span><span class="sxs-lookup"><span data-stu-id="3b188-126">Only item-level tasks can be used in an item-level role definition.</span></span>  
  
 <span data-ttu-id="3b188-127">**Descrição da tarefa**</span><span class="sxs-lookup"><span data-stu-id="3b188-127">**Task Description**</span></span>  
 <span data-ttu-id="3b188-128">Exibe uma descrição de tarefa que enumera as operações ou permissões às quais a tarefa dá suporte.</span><span class="sxs-lookup"><span data-stu-id="3b188-128">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b188-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b188-129">See Also</span></span>  
 <span data-ttu-id="3b188-130">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3b188-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="3b188-131">Definições de função</span><span class="sxs-lookup"><span data-stu-id="3b188-131">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
