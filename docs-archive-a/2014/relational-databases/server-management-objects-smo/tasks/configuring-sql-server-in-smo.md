---
title: Configurando SQL Server em SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server, configuring
- configuration options [SMO]
ms.assetid: 0a372643-15cb-45a7-8665-04f1215df8ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6da1bca0aec650c01553b42bc2f3628b0bf7282e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684645"
---
# <a name="configuring-sql-server-in-smo"></a><span data-ttu-id="952ef-102">Configurando o SQL Server no SMO</span><span class="sxs-lookup"><span data-stu-id="952ef-102">Configuring SQL Server in SMO</span></span>
  <span data-ttu-id="952ef-103">No SMO, o objeto, o objeto, <xref:Microsoft.SqlServer.Management.Smo.Information> <xref:Microsoft.SqlServer.Management.Smo.Settings> o objeto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e o <xref:Microsoft.SqlServer.Management.Smo.Configuration> objeto contêm configurações e informações para a instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="952ef-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Information> object, the <xref:Microsoft.SqlServer.Management.Smo.Settings> object, the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object, and the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object contain settings and information for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="952ef-104">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tem várias propriedades que descrevem o comportamento da instância instalada.</span><span class="sxs-lookup"><span data-stu-id="952ef-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has numerous properties that describe the behavior of the installed instance.</span></span> <span data-ttu-id="952ef-105">As propriedades descrevem opções de inicialização, os padrões do servidor, arquivos e diretórios, informações sobre o sistema e o processador, produtos e versões, informações sobre conexões, opções de memória, seleções de linguagem e ordenação, e o modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="952ef-105">The properties describe the startup options, the server defaults, files and directories, system and processor information, product and versions, connection information, memory options, language and collation selections, and the authentication mode.</span></span>  
  
