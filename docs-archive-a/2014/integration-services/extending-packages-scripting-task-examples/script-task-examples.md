---
title: Exemplos de Tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], examples
- examples [Integration Services]
- SSIS Script task, examples
ms.assetid: b0dd77ee-ee11-4cd9-87aa-61dd67f2fe1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 920d2ee5cc2e64db1048d10522d9be644794e55b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680983"
---
# <a name="script-task-examples"></a><span data-ttu-id="bc22e-102">Exemplos de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-102">Script Task Examples</span></span>
  <span data-ttu-id="bc22e-103">A tarefa Script é uma ferramenta com vários fins que pode ser usada em um pacote para preencher quase todos os requisitos que não sejam satisfeitos pelas tarefas incluídas no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc22e-103">The Script task is a multi-purpose tool that you can use in a package to fill almost any requirement that is not met by the tasks included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="bc22e-104">Este tópico lista exemplos de código da tarefa Script, que demonstram algumas das funcionalidades disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bc22e-104">This topic lists Script task code samples that demonstrate some of the available functionality.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc22e-105">Se desejar criar tarefas mais fáceis de serem reutilizadas em vários pacotes, procure utilizar o código desses exemplos de tarefa Script como o ponto inicial para tarefas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="bc22e-105">If you want to create tasks that you can more easily reuse across multiple packages, consider using the code in these Script task samples as the starting point for custom tasks.</span></span> <span data-ttu-id="bc22e-106">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="bc22e-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc22e-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bc22e-107">In This Section</span></span>  
  
