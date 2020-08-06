---
title: Importar e exportar pacotes (serviço SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], importing
- packages [Integration Services], exporting
- importing packages
- exporting packages
ms.assetid: ef18ec11-b536-47d9-abd1-794099f43486
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b69f9d23431ed86f6b84be6857b7104cd8ba3dcc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575957"
---
# <a name="import-and-export-packages-ssis-service"></a><span data-ttu-id="42b25-102">Importar e exportar pacotes (serviço SSIS)</span><span class="sxs-lookup"><span data-stu-id="42b25-102">Import and Export Packages (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="42b25-103">Esse tópico discute o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , um serviço do Windows para o gerenciamento de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42b25-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="42b25-104">dá suporte ao serviço para compatibilidade de versões anteriores com versões anteriores do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b25-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="42b25-105">A partir do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], você pode gerenciar objetos como pacotes no servidor do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="42b25-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="42b25-106">Os pacotes podem ser salvos na tabela sysssispackages no banco de dados msdb do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="42b25-106">Packages can be saved either in the sysssispackages table in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database or in the file system.</span></span>  
  
 <span data-ttu-id="42b25-107">O repositório de pacotes, que é o armazenamento lógico que o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] monitora e gerencia, pode incluir o banco de dados msdb e as pastas do sistema de arquivos especificadas no arquivo de configuração para o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42b25-107">The package store, which is the logical storage that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service monitors and manages, can include both the msdb database and the file system folders specified in the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="42b25-108">Você pode importar e exportar pacotes entre os seguintes tipos de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="42b25-108">You can import and export packages between the following storage types:</span></span>  
  
-   <span data-ttu-id="42b25-109">Pastas do sistema de arquivos em qualquer lugar do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="42b25-109">File system folders anywhere in the file system.</span></span>  
  
-   <span data-ttu-id="42b25-110">Pastas no repositório de pacotes SSIS.</span><span class="sxs-lookup"><span data-stu-id="42b25-110">Folders in the SSIS Package Store.</span></span> <span data-ttu-id="42b25-111">As duas pastas padrão são nomeadas Sistema de Arquivos e MSDB.</span><span class="sxs-lookup"><span data-stu-id="42b25-111">The two default folders are named File System and MSDB.</span></span>  
  