## <a name="sql-server-configuration"></a><span data-ttu-id="952ef-106">Configuração do SQL Server</span><span class="sxs-lookup"><span data-stu-id="952ef-106">SQL Server Configuration</span></span>  
 <span data-ttu-id="952ef-107">As propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Information> contêm informações sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], tais como processador e plataforma.</span><span class="sxs-lookup"><span data-stu-id="952ef-107">The <xref:Microsoft.SqlServer.Management.Smo.Information> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], such as processor and platform.</span></span>  
  
 <span data-ttu-id="952ef-108">As propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Settings> contêm informações sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="952ef-108">The <xref:Microsoft.SqlServer.Management.Smo.Settings> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="952ef-109">O diretório e o arquivo de banco de dados padrão podem ser modificados, além do Perfil de Email e da Conta de Servidor.</span><span class="sxs-lookup"><span data-stu-id="952ef-109">The default database file and directory can be modified in addition to the Mail Profile and the Server Account.</span></span> <span data-ttu-id="952ef-110">Essas propriedades serão mantidas enquanto durar a conexão.</span><span class="sxs-lookup"><span data-stu-id="952ef-110">These properties remain for the duration of the connection.</span></span>  
  
 <span data-ttu-id="952ef-111">As propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> contêm informações sobre o comportamento das conexões atuais em relação a aritmética, padrões ANSI e transações.</span><span class="sxs-lookup"><span data-stu-id="952ef-111">The <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object properties contain information about the current connections behavior relating to arithmetic, ANSI standards, and transactions.</span></span>  
  
 <span data-ttu-id="952ef-112">Também há um conjunto de opções de configuração que é representado pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="952ef-112">There is also a set of configuration options that is represented by the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object.</span></span> <span data-ttu-id="952ef-113">Ele contém um conjunto de propriedades que representam as opções que podem ser modificadas pelo procedimento armazenado `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="952ef-113">It contains a set of properties that represent the options that can be modified by the `sp_configure` stored procedure.</span></span> <span data-ttu-id="952ef-114">Opções como **aumento de prioridade**, **intervalo de recuperação** e tamanho do pacote de **rede**controlam o desempenho da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="952ef-114">Options such as **Priority Boost**, **Recovery Interval** and **Network Packet Size**control the performance of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="952ef-115">Muitas dessas opções podem ser alteradas de forma dinâmica, mas, em alguns casos, o valor é primeiro configurado e depois alterado quando a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é reiniciada.</span><span class="sxs-lookup"><span data-stu-id="952ef-115">Many of these options can be changed dynamically, but in some cases the value is first configured and then changed when the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
 <span data-ttu-id="952ef-116">Há uma propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Configuration> para cada opção de configuração.</span><span class="sxs-lookup"><span data-stu-id="952ef-116">There is a <xref:Microsoft.SqlServer.Management.Smo.Configuration> object property for every configuration option.</span></span> <span data-ttu-id="952ef-117">Usando o objeto <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>, você pode modificar o parâmetro de configuração global.</span><span class="sxs-lookup"><span data-stu-id="952ef-117">Using the <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> object you can modify the global configuration setting.</span></span> <span data-ttu-id="952ef-118">Muitas propriedades têm valores máximo e mínimo que também são armazenados como propriedades <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="952ef-118">Many properties have maximum and minimum values that are also stored as <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> properties.</span></span> <span data-ttu-id="952ef-119">Essas propriedades exigem o <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> método para confirmar a alteração na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="952ef-119">These properties require the <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> method to commit the change to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="952ef-120">Todas as opções de configuração no objeto <xref:Microsoft.SqlServer.Management.Smo.Configuration> devem ser alteradas pelo administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="952ef-120">All of the configuration options in the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object must be changed by the system administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="952ef-121">Exemplos</span><span class="sxs-lookup"><span data-stu-id="952ef-121">Examples</span></span>  
 <span data-ttu-id="952ef-122">Para os exemplos de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="952ef-122">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="952ef-123">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="952ef-123">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="modifying-sql-server-configuration-options-in-visual-basic"></a><span data-ttu-id="952ef-124">Modificando as opções de configuração do SQL Server no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="952ef-124">Modifying SQL Server Configuration Options in Visual Basic</span></span>  
 <span data-ttu-id="952ef-125">O exemplo de código mostra como atualizar uma opção de configuração no Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="952ef-125">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="952ef-126">Ele também recupera e exibe informações sobre os valores máximo e mínimo da opção de configuração especificada.</span><span class="sxs-lookup"><span data-stu-id="952ef-126">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="952ef-127">Finalmente, o programa informa ao usuário se a alteração foi feita dinamicamente ou se ela foi armazenada até o reinício da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="952ef-127">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure2](SMO How to#SMO_VBConfigure2)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-basic"></a><span data-ttu-id="952ef-128">Modificando configurações do SQL Server no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="952ef-128">Modifying SQL Server Settings in Visual Basic</span></span>  
 <span data-ttu-id="952ef-129">O exemplo de código exibe informações sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no <xref:Microsoft.SqlServer.Management.Smo.Information> e do <xref:Microsoft.SqlServer.Management.Smo.Settings> , e modifica as configurações nas <xref:Microsoft.SqlServer.Management.Smo.Settings> Propriedades do objeto e <xref:Microsoft.SqlServer.Management.Smo.UserOptions> .</span><span class="sxs-lookup"><span data-stu-id="952ef-129">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="952ef-130">No exemplo, ambos os objetos <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e <xref:Microsoft.SqlServer.Management.Smo.Settings> têm um método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="952ef-130">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="952ef-131">Você pode executar os métodos <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> para eles individualmente.</span><span class="sxs-lookup"><span data-stu-id="952ef-131">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure1](SMO How to#SMO_VBConfigure1)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-c"></a><span data-ttu-id="952ef-132">Modificando configurações do SQL Server no Visual C#</span><span class="sxs-lookup"><span data-stu-id="952ef-132">Modifying SQL Server Settings in Visual C#</span></span>  
 <span data-ttu-id="952ef-133">O exemplo de código exibe informações sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no <xref:Microsoft.SqlServer.Management.Smo.Information> e do <xref:Microsoft.SqlServer.Management.Smo.Settings> , e modifica as configurações nas <xref:Microsoft.SqlServer.Management.Smo.Settings> Propriedades do objeto e <xref:Microsoft.SqlServer.Management.Smo.UserOptions> .</span><span class="sxs-lookup"><span data-stu-id="952ef-133">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="952ef-134">No exemplo, ambos os objetos <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e <xref:Microsoft.SqlServer.Management.Smo.Settings> têm um método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="952ef-134">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="952ef-135">Você pode executar os métodos <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> para eles individualmente.</span><span class="sxs-lookup"><span data-stu-id="952ef-135">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
 `//Connect to the local, default instance of SQL Server.`  
  
