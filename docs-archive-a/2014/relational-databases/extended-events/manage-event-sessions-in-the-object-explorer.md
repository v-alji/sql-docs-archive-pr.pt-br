---
title: Gerenciar sessões de evento no Pesquisador de Objetos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 16849e38-d3fb-414d-8dcb-797b5ffce6ee
author: rothja
ms.author: jroth
ms.openlocfilehash: 1aa33a97137f63348898e6b1fcb7b19b2d218573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569467"
---
# <a name="manage-event-sessions-in-the-object-explorer"></a><span data-ttu-id="61f64-102">Gerenciar sessões de evento no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="61f64-102">Manage Event Sessions in the Object Explorer</span></span>
  <span data-ttu-id="61f64-103">Este tópico aborda as ações que você pode executar no **Pesquisador de Objetos** que afetam os Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="61f64-103">This topic discusses the actions you can take in **Object Explorer** that affect Extended Events:</span></span>  
  
-   <span data-ttu-id="61f64-104">Criar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-104">Create an Extended Events Session</span></span>  
  
-   <span data-ttu-id="61f64-105">Iniciando ou interrompendo uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-105">Starting or Stopping an Extended Events Session</span></span>  
  
-   <span data-ttu-id="61f64-106">Exportar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-106">Export an Extended Events Session</span></span>  
  
-   <span data-ttu-id="61f64-107">Importar um modelo da sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-107">Import an Extended Events Session Template</span></span>  
  
-   <span data-ttu-id="61f64-108">Editar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-108">Edit an Extended Events Session</span></span>  
  
-   <span data-ttu-id="61f64-109">Excluir uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-109">Delete an Extended Events Session</span></span>  
  
