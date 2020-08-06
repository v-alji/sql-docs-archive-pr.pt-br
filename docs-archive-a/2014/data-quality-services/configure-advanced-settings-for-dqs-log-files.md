---
title: Definir configurações avançadas para arquivos de log do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- log files,advanced settings
- dqs log files,advanced settings
ms.assetid: 1d565748-9759-425c-ae38-4d2032a86868
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ad41b0cac95f9bfe5565ccbac16b0fda3e28ddf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678984"
---
# <a name="configure-advanced-settings-for-dqs-log-files"></a><span data-ttu-id="a1a3a-102">Definir configurações avançadas para arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="a1a3a-102">Configure Advanced Settings for DQS Log Files</span></span>
  <span data-ttu-id="a1a3a-103">Este tópico descreve como definir configurações avançadas para os arquivos de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] e do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , como definir o limite de tamanho de arquivo de rolagem dos arquivos de log, definir o padrão de carimbo de data/hora dos eventos etc.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-103">This topic describes how to configure advanced settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log files, such as set the rolling file size limit of the log files, set the time stamp pattern of the events, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1a3a-104">Essas atividades não podem ser executadas por meio do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], e destinam-se apenas a usuários avançados.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-104">These activities cannot be performed using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and is intended for advanced users only.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a1a3a-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a1a3a-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a1a3a-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="a1a3a-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a1a3a-107">Permissões</span><span class="sxs-lookup"><span data-stu-id="a1a3a-107">Permissions</span></span>  
  
-   <span data-ttu-id="a1a3a-108">A conta de usuário do Windows deve ser um membro da função de servidor fixa sysadmin na instância do SQL Server para modificar as configurações na tabela A_CONFIGURATION do banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-108">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to modify configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
-   <span data-ttu-id="a1a3a-109">Você deve estar conectado como membro do grupo Administradores no computador onde está modificando o arquivo DQLog.Client.xml para definir as configurações de log do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1a3a-109">You must be logged on as a member of the Administrators group on the computer where you are modifying the DQLog.Client.xml file to configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] logging settings.</span></span>  
  
##  <a name="configure-data-quality-server-log-settings"></a><a name="DQSServer"></a><span data-ttu-id="a1a3a-110">Definir configurações de log do servidor de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="a1a3a-110">Configure Data Quality Server Log Settings</span></span>  
 <span data-ttu-id="a1a3a-111">As configurações de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] estão presentes em um formato XML na coluna **VALUE** da linha **ServerLogging** na tabela A_CONFIGURATION no banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-111">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings are present in an XML format in the **VALUE** column of the **ServerLogging** row in the A_CONFIGURATION table in the DQS_MAIN database.</span></span> <span data-ttu-id="a1a3a-112">Você pode executar a seguinte consulta SQL para exibir informações de configuração:</span><span class="sxs-lookup"><span data-stu-id="a1a3a-112">You can run the following SQL query to view the configuration information:</span></span>  
  
```sql  
select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'; 
```  
  
 <span data-ttu-id="a1a3a-113">Você deve atualizar as informações apropriadas na coluna **VALUE** da linha **ServerLogging** para alterar as configurações de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1a3a-113">You must update the appropriate information in the **VALUE** column of the **ServerLogging** row to change the configuration settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging.</span></span> <span data-ttu-id="a1a3a-114">Neste exemplo, atualizaremos as configurações de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] para definir o limite de tamanho do arquivo de rolagem como 25000 KB (o padrão é 20000 KB).</span><span class="sxs-lookup"><span data-stu-id="a1a3a-114">In this example, we will update the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings to set the rolling file size limit to 25000 KB (the default is 20000 KB).</span></span>  
  
