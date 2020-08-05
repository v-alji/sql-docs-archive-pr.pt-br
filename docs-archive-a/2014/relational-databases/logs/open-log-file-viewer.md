---
title: Abrir o Visualizador do Arquivo de Log | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, opening
ms.assetid: a86b89cb-0432-4648-895a-05ecc5450e45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269ff10275f7463a8a85249a2a0f06fe9bde364a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572537"
---
# <a name="open-log-file-viewer"></a><span data-ttu-id="3020f-102">Abrir o Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="3020f-102">Open Log File Viewer</span></span>
  <span data-ttu-id="3020f-103">É possível usar o Visualizador do Arquivo de Log no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para acessar informações sobre erros e eventos capturados nos seguintes logs:</span><span class="sxs-lookup"><span data-stu-id="3020f-103">You can use Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to access information about errors and events that are captured in the following logs:</span></span>  
  
-   <span data-ttu-id="3020f-104">Coleta de Auditoria</span><span class="sxs-lookup"><span data-stu-id="3020f-104">Audit Collection</span></span>  
  
-   <span data-ttu-id="3020f-105">Coleta de dados</span><span class="sxs-lookup"><span data-stu-id="3020f-105">Data Collection</span></span>  
  
-   <span data-ttu-id="3020f-106">Database Mail</span><span class="sxs-lookup"><span data-stu-id="3020f-106">Database Mail</span></span>  
  
-   <span data-ttu-id="3020f-107">Histórico de Trabalhos</span><span class="sxs-lookup"><span data-stu-id="3020f-107">Job History</span></span>  
  
-   <span data-ttu-id="3020f-108">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3020f-108">SQL Server</span></span>  
  
