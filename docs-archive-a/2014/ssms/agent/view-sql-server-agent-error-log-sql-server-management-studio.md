---
title: Exibir um log de erros do SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- viewing SQL Server Agent error logs
- displaying SQL Server Agent error logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: de920425-fa44-469f-b83d-49e3f97e97f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: b88214a158a970a754c5f313bde3d53f2652ae73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682066"
---
# <a name="view-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="5849d-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5849d-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5849d-103">Este tópico descreve como exibir o log de erros do  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5849d-103">This topic describes how to view the  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5849d-104">O Visualizador do Arquivo de Log exibe informações de muitos componentes diferentes.</span><span class="sxs-lookup"><span data-stu-id="5849d-104">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="5849d-105">Quando o Visualizador do Arquivo de Log estiver aberto, use o painel **Selecionar logs** para selecionar os logs que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="5849d-105">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="5849d-106">Cada log exibe as colunas adequadas àquele tipo de log.</span><span class="sxs-lookup"><span data-stu-id="5849d-106">Each log displays columns appropriate to that kind of log.</span></span> <span data-ttu-id="5849d-107">Os logs disponíveis dependem de como o Visualizador do Arquivo de Log é aberto.</span><span class="sxs-lookup"><span data-stu-id="5849d-107">The logs that are available depend on how Log File Viewer is opened.</span></span>  
  
 <span data-ttu-id="5849d-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5849d-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5849d-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5849d-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5849d-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5849d-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5849d-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="5849d-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="5849d-112">Para exibir o log de erros do SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5849d-112">To view the SQL Server Agent error log, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5849d-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5849d-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5849d-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5849d-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5849d-115">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="5849d-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5849d-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="5849d-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5849d-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="5849d-117">Permissions</span></span>  
 <span data-ttu-id="5849d-118">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5849d-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5849d-119">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="5849d-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="5849d-120">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="5849d-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="5849d-121">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5849d-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="5849d-122">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5849d-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="5849d-123">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5849d-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="5849d-124">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5849d-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5849d-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5849d-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-ssnoversion-agent-error-log"></a><span data-ttu-id="5849d-126">Para exibir o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="5849d-126">To view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log</span></span>  
  
1.  <span data-ttu-id="5849d-127">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="5849d-127">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to view.</span></span>  
  
2.  <span data-ttu-id="5849d-128">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="5849d-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5849d-129">Clique no sinal de adição para expandir a pasta **Logs de erro** .</span><span class="sxs-lookup"><span data-stu-id="5849d-129">Click the plus sign to expand the **Error Logs** folder.</span></span>  
  
