---
title: Configurações do pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package configuration syntax [Integration Services]
- SQL Server Integration Services packages, configurations
- SSIS packages, configurations
- XML [Integration Services]
- Integration Services packages, configurations
- configuration syntax [Integration Services]
- indirect configurations [Integration Services]
- configurations [Integration Services]
- direct configurations [Integration Services]
- packages [Integration Services], configurations
ms.assetid: d20e0311-1fc9-4ddc-a381-6d127cf11b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d22dbfedcf4cf7084e1667586f9774926f3b2a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583723"
---
# <a name="package-configurations"></a><span data-ttu-id="69772-102">Configurações do Pacote</span><span class="sxs-lookup"><span data-stu-id="69772-102">Package Configurations</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="69772-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fornece configurações de pacote que podem ser usadas para atualizar os valores das propriedades em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="69772-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides package configurations that you can use to update the values of properties at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69772-104">As configurações estão disponíveis para o modelo de implantação de pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="69772-105">Os parâmetros são usados no lugar das configurações para o modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="69772-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="69772-106">O modelo de implantação de projeto permite que você implante projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69772-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="69772-107">Para obter mais informações sobre os modelos de implantação, consulte [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="69772-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="69772-108">Uma configuração é um par propriedade/valor que você adiciona a um pacote concluído.</span><span class="sxs-lookup"><span data-stu-id="69772-108">A configuration is a property/value pair that you add to a completed package.</span></span> <span data-ttu-id="69772-109">Normalmente, você cria uma definição de propriedades do pacote nos objetos do pacote durante o desenvolvimento do pacote e, depois, adiciona as configurações ao pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-109">Typically, you create a package set properties on the package objects during package development, and then add the configuration to the package.</span></span> <span data-ttu-id="69772-110">Quando o pacote é executado, obtém os novos valores da propriedade da configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-110">When the package runs, it gets the new values of the property from the configuration.</span></span> <span data-ttu-id="69772-111">Por exemplo, ao usar uma configuração, você pode alterar a cadeia de caracteres de conexão de um gerenciador de conexões ou atualizar o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="69772-111">For example, by using a configuration, you can change the connection string of a connection manager, or update the value of a variable.</span></span>  
  
 <span data-ttu-id="69772-112">As configurações de pacote fornecem os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="69772-112">Package configurations provide the following benefits:</span></span>  
  
-   <span data-ttu-id="69772-113">As configurações facilitam a movimentação dos pacotes de um ambiente de desenvolvimento para um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="69772-113">Configurations make it easier to move packages from a development environment to a production environment.</span></span> <span data-ttu-id="69772-114">Por exemplo, uma configuração pode atualizar o caminho de um arquivo de origem, ou alterar o nome de um banco de dados ou de um servidor.</span><span class="sxs-lookup"><span data-stu-id="69772-114">For example, a configuration can update the path of a source file, or change the name of a database or server.</span></span>  
  
-   <span data-ttu-id="69772-115">As configurações são úteis quando você implanta pacotes em muitos servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="69772-115">Configurations are useful when you deploy packages to many different servers.</span></span> <span data-ttu-id="69772-116">Por exemplo, uma variável na configuração de cada pacote implantado pode conter um valor de espaço de disco diferente e, se o espaço em disco disponível não atingir esse valor, o pacote não será executado.</span><span class="sxs-lookup"><span data-stu-id="69772-116">For example, a variable in the configuration for each deployed package can contain a different disk space value, and if the available disk space does not meet this value, the package does not run.</span></span>  
  
-   <span data-ttu-id="69772-117">As configurações tornam os pacotes mais flexíveis.</span><span class="sxs-lookup"><span data-stu-id="69772-117">Configurations make packages more flexible.</span></span> <span data-ttu-id="69772-118">Por exemplo, uma configuração pode atualizar o valor de uma variável usada em uma expressão de propriedade.</span><span class="sxs-lookup"><span data-stu-id="69772-118">For example, a configuration can update the value of a variable that is used in a property expression.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="69772-119">oferece suporte a vários métodos diferentes de armazenamento de configurações de pacote, como arquivos XML, tabelas em um banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e variáveis de ambiente e pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-119">supports several different methods of storing package configurations, such as XML files, tables in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and environment and package variables.</span></span>  
  
 <span data-ttu-id="69772-120">Cada configuração é um par propriedade/valor.</span><span class="sxs-lookup"><span data-stu-id="69772-120">Each configuration is a property/value pair.</span></span> <span data-ttu-id="69772-121">O arquivo de configuração XML e os tipos de configuração [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] podem incluir várias configurações.</span><span class="sxs-lookup"><span data-stu-id="69772-121">The XML configuration file and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration types can include multiple configurations.</span></span>  
  
 <span data-ttu-id="69772-122">As configurações são incluídas quando você cria um utilitário de desenvolvimento de pacote para instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="69772-122">The configurations are included when you create a package deployment utility for installing packages.</span></span> <span data-ttu-id="69772-123">Quando você instala os pacotes, as configurações podem ser atualizadas como uma etapa na instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="69772-123">When you install the packages, the configurations can be updated as a step in the package installation.</span></span>  
  
