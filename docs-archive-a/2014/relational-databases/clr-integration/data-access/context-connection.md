---
title: Conexão de contexto | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 82c739aa9c1952c71e9a16aaa68ec999851b3202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573122"
---
# <a name="context-connection"></a><span data-ttu-id="45c93-102">Conexão de contexto</span><span class="sxs-lookup"><span data-stu-id="45c93-102">Context Connection</span></span>
  <span data-ttu-id="45c93-103">O problema de acesso a dados internos é um cenário bastante comum.</span><span class="sxs-lookup"><span data-stu-id="45c93-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="45c93-104">Ou seja, você deseja acessar o mesmo servidor no qual sua função ou seu procedimento armazenado CLR (Common Language Runtime) está em execução.</span><span class="sxs-lookup"><span data-stu-id="45c93-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="45c93-105">Uma opção é criar uma conexão usando `System.Data.SqlClient.SqlConnection`, especificar uma cadeia de conexão que aponta para o servidor local e abrir a conexão.</span><span class="sxs-lookup"><span data-stu-id="45c93-105">One option is to create a connection using `System.Data.SqlClient.SqlConnection`, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="45c93-106">Isso exige a especificação de credenciais para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="45c93-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="45c93-107">A conexão está em uma sessão do banco de dados diferente do procedimento armazenado ou da função, pode ter opções `SET` diferentes, está em uma transação separada, não vê suas tabelas temporárias e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="45c93-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="45c93-108">Se código da função ou do procedimento armazenado gerenciado estiver em execução no processo do SQL Server, isso ocorrerá porque alguém se conectou a esse servidor e executou uma instrução SQL para invocá-lo.</span><span class="sxs-lookup"><span data-stu-id="45c93-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="45c93-109">Provavelmente, você deseja que o procedimento armazenado ou a função seja executado no contexto dessa conexão, juntamente com sua transação, opções `SET` e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="45c93-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="45c93-110">Isto é chamado de conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="45c93-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="45c93-111">A conexão de contexto permite executar instruções Transact-SQL no mesmo contexto em que seu código foi invocado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="45c93-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="45c93-112">Para obter a conexão de contexto, use a palavra-chave de cadeia de conexão "context connection", como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="45c93-112">In order to obtain the context connection, you must use the "context connection" connection string keyword, as in the example below:</span></span>  
  
 <span data-ttu-id="45c93-113">[C#]</span><span class="sxs-lookup"><span data-stu-id="45c93-113">[C#]</span></span>  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 <span data-ttu-id="45c93-114">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="45c93-114">[Visual Basic]</span></span>  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="45c93-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="45c93-115">In This Section</span></span>  
 [<span data-ttu-id="45c93-116">Regular vs. Conexões de contexto</span><span class="sxs-lookup"><span data-stu-id="45c93-116">Regular vs. Context Connections</span></span>](context-connections-vs-regular-connections.md)  
 <span data-ttu-id="45c93-117">Descreve as diferenças entre conexões normais e de contexto.</span><span class="sxs-lookup"><span data-stu-id="45c93-117">Describes the differences between regular and context connections.</span></span>  
  
 [<span data-ttu-id="45c93-118">Restrições em conexões comuns e de contexto</span><span class="sxs-lookup"><span data-stu-id="45c93-118">Restrictions on Regular and Context Connections</span></span>](context-connections-and-regular-connections-restrictions.md)  
 <span data-ttu-id="45c93-119">Descreve as restrições em conexões normais e de contexto.</span><span class="sxs-lookup"><span data-stu-id="45c93-119">Describes the restrictions on regular and context connections.</span></span>  
  
  