## <a name="create-an-extended-events-session"></a><span data-ttu-id="61f64-110">Criar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-110">Create an Extended Events Session</span></span>  
 <span data-ttu-id="61f64-111">Para obter mais informações sobre como criar uma sessão de Eventos Estendidos, consulte [Criar uma sessão de Eventos Estendidos](../../database-engine/create-an-extended-events-session.md).</span><span class="sxs-lookup"><span data-stu-id="61f64-111">For more information about creating an Extended Events session, see [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span></span>  
  
## <a name="starting-or-stopping-an-extended-events-session"></a><span data-ttu-id="61f64-112">Iniciando ou interrompendo uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-112">Starting or Stopping an Extended Events Session</span></span>  
 <span data-ttu-id="61f64-113">Você pode iniciar ou parar uma sessão de eventos estendidos por meio do **Editor de consultas** usando a `ALTER EVENT SESSION` instrução ou usando o nó **eventos estendidos** do **pesquisador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="61f64-113">You can start or stop an Extended Events session through the **Query Editor** using the `ALTER EVENT SESSION` statement, or by using the **Extended Events** node of **Object Explorer**.</span></span>  
  
 <span data-ttu-id="61f64-114">Quando você interrompe uma sessão de eventos, a sessão não é mais listada como uma sessão ativa no DMV (exibição de gerenciamento dinâmico) sys.dm_xe_sessions.</span><span class="sxs-lookup"><span data-stu-id="61f64-114">When you stop an event session, the session is no longer listed as an active session in the sys.dm_xe_sessions dynamic management view (DMV).</span></span> <span data-ttu-id="61f64-115">No entanto, a definição de sessão permanece intacta e você pode reiniciar a sessão.</span><span class="sxs-lookup"><span data-stu-id="61f64-115">However, the session definition remains intact, and you can restart the session.</span></span> <span data-ttu-id="61f64-116">Para remover completamente uma definição de sessão, você deve excluir a sessão.</span><span class="sxs-lookup"><span data-stu-id="61f64-116">To completely remove a session definition, you must delete the session.</span></span>  
  
 <span data-ttu-id="61f64-117">Para iniciar ou interromper uma sessão de Eventos Estendidos, você deve ter a permissão ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="61f64-117">To start or stop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="61f64-118">Ao interromper uma sessão que usa um destino na memória, como o buffer de anéis, particionamento, emparelhamento de eventos ou destinos do contador de eventos síncrono, todas as informações armazenadas no buffer da sessão (a coluna target_data do sys.dm_xe_session_targets DMV) serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="61f64-118">When you stop a session that uses an in-memory target, such as the ring buffer, bucketing, event pairing, or synchronous event counter targets, all the information stored in the session's buffer (the target_data column of the sys.dm_xe_session_targets DMV) will be lost.</span></span> <span data-ttu-id="61f64-119">Para acessar os dados do evento após interromper a sessão, salve os dados antes de interrompê-la ou configure a sessão para usar o destino de arquivo.</span><span class="sxs-lookup"><span data-stu-id="61f64-119">To access event data after you stop the session, you should either save the data before you stop the session, or configure the session to use the file target.</span></span>  
  
### <a name="start-or-stop-an-extended-events-session-using-query-editor"></a><span data-ttu-id="61f64-120">Iniciar ou interromper uma sessão de Eventos Estendidos usando o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="61f64-120">Start or Stop an Extended Events Session Using Query Editor</span></span>  
 <span data-ttu-id="61f64-121">Para iniciar uma sessão, emita as seguintes instruções, substituindo *session_name* pelo nome da sessão de Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="61f64-121">To start a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = START  
```  
  
 <span data-ttu-id="61f64-122">Para interromper uma sessão, emita as seguintes instruções, substituindo *session_name* pelo nome da sessão de Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="61f64-122">To stop a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = STOP  
```  
  
### <a name="start-or-stop-an-extended-events-session-in-object-explorer"></a><span data-ttu-id="61f64-123">Iniciar ou interromper uma sessão de Eventos Estendidos no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="61f64-123">Start or Stop an Extended Events Session in Object Explorer</span></span>  
 <span data-ttu-id="61f64-124">Para iniciar ou interromper uma sessão de Eventos Estendidos no **Pesquisador de Objetos**, expanda os nós **Gerenciamento**, **Eventos Estendidos**e **Sessões** , clique com o botão direito do mouse em uma sessão e clique em **Iniciar Sessão** ou **Interromper Sessão**.</span><span class="sxs-lookup"><span data-stu-id="61f64-124">To start or stop an Extended Events session in **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes and right click on a session and then click **Start Session** or **Stop Session**.</span></span>  
  
## <a name="export-an-extended-events-session-template"></a><span data-ttu-id="61f64-125">Exportar um modelo da sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-125">Export an Extended Events Session Template</span></span>  
 <span data-ttu-id="61f64-126">Você pode exportar uma sessão de Eventos Estendidos usando o **Pesquisador de Objetos**e salvá-la como um arquivo de modelo .xml.</span><span class="sxs-lookup"><span data-stu-id="61f64-126">You can export an Extended Events session using **Object Explorer**, and save it as an .xml template file.</span></span> <span data-ttu-id="61f64-127">Por exemplo, talvez você queira exportar uma sessão e aplicar o modelo a uma nova sessão de eventos usando o **Assistente para Nova Sessão** ou o assistente **Nova Sessão** .</span><span class="sxs-lookup"><span data-stu-id="61f64-127">For example, you may want to export a session and then apply the template to a new event session using the **New Session Wizard** or the **New Session** wizard.</span></span>  
  
 <span data-ttu-id="61f64-128">Quando você exportar uma sessão, não se esqueça de salvar o arquivo de modelo em um local que use o sistema de arquivos NTFS e de restringir o acesso aos usuários que tenham autorização para exibir as informações.</span><span class="sxs-lookup"><span data-stu-id="61f64-128">When you export a session, make sure that you save the template file to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="61f64-129">Para exportar uma sessão de Eventos Estendidos usando o **Pesquisador de Objetos**:</span><span class="sxs-lookup"><span data-stu-id="61f64-129">To export an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="61f64-130">Expanda os nós **Gerenciamento**, **Eventos Estendidos**e **Sessões**</span><span class="sxs-lookup"><span data-stu-id="61f64-130">Expand the **Management**, **Extended Events**, and then **Sessions** nodes</span></span>  
  
2.  <span data-ttu-id="61f64-131">Clique com o botão direito do mouse na sessão a ser exportada e selecione **Export Session (Exportar Sessão)** .</span><span class="sxs-lookup"><span data-stu-id="61f64-131">Right-click the session that you want to export, and select **Export Session**.</span></span>  
  
3.  <span data-ttu-id="61f64-132">Na caixa de diálogo **Salvar Como** , selecione um local para salvar o arquivo, digite o nome do arquivo na caixa **Nome de arquivo** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="61f64-132">In the **Save As** dialog box, select a location to save the file, type the file name in the **File name** box, and then click **Save**.</span></span>  
  
     <span data-ttu-id="61f64-133">Se você salvar o arquivo no local de modelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] padrão, o modelo aparecerá na lista suspensa de modelos predefinidos quando você usar o **Assistente para Nova Sessão** e a caixa de diálogo **Nova Sessão** .</span><span class="sxs-lookup"><span data-stu-id="61f64-133">If you save the file to the default [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] template location, the template will appear in the dropdown list of predefined templates when you use the **New Session Wizard** and **New Session** dialog.</span></span>  
  
