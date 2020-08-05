---
title: Detalhes de programação do cursor (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- ODBC cursors, programming
- cursors [ODBC], programming
ms.assetid: 6bae29c4-7f49-419c-8712-90db734f992e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4108e195c16d321578a70852dd990f4f8d658832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572065"
---
# <a name="cursor-programming-details-odbc"></a><span data-ttu-id="94149-102">Detalhes da programação de cursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="94149-102">Cursor Programming Details (ODBC)</span></span>
  <span data-ttu-id="94149-103">A escolha do tipo de cursor correto pode melhorar o desempenho do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94149-103">Choosing the correct cursor type can improve application performance.</span></span> <span data-ttu-id="94149-104">Em determinadas condições, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pode converter um tipo de cursor implicitamente quando você executa uma instrução SQL para a qual o tipo de cursos solicitado não dá suporte.</span><span class="sxs-lookup"><span data-stu-id="94149-104">Under certain conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may implicitly convert a cursor type when you execute an SQL statement that is not supported by the cursor type you requested.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94149-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="94149-105">In This Section</span></span>  
  
-   [<span data-ttu-id="94149-106">Conversões de cursor implícitas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="94149-106">Implicit Cursor Conversions &#40;ODBC&#41;</span></span>](implicit-cursor-conversions-odbc.md)  
  
-   [<span data-ttu-id="94149-107">Usando a opção Autofetch com cursores ODBC</span><span class="sxs-lookup"><span data-stu-id="94149-107">Using Autofetch with ODBC Cursors</span></span>](using-autofetch-with-odbc-cursors.md)  
  
-   [<span data-ttu-id="94149-108">Cursores rápidos somente de avanço &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="94149-108">Fast Forward-Only Cursors &#40;ODBC&#41;</span></span>](fast-forward-only-cursors-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="94149-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94149-109">See Also</span></span>  
 [<span data-ttu-id="94149-110">Usando cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="94149-110">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
