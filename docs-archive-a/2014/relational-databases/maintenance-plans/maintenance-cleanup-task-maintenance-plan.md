---
title: Tarefa de limpeza de manutenção (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9023881ff5cf5ba5ddd8c61aa179c5881162bf44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574680"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a><span data-ttu-id="3f814-102">Tarefa de limpeza de manutenção (plano de manutenção)</span><span class="sxs-lookup"><span data-stu-id="3f814-102">Maintenance Cleanup Task (Maintenance Plan)</span></span>
  <span data-ttu-id="3f814-103">Use a **Tarefa de Limpeza de Manutenção** para remover arquivos antigos relacionados a planos de manutenção, inclusive relatórios de texto criados por planos de manutenção e arquivos de backup de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f814-103">Use the **Maintenance Cleanup Task** to remove old files related to maintenance plans, including text reports created by maintenance plans and database backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f814-104">A tarefa Limpeza de Manutenção não exclui automaticamente os arquivos nas subpastas do diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="3f814-104">The Maintenance Cleanup task does not automatically delete files in the subfolders of the specified directory.</span></span> <span data-ttu-id="3f814-105">Esse recurso reduz a possibilidade de um ataque mal-intencionado que use a tarefa de Limpeza de Manutenção para excluir arquivos.</span><span class="sxs-lookup"><span data-stu-id="3f814-105">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span> <span data-ttu-id="3f814-106">Se quiser excluir arquivos em subpastas de primeiro nível, você deverá selecionar **Incluir subpastas de primeiro nível**.</span><span class="sxs-lookup"><span data-stu-id="3f814-106">If you want to delete files in first-level subfolders, you must select **Include first-level subfolders**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3f814-107">Opções</span><span class="sxs-lookup"><span data-stu-id="3f814-107">Options</span></span>  
 <span data-ttu-id="3f814-108">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="3f814-108">**Connection**</span></span>  
 <span data-ttu-id="3f814-109">Exibe a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="3f814-109">Displays the current connection.</span></span>  
  
 <span data-ttu-id="3f814-110">**Novo**</span><span class="sxs-lookup"><span data-stu-id="3f814-110">**New**</span></span>  
 <span data-ttu-id="3f814-111">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="3f814-111">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="3f814-112">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f814-112">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="3f814-113">**Arquivos de backup**</span><span class="sxs-lookup"><span data-stu-id="3f814-113">**Backup files**</span></span>  
 <span data-ttu-id="3f814-114">Exclua arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="3f814-114">Delete backup files.</span></span>  
  
 <span data-ttu-id="3f814-115">**Relatórios de texto do Plano de Manutenção**</span><span class="sxs-lookup"><span data-stu-id="3f814-115">**Maintenance Plan text reports**</span></span>  
 <span data-ttu-id="3f814-116">Exclua relatórios de texto de planos de manutenção executados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3f814-116">Delete text reports of previously run maintenance plans.</span></span>  
  
 <span data-ttu-id="3f814-117">**Excluir arquivo específico**</span><span class="sxs-lookup"><span data-stu-id="3f814-117">**Delete specific file**</span></span>  
 <span data-ttu-id="3f814-118">Exclua o arquivo específico fornecido na caixa **Nome do arquivo** .</span><span class="sxs-lookup"><span data-stu-id="3f814-118">Delete the specific file provided in the **File name** box.</span></span>  
  
 <span data-ttu-id="3f814-119">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="3f814-119">**File name**</span></span>  
 <span data-ttu-id="3f814-120">Caminho e nome do arquivo a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="3f814-120">Path and name of the file to be deleted.</span></span>  
  
 <span data-ttu-id="3f814-121">**Pesquisar pasta e excluir arquivos com base em uma extensão**</span><span class="sxs-lookup"><span data-stu-id="3f814-121">**Search folder and delete files based on an extension**</span></span>  
 <span data-ttu-id="3f814-122">Exclua todos os arquivos com a extensão especificada na pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="3f814-122">Delete all files with the specified extension in the specified folder.</span></span> <span data-ttu-id="3f814-123">Use para excluir vários arquivos de uma vez, tais como todos os arquivos de backup com a extensão .bak, na pasta Terça-feira.</span><span class="sxs-lookup"><span data-stu-id="3f814-123">Use this to delete multiple files at once, such as all backup files with the .bak extension, in the Tuesday folder.</span></span>  
  
 <span data-ttu-id="3f814-124">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="3f814-124">**Folder**</span></span>  
 <span data-ttu-id="3f814-125">Caminho e nome da pasta que contém os arquivos a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="3f814-125">Path and name of the folder containing the files to be deleted.</span></span>  
  
 <span data-ttu-id="3f814-126">**Extensão de arquivo**</span><span class="sxs-lookup"><span data-stu-id="3f814-126">**File extension**</span></span>  
 <span data-ttu-id="3f814-127">Forneça a extensão de arquivo dos arquivos a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="3f814-127">Provide the file extension of the files to be deleted.</span></span>  
  
 <span data-ttu-id="3f814-128">**Incluir subpastas de primeiro nível**</span><span class="sxs-lookup"><span data-stu-id="3f814-128">**Include first-level subfolders**</span></span>  
 <span data-ttu-id="3f814-129">Exclua arquivos com a extensão especificada para **Extensão de arquivo** de subpastas de primeiro-nível em **Pasta**.</span><span class="sxs-lookup"><span data-stu-id="3f814-129">Delete files with the extension specified for **File extension** from first-level subfolders under **Folder**.</span></span>  
  
 <span data-ttu-id="3f814-130">**Excluir arquivos com base na idade do arquivo em tempo de execução da tarefa**</span><span class="sxs-lookup"><span data-stu-id="3f814-130">**Delete files based on the age of the file at task run time**</span></span>  
 <span data-ttu-id="3f814-131">Especifique a idade mínima dos arquivos que você deseja excluir fornecendo um número e unidade de tempo na caixa **Excluir arquivos com idade acima de** .</span><span class="sxs-lookup"><span data-stu-id="3f814-131">Specify the minimum age of the files that you want to delete by providing a number, and unit of time in the **Delete files older than the following** box.</span></span>  
  
 <span data-ttu-id="3f814-132">**Excluir arquivos com idade acima de**</span><span class="sxs-lookup"><span data-stu-id="3f814-132">**Delete files older than the following**</span></span>  
 <span data-ttu-id="3f814-133">Especifique a idade mínima dos arquivos que você deseja excluir, fornecendo um número e unidade de tempo (Dia, Semana, Mês ou Ano).</span><span class="sxs-lookup"><span data-stu-id="3f814-133">Specify the minimum age of the files that you want to delete by providing a number, and unit of time (Day, Week, Month, or Year).</span></span> <span data-ttu-id="3f814-134">Arquivos com idade acima do período especificado serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="3f814-134">Files older than the time frame specified will be deleted.</span></span>  
  
 <span data-ttu-id="3f814-135">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="3f814-135">**View T-SQL**</span></span>  
 <span data-ttu-id="3f814-136">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="3f814-136">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f814-137">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="3f814-137">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="3f814-138">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="3f814-138">New Connection Dialog Box</span></span>  
 <span data-ttu-id="3f814-139">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="3f814-139">**Connection name**</span></span>  
 <span data-ttu-id="3f814-140">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="3f814-140">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="3f814-141">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="3f814-141">**Select or enter a server name**</span></span>  
 <span data-ttu-id="3f814-142">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="3f814-142">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="3f814-143">**...**</span><span class="sxs-lookup"><span data-stu-id="3f814-143">**...**</span></span>  
 <span data-ttu-id="3f814-144">Selecione para exibir a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3f814-144">Select to view the list of available servers.</span></span>  
  
 <span data-ttu-id="3f814-145">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="3f814-145">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="3f814-146">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="3f814-146">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="3f814-147">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="3f814-147">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="3f814-148">Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] com a Autenticação do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3f814-148">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="3f814-149">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="3f814-149">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="3f814-150">Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3f814-150">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="3f814-151">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="3f814-151">This option is not available.</span></span>  
  
 <span data-ttu-id="3f814-152">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="3f814-152">**User name**</span></span>  
 <span data-ttu-id="3f814-153">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="3f814-153">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="3f814-154">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="3f814-154">This option is not available.</span></span>  
  
 <span data-ttu-id="3f814-155">**Senha**</span><span class="sxs-lookup"><span data-stu-id="3f814-155">**Password**</span></span>  
 <span data-ttu-id="3f814-156">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="3f814-156">Provide a password to use when authenticating.</span></span> <span data-ttu-id="3f814-157">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="3f814-157">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f814-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f814-158">See Also</span></span>  
 [<span data-ttu-id="3f814-159">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="3f814-159">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
