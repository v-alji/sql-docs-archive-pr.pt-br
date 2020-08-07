---
title: Escrever instruções Transact-SQL internacionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- writing international statements
- Transact-SQL international considerations
- international considerations [SQL Server], Transact-SQL
- Database Engine international considerations [SQL Server], Transact-SQL
- statements [SQL Server], international
- database international considerations [SQL Server], Transact-SQL
- dates [SQL Server], international considerations
ms.assetid: f0b10fee-27f7-45fe-aece-ccc3f63bdcdb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1888d1045e43e0a9839fd76a21c51500af63539a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583634"
---
# <a name="write-international-transact-sql-statements"></a><span data-ttu-id="5be25-102">Gravar instruções Transact-SQL internacionais</span><span class="sxs-lookup"><span data-stu-id="5be25-102">Write International Transact-SQL Statements</span></span>
  <span data-ttu-id="5be25-103">Os bancos de dados e aplicativos de bancos de dados que usam instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] serão mais portáteis de um idioma para outro, ou darão suporte a vários idiomas, se as diretrizes a seguir forem cumpridas.</span><span class="sxs-lookup"><span data-stu-id="5be25-103">Databases and database applications that use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements will become more portable from one language to another, or will support multiple languages, if the following guidelines are followed:</span></span>  
  
