---
title: Exemplo de Olá, Mundo pronto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 1cb94266-f702-4a57-a1ae-689a89c98757
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7cc3088af258962a4cec615214147d1f4f09c431
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685901"
---
# <a name="hello-world-ready-sample"></a><span data-ttu-id="8b47e-102">Exemplo pronto do Hello World</span><span class="sxs-lookup"><span data-stu-id="8b47e-102">Hello World Ready Sample</span></span>
  <span data-ttu-id="8b47e-103">O exemplo Hello World Ready demonstra as operações básicas envolvidas na criação, implantação e teste de um procedimento armazenado simples e pronto para uso, baseado na integração CLR (common language runtime).</span><span class="sxs-lookup"><span data-stu-id="8b47e-103">The Hello World Ready sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple world ready common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="8b47e-104">Um componente pronto para uso pode ser facilmente localizado em diferentes idiomas para diferentes mercados do mundo, sem alterar o código-fonte do componente.</span><span class="sxs-lookup"><span data-stu-id="8b47e-104">A world-ready component can be easily localized into different languages for different markets around the world without changing the component's source code.</span></span> <span data-ttu-id="8b47e-105">Este exemplo também demonstra como retornar dados por meio de um parâmetro de saída e de um registro, que é construído dinamicamente pelo procedimento armazenado e retornado ao cliente. Esse exemplo é quase idêntico ao Exemplo Hello World, com a exceção de que é muito mais fácil e mais seguro localizar este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8b47e-105">This sample also demonstrates how to return data through an output parameter and through a record, which is dynamically constructed by the stored procedure and returned to the client.This sample is almost identical to the Hello World Sample except that it is much easier and safer to localize this application.</span></span> <span data-ttu-id="8b47e-106">Para alterar textos localizados é necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b47e-106">To change localized text requires the following:</span></span>  
  
1.  <span data-ttu-id="8b47e-107">Alterar um arquivo XML (o.`resx`</span><span class="sxs-lookup"><span data-stu-id="8b47e-107">Changing an XML file (the .`resx`</span></span> <span data-ttu-id="8b47e-108">arquivo) para a cultura específica no diretório de recursos</span><span class="sxs-lookup"><span data-stu-id="8b47e-108">file) for the particular culture in the resources directory</span></span>  
  
2.  <span data-ttu-id="8b47e-109">Criar o arquivo de recursos da cultura por meio de `resgen`</span><span class="sxs-lookup"><span data-stu-id="8b47e-109">Building the culture's resources file by using `resgen`</span></span>  
  
3.  <span data-ttu-id="8b47e-110">Criar o DLL satélite atualizado para aquela cultura</span><span class="sxs-lookup"><span data-stu-id="8b47e-110">Building the updated satellite DLL for that culture</span></span>  
  
