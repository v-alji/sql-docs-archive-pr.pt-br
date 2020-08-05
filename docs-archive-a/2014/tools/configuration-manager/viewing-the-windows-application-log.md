---
title: Exibindo o Log de aplicativo do Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22f900a0b203e652bbc9cc6e9638711d138756c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573332"
---
# <a name="viewing-the-windows-application-log"></a><span data-ttu-id="8250a-102">Exibindo o log do aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="8250a-102">Viewing the Windows Application Log</span></span>
  <span data-ttu-id="8250a-103">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é configurado para usar o log do aplicativo do Microsoft Windows, cada sessão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] grava novos eventos nesse log.</span><span class="sxs-lookup"><span data-stu-id="8250a-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Microsoft Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="8250a-104">Ao contrário do log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , não é criado um novo log de aplicativos cada vez que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]é iniciada.</span><span class="sxs-lookup"><span data-stu-id="8250a-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8250a-105">Exiba e gerencie o log do aplicativo do Windows usando Visualizador de Eventos do Windows ou o Visualizador de Log no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8250a-105">View and manage the Windows application log by using Windows Event Viewer or the Log Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8250a-106">Há três logs que podem ser exibidos com Visualizador de Eventos.</span><span class="sxs-lookup"><span data-stu-id="8250a-106">There are three logs that can be viewed with Event Viewer.</span></span>  
  
|<span data-ttu-id="8250a-107">Tipo de log do Windows</span><span class="sxs-lookup"><span data-stu-id="8250a-107">Windows log type</span></span>|<span data-ttu-id="8250a-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8250a-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="8250a-109">Log do sistema</span><span class="sxs-lookup"><span data-stu-id="8250a-109">System log</span></span>|<span data-ttu-id="8250a-110">Registra eventos registrados pelos componentes do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="8250a-110">Records events logged by the Windows operating system components.</span></span> <span data-ttu-id="8250a-111">Por exemplo, a falha de um driver ou de outro componente do sistema carregados durante a inicialização é gravada no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="8250a-111">For example, the failure of a driver or other system component to load during startup is recorded in the system log.</span></span>|  
|<span data-ttu-id="8250a-112">Log de segurança</span><span class="sxs-lookup"><span data-stu-id="8250a-112">Security log</span></span>|<span data-ttu-id="8250a-113">Registra eventos de segurança, como tentativas de logon com falha.</span><span class="sxs-lookup"><span data-stu-id="8250a-113">Records security events, such as failed login attempts.</span></span> <span data-ttu-id="8250a-114">Também ajuda a localizar alterações no sistema de segurança e a identificar possíveis violações de segurança.</span><span class="sxs-lookup"><span data-stu-id="8250a-114">This helps track changes to the security system and identify possible breaches to security.</span></span> <span data-ttu-id="8250a-115">Por exemplo, tentativas de logon no sistema podem ser gravadas no log de segurança, dependendo das definições de auditoria no Gerenciador de Usuários.</span><span class="sxs-lookup"><span data-stu-id="8250a-115">For example, attempts to log on to the system may be recorded in the security log, depending on the audit settings in the User Manager.</span></span><br /><br /> <span data-ttu-id="8250a-116">Somente os membros da função de servidor fixa **sysadmin** podem exibir os logs de segurança.</span><span class="sxs-lookup"><span data-stu-id="8250a-116">Only members of the **sysadmin** fixed server role can view the security log.</span></span>|  
|<span data-ttu-id="8250a-117">Log do aplicativo</span><span class="sxs-lookup"><span data-stu-id="8250a-117">Application log</span></span>|<span data-ttu-id="8250a-118">Registra eventos que são registrados através de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8250a-118">Records events that are logged by applications.</span></span> <span data-ttu-id="8250a-119">Por exemplo, um aplicativo de banco de dados poderia registrar um erro de arquivo no log do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8250a-119">For example, a database application might record a file error in the application log.</span></span>|  
  
 <span data-ttu-id="8250a-120">Para obter mais informações sobre o recurso Visualizador de Eventos, como gerenciar o log do aplicativo e como compreender as informações apresentadas, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="8250a-120">For more information about using Event Viewer, managing the application log, and understanding the information it presents, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="8250a-121">**Para exibir o log de aplicativos do Windows**</span><span class="sxs-lookup"><span data-stu-id="8250a-121">**To view the Windows application log**</span></span>  
  
 [<span data-ttu-id="8250a-122">Exibir o log de aplicativos do Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="8250a-122">View the Windows Application Log &#40;Windows&#41;</span></span>](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
