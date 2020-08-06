---
title: REPLACENULL (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 70db7832-b5a0-4db5-a8ad-42ad8630d8e8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f10bb6ef6102076fe7b1cc236461e2358ad96372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681026"
---
# <a name="replacenull-ssis-expression"></a><span data-ttu-id="7192c-102">REPLACENULL (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="7192c-102">REPLACENULL (SSIS Expression)</span></span>
  <span data-ttu-id="7192c-103">Retornará o valor do parâmetro da segunda expressão se o valor do parâmetro da primeira expressão for NULL; caso contrário, retornará o valor da primeira expressão.</span><span class="sxs-lookup"><span data-stu-id="7192c-103">Returns the value of second expression parameter if the value of first expression parameter is NULL; otherwise, returns the value of first expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7192c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7192c-104">Syntax</span></span>  
  
```vb  
REPLACENULL(expression 1,expression 2)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7192c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7192c-105">Arguments</span></span>  
 <span data-ttu-id="7192c-106">*expressão 1*</span><span class="sxs-lookup"><span data-stu-id="7192c-106">*expression 1*</span></span>  
 <span data-ttu-id="7192c-107">O resultado desta expressão é verificado em relação a NULL.</span><span class="sxs-lookup"><span data-stu-id="7192c-107">The result of this expression is checked against NULL.</span></span>  
  
 <span data-ttu-id="7192c-108">*expressão 2*</span><span class="sxs-lookup"><span data-stu-id="7192c-108">*expression 2*</span></span>  
 <span data-ttu-id="7192c-109">O resultado desta expressão será retornado se a primeira expressão avaliar como NULL.</span><span class="sxs-lookup"><span data-stu-id="7192c-109">The result of this expression is returned if the first expression evaluates to NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7192c-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="7192c-110">Result Types</span></span>  
 <span data-ttu-id="7192c-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7192c-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7192c-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="7192c-112">Remarks</span></span>  
  
-   <span data-ttu-id="7192c-113">O comprimento de *expression 2* pode ser zero.</span><span class="sxs-lookup"><span data-stu-id="7192c-113">The length of *expression 2* may be zero.</span></span>  
  
-   <span data-ttu-id="7192c-114">REPLACENULL retornará um resultado nulo se qualquer argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="7192c-114">REPLACENULL returns a null result if any argument is null.</span></span>  
  
-   <span data-ttu-id="7192c-115">Não há suporte para colunas de BLOB (DT_TEXT, DT_NTEXT, DT_IMAGE) para nenhum parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7192c-115">BLOB columns (DT_TEXT, DT_NTEXT, DT_IMAGE) are not supported for either parameter.</span></span>  
  
-   <span data-ttu-id="7192c-116">É esperado que as duas expressões tenham o mesmo tipo de retorno.</span><span class="sxs-lookup"><span data-stu-id="7192c-116">The two expressions are expected to have the same return type.</span></span> <span data-ttu-id="7192c-117">Se isso não ocorrer, a função tentará converter a 2ª expressão para o tipo de retorno da 1ª, que pode resultar em erro se os tipos de dados forem incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="7192c-117">If they do not, the function attempts to cast the 2nd expression to the return type of the 1st expression, which may result in an error if the data types are incompatible.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7192c-118">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="7192c-118">Expression Examples</span></span>  
 <span data-ttu-id="7192c-119">O exemplo a seguir substitui os valores nulos em uma coluna de banco de dados por uma cadeia de caracteres (1900-01-01).</span><span class="sxs-lookup"><span data-stu-id="7192c-119">The following example replaces any NULL value in a database column with a string (1900-01-01).</span></span> <span data-ttu-id="7192c-120">Esta função é usada principalmente em padrões comuns de Coluna derivada onde você deseja substituir os valores NULL por qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="7192c-120">This function is especially used in common Derived Column patterns where you want to replace NULL values with something else.</span></span>  
  
```  
REPLACENULL(MyColumn, "1900-01-01")  
```  
  
> [!NOTE]  
>  <span data-ttu-id="7192c-121">O exemplo a seguir mostra como isso foi feito no [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7192c-121">The following example shows how it was done in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span></span>  
  
```  
(DT_DBTIMESTAMP) (ISNULL(MyColumn) ? "1900-01-01" : MyColumn)   
```  
  
  
