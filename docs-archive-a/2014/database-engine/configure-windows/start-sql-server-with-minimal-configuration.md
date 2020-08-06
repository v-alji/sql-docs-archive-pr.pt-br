---
title: Iniciar o SQL Server com a configuração mínima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- minimal configuration [SQL Server]
- starting SQL Server, minimal configuration
ms.assetid: 4d733c99-28b3-42d8-b7f6-7b943b548173
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c78fc10be584803b438b2cd125a77400ff369b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569636"
---
# <a name="start-sql-server-with-minimal-configuration"></a><span data-ttu-id="9618b-102">Iniciar o SQL Server com configuração mínima</span><span class="sxs-lookup"><span data-stu-id="9618b-102">Start SQL Server with Minimal Configuration</span></span>
  <span data-ttu-id="9618b-103">Se você tiver problemas de configuração que impeçam o servidor de ser iniciado, inicie uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a opção de inicialização de configuração mínima.</span><span class="sxs-lookup"><span data-stu-id="9618b-103">If you have configuration problems that prevent the server from starting, you can start an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the minimal configuration startup option.</span></span> <span data-ttu-id="9618b-104">Essa é a opção de inicialização **-f**.</span><span class="sxs-lookup"><span data-stu-id="9618b-104">This is the startup option **-f**.</span></span> <span data-ttu-id="9618b-105">Ao iniciar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com configuração mínima, o servidor é colocado automaticamente em modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="9618b-105">Starting an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with minimal configuration automatically puts the server in single-user mode.</span></span>  
  
 <span data-ttu-id="9618b-106">Ao iniciar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em modo de configuração mínimo, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9618b-106">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode, note the following:</span></span>  
  
-   <span data-ttu-id="9618b-107">Apenas um usuário único pode fazer a conexão e o processo de CHECKPOINT não é executado.</span><span class="sxs-lookup"><span data-stu-id="9618b-107">Only a single user can connect, and the CHECKPOINT process is not executed.</span></span>  
  
-   <span data-ttu-id="9618b-108">Acesso remoto e read-ahead são desabilitados.</span><span class="sxs-lookup"><span data-stu-id="9618b-108">Remote access and read-ahead are disabled.</span></span>  
  
-   <span data-ttu-id="9618b-109">Procedimentos de inicialização armazenados não são executados.</span><span class="sxs-lookup"><span data-stu-id="9618b-109">Startup stored procedures do not run.</span></span>  
  
 <span data-ttu-id="9618b-110">Depois que o servidor tiver sido iniciado com a configuração mínima, altere o valor ou os valores da opção de servidor apropriada, interrompa e, em seguida, reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="9618b-110">After the server has been started with minimal configuration, you should change the appropriate server option value or values, stop, and then restart the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9618b-111">Use o utilitário **sqlcmd** e a DAC (conexão de administrador dedicada) para se conectar com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9618b-111">Use the **sqlcmd** utility and the dedicated administrator connection (DAC) to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9618b-112">Se você usar uma conexão típica, interrompa o SQL Server Agent antes de conectar-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em modo de configuração mínimo.</span><span class="sxs-lookup"><span data-stu-id="9618b-112">If you use a typical connection, stop the SQL Server Agent service before connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode.</span></span> <span data-ttu-id="9618b-113">Caso contrário, o SQL Server Agent usará a conexão, bloqueando-a.</span><span class="sxs-lookup"><span data-stu-id="9618b-113">Otherwise, the SQL Server Agent service uses the connection, thereby blocking it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9618b-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9618b-114">See Also</span></span>  
 <span data-ttu-id="9618b-115">[Iniciar, parar ou pausar o serviço do SQL Server Agent](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span><span class="sxs-lookup"><span data-stu-id="9618b-115">[Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span></span>  
 <span data-ttu-id="9618b-116">[Conexão de diagnóstico para administradores de banco de dados](diagnostic-connection-for-database-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="9618b-116">[Diagnostic Connection for Database Administrators](diagnostic-connection-for-database-administrators.md) </span></span>  
 <span data-ttu-id="9618b-117">[Utilitário sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9618b-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="9618b-118">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9618b-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="9618b-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9618b-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="9618b-120">Opções de inicialização do serviço Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="9618b-120">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  