## <a name="understanding-how-package-configurations-are-applied-at-run-time"></a><span data-ttu-id="69772-124">Compreendendo como as configurações de pacote são aplicadas em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="69772-124">Understanding How Package Configurations Are Applied at Run Time</span></span>  
 <span data-ttu-id="69772-125">Quando você usa o utilitário do prompt de comando **dtexec** para executar um pacote implantado, o utilitário aplica as configurações do pacote duas vezes.</span><span class="sxs-lookup"><span data-stu-id="69772-125">When you use the **dtexec** command prompt utility (dtexec.exe) to run a deployed package, the utility applies package configurations twice.</span></span> <span data-ttu-id="69772-126">O utilitário aplica configurações antes e depois de aplicar as opções que você especificou na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="69772-126">The utility applies configurations both before and after it applies the options that you specified on command line.</span></span>  
  
 <span data-ttu-id="69772-127">Como o utilitário carrega e executa o pacote, os eventos ocorrem na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="69772-127">As the utility loads and runs the package, events occur in the following order:</span></span>  
  
1.  <span data-ttu-id="69772-128">O utilitário **dtexec** carrega o pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-128">The **dtexec** utility loads the package.</span></span>  
  
2.  <span data-ttu-id="69772-129">O utilitário aplica as configurações que foram especificadas no pacote em tempo de design e na ordem especificada no pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-129">The utility applies the configurations that were specified in the package at design time and in the order that is specified in the package.</span></span> <span data-ttu-id="69772-130">(A única exceção a essa regra são as configurações de Variáveis do Pacote Pai.</span><span class="sxs-lookup"><span data-stu-id="69772-130">(The one exception to this is the Parent Package Variables configurations.</span></span> <span data-ttu-id="69772-131">O utilitário só aplica essas configurações uma vez e posteriormente no processo.)</span><span class="sxs-lookup"><span data-stu-id="69772-131">The utility applies these configurations only once and later in the process.)</span></span>  
  
3.  <span data-ttu-id="69772-132">Em seguida, o utilitário aplica qualquer opção que você especificou na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="69772-132">The utility then applies any options that you specified on the command line.</span></span>  
  
4.  <span data-ttu-id="69772-133">O utilitário recarrega as configurações que foram especificadas no pacote em tempo de design e na ordem especificada no pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-133">The utility then reloads the configurations that were specified in the package at design time and in the order specified in the package.</span></span> <span data-ttu-id="69772-134">(Novamente, a exceção a essa regra são as configurações de Variáveis do Pacote Pai).</span><span class="sxs-lookup"><span data-stu-id="69772-134">(Again, the exception to this rule is the Parent Package Variables configurations).</span></span> <span data-ttu-id="69772-135">O utilitário usa qualquer opção de linha de comando que foi especificada para recarregar as configurações.</span><span class="sxs-lookup"><span data-stu-id="69772-135">The utility uses any command-line options that were specified to reload the configurations.</span></span> <span data-ttu-id="69772-136">Portanto, valores diferentes podem ser recarregados a partir de locais distintos.</span><span class="sxs-lookup"><span data-stu-id="69772-136">Therefore, different values might be reloaded from a different location.</span></span>  
  
5.  <span data-ttu-id="69772-137">O utilitário aplica as configurações Variáveis do Pacote Pai.</span><span class="sxs-lookup"><span data-stu-id="69772-137">The utility applies the Parent Package Variable configurations.</span></span>  
  
6.  <span data-ttu-id="69772-138">O utilitário executa o pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-138">The utility runs the package.</span></span>  
  
 <span data-ttu-id="69772-139">O modo como o utilitário **dtexec** aplica as configurações afeta as seguintes opções da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="69772-139">The way in which the **dtexec** utility applies configurations affects the following command-line options:</span></span>  
  