-   <span data-ttu-id="5be25-104">Substitua todos os usos do `char`, `varchar` e tipos de dados `text` por `nchar`, `nvarchar` e `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="5be25-104">Replace all uses of the `char`, `varchar`, and `text` data types with `nchar`, `nvarchar`, and `nvarchar(max)`.</span></span> <span data-ttu-id="5be25-105">Fazendo isto, você não deve considerar assuntos relacionados à conversão de página de código.</span><span class="sxs-lookup"><span data-stu-id="5be25-105">By doing this, you do not have to consider code page conversion issues.</span></span> <span data-ttu-id="5be25-106">Para obter mais informações, consulte [Suporte a ordenações e a Unicode](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="5be25-106">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="5be25-107">Ao executar comparações e operações de mês e dia da semana, use as partes de data numérica em vez de cadeias de caracteres de nomes.</span><span class="sxs-lookup"><span data-stu-id="5be25-107">When you perform month and day-of-week comparisons and operations, use the numeric date parts instead of the name strings.</span></span> <span data-ttu-id="5be25-108">Configurações de linguagem diferentes retornam nomes diferentes para os meses e dias de semana.</span><span class="sxs-lookup"><span data-stu-id="5be25-108">Different language settings return different names for the months and weekdays.</span></span> <span data-ttu-id="5be25-109">Por exemplo, DATENAME(MONTH,GETDATE()) retorna May quando o idioma está definido como inglês dos EUA, retorna Mai quando o idioma é definido como alemão e retorna mai quando o idioma é definido como francês.</span><span class="sxs-lookup"><span data-stu-id="5be25-109">For example, DATENAME(MONTH,GETDATE()) returns May when the language is set to U.S. English, returns Mai when the language is set to German, and returns mai when the language is set to French.</span></span> <span data-ttu-id="5be25-110">No lugar, use uma função como DATEPART que usa o número do mês ao invés do nome.</span><span class="sxs-lookup"><span data-stu-id="5be25-110">Instead, use a function such as DATEPART that uses the number of the month instead of the name.</span></span> <span data-ttu-id="5be25-111">Use os nomes DATEPART quando for construir conjuntos de resultados a serem exibidos a um usuário, pois os nomes de datas geralmente são mais significativos que uma representação numérica.</span><span class="sxs-lookup"><span data-stu-id="5be25-111">Use the DATEPART names when you build result sets to be displayed to a user, because the date names are frequently more meaningful than a numeric representation.</span></span> <span data-ttu-id="5be25-112">Porém, não codifique qualquer lógica que dependa dos nomes exibidos sendo modificados em um idioma específico.</span><span class="sxs-lookup"><span data-stu-id="5be25-112">However, do not code any logic that depends on the displayed names being from a specific language.</span></span>  
  
-   <span data-ttu-id="5be25-113">Quando especificar datas em comparações ou para entradas nas instruções INSERT ou UPDATE, use as constantes que são interpretadas da mesma maneira de todas as definições de linguagem:</span><span class="sxs-lookup"><span data-stu-id="5be25-113">When you specify dates in comparisons or for input to INSERT or UPDATE statements, use constants that are interpreted the same way for all language settings:</span></span>  
  
    -   <span data-ttu-id="5be25-114">Os aplicativos ODBC, ADO e OLE DB devem usar as cláusulas de fuga ODBC timestamp, data e hora para:</span><span class="sxs-lookup"><span data-stu-id="5be25-114">ADO, OLE DB, and ODBC applications should use the ODBC timestamp, date, and time escape clauses of:</span></span>  
  
         <span data-ttu-id="5be25-115">**{TS '** yyyy **-** _mm_ **-** _DDHH_**:**_mm_**:**_SS_[**.** _FFF_] **'}** Como: **{TS '** 1998 **-** 09 **-** 24 10 **:** 02 **:** 20 **'}**</span><span class="sxs-lookup"><span data-stu-id="5be25-115">**{ ts'** yyyy**-**_mm_**-**_ddhh_**:**_mm_**:**_ss_[**.**_fff_] **'}** such as: **{ ts'** 1998**-** 09**-** 24 10 **:** 02 **:** 20 **' }**</span></span>  
  
         <span data-ttu-id="5be25-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** como: **{ d'** 1998**-** 09**-** 24 **'}**</span><span class="sxs-lookup"><span data-stu-id="5be25-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** such as: **{ d'** 1998**-** 09**-** 24 **'}**</span></span>  
  
         <span data-ttu-id="5be25-117">**{T'** _hh_ **:** _mm_ **:** _SS_ **'}** como: **{T'** 10:02:20 **'}**</span><span class="sxs-lookup"><span data-stu-id="5be25-117">**{ t'** _hh_ **:** _mm_ **:** _ss_ **'}** such as: **{ t'** 10:02:20 **'}**</span></span>  
  
    -   <span data-ttu-id="5be25-118">Os aplicativos que usam outras APIs ou scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , procedimentos armazenados e gatilhos, devem usar as sequências numéricas de não separadas.</span><span class="sxs-lookup"><span data-stu-id="5be25-118">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers, should use the unseparated numeric strings.</span></span> <span data-ttu-id="5be25-119">Por exemplo, *yyyymmdd* como 19980924.</span><span class="sxs-lookup"><span data-stu-id="5be25-119">For example, *yyyymmdd* as 19980924.</span></span>  
  
    -   <span data-ttu-id="5be25-120">Os aplicativos que usam outras APIs, ou [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, procedimentos armazenados e gatilhos devem usar a instrução Convert com um parâmetro de estilo explícito para todas as conversões entre os tipos de dados `time` , `date` , `smalldate` , `datetime` , **datetime2** `datetimeoffset` e tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5be25-120">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers should use the CONVERT statement with an explicit style parameter for all conversions between the `time`, `date`, `smalldate`, `datetime`, **datetime2**, and `datetimeoffset` data types and character string data types.</span></span> <span data-ttu-id="5be25-121">Por exemplo, a instrução a seguir é interpretada da mesma maneira para todas configurações de conexão de formato de data ou de linguagem:</span><span class="sxs-lookup"><span data-stu-id="5be25-121">For example, the following statement is interpreted in the same way for all language or date format connection settings:</span></span>  
  
        ```  
        SELECT *  
        FROM AdventureWorks2012.Sales.SalesOrderHeader  
        WHERE OrderDate = CONVERT(DATETIME, '20060719', 101)  
        ```  
  
         <span data-ttu-id="5be25-122">Para obter mais informações, veja [CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5be25-122">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
  