## <a name="import-an-extended-events-session-template"></a><span data-ttu-id="61f64-134">Importar um modelo da sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-134">Import an Extended Events Session Template</span></span>  
 <span data-ttu-id="61f64-135">Usando o **Pesquisador de Objetos**, você pode importar um modelo para uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="61f64-135">Using **Object Explorer**, you can import a template for an Extended Events session.</span></span> <span data-ttu-id="61f64-136">Por exemplo, talvez você queira fazer isso para criar uma sessão de um modelo que foi exportado de outra instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61f64-136">For example, you may want to do this to create a session from a template that was exported from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="61f64-137">Para importar uma sessão de Eventos Estendidos, você deve ter as permissões `ALTER ANY EVENT SESSION` necessárias.</span><span class="sxs-lookup"><span data-stu-id="61f64-137">To import an Extended Events session, you must have the necessary `ALTER ANY EVENT SESSION` permissions.</span></span>  
  
 <span data-ttu-id="61f64-138">Antes de importar um arquivo de modelo, verifique se ele é de uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="61f64-138">Before you import a template file, make sure that the file is from a trusted source.</span></span> <span data-ttu-id="61f64-139">os arquivos de modelo devem ser salvos em um local que use o sistema de arquivos NTFS e onde o acesso aos usuários que tenham autorização para exibir as informações seja restrito.</span><span class="sxs-lookup"><span data-stu-id="61f64-139">Template files should be saved to a location that uses the NTFS file system and where access is restricted to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="61f64-140">Para importar uma sessão de Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="61f64-140">To import an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="61f64-141">No **Pesquisador de Objetos**, expanda os nós **Gerenciamento**e **Eventos Estendidos** .</span><span class="sxs-lookup"><span data-stu-id="61f64-141">In **Object Explorer**, expand the **Management**, and then **Extended Events** nodes.</span></span>  
  
2.  <span data-ttu-id="61f64-142">Clique com o botão direito do mouse em **Sessões** e selecione **Nova Sessão**.</span><span class="sxs-lookup"><span data-stu-id="61f64-142">Right-click **Sessions** and select **New Session**.</span></span>  
  
3.  <span data-ttu-id="61f64-143">Especifique um nome para a sessão.</span><span class="sxs-lookup"><span data-stu-id="61f64-143">Specify a name for the session.</span></span>  
  
4.  <span data-ttu-id="61f64-144">Expanda a caixa suspensa **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="61f64-144">Expand the **Template** drop down box.</span></span>  
  
5.  <span data-ttu-id="61f64-145">Clique em **\<File From ...>Abrir** e procure a sessão (arquivo XML) a ser importada.</span><span class="sxs-lookup"><span data-stu-id="61f64-145">Click **\<File From ...>Open** and browse for the session (XML file) you want to import.</span></span>  
  
 <span data-ttu-id="61f64-146">A sessão aparece abaixo do nó **Sessões** .</span><span class="sxs-lookup"><span data-stu-id="61f64-146">The session appears under the **Sessions** node.</span></span> <span data-ttu-id="61f64-147">Por padrão, a sessão não é iniciada.</span><span class="sxs-lookup"><span data-stu-id="61f64-147">By default, the session is not started.</span></span>  
  
## <a name="edit-an-extended-events-session"></a><span data-ttu-id="61f64-148">Editar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-148">Edit an Extended Events Session</span></span>  
 <span data-ttu-id="61f64-149">Você pode editar uma sessão de Eventos Estendidos no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="61f64-149">You can edit an Extended Events session in Object Explorer.</span></span>  
  
 <span data-ttu-id="61f64-150">Para editar uma sessão de Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="61f64-150">To edit an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="61f64-151">No **Pesquisador de Objetos**, expanda os nós **Gerenciamento**, **Eventos Estendidos**e **Sessões** .</span><span class="sxs-lookup"><span data-stu-id="61f64-151">In **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="61f64-152">Clique com o botão direito do mouse em uma sessão e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="61f64-152">Right-click a session and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="61f64-153">Na seção **Selecionar uma página** , selecione as páginas que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="61f64-153">In the **Select a page** section, select the page or pages you want to edit.</span></span>  
  
4.  <span data-ttu-id="61f64-154">Depois que você terminar de revisar a sessão de eventos, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="61f64-154">After you finish revising the event session, click **OK**.</span></span>  
  
