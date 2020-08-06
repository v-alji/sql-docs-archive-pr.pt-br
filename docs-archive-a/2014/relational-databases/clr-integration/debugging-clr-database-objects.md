---
title: Depurando objetos de banco de dados CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- database objects [CLR integration], debugging
- permissions [CLR integration]
- debugging [CLR integration]
- building database objects [CLR integration], debugging
- common language runtime [SQL Server], debugging
ms.assetid: 1332035c-d6ed-424d-8234-46ad21168319
author: rothja
ms.author: jroth
ms.openlocfilehash: 084b2494ec55b502f71154ca1f174a6de6d2ab70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568631"
---
# <a name="debugging-clr-database-objects"></a><span data-ttu-id="00720-102">Depurando objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="00720-102">Debugging CLR Database Objects</span></span>
  <span data-ttu-id="00720-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece suporte para depurar o [!INCLUDE[tsql](../../../includes/tsql-md.md)] e objetos CLR (Common Language Runtime) no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="00720-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides support for debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="00720-104">Os principais aspectos da depuração no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] são a facilidade de configuração e uso, e a integração do depurador do SQL Server com o depurador do Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00720-104">The key aspects of debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are the ease of setup and use, and the integration of the SQL Server debugger with the Microsoft Visual Studio debugger.</span></span> <span data-ttu-id="00720-105">Além disso, a depuração funciona entre idiomas.</span><span class="sxs-lookup"><span data-stu-id="00720-105">Furthermore, debugging works across languages.</span></span> <span data-ttu-id="00720-106">Os usuários podem entrar diretamente em objetos CLR do [!INCLUDE[tsql](../../../includes/tsql-md.md)] e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="00720-106">Users can step seamlessly into CLR objects from [!INCLUDE[tsql](../../../includes/tsql-md.md)], and vice versa.</span></span> <span data-ttu-id="00720-107">O depurador Transact-SQL no SQL Server Management Studio não pode ser usado para depurar objetos de banco de dados gerenciados, mas você pode depurar os objetos por meio dos depuradores do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00720-107">The Transact-SQL debugger in SQL Server Management Studio cannot be used to debug managed database objects, but you can debug the objects by using the debuggers in Visual Studio.</span></span> <span data-ttu-id="00720-108">A depuração de objetos de banco de dados gerenciados no Visual Studio oferece suporte a todos os recursos de depuração comuns, tais como as instruções de "depuração parcial" e "depuração completa" dentro de rotinas executadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="00720-108">Managed database object debugging in Visual Studio supports all common debugging features, such as "step into" and "step over" statements within routines executing on the server.</span></span> <span data-ttu-id="00720-109">Os depuradores podem definir pontos de interrupção, inspecionar a pilha de chamadas, inspecionar variáveis e modificar valores de variáveis durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="00720-109">Debuggers can set breakpoints, inspect the call stack, inspect variables, and modify variable values while debugging.</span></span> <span data-ttu-id="00720-110">Observe que o Visual Studio .NET 2003 não pode ser usado na programação de integração ou na depuração do CLR.</span><span class="sxs-lookup"><span data-stu-id="00720-110">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or debugging.</span></span> <span data-ttu-id="00720-111">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fornece o .NET Framework pré-instalado, e o Visual Studio .NET 2003 não pode usar os assemblies do .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="00720-111">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="00720-112">Para obter mais informações sobre como depurar código gerenciado usando o Visual Studio, consulte o tópico "[depuração de código gerenciado](https://go.microsoft.com/fwlink/?LinkId=120377)" na documentação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00720-112">For more information about debugging managed code using Visual Studio, see the "[Debugging Managed Code](https://go.microsoft.com/fwlink/?LinkId=120377)" topic in the Visual Studio documentation.</span></span>  
  
## <a name="debugging-permissions-and-restrictions"></a><span data-ttu-id="00720-113">Depurando permissões e restrições</span><span class="sxs-lookup"><span data-stu-id="00720-113">Debugging Permissions and Restrictions</span></span>  
 <span data-ttu-id="00720-114">A depuração é uma operação altamente privilegiada e, portanto, somente os membros da função de servidor fixa **sysadmin** podem fazer isso no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00720-114">Debugging is a highly privileged operation, and therefore only members of the **sysadmin** fixed server role are allowed to do so in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="00720-115">As seguintes restrições se aplicam durante a depuração:</span><span class="sxs-lookup"><span data-stu-id="00720-115">The following restrictions apply while debugging:</span></span>  
  
-   <span data-ttu-id="00720-116">A depuração de rotinas de CLR é restrita a uma instância de depurador de cada vez.</span><span class="sxs-lookup"><span data-stu-id="00720-116">Debugging CLR routines is restricted to one debugger instance at a time.</span></span> <span data-ttu-id="00720-117">Essa limitação se aplica pois a execução do código de CLR inteira fica congelada quando um ponto de interrupção é atingido; a execução só prossegue quando o depurador sai do ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="00720-117">This limitation applies because all CLR code execution freezes when a break point is hit and execution does not continue until the debugger advances from the break point.</span></span> <span data-ttu-id="00720-118">Porém, você pode continuar depurando o [!INCLUDE[tsql](../../../includes/tsql-md.md)] em outras conexões.</span><span class="sxs-lookup"><span data-stu-id="00720-118">However, you can continue debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] in other connections.</span></span> <span data-ttu-id="00720-119">Embora a depuração do [!INCLUDE[tsql](../../../includes/tsql-md.md)] não congele outras execuções no servidor, ela pode colocar outras conexões em espera quando mantém um bloqueio.</span><span class="sxs-lookup"><span data-stu-id="00720-119">Although [!INCLUDE[tsql](../../../includes/tsql-md.md)] debugging does not freeze other executions on the server, it could cause other connections to wait by holding a lock.</span></span>  
  