-   <span data-ttu-id="42b25-112">O banco de dados msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42b25-112">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="42b25-113">permite importar e exportar pacotes e, ao fazer isso, alterar o formato de armazenamento e o local de pacotes.</span><span class="sxs-lookup"><span data-stu-id="42b25-113">gives you the ability to import and export packages, and by doing this change the storage format and location of packages.</span></span> <span data-ttu-id="42b25-114">Usando os recursos de importação e exportação, você pode adicionar pacotes ao sistema de arquivos, ao repositório de pacotes ou ao banco de dados msdb e copiar pacotes de um formato de armazenamento para outro.</span><span class="sxs-lookup"><span data-stu-id="42b25-114">Using the import and export features, you can add packages to the file system, package store, or msdb database, and copy packages from one storage format to another.</span></span> <span data-ttu-id="42b25-115">Por exemplo, os pacotes salvos no msdb podem ser copiados para o sistema de arquivos e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="42b25-115">For example, packages saved in msdb can be copied to the file system and vice versa.</span></span>  
  
 <span data-ttu-id="42b25-116">Você também pode copiar um pacote em um formato diferente por meio do utilitário do prompt de comando **dtutil** (dtutil.exe).</span><span class="sxs-lookup"><span data-stu-id="42b25-116">You can also copy a package to a different format using the **dtutil** command prompt utility (dtutil.exe).</span></span> <span data-ttu-id="42b25-117">Para obter mais informações, consulte [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="42b25-117">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="to-import-or-export-a-package"></a><span data-ttu-id="42b25-118">Para importar ou exportar um pacote</span><span class="sxs-lookup"><span data-stu-id="42b25-118">To import or export a package</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42b25-119">Este tópico discute o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que faz parte do [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b25-119">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that is part of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="42b25-120">dá suporte ao serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para compatibilidade de versões anteriores com o [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b25-120">supports the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for backward compatibility with [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="42b25-121">Para obter mais informações sobre o gerenciamento de pacotes no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], consulte [Servidor do Integration Services &#40;SSIS&#41;](catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="42b25-121">For information about managing packages in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], see [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="42b25-122">Você pode importar ou exportar um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] de ou para os seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="42b25-122">You can import or export an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from or to the following locations:</span></span>  
  
-   <span data-ttu-id="42b25-123">É possível importar um pacote armazenado em uma instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], no sistema de arquivos ou no repositório de pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b25-123">You can import a package that is stored in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], in the file system, or in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span> <span data-ttu-id="42b25-124">O pacote importado é salvo no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou em uma pasta do armazenamento de pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42b25-124">The imported package is saved to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to a folder in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span>  
  
-   <span data-ttu-id="42b25-125">É possível exportar um pacote armazenado em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], no sistema de arquivos ou no Repositório de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] para outro formato e outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="42b25-125">You can export a package that is stored in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the file system, or the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store to a different storage format and location.</span></span>  
  
 <span data-ttu-id="42b25-126">No entanto, existem algumas restrições sobre a importação e a exportação de pacotes entre diferentes versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="42b25-126">However, there are some restrictions on importing and exporting a package between different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="42b25-127">Em uma instância do [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], você pode importar pacotes de uma instância do [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], mas não é possível exportar pacotes para uma instância do [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b25-127">On an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], you can import packages from an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], but you cannot export packages to an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="42b25-128">Em uma instância do [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], você não pode importar pacotes de, ou exportar pacotes para, uma instância do [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b25-128">On an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you cannot import packages from, or export packages to, an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="42b25-129">Os procedimentos a seguir descrevem como usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para importar ou exportar um pacote.</span><span class="sxs-lookup"><span data-stu-id="42b25-129">The following procedures describe how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to import or export a package.</span></span>  
  
#### <a name="to-import-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="42b25-130">Para importar um pacote usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="42b25-130">To import a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="42b25-131">Clique em **Iniciar**, aponte para **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="42b25-131">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="42b25-132">Na caixa de diálogo **Conectar ao Servidor** , defina as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="42b25-132">In the **Connect to Server** dialog box set the following options:</span></span>  
  
    -   <span data-ttu-id="42b25-133">Na caixa **Tipo de servidor** , selecione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="42b25-133">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="42b25-134">Na caixa **Nome do servidor**, forneça um nome do servidor ou clique em **\<Browse for more...>** e localize o servidor a ser usado.</span><span class="sxs-lookup"><span data-stu-id="42b25-134">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="42b25-135">Se o Pesquisador de Objetos não estiver aberto, clique em **Pesquisador de Objetos** no menu **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="42b25-135">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="42b25-136">No Pesquisador de Objetos, expanda a pasta **Pacotes Armazenados** .</span><span class="sxs-lookup"><span data-stu-id="42b25-136">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="42b25-137">Expanda as subpastas para localizar a pasta para a qual você deseja importar um pacote.</span><span class="sxs-lookup"><span data-stu-id="42b25-137">Expand the subfolders to locate the folder into which you want to import a package.</span></span>  
  
6.  <span data-ttu-id="42b25-138">Clique com o botão direito do mouse na pasta e clique em **Importar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="42b25-138">Right-click the folder, click **Import Package**.</span></span> <span data-ttu-id="42b25-139">Em seguida, proceda de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="42b25-139">and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="42b25-140">Para importar de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], selecione a opção **SQL Server** e depois especifique o servidor e selecione o modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="42b25-140">To import from an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="42b25-141">Se você selecionar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="42b25-141">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="42b25-142">Clique no botão Procurar **(...)** , selecione o pacote para importar e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="42b25-142">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
    -   <span data-ttu-id="42b25-143">Para importar do sistema de arquivos, selecione a opção **Sistema de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="42b25-143">To import from the file system, select the **File system** option.</span></span>  
  
         <span data-ttu-id="42b25-144">Clique no botão Procurar **(...)** , selecione o pacote para importar e então clique em **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="42b25-144">Click the browse button **(...)**, select the package to import, and then click **Open.**</span></span>  
  
    -   <span data-ttu-id="42b25-145">Para importar usando o Repositório de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] , selecione a opção **Repositório de Pacotes SSIS** e especifique o servidor.</span><span class="sxs-lookup"><span data-stu-id="42b25-145">To import from the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, select the **SSIS Package Store** option and specify the server.</span></span>  
  
         <span data-ttu-id="42b25-146">Clique no botão Procurar **(...)** , selecione o pacote para importar e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="42b25-146">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="42b25-147">Opcionalmente, atualize o nome de pacote.</span><span class="sxs-lookup"><span data-stu-id="42b25-147">Optionally, update the package name.</span></span>  
  
8.  <span data-ttu-id="42b25-148">Para atualizar o nível de proteção do pacote, clique no botão Procurar **(...)** e, na caixa de diálogo **Nível de Proteção do Pacote**, escolha um nível de proteção diferente.</span><span class="sxs-lookup"><span data-stu-id="42b25-148">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="42b25-149">Se a opção **Criptografar dados confidenciais com senhas** ou **Criptografar todos os dados com senhas** for selecionada, digite e confirme uma senha.</span><span class="sxs-lookup"><span data-stu-id="42b25-149">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
9. <span data-ttu-id="42b25-150">Clique em **OK** para concluir a importação.</span><span class="sxs-lookup"><span data-stu-id="42b25-150">Click **OK** to complete the import.</span></span>  
  
