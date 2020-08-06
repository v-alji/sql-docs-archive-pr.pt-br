---
title: Habilitar o registro em log programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- Integration Services packages, logs
- SSIS logging
- log providers [Integration Services]
- logs [Integration Services], enabling
- LoggingMode property
- LogProvider object
- packages [Integration Services], logs
ms.assetid: 3222a1ed-83eb-421c-b299-a53b67bba740
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff7f81aca330960e4e94b0343080a37ded8c1273
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680604"
---
# <a name="enabling-logging-programmatically"></a><span data-ttu-id="2da3a-102">Habilitando o registro em log programaticamente</span><span class="sxs-lookup"><span data-stu-id="2da3a-102">Enabling Logging Programmatically</span></span>
  <span data-ttu-id="2da3a-103">O mecanismo de tempo de execução fornece uma coleção de objetos <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> que permitem que informações específicas a eventos sejam capturadas durante a validação e a execução de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2da3a-103">The run-time engine provides a collection of <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects that enable event-specific information to be captured during package validation and execution.</span></span> <span data-ttu-id="2da3a-104">Os objetos <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> estão disponíveis para objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer>, inclusive os objetos <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop> e <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="2da3a-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects are available to <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer> objects, including the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>, and <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> objects.</span></span> <span data-ttu-id="2da3a-105">O registro em log é habilitado em contêineres individuais ou no pacote inteiro.</span><span class="sxs-lookup"><span data-stu-id="2da3a-105">Logging is enabled on individual containers, or on the whole package.</span></span>

 <span data-ttu-id="2da3a-106">Há vários tipos de provedores de log disponíveis para uso por um contêiner.</span><span class="sxs-lookup"><span data-stu-id="2da3a-106">There are several types of log providers that are available for a container to use.</span></span> <span data-ttu-id="2da3a-107">Isso fornece a flexibilidade para criar e armazenar informações de log em diversos formatos.</span><span class="sxs-lookup"><span data-stu-id="2da3a-107">This provides the flexibility to create and store log information in many formats.</span></span> <span data-ttu-id="2da3a-108">A inscrição de um objeto contêiner no registro em log é um processo de duas etapas: primeiro o registro é habilitado e depois um provedor de log é selecionado.</span><span class="sxs-lookup"><span data-stu-id="2da3a-108">Enlisting a container object in logging is a two-step process: first logging is enabled, and then a log provider is selected.</span></span> <span data-ttu-id="2da3a-109">As propriedades <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> do contêiner são usadas para especificar os eventos registrados e selecionar o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="2da3a-109">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> properties of the container are used to specify the logged events and to select the log provider.</span></span>

## <a name="enabling-logging"></a><span data-ttu-id="2da3a-110">Habilitando o registro em log</span><span class="sxs-lookup"><span data-stu-id="2da3a-110">Enabling Logging</span></span>
 <span data-ttu-id="2da3a-111">A propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>, localizada em cada contêiner que pode executar o registro em log, determina se as informações de evento do contêiner são registradas no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2da3a-111">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property, found in each container that can perform logging, determines whether the container's event information is recorded to the event log.</span></span> <span data-ttu-id="2da3a-112">É atribuído um valor a essa propriedade a partir da estrutura <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> e ele é herdado por padrão do pai do contêiner.</span><span class="sxs-lookup"><span data-stu-id="2da3a-112">This property is assigned a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> structure, and is inherited from the container's parent by default.</span></span> <span data-ttu-id="2da3a-113">Se o contêiner for um pacote e não tiver pai, a propriedade usará o <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, cujo padrão é `Disabled`.</span><span class="sxs-lookup"><span data-stu-id="2da3a-113">If the container is a package, and therefore has no parent, the property uses the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, which defaults to `Disabled`.</span></span>

