---
title: Configurando o serviço de Integration Services (serviço SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- configuration files [Integration Services]
- service [Integration Services], configuring
- default configuration files
ms.assetid: 36d78393-a54c-44b0-8709-7f003f44c27f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70c41377a2c302e1a021c6ade2a9d487579fa64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684297"
---
# <a name="configuring-the-integration-services-service-ssis-service"></a><span data-ttu-id="70832-102">Configurando o serviço Integration Services (serviço SSIS)</span><span class="sxs-lookup"><span data-stu-id="70832-102">Configuring the Integration Services Service (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="70832-103">Esse tópico discute o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , um serviço do Windows para o gerenciamento de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70832-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] <span data-ttu-id="70832-104">dá suporte ao serviço para compatibilidade de versões anteriores com versões anteriores do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="70832-105">A partir do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], você pode gerenciar objetos como pacotes no servidor do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="70832-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="70832-106">O serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] depende de um arquivo de configuração para suas configurações.</span><span class="sxs-lookup"><span data-stu-id="70832-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service relies on a configuration file for its settings.</span></span> <span data-ttu-id="70832-107">Por padrão, o nome desse arquivo de configuração é MsDtsSrvr.ini.xml e o arquivo está localizado na pasta,%ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="70832-107">By default, the name for this configuration file is MsDtsSrvr.ini.xml, and the file is located in the folder, %ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span></span>  
  
 <span data-ttu-id="70832-108">Normalmente, você não tem que fazer alterações neste arquivo de configuração, nem no local padrão dele.</span><span class="sxs-lookup"><span data-stu-id="70832-108">Typically, you do not have to make any changes to this configuration file, nor do you have to change the file's default location.</span></span> <span data-ttu-id="70832-109">Porém, será necessário modificar o arquivo de configuração se seus pacotes estiverem armazenados em uma instância nomeada ou remota do [!INCLUDE[ssDE](../includes/ssde-md.md)]ou em várias instâncias do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-109">However, you will have to modify the configuration file if your packages are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)], or in multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="70832-110">Além disso, se você mover o arquivo de configuração para um local que não o padrão, será necessário modificar a chave do Registro que especifica o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="70832-110">Also, if you move the configuration file to a location other than the default location, you will have to modify the Registry key that specifies the file location.</span></span>  
  
## <a name="configuration-file-contents"></a><span data-ttu-id="70832-111">Conteúdo do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="70832-111">Configuration File Contents</span></span>  
 <span data-ttu-id="70832-112">Ao instalar o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], o processo de instalação cria e instala o arquivo de configuração do serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70832-112">When you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the setup process creates and installs the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="70832-113">Este arquivo de configuração contém as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="70832-113">This configuration file contains the following settings:</span></span>  
  
-   <span data-ttu-id="70832-114">Um comando de parada é enviado aos pacotes quando o serviço para.</span><span class="sxs-lookup"><span data-stu-id="70832-114">Packages are sent a stop command when the service stops.</span></span>  
  
-   <span data-ttu-id="70832-115">As pastas raiz para exibir para [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] são as pastas MSDB e Sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="70832-115">The root folders to display for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in Object Explorer of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are the MSDB and File System folders.</span></span>  
  
-   <span data-ttu-id="70832-116">Os pacotes no sistema de arquivos que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] serviço gerencia estão localizados em%ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span><span class="sxs-lookup"><span data-stu-id="70832-116">The packages in the file system that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages are located in %ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span></span>  
  
 <span data-ttu-id="70832-117">Esse arquivo de configuração também especifica qual banco de dados msdb contém os pacotes que o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administrará.</span><span class="sxs-lookup"><span data-stu-id="70832-117">This configuration file also specifies which msdb database contains the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service will manage.</span></span> <span data-ttu-id="70832-118">Por padrão, o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] é configurado para gerenciar pacotes no banco de dados msdb de uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] que é instalada ao mesmo tempo em que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-118">By default, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed at the same time as [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="70832-119">Se uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] não for instalada ao mesmo tempo, o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] será configurado para gerenciar pacotes no banco de dados msdb de uma instância local padrão do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-119">If an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] is not installed at the same time, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the local, default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
### <a name="default-configuration-file-example"></a><span data-ttu-id="70832-120">Exemplo de arquivo de configuração padrão</span><span class="sxs-lookup"><span data-stu-id="70832-120">Default Configuration File Example</span></span>  
 <span data-ttu-id="70832-121">O exemplo a seguir mostra um arquivo de configuração padrão que especifica as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="70832-121">The following example shows a default configuration file that specifies the following settings:</span></span>  
  