4.  <span data-ttu-id="8b47e-111">Descartar e adicionar esse assembly ao SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b47e-111">Dropping and adding that assembly in SQL Server</span></span>  
  
 <span data-ttu-id="8b47e-112">O código-fonte e o assembly do próprio procedimento armazenado CLR não são alterados.</span><span class="sxs-lookup"><span data-stu-id="8b47e-112">The source code and assembly for the CLR stored procedure itself does not change.</span></span> <span data-ttu-id="8b47e-113">É fornecido um script `build.cmd` que demonstra como compilar e vincular os assemblies do recurso. Embora o código-fonte do aplicativo crie um gerenciador de recursos baseado no assembly que está sendo executado no momento, você não precisa inserir os recursos com neutralidade de cultura na DLL que contém o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8b47e-113">A `build.cmd` script is provided which demonstrates how to compile and link the resource assemblies.Although the source code for the application creates a resource manager based the currently executing assembly, you do not have to embed the culture neutral resources in the DLL that contains the stored procedure.</span></span> <span data-ttu-id="8b47e-114">O `System.Resources.NeutralResourcesLanguage attribute` permite que recursos com neutralidade de cultura existam em uma DLL satélite.</span><span class="sxs-lookup"><span data-stu-id="8b47e-114">The `System.Resources.NeutralResourcesLanguage attribute` permits the culture-neutral resources to exist in a satellite DLL.</span></span> <span data-ttu-id="8b47e-115">É muito melhor usar uma DLL separada para essa finalidade, de forma que, quando for necessário adicionar ou alterar textos localizados, a DLL primária que contém o procedimento armazenado CLR não precise ser alterado.</span><span class="sxs-lookup"><span data-stu-id="8b47e-115">It is much better to use a separate DLL for this purpose so that when localized text needs to be added or changed, the primary DLL that contains the CLR stored procedure does not have to be changed.</span></span> <span data-ttu-id="8b47e-116">Isso é especialmente útil para tipos de dados CLR definidos pelo usuário que podem ter colunas e outras dependências que dificultam a remoção e a nova adição do tipo. Normalmente, as versões de DLL satélite devem ser idênticas à versão do assembly principal.</span><span class="sxs-lookup"><span data-stu-id="8b47e-116">This is especially useful for CLR user-defined types that might have columns and other dependencies which would make it difficult to drop and re-add the type.Ordinarily, the satellite DLL versions must be identical to the main assembly version.</span></span> <span data-ttu-id="8b47e-117">No entanto, é possível usar o atributo `SatelliteContractVersion` para permitir que o assembly principal seja atualizado sem atualizar os assemblies satélites também.</span><span class="sxs-lookup"><span data-stu-id="8b47e-117">However, you can use the `SatelliteContractVersion` attribute to allow the main assembly to be updated without updating the satellite assemblies too.</span></span> <span data-ttu-id="8b47e-118">Para obter mais informações, consulte a documentação da classe `ResourceManager` no Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="8b47e-118">For more information, see the `ResourceManager` class in the Microsoft .NET documentation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8b47e-119">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8b47e-119">Prerequisites</span></span>  
 <span data-ttu-id="8b47e-120">Esse exemplo funciona apenas com o SQL Server 2005 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="8b47e-120">This sample works only with SQL Server 2005 and later versions.</span></span>  
  
 <span data-ttu-id="8b47e-121">Para criar e executar este projeto, o software a seguir deve estar instalado:</span><span class="sxs-lookup"><span data-stu-id="8b47e-121">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8b47e-122">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="8b47e-122">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="8b47e-123">É possível obter o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express gratuitamente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [de Documentação e Amostras do](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="8b47e-123">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="8b47e-124">O banco de dados AdventureWorks que está disponível no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [do](https://go.microsoft.com/fwlink/?linkid=62796)Developer</span><span class="sxs-lookup"><span data-stu-id="8b47e-124">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="8b47e-125">.NET Framework SDK 2.0 ou posterior ou Microsoft Visual Studio 2005 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8b47e-125">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="8b47e-126">Você pode obter o .NET Framework SDK gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="8b47e-126">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="8b47e-127">Além disso, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="8b47e-127">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="8b47e-128">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando deve ter a integração CLR habilitada.</span><span class="sxs-lookup"><span data-stu-id="8b47e-128">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="8b47e-129">Para habilitar a integração CLR, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="8b47e-129">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="8b47e-130">Habilitando integração CLR</span><span class="sxs-lookup"><span data-stu-id="8b47e-130">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="8b47e-131">Execute os seguintes comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="8b47e-131">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="8b47e-132">Para habilitar o CLR, é necessário ter a permissão `ALTER SETTINGS` de nível de servidor, que é mantida implicitamente por membros das funções de servidor fixas `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="8b47e-132">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="8b47e-133">O banco de dados AdventureWorks deve estar instalado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando.</span><span class="sxs-lookup"><span data-stu-id="8b47e-133">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="8b47e-134">Se você não for um administrador da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância que está usando, deverá ter um administrador para conceder a permissão **CreateAssembly** para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="8b47e-134">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="8b47e-135">Compilando o exemplo</span><span class="sxs-lookup"><span data-stu-id="8b47e-135">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="8b47e-136">Crie e execute o exemplo seguindo estas instruções:</span><span class="sxs-lookup"><span data-stu-id="8b47e-136">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="8b47e-137">Abra um prompt de comando do Visual Studio ou do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b47e-137">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="8b47e-138">Se necessário, crie um diretório para o seu exemplo.</span><span class="sxs-lookup"><span data-stu-id="8b47e-138">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="8b47e-139">Para este exemplo, usaremos C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="8b47e-139">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="8b47e-140">Em c:\MySample, crie `HelloWorld.vb` (para o exemplo do Visual Basic) ou `HelloWorld.cs` (para o exemplo do C#) e copie o código de exemplo adequado do Visual Basic ou do C# (a seguir) no arquivo.</span><span class="sxs-lookup"><span data-stu-id="8b47e-140">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="8b47e-141">Em c:\MySample, crie o arquivo `messages.resx` e copie o código de exemplo no arquivo.</span><span class="sxs-lookup"><span data-stu-id="8b47e-141">In c:\MySample, create the file `messages.resx` and copy the sample code into the file.</span></span>  
  
5.  <span data-ttu-id="8b47e-142">No c:\MySample, crie o arquivo `messages.de.resx` salvando o arquivo `messages.resx` como `messages.de.resx` depois de alterar a linha</span><span class="sxs-lookup"><span data-stu-id="8b47e-142">In c:\MySample, create the file `messages.de.resx` by saving the file `messages.resx` as `messages.de.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="8b47e-143">Para ler </span><span class="sxs-lookup"><span data-stu-id="8b47e-143">To read</span></span>  
  
    -   `<value xml:space="preserve">Hallo Welt!</value>`  
  
