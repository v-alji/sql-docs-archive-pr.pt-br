---
title: Programa externo do Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- external programs [Database Mail]
- DatabaseMail90.exe
- Database Mail [SQL Server], external programs
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 698fc8d97a565b4181552691a0260486c9c43bfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685780"
---
# <a name="database-mail-external-program"></a><span data-ttu-id="1e488-102">Programa externo do Database Mail</span><span class="sxs-lookup"><span data-stu-id="1e488-102">Database Mail External Program</span></span>
  <span data-ttu-id="1e488-103">O executável externo do Database Mail é **DatabaseMail.exe**, que está localizado no **diretório MSSQL\Binn** da instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e488-103">The Database Mail external executable is **DatabaseMail.exe**, located in the **MSSQL\Binn directory** of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="1e488-104">O Database Mail usa a ativação do Service Broker para iniciar o programa externo quando há mensagens de email a serem processadas.</span><span class="sxs-lookup"><span data-stu-id="1e488-104">Database Mail uses Service Broker activation to start the external program when there are e-mail messages to be processed.</span></span> <span data-ttu-id="1e488-105">O Database Mail inicia uma instância do programa externo.</span><span class="sxs-lookup"><span data-stu-id="1e488-105">Database Mail starts one instance of the external program.</span></span> <span data-ttu-id="1e488-106">O programa externo é executado no contexto de segurança da conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e488-106">The external program runs in the security context of the service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1e488-107">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="1e488-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="1e488-108">Conceitos de programas externos do Database Mail</span><span class="sxs-lookup"><span data-stu-id="1e488-108">Database Mail External Program Concepts</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="1e488-109">Tarefas relacionadas para configurar programa externo do Database Mail</span><span class="sxs-lookup"><span data-stu-id="1e488-109">Tasks Related to Configuring Database Mail External Program</span></span>](#RelatedTasks)  
  
##  <a name="database-mail-external-program-concepts"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="1e488-110">Conceitos de programas externos do Database Mail</span><span class="sxs-lookup"><span data-stu-id="1e488-110">Database Mail External Program Concepts</span></span>  
 <span data-ttu-id="1e488-111">Ao ser iniciado, o programa externo se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando autenticação do Windows e começa a processar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="1e488-111">When the external program starts, the program connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows Authentication and begins processing e-mail messages.</span></span> <span data-ttu-id="1e488-112">Quando não há nenhuma mensagem a enviar no tempo limite especificado, o programa é encerrado.</span><span class="sxs-lookup"><span data-stu-id="1e488-112">When there have been no messages to send for the specified time-out period, the program exits.</span></span> <span data-ttu-id="1e488-113">Você pode configurar o tempo que o programa deve aguardar antes de encerrar, usando o Assistente para Configuração do Database Mail ou procedimentos armazenados do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="1e488-113">You can configure the amount of time that the program waits before exiting by using either Database Mail Configuration Wizard or the Database Mail stored procedures.</span></span> <span data-ttu-id="1e488-114">Para obter mais informações, veja [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e488-114">For more information, see [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span></span>  
  
 <span data-ttu-id="1e488-115">O programa externo armazena informações em tabelas do sistema no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1e488-115">The external program stores information in system tables in the **msdb** database.</span></span> <span data-ttu-id="1e488-116">Se o programa externo não puder se comunicar com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ele registrará erros no log de eventos de aplicativos do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1e488-116">If the external program cannot communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the program logs errors to the Microsoft Windows application event log.</span></span> <span data-ttu-id="1e488-117">Há ainda outros registros de mensagens quando o nível de log é definido como **Detalhado** na caixa de diálogo **Configurar Parâmetros do Sistema** do **Assistente para Configuração do Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="1e488-117">Additional message logging is provided when the logging level is set to **Verbose** in the **Configure System Parameters** dialog box of the **Database Mail Configuration Wizard**.</span></span>  
  
 <span data-ttu-id="1e488-118">Observe que, por questão de eficiência, o programa externo coloca em cache as informações de conta e perfil.</span><span class="sxs-lookup"><span data-stu-id="1e488-118">Notice that, for efficiency, the external program caches account and profile information.</span></span> <span data-ttu-id="1e488-119">Portanto, alterações na configuração de contas e perfis podem não se refletir no programa externo por alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="1e488-119">Therefore, configuration changes to accounts and profiles may not be reflected in the external program for a few minutes.</span></span>  
  
##  <a name="tasks-related-to-configuring-database-mail-external-program"></a><a name="RelatedTasks"></a> <span data-ttu-id="1e488-120">Tarefas relacionadas para configurar programa externo do Database Mail</span><span class="sxs-lookup"><span data-stu-id="1e488-120">Tasks Related to Configuring Database Mail External Program</span></span>  
  
|<span data-ttu-id="1e488-121">Tarefa de configuração</span><span class="sxs-lookup"><span data-stu-id="1e488-121">Configuration Task</span></span>|<span data-ttu-id="1e488-122">Link do tópico</span><span class="sxs-lookup"><span data-stu-id="1e488-122">Topic Link</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="1e488-123">Especifique a hora do Programa Externo antes de sair.</span><span class="sxs-lookup"><span data-stu-id="1e488-123">Specify the time that the External Program before exiting.</span></span>|[<span data-ttu-id="1e488-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1e488-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="1e488-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e488-125">See Also</span></span>  
 <span data-ttu-id="1e488-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="1e488-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="1e488-127">[Registro em log e auditoria do Database Mail](database-mail-log-and-audits.md) </span><span class="sxs-lookup"><span data-stu-id="1e488-127">[Database Mail Log and Audits](database-mail-log-and-audits.md) </span></span>  
 [<span data-ttu-id="1e488-128">Database Mail</span><span class="sxs-lookup"><span data-stu-id="1e488-128">Database Mail</span></span>](database-mail.md)  
  
  
