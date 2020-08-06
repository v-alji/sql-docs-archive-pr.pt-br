---
title: 'Opções (editor de texto: guia Editor e página barra de status) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.editorcontextsettings
- VS.ToolsOptionsPages.Text_Editor.EditorTabAndStatusBar
ms.assetid: e4815678-7885-4631-878f-c6a2b857ee05
author: rothja
ms.author: jroth
ms.openlocfilehash: 920b7d48b5f7a2472a521af21c8217b1adba486a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582120"
---
# <a name="options-text-editor-editor-tab-and-status-bar-page"></a><span data-ttu-id="03b8e-102">Opções (página Editor de Texto: Guia Editor e Barra de Status)</span><span class="sxs-lookup"><span data-stu-id="03b8e-102">Options (Text Editor: Editor Tab and Status Bar Page)</span></span>
  <span data-ttu-id="03b8e-103">A **página Guia Editor e Barra de Status** permite que você personalize as informações exibidas pelos Editores de Consultas do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03b8e-103">The **Editor Tab and Status Bar Page** lets you customize the information displayed by the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Query Editors.</span></span> <span data-ttu-id="03b8e-104">Você pode especificar o nível de informações exibido na guia e na barra de status da janela Editor de Consulta e se a barra de status será exibida na parte superior ou parte inferior da janela do editor.</span><span class="sxs-lookup"><span data-stu-id="03b8e-104">You can specify the level of information displayed in the tab and status bar of the Query Editor window, and whether the status bar appears at the top or bottom of the editor window.</span></span>  
  