### <a name="selecting-a-log-provider"></a><span data-ttu-id="2da3a-114">Selecionando um provedor de log</span><span class="sxs-lookup"><span data-stu-id="2da3a-114">Selecting a Log Provider</span></span>
 <span data-ttu-id="2da3a-115">Depois que a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> é definida como `Enabled`, um provedor de log é adicionado à coleção <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> do contêiner para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="2da3a-115">After the <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property is set to `Enabled`, a log provider is added to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection of the container to complete the process.</span></span> <span data-ttu-id="2da3a-116">A coleção <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> está disponível no objeto <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> e contém os provedores de log selecionados para o contêiner.</span><span class="sxs-lookup"><span data-stu-id="2da3a-116">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection is available on the <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> object, and contains the log providers selected for the container.</span></span> <span data-ttu-id="2da3a-117">O método <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> é chamado para criar um provedor e adicioná-lo à coleção.</span><span class="sxs-lookup"><span data-stu-id="2da3a-117">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> method is called to create a provider and add it to the collection.</span></span> <span data-ttu-id="2da3a-118">O método retorna o provedor de log que foi adicionado à coleção.</span><span class="sxs-lookup"><span data-stu-id="2da3a-118">The method then returns the log provider that was added to the collection.</span></span> <span data-ttu-id="2da3a-119">Cada provedor tem parâmetros de configuração que são exclusivos desse provedor e essas propriedades são definidas através da propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="2da3a-119">Each provider has configuration settings that are unique to that provider, and these properties are set using the <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> property.</span></span>

 <span data-ttu-id="2da3a-120">A tabela a seguir lista os provedores de log disponíveis, sua descrição e as informações sobre <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="2da3a-120">The following table lists the available log providers, their description, and their <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> information.</span></span>

|<span data-ttu-id="2da3a-121">Provedor</span><span class="sxs-lookup"><span data-stu-id="2da3a-121">Provider</span></span>|<span data-ttu-id="2da3a-122">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2da3a-122">Description</span></span>|<span data-ttu-id="2da3a-123">Propriedade ConfigString</span><span class="sxs-lookup"><span data-stu-id="2da3a-123">ConfigString property</span></span>|
|--------------|-----------------|---------------------------|
|<span data-ttu-id="2da3a-124">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="2da3a-124">SQL Server Profiler</span></span>|<span data-ttu-id="2da3a-125">Gera rastreamentos do SQL que podem ser capturados e exibidos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span><span class="sxs-lookup"><span data-stu-id="2da3a-125">Generates SQL traces that may be captured and viewed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span></span> <span data-ttu-id="2da3a-126">A extensão de nome de arquivo padrão deste provedor é .trc.</span><span class="sxs-lookup"><span data-stu-id="2da3a-126">The default file name extension for this provider is .trc.</span></span>|<span data-ttu-id="2da3a-127">Nenhuma configuração é necessária.</span><span class="sxs-lookup"><span data-stu-id="2da3a-127">No configuration is required.</span></span>|
|<span data-ttu-id="2da3a-128">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2da3a-128">SQL Server</span></span>|<span data-ttu-id="2da3a-129">Escreve entradas de log de evento na tabela **sysssislog** em qualquer banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2da3a-129">Writes event log entries to the **sysssislog** table in any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>|<span data-ttu-id="2da3a-130">O provedor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exige a especificação da conexão ao banco de dados e também o nome do banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="2da3a-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider requires that the connection to the database be specified, and also the target database name.</span></span>|
|<span data-ttu-id="2da3a-131">Arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="2da3a-131">Text File</span></span>|<span data-ttu-id="2da3a-132">Grava entradas do log de eventos em arquivos de texto ASCII em formato CSV (valores separados por vírgula).</span><span class="sxs-lookup"><span data-stu-id="2da3a-132">Writes event log entries to ASCII text files in a comma-separated value (CSV) format.</span></span> <span data-ttu-id="2da3a-133">A extensão de nome de arquivo padrão deste provedor é .log.</span><span class="sxs-lookup"><span data-stu-id="2da3a-133">The default file name extension for this provider is .log.</span></span>|<span data-ttu-id="2da3a-134">O nome do gerenciador de conexões de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2da3a-134">The name of a file connection manager.</span></span>|
|<span data-ttu-id="2da3a-135">Log de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="2da3a-135">Windows Event Log</span></span>|<span data-ttu-id="2da3a-136">Conecta-se ao log de eventos padrão do Windows no computador local no log do Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2da3a-136">Logs to standard Windows Event Log on the local computer in the Application log.</span></span>|<span data-ttu-id="2da3a-137">Nenhuma configuração é necessária.</span><span class="sxs-lookup"><span data-stu-id="2da3a-137">No configuration is required.</span></span>|
|<span data-ttu-id="2da3a-138">Arquivo XML</span><span class="sxs-lookup"><span data-stu-id="2da3a-138">XML File</span></span>|<span data-ttu-id="2da3a-139">Grava entradas do log de eventos no arquivo em formato XML.</span><span class="sxs-lookup"><span data-stu-id="2da3a-139">Writes event log entries to XML formatted file.</span></span> <span data-ttu-id="2da3a-140">A extensão padrão do nome de arquivo desse provedor é .xml.</span><span class="sxs-lookup"><span data-stu-id="2da3a-140">The default file name extension for this provider is .xml</span></span>|<span data-ttu-id="2da3a-141">O nome do gerenciador de conexões de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2da3a-141">The name of a file connection manager.</span></span>|

 <span data-ttu-id="2da3a-142">Os eventos são incluídos em ou excluídos do log de eventos através da definição das propriedades `EventFilterKind` e `EventFilter` do contêiner.</span><span class="sxs-lookup"><span data-stu-id="2da3a-142">Events are included in or excluded from the event log by setting the `EventFilterKind` and the `EventFilter` properties of the container.</span></span> <span data-ttu-id="2da3a-143">A estrutura `EventFilterKind` contém dois valores, `ExclusionFilter` e `InclusionFilter`, que indicam se os eventos adicionados no `EventFilter` são incluídos no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2da3a-143">The `EventFilterKind` structure contains two values, `ExclusionFilter` and `InclusionFilter`, that indicate whether the events that are added to the `EventFilter` are included in the event log.</span></span> <span data-ttu-id="2da3a-144">A propriedade `EventFilter` recebe uma matriz de cadeia de caracteres que contém os nomes dos eventos que são o assunto da filtragem.</span><span class="sxs-lookup"><span data-stu-id="2da3a-144">The `EventFilter` property is then assigned a string array that contains the names of the events that are the subject of the filtering.</span></span>

 <span data-ttu-id="2da3a-145">O código a seguir habilita o registro em um pacote, adiciona o provedor de log dos arquivos de Texto à coleção <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> e especifica uma lista de eventos para incluir na saída de log.</span><span class="sxs-lookup"><span data-stu-id="2da3a-145">The following code enables logging on a package, adds the log provider for Text files to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection, and specifies a list of events to include in the logging output.</span></span>

