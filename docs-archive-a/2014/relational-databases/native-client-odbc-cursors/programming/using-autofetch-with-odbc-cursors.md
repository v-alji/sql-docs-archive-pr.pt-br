---
title: Usando a busca prévia com cursores ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
author: rothja
ms.author: jroth
ms.openlocfilehash: e3d9374cf9ceab4a7e73cc0059783486f2bf9c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576345"
---
# <a name="using-autofetch-with-odbc-cursors"></a><span data-ttu-id="0551d-102">Usando a opção Autofetch com cursores ODBC</span><span class="sxs-lookup"><span data-stu-id="0551d-102">Using Autofetch with ODBC Cursors</span></span>
  <span data-ttu-id="0551d-103">Quando conectado a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte a uma opção de AutoBusca ao usar qualquer tipo de cursor do servidor.</span><span class="sxs-lookup"><span data-stu-id="0551d-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports an autofetch option when using any server cursor type.</span></span> <span data-ttu-id="0551d-104">Com a busca prévia, a função **SQLExecute** ou **SQLExecDirect** que abre o cursor também tem uma função implícita de [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST).</span><span class="sxs-lookup"><span data-stu-id="0551d-104">With autofetch, the **SQLExecute** or **SQLExecDirect** function that opens the cursor also has an implicit [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) function.</span></span> <span data-ttu-id="0551d-105">As linhas que formam o primeiro conjunto de linhas são retornadas para as variáveis associadas de aplicativo como parte da execução da instrução, evitando outra viagem de ida e volta pela rede até o servidor.</span><span class="sxs-lookup"><span data-stu-id="0551d-105">The rows comprising the first rowset are returned to the bound application variables as part of the statement execution, saving another roundtrip across the network to the server.</span></span> <span data-ttu-id="0551d-106">Não há suporte para [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) quando a opção de AutoBusca está habilitada; as colunas do conjunto de resultados devem estar associadas a variáveis de programa.</span><span class="sxs-lookup"><span data-stu-id="0551d-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported when the autofetch option is enabled; the result set columns must be bound to program variables.</span></span>  
  
 <span data-ttu-id="0551d-107">Os aplicativos solicitam autofetch definindo o atributo de instrução SQL_SOPT_SS_CURSOR_OPTIONS específico de driver como SQL_CO_AF.</span><span class="sxs-lookup"><span data-stu-id="0551d-107">Applications request autofetch by setting the driver-specific SQL_SOPT_SS_CURSOR_OPTIONS statement attribute to SQL_CO_AF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0551d-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0551d-108">See Also</span></span>  
 [<span data-ttu-id="0551d-109">Detalhes de programação do cursor &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="0551d-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
