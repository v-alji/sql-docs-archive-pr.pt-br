---
title: Comandos que geram resultados de vários conjuntos de linhas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678732"
---
# <a name="commands-generating-multiple-rowset-results"></a><span data-ttu-id="bc14a-102">Comandos que geram resultados de vários conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="bc14a-102">Commands Generating Multiple-Rowset Results</span></span>
  <span data-ttu-id="bc14a-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo pode retornar vários conjuntos de linhas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instruções.</span><span class="sxs-lookup"><span data-stu-id="bc14a-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can return multiple rowsets from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements.</span></span> <span data-ttu-id="bc14a-104">As instruções do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornam resultados de vários conjuntos de linhas nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="bc14a-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements return multiple-rowset results under the following conditions:</span></span>  
  
-   <span data-ttu-id="bc14a-105">Instruções SQL processadas em lotes são enviadas como um único comando.</span><span class="sxs-lookup"><span data-stu-id="bc14a-105">Batched SQL statements are submitted as a single command.</span></span>  
  
-   <span data-ttu-id="bc14a-106">Os procedimentos armazenados implementam um lote de instruções SQL.</span><span class="sxs-lookup"><span data-stu-id="bc14a-106">Stored procedures implement a batch of SQL statements.</span></span>  
  
## <a name="batches"></a><span data-ttu-id="bc14a-107">Lotes</span><span class="sxs-lookup"><span data-stu-id="bc14a-107">Batches</span></span>  
 <span data-ttu-id="bc14a-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo reconhece o caractere ponto e vírgula como um delimitador de lote para instruções SQL:</span><span class="sxs-lookup"><span data-stu-id="bc14a-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes the semicolon character as a batch delimiter for SQL statements:</span></span>  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 <span data-ttu-id="bc14a-109">Enviar várias instruções SQL em um único lote é mais eficiente do que executar cada instrução SQL separadamente.</span><span class="sxs-lookup"><span data-stu-id="bc14a-109">Sending multiple SQL statements in one batch is more efficient than executing each SQL statement separately.</span></span> <span data-ttu-id="bc14a-110">O envio de um lote reduz as viagens de ida e volta de rede do cliente para o servidor.</span><span class="sxs-lookup"><span data-stu-id="bc14a-110">Sending one batch reduces the network round trips from the client to the server.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="bc14a-111">Procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="bc14a-111">Stored Procedures</span></span>  
 <span data-ttu-id="bc14a-112">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna um conjunto de resultados para cada instrução em um procedimento armazenado, assim a maioria dos procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="bc14a-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for each statement in a stored procedure, so most [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return multiple result sets.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc14a-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bc14a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="bc14a-114">Usando IMultipleResults para processar vários conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="bc14a-114">Using IMultipleResults to Process Multiple Result Sets</span></span>](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc14a-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc14a-115">See Also</span></span>  
 [<span data-ttu-id="bc14a-116">Comandos</span><span class="sxs-lookup"><span data-stu-id="bc14a-116">Commands</span></span>](commands.md)  
  
  
