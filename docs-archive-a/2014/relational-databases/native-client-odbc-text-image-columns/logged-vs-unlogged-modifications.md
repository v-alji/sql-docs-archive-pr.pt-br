---
title: Modificações registradas em log versus não registradas | Microsoft Docs
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
- data types [ODBC], image
- data types [ODBC], text
- logged vs. nonlogged modifications [SQL Server Native Client]
- columns [ODBC]
- ODBC data types, image columns
- nonlogged vs. logged modifications
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 20aa5b27-4a2c-46e7-8356-beb0eebf4b7e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8768acc75d18ea2236f0e9280e5d0c805e688107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685616"
---
# <a name="logged-vs-unlogged-modifications"></a><span data-ttu-id="cfd05-102">Modificações registradas vs. não registradas</span><span class="sxs-lookup"><span data-stu-id="cfd05-102">Logged vs. Unlogged Modifications</span></span>
  <span data-ttu-id="cfd05-103">Um aplicativo pode solicitar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client não faça log de modificações de **Text**, **ntext**e **Image** .</span><span class="sxs-lookup"><span data-stu-id="cfd05-103">An application can request that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver not log **text**, **ntext**, and **image** modifications.</span></span> <span data-ttu-id="cfd05-104">No entanto, tome cuidado ao usar essa opção.</span><span class="sxs-lookup"><span data-stu-id="cfd05-104">Care should be used with this option, however.</span></span> <span data-ttu-id="cfd05-105">Ele deve ser usado somente para as situações em que os dados **Text**, **ntext**ou **Image** não são críticos e os proprietários de dados estão dispostos a compensar a capacidade de recuperar dados para um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="cfd05-105">It should be used only for those situations where the **text**, **ntext**, or **image** data is not critical and data owners are willing to trade off the ability to recover data for higher performance.</span></span>  
  
 <span data-ttu-id="cfd05-106">O registro em log de modificações de **Text**, **ntext**e **Image** é controlado chamando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) com o parâmetro de *atributo* definido como SQL_SOPT_SS_ TEXTPTR_LOGGING e *ValuePtr* definido como SQL_TL_ON ou SQL_TL_OFF.</span><span class="sxs-lookup"><span data-stu-id="cfd05-106">The logging of **text**, **ntext**, and **image** modifications is controlled by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with the *Attribute* parameter set to SQL_SOPT_SS_ TEXTPTR_LOGGING and *ValuePtr* set to either SQL_TL_ON or SQL_TL_OFF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd05-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cfd05-107">See Also</span></span>  
 [<span data-ttu-id="cfd05-108">Gerenciando colunas de texto e imagem</span><span class="sxs-lookup"><span data-stu-id="cfd05-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