## <a name="script-an-event-session-definition-using-tsql"></a><span data-ttu-id="61f64-155">Criar o script de uma definição de sessão de eventos usando o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61f64-155">Script an Event Session Definition Using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
 <span data-ttu-id="61f64-156">O Assistente para Nova Sessão e a caixa de diálogo Nova Sessão têm uma opção Script que gera o [!INCLUDE[tsql](../../includes/tsql-md.md)] que define a sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="61f64-156">Both the New Session Wizard and the New Session dialog have a Script option that generates the [!INCLUDE[tsql](../../includes/tsql-md.md)] that defines the Extended Events session.</span></span>  
  
 <span data-ttu-id="61f64-157">Você pode acessar o [!INCLUDE[tsql](../../includes/tsql-md.md)] de uma sessão de Eventos Estendidos existente clicando o botão direito do mouse no nome da sessão, selecionando **Sessão de Script como**e selecionando **Create para**.</span><span class="sxs-lookup"><span data-stu-id="61f64-157">You can access the [!INCLUDE[tsql](../../includes/tsql-md.md)] for an existing Extended Events session by right clicking the session name, selecting **Script Session as**, and then selecting **Create to**.</span></span>  
  
## <a name="delete-an-extended-events-session"></a><span data-ttu-id="61f64-158">Excluir uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="61f64-158">Delete an Extended Events Session</span></span>  
 <span data-ttu-id="61f64-159">Você pode excluir uma sessão de Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="61f64-159">You can delete an Extended Events session:</span></span>  
  
-   <span data-ttu-id="61f64-160">No Editor de Consultas, usando `DROP EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="61f64-160">In Query Editor using `DROP EVENT SESSION`.</span></span>  
  
-   <span data-ttu-id="61f64-161">No **Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="61f64-161">In **Object Explorer**.</span></span>  
  
 <span data-ttu-id="61f64-162">Quando você exclui uma sessão de eventos, todas as informações de configuração são removidas e a definição de sessão não aparece mais na exibição de catálogo sys.server_event_sessions.</span><span class="sxs-lookup"><span data-stu-id="61f64-162">When you delete an event session, all configuration information is removed and the session definition no longer appears in the sys.server_event_sessions catalog view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61f64-163">system_health e AlwaysOn_health estão incluídos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; não os exclua.</span><span class="sxs-lookup"><span data-stu-id="61f64-163">system_health and AlwaysOn_health are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; do not delete them.</span></span> <span data-ttu-id="61f64-164">system_health é habilitada por padrão (para obter mais informações, consulte [Usar a sessão de system_health](use-the-ssms-xe-profiler.md)).</span><span class="sxs-lookup"><span data-stu-id="61f64-164">system_health is enabled by default (for more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md)).</span></span> <span data-ttu-id="61f64-165">AlwaysOn_health está desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="61f64-165">AlwaysOn_health is off by default.</span></span> <span data-ttu-id="61f64-166">Essas sessões coletam dados que podem ser úteis para diagnosticar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="61f64-166">These sessions collect data that can be useful for diagnosing performance issues.</span></span>  
  
 <span data-ttu-id="61f64-167">Para excluir uma sessão de Eventos Estendidos, você deve ter a permissão ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="61f64-167">To delete an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="61f64-168">Para excluir uma sessão de Eventos Estendidos no **Pesquisador de Objetos**:</span><span class="sxs-lookup"><span data-stu-id="61f64-168">To delete an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="61f64-169">Expanda os nós **Gerenciamento**, **Eventos Estendidos**e **Sessões** .</span><span class="sxs-lookup"><span data-stu-id="61f64-169">Expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="61f64-170">Clique com o botão direito do mouse em uma sessão e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="61f64-170">Right-click a session and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="61f64-171">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="61f64-171">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="61f64-172">Depois que você terminar de revisar a sessão de eventos, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="61f64-172">After you finish revising the event session, click **OK**.</span></span>  
  
 <span data-ttu-id="61f64-173">Para excluir uma sessão de Eventos Estendidos no **Editor de Consultas**, emita as seguintes instruções, substituindo *session_name* pelo nome da sessão de Eventos Estendidos que você deseja excluir:</span><span class="sxs-lookup"><span data-stu-id="61f64-173">To delete an Extended Events session in the **Query Editor**, Issue the following statements, replacing *session_name* with the name of the Extended Events session that you want to delete:</span></span>  
  
```  
DROP EVENT SESSION [session_name]  
ON SERVER  
```  
  
  
