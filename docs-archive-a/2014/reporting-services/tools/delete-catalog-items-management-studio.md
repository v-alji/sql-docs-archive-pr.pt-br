---
title: Excluir itens de catálogo (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d2a1824f2611165c9ae891fcb702418244f3621e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572938"
---
# <a name="delete-catalog-items-management-studio"></a><span data-ttu-id="659a3-102">Excluir itens do catálogo (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="659a3-102">Delete Catalog Items (Management Studio)</span></span>
  <span data-ttu-id="659a3-103">Use essa página para excluir agendas compartilhadas e definições de função.</span><span class="sxs-lookup"><span data-stu-id="659a3-103">Use this page to delete shared schedules and role definitions.</span></span>  
  
 <span data-ttu-id="659a3-104">Se uma agenda compartilhada usada por vários relatórios e assinaturas for excluída, o servidor de relatório criará agendas individuais para cada relatório e assinatura que usou anteriormente a agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="659a3-104">If you delete a shared schedule that is used by multiple reports and subscriptions, the report server will create individual schedules for each report and subscription that previously used the shared schedule.</span></span> <span data-ttu-id="659a3-105">Cada nova agenda individual conterá a data, a hora e o padrão de recorrência que foram especificados na agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="659a3-105">Each new individual schedule will contain the date, time, and recurrence pattern that was specified in the shared schedule.</span></span> <span data-ttu-id="659a3-106">Observe que o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não fornece o gerenciamento central de agendas individuais.</span><span class="sxs-lookup"><span data-stu-id="659a3-106">Note that [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide central management of individual schedules.</span></span> <span data-ttu-id="659a3-107">Se você excluir uma agenda compartilhada, deverá manter as informações de agenda para cada item individual.</span><span class="sxs-lookup"><span data-stu-id="659a3-107">If you delete a shared schedule, you will now need to maintain the schedule information for each individual item.</span></span> <span data-ttu-id="659a3-108">Antes de excluir uma agenda compartilhada, use a [página Relatórios](schedule-properties-reports-page.md) para determinar quais relatórios estão usando a agenda compartilhada atualmente.</span><span class="sxs-lookup"><span data-stu-id="659a3-108">Before deleting a shared schedule, use the [Reports page](schedule-properties-reports-page.md) to determine which reports are currently using the shared schedule.</span></span>  
  
 <span data-ttu-id="659a3-109">Para definições de função, você só pode excluir os que não são usados ativamente em uma atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="659a3-109">For role definitions, you can only delete those that are not actively used in a role assignment.</span></span> <span data-ttu-id="659a3-110">Se você tentar excluir uma função atualmente em uso, o servidor de relatório não excluirá a função e uma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="659a3-110">If you try to delete a role that is currently in use, the report server will not delete the role and you will see an error message to that effect.</span></span> <span data-ttu-id="659a3-111">Se a página contiver uma única definição de função que não está atualmente em uso, ela será excluída quando você clicar em **OK**.</span><span class="sxs-lookup"><span data-stu-id="659a3-111">If this page contains a single role definition that is not currently in use, it will be deleted when you click **OK**.</span></span> <span data-ttu-id="659a3-112">Se esta página contiver várias funções, você não poderá selecionar quais funções serão mantidas ou removidas.</span><span class="sxs-lookup"><span data-stu-id="659a3-112">If this page contains multiple roles, you cannot select which roles to keep or remove.</span></span> <span data-ttu-id="659a3-113">Todas as definições de função não usadas serão excluídas quando você clicar em **OK**.</span><span class="sxs-lookup"><span data-stu-id="659a3-113">All unused role definitions will be deleted when you click **OK**.</span></span>  
  
 <span data-ttu-id="659a3-114">Uma operação de exclusão não pode ser desfeita.</span><span class="sxs-lookup"><span data-stu-id="659a3-114">You cannot undo a delete operation.</span></span> <span data-ttu-id="659a3-115">Para recuperar um item excluído, recrie-o ou restaure uma cópia de backup do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="659a3-115">If you want to recover an item that you deleted, you must either recreate it or restore a backup copy of the report server database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="659a3-116">Opções</span><span class="sxs-lookup"><span data-stu-id="659a3-116">Options</span></span>  
 <span data-ttu-id="659a3-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="659a3-117">**Name**</span></span>  
 <span data-ttu-id="659a3-118">Especifica o nome do item que você está excluindo.</span><span class="sxs-lookup"><span data-stu-id="659a3-118">Specifies the name of the item you are deleting.</span></span>  
  
 <span data-ttu-id="659a3-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="659a3-119">**Type**</span></span>  
 <span data-ttu-id="659a3-120">Exibe o tipo de item que você está excluindo.</span><span class="sxs-lookup"><span data-stu-id="659a3-120">Shows the type of item you are deleting.</span></span>  
  
 <span data-ttu-id="659a3-121">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="659a3-121">**Owner**</span></span>  
 <span data-ttu-id="659a3-122">Exibe o nome do proprietário.</span><span class="sxs-lookup"><span data-stu-id="659a3-122">Shows the name of the owner.</span></span> <span data-ttu-id="659a3-123">Na maioria dos casos é o Sistema.</span><span class="sxs-lookup"><span data-stu-id="659a3-123">In most cases, this is System.</span></span>  
  
 <span data-ttu-id="659a3-124">**Status**</span><span class="sxs-lookup"><span data-stu-id="659a3-124">**Status**</span></span>  
 <span data-ttu-id="659a3-125">Exibe informações de andamento de uma operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="659a3-125">Shows progress information for a delete operation.</span></span>  
  
 <span data-ttu-id="659a3-126">**Erro**</span><span class="sxs-lookup"><span data-stu-id="659a3-126">**Error**</span></span>  
 <span data-ttu-id="659a3-127">Exibe um código de erro se um erro ocorrer durante a exclusão de um item.</span><span class="sxs-lookup"><span data-stu-id="659a3-127">Displays an error code if an error occurs while deleting an item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659a3-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="659a3-128">See Also</span></span>  
 <span data-ttu-id="659a3-129">[Excluir um item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="659a3-129">[Delete an Item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span></span>  
 <span data-ttu-id="659a3-130">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="659a3-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="659a3-131">Criar, modificar e excluir agendas</span><span class="sxs-lookup"><span data-stu-id="659a3-131">Create, Modify, and Delete Schedules</span></span>](../subscriptions/create-modify-and-delete-schedules.md)  
  
  
