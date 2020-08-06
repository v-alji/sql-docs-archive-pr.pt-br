---
title: Editor da tarefa inserção em massa (página conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684306"
---
# <a name="bulk-insert-task-editor-connection-page"></a><span data-ttu-id="41e27-102">Editor da Tarefa Inserção em Massa (página Conexão)</span><span class="sxs-lookup"><span data-stu-id="41e27-102">Bulk Insert Task Editor (Connection Page)</span></span>
  <span data-ttu-id="41e27-103">Use a página **Conexão** da caixa de diálogo **Editor da Tarefa Inserção em Massa** para especificar a origem e o destino da operação de inserção em massa e o formato a ser usado.</span><span class="sxs-lookup"><span data-stu-id="41e27-103">Use the **Connection** page of the **Bulk Insert Task Editor** dialog box to specify the source and destination of the bulk insert operation and the format to use.</span></span>  
  
 <span data-ttu-id="41e27-104">Para saber mais sobre como trabalhar com inserções em massa, consulte [Tarefa Inserção em Massa](control-flow/bulk-insert-task.md) e [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="41e27-104">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="41e27-105">Opções</span><span class="sxs-lookup"><span data-stu-id="41e27-105">Options</span></span>  
 <span data-ttu-id="41e27-106">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="41e27-106">**Connection**</span></span>  
 <span data-ttu-id="41e27-107">Selecione um gerenciador de conexões OLE DB na lista ou clique em \<**New connection...**> para criar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="41e27-107">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="41e27-108">**Tópicos relacionados:** [Gerenciador de conexões OLE DB](connection-manager/ole-db-connection-manager.md), [Configurar Gerenciador de Conexões OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="41e27-108">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="41e27-109">**Tabela de Destino**</span><span class="sxs-lookup"><span data-stu-id="41e27-109">**DestinationTable**</span></span>  
 <span data-ttu-id="41e27-110">Digite o nome da tabela ou exibição de destino ou selecione uma tabela ou exibição na lista.</span><span class="sxs-lookup"><span data-stu-id="41e27-110">Type the name of the destination table or view or select a table or view in the list.</span></span>  
  
 <span data-ttu-id="41e27-111">**Formato**</span><span class="sxs-lookup"><span data-stu-id="41e27-111">**Format**</span></span>  
 <span data-ttu-id="41e27-112">Selecione a fonte do formato para a inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="41e27-112">Select the source of the format for the bulk insert.</span></span> <span data-ttu-id="41e27-113">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="41e27-113">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="41e27-114">Valor</span><span class="sxs-lookup"><span data-stu-id="41e27-114">Value</span></span>|<span data-ttu-id="41e27-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="41e27-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41e27-116">**Usar Arquivo**</span><span class="sxs-lookup"><span data-stu-id="41e27-116">**Use File**</span></span>|<span data-ttu-id="41e27-117">Selecione um arquivo que contém a especificação de formato.</span><span class="sxs-lookup"><span data-stu-id="41e27-117">Select a file containing the format specification.</span></span> <span data-ttu-id="41e27-118">Selecionar esta opção faz com que seja exibida a opção dinâmica **Arquivo de Formato**.</span><span class="sxs-lookup"><span data-stu-id="41e27-118">Selecting this option displays the dynamic option, **FormatFile**.</span></span>|  
|<span data-ttu-id="41e27-119">**Especificar**</span><span class="sxs-lookup"><span data-stu-id="41e27-119">**Specify**</span></span>|<span data-ttu-id="41e27-120">Especifique o formato.</span><span class="sxs-lookup"><span data-stu-id="41e27-120">Specify the format.</span></span> <span data-ttu-id="41e27-121">A seleção dessa opção exibe as opções dinâmicas `RowDelimiter` e `ColumnDelimiter` .</span><span class="sxs-lookup"><span data-stu-id="41e27-121">Selecting this option displays the dynamic options, `RowDelimiter` and `ColumnDelimiter`.</span></span>|  
  
 <span data-ttu-id="41e27-122">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="41e27-122">**File**</span></span>  
 <span data-ttu-id="41e27-123">Selecione um gerenciador de conexões de Arquivo ou de Arquivo Simple na lista ou clique em \<**New connection...**> para criar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="41e27-123">Select a File or Flat File connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="41e27-124">O local do arquivo está relacionado ao Mecanismo de Banco de Dados do SQL Server especificado no gerenciador de conexões para esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="41e27-124">The file location is relative to the SQL Server Database Engine specified in the connection manager for this task.</span></span> <span data-ttu-id="41e27-125">O arquivo de texto deve ser acessível pelo Mecanismo de Banco de Dados do SQL Server em um disco rígido local no servidor, por um compartilhamento ou unidade mapeada para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="41e27-125">The text file must be accessible by the SQL Server Database Engine either on a local hard drive on the server, or via a share or mapped drive to the SQL Server.</span></span> <span data-ttu-id="41e27-126">O arquivo não pode ser acessado pelo Runtime do SSIS.</span><span class="sxs-lookup"><span data-stu-id="41e27-126">The file is not accessed by the SSIS Runtime.</span></span>  
  
 <span data-ttu-id="41e27-127">Se você acessa o arquivo de origem usando um gerenciador de conexões de Arquivo Simples, a tarefa de Inserção em Massa não usa o formato especificado no gerenciador de conexões de Arquivos Simples.</span><span class="sxs-lookup"><span data-stu-id="41e27-127">If you access the source file by using a Flat File connection manager, the Bulk Insert task does not use the format specified in the Flat File connection manager.</span></span> <span data-ttu-id="41e27-128">Em vez disso, a tarefa de Inserção em massa usa o formato especificado em um arquivo de formato ou os valores das propriedades RowDelimiter e ColumnDelimiter da tarefa.</span><span class="sxs-lookup"><span data-stu-id="41e27-128">Instead, the Bulk Insert task uses either the format specified in a format file or the values of the RowDelimiter and ColumnDelimiter properties of the task.</span></span>  
  
 <span data-ttu-id="41e27-129">**Tópicos relacionados:** [Gerenciador de Conexões de Arquivo](connection-manager/file-connection-manager.md), [Editor do Gerenciador de Conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md), [Editor do Gerenciador de Conexões de Arquivos Simples](connection-manager/flat-file-connection-manager.md), [Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Geral&#41;](general-page-of-integration-services-designers-options.md), [Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Colunas&#41](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Avançado&#41](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span><span class="sxs-lookup"><span data-stu-id="41e27-129">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md), [Flat File Connection Manager](connection-manager/flat-file-connection-manager.md), [Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md), [Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span></span>  
  
 <span data-ttu-id="41e27-130">**Atualizar Tabelas**</span><span class="sxs-lookup"><span data-stu-id="41e27-130">**Refresh Tables**</span></span>  
 <span data-ttu-id="41e27-131">Atualize a lista de tabelas e exibições.</span><span class="sxs-lookup"><span data-stu-id="41e27-131">Refresh the list of tables and views.</span></span>  
  
## <a name="format-dynamic-options"></a><span data-ttu-id="41e27-132">Opções Dinâmicas de Formato</span><span class="sxs-lookup"><span data-stu-id="41e27-132">Format Dynamic Options</span></span>  
  
### <a name="format--use-file"></a><span data-ttu-id="41e27-133">Formato = Usar Arquivo</span><span class="sxs-lookup"><span data-stu-id="41e27-133">Format = Use File</span></span>  
 <span data-ttu-id="41e27-134">**Arquivo de Formato**</span><span class="sxs-lookup"><span data-stu-id="41e27-134">**FormatFile**</span></span>  
 <span data-ttu-id="41e27-135">Digite o caminho do arquivo de formato ou clique no botão de reticências **(…)** para localizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="41e27-135">Type the path of the format file or click the ellipsis button **(...)** to locate the format file.</span></span>  
  
### <a name="format--specify"></a><span data-ttu-id="41e27-136">Formato = Especificar</span><span class="sxs-lookup"><span data-stu-id="41e27-136">Format = Specify</span></span>  
 `RowDelimiter`  
 <span data-ttu-id="41e27-137">Especifique o delimitador de linhas no arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="41e27-137">Specify the row delimiter in the source file.</span></span> <span data-ttu-id="41e27-138">O valor padrão é **{CR}{LF}** .</span><span class="sxs-lookup"><span data-stu-id="41e27-138">The default value is **{CR}{LF}**.</span></span>  
  
 `ColumnDelimiter`  
 <span data-ttu-id="41e27-139">Especifique o delimitador de colunas no arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="41e27-139">Specify the column delimiter in the source file.</span></span> <span data-ttu-id="41e27-140">O padrão é **Tab**.</span><span class="sxs-lookup"><span data-stu-id="41e27-140">The default is **Tab**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e27-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="41e27-141">See Also</span></span>  
 <span data-ttu-id="41e27-142">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="41e27-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="41e27-143">[Editor da tarefa inserção em massa &#40;página Geral&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="41e27-143">[Bulk Insert Task Editor &#40;General Page&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="41e27-144">[Editor da tarefa inserção em massa &#40;página opções&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="41e27-144">[Bulk Insert Task Editor &#40;Options Page&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span></span>  
 <span data-ttu-id="41e27-145">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="41e27-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="41e27-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41e27-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="41e27-147">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="41e27-147">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