```csharp
{  
            Server srv = new Server();  
            //Display all the configuration options.   
  
            foreach (ConfigProperty p in srv.Configuration.Properties)  
            {  
                Console.WriteLine(p.DisplayName);  
            }  
            Console.WriteLine("There are " + srv.Configuration.Properties.Count.ToString() + " configuration options.");  
            //Display the maximum and minimum values for ShowAdvancedOptions.   
            int min = 0;  
            int max = 0;  
            min = srv.Configuration.ShowAdvancedOptions.Minimum;  
            max = srv.Configuration.ShowAdvancedOptions.Maximum;  
            Console.WriteLine("Minimum and Maximum values are " + min + " and " + max + ".");  
            //Modify the value of ShowAdvancedOptions and run the Alter method.   
            srv.Configuration.ShowAdvancedOptions.ConfigValue = 0;  
            srv.Configuration.Alter();  
            //Display when the change takes place according to the IsDynamic property.   
            if (srv.Configuration.ShowAdvancedOptions.IsDynamic == true)  
            {  
                Console.WriteLine("Configuration option has been updated.");  
            }  
            else  
            {  
                Console.WriteLine("Configuration option will be updated when SQL Server is restarted.");  
            }  
        }  
```  
  
## <a name="modifying-sql-server-settings-in-powershell"></a><span data-ttu-id="952ef-136">Modificando configurações do SQL Server no PowerShell</span><span class="sxs-lookup"><span data-stu-id="952ef-136">Modifying SQL Server Settings in PowerShell</span></span>  
 <span data-ttu-id="952ef-137">O exemplo de código exibe informações sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no <xref:Microsoft.SqlServer.Management.Smo.Information> e do <xref:Microsoft.SqlServer.Management.Smo.Settings> , e modifica as configurações nas <xref:Microsoft.SqlServer.Management.Smo.Settings> Propriedades do objeto e <xref:Microsoft.SqlServer.Management.Smo.UserOptions> .</span><span class="sxs-lookup"><span data-stu-id="952ef-137">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="952ef-138">No exemplo, ambos os objetos <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e <xref:Microsoft.SqlServer.Management.Smo.Settings> têm um método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="952ef-138">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="952ef-139">Você pode executar os métodos <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> para eles individualmente.</span><span class="sxs-lookup"><span data-stu-id="952ef-139">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Display information about the instance of SQL Server in Information and Settings.  
"OS Version = " + $srv.Information.OSVersion  
"State = "+ $srv.Settings.State.ToString()  
  
#Display information specific to the current user in UserOptions.  
"Quoted Identifier support = " + $srv.UserOptions.QuotedIdentifier  
  
#Modify server settings in Settings.  
$srv.Settings.LoginMode = [Microsoft.SqlServer.Management.SMO.ServerLoginMode]::Integrated  
  
#Modify settings specific to the current connection in UserOptions.  
$srv.UserOptions.AbortOnArithmeticErrors = $true  
  
#Run the Alter method to make the changes on the instance of SQL Server.  
$srv.Alter()  
```  
  
## <a name="modifying-sql-server-configuration-options-in-powershell"></a><span data-ttu-id="952ef-140">Modificando as opções de configuração do SQL Server no PowerShell</span><span class="sxs-lookup"><span data-stu-id="952ef-140">Modifying SQL Server Configuration Options in PowerShell</span></span>  
 <span data-ttu-id="952ef-141">O exemplo de código mostra como atualizar uma opção de configuração no Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="952ef-141">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="952ef-142">Ele também recupera e exibe informações sobre os valores máximo e mínimo da opção de configuração especificada.</span><span class="sxs-lookup"><span data-stu-id="952ef-142">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="952ef-143">Finalmente, o programa informa ao usuário se a alteração foi feita dinamicamente ou se ela foi armazenada até o reinício da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="952ef-143">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalMachine  
$svr = Get-Item default  
  
#enumerate its properties  
foreach ($Item in $Svr.Configuration.Properties)   
{  
 $Item.DisplayName  
}  
  
"There are " + $svr.Configuration.Properties.Count.ToString() + " configuration options."  
  
#Display the maximum and minimum values for ShowAdvancedOptions.  
$min = $svr.Configuration.ShowAdvancedOptions.Minimum  
$max = $svr.Configuration.ShowAdvancedOptions.Maximum  
"Minimum and Maximum values are " + $min.ToString() + " and " + $max.ToString() + "."  
  
#Modify the value of ShowAdvancedOptions and run the Alter method.  
$svr.Configuration.ShowAdvancedOptions.ConfigValue = 0  
$svr.Configuration.Alter()  
  
#Display when the change takes place according to the IsDynamic property.  
If ($svr.Configuration.ShowAdvancedOptions.IsDynamic -eq $true)  
 {
   "Configuration option has been updated."  
 }  
Else  
 {  
    "Configuration option will be updated when SQL Server is restarted."  
 }  
```  
