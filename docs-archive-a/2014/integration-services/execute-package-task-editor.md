---
title: Editor da tarefa Executar Pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.parameter.F1
- sql12.dts.designer.executepackagetask.package.f1
- sql12.dts.designer.executepackagetask.general.f1
ms.assetid: c2c96b4f-eb10-4d8b-be34-88edfd0785fb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9b2e18516e1f5c1b7af56bd1e84ef875557fd49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574797"
---
# <a name="execute-package-task-editor"></a><span data-ttu-id="e1e94-102">Editor da tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="e1e94-102">Execute Package Task Editor</span></span>
  <span data-ttu-id="e1e94-103">Use o Editor da tarefa Executar Pacote para configurar a Tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-103">Use the Execute Package Task Editor to configure the Execute Package Task.</span></span> <span data-ttu-id="e1e94-104">A tarefa Executar Pacote estende os recursos empresariais do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ao permitir que pacotes executem outros pacotes como parte de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-104">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="e1e94-105">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="e1e94-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="e1e94-106">Abrir o editor da tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="e1e94-106">Open the Execute Package Task Editor</span></span>](#open)  
  
-   [<span data-ttu-id="e1e94-107">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="e1e94-107">Set the Options on the General Page</span></span>](#general)  
  
-   [<span data-ttu-id="e1e94-108">Definir as opções na página Pacote</span><span class="sxs-lookup"><span data-stu-id="e1e94-108">Set the Options on the Package Page</span></span>](#package)  
  
-   [<span data-ttu-id="e1e94-109">Defina as opções na Página Associação de Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e1e94-109">Set the Options on the Parameter Bindings Page</span></span>](#parameter)  
  
##  <a name="open-the-execute-package-task-editor"></a><a name="open"></a> <span data-ttu-id="e1e94-110">Abrir o editor da tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="e1e94-110">Open the Execute Package Task Editor</span></span>  
  
1.  <span data-ttu-id="e1e94-111">Abra um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] que contém um tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-111">Open an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] that contains an Execute Package task.</span></span>  
  
2.  <span data-ttu-id="e1e94-112">Clique com o botão direito do mouse na tarefa no Designer SSIS e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1e94-112">Right-click the task in the SSIS Designer, and then click **Edit**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="e1e94-113">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="e1e94-113">Set the Options on the General Page</span></span>  
 <span data-ttu-id="e1e94-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e1e94-114">**Name**</span></span>  
 <span data-ttu-id="e1e94-115">Forneça um nome exclusivo para a tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-115">Provide a unique name for the Execute Package task.</span></span> <span data-ttu-id="e1e94-116">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="e1e94-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1e94-117">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="e1e94-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e1e94-118">**Description**</span></span>  
 <span data-ttu-id="e1e94-119">Digite uma descrição para a tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-119">Type a description of the Execute Package task.</span></span>  
  
##  <a name="set-the-options-on-the-package-page"></a><a name="package"></a> <span data-ttu-id="e1e94-120">Definir as opções na página Pacote</span><span class="sxs-lookup"><span data-stu-id="e1e94-120">Set the Options on the Package Page</span></span>  
 <span data-ttu-id="e1e94-121">**ReferenceType**</span><span class="sxs-lookup"><span data-stu-id="e1e94-121">**ReferenceType**</span></span>  
 <span data-ttu-id="e1e94-122">Selecione **Referência do Projeto** para pacotes filho que estão no projeto.</span><span class="sxs-lookup"><span data-stu-id="e1e94-122">Select **Project Reference** for child packages that are in the project.</span></span> <span data-ttu-id="e1e94-123">Selecione **Referência Externa** para pacotes filho localizados fora do pacote</span><span class="sxs-lookup"><span data-stu-id="e1e94-123">Select **External Reference** for child packages that are located outside the package</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1e94-124">A opção **ReferenceType** é somente leitura e será definida como **Referência Externa** se o projeto que contém o pacote não tiver sido convertido no modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="e1e94-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="e1e94-125">Para obter mais informações sobre conversão, consulte [Implantar projetos no Servidor do Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1e94-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="e1e94-126">**Senha**</span><span class="sxs-lookup"><span data-stu-id="e1e94-126">**Password**</span></span>  
 <span data-ttu-id="e1e94-127">Se o pacote filho for protegido por senha, forneça a senha dele ou clique no botão de reticências (...) e crie uma senha para ele.</span><span class="sxs-lookup"><span data-stu-id="e1e94-127">If the child package is password protected, provide the password for the child package, or click the ellipsis button (...) and create a new password for the child package.</span></span>  
  
 `ExecuteOutOfProcess`  
 <span data-ttu-id="e1e94-128">Especifique se o pacote filho é executado no processo do pacote pai ou um processo separado.</span><span class="sxs-lookup"><span data-stu-id="e1e94-128">Specify whether the child package runs in the process of the parent package or in a separate process.</span></span> <span data-ttu-id="e1e94-129">Por padrão, a Propriedade ExecuteOutOfProcess da tarefa executar pacote é definida como `False` e o pacote filho é executado no mesmo processo que o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="e1e94-129">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="e1e94-130">Se você definir esta propriedade como `true`, o pacote filho será executado em um processo separado.</span><span class="sxs-lookup"><span data-stu-id="e1e94-130">If you set this property to `true`, the child package runs in a separate process.</span></span> <span data-ttu-id="e1e94-131">Isto pode reduzir a velocidade do lançamento do pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-131">This may slow down the launching of the child package.</span></span> <span data-ttu-id="e1e94-132">Além disso, se a propriedade foi definida como `true`, você não poderá depurar o pacote em uma instalação somente ferramentas; você deve instalar o produto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1e94-132">In addition, if set the property to `true`, you cannot debug the package in a tools-only install; you must install the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] product.</span></span> <span data-ttu-id="e1e94-133">Para obter mais informações, consulte [Instalar o Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1e94-133">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
### <a name="referencetype-dynamic-options"></a><span data-ttu-id="e1e94-134">Opções dinâmicas ReferenceType</span><span class="sxs-lookup"><span data-stu-id="e1e94-134">ReferenceType Dynamic Options</span></span>  
  
#### <a name="referencetype--external-reference"></a><span data-ttu-id="e1e94-135">ReferenceType = referência externa</span><span class="sxs-lookup"><span data-stu-id="e1e94-135">ReferenceType = External Reference</span></span>  
 <span data-ttu-id="e1e94-136">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="e1e94-136">**Location**</span></span>  
 <span data-ttu-id="e1e94-137">Selecione o local de armazenamento do pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-137">Select the location of the child package.</span></span> <span data-ttu-id="e1e94-138">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e1e94-138">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="e1e94-139">Valor</span><span class="sxs-lookup"><span data-stu-id="e1e94-139">Value</span></span>|<span data-ttu-id="e1e94-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1e94-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1e94-141">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e1e94-141">**SQL Server**</span></span>|<span data-ttu-id="e1e94-142">Defina o local como uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1e94-142">Set the location to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="e1e94-143">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="e1e94-143">**File system**</span></span>|<span data-ttu-id="e1e94-144">Defina o local para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e1e94-144">Set the location to the file system.</span></span>|  
  
 <span data-ttu-id="e1e94-145">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="e1e94-145">**Connection**</span></span>  
 <span data-ttu-id="e1e94-146">Selecione o tipo de local de armazenamento para o pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-146">Select the type of storage location for the child package.</span></span>  
  
 <span data-ttu-id="e1e94-147">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="e1e94-147">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="e1e94-148">Exibe o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-148">Displays the package name.</span></span>  
  
#### <a name="referencetype--project-reference"></a><span data-ttu-id="e1e94-149">ReferenceType = referência do projeto</span><span class="sxs-lookup"><span data-stu-id="e1e94-149">ReferenceType = Project Reference</span></span>  
 <span data-ttu-id="e1e94-150">**PackageNameFromProjectReference**</span><span class="sxs-lookup"><span data-stu-id="e1e94-150">**PackageNameFromProjectReference**</span></span>  
 <span data-ttu-id="e1e94-151">Selecione um pacote contido no projeto para ser o pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-151">Select a package contained in the project, to be the child package.</span></span>  
  
### <a name="location-dynamic-options"></a><span data-ttu-id="e1e94-152">Opções Dinâmicas de Local</span><span class="sxs-lookup"><span data-stu-id="e1e94-152">Location Dynamic Options</span></span>  
  
#### <a name="location--sql-server"></a><span data-ttu-id="e1e94-153">Local = SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1e94-153">Location = SQL Server</span></span>  
 <span data-ttu-id="e1e94-154">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="e1e94-154">**Connection**</span></span>  
 <span data-ttu-id="e1e94-155">Selecione um gerenciador de conexões OLE DB na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="e1e94-155">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="e1e94-156">**Tópicos relacionados:** [Gerenciador de conexões OLE DB](connection-manager/ole-db-connection-manager.md), [Configurar Gerenciador de Conexões OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e1e94-156">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="e1e94-157">**PackageName**</span><span class="sxs-lookup"><span data-stu-id="e1e94-157">**PackageName**</span></span>  
 <span data-ttu-id="e1e94-158">Digite o nome do pacote filho ou clique nas reticências (...) e localize o pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-158">Type the name of the child package, or click the ellipsis (...) and then locate the package.</span></span>  
  
#### <a name="location--file-system"></a><span data-ttu-id="e1e94-159">Local = Sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="e1e94-159">Location = File system</span></span>  
 <span data-ttu-id="e1e94-160">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="e1e94-160">**Connection**</span></span>  
 <span data-ttu-id="e1e94-161">Selecione um gerenciador de conexões de Arquivos na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="e1e94-161">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="e1e94-162">**Tópicos relacionados:** [Gerenciador de conexões de arquivos](connection-manager/file-connection-manager.md), [Editor do Gerenciador de conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="e1e94-162">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="e1e94-163">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="e1e94-163">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="e1e94-164">Exibe o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="e1e94-164">Displays the package name.</span></span>  
  
##  <a name="set-the-options-on-the-parameter-bindings-page"></a><a name="parameter"></a> <span data-ttu-id="e1e94-165">Defina as opções na Página Associação de Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e1e94-165">Set the Options on the Parameter Bindings Page</span></span>  
 <span data-ttu-id="e1e94-166">Você pode passar valores do pacote pai ou do projeto para o pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-166">You can pass values from the parent package or the project, to the child package.</span></span> <span data-ttu-id="e1e94-167">O projeto deve usar o modelo de implantação de projeto e o pacote filho deve ser contido no mesmo projeto que contém o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="e1e94-167">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span>  
  
 <span data-ttu-id="e1e94-168">Para obter mais informações sobre conversão de um projeto para o modelo de implantação de projetos, consulte [Implantar projetos no Servidor do Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1e94-168">For information about converting projects to the project deployment model, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="e1e94-169">**Parâmetro de pacote filho**</span><span class="sxs-lookup"><span data-stu-id="e1e94-169">**Child package parameter**</span></span>  
 <span data-ttu-id="e1e94-170">Insira ou selecione um nome para o parâmetro de pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-170">Enter or select a name for the child package parameter.</span></span>  
  
 <span data-ttu-id="e1e94-171">**Parâmetro ou variável de associação**</span><span class="sxs-lookup"><span data-stu-id="e1e94-171">**Binding parameter or variable**</span></span>  
 <span data-ttu-id="e1e94-172">Selecione o parâmetro ou variável que contêm o valor que você quer passar para o pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-172">Select the parameter or variable that contains the value that you want to pass to the child package.</span></span>  
  
 <span data-ttu-id="e1e94-173">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="e1e94-173">**Add**</span></span>  
 <span data-ttu-id="e1e94-174">Clique para mapear um parâmetro ou variável para um parâmetro de pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-174">Click to map a parameter or variable to a child package parameter.</span></span>  
  
 <span data-ttu-id="e1e94-175">**Remover**</span><span class="sxs-lookup"><span data-stu-id="e1e94-175">**Remove**</span></span>  
 <span data-ttu-id="e1e94-176">Clique para remover um mapeamento entre um parâmetro ou variável e um parâmetro de pacote filho.</span><span class="sxs-lookup"><span data-stu-id="e1e94-176">Click to remove a mapping between a parameter or variable and a child package parameter.</span></span>  
  
  