6.  <span data-ttu-id="8b47e-144">No c:\MySample, crie o arquivo `messages.es.resx` salvando o arquivo `messages.resx` como `messages.es.resx` depois de alterar a linha</span><span class="sxs-lookup"><span data-stu-id="8b47e-144">In c:\MySample, create the file `messages.es.resx` by saving the file `messages.resx` as `messages.es.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="8b47e-145">Para ler </span><span class="sxs-lookup"><span data-stu-id="8b47e-145">To read</span></span>  
  
    -   `<value xml:space="preserve">Hola a todos</value>`  
  
7.  <span data-ttu-id="8b47e-146">No c:\MySample, crie o arquivo `messages.fr.resx` salvando o arquivo `messages.resx` como `messages.fr.resx` depois de alterar a linha</span><span class="sxs-lookup"><span data-stu-id="8b47e-146">In c:\MySample, create the file `messages.fr.resx` by saving the file `messages.resx` as `messages.fr.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="8b47e-147">Para ler </span><span class="sxs-lookup"><span data-stu-id="8b47e-147">To read</span></span>  
  
    -   `<value xml:space="preserve">BonjourÂ !</value>`  
  
8.  <span data-ttu-id="8b47e-148">No c:\MySample, crie o arquivo `messages.fr-FR.resx` salvando o arquivo `messages.resx` como `messages.fr-FR.resx` depois de alterar a linha</span><span class="sxs-lookup"><span data-stu-id="8b47e-148">In c:\MySample, create the file `messages.fr-FR.resx` by saving the file `messages.resx` as `messages.fr-FR.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="8b47e-149">Para ler </span><span class="sxs-lookup"><span data-stu-id="8b47e-149">To read</span></span>  
  
    -   `<value xml:space="preserve">Bonjour de France!</value>`  
  
9. <span data-ttu-id="8b47e-150">No c:\MySample, crie o arquivo `messages.it.resx` salvando o arquivo `messages.resx` como `messages.it.resx` depois de alterar a linha</span><span class="sxs-lookup"><span data-stu-id="8b47e-150">In c:\MySample, create the file `messages.it.resx` by saving the file `messages.resx` as `messages.it.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="8b47e-151">Para ler </span><span class="sxs-lookup"><span data-stu-id="8b47e-151">To read</span></span>  
  
    -   `<value xml:space="preserve">Buongiorno</value>`  
  
10. <span data-ttu-id="8b47e-152">No c:\MySample, crie o arquivo `messages.ja.resx` salvando o arquivo `messages.resx` como `messages.ja.resx` depois de alterar a linha</span><span class="sxs-lookup"><span data-stu-id="8b47e-152">In c:\MySample, create the file `messages.ja.resx` by saving the file `messages.resx` as `messages.ja.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="8b47e-153">Para ler </span><span class="sxs-lookup"><span data-stu-id="8b47e-153">To read</span></span>  
  
    -   <span data-ttu-id="8b47e-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span><span class="sxs-lookup"><span data-stu-id="8b47e-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span></span>  
  
11. <span data-ttu-id="8b47e-155">Em c:\MySample, crie o arquivo `build.com` e copie o código de exemplo no arquivo</span><span class="sxs-lookup"><span data-stu-id="8b47e-155">In c:\MySample, create the file `build.com` and copy the sample code into the file</span></span>  
  
12. <span data-ttu-id="8b47e-156">Compile os assemblies satélites executando a compilação de arquivo no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8b47e-156">Build the satellite assembles by executing the file build at the command prompt.</span></span>  
  
13. <span data-ttu-id="8b47e-157">Compile o código de exemplo no prompt da linha de comando por meio da execução de uma das seguintes opções.</span><span class="sxs-lookup"><span data-stu-id="8b47e-157">Compile the sample code from the command line prompt by executing the one of the following:</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /out:HelloWorldReady.dll /target:library HelloWorld.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.XML.dll /out:HelloWorldReady.dll /target:library Hello.csCopy the tsql installation code into a file and save it as Install.sql in the sample directory.`  
  
