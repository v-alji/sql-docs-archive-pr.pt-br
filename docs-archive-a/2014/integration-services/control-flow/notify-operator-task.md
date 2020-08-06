---
title: Tarefa Notificar Operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.notifyoperatortask.f1
helpviewer_keywords:
- Notify Operator task
- notifications [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 6c816c68-c6d6-44e4-bb34-c8e060a958a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed5158a4ec5cfe8374fedbb2afbca1294b58f05e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685229"
---
# <a name="notify-operator-task"></a><span data-ttu-id="bcc39-102">Tarefa de Notificação do Operador</span><span class="sxs-lookup"><span data-stu-id="bcc39-102">Notify Operator Task</span></span>
  <span data-ttu-id="bcc39-103">A tarefa de Notificação do Operador envia mensagens de notificação aos operadores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="bcc39-103">The Notify Operator task sends notification messages to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operators.</span></span> <span data-ttu-id="bcc39-104">Um operador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é um alias para uma pessoa ou para grupo que pode receber notificações eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="bcc39-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator is an alias for a person or group that can receive electronic notifications.</span></span> <span data-ttu-id="bcc39-105">Para obter mais informações sobre operadores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [Operadores](../../ssms/agent//operators.md).</span><span class="sxs-lookup"><span data-stu-id="bcc39-105">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operators, see [Operators](../../ssms/agent//operators.md).</span></span>  
  
 <span data-ttu-id="bcc39-106">Ao usar a tarefa Notificar Operador, um pacote pode notificar um ou mais operadores usando email, pager ou **net send**.</span><span class="sxs-lookup"><span data-stu-id="bcc39-106">By using the Notify Operator task, a package can notify one or more operators via e-mail, pager, or **net send**.</span></span> <span data-ttu-id="bcc39-107">Cada operador pode ser notificado por métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="bcc39-107">Each operator can be notified by different methods.</span></span> <span data-ttu-id="bcc39-108">Por exemplo, OperatorA é notificado por email e pager, e OperatorB é notificado por pager e **net send**.</span><span class="sxs-lookup"><span data-stu-id="bcc39-108">For example, OperatorA is notified by e-mail and pager, and OperatorB is notified by pager and **net send**.</span></span> <span data-ttu-id="bcc39-109">Os operadores que recebem notificações da tarefa devem ser membros da coleção **OperatorNotify** na tarefa de Notificação do Operador.</span><span class="sxs-lookup"><span data-stu-id="bcc39-109">The operators who receive notifications from the task must be members of the **OperatorNotify** collection on the Notify Operator task.</span></span>  
  
 <span data-ttu-id="bcc39-110">A tarefa de Notificar Operador é a única tarefa de manutenção de banco de dados que não encapsula uma instrução Transact-SQL ou um comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="bcc39-110">The Notify Operator task is the only database maintenance task that does not encapsulate a Transact-SQL statement or a DBCC command.</span></span>  
  
## <a name="configuration-of-the-notify-operator-task"></a><span data-ttu-id="bcc39-111">Configuração da tarefa Notificar Operador</span><span class="sxs-lookup"><span data-stu-id="bcc39-111">Configuration of the Notify Operator Task</span></span>  
 <span data-ttu-id="bcc39-112">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="bcc39-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="bcc39-113">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bcc39-113">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="bcc39-114">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="bcc39-114">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="bcc39-115">Tarefa Notificar Operador &#40;Plano de manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="bcc39-115">Notify Operator Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/notify-operator-task-maintenance-plan.md)  
  
 <span data-ttu-id="bcc39-116">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="bcc39-116">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="bcc39-117">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="bcc39-117">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
