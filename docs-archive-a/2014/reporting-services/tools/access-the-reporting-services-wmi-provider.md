---
title: Acessar o provedor WMI do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services]
- programming [Reporting Services]
ms.assetid: 22cfbeb8-4ea3-4182-8f54-3341c771e87b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db0848ae8c988229a1804bbd4b19e6c38b68c35f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684063"
---
# <a name="access-the-reporting-services-wmi-provider"></a><span data-ttu-id="d79ef-102">Acessar o provedor WMI do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d79ef-102">Access the Reporting Services WMI Provider</span></span>
  <span data-ttu-id="d79ef-103">O provedor WMI do Reporting Services expõe duas classes WMI para administração de instâncias de servidor de relatório do modo nativo através de scripts:</span><span class="sxs-lookup"><span data-stu-id="d79ef-103">The Reporting Services WMI provider exposes two WMI classes for administration of Native mode report server instances through scripting:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d79ef-104">A partir da versão [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , o provedor WMI tem suporte apenas para servidores de relatórios no modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d79ef-104">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the WMI provider is supported for only native mode report servers.</span></span> <span data-ttu-id="d79ef-105">Servidores de relatórios no modo do SharePoint podem ser gerenciados com páginas Administração Central do SharePoint e scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d79ef-105">SharePoint mode report servers can be managed with SharePoint Central Administration pages and PowerShell scripts.</span></span>  
  
