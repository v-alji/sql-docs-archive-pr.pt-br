---
title: Ajuda F1 do Visualizador do Arquivo de Log | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.errorlog.f1
helpviewer_keywords:
- Log File Viewer
ms.assetid: 2243845c-4880-4aa0-9ee8-0a97a128996b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6eadb4baa4a47202b40a9cde1eca896022f31d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572544"
---
# <a name="log-file-viewer-f1-help"></a><span data-ttu-id="12cca-102">Ajuda F1 do Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="12cca-102">Log File Viewer F1 Help</span></span>
  <span data-ttu-id="12cca-103">O Visualizador do Arquivo de Log exibe informações de muitos componentes diferentes.</span><span class="sxs-lookup"><span data-stu-id="12cca-103">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="12cca-104">Quando o Visualizador do Arquivo de Log estiver aberto, use o painel **Selecionar logs** para selecionar os logs que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="12cca-104">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="12cca-105">Cada log exibe as colunas adequadas àquele tipo de log.</span><span class="sxs-lookup"><span data-stu-id="12cca-105">Each log displays columns appropriate to that kind of log.</span></span>  
  
 <span data-ttu-id="12cca-106">Os logs disponíveis dependem de como o Visualizador do Arquivo de Log é aberto.</span><span class="sxs-lookup"><span data-stu-id="12cca-106">The logs that are available depend on how Log File Viewer is opened.</span></span> <span data-ttu-id="12cca-107">Para obter mais informações, consulte [Abrir o Visualizador do Arquivo de Log](open-log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="12cca-107">For more information, see [Open Log File Viewer](open-log-file-viewer.md).</span></span>  
  
 <span data-ttu-id="12cca-108">O número de linhas exibidas para logs de auditoria pode ser configurado na página **Pesquisador de Objetos do SQL Server/Comandos** da caixa de diálogo **Ferramentas/Opções** .</span><span class="sxs-lookup"><span data-stu-id="12cca-108">The number of rows that are displayed for audit logs can be configured on the **SQL Server Object Explorer/Commands** page of the **Tools/Options** dialog box.</span></span> <span data-ttu-id="12cca-109">Para obter descrições das colunas exibidas para logs de auditoria, consulte [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12cca-109">For descriptions of the columns that are displayed for audit logs, see [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="12cca-110">Opções</span><span class="sxs-lookup"><span data-stu-id="12cca-110">Options</span></span>  
 <span data-ttu-id="12cca-111">**Carregar Log**</span><span class="sxs-lookup"><span data-stu-id="12cca-111">**Load Log**</span></span>  
 <span data-ttu-id="12cca-112">Abra uma caixa de diálogo onde seja possível especificar um arquivo de log a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="12cca-112">Open a dialog box where you can specify a log file to load.</span></span>  
  
 <span data-ttu-id="12cca-113">**Exportar**</span><span class="sxs-lookup"><span data-stu-id="12cca-113">**Export**</span></span>  
 <span data-ttu-id="12cca-114">Abra uma caixa de diálogo que permita exportar as informações mostradas na grade **Resumo do arquivo de log** para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="12cca-114">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
 <span data-ttu-id="12cca-115">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="12cca-115">**Refresh**</span></span>  
 <span data-ttu-id="12cca-116">Atualize a exibição dos logs selecionados.</span><span class="sxs-lookup"><span data-stu-id="12cca-116">Refresh the view of the selected logs.</span></span> <span data-ttu-id="12cca-117">O botão **Atualizar** relê os logs selecionados do servidor de destino ao aplicar qualquer configuração de filtro.</span><span class="sxs-lookup"><span data-stu-id="12cca-117">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
 <span data-ttu-id="12cca-118">**Filter**</span><span class="sxs-lookup"><span data-stu-id="12cca-118">**Filter**</span></span>  
 <span data-ttu-id="12cca-119">Abra uma caixa de diálogo que permita especificar configurações usadas para filtrar o arquivo de log, como **Conexão**, **Data**ou outros critérios de filtragem **Gerais** .</span><span class="sxs-lookup"><span data-stu-id="12cca-119">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
 <span data-ttu-id="12cca-120">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="12cca-120">**Search**</span></span>  
 <span data-ttu-id="12cca-121">Pesquise o texto específico no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="12cca-121">Search the log file for specific text.</span></span> <span data-ttu-id="12cca-122">Não há suporte à pesquisa com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="12cca-122">Searching with wildcard characters is not supported.</span></span>  
  
 <span data-ttu-id="12cca-123">**Parar**</span><span class="sxs-lookup"><span data-stu-id="12cca-123">**Stop**</span></span>  
 <span data-ttu-id="12cca-124">Interrompe o carregamento das entradas do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="12cca-124">Stops loading the log file entries.</span></span> <span data-ttu-id="12cca-125">Por exemplo, você poderá usar essa opção se um arquivo de log remoto ou offline demorar muito tempo para ser carregado e você desejar exibir apenas as entradas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="12cca-125">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
 <span data-ttu-id="12cca-126">**Resumo do arquivo de log**</span><span class="sxs-lookup"><span data-stu-id="12cca-126">**Log file summary**</span></span>  
 <span data-ttu-id="12cca-127">Esse painel de informações exibe um resumo da filtragem do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="12cca-127">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="12cca-128">Se o arquivo não for filtrado, você verá o seguinte texto, **Nenhum filtro aplicado**.</span><span class="sxs-lookup"><span data-stu-id="12cca-128">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="12cca-129">Se um filtro for aplicado ao log, você verá o seguinte texto **Filtrar entradas do log em que:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="12cca-129">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
 <span data-ttu-id="12cca-130">**Detalhes da linha selecionada**</span><span class="sxs-lookup"><span data-stu-id="12cca-130">**Selected row details**</span></span>  
 <span data-ttu-id="12cca-131">Selecione uma linha para exibir detalhes adicionais sobre a linha de evento selecionada na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="12cca-131">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="12cca-132">As colunas podem ser reordenadas arrastando-as para locais novos na grade.</span><span class="sxs-lookup"><span data-stu-id="12cca-132">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="12cca-133">As colunas podem ser redimensionadas arrastando para a esquerda ou direta as barras separadoras de coluna no cabeçalho de grade.</span><span class="sxs-lookup"><span data-stu-id="12cca-133">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="12cca-134">Clique duas vezes nas barras separadoras de coluna no cabeçalho da grade para dimensionar automaticamente a coluna para a largura do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="12cca-134">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
 <span data-ttu-id="12cca-135">**Instância**</span><span class="sxs-lookup"><span data-stu-id="12cca-135">**Instance**</span></span>  
 <span data-ttu-id="12cca-136">O nome da instância do na qual ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="12cca-136">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="12cca-137">Esse nome é exibido como *nome do computador*\\*nome da instância*.</span><span class="sxs-lookup"><span data-stu-id="12cca-137">This is displayed as *computer name*\\*instance name*.</span></span>  
  
## <a name="frequently-displayed-columns"></a><span data-ttu-id="12cca-138">Colunas exibidas frequentemente</span><span class="sxs-lookup"><span data-stu-id="12cca-138">Frequently Displayed Columns</span></span>  
 <span data-ttu-id="12cca-139">**Data**</span><span class="sxs-lookup"><span data-stu-id="12cca-139">**Date**</span></span>  
 <span data-ttu-id="12cca-140">Exibe a data do evento.</span><span class="sxs-lookup"><span data-stu-id="12cca-140">Displays the date of the event.</span></span>  
  
 <span data-ttu-id="12cca-141">**Origem**</span><span class="sxs-lookup"><span data-stu-id="12cca-141">**Source**</span></span>  
 <span data-ttu-id="12cca-142">Exibe o recurso de origem do qual o evento é criado, como o nome do serviço (MSSQLSERVER, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="12cca-142">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="12cca-143">Isso não é exibido para todos os tipos de log.</span><span class="sxs-lookup"><span data-stu-id="12cca-143">This does not appear for all log types.</span></span>  
  
 <span data-ttu-id="12cca-144">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="12cca-144">**Message**</span></span>  
 <span data-ttu-id="12cca-145">Exibe todas as mensagens associadas ao evento.</span><span class="sxs-lookup"><span data-stu-id="12cca-145">Displays any messages associated with the event.</span></span>  
  
 <span data-ttu-id="12cca-146">**Tipo de Log**</span><span class="sxs-lookup"><span data-stu-id="12cca-146">**Log Type**</span></span>  
 <span data-ttu-id="12cca-147">Exibe o tipo de log ao qual o evento pertence.</span><span class="sxs-lookup"><span data-stu-id="12cca-147">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="12cca-148">Todos os logs selecionados são exibidos na janela de resumo de arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="12cca-148">All selected logs appear in the log file summary window.</span></span>  
  
 <span data-ttu-id="12cca-149">**Origem do Log**</span><span class="sxs-lookup"><span data-stu-id="12cca-149">**Log Source**</span></span>  
 <span data-ttu-id="12cca-150">Exibe uma descrição do log de origem no qual o evento é capturado.</span><span class="sxs-lookup"><span data-stu-id="12cca-150">Displays a description of the source log in which the event is captured.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="12cca-151">Permissões</span><span class="sxs-lookup"><span data-stu-id="12cca-151">Permissions</span></span>  
 <span data-ttu-id="12cca-152">Para acessar arquivos de log de instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que estão online, é necessária associação na função de servidor fixa securityadmin.</span><span class="sxs-lookup"><span data-stu-id="12cca-152">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="12cca-153">Para acessar arquivos de log de instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que estão offline, é necessário ter acesso de leitura no namespace do WMI **Root\Microsoft\SqlServer\ComputerManagement10** e na pasta em que os arquivos de log estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="12cca-153">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="12cca-154">Para obter mais informações, veja a seção Segurança do tópico [Exibir arquivos de log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="12cca-154">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cca-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12cca-155">See Also</span></span>  
 <span data-ttu-id="12cca-156">[Visualizador do Arquivo de Log](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="12cca-156">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="12cca-157">[Abrir o Visualizador do Arquivo de Log](open-log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="12cca-157">[Open Log File Viewer](open-log-file-viewer.md) </span></span>  
 [<span data-ttu-id="12cca-158">Exibir arquivos de log offline</span><span class="sxs-lookup"><span data-stu-id="12cca-158">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