14. <span data-ttu-id="8b47e-158">Se o exemplo tiver sido instalado em um diretório diferente de `C:\MySample\`, edite o arquivo `Install.sql` conforme indicado para apontar para esse local.</span><span class="sxs-lookup"><span data-stu-id="8b47e-158">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
15. <span data-ttu-id="8b47e-159">Implante o assembly e o procedimento armazenado executando o seguinte</span><span class="sxs-lookup"><span data-stu-id="8b47e-159">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
16. <span data-ttu-id="8b47e-160">Copie o script de comando de teste do [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `test.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8b47e-160">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
17. <span data-ttu-id="8b47e-161">Execute o script de teste com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="8b47e-161">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
18. <span data-ttu-id="8b47e-162">Copie o script de limpeza [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `cleanup.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8b47e-162">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
19. <span data-ttu-id="8b47e-163">Execute o script com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="8b47e-163">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="8b47e-164">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="8b47e-164">Sample Code</span></span>  
 <span data-ttu-id="8b47e-165">As listagens de código deste exemplo são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="8b47e-165">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="8b47e-166">C#</span><span class="sxs-lookup"><span data-stu-id="8b47e-166">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Globalization;  
using System.Threading;  
using System.Resources;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
  
[assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)]  
[assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)]  
[assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance, System.Runtime.ConstrainedExecution.Cer.None)]  
  
    public sealed partial class StoredProcedures  
    {  
        private StoredProcedures()  
        {  
        }  
  
        [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1021:AvoidOutParameters"), Microsoft.SqlServer.Server.SqlProcedure]  
        public static void HelloWorldReady(string culture, out string greeting)  
        {  
ResourceManager rm   
= new ResourceManager("Messages",   
Assembly.GetExecutingAssembly());  
  
string message = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture));  
  
            Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 24);  
            SqlDataRecord greetingRecord  
                = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
            greetingRecord.SetString(0, message);  
            SqlContext.Pipe.Send(greetingRecord);  
            greeting = message;  
        }  
    }  
  
```  
  
 <span data-ttu-id="8b47e-167">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8b47e-167">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Globalization  
Imports System.Resources  
Imports System.Reflection  
Imports System.Runtime.InteropServices  
<Assembly: AssemblyVersion("1.0.*")>   
<Assembly: System.Runtime.InteropServices.ComVisible(False)>   
<Assembly: System.CLSCompliant(True)>   
<Assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)>   
<Assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)>   
<Assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState, Runtime.ConstrainedExecution.Cer.None)>   
  
Partial Public NotInheritable Class StoredProcedures  
    Private Sub New()  
    End Sub  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorldReady(ByVal culture As String, ByRef greeting As String)  
        Dim rm As New ResourceManager("Messages", Assembly.GetExecutingAssembly())  
        Dim message As String = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture))  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 24)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, message)  
        SqlContext.Pipe.Send(greetingRecord)  
        greeting = message  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="8b47e-168">Este é o `build.com` que compila os assemblies satélites.</span><span class="sxs-lookup"><span data-stu-id="8b47e-168">This is `build.com`, which builds the satellite assemblies.</span></span>  
  
```  
resgen Messages.resx  
resgen Messages.de.resx  
resgen Messages.es.resx  
resgen Messages.fr.resx  
resgen Messages.fr-Fr.resx  
resgen Messages.it.resx  
resgen Messages.ja.resx  
if not exist de/ mkdir de  
if not exist es/ mkdir es  
if not exist fr/ mkdir fr  
if not exist fr-FR/ mkdir fr-FR  
if not exist it/ mkdir it  
if not exist ja/ mkdir ja  
al /t:lib /culture:de /embed:Messages.de.resources /out:de\HelloWorldReady.resources.dll  
al /t:lib /culture:es /embed:Messages.es.resources /out:es\HelloWorldReady.resources.dll  
al /t:lib /culture:fr /embed:Messages.fr.resources /out:fr\HelloWorldReady.resources.dll  
al /t:lib /culture:fr-FR /embed:Messages.fr-FR.resources /out:fr-FR\HelloWorldReady.resources.dll  
al /t:lib /culture:it /embed:Messages.it.resources /out:it\HelloWorldReady.resources.dll  
al /t:lib /culture:ja /embed:Messages.ja.resources /out:ja\HelloWorldReady.resources.dll  
al /t:lib /culture:"" /embed:Messages.resources /out:HelloWorldReady.resources.dll  
```  
  
 <span data-ttu-id="8b47e-169">Este é o script de instalação do [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) que implanta os assemblies e cria o procedimento armazenado dentro do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8b47e-169">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assemblies and creates the stored procedure within the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of this variable if you have installed the sample someplace other than the default location.  