1.  <span data-ttu-id="a1a3a-115">Inicie o Microsoft SQL Server Management Studio e conecte-se à instância apropriada do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-115">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="a1a3a-116">No Pesquisador de Objetos, clique com o botão direito do mouse no servidor e, depois, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-116">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a1a3a-117">Na janela Editor de Consultas, copie as seguintes instruções SQL:</span><span class="sxs-lookup"><span data-stu-id="a1a3a-117">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    -- Begin the transaction.  
    BEGIN TRAN  
    GO  
    -- set the XML value field for the row with name=ServerLogging  
    update DQS_MAIN.dbo.A_CONFIGURATION   
    set VALUE='<configuration>  
      <configSections>  
        <section name="loggingConfiguration" type="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.LoggingSettings, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" />  
      </configSections>  
      <loggingConfiguration name="Logging Application Block" tracingEnabled="true" defaultCategory="" logWarningsWhenNoCategoriesMatch="true">  
        <listeners>  
          <add fileName="###REPLACE_THIS_WITH_SQL_SERVER_INSTANCE_LOG_FOLDER_NAME###DQServerLog.###REPLACE_THIS_WITH_SQL_CATALOG_NAME###.log" footer="" formatter="Custom Text Formatter" header="" rollFileExistsBehavior="Increment" rollInterval="None" rollSizeKB="25000" timeStampPattern="yyyy-MM-dd" listenerDataType="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.RollingFlatFileTraceListenerData, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" traceOutputOptions="None" filter="All" type="Microsoft.Practices.EnterpriseLibrary.Logging.TraceListeners.RollingFlatFileTraceListener, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Rolling Flat File Trace Listener" />  
        </listeners>  
        <formatters>  
          <add template="{timestamp(local)}|[{threadName}]|{dictionary({value}|)}{message}" type="Microsoft.Practices.EnterpriseLibrary.Logging.Formatters.TextFormatter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Custom Text Formatter" />  
        </formatters>  
        <logFilters>  
          <add enabled="true" type="Microsoft.Practices.EnterpriseLibrary.Logging.Filters.LogEnabledFilter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="LogEnabled Filter" />  
        </logFilters>  
        <categorySources />  
        <specialSources>  
          <allEvents switchValue="All" name="All Events" />  
          <notProcessed switchValue="All" name="Unprocessed Category" />  
          <errors switchValue="All" name="Logging Errors & Warnings">  
            <listeners>  
              <add name="Rolling Flat File Trace Listener" />  
            </listeners>  
          </errors>  
        </specialSources>  
      </loggingConfiguration>  
    </configuration>'  
    WHERE NAME='ServerLogging'  
    GO  
    -- check the result  
    select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'  
  
    -- Commit the transaction.  
    COMMIT TRAN  
  
    ```  
  
4.  <span data-ttu-id="a1a3a-118">Pressione F5 para executar as instruções.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-118">Press F5 to execute the statements.</span></span> <span data-ttu-id="a1a3a-119">Consulte o painel **Resultados** para verificar se as instruções foram executadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-119">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
5.  <span data-ttu-id="a1a3a-120">Para aplicar as alterações feitas na configuração de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , execute as seguintes instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-120">To apply changes done to the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging configuration, you must run the following Transact-SQL statements.</span></span> <span data-ttu-id="a1a3a-121">Abra uma nova janela Editor de Consultas e cole as seguintes instruções Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="a1a3a-121">Open a new Query Editor window, and paste the following Transact-SQL statements:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    DECLARE @return_value int  
    EXEC @return_value = [internal_core].[RefreshLogSettings]  
    SELECT 'Return Value' = @return_value  
    GO  
    ```  
  
6.  <span data-ttu-id="a1a3a-122">Pressione F5 para executar as instruções.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-122">Press F5 to execute the statements.</span></span> <span data-ttu-id="a1a3a-123">Consulte o painel **Resultados** para verificar se as instruções foram executadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-123">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1a3a-124">As configurações de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] são geradas e armazenadas dinamicamente no arquivo DQS_MAIN.Log, que geralmente estará disponível em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log caso você tenha instalado a instância padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-124">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging settings configuration is dynamically generated and stored in the DQS_MAIN.Log file, which is typically available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log if you installed the default instance of SQL Server.</span></span> <span data-ttu-id="a1a3a-125">No entanto, as alterações feitas diretamente nesse arquivo não são mantidas, sendo substituídas pelas configurações da tabela A_CONFIGURATION no banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-125">However, changes done directly in this file do not hold, and are overwritten by the configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
##  <a name="configure-data-quality-client-log-settings"></a><a name="DQSClient"></a><span data-ttu-id="a1a3a-126">Definir configurações de log de Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="a1a3a-126">Configure Data Quality Client Log Settings</span></span>  
 <span data-ttu-id="a1a3a-127">O [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] arquivo de configuração de configuração de log, DQLog.Client.xml, normalmente está disponível em C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. O conteúdo do arquivo XML é semelhante ao arquivo XML que você modificou anteriormente para as [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] definições de configuração de log.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log setting configuration file, DQLog.Client.xml, is typically available at C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. The contents of the XML file is similar to the XML file that you modified earlier for the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="a1a3a-128">Para configurar as configurações de log do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a1a3a-128">To configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log settings:</span></span>  
  
1.  <span data-ttu-id="a1a3a-129">Execute qualquer ferramenta de edição XML ou bloco de notas como um administrador.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-129">Run any XML editing tool or notepad as an administrator.</span></span>  
  
2.  <span data-ttu-id="a1a3a-130">Abra o arquivo DQLog.Client.xml na ferramenta ou no bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-130">Open the DQLog.Client.xml file in the tool or notepad.</span></span>  
  
3.  <span data-ttu-id="a1a3a-131">Faça as alterações necessárias e salve o arquivo para aplicar as novas alterações de log.</span><span class="sxs-lookup"><span data-stu-id="a1a3a-131">Make the required changes, and save the file to apply the new logging changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a3a-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a1a3a-132">See Also</span></span>  
 [<span data-ttu-id="a1a3a-133">Configurar níveis de severidade para arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="a1a3a-133">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)  
  
  
