---
title: Log e auditoria do Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- Database Mail [SQL Server], auditing
- logs [Database Mail]
- audits [SQL Server], Database Mail
- Database Mail [SQL Server], logging
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6267389f187b955982ec1c18c411f703b4562f3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685772"
---
# <a name="database-mail-log-and-audits"></a><span data-ttu-id="6e5e4-102">Registro em log e auditoria do Database Mail</span><span class="sxs-lookup"><span data-stu-id="6e5e4-102">Database Mail Log and Audits</span></span>
  <span data-ttu-id="6e5e4-103">A funcionalidade de log do Database Mail é criada para fornecer um modo de isolar e corrigir problemas.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-103">The Database Mail logging functionality is designed to provide a way to isolate and correct problems.</span></span> <span data-ttu-id="6e5e4-104">O Database Mail armazena as informações de log no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="6e5e4-104">Database Mail stores the log information in the **msdb** database.</span></span> <span data-ttu-id="6e5e4-105">Informações sobre conteúdo de e-mail do Database Mail, status de emails e qualquer mensagem recebida, tais como erros, são registradas em log pelo Database Mail e podem ser usadas para fins de solução de problemas e auditoria.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-105">Information about Database Mail e-mail content, status of e-mails, and any messages received, such as errors  are logged by Database Mail and can be used for troubleshooting and auditing purposes.</span></span>  
  
## <a name="database-mail-logs"></a><span data-ttu-id="6e5e4-106">Logs do Database Mail</span><span class="sxs-lookup"><span data-stu-id="6e5e4-106">Database Mail Logs</span></span>  
 <span data-ttu-id="6e5e4-107">Tabelas no banco de dados **msdb** registram informações do [Database Mail External Program](database-mail-external-program.md).</span><span class="sxs-lookup"><span data-stu-id="6e5e4-107">Tables in the **msdb** database log information from the [Database Mail External Program](database-mail-external-program.md).</span></span> <span data-ttu-id="6e5e4-108">[Exibições do Database Mail &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expõe as tabelas para fins de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-108">[Database Mail Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expose the tables for troubleshooting purposes.</span></span> <span data-ttu-id="6e5e4-109">Erros aparecem na exibição [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) quando o Service Broker não consegue ativar o programa externo, se o programa externo encontra erros de rede ou se o servidor SMTP recusa uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-109">Errors appear in the [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) view if Service Broker cannot activate the external program, if the external program encounters networking errors or if the Simple Mail Transport Protocol (SMTP) server refuses an e-mail message.</span></span> <span data-ttu-id="6e5e4-110">Na eventualidade de o programa externo não conseguir fazer registros nas tabelas do **msdb** , o programa registrará os erros no log de eventos de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-110">In the event that the external program cannot log to the **msdb** tables, the program logs errors to the Windows application event log.</span></span>  
  
 <span data-ttu-id="6e5e4-111">Tabelas internas do **msdb** contêm as mensagens de email e anexos enviados por meio do Database Mail, além do status atual de cada mensagem.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-111">Internal tables in the **msdb** database contain the e-mail messages and attachments sent from Database Mail, together with the current status of each message.</span></span> <span data-ttu-id="6e5e4-112">O Database Mail atualiza essas tabelas assim que cada mensagem é processada.</span><span class="sxs-lookup"><span data-stu-id="6e5e4-112">Database Mail updates these tables as each message is processed.</span></span>  
  
## <a name="database-mail-auditing-tasks"></a><span data-ttu-id="6e5e4-113">Tarefas de auditoria do Database Mail</span><span class="sxs-lookup"><span data-stu-id="6e5e4-113">Database Mail Auditing tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e5e4-114">**Examinando e gerenciando logs do Database Mail**</span><span class="sxs-lookup"><span data-stu-id="6e5e4-114">**Reviewing and managing Database Mail logs**</span></span>|<span data-ttu-id="6e5e4-115">**Link para o tópico**</span><span class="sxs-lookup"><span data-stu-id="6e5e4-115">**Link to Topic**</span></span>|  
|<span data-ttu-id="6e5e4-116">Verifique o status de entrega de uma mensagem individual</span><span class="sxs-lookup"><span data-stu-id="6e5e4-116">Check the delivery status of an individual message</span></span>|[<span data-ttu-id="6e5e4-117">Verificar o status de mensagens de email enviadas com o Database Mail</span><span class="sxs-lookup"><span data-stu-id="6e5e4-117">Check the Status of E-Mail Messages Sent With Database Mail</span></span>](check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|<span data-ttu-id="6e5e4-118">Limpe mensagens, anexos e entradas de log do Database Mail</span><span class="sxs-lookup"><span data-stu-id="6e5e4-118">Clean up Database Mail messages, attachments, and log entries</span></span>|[<span data-ttu-id="6e5e4-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6e5e4-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql)<br /><br /> [<span data-ttu-id="6e5e4-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6e5e4-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql)|  
|<span data-ttu-id="6e5e4-121">Arquive mensagens e logs do Database Email</span><span class="sxs-lookup"><span data-stu-id="6e5e4-121">Archive the Database Email Messages and Logs</span></span>|[<span data-ttu-id="6e5e4-122">Criar um trabalho do SQL Server Agent para arquivar mensagens e logs de eventos do Database Mail</span><span class="sxs-lookup"><span data-stu-id="6e5e4-122">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>](create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="6e5e4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e5e4-123">See Also</span></span>  
 [<span data-ttu-id="6e5e4-124">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="6e5e4-124">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](../performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