-   <span data-ttu-id="3020f-109">SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3020f-109">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="3020f-110">Eventos do Windows (esses eventos também podem ser acessados no Visualizador de Eventos do Windows.)</span><span class="sxs-lookup"><span data-stu-id="3020f-110">Windows events (These Windows events can also be accessed from Event Viewer.)</span></span>  
  
 <span data-ttu-id="3020f-111">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], você pode usar Servidores Registrados para exibir arquivos de log [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de instâncias locais ou remotas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3020f-111">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can use Registered Servers to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from local or remote instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3020f-112">Usando Servidores Registrados, você poderá exibir os arquivos de log quando as instâncias forem online ou offline.</span><span class="sxs-lookup"><span data-stu-id="3020f-112">By using Registered Servers, you can view the log files when the instances are either online or offline.</span></span> <span data-ttu-id="3020f-113">Para obter mais informações sobre o acesso online, veja o procedimento “Para exibir arquivos de log online de Servidores Registrados”, mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3020f-113">For more information about online access, see the procedure "To view online log files from Registered Servers" later in this topic.</span></span> <span data-ttu-id="3020f-114">Para obter mais informações sobre como acessar arquivos de log offline do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , veja [Exibir arquivos de log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="3020f-114">For more information about how to access offline [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files, see [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
 <span data-ttu-id="3020f-115">Você pode abrir o Visualizador do Arquivo de Log de várias maneiras, dependendo das informações que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="3020f-115">You can open Log File Viewer in several ways, depending on the information that you want to view.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3020f-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="3020f-116">Permissions</span></span>  
 <span data-ttu-id="3020f-117">Para acessar arquivos de log de instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estão online, é necessária associação na função de servidor fixa securityadmin.</span><span class="sxs-lookup"><span data-stu-id="3020f-117">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="3020f-118">Para acessar arquivos de log de instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estão offline, é necessário ter acesso de leitura no namespace do WMI **Root\Microsoft\SqlServer\ComputerManagement10** e na pasta em que os arquivos de log estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="3020f-118">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="3020f-119">Para obter mais informações, veja a seção Segurança do tópico [Exibir arquivos de log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="3020f-119">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
### <a name="security"></a><span data-ttu-id="3020f-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="3020f-120">Security</span></span>  
 <span data-ttu-id="3020f-121">Exige associação à função de servidor fixa securityadmin.</span><span class="sxs-lookup"><span data-stu-id="3020f-121">Requires membership in the securityadmin fixed server role.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="3020f-122">Exibir Arquivos de Log</span><span class="sxs-lookup"><span data-stu-id="3020f-122">View Log Files</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-general-sql-server-activity"></a><span data-ttu-id="3020f-123">Para exibir logs relacionados a atividades gerais do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3020f-123">To view logs that are related to general SQL Server activity</span></span>  
  
1.  <span data-ttu-id="3020f-124">No Pesquisador de Objetos, expanda **Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="3020f-124">In Object Explorer, expand **Management**.</span></span>  
  
2.  <span data-ttu-id="3020f-125">Execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3020f-125">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="3020f-126">Clique com o botão direito do mouse em **Logs do SQL Server**, aponte para **Exibir**e clique em **Log do SQL Server** ou em **Log do SQL Server e do Windows**.</span><span class="sxs-lookup"><span data-stu-id="3020f-126">Right-click **SQL Server Logs**, point to **View**, and then click either **SQL Server Log** or **SQL Server and Windows Log**.</span></span>  
  
    -   <span data-ttu-id="3020f-127">Expanda **Logs do SQL Server**, clique com o botão direito do mouse em qualquer arquivo de log e clique em **Exibir Log do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3020f-127">Expand **SQL Server Logs**, right-click any log file, and then click **View SQL Server Log**.</span></span> <span data-ttu-id="3020f-128">Você também pode clicar duas vezes em qualquer arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="3020f-128">You can also double-click any log file.</span></span>  
  
     <span data-ttu-id="3020f-129">Os logs incluem **Database Mail**, **SQL Server**, **SQL Server Agent**e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="3020f-129">The logs include **Database Mail**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-jobs"></a><span data-ttu-id="3020f-130">Para exibir logs relacionados a trabalhos</span><span class="sxs-lookup"><span data-stu-id="3020f-130">To view logs that are related to jobs</span></span>  
  
-   <span data-ttu-id="3020f-131">No Pesquisador de Objetos, expanda **SQL Server Agent**, clique com o botão direito do mouse em **Trabalhos**e clique em **Exibir Histórico**.</span><span class="sxs-lookup"><span data-stu-id="3020f-131">In Object Explorer, expand **SQL Server Agent**, right-click **Jobs**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="3020f-132">Os logs incluem **Database Mail**, **Histórico de Trabalhos**e **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="3020f-132">The logs include **Database Mail**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-maintenance-plans"></a><span data-ttu-id="3020f-133">Para exibir logs relacionados a planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="3020f-133">To view logs that are related to maintenance plans</span></span>  
  
-   <span data-ttu-id="3020f-134">No Pesquisador de Objetos, expanda **Gerenciamento**, clique com o botão direito do mouse em **Planos de Manutenção**e clique em **Exibir Histórico**.</span><span class="sxs-lookup"><span data-stu-id="3020f-134">In Object Explorer, expand **Management**, right-click **Maintenance Plans**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="3020f-135">Os logs incluem **Database Mail**, **Histórico do Trabalho**, **Planos de Manutenção**, **Planos de Manutenção Remotos**e **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="3020f-135">The logs include **Database Mail**, **Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-data-collection"></a><span data-ttu-id="3020f-136">Para exibir logs relacionados à Coleção de Dados</span><span class="sxs-lookup"><span data-stu-id="3020f-136">To view logs that are related to Data Collection</span></span>  
  
-   <span data-ttu-id="3020f-137">No Pesquisador de Objetos, expanda **Gerenciamento**, clique com o botão direito do mouse em **Coleção de Dados**e clique em **Exibir Logs**.</span><span class="sxs-lookup"><span data-stu-id="3020f-137">In Object Explorer, expand **Management**, right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="3020f-138">Os logs incluem **Coleta de Dados**, **Histórico de Trabalhos**e **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="3020f-138">The logs include **Data Collection**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-database-mail"></a><span data-ttu-id="3020f-139">Para exibir logs relacionados ao Database Mail</span><span class="sxs-lookup"><span data-stu-id="3020f-139">To view logs that are related to Database Mail</span></span>  
  
-   <span data-ttu-id="3020f-140">No Pesquisador de Objetos, expanda **Gerenciamento**, clique com o botão direito do mouse em **Database Mail**e clique em **Exibir Log do Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="3020f-140">In Object Explorer, expand **Management**, right-click **Database Mail**, and then click **View Database Mail Log**.</span></span>  
  
     <span data-ttu-id="3020f-141">Os logs incluem **Database Mail, Histórico de Trabalhos**, **Planos de Manutenção**, **Planos de Manutenção Remotos**, **SQL Server**, **SQL Server Agent**e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="3020f-141">The logs include **Database Mail, Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="3020f-142">Para exibir logs relacionados a coletas de auditorias</span><span class="sxs-lookup"><span data-stu-id="3020f-142">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="3020f-143">No Pesquisador de Objetos, expanda **Segurança**e **Auditorias**, clique com o botão direito do mouse em uma auditoria e clique em **Exibir Logs de Auditoria**.</span><span class="sxs-lookup"><span data-stu-id="3020f-143">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="3020f-144">Os logs incluem **Coleta de Auditoria** e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="3020f-144">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="3020f-145">Para exibir logs relacionados a coletas de auditorias</span><span class="sxs-lookup"><span data-stu-id="3020f-145">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="3020f-146">No Pesquisador de Objetos, expanda **Segurança**e **Auditorias**, clique com o botão direito do mouse em uma auditoria e clique em **Exibir Logs de Auditoria**.</span><span class="sxs-lookup"><span data-stu-id="3020f-146">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="3020f-147">Os logs incluem **Coleta de Auditoria** e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="3020f-147">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3020f-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3020f-148">See Also</span></span>  
 <span data-ttu-id="3020f-149">[Visualizador do Arquivo de Log](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="3020f-149">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="3020f-150">[Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="3020f-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="3020f-151">Exibir arquivos de log offline</span><span class="sxs-lookup"><span data-stu-id="3020f-151">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
