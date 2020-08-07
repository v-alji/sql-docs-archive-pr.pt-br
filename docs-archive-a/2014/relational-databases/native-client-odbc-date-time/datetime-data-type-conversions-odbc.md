---
title: conversões de tipo de dados DateTime (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC]
- bindings [ODBC]
- ODBC, bindings and conversions
ms.assetid: 66b9d282-c88d-40e5-93c2-fd5499a74458
author: rothja
ms.author: jroth
ms.openlocfilehash: 142e4388cb87055ddbc6faa7d5b1a92a627738c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576336"
---
# <a name="datetime-data-type-conversions-odbc"></a><span data-ttu-id="9cf71-102">Conversões do tipo de dados datetime (ODBC)</span><span class="sxs-lookup"><span data-stu-id="9cf71-102">datetime Data Type Conversions (ODBC)</span></span>
  <span data-ttu-id="9cf71-103">As conversões a seguir já estão definidas pelo ODBC ou são uma extensão consistente do ODBC.</span><span class="sxs-lookup"><span data-stu-id="9cf71-103">The following conversions are either already defined by ODBC or are a consistent extension of ODBC.</span></span> <span data-ttu-id="9cf71-104">As conversões fornecidas por cada provedor são determinadas pela comunidade atendida pelo provedor e, com frequência, existem inconsistências entre os resultados.</span><span class="sxs-lookup"><span data-stu-id="9cf71-104">The conversions supplied by each provider are determined by the community served by the provider, and there are often inconsistencies between providers as a result.</span></span> <span data-ttu-id="9cf71-105">Os valores entre colchetes são opcionais.</span><span class="sxs-lookup"><span data-stu-id="9cf71-105">Values in square brackets are optional.</span></span>  
  
-   <span data-ttu-id="9cf71-106">O formato de cadeias de caracteres datetime é 'aaaa-mm-dd[ hh:mm:ss[.9999999][ mais/menos hh:mm]]'</span><span class="sxs-lookup"><span data-stu-id="9cf71-106">The format of datetime strings is 'yyyy-mm-dd[ hh:mm:ss[.9999999][ plus/minus hh:mm]]'</span></span>  
  
-   <span data-ttu-id="9cf71-107">O formato de cadeias de caracteres de hora é 'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="9cf71-107">The format of time strings is 'hh:mm:ss[.9999999]'</span></span>  
  
-   <span data-ttu-id="9cf71-108">O formato de cadeias de caracteres de data é 'aaaa-mm-dd'</span><span class="sxs-lookup"><span data-stu-id="9cf71-108">The format of date strings is 'yyyy-mm-dd'</span></span>  
  
 <span data-ttu-id="9cf71-109">As conversões de cadeias de caracteres permitem uma flexibilidade nos espaços em branco e na largura dos campos.</span><span class="sxs-lookup"><span data-stu-id="9cf71-109">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="9cf71-110">Para obter mais informações, consulte a seção "formatos de dados: cadeias de caracteres e literais" do [suporte de tipo de dados para aprimoramentos de data e hora ODBC](data-type-support-for-odbc-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf71-110">For more information, see the "Data Formats: Strings and Literals" section of [Data Type Support for ODBC Date and Time Improvements](data-type-support-for-odbc-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="9cf71-111">Seguem as regras de conversão gerais:</span><span class="sxs-lookup"><span data-stu-id="9cf71-111">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="9cf71-112">Se não houver uma hora mas o receptor puder armazenar horas, a hora será definida como zero.</span><span class="sxs-lookup"><span data-stu-id="9cf71-112">If no time is present but the receiver can store time, the time is set to zero.</span></span>  
  
-   <span data-ttu-id="9cf71-113">Se não houver uma data presente, mas o receptor puder armazenar datas, a data atual será usada.</span><span class="sxs-lookup"><span data-stu-id="9cf71-113">If no date is present but the receiver can store date, the current date is used.</span></span>  
  
-   <span data-ttu-id="9cf71-114">Se não houver um fuso horário presente no tipo de dados que o cliente está utilizando, mas o servidor puder armazenar fusos horários, a data será armazenada no fuso horário do cliente.</span><span class="sxs-lookup"><span data-stu-id="9cf71-114">If no timezone is present in the data type that the client is using but the server can store timezone, the date is stored in the client timezone.</span></span> <span data-ttu-id="9cf71-115">Observe que isso é diferente do comportamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="9cf71-115">Note that this differs from the server behavior.</span></span>  
  
-   <span data-ttu-id="9cf71-116">Se não houver um fuso horário presente no tipo do servidor, mas o tipo do cliente tiver um fuso horário, a hora será convertida para UTC antes de ser armazenada no servidor.</span><span class="sxs-lookup"><span data-stu-id="9cf71-116">If no timezone is present in the server type but the client type has a timezone, time is converted to UTC before being stored on the server.</span></span>  
  
-   <span data-ttu-id="9cf71-117">Se houver uma hora presente, mas o receptor não puder armazenar horas, o componente de hora será ignorado.</span><span class="sxs-lookup"><span data-stu-id="9cf71-117">If time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="9cf71-118">Se houver uma data presente, mas o receptor não puder armazenar datas, o componente de data será ignorado.</span><span class="sxs-lookup"><span data-stu-id="9cf71-118">If a date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="9cf71-119">Se ocorrer o truncamento de segundos ou frações de segundos ao converter do C para o SQL, um registro de diagnóstico será gerado com SQLSTATE 22008 e a mensagem "Estouro do campo datetime".</span><span class="sxs-lookup"><span data-stu-id="9cf71-119">If truncation of seconds or fractional seconds occurs when converting from C to SQL, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>  
  
-   <span data-ttu-id="9cf71-120">Se ocorrer o truncamento de segundos ou frações de segundos ao converter do SQL para o C, um registro de diagnóstico será gerado com SQLSTATE 01S07 e a mensagem "Truncamento de frações".</span><span class="sxs-lookup"><span data-stu-id="9cf71-120">If truncation of seconds or fractional seconds occurs when converting from SQL to C, a diagnostic record is generated with SQLSTATE 01S07 and the message "Fractional truncation".</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9cf71-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9cf71-121">In This Section</span></span>  
 [<span data-ttu-id="9cf71-122">Conversões do C para o SQL</span><span class="sxs-lookup"><span data-stu-id="9cf71-122">Conversions from C to SQL</span></span>](datetime-data-type-conversions-from-c-to-sql.md)  
 <span data-ttu-id="9cf71-123">Lista os problemas a serem considerados ao converter tipos do C em tipos de data/hora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cf71-123">Lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types.</span></span>  
  
 [<span data-ttu-id="9cf71-124">Conversões de SQL em C</span><span class="sxs-lookup"><span data-stu-id="9cf71-124">Conversions from SQL to C</span></span>](datetime-data-type-conversions-from-sql-to-c.md)  
 <span data-ttu-id="9cf71-125">Lista os problemas a serem considerados ao converter tipos de data/hora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em tipos do C.</span><span class="sxs-lookup"><span data-stu-id="9cf71-125">Lists issues to consider when you convert from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types to C types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf71-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cf71-126">See Also</span></span>  
 [<span data-ttu-id="9cf71-127">Melhorias de data e hora &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="9cf71-127">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