## <a name="sample"></a><span data-ttu-id="2da3a-146">Amostra</span><span class="sxs-lookup"><span data-stu-id="2da3a-146">Sample</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package p = new Package();

      ConnectionManager loggingConnection = p.Connections.Add("FILE");
      loggingConnection.ConnectionString = @"C:\SSISPackageLog.txt";

      LogProvider provider = p.LogProviders.Add("DTS.LogProviderTextFile.2");
      provider.ConfigString = loggingConnection.Name;
      p.LoggingOptions.SelectedLogProviders.Add(provider);
      p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion;
      p.LoggingOptions.EventFilter = new String[] { "OnPreExecute", 
         "OnPostExecute", "OnError", "OnWarning", "OnInformation" };
      p.LoggingMode = DTSLoggingMode.Enabled;

      // Add tasks and other objects to the package.

    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim p As Package = New Package()

    Dim loggingConnection As ConnectionManager = p.Connections.Add("FILE")
    loggingConnection.ConnectionString = "C:\SSISPackageLog.txt"

    Dim provider As LogProvider = p.LogProviders.Add("DTS.LogProviderTextFile.2")
    provider.ConfigString = loggingConnection.Name
    p.LoggingOptions.SelectedLogProviders.Add(provider)
    p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion
    p.LoggingOptions.EventFilter = New String() {"OnPreExecute", _
       "OnPostExecute", "OnError", "OnWarning", "OnInformation"}
    p.LoggingMode = DTSLoggingMode.Enabled

    ' Add tasks and other objects to the package.

  End Sub

End Module
```

<span data-ttu-id="2da3a-147">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2da3a-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2da3a-148">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="2da3a-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2da3a-149">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="2da3a-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2da3a-150">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="2da3a-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="2da3a-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2da3a-151">See Also</span></span>
 [<span data-ttu-id="2da3a-152">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2da3a-152">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)


