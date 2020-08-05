---
title: Aplicativo sqlagent90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server Agent
- sqlagent90 application
- SQL Server Agent, starting
- command prompt utilities [SQL Server], sqlagent90
ms.assetid: e8b80e8d-d0c9-4500-a868-0ce08233da08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 290cb69f39aa3b08bb290c210b2d37977614a1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571728"
---
# <a name="sqlagent90-application"></a><span data-ttu-id="aa843-102">aplicativo sqlagent90</span><span class="sxs-lookup"><span data-stu-id="aa843-102">sqlagent90 Application</span></span>
  <span data-ttu-id="aa843-103">O aplicativo **sqlagent90** inicia o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="aa843-103">The **sqlagent90** application starts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from the command prompt.</span></span> <span data-ttu-id="aa843-104">Normalmente, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent deve ser executado no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou usando métodos SQL-SMO em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aa843-104">Usually, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should be run from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by using SQL-SMO methods in an application.</span></span> <span data-ttu-id="aa843-105">Execute o **sqlagent90** no prompt de comando apenas quando estiver diagnosticando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent ou quando for direcionado a ele por seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="aa843-105">Only run **sqlagent90** from the command prompt when you are diagnosing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, or when you are directed to it by your primary support provider.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa843-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa843-106">Syntax</span></span>  
  
```  
  
sqlagent90  
-c [-v] [-iinstance_name]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aa843-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aa843-107">Arguments</span></span>  
 <span data-ttu-id="aa843-108">**-c**</span><span class="sxs-lookup"><span data-stu-id="aa843-108">**-c**</span></span>  
 <span data-ttu-id="aa843-109">Indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent está sendo executado pelo prompt de comando e é independente do Gerenciador de Controle de Serviços do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="aa843-109">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is running from the command prompt and is independent of the Microsoft Windows Services Control Manager.</span></span> <span data-ttu-id="aa843-110">Quando **-c** é usado, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent não pode ser controlado no aplicativo de Serviços nas Ferramentas Administrativas nem no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="aa843-110">When **-c** is used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent cannot be controlled from either the Services application in Administrative Tools or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="aa843-111">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="aa843-111">This argument is mandatory.</span></span>  
  
 <span data-ttu-id="aa843-112">**-v**</span><span class="sxs-lookup"><span data-stu-id="aa843-112">**-v**</span></span>  
 <span data-ttu-id="aa843-113">Indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent é executado em modo detalhado e grava informações de diagnóstico na janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="aa843-113">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in verbose mode and writes diagnostic information to the command-prompt window.</span></span> <span data-ttu-id="aa843-114">As informações de diagnóstico são iguais às informações gravadas no log de erros do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="aa843-114">The diagnostic information is the same as the information written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log.</span></span>  
  
 <span data-ttu-id="aa843-115">**-i** *instance_name*</span><span class="sxs-lookup"><span data-stu-id="aa843-115">**-i** *instance_name*</span></span>  
 <span data-ttu-id="aa843-116">Indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent se conecta com a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nomeada especificada por *instance_name*.</span><span class="sxs-lookup"><span data-stu-id="aa843-116">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent connects to the named [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance specified by *instance_name*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa843-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="aa843-117">Remarks</span></span>  
 <span data-ttu-id="aa843-118">Depois de exibir uma mensagem de direitos autorais, o **sqlagent90** exibe a saída na janela de prompt de comando somente quando a opção **-v** é especificada.</span><span class="sxs-lookup"><span data-stu-id="aa843-118">After displaying a copyright message, **sqlagent90** displays output in the command prompt window only when the **-v** switch is specified.</span></span> <span data-ttu-id="aa843-119">Para interromper o **sqlagent90**, pressione CTRL+C no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="aa843-119">To stop **sqlagent90**, press CTRL+C at the command prompt.</span></span> <span data-ttu-id="aa843-120">Não feche a janela do prompt de comando antes de interromper o **sqlagent90**.</span><span class="sxs-lookup"><span data-stu-id="aa843-120">Do not close the command-prompt window before stopping **sqlagent90**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa843-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa843-121">See Also</span></span>  
 [<span data-ttu-id="aa843-122">Tarefas de administração automatizadas &#40;SQL Server Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="aa843-122">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../ssms/agent/automated-administration-tasks-sql-server-agent.md)  
  
  