## <a name="option-settings-by-editor"></a><span data-ttu-id="03b8e-105">Configurações de opção por editor</span><span class="sxs-lookup"><span data-stu-id="03b8e-105">Option Settings by Editor</span></span>  
 <span data-ttu-id="03b8e-106">A guia Editor e a barra de status estão disponíveis em todos os editores do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , mas possuem níveis diferentes de funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="03b8e-106">The editor tab and the status bar are available in all of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, but have different levels of functionality.</span></span>  
  
 <span data-ttu-id="03b8e-107">O Editor de Consultas do Mecanismo de Banco de Dados pode se conectar a um grupo de servidores e, nesse caso, ele estabelece conexões com todas as instâncias no Grupo de Servidores e pode executar a mesma consulta simultaneamente em cada conexão.</span><span class="sxs-lookup"><span data-stu-id="03b8e-107">The Database Engine Query Editor can connect to a server group, in which case it opens connections to all the instances in the Server Group and can simultaneously run the same query on each connection.</span></span> <span data-ttu-id="03b8e-108">Você pode usar essa caixa de diálogo para especificar que a barra de status tenha cores diferentes quando estiver conectada a várias instâncias, em vez de a uma instância. Para alterar as opções de resultados de multisservidor, use a página [Opções (Resultados da consulta/SQL Server/Multisservidor)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) .</span><span class="sxs-lookup"><span data-stu-id="03b8e-108">You can use this dialog to specify that the status bar has different colors when connected to multiple instances rather than one instance.To change the multi-server results options, use the [Options (Query Results/SQL Server/Multi-Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) page.</span></span>  
  
## <a name="status-bar-content"></a><span data-ttu-id="03b8e-109">Conteúdo da barra de status</span><span class="sxs-lookup"><span data-stu-id="03b8e-109">Status Bar Content</span></span>  
 <span data-ttu-id="03b8e-110">Especifica as informações que aparecem na barra de status do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="03b8e-110">Specifies the information that appears in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="03b8e-111">**Exibe o tempo de execução**</span><span class="sxs-lookup"><span data-stu-id="03b8e-111">**Display execution time**</span></span>  
 <span data-ttu-id="03b8e-112">Inclui a hora de execução do script.</span><span class="sxs-lookup"><span data-stu-id="03b8e-112">Includes the script execution time.</span></span> <span data-ttu-id="03b8e-113">As configurações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="03b8e-113">The settings are as follows:</span></span>  
  
 <span data-ttu-id="03b8e-114">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="03b8e-114">**None**</span></span>  
 <span data-ttu-id="03b8e-115">A barra de status não exibe nenhuma informação de hora.</span><span class="sxs-lookup"><span data-stu-id="03b8e-115">The status bar displays no time information.</span></span>  
  
 <span data-ttu-id="03b8e-116">**End**</span><span class="sxs-lookup"><span data-stu-id="03b8e-116">**End**</span></span>  
 <span data-ttu-id="03b8e-117">A barra de status exibe a hora atual enquanto o script está em execução.</span><span class="sxs-lookup"><span data-stu-id="03b8e-117">The status bar displays the current time of day while the script is running.</span></span> <span data-ttu-id="03b8e-118">Quando o script é concluído, o vídeo exibe a hora em que o script foi concluído.</span><span class="sxs-lookup"><span data-stu-id="03b8e-118">When the script completes, the display shows the time of day that the script completed.</span></span>  
  
 <span data-ttu-id="03b8e-119">**Decorrido**</span><span class="sxs-lookup"><span data-stu-id="03b8e-119">**Elapsed**</span></span>  
 <span data-ttu-id="03b8e-120">A barra de status exibe o período de tempo que o script esteve em execução.</span><span class="sxs-lookup"><span data-stu-id="03b8e-120">The status bar displays the length of time that the script has been running.</span></span> <span data-ttu-id="03b8e-121">Quando o script é concluído, o vídeo exibe o período de temo gasto na execução do script.</span><span class="sxs-lookup"><span data-stu-id="03b8e-121">When the script completes, the display shows how much time was taken to run the script.</span></span>  
  
 <span data-ttu-id="03b8e-122">**Incluir o nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="03b8e-122">**Include database name**</span></span>  
 <span data-ttu-id="03b8e-123">Inclui o nome do banco de dados atual para a conexão.</span><span class="sxs-lookup"><span data-stu-id="03b8e-123">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="03b8e-124">Quando o editor de consultas é aberto pela primeira vez, esse é o banco de dados padrão para o logon.</span><span class="sxs-lookup"><span data-stu-id="03b8e-124">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="03b8e-125">O contexto do banco de dados pode ser alterado posteriormente com a instrução USE do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="03b8e-125">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="03b8e-126">**Incluir nome de logon**</span><span class="sxs-lookup"><span data-stu-id="03b8e-126">**Include login name**</span></span>  
 <span data-ttu-id="03b8e-127">Inclui o nome de logon.</span><span class="sxs-lookup"><span data-stu-id="03b8e-127">Includes the login name.</span></span>  
  
 <span data-ttu-id="03b8e-128">**Incluir contagem de linhas**</span><span class="sxs-lookup"><span data-stu-id="03b8e-128">**Include row count**</span></span>  
 <span data-ttu-id="03b8e-129">Inclui uma contagem das linhas que foram processadas pelo script atualmente em execução.</span><span class="sxs-lookup"><span data-stu-id="03b8e-129">Includes a count of the rows that have been processed by the script that is currently executing.</span></span>  
  
 <span data-ttu-id="03b8e-130">**Incluir nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="03b8e-130">**Include server name**</span></span>  
 <span data-ttu-id="03b8e-131">Inclui o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="03b8e-131">Includes the server name.</span></span> <span data-ttu-id="03b8e-132">Para conexões locais, esse é o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="03b8e-132">For local connections, this is the instance name.</span></span> <span data-ttu-id="03b8e-133">Para conexões remotas, esse é o nome do computador remoto e o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="03b8e-133">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="status-bar-layout-and-colors"></a><span data-ttu-id="03b8e-134">Layout e cores da barra de status</span><span class="sxs-lookup"><span data-stu-id="03b8e-134">Status Bar Layout and Colors</span></span>  
 <span data-ttu-id="03b8e-135">Especifica as cores dos itens na barra de status do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="03b8e-135">Specifies the colors for items in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="03b8e-136">**Conexões em grupo**</span><span class="sxs-lookup"><span data-stu-id="03b8e-136">**Group connections**</span></span>  
 <span data-ttu-id="03b8e-137">Define a cor da barra de status para quando o Editor de Consultas tiver mais de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="03b8e-137">Set the color of the status bar when the Query Editor has more than one connection.</span></span>  
  
 <span data-ttu-id="03b8e-138">**Conexões de servidor único**</span><span class="sxs-lookup"><span data-stu-id="03b8e-138">**Single server connections**</span></span>  
 <span data-ttu-id="03b8e-139">Define a cor da barra de status para quando o Editor de Consultas tiver uma única conexão.</span><span class="sxs-lookup"><span data-stu-id="03b8e-139">Set the color of the status bar when the Query Editor has one connection.</span></span>  
  
 <span data-ttu-id="03b8e-140">**Local de barra de status**</span><span class="sxs-lookup"><span data-stu-id="03b8e-140">**Status bar location**</span></span>  
 <span data-ttu-id="03b8e-141">Especifica o local da barra de status.</span><span class="sxs-lookup"><span data-stu-id="03b8e-141">Specifies the location of the status bar.</span></span> <span data-ttu-id="03b8e-142">As configurações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="03b8e-142">The settings are as follows:</span></span>  
  
 <span data-ttu-id="03b8e-143">**Top**</span><span class="sxs-lookup"><span data-stu-id="03b8e-143">**Top**</span></span>  
 <span data-ttu-id="03b8e-144">A barra de status aparece na parte superior do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="03b8e-144">The status bar appears at the top of the Query Editor window.</span></span>  
  
 <span data-ttu-id="03b8e-145">**Menor**</span><span class="sxs-lookup"><span data-stu-id="03b8e-145">**Bottom**</span></span>  
 <span data-ttu-id="03b8e-146">A barra de status aparece na parte inferior da janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="03b8e-146">The status bar appears at the bottom of the Query Editor window.</span></span>  
  
## <a name="tab-text"></a><span data-ttu-id="03b8e-147">Texto da Guia</span><span class="sxs-lookup"><span data-stu-id="03b8e-147">Tab Text</span></span>  
 <span data-ttu-id="03b8e-148">Especifica o texto exibido na guia, na parte superior de uma janela Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="03b8e-148">Specifies the text that appears in the tab at the top of a Query Editor window.</span></span> <span data-ttu-id="03b8e-149">Se o texto for muito longo para ser exibido, você poderá visualizar toda a cadeia de caracteres em uma dica de ferramenta que é exibida quando você passa o mouse sobre a guia.</span><span class="sxs-lookup"><span data-stu-id="03b8e-149">If the text is too long to display, you can view the full string in a tooltip that is displayed if you hover over the tab.</span></span>  
  
 <span data-ttu-id="03b8e-150">**Incluir o nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="03b8e-150">**Include database name**</span></span>  
 <span data-ttu-id="03b8e-151">Inclui o nome do banco de dados atual para a conexão.</span><span class="sxs-lookup"><span data-stu-id="03b8e-151">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="03b8e-152">Quando o editor de consultas é aberto pela primeira vez, esse é o banco de dados padrão para o logon.</span><span class="sxs-lookup"><span data-stu-id="03b8e-152">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="03b8e-153">O contexto do banco de dados pode ser alterado posteriormente com a instrução USE do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="03b8e-153">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="03b8e-154">**Incluir nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="03b8e-154">**Include file name**</span></span>  
 <span data-ttu-id="03b8e-155">Inclui o nome do arquivo no qual o script está armazenado.</span><span class="sxs-lookup"><span data-stu-id="03b8e-155">Includes the name of the file where the script is stored.</span></span>  
  
 <span data-ttu-id="03b8e-156">**Incluir nome da pasta**</span><span class="sxs-lookup"><span data-stu-id="03b8e-156">**Include folder name**</span></span>  
 <span data-ttu-id="03b8e-157">Inclui o caminho da pasta na qual o arquivo de script está armazenado.</span><span class="sxs-lookup"><span data-stu-id="03b8e-157">Includes the path of the folder where the script file is stored.</span></span>  
  
 <span data-ttu-id="03b8e-158">**Incluir nome de logon**</span><span class="sxs-lookup"><span data-stu-id="03b8e-158">**Include login name**</span></span>  
 <span data-ttu-id="03b8e-159">Inclui o nome de logon.</span><span class="sxs-lookup"><span data-stu-id="03b8e-159">Includes the login name.</span></span>  
  
 <span data-ttu-id="03b8e-160">**Incluir nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="03b8e-160">**Include server name**</span></span>  
 <span data-ttu-id="03b8e-161">Inclui o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="03b8e-161">Includes the server name.</span></span> <span data-ttu-id="03b8e-162">Para conexões locais, esse é o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="03b8e-162">For local connections, this is the instance name.</span></span> <span data-ttu-id="03b8e-163">Para conexões remotas, esse é o nome do computador remoto e o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="03b8e-163">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b8e-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="03b8e-164">See Also</span></span>  
 <span data-ttu-id="03b8e-165">[Opções &#40;ambiente: página fontes e cores&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span><span class="sxs-lookup"><span data-stu-id="03b8e-165">[Options &#40;Environment: Fonts and Colors Page&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span></span>  
 [<span data-ttu-id="03b8e-166">Codificação por cores no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="03b8e-166">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
  
  
