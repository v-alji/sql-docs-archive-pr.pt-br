---
title: Criando, alterando e removendo gatilhos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- triggers [SMO]
ms.assetid: 8ddbe23b-6e31-4f8e-8a70-17bd5072413e
author: stevestein
ms.author: sstein
ms.openlocfilehash: c2cdd1573c488fbe7b2309f656cd6bf42e82a527
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582927"
---
# <a name="creating-altering-and-removing-triggers"></a><span data-ttu-id="93c0d-102">Criando, alterando e removendo gatilhos</span><span class="sxs-lookup"><span data-stu-id="93c0d-102">Creating, Altering, and Removing Triggers</span></span>
  <span data-ttu-id="93c0d-103">No SMO, gatilhos são representados por meio do uso do objeto <xref:Microsoft.SqlServer.Management.Smo.Trigger>.</span><span class="sxs-lookup"><span data-stu-id="93c0d-103">In SMO, triggers are represented by using the <xref:Microsoft.SqlServer.Management.Smo.Trigger> object.</span></span> <span data-ttu-id="93c0d-104">O [!INCLUDE[tsql](../../../includes/tsql-md.md)] código que é executado quando o gatilho é acionado é definido pela <xref:Microsoft.SqlServer.Management.Smo.Trigger.TextBody%2A> Propriedade do objeto de gatilho.</span><span class="sxs-lookup"><span data-stu-id="93c0d-104">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] code that runs when the trigger that is fired is set by the <xref:Microsoft.SqlServer.Management.Smo.Trigger.TextBody%2A> property of the Trigger object.</span></span> <span data-ttu-id="93c0d-105">O tipo de gatilho é definido através de outras propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Trigger>, como, por exemplo, a propriedade <xref:Microsoft.SqlServer.Management.Smo.Trigger.Update%2A>.</span><span class="sxs-lookup"><span data-stu-id="93c0d-105">The type of trigger is set by using other properties of the <xref:Microsoft.SqlServer.Management.Smo.Trigger> object, such as the <xref:Microsoft.SqlServer.Management.Smo.Trigger.Update%2A> property.</span></span> <span data-ttu-id="93c0d-106">Essa é uma propriedade booliana que especifica se o gatilho é acionado por um `UPDATE` de registros na tabela pai.</span><span class="sxs-lookup"><span data-stu-id="93c0d-106">This is a Boolean property that specifies whether the trigger is fired by an `UPDATE` of records on the parent table.</span></span>  
  
 <span data-ttu-id="93c0d-107">O objeto <xref:Microsoft.SqlServer.Management.Smo.Trigger> representa gatilhos tradicionais da DML (linguagem de manipulação de dados).</span><span class="sxs-lookup"><span data-stu-id="93c0d-107">The <xref:Microsoft.SqlServer.Management.Smo.Trigger> object represents traditional, data manipulation language (DML) triggers.</span></span> <span data-ttu-id="93c0d-108">No [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] e em versões posteriores, também há suporte a gatilhos da DDL (linguagem de definição de dados).</span><span class="sxs-lookup"><span data-stu-id="93c0d-108">In [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions, data definition language (DDL) triggers are also supported.</span></span> <span data-ttu-id="93c0d-109">Os gatilhos da DDL são representados pelos objetos <xref:Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger> e <xref:Microsoft.SqlServer.Management.Smo.ServerDdlTrigger>.</span><span class="sxs-lookup"><span data-stu-id="93c0d-109">DDL triggers are represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger> object and the <xref:Microsoft.SqlServer.Management.Smo.ServerDdlTrigger> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93c0d-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="93c0d-110">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="creating-altering-and-removing-a-trigger-in-visual-basic"></a><span data-ttu-id="93c0d-111">Criando, alterando e removendo um gatilho no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93c0d-111">Creating, Altering, and Removing a Trigger in Visual Basic</span></span>  
 <span data-ttu-id="93c0d-112">Este exemplo de código mostra como criar e inserir um gatilho de atualização em uma tabela existente, chamada `Sales`, no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93c0d-112">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="93c0d-113">O gatilho envia uma mensagem de lembrete quando a tabela é atualizada ou um novo registro é inserido.</span><span class="sxs-lookup"><span data-stu-id="93c0d-113">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBTriggers1](SMO How to#SMO_VBTriggers1)]  -->  
  
## <a name="creating-altering-and-removing-a-trigger-in-visual-c"></a><span data-ttu-id="93c0d-114">Criando, alterando e removendo um gatilho no Visual C#</span><span class="sxs-lookup"><span data-stu-id="93c0d-114">Creating, Altering, and Removing a Trigger in Visual C#</span></span>  
 <span data-ttu-id="93c0d-115">Este exemplo de código mostra como criar e inserir um gatilho de atualização em uma tabela existente, chamada `Sales`, no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93c0d-115">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="93c0d-116">O gatilho envia uma mensagem de lembrete quando a tabela é atualizada ou um novo registro é inserido.</span><span class="sxs-lookup"><span data-stu-id="93c0d-116">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server mysrv;  
            mysrv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database mydb;  
            mydb = mysrv.Databases["AdventureWorks2012"];  
            //Declare a Table object variable and reference the Customer table.   
            Table mytab;  
            mytab = mydb.Tables["Customer", "Sales"];  
            //Define a Trigger object variable by supplying the parent table, schema ,and name in the constructor.   
            Trigger tr;  
            tr = new Trigger(mytab, "Sales");  
            //Set TextMode property to False, then set other properties to define the trigger.   
            tr.TextMode = false;  
            tr.Insert = true;  
            tr.Update = true;  
            tr.InsertOrder = ActivationOrder.First;  
            string stmt;  
            stmt = " RAISERROR('Notify Customer Relations',16,10) ";  
            tr.TextBody = stmt;  
            tr.ImplementationType = ImplementationType.TransactSql;  
            //Create the trigger on the instance of SQL Server.   
            tr.Create();  
            //Remove the trigger.   
            tr.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-trigger-in-powershell"></a><span data-ttu-id="93c0d-117">Criando, alterando e removendo um gatilho no PowerShell</span><span class="sxs-lookup"><span data-stu-id="93c0d-117">Creating, Altering, and Removing a Trigger in PowerShell</span></span>  
 <span data-ttu-id="93c0d-118">Este exemplo de código mostra como criar e inserir um gatilho de atualização em uma tabela existente, chamada `Sales`, no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93c0d-118">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="93c0d-119">O gatilho envia uma mensagem de lembrete quando a tabela é atualizada ou um novo registro é inserido.</span><span class="sxs-lookup"><span data-stu-id="93c0d-119">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and to the  
#database tables in Adventureworks2012  
CD \sql\localhost\default\databases\AdventureWorks2012\Tables\  
  
#Get reference to the trigger's target table  
$mytab = Get-Item Sales.Customer  
  
# Define a Trigger object variable by supplying the parent table, schema ,and name in the constructor.  
$tr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Trigger -argumentlist $mytab, "Sales"  
  
# Set TextMode property to False, then set other properties to define the trigger.
$tr.TextMode = $false  
$tr.Insert = $true  
$tr.Update = $true  
$tr.InsertOrder = [Microsoft.SqlServer.Management.SMO.Agent.ActivationOrder]::First  
$tr.TextBody = " RAISERROR('Notify Customer Relations',16,10) "  
$tr.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Create the trigger on the instance of SQL Server.
$tr.Create()  
  
#Remove the trigger.
$tr.Drop()  
```  
