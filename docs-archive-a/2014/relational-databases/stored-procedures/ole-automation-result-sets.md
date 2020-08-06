---
title: Conjuntos de resultados de automação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- data types [SQL Server], OLE Automation
- two-dimensional arrays
- one-dimensional arrays
- result sets [SQL Server], OLE Automation
- OLE Automation [SQL Server], result sets
- arrays [SQL Server]
ms.assetid: b2f99e33-2303-427c-94b9-9d55f8e2a6ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7c9bdc4d51d989db2d4d676b29e0824c0e5b59a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584111"
---
# <a name="ole-automation-result-sets"></a><span data-ttu-id="4f8ca-102">Conjuntos de resultado de automação OLE</span><span class="sxs-lookup"><span data-stu-id="4f8ca-102">OLE Automation Result Sets</span></span>
  <span data-ttu-id="4f8ca-103">Se uma propriedade de automação OLE ou método retorna dados em uma matriz com uma ou duas dimensões, a matriz é retornada ao cliente como um conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="4f8ca-103">If an OLE Automation property or method returns data in an array with one or two dimensions, the array is returned to the client as a result set:</span></span>  
  
-   <span data-ttu-id="4f8ca-104">Uma matriz unidimensional é retornada ao cliente como um conjunto de resultados de uma linha, com tantas colunas quanto houver elementos na matriz.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-104">A one-dimensional array is returned to the client as a single-row result set with as many columns as there are elements in the array.</span></span> <span data-ttu-id="4f8ca-105">Por exemplo, uma matriz (10) é retornada como uma única linha de 10 colunas.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-105">For example, an array(10) is returned as a single row of 10 columns.</span></span>  
  
-   <span data-ttu-id="4f8ca-106">Uma matriz bidimensional é retornada ao cliente como um conjunto de resultados com tantas colunas quanto houver elementos na primeira dimensão da matriz e com tantas linhas quanto houver elementos na segunda dimensão da matriz.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-106">A two-dimensional array is returned to the client as a result set with as many columns as there are elements in the first dimension of the array and with as many rows as there are elements in the second dimension of the array.</span></span> <span data-ttu-id="4f8ca-107">Por exemplo, uma matriz (2,3) é retornada como 2 colunas em 3 linhas.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-107">For example, an array(2,3) is returned as 2 columns in 3 rows.</span></span>  
  
 <span data-ttu-id="4f8ca-108">Quando o valor de retorno de uma propriedade ou o valor de retorno de um método for uma matriz, sp_OAGetProperty ou sp_OAMethod retornará um conjunto de resultados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-108">When a property return value or method return value is an array, sp_OAGetProperty or sp_OAMethod returns a result set to the client.</span></span> <span data-ttu-id="4f8ca-109">(Os parâmetros de saída de método não podem ser matrizes.) Esses procedimentos examinam todos os valores de dados na matriz para determinar os tipos de dados apropriados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e os tamanhos dos dados a serem usados para cada coluna no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-109">(Method output parameters cannot be arrays.) These procedures scan all the data values in the array to determine the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and data lengths to use for each column in the result set.</span></span> <span data-ttu-id="4f8ca-110">Para uma coluna específica, esses procedimentos usam o tipo de dados e o tamanho necessários para representar todos os valores de dados nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-110">For a particular column, these procedures use the data type and length required to represent all data values in that column.</span></span>  
  
 <span data-ttu-id="4f8ca-111">Quando todos os valores de dados em uma coluna compartilharem o mesmo tipo de dados, esse tipo de dados será usado para a coluna inteira.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-111">When all data values in a column share the same data type, that data type is used for the whole column.</span></span> <span data-ttu-id="4f8ca-112">Quando os valores de dados em uma coluna são de tipos de dados diferentes, o tipo de dados da coluna inteira é escolhido com base na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-112">When data values in a column are different data types, the data type of the whole column is chosen based on the following table.</span></span> <span data-ttu-id="4f8ca-113">Para usar a tabela a seguir, localize um tipo de dados ao longo do eixo da linha esquerda e um segundo tipo de dados ao longo do eixo da coluna superior.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-113">To use the following table, find one data type along the left row axis and a second data type along the top column axis.</span></span> <span data-ttu-id="4f8ca-114">A interseção da linha com a coluna descreve o tipo de dados da coluna do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4f8ca-114">The intersection of the row and column describes the data type of the result set column.</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
||`int`|`float`|`money`|`datetime`|`varchar`|`nvarchar`|  
|`int`|`int`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`float`|`float`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`money`|`money`|`money`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`datetime`|`varchar`|`varchar`|`varchar`|`datetime`|`varchar`|`nvarchar`|  
|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`nvarchar`|  
|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|  
  
## <a name="related-content"></a><span data-ttu-id="4f8ca-115">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="4f8ca-115">Related Content</span></span>  
 [<span data-ttu-id="4f8ca-116">Procedimentos armazenados de Automação OLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8ca-116">OLE Automation Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql)  
  
 [<span data-ttu-id="4f8ca-117">Opção de configuração de servidor Ole Automation Procedures</span><span class="sxs-lookup"><span data-stu-id="4f8ca-117">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  
