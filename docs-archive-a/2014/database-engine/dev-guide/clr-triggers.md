---
title: Gatilhos CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- inserted tables
- database objects [CLR integration], triggers
- common language runtime [SQL Server], triggers
- updated columns
- building database objects [CLR integration], triggers
- triggers [CLR integration]
- deleted tables
- EventData property
- SqlTriggerContext class
- transactions [CLR integration]
ms.assetid: 302a4e4a-3172-42b6-9cc0-4a971ab49c1c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 91f12b0d97d2e2065c5bb08d175253c22dffb032
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571541"
---
# <a name="clr-triggers"></a><span data-ttu-id="e8ff7-102">Gatilhos de CLR</span><span class="sxs-lookup"><span data-stu-id="e8ff7-102">CLR Triggers</span></span>
  <span data-ttu-id="e8ff7-103">Por causa da integração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com CLR (Common Language Runtime) do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], você pode usar qualquer linguagem do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para criar gatilhos CLR.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-103">Because of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR), you can use any [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language to create CLR triggers.</span></span> <span data-ttu-id="e8ff7-104">Esta seção contém informações específicas para gatilhos implementados com a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-104">This section covers information specific to triggers implemented with CLR integration.</span></span> <span data-ttu-id="e8ff7-105">Para obter uma discussão completa sobre gatilhos, consulte [gatilhos DDL](../../relational-databases/triggers/ddl-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="e8ff7-105">For a complete discussion of triggers, see [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).</span></span>  
  
## <a name="what-are-triggers"></a><span data-ttu-id="e8ff7-106">O que são gatilhos?</span><span class="sxs-lookup"><span data-stu-id="e8ff7-106">What Are Triggers?</span></span>  
 <span data-ttu-id="e8ff7-107">Um gatilho é um tipo especial de procedimento armazenado executado automaticamente quando um evento de linguagem é executado.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-107">A trigger is a special type of stored procedure that automatically runs when a language event executes.</span></span> <span data-ttu-id="e8ff7-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inclui dois tipos gerais de gatilhos: DML (linguagem de manipulação de dados) e DDL (linguagem de definição de dados).</span><span class="sxs-lookup"><span data-stu-id="e8ff7-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes two general types of triggers: data manipulation language (DML) and data definition language (DDL) triggers.</span></span> <span data-ttu-id="e8ff7-109">Os gatilhos do tipo DML podem ser usados quando as instruções `INSERT`, `UPDATE`ou `DELETE` modificarem dados em uma tabela especificada ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-109">DML triggers can be used when `INSERT`, `UPDATE`, or `DELETE` statements modify data in a specified table or view.</span></span> <span data-ttu-id="e8ff7-110">Já os gatilhos DDL acionam procedimentos armazenados em resposta a uma variedade de instruções DDL que são instruções iniciadas, principalmente, com `CREATE`, `ALTER`e `DROP`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-110">DDL triggers fire stored procedures in response to a variety of DDL statements, which are primarily statements that begin with `CREATE`, `ALTER`, and `DROP`.</span></span> <span data-ttu-id="e8ff7-111">Os gatilhos DDL podem ser usados para tarefas administrativas, como operações de auditoria e regulamentação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-111">DDL triggers can be used for administrative tasks, such as auditing and regulating database operations.</span></span>  
  
## <a name="unique-capabilities-of-clr-triggers"></a><span data-ttu-id="e8ff7-112">Recursos exclusivos de gatilhos CLR</span><span class="sxs-lookup"><span data-stu-id="e8ff7-112">Unique Capabilities of CLR Triggers</span></span>  
 <span data-ttu-id="e8ff7-113">Os gatilhos gravados em [!INCLUDE[tsql](../../includes/tsql-md.md)] têm a capacidade de determinar quais colunas da exibição ou tabela acionada foram atualizadas com as funções `UPDATE(column)` e `COLUMNS_UPDATED()`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-113">Triggers written in [!INCLUDE[tsql](../../includes/tsql-md.md)] have the capability of determining which columns from the firing view or table have been updated by using the `UPDATE(column)` and `COLUMNS_UPDATED()` functions.</span></span>  
  
 <span data-ttu-id="e8ff7-114">Os gatilhos gravados em linguagem CLR diferem de outros objetos de integração CLR de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-114">Triggers written in a CLR language differ from other CLR integration objects in several significant ways.</span></span> <span data-ttu-id="e8ff7-115">Os gatilhos CLR podem:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-115">CLR triggers can:</span></span>  
  
-   <span data-ttu-id="e8ff7-116">Fazer referência a dados nas tabelas `INSERTED` e `DELETED`</span><span class="sxs-lookup"><span data-stu-id="e8ff7-116">Reference data in the `INSERTED` and `DELETED` tables</span></span>  
  
-   <span data-ttu-id="e8ff7-117">Determinar quais colunas foram modificadas como resultado de uma operação `UPDATE`</span><span class="sxs-lookup"><span data-stu-id="e8ff7-117">Determine which columns have been modified as a result of an `UPDATE` operation</span></span>  
  
-   <span data-ttu-id="e8ff7-118">Acessar informações sobre objetos de banco de dados afetados pela execução de instruções DDL.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-118">Access information about database objects affected by the execution of DDL statements.</span></span>  
  
 <span data-ttu-id="e8ff7-119">Essas capacidades são fornecidas inerentemente na linguagem de consulta, ou pela classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-119">These capabilities are provided inherently in the query language, or by the `SqlTriggerContext` class.</span></span> <span data-ttu-id="e8ff7-120">Para obter informações sobre as vantagens da integração CLR e como escolher entre código gerenciado e [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [visão geral da integração do CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e8ff7-120">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="using-the-sqltriggercontext-class"></a><span data-ttu-id="e8ff7-121">Usando a classe SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="e8ff7-121">Using the SqlTriggerContext Class</span></span>  
 <span data-ttu-id="e8ff7-122">A classe `SqlTriggerContext` não pode ser criada publicamente e só pode ser obtida por meio do acesso à propriedade `SqlContext.TriggerContext` dentro do corpo de um gatilho CLR.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-122">The `SqlTriggerContext` class cannot be publicly constructed and can only be obtained by accessing the `SqlContext.TriggerContext` property within the body of a CLR trigger.</span></span> <span data-ttu-id="e8ff7-123">A classe `SqlTriggerContext` pode ser obtida do `SqlContext` ativo chamando a propriedade `SqlContext.TriggerContext`:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-123">The `SqlTriggerContext` class can be obtained from the active `SqlContext` by calling the `SqlContext.TriggerContext` property:</span></span>  
  
 `SqlTriggerContext myTriggerContext = SqlContext.TriggerContext;`  
  
 <span data-ttu-id="e8ff7-124">A classe `SqlTriggerContext` fornece informações de contexto sobre o gatilho.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-124">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="e8ff7-125">Essas informações contextuais incluem o tipo de ação que causou o acionamento do gatilho, quais colunas foram modificadas em uma operação UPDATE e, no caso de um gatilho DDL, uma estrutura XML `EventData` que descreve a operação de acionamento.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-125">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a DDL trigger, an XML `EventData` structure which describes the triggering operation.</span></span> <span data-ttu-id="e8ff7-126">Para obter mais informações, consulte [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e8ff7-126">For more information, see [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span></span>  
  
### <a name="determining-the-trigger-action"></a><span data-ttu-id="e8ff7-127">Determinando a ação do gatilho</span><span class="sxs-lookup"><span data-stu-id="e8ff7-127">Determining the Trigger Action</span></span>  
 <span data-ttu-id="e8ff7-128">Depois que você obtiver uma classe `SqlTriggerContext`, poderá usá-la para determinar o tipo de ação que acionou o gatilho.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-128">Once you have obtained a `SqlTriggerContext`, you can use it to determine the type of action that caused the trigger to fire.</span></span> <span data-ttu-id="e8ff7-129">Essas informações estão disponíveis por meio da propriedade `TriggerAction` da classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-129">This information is available through the `TriggerAction` property of the `SqlTriggerContext` class.</span></span>  
  
 <span data-ttu-id="e8ff7-130">No caso dos gatilhos DML, a propriedade `TriggerAction` pode ter um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-130">For DML triggers, the `TriggerAction` property can be one of the following values:</span></span>  
  
-   <span data-ttu-id="e8ff7-131">TriggerAction.Update (0x1)</span><span class="sxs-lookup"><span data-stu-id="e8ff7-131">TriggerAction.Update (0x1)</span></span>  
  
-   <span data-ttu-id="e8ff7-132">TriggerAction.Insert (0x2)</span><span class="sxs-lookup"><span data-stu-id="e8ff7-132">TriggerAction.Insert (0x2)</span></span>  
  
-   <span data-ttu-id="e8ff7-133">TriggerAction.Delete(0x3)</span><span class="sxs-lookup"><span data-stu-id="e8ff7-133">TriggerAction.Delete(0x3)</span></span>  
  
-   <span data-ttu-id="e8ff7-134">Para os gatilhos DDL, a lista de possíveis valores TriggerAction é consideravelmente mais longa.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-134">For DDL triggers, the list of possible TriggerAction values is considerably longer.</span></span> <span data-ttu-id="e8ff7-135">Consulte "TriggerAction Enumeration" no .NET Framework SDK para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-135">Please see "TriggerAction Enumeration" in the .NET Framework SDK for more information.</span></span>  
  
### <a name="using-the-inserted-and-deleted-tables"></a><span data-ttu-id="e8ff7-136">Usando as tabelas Inserted e Deleted</span><span class="sxs-lookup"><span data-stu-id="e8ff7-136">Using the Inserted and Deleted Tables</span></span>  
 <span data-ttu-id="e8ff7-137">Duas tabelas especiais são usadas em instruções de gatilho DML: a tabela **inserida** e a tabela **excluída** .</span><span class="sxs-lookup"><span data-stu-id="e8ff7-137">Two special tables are used in DML trigger statements: the **inserted** table and the **deleted** table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e8ff7-138">cria e gerencia automaticamente essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-138">automatically creates and manages these tables.</span></span> <span data-ttu-id="e8ff7-139">Você pode usar essas tabelas temporárias para testar os efeitos de determinadas modificações de dados e definir condições para ações de gatilho DML; no entanto, você não pode alterar os dados diretamente nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-139">You can use these temporary tables to test the effects of certain data modifications and to set conditions for DML trigger actions; however, you cannot alter the data in the tables directly.</span></span>  
  
 <span data-ttu-id="e8ff7-140">Os gatilhos CLR podem acessar as tabelas **inseridas** e **excluídas** por meio do provedor CLR em processo.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-140">CLR triggers can access the **inserted** and **deleted** tables through the CLR in-process provider.</span></span> <span data-ttu-id="e8ff7-141">Isso é feito obtendo-se um objeto `SqlCommand` do objeto SqlContext.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-141">This is done by obtaining a `SqlCommand` object from the SqlContext object.</span></span> <span data-ttu-id="e8ff7-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-142">For example:</span></span>  
  
 <span data-ttu-id="e8ff7-143">C#</span><span class="sxs-lookup"><span data-stu-id="e8ff7-143">C#</span></span>  
  
```  
SqlConnection connection = new SqlConnection ("context connection = true");  
connection.Open();  
SqlCommand command = connection.CreateCommand();  
command.CommandText = "SELECT * from " + "inserted";  
```  
  
 <span data-ttu-id="e8ff7-144">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ff7-144">Visual Basic</span></span>  
  
```  
Dim connection As New SqlConnection("context connection=true")  
Dim command As SqlCommand  
connection.Open()  
command = connection.CreateCommand()  
command.CommandText = "SELECT * FROM " + "inserted"  
```  
  
### <a name="determining-updated-columns"></a><span data-ttu-id="e8ff7-145">Determinando colunas atualizadas</span><span class="sxs-lookup"><span data-stu-id="e8ff7-145">Determining Updated Columns</span></span>  
 <span data-ttu-id="e8ff7-146">Você pode determinar o número de colunas que foram modificadas por uma operação UPDATE usando a propriedade `ColumnCount` do objeto `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-146">You can determine the number of columns that were modified by an UPDATE operation by using the `ColumnCount` property of the `SqlTriggerContext` object.</span></span> <span data-ttu-id="e8ff7-147">Você pode usar o método `IsUpdatedColumn` que considera o ordinal da coluna como um parâmetro de entrada, a fim de determinar se a coluna foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-147">You can use the `IsUpdatedColumn` method, which takes the column ordinal as an input parameter, to determine whether the column was updated.</span></span> <span data-ttu-id="e8ff7-148">Um valor `True` indica que a coluna foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-148">A `True` value indicates that the column has been updated.</span></span>  
  
 <span data-ttu-id="e8ff7-149">Por exemplo, este snippet de código (do gatilho EmailAudit mais adiante neste tópico) lista todas as colunas atualizadas:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-149">For example, this code snippet (from the EmailAudit trigger later in this topic) lists all of the columns updated:</span></span>  
  
 <span data-ttu-id="e8ff7-150">C#</span><span class="sxs-lookup"><span data-stu-id="e8ff7-150">C#</span></span>  
  
```  
reader = command.ExecuteReader();  
reader.Read();  
for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
{  
   pipe.Send("Updated column "  
      + reader.GetName(columnNumber) + "? "  
   + triggContext.IsUpdatedColumn(columnNumber).ToString());  
 }  
  
 reader.Close();  
```  
  
 <span data-ttu-id="e8ff7-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ff7-151">Visual Basic</span></span>  
  
```  
reader = command.ExecuteReader()  
reader.Read()  
Dim columnNumber As Integer  
  
For columnNumber=0 To triggContext.ColumnCount-1  
  
   pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
   "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
Next  
  
reader.Close()  
```  
  
### <a name="accessing-eventdata-for-clr-ddl-triggers"></a><span data-ttu-id="e8ff7-152">Acessando EventData para gatilhos DDL CLR</span><span class="sxs-lookup"><span data-stu-id="e8ff7-152">Accessing EventData for CLR DDL Triggers</span></span>  
 <span data-ttu-id="e8ff7-153">Os gatilhos DDL, como os gatilhos regulares, disparam procedimentos armazenados em resposta a um evento.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-153">DDL triggers, like regular triggers, fire stored procedures in response to an event.</span></span> <span data-ttu-id="e8ff7-154">Mas, ao contrário dos gatilhos DML, não disparam em resposta a instruções UPDATE, INSERT ou DELETE em uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-154">But unlike DML triggers, they do not fire in response to UPDATE, INSERT, or DELETE statements on a table or view.</span></span> <span data-ttu-id="e8ff7-155">Em vez disso, eles são acionados em resposta a uma variedade de instruções DDL que são instruções iniciadas, principalmente, com CREATE, ALTER e DROP.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-155">Instead, they fire in response to a variety of DDL statements, which are primarily statements that begin with CREATE, ALTER, and DROP.</span></span> <span data-ttu-id="e8ff7-156">Os gatilhos DDL podem ser usados para tarefas administrativas, como operações de auditoria e monitoramento de operações de banco de dados e alterações de esquema.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-156">DDL triggers can be used for administrative tasks, such as auditing and monitoring of database operations and schema changes.</span></span>  
  
 <span data-ttu-id="e8ff7-157">Informações sobre um evento que aciona um gatilho DDL estão disponíveis na propriedade `EventData` da classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-157">Information about an event that fires a DDL trigger is available in the `EventData` property of the `SqlTriggerContext` class.</span></span> <span data-ttu-id="e8ff7-158">Essa propriedade contém um valor `xml`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-158">This property contains an `xml` value.</span></span> <span data-ttu-id="e8ff7-159">O esquema xml inclui informações sobre:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-159">The xml schema includes information about:</span></span>  
  
-   <span data-ttu-id="e8ff7-160">A hora do evento.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-160">The time of the event.</span></span>  
  
-   <span data-ttu-id="e8ff7-161">O SPID (System Process ID) da conexão durante a qual o gatilho é executado.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-161">The System Process ID (SPID) of the connection during which the trigger executed.</span></span>  
  
-   <span data-ttu-id="e8ff7-162">O tipo de evento que acionou o gatilho.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-162">The type of event that fired the trigger.</span></span>  
  
 <span data-ttu-id="e8ff7-163">Assim, dependendo do tipo de evento, o esquema poderá conter ainda outras informações, como o banco de dados em que o evento ocorreu, o objeto em relação ao qual ele ocorreu e o comando [!INCLUDE[tsql](../../includes/tsql-md.md)] do evento.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-163">Then, depending on the event type, the schema includes additional information, such as the database in which the event occurred, the object against which the event occurred, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] command of the event.</span></span>  
  
 <span data-ttu-id="e8ff7-164">No exemplo a seguir, o gatilho DDL retorna a propriedade bruta `EventData`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-164">In the following example, the following DDL trigger returns the raw `EventData` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8ff7-165">O envio de resultados e mensagens pelo objeto `SqlPipe` é mostrado aqui apenas para fins ilustrativos e, em geral, não é uma prática recomendada para o código de produção durante a programação de gatilhos CLR.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-165">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code when programming CLR triggers.</span></span> <span data-ttu-id="e8ff7-166">Talvez dados inesperados sejam retornados, o que pode levar a erros de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-166">Additional data returned may be unexpected and lead to application errors.</span></span>  
  
 <span data-ttu-id="e8ff7-167">C#</span><span class="sxs-lookup"><span data-stu-id="e8ff7-167">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   public static void DropTableTrigger()  
   {  
       SqlTriggerContext triggContext = SqlContext.TriggerContext;             
  
       switch(triggContext.TriggerAction)  
       {  
           case TriggerAction.DropTable:  
           SqlContext.Pipe.Send("Table dropped! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
  
           default:  
           SqlContext.Pipe.Send("Something happened! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
       }  
   }  
}  
```  
  
 <span data-ttu-id="e8ff7-168">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ff7-168">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    Public Shared Sub DropTableTrigger()  
        Dim triggContext As SqlTriggerContext  
        triggContext = SqlContext.TriggerContext  
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.DropTable  
              SqlContext.Pipe.Send("Table dropped! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
           Case Else  
              SqlContext.Pipe.Send("Something else happened! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
        End Select  
    End Sub  
End Class     
```  
  
 <span data-ttu-id="e8ff7-169">A seguinte saída de exemplo é o valor de propriedade `EventData` depois que um gatilho DDL foi acionado por um evento `CREATE TABLE`:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-169">The following sample output is the `EventData` property value after a DDL trigger fired by a `CREATE TABLE` event:</span></span>  
  
 `<EVENT_INSTANCE><PostTime>2004-04-16T21:17:16.160</PostTime><SPID>58</SPID><EventType>CREATE_TABLE</EventType><ServerName>MACHINENAME</ServerName><LoginName>MYDOMAIN\myname</LoginName><UserName>MYDOMAIN\myname</UserName><DatabaseName>AdventureWorks</DatabaseName><SchemaName>dbo</SchemaName><ObjectName>UserName</ObjectName><ObjectType>TABLE</ObjectType><TSQLCommand><SetOptions ANSI_NULLS="ON" ANSI_NULL_DEFAULT="ON" ANSI_PADDING="ON" QUOTED_IDENTIFIER="ON" ENCRYPTED="FALSE" /><CommandText>create table dbo.UserName  
(  
 UserName varchar(50),  
 RealName varchar(50)  
)  
</CommandText></TSQLCommand></EVENT_INSTANCE>`  
  
 <span data-ttu-id="e8ff7-170">Além das informações acessíveis através da classe `SqlTriggerContext`, as consultas ainda podem fazer referência a `COLUMNS_UPDATED` e inserted/deleted dentro do texto de um comando executado em processo.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-170">In addition to the information accessible through the `SqlTriggerContext` class, queries can still refer to `COLUMNS_UPDATED` and inserted/deleted within the text of a command executed in-process.</span></span>  
  
## <a name="sample-clr-trigger"></a><span data-ttu-id="e8ff7-171">Exemplo de gatilho CLR</span><span class="sxs-lookup"><span data-stu-id="e8ff7-171">Sample CLR Trigger</span></span>  
 <span data-ttu-id="e8ff7-172">Neste exemplo, considere o cenário no qual você permite que o usuário escolha o ID que desejar, mas você deseja saber quais usuários inseriram especificamente um endereço de email como ID.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-172">In this example, consider the scenario in which you let the user choose any ID they want, but you want to know the users that specifically entered an e-mail address as an ID.</span></span> <span data-ttu-id="e8ff7-173">O gatilho a seguir detectaria essas informações e as registraria em uma tabela de auditoria.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-173">The following trigger would detect that information and log it to an audit table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8ff7-174">O envio de resultados e mensagens pelo objeto `SqlPipe` é mostrado aqui apenas para fins ilustrativos, não sendo, em geral, uma prática recomendada para o código de produção.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-174">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code.</span></span> <span data-ttu-id="e8ff7-175">Talvez dados inesperados sejam retornados, o que pode levar a erros de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e8ff7-175">Additional data returned may be unexpected and lead to application errors</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   [SqlTrigger(Name = @"EmailAudit", Target = "[dbo].[Users]", Event = "FOR INSERT, UPDATE, DELETE")]  
   public static void EmailAudit()  
   {  
      string userName;  
      string realName;  
      SqlCommand command;  
      SqlTriggerContext triggContext = SqlContext.TriggerContext;  
      SqlPipe pipe = SqlContext.Pipe;  
      SqlDataReader reader;  
  
      switch (triggContext.TriggerAction)  
      {  
         case TriggerAction.Insert:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
            reader.Close();  
  
            if (IsValidEMailAddress(userName))  
            {  
               command = new SqlCommand(  
                  @"INSERT [dbo].[UserNameAudit] VALUES ('"  
                  + userName + @"', '" + realName + @"');",  
                  connection);  
               pipe.Send(command.CommandText);  
               command.ExecuteNonQuery();  
               pipe.Send("You inserted: " + userName);  
            }  
         }  
  
         break;  
  
         case TriggerAction.Update:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
  
            pipe.Send(@"You updated: '" + userName + @"' - '"  
               + realName + @"'");  
  
            for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
            {  
               pipe.Send("Updated column "  
                  + reader.GetName(columnNumber) + "? "  
                  + triggContext.IsUpdatedColumn(columnNumber).ToString());  
            }  
  
            reader.Close();  
         }  
  
         break;  
  
         case TriggerAction.Delete:  
            using (SqlConnection connection  
               = new SqlConnection(@"context connection=true"))  
               {  
                  connection.Open();  
                  command = new SqlCommand(@"SELECT * FROM DELETED;",  
                     connection);  
                  reader = command.ExecuteReader();  
  
                  if (reader.HasRows)  
                  {  
                     pipe.Send(@"You deleted the following rows:");  
                     while (reader.Read())  
                     {  
                        pipe.Send(@"'" + reader.GetString(0)  
                        + @"', '" + reader.GetString(1) + @"'");  
                     }  
  
                     reader.Close();  
  
                     //alternately, to just send a tabular resultset back:  
                     //pipe.ExecuteAndSend(command);  
                  }  
                  else  
                  {  
                     pipe.Send("No rows affected.");  
                  }  
               }  
  
               break;  
            }  
        }  
  
     public static bool IsValidEMailAddress(string email)  
     {  
         return Regex.IsMatch(email, @"^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$");  
     }  
}  
```  
  
 <span data-ttu-id="e8ff7-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ff7-176">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Text.RegularExpressions  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    <SqlTrigger(Name:="EmailAudit", Target:="[dbo].[Users]", Event:="FOR INSERT, UPDATE, DELETE")> _  
    Public Shared Sub EmailAudit()  
        Dim userName As String  
        Dim realName As String  
        Dim command As SqlCommand  
        Dim triggContext As SqlTriggerContext  
        Dim pipe As SqlPipe  
        Dim reader As SqlDataReader    
  
        triggContext = SqlContext.TriggerContext      
        pipe = SqlContext.Pipe    
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.Insert  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 reader.Close()  
  
                 If IsValidEmailAddress(userName) Then  
                     command = New SqlCommand("INSERT [dbo].[UserNameAudit] VALUES ('" & _  
                       userName & "', '" & realName & "');", connection)  
  
                    pipe.Send(command.CommandText)  
                    command.ExecuteNonQuery()  
                    pipe.Send("You inserted: " & userName)  
  
                 End If  
              End Using  
  
           Case TriggerAction.Update  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 pipe.Send("You updated: " & userName & " - " & realName)  
  
                 Dim columnNumber As Integer  
  
                 For columnNumber=0 To triggContext.ColumnCount-1  
  
                    pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
                      "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
                 Next  
  
                 reader.Close()  
              End Using  
  
           Case TriggerAction.Delete  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM DELETED;", connection)  
  
                 reader = command.ExecuteReader()  
  
                 If reader.HasRows Then  
                    pipe.Send("You deleted the following rows:")  
  
                    While reader.Read()  
  
                       pipe.Send( reader.GetString(0) & ", " & reader.GetString(1) )  
  
                    End While   
  
                    reader.Close()  
  
                    ' Alternately, just send a tabular resultset back:  
                    ' pipe.ExecuteAndSend(command)  
  
                 Else  
                   pipe.Send("No rows affected.")  
                 End If  
  
              End Using   
        End Select  
    End Sub  
  
    Public Shared Function IsValidEMailAddress(emailAddress As String) As Boolean  
  
       return Regex.IsMatch(emailAddress, "^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$")  
    End Function      
End Class  
```  
  
 <span data-ttu-id="e8ff7-177">Suponha que existam duas tabelas com as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-177">Assuming two tables exist with the following definitions:</span></span>  
  
```  
CREATE TABLE Users  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
);  
GO CREATE TABLE UserNameAudit  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
)  
```  
  
 <span data-ttu-id="e8ff7-178">A [!INCLUDE[tsql](../../includes/tsql-md.md)] instrução que cria o gatilho no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é a seguinte e pressupõe que o assembly **SQLCLRTest** já esteja registrado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-178">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that creates the trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is as follows, and assumes assembly **SQLCLRTest** is already registered in the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
```  
CREATE TRIGGER EmailAudit  
ON Users  
FOR INSERT, UPDATE, DELETE  
AS  
EXTERNAL NAME SQLCLRTest.CLRTriggers.EmailAudit  
```  
  
## <a name="validating-and-canceling-invalid-transactions"></a><span data-ttu-id="e8ff7-179">Validando e cancelando transações inválidas</span><span class="sxs-lookup"><span data-stu-id="e8ff7-179">Validating and Canceling Invalid Transactions</span></span>  
 <span data-ttu-id="e8ff7-180">O uso de gatilhos para validar e cancelar transações INSERT, UPDATE ou DELETE inválidas ou impedir alterações em seu esquema de banco de dados é comum.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-180">Using triggers to validate and cancel invalid INSERT, UPDATE, or DELETE transactions or to prevent changes to your database schema is common.</span></span> <span data-ttu-id="e8ff7-181">Para isso, incorpore a lógica de validação em seu gatilho e, em seguida, reverta a transação atual se a ação não corresponder aos critérios de validação.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-181">This can be accomplished by incorporating validation logic into your trigger and then rolling back the current transaction if the action does not meet the validation criteria.</span></span>  
  
 <span data-ttu-id="e8ff7-182">Quando chamado em um gatilho, o método `Transaction.Rollback` ou um SqlCommand com o texto de comando "TRANSACTION ROLLBACK" lança uma exceção com uma mensagem de erro ambígua e deve ser encapsulado em um bloco try/catch.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-182">When called within a trigger, the `Transaction.Rollback` method or a SqlCommand with the command text "TRANSACTION ROLLBACK" throws an exception with an ambiguous error message and must be wrapped in a try/catch block.</span></span> <span data-ttu-id="e8ff7-183">A mensagem de erro exibida é semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="e8ff7-183">The error message you see is similar to the following:</span></span>  
  
```  
Msg 6549, Level 16, State 1, Procedure trig_InsertValidator, Line 0  
A .NET Framework error occurred during execution of user defined routine or aggregate 'trig_InsertValidator':   
System.Data.SqlClient.SqlException: Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting... User transaction, if any, will be rolled back.  
```  
  
 <span data-ttu-id="e8ff7-184">Essa exceção é esperada e o bloco try/catch é necessário para que a execução do código continue.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-184">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="e8ff7-185">Quando o código de gatilho termina a execução, outra exceção é gerada</span><span class="sxs-lookup"><span data-stu-id="e8ff7-185">When the trigger code finishes execution, another exception is raised</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure trig_InsertValidator, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate "trig_InsertValidator" has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting.  
The statement has been terminated.  
```  
  
 <span data-ttu-id="e8ff7-186">Essa exceção também é esperada, sendo necessário um bloco try/catch ao redor da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] que executa a ação que aciona o gatilho para que a execução possa continuar.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-186">This exception is also expected, and a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger is necessary so that execution can continue.</span></span> <span data-ttu-id="e8ff7-187">Apesar das duas exceções lançadas, a transação é revertida e as alterações não são confirmadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-187">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed to the table.</span></span> <span data-ttu-id="e8ff7-188">A principal diferença entre gatilhos CLR e gatilhos [!INCLUDE[tsql](../../includes/tsql-md.md)] é que os gatilhos [!INCLUDE[tsql](../../includes/tsql-md.md)] podem continuar a operar depois que a transação é revertida.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-188">A major difference between CLR triggers and [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers is that [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers can continue to perform more work after the transaction is rolled back.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e8ff7-189">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e8ff7-189">Example</span></span>  
 <span data-ttu-id="e8ff7-190">O gatilho a seguir executa uma validação simples de instruções INSERT em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-190">The following trigger performs simple validation of INSERT statements on a table.</span></span> <span data-ttu-id="e8ff7-191">Se o valor inteiro inserido for igual a um, a transação será revertida e o valor não será inserido na tabela.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-191">If the inserted integer value is equal to one, the transaction is rolled back and the value is not inserted into the table.</span></span> <span data-ttu-id="e8ff7-192">Todos os outros valores inteiros são inseridos na tabela.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-192">All other integer values are inserted into the table.</span></span> <span data-ttu-id="e8ff7-193">Observe o bloco try/catch ao redor do método `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-193">Note the try/catch block around the `Transaction.Rollback` method.</span></span> <span data-ttu-id="e8ff7-194">O script [!INCLUDE[tsql](../../includes/tsql-md.md)] cria uma tabela de teste, um assembly e um procedimento armazenado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-194">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates a test table, assembly, and managed stored procedure.</span></span> <span data-ttu-id="e8ff7-195">Observe que as duas instruções INSERT são encapsuladas em um bloco try/catch de forma que a exceção lançada quando a execução do gatilho termina é capturada.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-195">Note that the two INSERT statements are wrapped in a try/catch block so that the exception thrown when the trigger finishes execution is caught.</span></span>  
  
 <span data-ttu-id="e8ff7-196">C#</span><span class="sxs-lookup"><span data-stu-id="e8ff7-196">C#</span></span>  
  
```  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class Triggers  
{  
    // Enter existing table or view for the target and uncomment the attribute line  
    // [Microsoft.SqlServer.Server.SqlTrigger (Name="trig_InsertValidator", Target="Table1", Event="FOR INSERT")]  
    public static void trig_InsertValidator()  
    {  
        using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
        {  
            SqlCommand command;  
            SqlDataReader reader;  
            int value;  
  
            // Open the connection.  
            connection.Open();  
  
            // Get the inserted value.  
            command = new SqlCommand(@"SELECT * FROM INSERTED", connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            value = (int)reader[0];  
            reader.Close();  
  
            // Rollback the transaction if a value of 1 was inserted.  
            if (1 == value)  
            {  
                try  
                {  
                    // Get the current transaction and roll it back.  
                    Transaction trans = Transaction.Current;  
                    trans.Rollback();                      
                }  
                catch (SqlException ex)  
                {  
                    // Catch the expected exception.                      
                }  
            }  
            else  
            {  
                // Perform other actions here.  
            }  
  
            // Close the connection.  
            connection.Close();              
        }  
    }  
}  
```  
  
 <span data-ttu-id="e8ff7-197">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ff7-197">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class Triggers  
' Enter existing table or view for the target and uncomment the attribute line  
' <Microsoft.SqlServer.Server.SqlTrigger(Name:="trig_InsertValidator", Target:="Table1", Event:="FOR INSERT")> _  
Public Shared Sub  trig_InsertValidator ()  
    Using connection As New SqlConnection("context connection=true")  
  
        Dim command As SqlCommand  
        Dim reader As SqlDataReader  
        Dim value As Integer  
  
        ' Open the connection.  
        connection.Open()  
  
        ' Get the inserted value.  
        command = New SqlCommand("SELECT * FROM INSERTED", connection)  
        reader = command.ExecuteReader()  
        reader.Read()  
        value = CType(reader(0), Integer)  
        reader.Close()  
  
        ' Rollback the transaction if a value of 1 was inserted.  
        If value = 1 Then  
  
            Try  
                ' Get the current transaction and roll it back.  
                Dim trans As Transaction  
                trans = Transaction.Current  
                trans.Rollback()  
  
            Catch ex As SqlException  
  
                ' Catch the exception.                      
            End Try  
        Else  
  
            ' Perform other actions here.  
        End If  
  
        ' Close the connection.  
        connection.Close()  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="e8ff7-198">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e8ff7-198">Transact-SQL</span></span>  
  
```  
-- Create the test table, assembly, and trigger.  
CREATE TABLE Table1(c1 int);  
go  
  
CREATE ASSEMBLY ValidationTriggers from 'E:\programming\ ValidationTriggers.dll';  
go  
  
CREATE TRIGGER trig_InsertValidator  
ON Table1  
FOR INSERT  
AS EXTERNAL NAME ValidationTriggers.Triggers.trig_InsertValidator;  
go  
  
-- Use a Try/Catch block to catch the expected exception  
BEGIN TRY  
   INSERT INTO Table1 VALUES(42)  
   INSERT INTO Table1 VALUES(1)  
END TRY  
BEGIN CATCH  
  SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
END CATCH;  
  
-- Clean up.  
DROP TRIGGER trig_InsertValidator;  
DROP ASSEMBLY ValidationTriggers;  
DROP TABLE Table1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8ff7-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8ff7-199">See Also</span></span>  
 <span data-ttu-id="e8ff7-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8ff7-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="e8ff7-201">[Gatilhos DML](../../relational-databases/triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e8ff7-201">[DML Triggers](../../relational-databases/triggers/dml-triggers.md) </span></span>  
 <span data-ttu-id="e8ff7-202">[Gatilhos DDL](../../relational-databases/triggers/ddl-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e8ff7-202">[DDL Triggers](../../relational-databases/triggers/ddl-triggers.md) </span></span>  
 <span data-ttu-id="e8ff7-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8ff7-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="e8ff7-204">[Criando objetos de banco de dados com o Common Language Runtime &#40;integração de&#41; CLR](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span><span class="sxs-lookup"><span data-stu-id="e8ff7-204">[Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span></span>  
 [<span data-ttu-id="e8ff7-205">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ff7-205">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