-   <span data-ttu-id="70832-122">Pacotes deixam de executar quando o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para.</span><span class="sxs-lookup"><span data-stu-id="70832-122">Packages stop running when the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service stops.</span></span>  
  
-   <span data-ttu-id="70832-123">As pastas raiz do armazenamento do pacote no [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] são MSDB e Arquivos do Sistema.</span><span class="sxs-lookup"><span data-stu-id="70832-123">The root folders for package storage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are MSDB and File System.</span></span>  
  
-   <span data-ttu-id="70832-124">O serviço gerencia pacotes que estão armazenados no banco de dado msdb da instância local padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-124">The service manages packages that are stored in the msdb database of the local, default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="70832-125">O serviço administra pacotes que estão armazenados no sistema de arquivos na pasta Pacotes.</span><span class="sxs-lookup"><span data-stu-id="70832-125">The service manages packages that are stored in the file system in the Packages folder.</span></span>  
  
 <span data-ttu-id="70832-126">**Exemplo de um arquivo de configuração padrão**</span><span class="sxs-lookup"><span data-stu-id="70832-126">**Example of a Default Configuration File**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>.</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file"></a><span data-ttu-id="70832-127">Modificação do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="70832-127">Modification of the Configuration File</span></span>  
 <span data-ttu-id="70832-128">Você pode modificar o arquivo de configuração para permitir que pacotes continuem sendo executados se o serviço for interrompido, para exibir pastas raiz adicionais no Pesquisador de Objetos ou para especificar uma pasta diferente ou pastas adicionais no sistema de arquivos gerenciado pelo serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70832-128">You can modify the configuration file to allow packages to continue running if the service stops, to display additional root folders in Object Explorer, or to specify a different folder or additional folders in the file system to be managed by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="70832-129">Por exemplo, você pode criar pastas raiz adicionais de tipo, `SqlServerFolder`, para gerenciar pacotes nos bancos de dados msdb de instâncias adicionais do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-129">For example, you can create additional root folders of type, `SqlServerFolder`, to manage packages in the msdb databases of additional instances of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70832-130">Alguns caracteres não são válidos em nomes de pasta.</span><span class="sxs-lookup"><span data-stu-id="70832-130">Some characters are not valid in folder names.</span></span> <span data-ttu-id="70832-131">Caracteres válidos para nomes de pastas são determinados pela classe [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]**System.IO.Path** e pelo campo **GetInvalidFilenameChars** .</span><span class="sxs-lookup"><span data-stu-id="70832-131">Valid characters for folder names are determined by the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] class **System.IO.Path** and the **GetInvalidFilenameChars** field.</span></span> <span data-ttu-id="70832-132">O campo **GetInvalidFilenameChars** fornece uma matriz de caracteres específica da plataforma que não pode ser especificada em argumentos de cadeia de caracteres de caminho passados para membros da classe **Path** .</span><span class="sxs-lookup"><span data-stu-id="70832-132">The **GetInvalidFilenameChars** field provides a platform-specific array of characters that cannot be specified in path string arguments passed to members of the **Path** class.</span></span> <span data-ttu-id="70832-133">O conjunto de caracteres inválidos pode variar por sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="70832-133">The set of invalid characters can vary by file system.</span></span> <span data-ttu-id="70832-134">Normalmente, os caracteres inválidos são aspas ("), caractere menos que (<) e caractere pipe (|).</span><span class="sxs-lookup"><span data-stu-id="70832-134">Typically, invalid characters are the quotation mark ("), less than (<) character, and pipe (|) character.</span></span>  
  
 <span data-ttu-id="70832-135">No entanto você precisa modificar o arquivo de configuração para gerenciar pacotes que são armazenados em uma instância nomeada ou remota do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-135">However, you will have to modify the configuration file to manage packages that are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="70832-136">Se você não atualizar o arquivo de configuração, não será possível usar o **Pesquisador de Objetos** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para exibir pacotes armazenados no banco de dados msdb na instância nomeada ou remota.</span><span class="sxs-lookup"><span data-stu-id="70832-136">If you do not update the configuration file, you cannot use **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view packages that are stored in the msdb database on the named instance or the remote instance.</span></span> <span data-ttu-id="70832-137">Se você tentar usar o **Pesquisador de Objetos** para exibir esses pacotes, receberá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="70832-137">If you try to use **Object Explorer** to view these packages, you receive the following error message:</span></span>  
  
 `Failed to retrieve data for this request. (Microsoft.SqlServer.SmoEnum)`  
  
 `The SQL Server specified in Integration Services service configuration is not present or is not available. This might occur when there is no default instance of SQL Server on the computer. For more information, see the topic "Configuring the Integration Services Service" in SQL Server 2008 Books Online.`  
  
 `Login Timeout Expired`  
  
 `An error has occurred while establishing a connection to the server. When connecting to SQL Server 2008, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.`  
  
 `Named Pipes Provider: Could not open a connection to SQL Server [2]. (MsDtsSvr).`  
  
 <span data-ttu-id="70832-138">Para modificar o arquivo de configuração do serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , use um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="70832-138">To modify the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, you use a text editor.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70832-139">Depois de modificar o arquivo de configuração de serviço, você deve reiniciar o serviço para usar a configuração de serviço atualizada.</span><span class="sxs-lookup"><span data-stu-id="70832-139">After you modify the service configuration file, you must restart the service to use the updated service configuration.</span></span>  
  
### <a name="modified-configuration-file-example"></a><span data-ttu-id="70832-140">Exemplo de arquivo de configuração modificado</span><span class="sxs-lookup"><span data-stu-id="70832-140">Modified Configuration File Example</span></span>  
 <span data-ttu-id="70832-141">O exemplo a seguir mostra um arquivo de configuração modificado do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70832-141">The following example shows a modified configuration file for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="70832-142">Este arquivo destina-se a uma instância nomeada do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] chamada `InstanceName` em um servidor nomeado `ServerName`.</span><span class="sxs-lookup"><span data-stu-id="70832-142">This file is for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] called `InstanceName` on a server named `ServerName`.</span></span>  
  
 <span data-ttu-id="70832-143">**Exemplo de um arquivo de configuração modificado para uma instância nomeada do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="70832-143">**Example of a Modified Configuration File for a Named Instance of SQL Server**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>ServerName\InstanceName</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file-location"></a><span data-ttu-id="70832-144">Modificação do local do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="70832-144">Modification of the Configuration File Location</span></span>  
<span data-ttu-id="70832-145">A chave do registro **HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\120\SSIS\ServiceConfigFile** especifica o local e o nome do arquivo de configuração que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] serviço usa.</span><span class="sxs-lookup"><span data-stu-id="70832-145">The Registry key **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\ServiceConfigFile** specifies the location and name for the configuration file that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service uses.</span></span> <span data-ttu-id="70832-146">O valor padrão da chave do registro é **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span><span class="sxs-lookup"><span data-stu-id="70832-146">The default value of the Registry key is **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span></span> <span data-ttu-id="70832-147">Você pode atualizar o valor da chave do Registro para usar um nome e local diferentes para o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="70832-147">You can update the value of the Registry key to use a different name and location for the configuration file.</span></span> <span data-ttu-id="70832-148">Observe que o número de versão no caminho (120 para SQL Server [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] ) varia dependendo da versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70832-148">Note that the version number in the path (120 for SQL Server  [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)]) will vary depending on the SQL Server version.</span></span> 
  
  
> [!CAUTION]  
>  <span data-ttu-id="70832-149">A edição incorreta do Registro pode provocar problemas sérios que exigem a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="70832-149">Incorrectly editing the Registry can cause serious problems that may require you to reinstall your operating system.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="70832-150">não pode garantir que os problemas resultantes da edição incorreta do Registro podem ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="70832-150">cannot guarantee that problems resulting from editing the Registry incorrectly can be resolved.</span></span> <span data-ttu-id="70832-151">Antes de editar o Registro, faça backup de todos os dados valiosos.</span><span class="sxs-lookup"><span data-stu-id="70832-151">Before editing the Registry, back up any valuable data.</span></span> <span data-ttu-id="70832-152">Para obter informações sobre como fazer backup, restaurar e editar o Registro, consulte o artigo da Base de Dados de Conhecimento sobre o [!INCLUDE[msCoName](../includes/msconame-md.md)] , [Descrição do Registro do Microsoft Windows](https://support.microsoft.com/kb/256986).</span><span class="sxs-lookup"><span data-stu-id="70832-152">For information about how to back up, restore, and edit the Registry, see the [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base article, [Description of the Microsoft Windows registry](https://support.microsoft.com/kb/256986).</span></span>  
  
 <span data-ttu-id="70832-153">O serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] carrega o arquivo de configuração quando o serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="70832-153">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service loads the configuration file when the service is started.</span></span> <span data-ttu-id="70832-154">Qualquer alteração na entrada do Registro exige que o serviço seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="70832-154">Any changes to the Registry entry require that the service be restarted.</span></span>  
  
  
