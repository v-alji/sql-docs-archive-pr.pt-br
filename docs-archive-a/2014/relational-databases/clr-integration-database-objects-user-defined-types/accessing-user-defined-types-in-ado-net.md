---
title: Acessando tipos definidos pelo usuário em ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: a94e333ad743ed07dff6b973ebfe227312a1cab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576449"
---
# <a name="accessing-user-defined-types-in-adonet"></a><span data-ttu-id="65c0f-102">Acessando tipos definidos pelo usuário no ADO.NET</span><span class="sxs-lookup"><span data-stu-id="65c0f-102">Accessing User-Defined Types in ADO.NET</span></span>
  <span data-ttu-id="65c0f-103">Os tipos definidos pelo usuário (UDTs) são escritos usando qualquer um dos idiomas compatíveis com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework Common Language Runtime (CLR) que produz código verificável.</span><span class="sxs-lookup"><span data-stu-id="65c0f-103">User-defined types (UDTs) are written using any of the languages supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="65c0f-104">Isso inclui o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# e o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="65c0f-104">This includes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span></span> <span data-ttu-id="65c0f-105">Os UDTs permitem armazenar objetos e estruturas de dados personalizadas em um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65c0f-105">UDTs allow objects and custom data structures to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="65c0f-106">Os dados são expostos como membros públicos de uma classe ou estrutura do .NET Framework e os comportamentos são definidos pelos métodos da classe ou estrutura.</span><span class="sxs-lookup"><span data-stu-id="65c0f-106">The data is exposed as public members of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span> <span data-ttu-id="65c0f-107">Um UDT pode ser usado como definição de coluna de uma tabela, como uma variável em um lote [!INCLUDE[tsql](../../includes/tsql-md.md)], ou como um argumento de uma função [!INCLUDE[tsql](../../includes/tsql-md.md)] ou um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="65c0f-107">A UDT can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
 <span data-ttu-id="65c0f-108">No ADO.NET, o provedor `System.Data.SqlClient` expõe UDTs dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="65c0f-108">In ADO.NET, the `System.Data.SqlClient` provider exposes UDTs in the following ways:</span></span>  
  
-   <span data-ttu-id="65c0f-109">Por meio do `System.Data.SqlClient.SqlDataReader` como um objeto.</span><span class="sxs-lookup"><span data-stu-id="65c0f-109">Through the `System.Data.SqlClient.SqlDataReader` as an object.</span></span>  
  
-   <span data-ttu-id="65c0f-110">Por meio do `SqlDataReader` como bytes brutos.</span><span class="sxs-lookup"><span data-stu-id="65c0f-110">Through the `SqlDataReader` as raw bytes.</span></span>  
  
-   <span data-ttu-id="65c0f-111">Como um parâmetro de um objeto `System.Data.SqlClient.SqlParameter`.</span><span class="sxs-lookup"><span data-stu-id="65c0f-111">As a parameter of a `System.Data.SqlClient.SqlParameter` object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65c0f-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="65c0f-112">In This Section</span></span>  
 [<span data-ttu-id="65c0f-113">Recuperando dados UDT</span><span class="sxs-lookup"><span data-stu-id="65c0f-113">Retrieving UDT Data</span></span>](accessing-user-defined-types-retrieving-udt-data.md)  
 <span data-ttu-id="65c0f-114">Descreve como recuperar dados UDT e como especificar parâmetros.</span><span class="sxs-lookup"><span data-stu-id="65c0f-114">Describes how to retrieve UDT data and how to specify parameters.</span></span>  
  
 [<span data-ttu-id="65c0f-115">Atualizando colunas UDT com DataAdapters</span><span class="sxs-lookup"><span data-stu-id="65c0f-115">Updating UDT Columns with DataAdapters</span></span>](accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 <span data-ttu-id="65c0f-116">Descreve como trabalhar com UDTs em `DataSets` e como atualizar dados UDT usando `DataAdapters`.</span><span class="sxs-lookup"><span data-stu-id="65c0f-116">Describes how to work with UDTs in `DataSets` and how to update UDT data using `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c0f-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65c0f-117">See Also</span></span>  
 [<span data-ttu-id="65c0f-118">Tipos definido pelo usuário CLR</span><span class="sxs-lookup"><span data-stu-id="65c0f-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
