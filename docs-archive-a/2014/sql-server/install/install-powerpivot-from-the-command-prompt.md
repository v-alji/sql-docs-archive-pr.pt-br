---
title: Instalar o PowerPivot no prompt de comando | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7f1f2b28-c9f5-49ad-934b-02f2fa6b9328
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 54f30142cdc2e39b3ec565d4f965fdad675405e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582772"
---
# <a name="install-powerpivot-from-the-command-prompt"></a><span data-ttu-id="631e8-102">Instalar o PowerPivot pelo prompt de comando</span><span class="sxs-lookup"><span data-stu-id="631e8-102">Install PowerPivot from the Command Prompt</span></span>
  <span data-ttu-id="631e8-103">É possível executar a Instalação na linha de comando para instalar o SQL Server PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="631e8-103">You can run Setup from the command line to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="631e8-104">Você deve incluir o parâmetro `/ROLE` no comando e excluir o parâmetro `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="631e8-104">You must include the `/ROLE` parameter in your command and exclude the `/FEATURES` parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="631e8-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="631e8-105">Prerequisites</span></span>  
 <span data-ttu-id="631e8-106">O SharePoint Server 2010 Enterprise Edition com Service Pack 1 (SP1) deve ser instalado.</span><span class="sxs-lookup"><span data-stu-id="631e8-106">SharePoint Server 2010 enterprise edition with Service Pack 1 (SP1) must be installed.</span></span>  
  
 <span data-ttu-id="631e8-107">Você deve usar contas de domínio para provisionar o Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="631e8-107">You must use domain accounts to provision Analysis Services.</span></span>  
  
 <span data-ttu-id="631e8-108">O computador deve ingressar no mesmo domínio do farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="631e8-108">The computer must be joined to the same domain as the SharePoint farm.</span></span>  
  
##  <a name="role-based-installation-options"></a><a name="Commands"></a><span data-ttu-id="631e8-109">Opções de instalação baseadas em/ROLE</span><span class="sxs-lookup"><span data-stu-id="631e8-109">/ROLE based installation options</span></span>  
 <span data-ttu-id="631e8-110">Para implantações do PowerPivot para SharePoint, o parâmetro `/ROLE` é usado no lugar do parâmetro `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="631e8-110">For PowerPivot for SharePoint deployments, the `/ROLE` parameter is used in place of the `/FEATURES` parameter.</span></span> <span data-ttu-id="631e8-111">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="631e8-111">Valid values include:</span></span>  
  
-   `SPI_AS_ExistingFarm`  
  
