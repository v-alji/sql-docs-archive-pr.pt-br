---
title: Visão geral dos atributos personalizados de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- custom attributes [CLR integration]
- attributes [CLR integration]
- common language runtime [SQL Server], attributes
- database objects [CLR integration], custom attributes
- building database objects [CLR integration], custom attributes
ms.assetid: ecf5c097-0972-48e2-a9c0-b695b7dd2820
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: aa0bf94ee27fd89a6aa690e0ff2f8e3295648946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569633"
---
# <a name="overview-of-clr-integration-custom-attributes"></a><span data-ttu-id="e2529-102">Visão geral dos atributos personalizados da integração CLR</span><span class="sxs-lookup"><span data-stu-id="e2529-102">Overview of CLR Integration Custom Attributes</span></span>
  <span data-ttu-id="e2529-103">O CLR (common language runtime) do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] permite o uso de palavras-chave descritivas, denominadas atributos.</span><span class="sxs-lookup"><span data-stu-id="e2529-103">The common language runtime (CLR) of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] allows the use of descriptive keywords, called attributes.</span></span> <span data-ttu-id="e2529-104">Esses atributos fornecem informações adicionais para vários elementos, como métodos e classes.</span><span class="sxs-lookup"><span data-stu-id="e2529-104">These attributes provide additional information for many elements, such as methods and classes.</span></span> <span data-ttu-id="e2529-105">Os atributos são salvos no assembly com os metadados do objeto e podem ser usados para descrever seu código para outras ferramentas de desenvolvimento ou para afetar o comportamento do runtime dentro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2529-105">The attributes are saved in the assembly with the metadata of the object, and can be used to describe your code to other development tools or to affect runtime behavior inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e2529-106">Quando você registrar uma rotina de CLR com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será gerado um conjunto de propriedades sobre a rotina.</span><span class="sxs-lookup"><span data-stu-id="e2529-106">When you register a CLR routine with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives a set of properties about the routine.</span></span> <span data-ttu-id="e2529-107">Essas propriedades de rotina determinam os recursos da rotina, incluindo sua possibilidade de ser indexada.</span><span class="sxs-lookup"><span data-stu-id="e2529-107">These routine properties determine the capabilities of the routine, including whether the routine can be indexed.</span></span> <span data-ttu-id="e2529-108">Por exemplo, a definição da propriedade `DataAccess` como `DataAccessKind.Read` permite que você acesse dados de tabelas do usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dentro de uma função CLR.</span><span class="sxs-lookup"><span data-stu-id="e2529-108">For example, setting the `DataAccess` property to `DataAccessKind.Read` lets you access data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user tables inside a CLR function.</span></span> <span data-ttu-id="e2529-109">O exemplo a seguir mostra um caso simples no qual a `DataAccess` propriedade é definida para facilitar o acesso a dados de uma tabela de usuário **Table1**.</span><span class="sxs-lookup"><span data-stu-id="e2529-109">The following example shows a simple case in which the `DataAccess` property is set to facilitate data access from a user table **table1**.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public partial class UserDefinedFunctions  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static string func1()  
    {  
        // Open a connection and create a command  
        SqlConnection conn = new SqlConnection("context connection = true");  
        conn.Open();  
        SqlCommand cmd = conn.CreateCommand();  
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10";  
        // where table1 is a user table  
        // Execute this command   
        SqlDataReader rd = cmd.ExecuteReader();  
        // Set string ret_val to str_val returned from the query  
        string ret_val = rd.GetValue(0).ToString();  
        rd.Close();  
        return ret_val;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public partial Class UserDefinedFunctions  
    <SqlFunction(DataAccess = DataAccessKind.Read)> _   
    Public Shared Function func1() As String  
        ' Open a connection and create a command  
        Dim conn As SqlConnection = New SqlConnection("context connection = true")   
        conn.Open()  
        Dim cmd As SqlCommand =  conn.CreateCommand()   
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10"  
        ' where table1 is a user table  
        ' Execute this command   
        Dim rd As SqlDataReader =  cmd.ExecuteReader()   
        ' Set string ret_val to str_val returned from the query  
        Dim ret_val As String =  rd.GetValue(0).ToString()   
        rd.Close()  
        Return ret_val  
    End Function  
End Class  
```  
  
 <span data-ttu-id="e2529-110">Para rotinas do [!INCLUDE[tsql](../../includes/tsql-md.md)], o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gera as propriedades de rotina diretamente da definição de rotina.</span><span class="sxs-lookup"><span data-stu-id="e2529-110">For [!INCLUDE[tsql](../../includes/tsql-md.md)] routines, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives routine properties directly from the routine definition.</span></span> <span data-ttu-id="e2529-111">Para rotinas de CLR, o servidor não analisa o corpo da rotina para gerar essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="e2529-111">For CLR routines, the server does not analyze the body of the routine to derive these properties.</span></span> <span data-ttu-id="e2529-112">Em vez disso, você pode personalizar atributos para classes e membros de classe implementados em uma linguagem do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2529-112">Instead, you can use custom attributes for classes and class members implemented in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language.</span></span>  
  
 <span data-ttu-id="e2529-113">Os atributos personalizados necessários para rotinas de CLR, tipos definidos pelo usuário e agregações são definidos no namespace `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="e2529-113">The custom attributes needed for CLR routines, user-defined types, and aggregates are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2529-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2529-114">See Also</span></span>  
 [<span data-ttu-id="e2529-115">Atributos personalizados para rotinas do CLR</span><span class="sxs-lookup"><span data-stu-id="e2529-115">Custom Attributes for CLR Routines</span></span>](../../relational-databases/clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)  
  
  
