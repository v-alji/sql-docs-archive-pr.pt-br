---
title: Usando cursores do servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, cursors
- cursors [ODBC], server cursors
- ODBC cursors, server cursors
- server cursors [SQL Server]
ms.assetid: 8a6d99b7-10b8-4474-8639-4914b25ba170
author: rothja
ms.author: jroth
ms.openlocfilehash: e596af3c46849313d813ce2d7f1dab2a7425c090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572069"
---
# <a name="using-server-cursors"></a><span data-ttu-id="85fad-102">Usando cursores de servidor</span><span class="sxs-lookup"><span data-stu-id="85fad-102">Using Server Cursors</span></span>
  <span data-ttu-id="85fad-103">Se um aplicativo ODBC definir qualquer um dos atributos de cursor do ODBC para qualquer coisa diferente dos padrões, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client solicitará que o servidor implemente um cursor do servidor de API do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="85fad-103">If an ODBC application sets any of the ODBC cursor attributes to anything other than the defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver requests the server to implement an API server cursor of the same type.</span></span> <span data-ttu-id="85fad-104">O uso de cursores de servidor de API libera memória no cliente e pode reduzir significativamente o tráfego de rede entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="85fad-104">Using API server cursors frees memory on the client and can significantly reduce network traffic between the client and server.</span></span>  
  
 <span data-ttu-id="85fad-105">Uma desvantagem potencial de cursores de servidor de API é que atualmente eles não dão suporte a todas as instruções SQL.</span><span class="sxs-lookup"><span data-stu-id="85fad-105">A potential drawback of API server cursors is that they currently do not support all SQL statements.</span></span> <span data-ttu-id="85fad-106">Os cursores de servidor de API não podem ser usados para executar:</span><span class="sxs-lookup"><span data-stu-id="85fad-106">API server cursors cannot be used to execute:</span></span>  
  
-   <span data-ttu-id="85fad-107">Lotes ou procedimentos armazenados que retornam vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="85fad-107">Batches or stored procedures that return multiple result sets.</span></span>  
  
-   <span data-ttu-id="85fad-108">Instruções SELECT que contêm cláusulas COMPUTE, COMPUTE BY, FOR BROWSE ou INTO.</span><span class="sxs-lookup"><span data-stu-id="85fad-108">SELECT statements that contain COMPUTE, COMPUTE BY, FOR BROWSE, or INTO clauses.</span></span>  
  
-   <span data-ttu-id="85fad-109">Uma instrução EXECUTE que faz referência a um procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="85fad-109">An EXECUTE statement referencing a remote stored procedure.</span></span>  
  
 <span data-ttu-id="85fad-110">Em caso de conexão a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a execução de uma instrução com essas características usando um cursor de servidor faz com que o cursor seja convertido em um conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="85fad-110">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], executing a statement with these characteristics using a server cursor causes the cursor being converted to a default result set.</span></span> <span data-ttu-id="85fad-111">Em caso de conexão a versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], é gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="85fad-111">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it causes an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fad-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85fad-112">See Also</span></span>  
 [<span data-ttu-id="85fad-113">Como os cursores são implementados</span><span class="sxs-lookup"><span data-stu-id="85fad-113">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