Set @SamplesPath = N'C:\MySample\'  
  
-- Add the assembly and CLR integration based stored procedure  
  
CREATE ASSEMBLY HelloWorldReady  
FROM @SamplesPath + 'HelloWorldReady.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.neutral]  
FROM @SamplesPath + 'HelloWorldReady.resources.dll'  
WITH permission_set = Safe;   
  
CREATE ASSEMBLY [HelloWorldReady.resources.de]  
FROM @SamplesPath + '\de\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.es]  
FROM @SamplesPath + '\es\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr]  
FROM @SamplesPath + '\fr\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr-FR]  
FROM @SamplesPath + '\fr-FR\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.it]  
FROM @SamplesPath + '\it\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.ja]  
FROM @SamplesPath + '\ja\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorldReady  
(  
@Culture NVarchar(12),  
@Greeting NVarchar(24) OUTPUT  
)  
AS EXTERNAL NAME HelloWorldReady.StoredProcedures.HelloWorldReady;  
GO  
  
USE master;  
GO  
```  
  
 <span data-ttu-id="8b47e-170">Este é `test.sql` que testa o exemplo por meio da execução das funções em cada localidade.</span><span class="sxs-lookup"><span data-stu-id="8b47e-170">This is `test.sql`, which tests the sample by executing the functions on each locale.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
DECLARE @GreetingDe nvarchar(24);  
DECLARE @GreetingDe_CH nvarchar(24);  
DECLARE @GreetingEn nvarchar(24);  
DECLARE @GreetingEs nvarchar(24);  
DECLARE @GreetingFr nvarchar(24);  
DECLARE @GreetingFr_FR nvarchar(24);  
DECLARE @GreetingIt nvarchar(24);  
DECLARE @GreetingJa nvarchar(24);  
  
--German as spoken anywhere in the world (the neutral German culture)  
EXEC usp_HelloWorldReady 'de', @GreetingDe OUTPUT;  
--German as spoken in Switzerland.  Because we don't have a specific assembly  
--for this case, the .NET Framework will automatically fall back to the neutral German culture DLL.  
EXEC usp_HelloWorldReady 'de-CH', @GreetingDe_CH OUTPUT;  
EXEC usp_HelloWorldReady 'en', @GreetingEn OUTPUT;  
EXEC usp_HelloWorldReady 'es', @GreetingEs OUTPUT;  
--French as spoken anywhere in the world (the neutral French culture)  
EXEC usp_HelloWorldReady 'fr', @GreetingFr OUTPUT  
--French as spoken in France.  Since we do have a specific assembly for this case, a specific   
--greeting is provided from that DLL.  The neutral French culture DLL is not used in this case.  
EXEC usp_HelloWorldReady 'fr-FR', @GreetingFr_FR OUTPUT  
EXEC usp_HelloWorldReady 'it', @GreetingIt OUTPUT;  
EXEC usp_HelloWorldReady 'ja', @GreetingJa OUTPUT;  
  
SELECT @GreetingDe AS OUTPUT_PARAMETER_DE;  
SELECT @GreetingDe_CH AS OUTPUT_PARAMETER_De_CH;  
SELECT @GreetingEn AS OUTPUT_PARAMETER_EN;  
SELECT @GreetingEs AS OUTPUT_PARAMETER_ES;  
SELECT @GreetingFr AS OUTPUT_PARAMETER_FR;  
SELECT @GreetingFr_FR AS OUTPUT_PARAMETER_Fr_FR;  
SELECT @GreetingIt AS OUTPUT_PARAMETER_IT;  
SELECT @GreetingJa AS OUTPUT_PARAMETER_JA;  
  
GO  
```  
  
 <span data-ttu-id="8b47e-171">O exemplo a seguir remove os assemblies e o procedimento armazenado do [!INCLUDE[tsql](../../includes/tsql-md.md)] do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8b47e-171">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assemblies and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
USE master;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b47e-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b47e-172">See Also</span></span>  
 [<span data-ttu-id="8b47e-173">Cenários de uso e exemplos para a integração do CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="8b47e-173">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