-   `SPI_AS_NewFarm`  
  
 <span data-ttu-id="631e8-112">Ambas as funções instalam arquivos de aplicativo, de configuração e de implantação que permitem a execução de um PowerPivot para SharePoint em um farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="631e8-112">Both roles install application, configuration, and deployment files that enable a PowerPivot for SharePoint to run in a SharePoint farm.</span></span> <span data-ttu-id="631e8-113">A especificação de uma função fará a Instalação verificar os requisitos de hardware e de software necessários à integração com o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="631e8-113">Specifying either role will cause Setup to check for hardware and software requirements necessary for SharePoint integration.</span></span>  
  
 <span data-ttu-id="631e8-114">A opção de farm existente pressupõe que um farm do SharePoint já está em vigor.</span><span class="sxs-lookup"><span data-stu-id="631e8-114">The existing farm option assumes that a SharePoint farm is already in place.</span></span> <span data-ttu-id="631e8-115">A nova opção de farm pressupõe que você criará um novo farm; Ele dá suporte à adição de uma instância de Mecanismo de Banco de Dados na sintaxe de linha de comando para que você possa usar a instância de Mecanismo de Banco de Dados como o servidor de banco de dados do farm.</span><span class="sxs-lookup"><span data-stu-id="631e8-115">The new farm option assumes that you will create a new farm; it supports the addition of a Database Engine instance in the command line syntax so that you can use the Database Engine instance as the farm's database server.</span></span>  
  
 <span data-ttu-id="631e8-116">Em comparação com as versões anteriores, todas as tarefas de configuração de servidor são executadas como tarefas pós-instalação.</span><span class="sxs-lookup"><span data-stu-id="631e8-116">In contrast with the previous releases, all server configuration tasks are performed as post-installation tasks.</span></span> <span data-ttu-id="631e8-117">Se você estiver automatizando as etapas de instalação e configuração, poderá usar o PowerShell para configurar o servidor.</span><span class="sxs-lookup"><span data-stu-id="631e8-117">If you are automating installation and configuration steps, you can use PowerShell to configure the server.</span></span> <span data-ttu-id="631e8-118">Para obter mais informações, consulte [configuração do PowerPivot usando o Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="631e8-118">For more information, see [PowerPivot Configuration using Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span></span>  
  
## <a name="example-commands"></a><span data-ttu-id="631e8-119">Comandos de exemplo</span><span class="sxs-lookup"><span data-stu-id="631e8-119">Example Commands</span></span>  
 <span data-ttu-id="631e8-120">Os exemplos a seguir ilustram o uso de cada opção.</span><span class="sxs-lookup"><span data-stu-id="631e8-120">The following examples illustrate the usage of each option.</span></span> <span data-ttu-id="631e8-121">O exemplo 1 mostra `SPI_AS_ExistingFarm` .</span><span class="sxs-lookup"><span data-stu-id="631e8-121">Example 1 shows `SPI_AS_ExistingFarm`.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="631e8-122">O Exemplo 2 mostra `SPI_AS_NewFarm`.</span><span class="sxs-lookup"><span data-stu-id="631e8-122">Example 2 shows `SPI_AS_NewFarm`.</span></span> <span data-ttu-id="631e8-123">Observe que isso inclui parâmetros para o provisionamento do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="631e8-123">Notice that it includes parameters for provisioning the Database Engine.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_NewFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/SQLSVCACCOUNT=<DomainName\UserName> /SQLSVCPASSWORD=<StrongPassword> /SQLSYSADMINACCOUNTS=<DomainName\UserName> /AGTSVCACCOUNT=<DomainName\UserName> /AGTSVCPASSWORD=<StrongPassword> /ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
##  <a name="modifying-the-command-syntax"></a><a name="Join"></a><span data-ttu-id="631e8-124">Modificando a sintaxe do comando</span><span class="sxs-lookup"><span data-stu-id="631e8-124">Modifying the command syntax</span></span>  
 <span data-ttu-id="631e8-125">Use as etapas a seguir para modificar a sintaxe do comando de exemplo.</span><span class="sxs-lookup"><span data-stu-id="631e8-125">Use the following steps to modify the example command syntax.</span></span>  
  
1.  <span data-ttu-id="631e8-126">Copie e cole o seguinte comando no Bloco de Notas:</span><span class="sxs-lookup"><span data-stu-id="631e8-126">Copy the following command into Notepad:</span></span>  
  
    ```cmd
    Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
    ```  
  
     <span data-ttu-id="631e8-127">O parâmetro `/q` executa a Instalação no modo silencioso, que suprime a interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="631e8-127">The `/q` parameter runs Setup in quiet mode, which suppresses the user interface.</span></span>  
  
     <span data-ttu-id="631e8-128">O `/IAcceptSQLServerLicenseTerms` será obrigatório quando o parâmetro `/q` ou `/qs` for especificado para instalações autônomas.</span><span class="sxs-lookup"><span data-stu-id="631e8-128">The `/IAcceptSQLServerLicenseTerms` is required when the `/q` or `/qs` parameter is specified for un-attended installations.</span></span>  
  
     <span data-ttu-id="631e8-129">O parâmetro `/action` instrui a Instalação a executar uma instalação.</span><span class="sxs-lookup"><span data-stu-id="631e8-129">The `/action` parameter instructs Setup to perform an installation.</span></span>  
  
     <span data-ttu-id="631e8-130">O parâmetro `/role` instrui a Instalação a instalar o programa Analysis Services e os arquivos de configuração necessários para o PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="631e8-130">The `/role` parameter instructs Setup to install the Analysis Services program and configuration files required for PowerPivot for SharePoint.</span></span> <span data-ttu-id="631e8-131">Essa função também detecta e usa as informações de conectividade do farm existente para acessar o banco de dados de configuração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="631e8-131">This role also detects and uses the existing farm connectivity information to access the SharePoint configuration database.</span></span> <span data-ttu-id="631e8-132">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="631e8-132">This parameter is required.</span></span> <span data-ttu-id="631e8-133">Use-o em lugar do parâmetro `/features` para especificar os componentes a serem instalados.</span><span class="sxs-lookup"><span data-stu-id="631e8-133">Use it instead of the `/features` parameter to specify the components to install.</span></span>  
  
     <span data-ttu-id="631e8-134">O parâmetro `/instancename` especifica 'PowerPivot' como uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="631e8-134">The `/instancename` parameter specifies 'PowerPivot' as a named instance.</span></span> <span data-ttu-id="631e8-135">Esse valor é embutido em código e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="631e8-135">This value is hard-coded and cannot be changed.</span></span> <span data-ttu-id="631e8-136">Ele está especificado no comando para fins instrutivos para que você saiba como o serviço é instalado.</span><span class="sxs-lookup"><span data-stu-id="631e8-136">It is specified in the command for educational purposes so that you know how the service is installed.</span></span>  
  
     <span data-ttu-id="631e8-137">O parâmetro `/indicateprogress` permite monitorar o andamento na janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="631e8-137">The `/indicateprogress` parameter allows you to monitor progress in the command prompt window.</span></span>  
  
2.  <span data-ttu-id="631e8-138">O parâmetro `PID` é omitido do comando, o que faz a edição Evaluation ser instalada.</span><span class="sxs-lookup"><span data-stu-id="631e8-138">The `PID` parameter is omitted from the command, which causes the Evaluation edition to be installed.</span></span> <span data-ttu-id="631e8-139">Se você quiser instalar a edição Enterprise, adicione o PID ao comando da Instalação e forneça uma chave de produto válida.</span><span class="sxs-lookup"><span data-stu-id="631e8-139">If you want to install the Enterprise edition, add the PID to your Setup command and provide a valid product key.</span></span>  
  
    ```  
    /PID=<product key for an Enterprise installation>  
    ```  
  
3.  <span data-ttu-id="631e8-140">Substitua os espaços reservados para \<domain\username> e \<StrongPassword> por contas de usuário e senhas válidas.</span><span class="sxs-lookup"><span data-stu-id="631e8-140">Replace the placeholders for \<domain\username> and \<StrongPassword>with valid user accounts and passwords.</span></span>  
  
     <span data-ttu-id="631e8-141">Os `/assvaccount` parâmetros e **/assvcpassword** são usados para configurar a [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instância no servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="631e8-141">The `/assvaccount` and **/assvcpassword** parameters are used to configure the [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance on the application server.</span></span> <span data-ttu-id="631e8-142">Substitua esses espaços reservados pelas informações de conta válidas.</span><span class="sxs-lookup"><span data-stu-id="631e8-142">Replace these placeholders with valid account information.</span></span>  
  
     <span data-ttu-id="631e8-143">O parâmetro **/assysadminaccounts** deve ser definido como a identidade do usuário que está executando SQL Server configuração.</span><span class="sxs-lookup"><span data-stu-id="631e8-143">The **/assysadminaccounts** parameter must be set to the identity of the user who is running SQL Server Setup.</span></span> <span data-ttu-id="631e8-144">Você deve especificar pelo menos um administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="631e8-144">You must specify at least one system administrator.</span></span> <span data-ttu-id="631e8-145">Observe que a Instalação do SQL Server deixou de conceder permissões sysadmin para membros do grupo Administradores interno.</span><span class="sxs-lookup"><span data-stu-id="631e8-145">Note that SQL Server Setup no long grants automatic sysadmin permissions to members of the built-in Administrators group.</span></span>  
  
4.  <span data-ttu-id="631e8-146">Remova quebras de linha.</span><span class="sxs-lookup"><span data-stu-id="631e8-146">Remove line breaks.</span></span>  
  
5.  <span data-ttu-id="631e8-147">Selecione o comando inteiro e, em seguida, clique em **copiar** no menu Editar.</span><span class="sxs-lookup"><span data-stu-id="631e8-147">Select the entire command and then click **Copy** on the Edit menu.</span></span>  
  
6.  <span data-ttu-id="631e8-148">Abra um prompt de comando do administrador.</span><span class="sxs-lookup"><span data-stu-id="631e8-148">Open an administrator command prompt.</span></span> <span data-ttu-id="631e8-149">Para fazer isso, clique em **Iniciar**, clique com o botão direito do mouse no prompt de comando e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="631e8-149">To do this, click **Start**, right-click the command prompt, and select **Run as administrator**.</span></span>  
  
7.  <span data-ttu-id="631e8-150">Navegue para a unidade ou pasta compartilhada que contém a mídia de instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="631e8-150">Navigate to the drive or shared folder that contains the SQL Server installation media.</span></span>  
  
8.  <span data-ttu-id="631e8-151">Cole o comando revisado na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="631e8-151">Paste the revised command into the command line.</span></span> <span data-ttu-id="631e8-152">Para fazer isso, clique no ícone no canto superior esquerdo da janela do prompt de comando, aponte para **Editar**e clique em **colar**.</span><span class="sxs-lookup"><span data-stu-id="631e8-152">To do this, click the icon in the top left corner of the command prompt window, point to **Edit**, and then click **Paste**.</span></span>  
  
9. <span data-ttu-id="631e8-153">Pressione **Enter** para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="631e8-153">Press **Enter** to run the command.</span></span> <span data-ttu-id="631e8-154">Aguarde a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="631e8-154">Wait for setup to complete.</span></span> <span data-ttu-id="631e8-155">É possível monitorar o andamento da Instalação na janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="631e8-155">You can monitor Setup's progress in the command prompt window.</span></span>  
  
10. <span data-ttu-id="631e8-156">Para verificar a instalação, consulte o arquivo summary.txt em \Arquivos de Programas\SQL Server\120\Setup Bootstrap\Log.</span><span class="sxs-lookup"><span data-stu-id="631e8-156">To verify installation, check the summary.txt file at \Program Files\SQL Server\120\Setup Bootstrap\Log.</span></span> <span data-ttu-id="631e8-157">O resultado final deverá indicar "Aprovado" se o servidor for instalado sem erros.</span><span class="sxs-lookup"><span data-stu-id="631e8-157">Final result should say "Passed" if the server installed without errors.</span></span>  
  
11. <span data-ttu-id="631e8-158">Configure o servidor.</span><span class="sxs-lookup"><span data-stu-id="631e8-158">Configure the server.</span></span> <span data-ttu-id="631e8-159">Você deve, no mínimo, implantar soluções, criar um aplicativo de serviço e habilitar o recurso de cada conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="631e8-159">At a minimum, you must deploy solutions, create a service application, and enable the feature for each site collection.</span></span> <span data-ttu-id="631e8-160">Para obter mais informações, consulte [Configurar ou reparar 2010 PowerPivot para SharePoint &#40;ferramenta de configuração do powerpivot&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) ou a [Administração e a configuração do servidor PowerPivot na administração central](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span><span class="sxs-lookup"><span data-stu-id="631e8-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) or [PowerPivot Server Administration and Configuration in Central Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631e8-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="631e8-161">See Also</span></span>  
 <span data-ttu-id="631e8-162">[Configurar contas de serviço PowerPivot](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span><span class="sxs-lookup"><span data-stu-id="631e8-162">[Configure PowerPivot Service Accounts](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span></span>  
 [<span data-ttu-id="631e8-163">Instalação do PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="631e8-163">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