### <a name="example-topics"></a><span data-ttu-id="bc22e-108">Tópicos de exemplo</span><span class="sxs-lookup"><span data-stu-id="bc22e-108">Example Topics</span></span>  
 <span data-ttu-id="bc22e-109">Esta seção contém exemplos de código que demonstram vários usos das classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que você pode incorporar em uma tarefa Script do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bc22e-109">This section contains code examples that demonstrate various uses of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that you can incorporate into an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task:</span></span>  
  
 [<span data-ttu-id="bc22e-110">Detectar um arquivo simples vazio com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-110">Detecting an Empty Flat File with the Script Task</span></span>](../extending-packages-scripting-task-examples/detecting-an-empty-flat-file-with-the-script-task.md)  
 <span data-ttu-id="bc22e-111">Verifica um arquivo simples para determinar se ele contém linhas de dados e salva o resultado em uma variável para ser usado na ramificação do fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="bc22e-111">Checks a flat file to determine whether it contains rows of data, and saves the result to a variable for use in control flow branching.</span></span>  
  
 [<span data-ttu-id="bc22e-112">Obter uma lista para o loop ForEach com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-112">Gathering a List for the ForEach Loop with the Script Task</span></span>](../extending-packages-scripting-task-examples/gathering-a-list-for-the-foreach-loop-with-the-script-task.md)  
 <span data-ttu-id="bc22e-113">Coleta uma lista de arquivos que satisfazem critérios especificados pelo usuário e preenche uma variável para ser usada posteriormente pelo Enumerador Foreach de Variável.</span><span class="sxs-lookup"><span data-stu-id="bc22e-113">Gathers a list of files that meet user-specified criteria, and populates a variable for later use by the Foreach from Variable Enumerator.</span></span>  
  
 [<span data-ttu-id="bc22e-114">Consultar o Active Directory com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-114">Querying the Active Directory with the Script Task</span></span>](../extending-packages-scripting-task-examples/querying-the-active-directory-with-the-script-task.md)  
 <span data-ttu-id="bc22e-115">Recupera informações de usuário do Active Directory com base no valor de uma variável do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], usando classes no namespace System.DirectoryServices.</span><span class="sxs-lookup"><span data-stu-id="bc22e-115">Retrieves user information from Active Directory based on the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, by using classes in the System.DirectoryServices namespace.</span></span>  
  
 [<span data-ttu-id="bc22e-116">Monitorar contadores de desempenho com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-116">Monitoring Performance Counters with the Script Task</span></span>](../extending-packages-scripting-task-examples/monitoring-performance-counters-with-the-script-task.md)  
 <span data-ttu-id="bc22e-117">Cria um contador de desempenho personalizado que pode ser usado para rastrear o progresso da execução de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], usando classes no namespace System.Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="bc22e-117">Creates a custom performance counter that can be used to track the execution progress of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, by using classes in the System.Diagnostics namespace.</span></span>  
  
 [<span data-ttu-id="bc22e-118">Trabalhar com imagens com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-118">Working with Images with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md)  
 <span data-ttu-id="bc22e-119">Compacta imagens no formato JPEG e cria imagens de miniatura, usando classes no namespace System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="bc22e-119">Compresses images into the JPEG format and creates thumbnail images from them, by using classes in the System.Drawing namespace.</span></span>  
  
 [<span data-ttu-id="bc22e-120">Localizar impressoras instaladas com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-120">Finding Installed Printers with the Script Task</span></span>](../extending-packages-scripting-task-examples/finding-installed-printers-with-the-script-task.md)  
 <span data-ttu-id="bc22e-121">Localiza impressoras instaladas compatíveis com um tamanho de papel específico, usando classes no namespace System.Drawing.Printing.</span><span class="sxs-lookup"><span data-stu-id="bc22e-121">Locates installed printers that support a specific paper size, by using classes in the System.Drawing.Printing namespace.</span></span>  
  
 [<span data-ttu-id="bc22e-122">Enviar uma mensagem de email HTML com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-122">Sending an HTML Mail Message with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-an-html-mail-message-with-the-script-task.md)  
 <span data-ttu-id="bc22e-123">Envia uma mensagem de email em formato HTML em vez de formato de texto sem-formatação.</span><span class="sxs-lookup"><span data-stu-id="bc22e-123">Sends a mail message in HTML format instead of plain text format.</span></span>  
  
 [<span data-ttu-id="bc22e-124">Trabalhar com arquivos do Excel com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-124">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
 <span data-ttu-id="bc22e-125">Lista as planilhas em um arquivo de Excel e verifica a existência de uma planilha específica.</span><span class="sxs-lookup"><span data-stu-id="bc22e-125">Lists the worksheets in an Excel file and checks for the existence of a specific worksheet.</span></span>  
  
 [<span data-ttu-id="bc22e-126">Enviar a uma fila de mensagens particular remota com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-126">Sending to a Remote Private Message Queue with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-to-a-remote-private-message-queue-with-the-script-task.md)  
 <span data-ttu-id="bc22e-127">Envia uma mensagem para uma fila de mensagens privada remota.</span><span class="sxs-lookup"><span data-stu-id="bc22e-127">Sends a message to a remote private message queue.</span></span>  
  
### <a name="other-examples"></a><span data-ttu-id="bc22e-128">Outros exemplos</span><span class="sxs-lookup"><span data-stu-id="bc22e-128">Other Examples</span></span>  
 <span data-ttu-id="bc22e-129">Os tópicos a seguir também contêm exemplos de código para uso com a tarefa Script:</span><span class="sxs-lookup"><span data-stu-id="bc22e-129">The following topics also contain code examples for use with the Script task:</span></span>  
  
 [<span data-ttu-id="bc22e-130">Usar variáveis na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-130">Using Variables in the Script Task</span></span>](../extending-packages-scripting/task/using-variables-in-the-script-task.md)  
 <span data-ttu-id="bc22e-131">Solicita que o usuário confirme se o pacote deve continuar sendo executado, com base no valor de uma variável de pacote que pode exceder o limite especificado em outra variável.</span><span class="sxs-lookup"><span data-stu-id="bc22e-131">Asks the user for confirmation of whether the package should continue to run, based on the value of a package variable that may exceed the limit specified in another variable.</span></span>  
  
 [<span data-ttu-id="bc22e-132">Conectar-se a fontes de dados na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-132">Connecting to Data Sources in the Script Task</span></span>](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md)  
 <span data-ttu-id="bc22e-133">Recupera uma conexão ou informações de conexão de gerenciadores de conexões definidos no pacote.</span><span class="sxs-lookup"><span data-stu-id="bc22e-133">Retrieves a connection or connection information from connection managers defined in the package.</span></span>  
  
 [<span data-ttu-id="bc22e-134">Gerar eventos na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="bc22e-134">Raising Events in the Script Task</span></span>](../extending-packages-scripting/task/raising-events-in-the-script-task.md)  
 <span data-ttu-id="bc22e-135">Aumenta um erro, uma advertência ou uma mensagem informativa com base no status da conexão de Internet no servidor.</span><span class="sxs-lookup"><span data-stu-id="bc22e-135">Raises an error, a warning, or an informational message based on the status of the Internet connection on the server.</span></span>  
  
 [<span data-ttu-id="bc22e-136">Registrar a tarefa Script em log</span><span class="sxs-lookup"><span data-stu-id="bc22e-136">Logging in the Script Task</span></span>](../extending-packages-scripting/task/logging-in-the-script-task.md)  
 <span data-ttu-id="bc22e-137">Registra o número de itens processados pela tarefa para provedores de log habilitados.</span><span class="sxs-lookup"><span data-stu-id="bc22e-137">Logs the number of items processed by the task to enabled log providers.</span></span>  
  
<span data-ttu-id="bc22e-138">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bc22e-138">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bc22e-139">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="bc22e-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bc22e-140">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="bc22e-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bc22e-141">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="bc22e-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
