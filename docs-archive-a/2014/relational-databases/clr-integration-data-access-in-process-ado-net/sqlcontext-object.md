---
title: Objeto SqlContext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- Windows identity [CLR integration]
- SqlContext object
- context [CLR integration]
ms.assetid: 67437853-8a55-44d9-9337-90689ebba730
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f036e274925f7b28b79f619f8e24b3e8804140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681693"
---
# <a name="sqlcontext-object"></a><span data-ttu-id="4a567-102">Objeto SqlContext</span><span class="sxs-lookup"><span data-stu-id="4a567-102">SqlContext Object</span></span>
  <span data-ttu-id="4a567-103">O código gerenciado é invocado no servidor quando você chama um procedimento ou uma função, quando chama um método em um tipo CLR (Common Language Runtime) definido pelo usuário ou quando sua ação dispara um gatilho definido em qualquer das linguagens do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a567-103">You invoke managed code in the server when you call a procedure or function, when you call a method on a common language runtime (CLR) user-defined type, or when your action fires a trigger defined in any of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework languages.</span></span> <span data-ttu-id="4a567-104">Como a execução desse código é exigida como parte de uma conexão de usuário, o acesso ao contexto do chamador a partir do código em execução no servidor é necessário.</span><span class="sxs-lookup"><span data-stu-id="4a567-104">Because execution of this code is requested as part of a user connection, access to the context of the caller from the code running in the server is required.</span></span> <span data-ttu-id="4a567-105">Além disso, determinadas operações de acesso a dados podem ser válidas somente se executadas no contexto do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a567-105">In addition, certain data access operations may only be valid if run under the context of the caller.</span></span> <span data-ttu-id="4a567-106">Por exemplo, o acesso a pseudotabelas inseridas e excluídas usadas em operações de gatilho será válido somente no contexto do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a567-106">For example, access to inserted and deleted pseudo-tables used in trigger operations is only valid under the context of the caller.</span></span>  
  
 <span data-ttu-id="4a567-107">O contexto do chamador é abstraído em um objeto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="4a567-107">The context of the caller is abstracted in a `SqlContext` object.</span></span> <span data-ttu-id="4a567-108">Para obter mais informações sobre os métodos e as propriedades `SqlTriggerContext`, consulte a documentação de referência da classe `Microsoft.SqlServer.Server.SqlTriggerContext` no SDK do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a567-108">For more information about the `SqlTriggerContext` methods and properties, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="4a567-109">`SqlContext` fornece acesso aos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="4a567-109">`SqlContext` provides access to the following components:</span></span>  
  
-   <span data-ttu-id="4a567-110">`SqlPipe`: o objeto `SqlPipe` representa o "pipe" pelo qual os resultados fluem para o cliente.</span><span class="sxs-lookup"><span data-stu-id="4a567-110">`SqlPipe`: The `SqlPipe` object represents the "pipe" through which results flow to the client.</span></span> <span data-ttu-id="4a567-111">Para obter mais informações sobre o `SqlPipe` objeto, consulte [objeto SqlPipe](sqlpipe-object.md).</span><span class="sxs-lookup"><span data-stu-id="4a567-111">For more information about the `SqlPipe` object, see [SqlPipe Object](sqlpipe-object.md).</span></span>  
  
-   <span data-ttu-id="4a567-112">`SqlTriggerContext`: o objeto `SqlTriggerContext` pode ser recuperado somente de dentro um gatilho CLR.</span><span class="sxs-lookup"><span data-stu-id="4a567-112">`SqlTriggerContext`: The `SqlTriggerContext` object can only be retrieved from within a CLR trigger.</span></span> <span data-ttu-id="4a567-113">Ele fornece informações sobre a operação que fez o gatilho ser acionado e um mapa das colunas que foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="4a567-113">It provides information about the operation that caused the trigger to fire and a map of the columns that were updated.</span></span> <span data-ttu-id="4a567-114">Para obter mais informações sobre o `SqlTriggerContext` objeto, consulte [objeto SqlTriggerContext](sqltriggercontext-object.md).</span><span class="sxs-lookup"><span data-stu-id="4a567-114">For more information about the `SqlTriggerContext` object, see [SqlTriggerContext Object](sqltriggercontext-object.md).</span></span>  
  
