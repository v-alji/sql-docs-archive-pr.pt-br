---
title: Exibir um log de auditoria do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8f9902a4fc92ef0b35bae62eb80170762c52fdec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570577"
---
# <a name="view-a-sql-server-audit-log"></a><span data-ttu-id="ab159-102">Exibir um log auditoria do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab159-102">View a SQL Server Audit Log</span></span>
  <span data-ttu-id="ab159-103">Este tópico descreve como exibir um log de auditoria do SQL Server no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab159-103">This topic describes how to view a SQL Server audit log in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ab159-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ab159-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ab159-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ab159-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ab159-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="ab159-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ab159-107">**Para exibir um log de auditoria do SQL Server usando:**</span><span class="sxs-lookup"><span data-stu-id="ab159-107">**To view a SQL Server audit log, using:**</span></span>  
  
     [<span data-ttu-id="ab159-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab159-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ab159-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ab159-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ab159-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="ab159-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ab159-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="ab159-111">Permissions</span></span>  
 <span data-ttu-id="ab159-112">Requer a permissão `CONTROL SERVER`.</span><span class="sxs-lookup"><span data-stu-id="ab159-112">Requires the `CONTROL SERVER` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ab159-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab159-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-sql-server-audit-log"></a><span data-ttu-id="ab159-114">Para exibir um log de auditoria do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab159-114">To view a SQL Server audit log</span></span>  
  
1.  <span data-ttu-id="ab159-115">No Pesquisador de Objetos, expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="ab159-115">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="ab159-116">Expanda a pasta **Auditorias** .</span><span class="sxs-lookup"><span data-stu-id="ab159-116">Expand the **Audits** folder.</span></span>  
  
3.  <span data-ttu-id="ab159-117">Clique com o botão direito do mouse no log de auditoria que você deseja exibir e selecione **Exibir Logs de Auditoria**.</span><span class="sxs-lookup"><span data-stu-id="ab159-117">Right-click the audit log that you want to view and select **View Audit Logs**.</span></span> <span data-ttu-id="ab159-118">Isso abre a caixa de diálogo **Visualizador do arquivo de log-**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="ab159-118">This opens the **Log File Viewer -**_server_name_ dialog box.</span></span> <span data-ttu-id="ab159-119">Para obter mais informações, consulte [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="ab159-119">For more information, see [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span></span>  
  
4.  <span data-ttu-id="ab159-120">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ab159-120">When finished, click **Close**.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="ab159-121">recomenda exibir o log de auditoria usando o Visualizador do Arquivo de Log.</span><span class="sxs-lookup"><span data-stu-id="ab159-121">recommends viewing the audit log by using the Log File Viewer.</span></span> <span data-ttu-id="ab159-122">No entanto, se você estiver criando um sistema de monitoramento automatizado, as informações no arquivo de auditoria podem ser lidas diretamente usando a função [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab159-122">However, if you are creating an automated monitoring system, the information in the audit file can be read directly by using the [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) function.</span></span> <span data-ttu-id="ab159-123">Ler o arquivo diretamente retorna dados em um formato ligeiramente diferente (não processado).</span><span class="sxs-lookup"><span data-stu-id="ab159-123">Reading the file directly returns data in a slightly different (unprocessed) format.</span></span> <span data-ttu-id="ab159-124">Consulte **Sys. fn_get_audit_file** para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="ab159-124">See **sys.fn_get_audit_file** for more information</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab159-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab159-125">See Also</span></span>  
 <span data-ttu-id="ab159-126">[Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;](sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="ab159-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="ab159-127">Gravar eventos de auditoria do SQL Server no log de segurança</span><span class="sxs-lookup"><span data-stu-id="ab159-127">Write SQL Server Audit Events to the Security Log</span></span>](write-sql-server-audit-events-to-the-security-log.md)  
  
  
