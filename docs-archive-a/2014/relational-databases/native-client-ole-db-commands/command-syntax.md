---
title: Sintaxe de comando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
author: rothja
ms.author: jroth
ms.openlocfilehash: da5ddb75a5c6fc10db031707b7d97ead71363e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685600"
---
# <a name="command-syntax"></a><span data-ttu-id="c5b2b-102">Sintaxe de comando</span><span class="sxs-lookup"><span data-stu-id="c5b2b-102">Command Syntax</span></span>
  <span data-ttu-id="c5b2b-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo reconhece a sintaxe de comando especificada pela macro DBGUID_SQL.</span><span class="sxs-lookup"><span data-stu-id="c5b2b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes command syntax specified by the DBGUID_SQL macro.</span></span> <span data-ttu-id="c5b2b-104">Para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, o especificador indica que um mistura de ODBC SQL, ISO e [!INCLUDE[tsql](../../includes/tsql-md.md)] é uma sintaxe válida.</span><span class="sxs-lookup"><span data-stu-id="c5b2b-104">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the specifier indicates that an amalgam of ODBC SQL, ISO, and [!INCLUDE[tsql](../../includes/tsql-md.md)] is valid syntax.</span></span> <span data-ttu-id="c5b2b-105">Por exemplo, a seguinte instrução SQL usa uma sequência de escape do ODBC SQL para especificar a função de cadeia de caracteres LCASE:</span><span class="sxs-lookup"><span data-stu-id="c5b2b-105">For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 <span data-ttu-id="c5b2b-106">LCASE retorna uma cadeia de caracteres, convertendo todos os caracteres em maiúscula aos seus equivalentes em minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c5b2b-106">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents.</span></span> <span data-ttu-id="c5b2b-107">A função LOWER de cadeia de caracteres ISO executa a mesma operação, assim a seguinte instrução SQL é uma equivalente ISO para a instrução ODBC apresentada acima:</span><span class="sxs-lookup"><span data-stu-id="c5b2b-107">The ISO string function LOWER performs the same operation, so the following SQL statement is a ISO equivalent to the ODBC statement presented above:</span></span>  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 <span data-ttu-id="c5b2b-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo processa qualquer forma da instrução com êxito quando especificado como texto para um comando.</span><span class="sxs-lookup"><span data-stu-id="c5b2b-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider processes either form of the statement successfully when specified as text for a command.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="c5b2b-109">Procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="c5b2b-109">Stored Procedures</span></span>  
 <span data-ttu-id="c5b2b-110">Ao executar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedimento armazenado usando um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comando de provedor de OLE DB de cliente nativo, use a sequência de escape de chamada ODBC no texto do comando.</span><span class="sxs-lookup"><span data-stu-id="c5b2b-110">When executing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider command, use the ODBC CALL escape sequence in the command text.</span></span> <span data-ttu-id="c5b2b-111">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo usa o mecanismo de chamada de procedimento remoto do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para otimizar o processamento de comandos.</span><span class="sxs-lookup"><span data-stu-id="c5b2b-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider then uses the remote procedure call mechanism of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize command processing.</span></span> <span data-ttu-id="c5b2b-112">Por exemplo, a seguinte instrução SQL do ODBC é o texto de comando preferido à forma do [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c5b2b-112">For example, the following ODBC SQL statement is preferred command text over the [!INCLUDE[tsql](../../includes/tsql-md.md)] form:</span></span>  
  
-   <span data-ttu-id="c5b2b-113">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="c5b2b-113">ODBC SQL</span></span>  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   <span data-ttu-id="c5b2b-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5b2b-114">Transact-SQL</span></span>  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5b2b-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5b2b-115">See Also</span></span>  
 [<span data-ttu-id="c5b2b-116">Comandos</span><span class="sxs-lookup"><span data-stu-id="c5b2b-116">Commands</span></span>](commands.md)  
  
  