-   <span data-ttu-id="4a567-115">`IsAvailable`: a propriedade `IsAvailable` é usada para determinar a disponibilidade de contexto.</span><span class="sxs-lookup"><span data-stu-id="4a567-115">`IsAvailable`: The `IsAvailable` property is used to determine context availability.</span></span>  
  
-   <span data-ttu-id="4a567-116">`WindowsIdentity`: a propriedade `WindowsIdentity` é usada para recuperar a identidade do Windows do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a567-116">`WindowsIdentity`: The `WindowsIdentity` property is used to retrieve the Windows identity of the caller.</span></span>  
  
## <a name="determining-context-availability"></a><span data-ttu-id="4a567-117">Determinando a disponibilidade de contexto</span><span class="sxs-lookup"><span data-stu-id="4a567-117">Determining Context Availability</span></span>  
 <span data-ttu-id="4a567-118">Consulte a classe `SqlContext` para ver se o código em execução no momento está sendo executado em processo.</span><span class="sxs-lookup"><span data-stu-id="4a567-118">Query the `SqlContext` class to see if the currently executing code is running in-process.</span></span> <span data-ttu-id="4a567-119">Para fazer isso, verifique a propriedade `IsAvailable` do objeto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="4a567-119">To do this, check the `IsAvailable` property of the `SqlContext` object.</span></span> <span data-ttu-id="4a567-120">A propriedade `IsAvailable` é somente leitura e retornará `True` se o código de chamada estiver em execução no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e se outros membros de `SqlContext` puderem ser acessados.</span><span class="sxs-lookup"><span data-stu-id="4a567-120">The `IsAvailable` property is read-only, and returns `True` if the calling code is running inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and if other `SqlContext` members can be accessed.</span></span> <span data-ttu-id="4a567-121">Se a propriedade `IsAvailable` retornar `False`, todos os outros membros de `SqlContext` lançarão um `InvalidOperationException`, se usado.</span><span class="sxs-lookup"><span data-stu-id="4a567-121">If the `IsAvailable` property returns `False`, all the other `SqlContext` members throw an `InvalidOperationException`, if used.</span></span> <span data-ttu-id="4a567-122">Se `IsAvailable` retornar `False`, qualquer tentativa de abrir um objeto de conexão que tem "context connection=true" na cadeia de conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="4a567-122">If `IsAvailable` returns `False`, any attempt to open a connection object that has "context connection=true" in the connection string fails.</span></span>  
  
