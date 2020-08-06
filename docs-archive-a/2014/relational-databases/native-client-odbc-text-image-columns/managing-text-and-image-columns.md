---
title: Gerenciando colunas de texto e imagem | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- data types [ODBC], mapping
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 7b543556-ff36-4d35-ac08-de96223d92cd
author: rothja
ms.author: jroth
ms.openlocfilehash: e9d7d5b0f48c68e8ac911f5e274c9afdb8cfe17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685613"
---
# <a name="managing-text-and-image-columns"></a><span data-ttu-id="ce4f5-102">Gerenciando colunas de texto e imagem</span><span class="sxs-lookup"><span data-stu-id="ce4f5-102">Managing Text and Image Columns</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="ce4f5-103">os dados **Text**, **ntext**e **Image** (também conhecidos como Long Data) são tipos de dados character ou Binary String que podem conter valores de dados muito grandes para se ajustarem às colunas **Char**, **varchar**, **Binary**ou **varbinary** .</span><span class="sxs-lookup"><span data-stu-id="ce4f5-103">**text**, **ntext**, and **image** data (also referred to as long data) are character or binary string data types that can hold data values too large to fit into **char**, **varchar**, **binary**, or **varbinary** columns.</span></span> <span data-ttu-id="ce4f5-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de dados **Text** é mapeado para o tipo de dados ODBC SQL_LONGVARCHAR; **ntext** mapeia para SQL_WLONGVARCHAR; e mapas de **imagem** para SQL_LONGVARBINARY.</span><span class="sxs-lookup"><span data-stu-id="ce4f5-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **text** data type maps to the ODBC SQL_LONGVARCHAR data type; **ntext** maps to SQL_WLONGVARCHAR; and **image** maps to SQL_LONGVARBINARY.</span></span> <span data-ttu-id="ce4f5-105">Alguns itens de dados, como documentos longos ou bitmaps grandes, podem ser muito grandes para serem armazenados na memória de forma aceitável.</span><span class="sxs-lookup"><span data-stu-id="ce4f5-105">Some data items, such as long documents or large bitmaps, may be too large to store reasonably in memory.</span></span> <span data-ttu-id="ce4f5-106">Para recuperar dados longos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] partes sequenciais, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client permite que um aplicativo chame [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span><span class="sxs-lookup"><span data-stu-id="ce4f5-106">To retrieve long data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sequential parts, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to call [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span></span> <span data-ttu-id="ce4f5-107">Para enviar dados longos em partes sequenciais, o aplicativo pode chamar [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="ce4f5-107">To send long data in sequential parts, the application can call [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span></span> <span data-ttu-id="ce4f5-108">Os parâmetros para os quais os dados são enviados no tempo de execução são conhecidos como parâmetros de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="ce4f5-108">Parameters for which data is sent at execution time are known as data-at-execution parameters.</span></span>  
  
 <span data-ttu-id="ce4f5-109">Um aplicativo pode realmente gravar ou recuperar qualquer tipo de dados (não apenas dados longos) com **SQLPutData** ou **SQLGetData**, embora apenas dados de **caracteres** e **binários** possam ser enviados ou recuperados em partes.</span><span class="sxs-lookup"><span data-stu-id="ce4f5-109">An application can actually write or retrieve any type of data (not just long data) with **SQLPutData** or **SQLGetData**, although only **character** and **binary** data can be sent or retrieved in parts.</span></span> <span data-ttu-id="ce4f5-110">No entanto, se os dados forem pequenos o suficiente para caber em um único buffer, geralmente não há motivo para usar **SQLPutData** ou **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="ce4f5-110">However, if the data is small enough to fit in a single buffer, there is generally no reason to use **SQLPutData** or **SQLGetData**.</span></span> <span data-ttu-id="ce4f5-111">É muito mais fácil associar o único buffer ao parâmetro ou à coluna.</span><span class="sxs-lookup"><span data-stu-id="ce4f5-111">It is much easier to bind the single buffer to the parameter or column.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce4f5-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ce4f5-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ce4f5-113">Colunas de texto e imagem associadas vs. não associadas</span><span class="sxs-lookup"><span data-stu-id="ce4f5-113">Bound vs. Unbound Text and Image Columns</span></span>](bound-vs-unbound-text-and-image-columns.md)  
  
-   [<span data-ttu-id="ce4f5-114">Modificações registradas vs. não registradas</span><span class="sxs-lookup"><span data-stu-id="ce4f5-114">Logged vs. Unlogged Modifications</span></span>](logged-vs-unlogged-modifications.md)  
  
-   [<span data-ttu-id="ce4f5-115">Dados em execução e colunas Text, ntext ou Image</span><span class="sxs-lookup"><span data-stu-id="ce4f5-115">Data-at-Execution and Text, ntext, or Image Columns</span></span>](data-at-execution-and-text-ntext-or-image-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce4f5-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce4f5-116">See Also</span></span>  
 [<span data-ttu-id="ce4f5-117">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4f5-117">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
