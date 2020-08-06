---
title: 'Propriedades do trabalho: novo trabalho (página notificações) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569804"
---
# <a name="job-properties-new-job-notifications-page"></a><span data-ttu-id="fd1da-102">Propriedades do Trabalho: Novo Trabalho (página Notificações)</span><span class="sxs-lookup"><span data-stu-id="fd1da-102">Job Properties: New Job (Notifications Page)</span></span>
  <span data-ttu-id="fd1da-103">Use esta página para definir ações para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executar quando o trabalho for concluído.</span><span class="sxs-lookup"><span data-stu-id="fd1da-103">Use this page to set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd1da-104">Opções</span><span class="sxs-lookup"><span data-stu-id="fd1da-104">Options</span></span>  
 <span data-ttu-id="fd1da-105">**Mensagens**</span><span class="sxs-lookup"><span data-stu-id="fd1da-105">**E-mail**</span></span>  
 <span data-ttu-id="fd1da-106">Selecione esta opção para enviar email quando o trabalho terminar.</span><span class="sxs-lookup"><span data-stu-id="fd1da-106">Select this option to send e-mail when the job completes.</span></span> <span data-ttu-id="fd1da-107">Após selecionar essa opção, escolha o operador a ser notificado, além das condições que dispararão a notificação: **Quando o trabalho for bem-sucedido**; **Quando ocorrer falha no trabalho**; ou **Quando o trabalho for concluído**.</span><span class="sxs-lookup"><span data-stu-id="fd1da-107">After selecting this option, choose the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="fd1da-108">**Página**</span><span class="sxs-lookup"><span data-stu-id="fd1da-108">**Page**</span></span>  
 <span data-ttu-id="fd1da-109">Selecione esta opção para enviar email ao pager de um operador quando o trabalho terminar.</span><span class="sxs-lookup"><span data-stu-id="fd1da-109">Select this option to send e-mail to an operator's pager when the job completes.</span></span> <span data-ttu-id="fd1da-110">Após selecionar essa opção, especifique o operador a ser notificado, além das condições que dispararão a notificação: **Quando o trabalho for bem-sucedido**; **Quando ocorrer falha no trabalho**; ou **Quando o trabalho for concluído**.</span><span class="sxs-lookup"><span data-stu-id="fd1da-110">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="fd1da-111">**Net send**</span><span class="sxs-lookup"><span data-stu-id="fd1da-111">**Net send**</span></span>  
 <span data-ttu-id="fd1da-112">Selecione esta opção para usar o net send para notificar um operador quando o trabalho terminar.</span><span class="sxs-lookup"><span data-stu-id="fd1da-112">Select this option to use net send to notify an operator when the job completes.</span></span> <span data-ttu-id="fd1da-113">Após selecionar essa opção, especifique o operador a ser notificado, além das condições que dispararão a notificação: **Quando o trabalho for bem-sucedido**; **Quando ocorrer falha no trabalho**; ou **Quando o trabalho for concluído**.</span><span class="sxs-lookup"><span data-stu-id="fd1da-113">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="fd1da-114">**Gravar no log de eventos de Aplicativo do Windows**</span><span class="sxs-lookup"><span data-stu-id="fd1da-114">**Write to the Windows Application event log**</span></span>  
 <span data-ttu-id="fd1da-115">Selecione esta opção para gravar uma entrada no log de eventos de aplicativo quando o trabalho terminar.</span><span class="sxs-lookup"><span data-stu-id="fd1da-115">Select this option to write an entry in the application event log when the job completes.</span></span> <span data-ttu-id="fd1da-116">Após selecionar essa opção, especifique a condição que fará com que a entrada seja gravada: **Quando o trabalho for bem-sucedido**; **Quando ocorrer falha no trabalho**; ou **Quando o trabalho for concluído**.</span><span class="sxs-lookup"><span data-stu-id="fd1da-116">After selecting this option, specify the condition that will cause the entry to be written: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="fd1da-117">**Excluir trabalho automaticamente**</span><span class="sxs-lookup"><span data-stu-id="fd1da-117">**Automatically delete job**</span></span>  
 <span data-ttu-id="fd1da-118">Selecione essa opção para excluir o trabalho quando ele terminar.</span><span class="sxs-lookup"><span data-stu-id="fd1da-118">Select this option to delete the job when the job completes.</span></span> <span data-ttu-id="fd1da-119">Após selecionar essa opção, especifique a condição que disparará a exclusão do trabalho: **Quando o trabalho for bem-sucedido**; **Quando ocorrer falha no trabalho**; ou **Quando o trabalho for concluído**.</span><span class="sxs-lookup"><span data-stu-id="fd1da-119">After selecting this option, specify the condition that will trigger deletion of the job: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1da-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd1da-120">See Also</span></span>  
 <span data-ttu-id="fd1da-121">[Implementar trabalhos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="fd1da-121">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="fd1da-122">Configurar o SQL Server Agent Mail para usar o Database Mail</span><span class="sxs-lookup"><span data-stu-id="fd1da-122">Configure SQL Server Agent Mail to Use Database Mail</span></span>](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