-   <span data-ttu-id="00720-120">As conexões existentes não podem ser depuradas, apenas as conexões novas, pois o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] exige informações sobre o cliente e o ambiente do depurador para poder fazer a conexão.</span><span class="sxs-lookup"><span data-stu-id="00720-120">Existing connections cannot be debugged, only new connections, as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires information about the client and debugger environment before the connection can be made.</span></span>  
  
 <span data-ttu-id="00720-121">Devido às restrições anteriores, recomendamos que o [!INCLUDE[tsql](../../../includes/tsql-md.md)] e o código CLR sejam depurados em um servidor de teste, e não em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="00720-121">Due to the above restrictions, we recommend that [!INCLUDE[tsql](../../../includes/tsql-md.md)] and CLR code be debugged on a test server, and not on a production server.</span></span>  
  
## <a name="overview-of-debugging-managed-database-objects"></a><span data-ttu-id="00720-122">Visão geral da depuração de objetos de banco de dados gerenciados</span><span class="sxs-lookup"><span data-stu-id="00720-122">Overview of Debugging Managed Database Objects</span></span>  
 <span data-ttu-id="00720-123">A depuração no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] segue um modelo por conexão.</span><span class="sxs-lookup"><span data-stu-id="00720-123">Debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] follows a per-connection model.</span></span> <span data-ttu-id="00720-124">Um depurador só pode detectar e depurar atividades para a conexão do cliente à qual ele está anexado.</span><span class="sxs-lookup"><span data-stu-id="00720-124">A debugger can detect and debug activities only to the client connection to which it is attached.</span></span> <span data-ttu-id="00720-125">Como a funcionalidade do depurador não é limitada pelo tipo de conexão, pode-se depurar conexões do protocolo TDS e HTTP.</span><span class="sxs-lookup"><span data-stu-id="00720-125">Because the functionality of the debugger is not limited by the type of connection, both tabular data stream (TDS) and HTTP connections can be debugged.</span></span> <span data-ttu-id="00720-126">Porém, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não permite a depuração de conexões existentes.</span><span class="sxs-lookup"><span data-stu-id="00720-126">However, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow debugging existing connections.</span></span> <span data-ttu-id="00720-127">A depuração oferece suporte a todos os recursos de depuração comuns dentro de rotinas executadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="00720-127">Debugging supports all common debugging features within routines executing on the server.</span></span> <span data-ttu-id="00720-128">A interação entre um depurador e o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ocorre através do COM (Component Object Model) distribuído.</span><span class="sxs-lookup"><span data-stu-id="00720-128">The interaction between a debugger and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] happens through distributed Component Object Model (COM).</span></span>  
  
 <span data-ttu-id="00720-129">Para obter mais informações e cenários sobre como depurar procedimentos armazenados gerenciados, funções, gatilhos, tipos definidos pelo usuário e agregações, consulte o tópico "[SQL Server a depuração do banco de dados de integração CLR](https://go.microsoft.com/fwlink/?LinkId=120378)" na documentação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00720-129">For more information and scenarios about debugging managed stored procedures, functions, triggers, user-defined types, and aggregates, see the "[SQL Server CLR Integration Database Debugging](https://go.microsoft.com/fwlink/?LinkId=120378)" topic in the Visual Studio documentation.</span></span>  
  
 <span data-ttu-id="00720-130">O protocolo de rede TCP/IP deve estar habilitado na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para permitir o uso do Visual Studio no desenvolvimento remoto, na depuração e no desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="00720-130">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="00720-131">Para obter mais informações sobre como habilitar o protocolo TCP/IP no servidor, consulte [Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="00720-131">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-debug-a-managed-database-object"></a><span data-ttu-id="00720-132">Para depurar um objeto de banco de dados gerenciado</span><span class="sxs-lookup"><span data-stu-id="00720-132">To debug a managed database object</span></span>  
  
1.  <span data-ttu-id="00720-133">Abra o Microsoft Visual Studio, crie um novo projeto do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e estabeleça uma conexão com um banco de dados em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00720-133">Open Microsoft Visual Studio, create a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project, and establish a connection to a database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="00720-134">Crie um tipo novo.</span><span class="sxs-lookup"><span data-stu-id="00720-134">Create a new type.</span></span> <span data-ttu-id="00720-135">Em **Gerenciador de soluções**, clique com o botão direito do mouse no projeto, selecione **Adicionar** e **novo item...** Na janela **Adicionar novo item** , selecione **procedimento armazenado**, **função definida pelo usuário**, **tipo definido pelo usuário**, **gatilho**, **agregação**ou **classe**.</span><span class="sxs-lookup"><span data-stu-id="00720-135">In **Solution Explorer**, right-click the project, select **Add** and **New Item...** From the **Add New Item** window, select **Stored Procedure**, **User-Defined Function**, **User-Defined Type**, **Trigger**, **Aggregate**, or **Class**.</span></span> <span data-ttu-id="00720-136">Especifique um nome para o arquivo de origem do novo tipo e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="00720-136">Specify a name for the source file of the new type and click **Add**.</span></span>  
  
3.  <span data-ttu-id="00720-137">Adicione código para o tipo novo no editor de texto.</span><span class="sxs-lookup"><span data-stu-id="00720-137">Add code for the new type to the text editor.</span></span> <span data-ttu-id="00720-138">Para obter um código de exemplo de um procedimento armazenado de exemplo, consulte a seção correspondente mais adiante nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="00720-138">For sample code for an example stored procedure, see the section later in this topic.</span></span>  
  
4.  <span data-ttu-id="00720-139">Adicione um script que testa o tipo.</span><span class="sxs-lookup"><span data-stu-id="00720-139">Add a script that tests the type.</span></span> <span data-ttu-id="00720-140">Em **Gerenciador de soluções**, expanda o diretório **TestScripts** clique duas vezes em **Test. SQL** para abrir o arquivo de origem do script de teste padrão.</span><span class="sxs-lookup"><span data-stu-id="00720-140">In **Solution Explorer**, expand the **TestScripts** directory double-click **Test.sql** to open the default test script source file.</span></span> <span data-ttu-id="00720-141">Adicione o script de teste, aquele que invoca o código a ser depurado, no editor de texto.</span><span class="sxs-lookup"><span data-stu-id="00720-141">Add the test script, one that invokes the code to be debugged, to the text editor.</span></span> <span data-ttu-id="00720-142">Veja um script de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="00720-142">See below for a sample script.</span></span>  
  
5.  <span data-ttu-id="00720-143">Coloque um ou mais pontos de interrupção no código fonte.</span><span class="sxs-lookup"><span data-stu-id="00720-143">Place one or more breakpoints in the source code.</span></span> <span data-ttu-id="00720-144">Clique com o botão direito do mouse em uma linha de código no editor de texto, dentro da função ou da rotina que você deseja depurar e selecione **ponto** de interrupção e **Inserir ponto de interrupção**.</span><span class="sxs-lookup"><span data-stu-id="00720-144">Right-click on a line of code in the text editor, within the function or routine you want to debug, and select **Breakpoint** and **Insert Breakpoint**.</span></span> <span data-ttu-id="00720-145">O ponto de interrupção é adicionado, destacando a linha de código em vermelho.</span><span class="sxs-lookup"><span data-stu-id="00720-145">The breakpoint is added, highlighting the line of code in red.</span></span>  
  
6.  <span data-ttu-id="00720-146">No menu **depurar** , selecione **Iniciar Depuração** para compilar, implantar e testar o projeto.</span><span class="sxs-lookup"><span data-stu-id="00720-146">In the **Debug** menu, select **Start Debugging** to compile, deploy, and test the project.</span></span> <span data-ttu-id="00720-147">O script de teste em Test.sql será executado e o objeto de banco de dados gerenciado será invocado.</span><span class="sxs-lookup"><span data-stu-id="00720-147">The test script in Test.sql will be run and the managed database object will be invoked.</span></span>  
  
7.  <span data-ttu-id="00720-148">Quando a seta amarela que designa o ponteiro de instrução aparece no ponto de interrupção, há uma pausa na execução do código e você pode começar a depurar seu objeto de banco de dados gerenciado.</span><span class="sxs-lookup"><span data-stu-id="00720-148">When the yellow arrow designating the instruction pointer appears at the breakpoint code execution pauses and you can begin debugging your managed database object.</span></span> <span data-ttu-id="00720-149">Você pode **percorrer** o menu **depurar** para avançar o ponteiro de instrução para a próxima linha de código.</span><span class="sxs-lookup"><span data-stu-id="00720-149">You can **Step Over** from the **Debug** menu to advance the instruction pointer to the next line of code.</span></span> <span data-ttu-id="00720-150">A janela **locais** é usada para observar o estado dos objetos realçados no momento pelo ponteiro de instrução.</span><span class="sxs-lookup"><span data-stu-id="00720-150">The **Locals** window is used to observe the state of the objects currently highlighted by the instruction pointer.</span></span> <span data-ttu-id="00720-151">As variáveis podem ser adicionadas à janela **Watch** .</span><span class="sxs-lookup"><span data-stu-id="00720-151">Variables can be added to the **Watch** window.</span></span> <span data-ttu-id="00720-152">O estado de variáveis inspecionadas pode ser observado na sessão de depuração inteira, e não apenas quando a variável está na linha de código destacada no momento pelo ponteiro de instrução.</span><span class="sxs-lookup"><span data-stu-id="00720-152">The state of watched variables can be observed throughout the entire debugging session, not only when the variable is in the line of code currently highlighted by instruction pointer.</span></span> <span data-ttu-id="00720-153">Selecione Continuar no menu Depurar para avançar o ponteiro de instrução até o próximo ponto de interrupção ou para concluir a execução da rotina se não houver mais pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="00720-153">Select Continue from the Debug menu to advance the instruction pointer to the next breakpoint or to complete execution of the routine if there are no more breakpoints.</span></span>  
  
### <a name="example"></a><span data-ttu-id="00720-154">Exemplo</span><span class="sxs-lookup"><span data-stu-id="00720-154">Example</span></span>  
 <span data-ttu-id="00720-155">O exemplo a seguir retorna a versão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para o chamador.</span><span class="sxs-lookup"><span data-stu-id="00720-155">The following example returns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] version to the caller.</span></span>  
  
 <span data-ttu-id="00720-156">C#</span><span class="sxs-lookup"><span data-stu-id="00720-156">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void GetVersion()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version",  
                                           connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="00720-157">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00720-157">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Partial Public Class StoredProcedures   
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub GetVersion()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="00720-158">O script de teste a seguir invoca o procedimento armazenado GetVersion, definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="00720-158">The following is a test script that invokes the GetVersion stored procedure defined above.</span></span>  
  
```  
EXEC GetVersion  
```  
  
## <a name="see-also"></a><span data-ttu-id="00720-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00720-159">See Also</span></span>  
 [<span data-ttu-id="00720-160">Conceitos de programação da Integração CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="00720-160">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
