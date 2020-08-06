---
title: Exibindo o log de erros do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cycling SQL Server error log
- viewing SQL Server error log
- errors [SQL Server], logs
- SQL Server error log
- displaying SQL Server error log
- logs [SQL Server], SQL Server error logs
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
author: stevestein
ms.author: sstein
ms.openlocfilehash: 822ae4fba589f005aaee41857a9db3388a309254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568276"
---
# <a name="viewing-the-sql-server-error-log"></a><span data-ttu-id="24228-102">Exibindo o log de erros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="24228-102">Viewing the SQL Server Error Log</span></span>
  <span data-ttu-id="24228-103">Exiba o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para garantir que os processos tenham sido concluídos com êxito (por exemplo, operações de backup e restauração, comandos em lotes ou outros scripts e processos).</span><span class="sxs-lookup"><span data-stu-id="24228-103">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to ensure that processes have completed successfully (for example, backup and restore operations, batch commands, or other scripts and processes).</span></span> <span data-ttu-id="24228-104">Isso poderá ajudar a detectar áreas com problemas atuais ou em potencial, inclusive mensagens de recuperação automática, principalmente se tiver ocorrido parada e reinicialização de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mensagens do kernel ou outras mensagens de erro do servidor.</span><span class="sxs-lookup"><span data-stu-id="24228-104">This can be helpful to detect any current or potential problem areas, including automatic recovery messages (particularly if an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been stopped and restarted), kernel messages, or other server-level error messages.</span></span>  
  
 <span data-ttu-id="24228-105">Exiba o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="24228-105">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor.</span></span> <span data-ttu-id="24228-106">Para obter mais informações sobre como exibir o log de erros, consulte [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="24228-106">For more information about how to view the error log, see [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span></span> <span data-ttu-id="24228-107">Por padrão, o log de erros está localizado nos arquivos `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` e `ERRORLOG.`*n* .</span><span class="sxs-lookup"><span data-stu-id="24228-107">By default, the error log is located at `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` and `ERRORLOG.`*n* files.</span></span>  
  
 <span data-ttu-id="24228-108">Um novo log de erros é criado sempre que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciada, embora o procedimento armazenado do sistema, [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) , possa ser usado no ciclo de arquivos de log de erros sem a necessidade de reiniciar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24228-108">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, although the [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) system stored procedure can be used to cycle the error log files without having to restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="24228-109">Em geral, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retém backups dos seis logs anteriores e fornece ao backup de log mais recente a extensão .1, ao segundo mais recente a extensão .2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="24228-109">Typically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains backups of the previous six logs and gives the most recent log backup the extension .1, the second most recent the extension .2, and so on.</span></span> <span data-ttu-id="24228-110">O log de erros atual não tem extensão.</span><span class="sxs-lookup"><span data-stu-id="24228-110">The current error log has no extension.</span></span>  
  
 <span data-ttu-id="24228-111">Também é possível exibir o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log de erros em instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estejam offline ou que não seja possível inicializar.</span><span class="sxs-lookup"><span data-stu-id="24228-111">Be aware that you can also view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline or cannot start.</span></span> <span data-ttu-id="24228-112">Para obter mais informações, veja [Exibir arquivos de log offline](../../relational-databases/logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="24228-112">For more information, see [View Offline Log Files](../../relational-databases/logs/view-offline-log-files.md).</span></span>  
  
  