|<span data-ttu-id="d79ef-106">Classe</span><span class="sxs-lookup"><span data-stu-id="d79ef-106">Class</span></span>|<span data-ttu-id="d79ef-107">Namespace</span><span class="sxs-lookup"><span data-stu-id="d79ef-107">Namespace</span></span>|<span data-ttu-id="d79ef-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d79ef-108">Description</span></span>|  
|-----------|---------------|-----------------|  
|<span data-ttu-id="d79ef-109">MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="d79ef-109">MSReportServer_Instance</span></span>|<span data-ttu-id="d79ef-110">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11</span><span class="sxs-lookup"><span data-stu-id="d79ef-110">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11</span></span>|<span data-ttu-id="d79ef-111">Fornece as informações básicas exigidas para um cliente se conectar a um servidor de relatório instalado.</span><span class="sxs-lookup"><span data-stu-id="d79ef-111">Provides basic information required for a client to connect to an installed report server.</span></span>|  
|<span data-ttu-id="d79ef-112">MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d79ef-112">MSReportServer_ConfigurationSetting</span></span>|<span data-ttu-id="d79ef-113">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11\Admin</span><span class="sxs-lookup"><span data-stu-id="d79ef-113">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11\Admin</span></span>|<span data-ttu-id="d79ef-114">Representa os parâmetros de instalação e de tempo de execução de uma instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d79ef-114">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="d79ef-115">Esses parâmetros são armazenados no arquivo de configuração para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d79ef-115">These parameters are stored in the configuration file for the report server.</span></span><br /><br /> <span data-ttu-id="d79ef-116">**\*\* Importante \*\*** Esta classe é acessível apenas com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d79ef-116">**\*\* Important \*\*** This class is only accessible with administrative privileges.</span></span>|  
  
 <span data-ttu-id="d79ef-117">Uma instância de cada uma das classes anteriores é criada para cada instância de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d79ef-117">An instance of each of the above classes is created for each report server instance.</span></span> <span data-ttu-id="d79ef-118">Você pode usar qualquer ferramenta Microsoft ou de terceiros para acessar os objetos WMI expostos pelo servidor de relatório, inclusive interfaces de programação de WMI expostas pelo próprio .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d79ef-118">You can use any Microsoft or third party tools to access the WMI objects exposed by the report server, including WMI programming interfaces exposed by the .NET Framework itself.</span></span> <span data-ttu-id="d79ef-119">Este tópico descreve como acessar e usar as instâncias de classe WMI com o comando do PowerShell [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span><span class="sxs-lookup"><span data-stu-id="d79ef-119">This topic describes how to access and use the WMI class instances with the PowerShell command [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span></span>  
  
## <a name="determine-the-instance-name-in-the-namespace-string"></a><span data-ttu-id="d79ef-120">Determine o nome de instância na cadeia de caracteres de namespace</span><span class="sxs-lookup"><span data-stu-id="d79ef-120">Determine the Instance Name in the Namespace String</span></span>  
 <span data-ttu-id="d79ef-121">O nome de instância no caminho de namespace para as classes WMI do Reporting Services é uma codificação dos nomes de instância que você especifica ao instalar as instâncias nomeadas do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d79ef-121">The instance name in the namespace path for the Reporting Services WMI classes is an encoding of the instance names that you specify when installing the named Reporting Services instances.</span></span> <span data-ttu-id="d79ef-122">Isto é, caracteres especiais são codificados nos nomes de instância.</span><span class="sxs-lookup"><span data-stu-id="d79ef-122">Namely, special characters in the instance names are encoded.</span></span> <span data-ttu-id="d79ef-123">Por exemplo, um sublinhado (_) é codificado como "_5f"; assim, um nome de instância de "My_Instance" é codificado como "My_5fInstance" no caminho de namespace do WMI.</span><span class="sxs-lookup"><span data-stu-id="d79ef-123">For example, an underline (_) is encoded as "_5f", so an instance name of "My_Instance" is encoded as "My_5fInstance" in the WMI namespace path.</span></span>  
  
 <span data-ttu-id="d79ef-124">Para listar os nomes de instância codificados de suas instâncias de servidor de relatório no caminho de namespace do WMI, use o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d79ef-124">To list the encoded instance names of your report server instances in the WMI namespace path, use the following PowerShell command:</span></span>  
  
```powershell
Get-WmiObject -Namespace root\Microsoft\SqlServer\ReportServer -Class __Namespace -ComputerName hostname | Select Name  
```  
  
## <a name="access-the-wmi-classes-using-powershell"></a><span data-ttu-id="d79ef-125">Acesse as classes WMI usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d79ef-125">Access the WMI Classes Using PowerShell</span></span>  
 <span data-ttu-id="d79ef-126">Para acessar as classes WMI, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d79ef-126">To access the WMI classes, run the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace <namespacename> -Class <classname> -ComputerName <hostname>  
```  
  
 <span data-ttu-id="d79ef-127">Por exemplo, para acessar a classe MSReportServer_ConfigurationSetting na instância de servidor de relatório padrão do myrshost de host, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="d79ef-127">For example, to access the MSReportServer_ConfigurationSetting class on the default report server instance of the host myrshost, run the following command.</span></span> <span data-ttu-id="d79ef-128">A instância de servidor de relatório padrão deve ser instalada no myrshost para este comando ter êxito.</span><span class="sxs-lookup"><span data-stu-id="d79ef-128">The default report server instance must be installed on myrshost for this command to succeed.</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLSERER\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost  
```  
  
 <span data-ttu-id="d79ef-129">Esta sintaxe de comando gera todos os nomes e valores de propriedade de classe.</span><span class="sxs-lookup"><span data-stu-id="d79ef-129">This command syntax outputs all class property names and values.</span></span> <span data-ttu-id="d79ef-130">Observe que todas as instâncias da classe MSReportServer_ConfigurationSetting são retornadas, embora você esteja acessando a classe no namespace da instância de servidor de relatório padrão (RS_MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d79ef-130">Note that all instances of the class MSReportServer_ConfigurationSetting is returned, even though you are accessing the class in the namespace of the default report server instance (RS_MSSQLSERVER).</span></span> <span data-ttu-id="d79ef-131">Por exemplo, se myrshost for instalado com a instância de servidor de relatório padrão e uma instância de servidor de relatório nomeada chamada SHAREPOINT, este comando retornará dois objetos WMI e gerará os nomes e valores de propriedade para ambas as instâncias de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d79ef-131">For example, if myrshost is installed with the default report server instance and a named report server instance called SHAREPOINT, this command will return two WMI objects and output the property names and values for both report server instances.</span></span>  
  
 <span data-ttu-id="d79ef-132">Para retornar uma instância de classe específica quando várias instâncias são retornadas, use o parâmetro -Filter para filtrar os resultados com base em propriedades com valores exclusivos como InstanceName.</span><span class="sxs-lookup"><span data-stu-id="d79ef-132">To return a specific class instance when multiple instances are returned, use the -Filter parameter to filter the results based on properties with unique values such as InstanceName.</span></span> <span data-ttu-id="d79ef-133">Por exemplo, para retornar apenas o objeto WMI para a instância de servidor de relatório padrão, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d79ef-133">For example, to return only the WMI object for the default report server instance, use the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='MSSQLSERVER'"  
```  
  
## <a name="query-the-available-methods-and-properties"></a><span data-ttu-id="d79ef-134">Consultar os métodos e as propriedades disponíveis</span><span class="sxs-lookup"><span data-stu-id="d79ef-134">Query the Available Methods and Properties</span></span>  
 <span data-ttu-id="d79ef-135">Para consultar que métodos e propriedades estão disponíveis em uma das classes WMI do Reporting Services, canalize os resultados de Get-WmiObject para o comando Get-Member.</span><span class="sxs-lookup"><span data-stu-id="d79ef-135">To see what methods and properties are available in one of the Reporting Services WMI classes, pipe the results from Get-WmiObject to the Get-Member command.</span></span> <span data-ttu-id="d79ef-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d79ef-136">For example:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost | Get-Member  
```  
  
 <span data-ttu-id="d79ef-137">Para obter a documentação sobre as propriedades e métodos do Reporting Services classes WMI, consulte....</span><span class="sxs-lookup"><span data-stu-id="d79ef-137">For documentation on the properties and methods of the Reporting Services WMI classes, see ....</span></span>  
  
## <a name="use-a-wmi-method-or-property"></a><span data-ttu-id="d79ef-138">Usar um método ou propriedade WMI</span><span class="sxs-lookup"><span data-stu-id="d79ef-138">Use a WMI Method or Property</span></span>  
 <span data-ttu-id="d79ef-139">Quando você tiver os objetos WMI para as classes do Reporting Services e conhecer os métodos e as propriedades disponíveis, poderá usar esses métodos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="d79ef-139">Once you have the WMI objects to the Reporting Services classes and know the available methods and properties, you can use these methods and properties.</span></span> <span data-ttu-id="d79ef-140">Por exemplo, se você tiver uma instância de servidor de relatório nomeada no modo Integrado do SharePoint chamado SHAREPOINT, use a seguinte sequência de comandos para recuperar a URL para o site de Administração Central do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="d79ef-140">For example, if you have a named report server instance in SharePoint integrated mode called SHAREPOINT, use the following command sequence to retrieve the URL for the SharePoint Central Administration site:</span></span>  
  
```powershell
$rsconfig = Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='SHAREPOINT'"  
$rsconfig.GetAdminSiteUrl()  
```  
  
## <a name="see-also"></a><span data-ttu-id="d79ef-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d79ef-141">See Also</span></span>
 <span data-ttu-id="d79ef-142">[Reporting Services referência da biblioteca do provedor WMI &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d79ef-142">[Reporting Services WMI Provider Library Reference &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="d79ef-143">Arquivo de configuração RSReportServer</span><span class="sxs-lookup"><span data-stu-id="d79ef-143">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
