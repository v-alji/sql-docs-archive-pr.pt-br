---
title: Verificar o status de mensagens de email enviadas com o Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1642c456cd64484dede64f8127ff2f979f2242e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583618"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a><span data-ttu-id="c1ea8-102">Verificar o status de mensagens de email enviadas por Database Mail</span><span class="sxs-lookup"><span data-stu-id="c1ea8-102">Check the Status of E-Mail Messages Sent With Database Mail</span></span>
  <span data-ttu-id="c1ea8-103">Este tópico descreve como verificar o status da mensagem de email enviada usando o Database no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] com [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1ea8-103">This topic describes how to check the status of the e-mail message sent using Database Mail  in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="c1ea8-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c1ea8-104">**Before you begin:**</span></span>  
  
-   <span data-ttu-id="c1ea8-105">**Para exibir o status do email enviado usando Database Mail, com:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="c1ea8-105">**To view the status of the e-mail sent using Database Mail, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1ea8-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c1ea8-106">Before You Begin</span></span>  
 <span data-ttu-id="c1ea8-107">O Database Mail mantém cópias das mensagens de email enviadas, que podem ser visualizadas nas exibições **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**e **sysmail_faileditems** do banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c1ea8-107">Database Mail keeps copies of outgoing e-mail messages and displays them in the **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**, **sysmail_faileditems** views of the **msdb** database.</span></span> <span data-ttu-id="c1ea8-108">O programa externo do Database Mail registra a atividade e exibe o log por meio do Log de Eventos de Aplicativos do Windows e da exibição **sysmail_event_log** do banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c1ea8-108">The Database Mail external program logs activity and displays the log through the Windows Application Event Log and the **sysmail_event_log** view in the **msdb** database.</span></span> <span data-ttu-id="c1ea8-109">Para verificar o status de uma mensagem de email, execute uma consulta para essa exibição.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-109">To check the status of an e-mail message, run a query against this view.</span></span> <span data-ttu-id="c1ea8-110">São quatro os status possíveis das mensagens de email: **sent**(enviada), **unsent**(não enviada), **retrying**(tentando novamente) e **failed**(falhou).</span><span class="sxs-lookup"><span data-stu-id="c1ea8-110">E-mail messages have one of four possible statuses: **sent**, **unsent**, **retrying**, and **failed**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1ea8-111">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1ea8-111">Using Transact-SQL</span></span>  
 <span data-ttu-id="c1ea8-112">**Para exibir o status do email enviado usando Database Mail**</span><span class="sxs-lookup"><span data-stu-id="c1ea8-112">**To view the status of the e-mail sent using Database Mail**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1ea8-113">Para obter um exemplo desse procedimento, veja [Exemplo (Transact-SQL)](#TsqlExample), mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-113">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="c1ea8-114">Selecione na tabela **sysmail_allitems** as mensagens de interesse, especificando-as por **mailitem_id** ou **sent_status**.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-114">Select from the **sysmail_allitems** table, specifying the messages of interest by **mailitem_id** or **sent_status**.</span></span>  
  
2.  <span data-ttu-id="c1ea8-115">Para verificar o status retornado pelo programa externo para as mensagens de email, una a exibição **sysmail_allitems** à exibição **sysmail_event_log** na coluna **mailitem_id** , como mostra a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-115">To check the status returned from the external program for the e-mail messages, join **sysmail_allitems** to **sysmail_event_log** view on the **mailitem_id** column, as shown in the following section.</span></span>  
  
     <span data-ttu-id="c1ea8-116">Por padrão, o programa externo não registra informações sobre mensagens enviadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-116">By default, the external program does not log information about messages that were successfully sent.</span></span> <span data-ttu-id="c1ea8-117">Para registrar todas as mensagens, defina o nível de log como detalhado na página **Configurar Parâmetros do Sistema** do **Assistente para Configuração do Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-117">To log all messages, set the logging level to verbose using the **Configure System Parameters** page of the **Database Mail Configuration Wizard.**</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c1ea8-118">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c1ea8-118">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c1ea8-119">O exemplo a seguir lista informações sobre todas as mensagens de email enviadas a `danw` que o programa externo não conseguiu enviar com êxito.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-119">The following example lists information about any e-mail messages sent to `danw` that the external program could not send successfully.</span></span> <span data-ttu-id="c1ea8-120">A instrução lista o assunto, a data e a hora que o programa externo falhou em enviar a mensagem, além da mensagem de erro do log do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-120">The statement lists the subject, the date and time that the external program failed to send the message, and the error message from the Database Mail log.</span></span>  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1ea8-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c1ea8-121">See Also</span></span>  
 [<span data-ttu-id="c1ea8-122">Log e auditoria do Database Mail</span><span class="sxs-lookup"><span data-stu-id="c1ea8-122">Database Mail Log and Audits</span></span>](database-mail-log-and-audits.md)  
  
  
