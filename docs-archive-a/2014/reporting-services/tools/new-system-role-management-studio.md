---
title: Nova Função de Sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680784"
---
# <a name="new-system-role-management-studio"></a><span data-ttu-id="9df52-102">Nova Função do Sistema (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9df52-102">New System Role (Management Studio)</span></span>
  <span data-ttu-id="9df52-103">Use essa página para criar uma definição de função de nível de sistema.</span><span class="sxs-lookup"><span data-stu-id="9df52-103">Use this page to create a system-level role definition.</span></span> <span data-ttu-id="9df52-104">Uma definição de função de sistema especifica um conjunto de tarefas de nível de sistema que se aplica a um servidor de relatório como um todo.</span><span class="sxs-lookup"><span data-stu-id="9df52-104">A system role definition specifies a set of system-level tasks that apply to a report server as whole.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9df52-105">Definições de função só são usadas em um servidor de relatório que executa em modo nativo.</span><span class="sxs-lookup"><span data-stu-id="9df52-105">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="9df52-106">Se o servidor de relatório for configurado para integração do SharePoint, essa página não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="9df52-106">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9df52-107">Opções</span><span class="sxs-lookup"><span data-stu-id="9df52-107">Options</span></span>  
 <span data-ttu-id="9df52-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9df52-108">**Name**</span></span>  
 <span data-ttu-id="9df52-109">Digite o nome da definição da função.</span><span class="sxs-lookup"><span data-stu-id="9df52-109">Type the name of the role definition.</span></span> <span data-ttu-id="9df52-110">O nome de definição de função deve ser exclusivo no namespace do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9df52-110">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="9df52-111">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="9df52-111">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="9df52-112">Também pode conter espaços e alguns símbolos.</span><span class="sxs-lookup"><span data-stu-id="9df52-112">It can also include spaces and some symbols.</span></span> <span data-ttu-id="9df52-113">Não use os seguintes caracteres ao especificar um nome:</span><span class="sxs-lookup"><span data-stu-id="9df52-113">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="9df52-114">; ?</span><span class="sxs-lookup"><span data-stu-id="9df52-114">; ?</span></span> <span data-ttu-id="9df52-115">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="9df52-115">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="9df52-116">" /</span><span class="sxs-lookup"><span data-stu-id="9df52-116">" /</span></span>  
  
 <span data-ttu-id="9df52-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9df52-117">**Description**</span></span>  
 <span data-ttu-id="9df52-118">Fornece uma descrição que explica como usar a função e enumera a que a função dá suporte.</span><span class="sxs-lookup"><span data-stu-id="9df52-118">Provide a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="9df52-119">**Tarefa**</span><span class="sxs-lookup"><span data-stu-id="9df52-119">**Task**</span></span>  
 <span data-ttu-id="9df52-120">Selecione as tarefas de nível de sistema que podem ser executadas por essa função.</span><span class="sxs-lookup"><span data-stu-id="9df52-120">Select the system-level tasks that can be performed through this role.</span></span> <span data-ttu-id="9df52-121">Você não pode criar tarefas novas ou modificar as tarefas existentes compatíveis com o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9df52-121">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9df52-122">Você não pode escolher tarefas de nível de item para uma definição de função do sistema.</span><span class="sxs-lookup"><span data-stu-id="9df52-122">You cannot choose item-level tasks for a system role definition.</span></span>  
  
 <span data-ttu-id="9df52-123">**Descrição da tarefa**</span><span class="sxs-lookup"><span data-stu-id="9df52-123">**Task Description**</span></span>  
 <span data-ttu-id="9df52-124">Exibe uma descrição de tarefa que enumera as operações ou permissões às quais a tarefa dá suporte.</span><span class="sxs-lookup"><span data-stu-id="9df52-124">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df52-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9df52-125">See Also</span></span>  
 <span data-ttu-id="9df52-126">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9df52-126">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="9df52-127">Definições de função</span><span class="sxs-lookup"><span data-stu-id="9df52-127">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
