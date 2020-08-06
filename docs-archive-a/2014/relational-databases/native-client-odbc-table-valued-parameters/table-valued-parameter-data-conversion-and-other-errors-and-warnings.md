---
title: Conversão de dados de parâmetro com valor de tabela e outros erros e avisos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), data conversion
- table-valued parameters (ODBC), error messages
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
author: rothja
ms.author: jroth
ms.openlocfilehash: 45b9ba7f91b54548e096bbe47da6e01ba562f59d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569399"
---
# <a name="table-valued-parameter-data-conversion-and-other-errors-and-warnings"></a><span data-ttu-id="a761d-102">Conversão de dados de parâmetros com valor de tabela e outros erros e avisos</span><span class="sxs-lookup"><span data-stu-id="a761d-102">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>
  <span data-ttu-id="a761d-103">Valores da coluna de parâmetros com valor de tabela podem ser convertidos entre tipos de dados de cliente e servidor da mesma forma que outros valores de parâmetro e coluna.</span><span class="sxs-lookup"><span data-stu-id="a761d-103">Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values.</span></span> <span data-ttu-id="a761d-104">Mas como um parâmetro com valor de tabela pode conter várias colunas e várias linhas, é importante conseguir identificar o valor real quando o erro ocorrer.</span><span class="sxs-lookup"><span data-stu-id="a761d-104">But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.</span></span>  
  
 <span data-ttu-id="a761d-105">Quando um erro ou aviso é detectado em uma coluna de parâmetro com valor de tabela, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client gerará um registro diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a761d-105">When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record.</span></span> <span data-ttu-id="a761d-106">A mensagem de erro conterá o número de parâmetro com valor de tabela, assim como o número da linha e o ordinal da coluna.</span><span class="sxs-lookup"><span data-stu-id="a761d-106">The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number.</span></span> <span data-ttu-id="a761d-107">Um aplicativo também pode usar os campos de diagnóstico SQL_DIAG_SS_TABLE_COLUMN_NUMBER e SQL_DIAG_SS_TABLE_ROW_NUMBER dentro dos registros de diagnóstico para determinar quais valores são associados a erros e avisos.</span><span class="sxs-lookup"><span data-stu-id="a761d-107">An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings.</span></span> <span data-ttu-id="a761d-108">Estes campos de diagnóstico estão disponíveis no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="a761d-108">These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span>  
  
 <span data-ttu-id="a761d-109">Os componentes de mensagem e SQLSTATE dos registros de diagnóstico estarão em conformidade com o comportamento de ODBC existente em todos os níveis.</span><span class="sxs-lookup"><span data-stu-id="a761d-109">The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects.</span></span> <span data-ttu-id="a761d-110">Ou seja, exceto para as informações de identificação de parâmetro, linha e coluna, as mensagens de erro têm os mesmos valores para parâmetros com valor de tabela como seriam para parâmetros com valor não tabela.</span><span class="sxs-lookup"><span data-stu-id="a761d-110">That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non-table-valued parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a761d-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a761d-111">See Also</span></span>  
 [<span data-ttu-id="a761d-112">Parâmetros com valor de tabela &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a761d-112">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