-   <span data-ttu-id="69772-140">Você pode usar a opção **/Connection** ou **/Set** na execução para carregar as configurações do pacote por meio de um local diferente do especificado no design.</span><span class="sxs-lookup"><span data-stu-id="69772-140">You can use the **/Connection** or **/Set** option at run time to load package configurations from a location other than the location that you specified at design time.</span></span>  
  
-   <span data-ttu-id="69772-141">Você pode usar a opção **/ConfigFile** para carregar as configurações adicionais não especificadas no design.</span><span class="sxs-lookup"><span data-stu-id="69772-141">You can use the **/ConfigFile** option to load additional configurations that you did not specify at design time.</span></span>  
  
 <span data-ttu-id="69772-142">Porém, essas opções de linha de comando têm algumas restrições:</span><span class="sxs-lookup"><span data-stu-id="69772-142">However, these command-line options do have some restrictions:</span></span>  
  
-   <span data-ttu-id="69772-143">Não é possível usar a opção **/Set** ou **/Connection** para substituir os valores únicos que também são definidos por uma configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-143">You cannot use the **/Set** or the **/Connection** option to override single values that are also set by a configuration.</span></span>  
  
-   <span data-ttu-id="69772-144">Não é possível usar a opção **/ConfigFile** para carregar as configurações que substituem as configurações especificadas no design.</span><span class="sxs-lookup"><span data-stu-id="69772-144">You cannot use the **/ConfigFile** option to load configurations that replace the configurations that you specified at design time.</span></span>  
  
 <span data-ttu-id="69772-145">Para obter mais informações sobre essas opções e como o comportamento dessas opções é diferente entre o [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] e versões anteriores, consulte [alterações de comportamento para Integration Services recursos no SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="69772-145">For more information about these options, and how the behavior of these options differs between [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] and earlier versions, see [Behavior Changes to Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span></span>  
  
## <a name="package-configuration-types"></a><span data-ttu-id="69772-146">Tipos de configuração de pacotes</span><span class="sxs-lookup"><span data-stu-id="69772-146">Package Configuration Types</span></span>  
 <span data-ttu-id="69772-147">A tabela a seguir descreve os tipos de configuração de pacotes.</span><span class="sxs-lookup"><span data-stu-id="69772-147">The following table describes the package configuration types.</span></span>  
  
|<span data-ttu-id="69772-148">Type</span><span class="sxs-lookup"><span data-stu-id="69772-148">Type</span></span>|<span data-ttu-id="69772-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="69772-149">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="69772-150">Arquivo de configuração XML</span><span class="sxs-lookup"><span data-stu-id="69772-150">XML configuration file</span></span>|<span data-ttu-id="69772-151">Um arquivo XML contém as configurações.</span><span class="sxs-lookup"><span data-stu-id="69772-151">An XML file contains the configurations.</span></span> <span data-ttu-id="69772-152">O arquivo XML pode incluir várias configurações.</span><span class="sxs-lookup"><span data-stu-id="69772-152">The XML file can include multiple configurations.</span></span>|  
|<span data-ttu-id="69772-153">Variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="69772-153">Environment variable</span></span>|<span data-ttu-id="69772-154">Uma variável de ambiente contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-154">An environment variable contains the configuration.</span></span>|  
|<span data-ttu-id="69772-155">Entrada de Registro</span><span class="sxs-lookup"><span data-stu-id="69772-155">Registry entry</span></span>|<span data-ttu-id="69772-156">Uma entrada de Registro contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-156">A Registry entry contains the configuration.</span></span>|  
|<span data-ttu-id="69772-157">Variável de pacote pai</span><span class="sxs-lookup"><span data-stu-id="69772-157">Parent package variable</span></span>|<span data-ttu-id="69772-158">Uma variável no pacote contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-158">A variable in the package contains the configuration.</span></span> <span data-ttu-id="69772-159">Normalmente, esse tipo de configuração é usado para atualizar as propriedades em pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="69772-159">This configuration type is typically used to update properties in child packages.</span></span>|  
|<span data-ttu-id="69772-160">Tabela [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69772-160">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>|<span data-ttu-id="69772-161">Uma tabela em um banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que contém a configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-161">A table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database contains the configuration.</span></span> <span data-ttu-id="69772-162">A tabela pode incluir várias configurações.</span><span class="sxs-lookup"><span data-stu-id="69772-162">The table can include multiple configurations.</span></span>|  
  
### <a name="xml-configuration-files"></a><span data-ttu-id="69772-163">Arquivos de configuração XML</span><span class="sxs-lookup"><span data-stu-id="69772-163">XML Configuration Files</span></span>  
 <span data-ttu-id="69772-164">Se você selecionar o tipo de configuração **arquivo de configuração XML** , poderá criar um novo arquivo de configuração, reutilizar um arquivo existente e adicionar configurações novas ou reutilizar um arquivo existente, mas substituir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="69772-164">If you select the **XML configuration file** configuration type, you can create a new configuration file, reuse an existing file and add new configurations, or reuse an existing file but overwrite existing file content.</span></span>  
  
 <span data-ttu-id="69772-165">Um arquivo de configuração XML inclui duas seções:</span><span class="sxs-lookup"><span data-stu-id="69772-165">An XML configuration file includes two sections:</span></span>  
  
-   <span data-ttu-id="69772-166">Um título que contém informações sobre o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-166">A heading that contains information about the configuration file.</span></span> <span data-ttu-id="69772-167">Esse elemento inclui atributos tais como quando o arquivo foi criado e o nome da pessoa que gerou o arquivo.</span><span class="sxs-lookup"><span data-stu-id="69772-167">This element includes attributes such as when the file was created and the name of the person who generated the file.</span></span>  
  
-   <span data-ttu-id="69772-168">Elementos de configuração que contêm informações sobre cada configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-168">Configuration elements that contain information about each configuration.</span></span> <span data-ttu-id="69772-169">Esse elemento inclui atributos como o caminho da propriedade e o valor configurado de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="69772-169">This element includes attributes such as the property path and the configured value of a property.</span></span>  
  
 <span data-ttu-id="69772-170">O código XML a seguir mostra a sintaxe de um arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="69772-170">The following XML code demonstrates the syntax of an XML configuration file.</span></span> <span data-ttu-id="69772-171">Esse exemplo mostra uma configuração para a propriedade Value de uma variável de inteiro chamada `MyVar`.</span><span class="sxs-lookup"><span data-stu-id="69772-171">This example shows a configuration for the Value property of an integer variable named `MyVar`.</span></span>  
  
```  
<?xml version="1.0"?>  
<DTSConfiguration>  
   <DTSConfigurationHeading>  
      <DTSConfigurationFileInfo  
          GeneratedBy="DomainName\UserName"  
          GeneratedFromPackageName="Package"  
          GeneratedFromPackageID="{2AF06766-817A-4E28-9878-0DE37A150648}"  
          GeneratedDate="2/01/2005 5:58:09 PM"/>  
   </DTSConfigurationHeading>  
   <Configuration ConfiguredType="Property" Path="\Package.Variables[User::MyVar].Value" ValueType="Int32">  
      <ConfiguredValue>0</ConfiguredValue>  
   </Configuration>  
</DTSConfiguration>  
  
```  
  
### <a name="registry-entry"></a><span data-ttu-id="69772-172">Entrada de Registro</span><span class="sxs-lookup"><span data-stu-id="69772-172">Registry Entry</span></span>  
 <span data-ttu-id="69772-173">Se você desejar usar uma entrada de Registro para armazenar a configuração, poderá usar uma chave existente ou criar uma nova chave em HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="69772-173">If you want to use a Registry entry to store the configuration, you can either use an existing key or create a new key in HKEY_CURRENT_USER.</span></span> <span data-ttu-id="69772-174">A chave do Registro que você usa deve ter um valor denominado `Value`.</span><span class="sxs-lookup"><span data-stu-id="69772-174">The Registry key that you use must have a value named `Value`.</span></span> <span data-ttu-id="69772-175">O valor pode ser um DWORD ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69772-175">The value can be a DWORD or a string.</span></span>  
  
 <span data-ttu-id="69772-176">Se você selecionar o tipo de configuração **Entrada de Registro** , digitará o nome da chave do Registro na caixa de entrada de Registro.</span><span class="sxs-lookup"><span data-stu-id="69772-176">If you select the **Registry entry** configuration type, you type the name of the Registry key in the Registry entry box.</span></span> <span data-ttu-id="69772-177">O formato é \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="69772-177">The format is \<registry key>.</span></span> <span data-ttu-id="69772-178">Se desejar usar uma chave do Registro que não está na raiz de HKEY_CURRENT_USER, use o formato \<Registry key\registry key\\...> para identificá-la.</span><span class="sxs-lookup"><span data-stu-id="69772-178">If you want to use a Registry key that is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span> <span data-ttu-id="69772-179">Por exemplo, para usar a chave MyPackage localizada em SSISPackages, digite `SSISPackages\MyPackage`.</span><span class="sxs-lookup"><span data-stu-id="69772-179">For example, to use the MyPackage key located in SSISPackages, type `SSISPackages\MyPackage`.</span></span>  
  
### <a name="sql-server"></a><span data-ttu-id="69772-180">SQL Server</span><span class="sxs-lookup"><span data-stu-id="69772-180">SQL Server</span></span>  
 <span data-ttu-id="69772-181">Se você selecionar o tipo de configuração **SQL Server** , especifique a conexão para o banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em que deseja armazenar as configurações.</span><span class="sxs-lookup"><span data-stu-id="69772-181">If you select the **SQL Server** configuration type, you specify the connection to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database in which you want to store the configurations.</span></span> <span data-ttu-id="69772-182">Você pode salvar as configurações em uma tabela existente ou criar uma tabela no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="69772-182">You can save the configurations to an existing table or create a new table in the specified database.</span></span>  
  
 <span data-ttu-id="69772-183">A instrução SQL a seguir mostra a instrução padrão CREATE TABLE fornecida pelo Assistente de Configuração de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="69772-183">The following SQL statement shows the default CREATE TABLE statement that the Package Configuration Wizard provides.</span></span>  
  
```  
CREATE TABLE [dbo].[SSIS Configurations]  
(  
ConfigurationFilter NVARCHAR(255) NOT NULL,  
ConfiguredValue NVARCHAR(255) NULL,  
PackagePath NVARCHAR(255) NOT NULL,  
ConfiguredValueType NVARCHAR(20) NOT NULL  
)  
  
```  
  
 <span data-ttu-id="69772-184">O nome fornecido para a configuração é o valor armazenado na coluna **ConfigurationFilter** .</span><span class="sxs-lookup"><span data-stu-id="69772-184">The name that you provide for the configuration is the value stored in the **ConfigurationFilter** column.</span></span>  
  
## <a name="direct-and-indirect-configurations"></a><span data-ttu-id="69772-185">Configurações diretas e indiretas</span><span class="sxs-lookup"><span data-stu-id="69772-185">Direct and Indirect Configurations</span></span>  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="69772-186">fornece configurações diretas e indiretas.</span><span class="sxs-lookup"><span data-stu-id="69772-186">provides direct and indirect configurations.</span></span> <span data-ttu-id="69772-187">Se você especificar as configurações diretamente, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] criará um vínculo direto entre o item de configuração e a propriedade de objeto do pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-187">If you specify configurations directly, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] creates a direct link between the configuration item and the package object property.</span></span> <span data-ttu-id="69772-188">As configurações diretas são a melhor escolha quando o local da origem não é alterado.</span><span class="sxs-lookup"><span data-stu-id="69772-188">Direct configurations are a better choice when the location of the source does not change.</span></span> <span data-ttu-id="69772-189">Por exemplo, se você tiver certeza de que todas as implantações no pacote usam o mesmo caminho de arquivo, poderá especificar um arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="69772-189">For example, if you are sure that all deployments in the package use the same file path, you can specify an XML configuration file.</span></span>  
  
 <span data-ttu-id="69772-190">As configurações indiretas usam variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="69772-190">Indirect configurations use environment variables.</span></span> <span data-ttu-id="69772-191">Em vez de especificar os parâmetros de configuração diretamente, a configuração aponta para uma variável de ambiente que, por sua vez, contém o valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="69772-191">Instead of specifying the configuration setting directly, the configuration points to an environment variable, which in turn contains the configuration value.</span></span> <span data-ttu-id="69772-192">O uso de configurações indiretas é a escolha mais adequada quando o local da configuração pode ser alterado em cada implantação de um pacote.</span><span class="sxs-lookup"><span data-stu-id="69772-192">Using indirect configurations is a better choice when the location of the configuration can change for each deployment of a package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="69772-193">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="69772-193">Related Tasks</span></span>  
 [<span data-ttu-id="69772-194">Criar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="69772-194">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
## <a name="related-content"></a><span data-ttu-id="69772-195">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="69772-195">Related Content</span></span>  
  
-   <span data-ttu-id="69772-196">Artigo técnico de [Noções básicas sobre configurações de pacotes do Integration Services](https://go.microsoft.com/fwlink/?LinkId=165643), em msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="69772-196">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="69772-197">Entrada de blog, [criando pacotes em configurações de pacote de código](https://go.microsoft.com/fwlink/?LinkId=217663), em www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="69772-197">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="69772-198">Entrada de blog, [exemplo de API – adicione programaticamente um arquivo de configuração a um pacote](https://go.microsoft.com/fwlink/?LinkId=217664), em Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="69772-198">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
  
