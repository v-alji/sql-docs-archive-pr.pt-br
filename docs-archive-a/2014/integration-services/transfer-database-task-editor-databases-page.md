---
title: Editor da tarefa Transferir Banco de dados (página databases) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.database.f1
helpviewer_keywords:
- Transfer Database Task Editor
ms.assetid: ccdb74d0-4bea-420c-a726-2e0eb8957e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df4452e28a32463a7825e9c64cfd053f98c53ee8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678257"
---
# <a name="transfer-database-task-editor-databases-page"></a><span data-ttu-id="62907-102">Editor da Tarefa Transferir Banco de Dados (página Bancos de Dados)</span><span class="sxs-lookup"><span data-stu-id="62907-102">Transfer Database Task Editor (Databases Page)</span></span>
  <span data-ttu-id="62907-103">Use a página **Bancos de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** para especificar as propriedades para os bancos de dado de origem e de destino envolvidos na tarefa Transferir Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="62907-103">Use the **Databases** page of the **Transfer Database Task Editor** dialog box to specify properties for the source and destination databases involved in the Transfer Database task.</span></span> <span data-ttu-id="62907-104">A tarefa Transferir Banco de Dados copia ou move um bancos de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] entre duas instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62907-104">The Transfer Database task copies or moves a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database between two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62907-105">Essa tarefa também pode ser usada para copiar um banco de dados dentro do mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="62907-105">This task can also be used to copy a database within the same server.</span></span> <span data-ttu-id="62907-106">Para obter mais informações sobre essa tarefa, consulte [Tarefa Transferir Banco de Dados](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="62907-106">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="62907-107">Opções</span><span class="sxs-lookup"><span data-stu-id="62907-107">Options</span></span>  
 <span data-ttu-id="62907-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="62907-108">**SourceConnection**</span></span>  
 <span data-ttu-id="62907-109">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="62907-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="62907-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="62907-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="62907-111">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="62907-112">**DestinationDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="62907-112">**DestinationDatabaseName**</span></span>  
 <span data-ttu-id="62907-113">Especifique o nome do banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-113">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database on the destination server.</span></span>  
  
 <span data-ttu-id="62907-114">Para popular este campo automaticamente com o nome do banco de dados de origem, especifique o **SourceConnection** e **SourceDatabaseName** primeiro.</span><span class="sxs-lookup"><span data-stu-id="62907-114">To automatically populate this field with the source database name, specify the **SourceConnection** and **SourceDatabaseName** first.</span></span>  
  
 <span data-ttu-id="62907-115">Para renomear o banco de dados no servidor de destino, digite o novo nome neste campo.</span><span class="sxs-lookup"><span data-stu-id="62907-115">To rename the database on the destination server, type the new name in this field.</span></span>  
  
 <span data-ttu-id="62907-116">**DestinationDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="62907-116">**DestinationDatabaseFiles**</span></span>  
 <span data-ttu-id="62907-117">Especifica os nomes e locais dos arquivos de banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-117">Specifies the names and locations of the database files on the destination server.</span></span>  
  
 <span data-ttu-id="62907-118">Para popular este campo automaticamente com os nomes e locais de arquivo de banco de dados, especifique o **SourceConnection**, **SourceDatabaseName**e **SourceDatabaseFiles** primeiro.</span><span class="sxs-lookup"><span data-stu-id="62907-118">To automatically populate this field with the source database file names and locations, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first.</span></span>  
  
 <span data-ttu-id="62907-119">Para renomear os arquivos de banco de dados ou especificar os novos locais no servidor de destino, popule esse campo com as informações de banco de dados de origem e clique no botão Procurar.</span><span class="sxs-lookup"><span data-stu-id="62907-119">To rename the database files or to specify the new locations on the destination server, populate this field with the source database information, and then click the browse button.</span></span> <span data-ttu-id="62907-120">Na caixa de diálogo **Arquivos de banco de dados de destino** , edite o **Arquivo de Destino**, a **Pasta de Destino**ou o **Compartilhamento de Arquivos na Rede**.</span><span class="sxs-lookup"><span data-stu-id="62907-120">In the **Destination database files** dialog box, edit the **Destination File**, **Destination Folder**, or **Network File Share**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62907-121">Se você localizar os arquivos de banco de dados usando o botão Procurar, o local de arquivo será inserido usando a notação da unidade local: por exemplo, c:\\.</span><span class="sxs-lookup"><span data-stu-id="62907-121">If you locate the database files by using the browse button, the file location is entered using the local drive notation: for example, c:\\.</span></span> <span data-ttu-id="62907-122">É possível substituir isso pela a notação de compartilhamento na rede, inclusive o nome do computador e o nome de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="62907-122">You must replace this with the network share notation, including the computer name and share name.</span></span> <span data-ttu-id="62907-123">Se o compartilhamento administrativo padrão for usado, será necessário usar a notação de $ e ter acesso administrativo ao compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="62907-123">If the default administrative share is used, you must use the $ notation, and have administrative access to the share.</span></span>  
  
 <span data-ttu-id="62907-124">**DestinationOverwrite**</span><span class="sxs-lookup"><span data-stu-id="62907-124">**DestinationOverwrite**</span></span>  
 <span data-ttu-id="62907-125">Especifique se o é possível substituir o banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-125">Specify whether the database on the destination server can be overwritten.</span></span>  
  
 <span data-ttu-id="62907-126">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="62907-126">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="62907-127">Valor</span><span class="sxs-lookup"><span data-stu-id="62907-127">Value</span></span>|<span data-ttu-id="62907-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="62907-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="62907-129">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="62907-129">**True**</span></span>|<span data-ttu-id="62907-130">Substitui o banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-130">Overwrite destination server database.</span></span>|  
|<span data-ttu-id="62907-131">**Falso**</span><span class="sxs-lookup"><span data-stu-id="62907-131">**False**</span></span>|<span data-ttu-id="62907-132">Não substitui o banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-132">Do not overwrite destination server database.</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="62907-133">Os dados no banco de dados do servidor de destino serão substituídos se você especificar **True** para **DestinationOverwrite**, o que pode resultar na perda de dados.</span><span class="sxs-lookup"><span data-stu-id="62907-133">The data in the destination server database will be overwritten if you specify **True** for **DestinationOverwrite**, which may result in data loss.</span></span> <span data-ttu-id="62907-134">Para evitar isso, faça backup do banco de dados do servidor de destino em outro local antes de executar a tarefa Transferir Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="62907-134">To avoid this, back up the destination server database to another location before executing the Transfer Database task.</span></span>  
  
 <span data-ttu-id="62907-135">**Ação**</span><span class="sxs-lookup"><span data-stu-id="62907-135">**Action**</span></span>  
 <span data-ttu-id="62907-136">Especifique se a tarefa vai **Copiar** ou **Mover** o banco de dados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="62907-136">Specify whether the task will **Copy** or **Move** the database to the destination server.</span></span>  
  
 <span data-ttu-id="62907-137">**Método**</span><span class="sxs-lookup"><span data-stu-id="62907-137">**Method**</span></span>  
 <span data-ttu-id="62907-138">Especifique se a tarefa será executada enquanto o banco de dados no servidor de origem estiver no modo online ou offline.</span><span class="sxs-lookup"><span data-stu-id="62907-138">Specify whether the task will be executed while the database on the source server is in online or offline mode.</span></span>  
  
 <span data-ttu-id="62907-139">Para transferir um banco de dados usando o modo offline, é necessário que o usuário que executa o pacote seja um membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="62907-139">To transfer a database using offline mode, the user that runs the package must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="62907-140">Para transferir um banco de dados usando o modo online, é necessário que o usuário que executa o pacote seja um membro da função de servidor fixa **sysadmin** ou o proprietário do banco de dados (**dbo**) do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="62907-140">To transfer a database using the online mode, the user that runs the package must be a member of the **sysadmin** fixed server role, or the database owner (**dbo**) of the selected database.</span></span>  
  
 <span data-ttu-id="62907-141">**SourceDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="62907-141">**SourceDatabaseName**</span></span>  
 <span data-ttu-id="62907-142">Selecione o nome do banco de dados a ser copiado ou movido.</span><span class="sxs-lookup"><span data-stu-id="62907-142">Select the name of the database to be copied or moved.</span></span>  
  
 <span data-ttu-id="62907-143">**SourceDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="62907-143">**SourceDatabaseFiles**</span></span>  
 <span data-ttu-id="62907-144">Clique no botão Procurar para selecionar os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62907-144">Click the browse button to select the database files.</span></span>  
  
 <span data-ttu-id="62907-145">**ReattachSourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="62907-145">**ReattachSourceDatabase**</span></span>  
 <span data-ttu-id="62907-146">Especifique se a tarefa tentará anexar novamente o banco de dados de origem se ocorrer uma falha.</span><span class="sxs-lookup"><span data-stu-id="62907-146">Specify whether the task will attempt to reattach the source database if a failure occurs.</span></span>  
  
 <span data-ttu-id="62907-147">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="62907-147">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="62907-148">Valor</span><span class="sxs-lookup"><span data-stu-id="62907-148">Value</span></span>|<span data-ttu-id="62907-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="62907-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="62907-150">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="62907-150">**True**</span></span>|<span data-ttu-id="62907-151">Anexa novamente o banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="62907-151">Reattach source database.</span></span>|  
|<span data-ttu-id="62907-152">**Falso**</span><span class="sxs-lookup"><span data-stu-id="62907-152">**False**</span></span>|<span data-ttu-id="62907-153">Não anexa novamente o banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="62907-153">Do not reattach source database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62907-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62907-154">See Also</span></span>  
 <span data-ttu-id="62907-155">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="62907-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="62907-156">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="62907-156">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="62907-157">[Editor da tarefa Transferir Banco de dados &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="62907-157">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="62907-158">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="62907-158">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="62907-159">Gerenciador de Conexões SMO</span><span class="sxs-lookup"><span data-stu-id="62907-159">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