## <a name="retrieving-windows-identity"></a><span data-ttu-id="4a567-123">Recuperando a identidade do Windows</span><span class="sxs-lookup"><span data-stu-id="4a567-123">Retrieving Windows Identity</span></span>  
 <span data-ttu-id="4a567-124">O código CLR em execução no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sempre é invocado no contexto da conta de processo.</span><span class="sxs-lookup"><span data-stu-id="4a567-124">CLR code executing inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is always invoked in the context of the process account.</span></span> <span data-ttu-id="4a567-125">Se o código deve executar determinadas ações usando a identidade do usuário que fez a chamada em vez da identidade de processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um token de representação deve ser obtido por meio da propriedade `WindowsIdentity` do objeto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="4a567-125">If the code should perform certain actions using the identity of the calling user, instead of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process identity, then an impersonation token should be obtained through the `WindowsIdentity` property of the `SqlContext` object.</span></span> <span data-ttu-id="4a567-126">A propriedade `WindowsIdentity` retorna uma instância `WindowsIdentity` que representa a identidade do [!INCLUDE[msCoName](../../includes/msconame-md.md)] do chamador ou que é nula, se o cliente foi autenticado usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a567-126">The `WindowsIdentity` property returns a `WindowsIdentity` instance representing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows identity of the caller, or null if the client was authenticated using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="4a567-127">Outros assemblies marcados com `EXTERNAL_ACCESS` ou permissões `UNSAFE` podem acessar esta propriedade.</span><span class="sxs-lookup"><span data-stu-id="4a567-127">Only assemblies marked with `EXTERNAL_ACCESS` or `UNSAFE` permissions can access this property.</span></span>  
  
 <span data-ttu-id="4a567-128">Depois de obter o objeto `WindowsIdentity`, os chamadores podem representar a conta de cliente e executar ações em seu nome.</span><span class="sxs-lookup"><span data-stu-id="4a567-128">After obtaining the `WindowsIdentity` object, callers can impersonate the client account and perform actions on their behalf.</span></span>  
  
 <span data-ttu-id="4a567-129">A identidade do chamador está disponível por meio de `SqlContext.WindowsIdentity` somente se o cliente que iniciou a execução do procedimento armazenado ou da função se conectou ao servidor usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4a567-129">The identity of the caller is only available through `SqlContext.WindowsIdentity` if the client that initiated execution of the stored-procedure or function connected to the server using Windows Authentication.</span></span> <span data-ttu-id="4a567-130">Se, em vez disso, a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi usada, essa propriedade será nula e o código não poderá representar o chamador.</span><span class="sxs-lookup"><span data-stu-id="4a567-130">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication was used instead, this property is null and the code is unable to impersonate the caller.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4a567-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4a567-131">Example</span></span>  
 <span data-ttu-id="4a567-132">O exemplo a seguir mostra como obter a identidade do Windows do cliente que fez a chamada e representar o cliente.</span><span class="sxs-lookup"><span data-stu-id="4a567-132">The following example shows how to get the Windows identity of the calling client and impersonate the client.</span></span>  
  
 <span data-ttu-id="4a567-133">C#</span><span class="sxs-lookup"><span data-stu-id="4a567-133">C#</span></span>  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void WindowsIDTestProc()  
{  
    WindowsIdentity clientId = null;  
    WindowsImpersonationContext impersonatedUser = null;  
  
    // Get the client ID.  
    clientId = SqlContext.WindowsIdentity;  
  
    // This outer try block is used to thwart exception filter   
    // attacks which would prevent the inner finally   
    // block from executing and resetting the impersonation.  
    try  
    {  
        try  
        {  
            impersonatedUser = clientId.Impersonate();  
            if (impersonatedUser != null)  
            {  
                // Perform some action using impersonation.  
            }  
        }  
        finally  
        {  
            // Undo impersonation.  
            if (impersonatedUser != null)  
                impersonatedUser.Undo();  
        }  
    }  
    catch  
    {  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="4a567-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a567-134">Visual Basic</span></span>  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  WindowsIDTestProcVB ()  
    Dim clientId As WindowsIdentity  
    Dim impersonatedUser As WindowsImpersonationContext  
  
    ' Get the client ID.  
    clientId = SqlContext.WindowsIdentity  
  
    ' This outer try block is used to thwart exception filter   
    ' attacks which would prevent the inner finally   
    ' block from executing and resetting the impersonation.  
  
    Try  
        Try  
  
            impersonatedUser = clientId.Impersonate()  
  
            If impersonatedUser IsNot Nothing Then  
                ' Perform some action using impersonation.  
            End If  
  
        Finally  
            ' Undo impersonation.  
            If impersonatedUser IsNot Nothing Then  
                impersonatedUser.Undo()  
            End If  
        End Try  
  
    Catch e As Exception  
  
        Throw e  
  
    End Try  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a567-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a567-135">See Also</span></span>  
 <span data-ttu-id="4a567-136">[Objeto SqlPipe](sqlpipe-object.md) </span><span class="sxs-lookup"><span data-stu-id="4a567-136">[SqlPipe Object](sqlpipe-object.md) </span></span>  
 <span data-ttu-id="4a567-137">[Objeto SqlTriggerContext](sqltriggercontext-object.md) </span><span class="sxs-lookup"><span data-stu-id="4a567-137">[SqlTriggerContext Object](sqltriggercontext-object.md) </span></span>  
 <span data-ttu-id="4a567-138">[Gatilhos CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="4a567-138">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="4a567-139">Extensões específicas em processo do SQL Server para o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a567-139">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