4.  <span data-ttu-id="5849d-130">Clique com o botão direito do mouse no log de erros que você deseja exibir e selecione **Exibir Log do Agente**.</span><span class="sxs-lookup"><span data-stu-id="5849d-130">Right-click the error log you want to view and select **View Agent Log**.</span></span>  
  
     <span data-ttu-id="5849d-131">As opções a seguir estão disponíveis na caixa de diálogo **Visualizador do Arquivo de Log -**_nome_do_servidor_:</span><span class="sxs-lookup"><span data-stu-id="5849d-131">The following options are available in the **Log File Viewer -**_server_name_ dialog box:</span></span>  
  
     <span data-ttu-id="5849d-132">**Carregar Log**</span><span class="sxs-lookup"><span data-stu-id="5849d-132">**Load Log**</span></span>  
     <span data-ttu-id="5849d-133">Abra uma caixa de diálogo onde seja possível especificar um arquivo de log a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="5849d-133">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="5849d-134">**Exportar**</span><span class="sxs-lookup"><span data-stu-id="5849d-134">**Export**</span></span>  
     <span data-ttu-id="5849d-135">Abra uma caixa de diálogo que permita exportar as informações mostradas na grade **Resumo do arquivo de log** para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="5849d-135">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="5849d-136">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="5849d-136">**Refresh**</span></span>  
     <span data-ttu-id="5849d-137">Atualize a exibição dos logs selecionados.</span><span class="sxs-lookup"><span data-stu-id="5849d-137">Refresh the view of the selected logs.</span></span> <span data-ttu-id="5849d-138">O botão **Atualizar** relê os logs selecionados do servidor de destino ao aplicar qualquer configuração de filtro.</span><span class="sxs-lookup"><span data-stu-id="5849d-138">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="5849d-139">**Filter**</span><span class="sxs-lookup"><span data-stu-id="5849d-139">**Filter**</span></span>  
     <span data-ttu-id="5849d-140">Abra uma caixa de diálogo que permita especificar configurações usadas para filtrar o arquivo de log, como **Conexão**, **Data**ou outros critérios de filtragem **Gerais** .</span><span class="sxs-lookup"><span data-stu-id="5849d-140">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="5849d-141">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="5849d-141">**Search**</span></span>  
     <span data-ttu-id="5849d-142">Pesquise o texto específico no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="5849d-142">Search the log file for specific text.</span></span> <span data-ttu-id="5849d-143">Não há suporte à pesquisa com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="5849d-143">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="5849d-144">**Parar**</span><span class="sxs-lookup"><span data-stu-id="5849d-144">**Stop**</span></span>  
     <span data-ttu-id="5849d-145">Interrompe o carregamento das entradas do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="5849d-145">Stops loading the log file entries.</span></span> <span data-ttu-id="5849d-146">Por exemplo, você poderá usar essa opção se um arquivo de log remoto ou offline demorar muito tempo para ser carregado e você desejar exibir apenas as entradas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="5849d-146">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="5849d-147">**Resumo do arquivo de log**</span><span class="sxs-lookup"><span data-stu-id="5849d-147">**Log file summary**</span></span>  
     <span data-ttu-id="5849d-148">Esse painel de informações exibe um resumo da filtragem do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="5849d-148">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="5849d-149">Se o arquivo não for filtrado, você verá o seguinte texto, **Nenhum filtro aplicado**.</span><span class="sxs-lookup"><span data-stu-id="5849d-149">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="5849d-150">Se um filtro for aplicado ao log, você verá o seguinte texto **Filtrar entradas do log em que:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="5849d-150">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="5849d-151">**Detalhes da linha selecionada**</span><span class="sxs-lookup"><span data-stu-id="5849d-151">**Selected row details**</span></span>  
     <span data-ttu-id="5849d-152">Selecione uma linha para exibir detalhes adicionais sobre a linha de evento selecionada na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="5849d-152">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="5849d-153">As colunas podem ser reordenadas arrastando-as para locais novos na grade.</span><span class="sxs-lookup"><span data-stu-id="5849d-153">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="5849d-154">As colunas podem ser redimensionadas arrastando para a esquerda ou direta as barras separadoras de coluna no cabeçalho de grade.</span><span class="sxs-lookup"><span data-stu-id="5849d-154">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="5849d-155">Clique duas vezes nas barras separadoras de coluna no cabeçalho da grade para dimensionar automaticamente a coluna para a largura do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5849d-155">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="5849d-156">**Instância**</span><span class="sxs-lookup"><span data-stu-id="5849d-156">**Instance**</span></span>  
     <span data-ttu-id="5849d-157">O nome da instância do na qual ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="5849d-157">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="5849d-158">Esse nome é exibido como *nome do computador*\\*nome da instância*.</span><span class="sxs-lookup"><span data-stu-id="5849d-158">This is displayed as *computer name*\\*instance name*.</span></span>  
  
     <span data-ttu-id="5849d-159">**Data**</span><span class="sxs-lookup"><span data-stu-id="5849d-159">**Date**</span></span>  
     <span data-ttu-id="5849d-160">Exibe a data do evento.</span><span class="sxs-lookup"><span data-stu-id="5849d-160">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="5849d-161">**Origem**</span><span class="sxs-lookup"><span data-stu-id="5849d-161">**Source**</span></span>  
     <span data-ttu-id="5849d-162">Exibe o recurso de origem do qual o evento é criado, como o nome do serviço (MSSQLSERVER, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="5849d-162">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="5849d-163">Isso não é exibido para todos os tipos de log.</span><span class="sxs-lookup"><span data-stu-id="5849d-163">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="5849d-164">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="5849d-164">**Message**</span></span>  
     <span data-ttu-id="5849d-165">Exibe todas as mensagens associadas ao evento.</span><span class="sxs-lookup"><span data-stu-id="5849d-165">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="5849d-166">**Tipo de Log**</span><span class="sxs-lookup"><span data-stu-id="5849d-166">**Log Type**</span></span>  
     <span data-ttu-id="5849d-167">Exibe o tipo de log ao qual o evento pertence.</span><span class="sxs-lookup"><span data-stu-id="5849d-167">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="5849d-168">Todos os logs selecionados são exibidos na janela de resumo de arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="5849d-168">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="5849d-169">**Origem do Log**</span><span class="sxs-lookup"><span data-stu-id="5849d-169">**Log Source**</span></span>  
     <span data-ttu-id="5849d-170">Exibe uma descrição do log de origem no qual o evento é capturado.</span><span class="sxs-lookup"><span data-stu-id="5849d-170">Displays a description of the source log in which the event is captured.</span></span>  
  
5.  <span data-ttu-id="5849d-171">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5849d-171">When finished, click **Close**.</span></span>  
  
  
