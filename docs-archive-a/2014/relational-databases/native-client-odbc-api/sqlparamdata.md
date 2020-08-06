---
title: SQLParamData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: rothja
ms.author: jroth
ms.openlocfilehash: a4e0e8b31a65f28ce83e0d114231bdedd7a35a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583009"
---
# <a name="sqlparamdata"></a><span data-ttu-id="e16a6-102">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="e16a6-102">SQLParamData</span></span>
  <span data-ttu-id="e16a6-103">Quando SQLParamData retorna o *ValuePtrPtr* associado a um parâmetro com valor de tabela, o aplicativo deve chamar SQLPutData com *StrLen_or_Ind*.</span><span class="sxs-lookup"><span data-stu-id="e16a6-103">When SQLParamData returns the *ValuePtrPtr* associated with a table-valued parameter, the application should call SQLPutData with *StrLen_Or_Ind*.</span></span> <span data-ttu-id="e16a6-104">Se *StrLen_Or_Ind* tiver um valor maior que 0, significará que o aplicativo está pronto para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client coletar dados de parâmetro para a próxima linha de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="e16a6-104">If *StrLen_Or_Ind* has a value greater than 0, it means that the application is ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to gather parameter data for the next table-valued parameter row.</span></span> <span data-ttu-id="e16a6-105">Se *StrLen_Or_Ind* tiver um valor 0, significará que não há mais linhas de dados para o parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="e16a6-105">If *StrLen_Or_Ind* has a value of 0, it means there are no more rows of data for the table-valued parameter.</span></span> <span data-ttu-id="e16a6-106">Para obter mais informações, consulte [associação e transferência de dados de parâmetros com valor de tabela e valores de coluna](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="e16a6-106">For more information, see [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="e16a6-107">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="e16a6-107">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16a6-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e16a6-108">See Also</span></span>  
 <span data-ttu-id="e16a6-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span><span class="sxs-lookup"><span data-stu-id="e16a6-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span></span>  
 [<span data-ttu-id="e16a6-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="e16a6-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