#### <a name="to-export-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="42b25-151">Para exportar um pacote usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="42b25-151">To export a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="42b25-152">Clique em **Iniciar**, aponte para **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="42b25-152">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="42b25-153">Na caixa de diálogo **Conectar ao Servidor** , defina as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="42b25-153">In the **Connect to Server** dialog box, set the following options:</span></span>  
  
    -   <span data-ttu-id="42b25-154">Na caixa **Tipo de servidor** , selecione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="42b25-154">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="42b25-155">Na caixa **Nome do servidor**, forneça um nome do servidor ou clique em **\<Browse for more...>** e localize o servidor a ser usado.</span><span class="sxs-lookup"><span data-stu-id="42b25-155">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="42b25-156">Se o Pesquisador de Objetos não estiver aberto, clique em **Pesquisador de Objetos** no menu **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="42b25-156">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="42b25-157">No Pesquisador de Objetos, expanda a pasta **Pacotes Armazenados** .</span><span class="sxs-lookup"><span data-stu-id="42b25-157">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="42b25-158">Expanda as subpastas para localizar o pacote que deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="42b25-158">Expand the subfolders to locate the package you want to export.</span></span>  
  
6.  <span data-ttu-id="42b25-159">Clique com o botão direito do mouse no pacote, clique em **Exportar**e depois execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="42b25-159">Right-click the package, click **Export**, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="42b25-160">Para exportar para uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], selecione a opção **SQL Server** e depois especifique o servidor e selecione o modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="42b25-160">To export to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="42b25-161">Se você selecionar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="42b25-161">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="42b25-162">Clique no botão Procurar **(...)** e expanda a pasta do **Pacotes SSIS** para localizar a pasta na qual deseja salvar o pacote.</span><span class="sxs-lookup"><span data-stu-id="42b25-162">Click the browse button **(...)**, and expand the **SSIS Packages** folder to locate the folder to which you want to save the package.</span></span> <span data-ttu-id="42b25-163">Opcionalmente, atualize o nome padrão do pacote e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42b25-163">Optionally, update the default name of the package, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="42b25-164">Para exportar para o sistema de arquivos, selecione a opção **Sistema de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="42b25-164">To export to the file system, select the **File System** option.</span></span>  
  
         <span data-ttu-id="42b25-165">Clique no botão Procurar **(...)** para localizar a pasta para a qual deseja exportar o pacote, digite o nome do arquivo do pacote e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="42b25-165">Click the browse button **(...)** to locate the folder to which you want to export the package, type the name of the package file, and then click **Save.**</span></span>  
  
    -   <span data-ttu-id="42b25-166">Para exportar para o repositório de pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] , selecione a opção **Repositório de Pacotes SISS** e especifique o servidor.</span><span class="sxs-lookup"><span data-stu-id="42b25-166">To export to the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store, select the **SSIS Package Store** option, and specify the server.</span></span>  
  
         <span data-ttu-id="42b25-167">Clique no botão Procurar **(...)** , expanda a pasta dos **Pacotes SSIS** e selecione a pasta na qual deseja salvar o pacote.</span><span class="sxs-lookup"><span data-stu-id="42b25-167">Click the browse button **(...)**, expand the **SSIS Packages** folder, and select the folder to which you want to save the package.</span></span> <span data-ttu-id="42b25-168">Opcionalmente, digite um novo nome para o pacote na caixa de texto **Nome do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="42b25-168">Optionally, enter a new name for the package in the **Package Name** text box.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="42b25-169">Para atualizar o nível de proteção do pacote, clique no botão Procurar **(...)** e, na caixa de diálogo **Nível de Proteção do Pacote**, escolha um nível de proteção diferente.</span><span class="sxs-lookup"><span data-stu-id="42b25-169">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="42b25-170">Se a opção **Criptografar dados confidenciais com senhas** ou **Criptografar todos os dados com senhas** for selecionada, digite e confirme uma senha.</span><span class="sxs-lookup"><span data-stu-id="42b25-170">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
8.  <span data-ttu-id="42b25-171">Clique em **OK** para completar a exportação.</span><span class="sxs-lookup"><span data-stu-id="42b25-171">Click **OK** to complete the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b25-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42b25-172">See Also</span></span>  
 [<span data-ttu-id="42b25-173">Gerenciamento de pacotes &#40;Serviço SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="42b25-173">Package Management &#40;SSIS Service&#41;</span></span>](service/package-management-ssis-service.md)  
  
  
