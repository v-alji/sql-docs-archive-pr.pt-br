---
title: Suporte a tipos de dados para melhorias de data e hora do OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], data type support
- OLE DB, date/time improvements
ms.assetid: d40e3fd6-9057-4371-8236-95cef300603e
author: rothja
ms.author: jroth
ms.openlocfilehash: 834583fdec63a8f613e623c239f9c3a1c9398950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684173"
---
# <a name="data-type-support-for-ole-db-date-and-time-improvements"></a><span data-ttu-id="36ae5-102">Suporte a tipos de dados para melhorias de data e hora do OLE DB</span><span class="sxs-lookup"><span data-stu-id="36ae5-102">Data Type Support for OLE DB Date and Time Improvements</span></span>
  <span data-ttu-id="36ae5-103">Este tópico fornece informações sobre os tipos OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) que oferecem suporte aos tipos de dados de data/hora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ae5-103">This topic provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time data types.</span></span>  
  
## <a name="data-type-mapping-in-rowsets-and-parameters"></a><span data-ttu-id="36ae5-104">Mapeamento de tipos de dados em conjuntos de linhas e parâmetros</span><span class="sxs-lookup"><span data-stu-id="36ae5-104">Data Type Mapping in Rowsets and Parameters</span></span>  
 <span data-ttu-id="36ae5-105">O OLE DB fornece dois novos tipos de dados para dar suporte aos novos tipos de servidor: DBTYPE_DBTIME2 e DBTYPE_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="36ae5-105">OLE DB provides two new data types to support the new server types: DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="36ae5-106">A seguinte tabela mostra o mapeamento de tipo do servidor completo:</span><span class="sxs-lookup"><span data-stu-id="36ae5-106">The following table shows the complete server type mapping:</span></span>  
  
|<span data-ttu-id="36ae5-107">Tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ae5-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="36ae5-108">Tipo de dados OLE DB</span><span class="sxs-lookup"><span data-stu-id="36ae5-108">OLE DB data type</span></span>|<span data-ttu-id="36ae5-109">Valor</span><span class="sxs-lookup"><span data-stu-id="36ae5-109">Value</span></span>|  
|-----------------------------------------|----------------------|-----------|  
|<span data-ttu-id="36ae5-110">DATETIME</span><span class="sxs-lookup"><span data-stu-id="36ae5-110">datetime</span></span>|<span data-ttu-id="36ae5-111">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-111">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-112">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="36ae5-112">135 (oledb.h)</span></span>|  
|<span data-ttu-id="36ae5-113">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="36ae5-113">smalldatetime</span></span>|<span data-ttu-id="36ae5-114">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-114">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-115">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="36ae5-115">135 (oledb.h)</span></span>|  
|<span data-ttu-id="36ae5-116">date</span><span class="sxs-lookup"><span data-stu-id="36ae5-116">date</span></span>|<span data-ttu-id="36ae5-117">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="36ae5-117">DBTYPE_DBDATE</span></span>|<span data-ttu-id="36ae5-118">133 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="36ae5-118">133 (oledb.h)</span></span>|  
|<span data-ttu-id="36ae5-119">time</span><span class="sxs-lookup"><span data-stu-id="36ae5-119">time</span></span>|<span data-ttu-id="36ae5-120">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="36ae5-120">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="36ae5-121">145 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="36ae5-121">145 (sqlncli.h)</span></span>|  
|<span data-ttu-id="36ae5-122">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="36ae5-122">datetimeoffset</span></span>|<span data-ttu-id="36ae5-123">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="36ae5-123">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="36ae5-124">146 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="36ae5-124">146 (sqlncli.h)</span></span>|  
|<span data-ttu-id="36ae5-125">datetime2</span><span class="sxs-lookup"><span data-stu-id="36ae5-125">datetime2</span></span>|<span data-ttu-id="36ae5-126">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-126">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-127">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="36ae5-127">135 (oledb.h)</span></span>|  
  
## <a name="data-formats-strings-and-literals"></a><span data-ttu-id="36ae5-128">Formatos de dados: cadeias e literais</span><span class="sxs-lookup"><span data-stu-id="36ae5-128">Data Formats: Strings and Literals</span></span>  
  
|<span data-ttu-id="36ae5-129">Tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ae5-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="36ae5-130">Tipo de dados OLE DB</span><span class="sxs-lookup"><span data-stu-id="36ae5-130">OLE DB data type</span></span>|<span data-ttu-id="36ae5-131">Formato de cadeia de caracteres para conversões do cliente</span><span class="sxs-lookup"><span data-stu-id="36ae5-131">String format for client conversions</span></span>|  
|-----------------------------------------|----------------------|------------------------------------------|  
|<span data-ttu-id="36ae5-132">DATETIME</span><span class="sxs-lookup"><span data-stu-id="36ae5-132">datetime</span></span>|<span data-ttu-id="36ae5-133">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-133">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-134">'aaaa-mm-dd hh:mm:ss[.999]'</span><span class="sxs-lookup"><span data-stu-id="36ae5-134">'yyyy-mm-dd hh:mm:ss[.999]'</span></span><br /><br /> <span data-ttu-id="36ae5-135">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a até três dígitos de fração de segundo para Datetime.</span><span class="sxs-lookup"><span data-stu-id="36ae5-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports up to three fractional second digits for Datetime.</span></span>|  
|<span data-ttu-id="36ae5-136">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="36ae5-136">smalldatetime</span></span>|<span data-ttu-id="36ae5-137">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-137">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-138">'aaaa-mm-dd hh:mm:ss'</span><span class="sxs-lookup"><span data-stu-id="36ae5-138">'yyyy-mm-dd hh:mm:ss'</span></span><br /><br /> <span data-ttu-id="36ae5-139">Este tipo de dados tem precisão de um minuto.</span><span class="sxs-lookup"><span data-stu-id="36ae5-139">This data type has an accuracy of one minute.</span></span> <span data-ttu-id="36ae5-140">O componente de segundos será zero na saída, sendo arredondado pelo servidor na entrada.</span><span class="sxs-lookup"><span data-stu-id="36ae5-140">The seconds component will be zero on output and will be rounded by the server on input.</span></span>|  
|<span data-ttu-id="36ae5-141">date</span><span class="sxs-lookup"><span data-stu-id="36ae5-141">date</span></span>|<span data-ttu-id="36ae5-142">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="36ae5-142">DBTYPE_DBDATE</span></span>|<span data-ttu-id="36ae5-143">'aaaa-mm-dd'</span><span class="sxs-lookup"><span data-stu-id="36ae5-143">'yyyy-mm-dd'</span></span>|  
|<span data-ttu-id="36ae5-144">time</span><span class="sxs-lookup"><span data-stu-id="36ae5-144">time</span></span>|<span data-ttu-id="36ae5-145">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="36ae5-145">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="36ae5-146">'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="36ae5-146">'hh:mm:ss[.9999999]'</span></span><br /><br /> <span data-ttu-id="36ae5-147">Opcionalmente, podem ser especificadas frações de segundo usando até sete dígitos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-147">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="36ae5-148">datetime2</span><span class="sxs-lookup"><span data-stu-id="36ae5-148">datetime2</span></span>|<span data-ttu-id="36ae5-149">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-149">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-150">'aaaa-mm-dd hh:mm:ss[.fffffff]'</span><span class="sxs-lookup"><span data-stu-id="36ae5-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span></span><br /><br /> <span data-ttu-id="36ae5-151">Opcionalmente, podem ser especificadas frações de segundo usando até sete dígitos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-151">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="36ae5-152">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="36ae5-152">datetimeoffset</span></span>|<span data-ttu-id="36ae5-153">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="36ae5-153">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="36ae5-154">'aaaa-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span><span class="sxs-lookup"><span data-stu-id="36ae5-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span></span><br /><br /> <span data-ttu-id="36ae5-155">Opcionalmente, podem ser especificadas frações de segundo usando até sete dígitos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-155">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
  
 <span data-ttu-id="36ae5-156">Não há nenhuma alteração às sequências de escape para literais de data/hora.</span><span class="sxs-lookup"><span data-stu-id="36ae5-156">There are no changes to the escape sequences for date/time literals.</span></span>  
  
 <span data-ttu-id="36ae5-157">As frações de segundo nos resultados usam um ponto (.) em vez de um dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="36ae5-157">Fractional seconds in results use a dot (.) rather than a colon (:).</span></span>  
  
 <span data-ttu-id="36ae5-158">Valores da cadeia de caracteres passados como retorno aos aplicativos sempre terão o mesmo comprimento para uma determinada coluna.</span><span class="sxs-lookup"><span data-stu-id="36ae5-158">String values returned to applications will always be the same length for a given column.</span></span> <span data-ttu-id="36ae5-159">Componentes de ano, mês, dia, hora, minuto e segundo serão preenchidos com zeros à esquerda até seu comprimento máximo.</span><span class="sxs-lookup"><span data-stu-id="36ae5-159">Year, month, day, hour, minute, and second components will be padded with leading zeros to their maximum width.</span></span> <span data-ttu-id="36ae5-160">Haverá exatamente um espaço entre a data e a hora e exatamente um espaço entre a hora e o deslocamento de fuso horário.</span><span class="sxs-lookup"><span data-stu-id="36ae5-160">There will be exactly one space between date and time and exactly one space between the time and timezone offset.</span></span> <span data-ttu-id="36ae5-161">Um deslocamento de fuso horário sempre será precedido de um sinal.</span><span class="sxs-lookup"><span data-stu-id="36ae5-161">A timezone offset will always be preceded by a sign.</span></span> <span data-ttu-id="36ae5-162">Este sinal será positivo (+) quando o deslocamento for zero.</span><span class="sxs-lookup"><span data-stu-id="36ae5-162">This sign will be a plus (+) when the offset is zero.</span></span> <span data-ttu-id="36ae5-163">Não haverá nenhum espaço em branco entre o sinal e o valor do deslocamento.</span><span class="sxs-lookup"><span data-stu-id="36ae5-163">There will be no white space between the sign and the offset value.</span></span> <span data-ttu-id="36ae5-164">Frações de segundo serão preenchidas com zero à direita, se necessário, até a precisão definida para a coluna, mas não mais que isso.</span><span class="sxs-lookup"><span data-stu-id="36ae5-164">Fractional seconds will be padded with trailing zeros, if necessary, up to the defined precision for the column, but no further.</span></span> <span data-ttu-id="36ae5-165">Para colunas do tipo datetime, haverá três dígitos para frações de segundo.</span><span class="sxs-lookup"><span data-stu-id="36ae5-165">For datetime columns, there will be three fractional seconds digits.</span></span> <span data-ttu-id="36ae5-166">Para colunas do tipo smalldatetime, não haverá nenhum dígito de fração de segundo e os segundos sempre serão zero.</span><span class="sxs-lookup"><span data-stu-id="36ae5-166">For smalldatetime columns, there will be no fractional seconds digits and the seconds will always be zero.</span></span>  
  
 <span data-ttu-id="36ae5-167">Conversões de valores da cadeia de caracteres fornecidos pelo aplicativo serão mais flexíveis e permitirão valores componentes com comprimento menor que o máximo.</span><span class="sxs-lookup"><span data-stu-id="36ae5-167">Conversions from string values provided by the application will be more flexible and will allow component values less than maximum width.</span></span> <span data-ttu-id="36ae5-168">Anos podem ter de 1 a 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-168">Years can be 1-4 digits.</span></span> <span data-ttu-id="36ae5-169">Meses, dias, horas, minutos e segundos podem ter 1 ou 2 dígitos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-169">Months, days, hours, minutes, and seconds can be 1 or 2 digits.</span></span> <span data-ttu-id="36ae5-170">Pode haver um espaço em branco arbitrário entre data/hora e hora/deslocamentos de fuso horário.</span><span class="sxs-lookup"><span data-stu-id="36ae5-170">There can be arbitrary white space between date/time and time/timezone offsets.</span></span> <span data-ttu-id="36ae5-171">O sinal de um deslocamento com zero horas e zero minutos pode ser mais ou menos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-171">The sign of an offset with zero hours and zero minutes can be plus or minus.</span></span> <span data-ttu-id="36ae5-172">São permitidos zeros à direita para frações de segundo até um máximo de 9 dígitos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-172">Trailing zeros are allowed for fractional seconds up to a maximum of 9 digits.</span></span> <span data-ttu-id="36ae5-173">Um componente de hora pode terminar com um ponto decimal e não ter dígitos de fração de segundo.</span><span class="sxs-lookup"><span data-stu-id="36ae5-173">A time component can terminate with a decimal point and no fractional seconds digits.</span></span>  
  
 <span data-ttu-id="36ae5-174">Uma cadeia de caracteres vazia não é um literal de data/hora válido e não representa um valor NULL.</span><span class="sxs-lookup"><span data-stu-id="36ae5-174">An empty string is not a valid date/time literal and it does not represent a NULL value.</span></span> <span data-ttu-id="36ae5-175">Uma tentativa de conversão de uma cadeia de caracteres vazia para um valor de data/hora resultará em erros com SQLState 22018 e a mensagem "Valor de caractere inválido para a especificação de difusão".</span><span class="sxs-lookup"><span data-stu-id="36ae5-175">An attempt to convert an empty string to a date/time value will result in errors with SQLState 22018 and the message "Invalid character value for cast specification".</span></span>  
  
## <a name="data-formats-data-structures"></a><span data-ttu-id="36ae5-176">Formatos de dados: estruturas de dados</span><span class="sxs-lookup"><span data-stu-id="36ae5-176">Data Formats: Data Structures</span></span>  
 <span data-ttu-id="36ae5-177">Nas estruturas específicas do OLE DB descritas a seguir, o OLE DB obedece às mesmas restrições que o ODBC.</span><span class="sxs-lookup"><span data-stu-id="36ae5-177">In the OLE DB-specific structures described below, OLE DB conforms to the same constraints as ODBC.</span></span> <span data-ttu-id="36ae5-178">Elas são extraídas do calendário gregoriano:</span><span class="sxs-lookup"><span data-stu-id="36ae5-178">These are taken from the Gregorian calendar:</span></span>  
  
-   <span data-ttu-id="36ae5-179">O intervalo de meses é de 1 a 12.</span><span class="sxs-lookup"><span data-stu-id="36ae5-179">Month range is 1 through 12.</span></span>  
  
-   <span data-ttu-id="36ae5-180">O intervalo do campo de dias é de 1 ao número de dias do mês e deve ser coerente com os campos de ano e mês, levando em conta os anos bissextos.</span><span class="sxs-lookup"><span data-stu-id="36ae5-180">Day field range is 1 through the number of days in the month, and must be consistent with year and month fields, taking account of leap years.</span></span>  
  
-   <span data-ttu-id="36ae5-181">O intervalo de horas é de 0 a 23.</span><span class="sxs-lookup"><span data-stu-id="36ae5-181">Hour range is 0 through 23.</span></span>  
  
-   <span data-ttu-id="36ae5-182">O intervalo de minutos é de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="36ae5-182">Minute range is 0 through 59.</span></span>  
  
-   <span data-ttu-id="36ae5-183">O intervalo de segundos é de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="36ae5-183">Seconds range from 0 through 59.</span></span> <span data-ttu-id="36ae5-184">Isso permite até dois segundos bissextos para manter a sincronização com a hora sideral.</span><span class="sxs-lookup"><span data-stu-id="36ae5-184">This allows up to two leap seconds to maintain synchronization with sidereal time.</span></span>  
  
 <span data-ttu-id="36ae5-185">Foram modificadas as implementações dos seguintes structs do OLE DB existentes para dar suporte aos novos tipos de data e hora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ae5-185">Implementations for the following existing OLE DB structs have been modified to support the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span> <span data-ttu-id="36ae5-186">Porém, as definições não foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="36ae5-186">The definitions, however, have not changed.</span></span>  
  
-   <span data-ttu-id="36ae5-187">DBTYPE_DATE (É um tipo de automação DATE.</span><span class="sxs-lookup"><span data-stu-id="36ae5-187">DBTYPE_DATE (This is an automation DATE type.</span></span> <span data-ttu-id="36ae5-188">representado internamente como um `double`.</span><span class="sxs-lookup"><span data-stu-id="36ae5-188">It is internally represented as a `double`..</span></span> <span data-ttu-id="36ae5-189">A parte inteira é o número de dias desde 30 de dezembro de 1899 e a parte fracionária é a fração de um dia.</span><span class="sxs-lookup"><span data-stu-id="36ae5-189">The whole part is the number of days since December 30, 1899 and the fractional part is the fraction of a day.</span></span> <span data-ttu-id="36ae5-190">Este tipo tem uma exatidão de 1 segundo, portanto tem uma escala efetiva de 0.)</span><span class="sxs-lookup"><span data-stu-id="36ae5-190">This type has an accuracy of 1 second, so has an effective scale of 0.)</span></span>  
  
-   <span data-ttu-id="36ae5-191">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="36ae5-191">DBTYPE_DBDATE</span></span>  
  
-   <span data-ttu-id="36ae5-192">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="36ae5-192">DBTYPE_DBTIME</span></span>  
  
-   <span data-ttu-id="36ae5-193">DBTYPE_DBTIMESTAMP (o campo de fração é definido pelo OLE DB como o número de bilionésimos de segundo (nanossegundos) e varia de 0 a 999.999.999)</span><span class="sxs-lookup"><span data-stu-id="36ae5-193">DBTYPE_DBTIMESTAMP (the fraction field is defined by OLE DB as the number of billionths of a second (nanoseconds) and ranges from 0-999,999,999)</span></span>  
  
-   <span data-ttu-id="36ae5-194">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="36ae5-194">DBTYPE_FILETIME</span></span>  
  
### <a name="dbtype_dbtime2"></a><span data-ttu-id="36ae5-195">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="36ae5-195">DBTYPE_DBTIME2</span></span>  
 <span data-ttu-id="36ae5-196">Esse struct é preenchido com até 12 bytes nos sistemas operacionais de 32 e 64 bits.</span><span class="sxs-lookup"><span data-stu-id="36ae5-196">This struct is padded to 12 bytes on both 32-bit and 64-bit operating systems.</span></span>  
  
```  
typedef struct tagDBTIME2 {  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    } DBTIME2;  
```  
  
### <a name="dbtype_-dbtimestampoffset"></a><span data-ttu-id="36ae5-197">DBTYPE_ DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="36ae5-197">DBTYPE_ DBTIMESTAMPOFFSET</span></span>  
  
```  
typedef struct tagDBTIMESTAMPOFFSET {  
    SHORT year;  
    USHORT month;  
    USHORT day;  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    SHORT timezone_hour;  
    SHORT timezone_minute;  
    } DBTIMESTAMPOFFSET;  
```  
  
 <span data-ttu-id="36ae5-198">Se `timezone_hour` for negativo, `timezone_minute` deve ser negativo ou zero.</span><span class="sxs-lookup"><span data-stu-id="36ae5-198">If `timezone_hour` is negative, `timezone_minute` must be negative or zero.</span></span> <span data-ttu-id="36ae5-199">Se `timezone_hour` for positivo, `timezone minute` deve ser positivo ou zero.</span><span class="sxs-lookup"><span data-stu-id="36ae5-199">If `timezone_hour` is positive, `timezone minute` must be positive or zero.</span></span> <span data-ttu-id="36ae5-200">Se `timezone_hour` for zero, `timezone minute` poderá ter valor entre -59 e +59.</span><span class="sxs-lookup"><span data-stu-id="36ae5-200">If `timezone_hour` is zero, `timezone minute` can hold a value between -59 and +59.</span></span>  
  
### <a name="ssvariant"></a><span data-ttu-id="36ae5-201">SSVARIANT</span><span class="sxs-lookup"><span data-stu-id="36ae5-201">SSVARIANT</span></span>  
 <span data-ttu-id="36ae5-202">Agora esse struct inclui as novas estruturas, DBTYPE_DBTIME2 e DBTYPE_DBTIMESTAMPOFFSET, e adiciona a escala de frações de segundo para os tipos apropriados.</span><span class="sxs-lookup"><span data-stu-id="36ae5-202">This struct now includes the new structures, DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET, and adds fractional seconds scale for appropriate types.</span></span>  
  
```  
struct SSVARIANT {  
   SSVARTYPE vt;  
   DWORD dwReserved1;  
   DWORD dwReserved2;  
   union {  
// ...  
      DBTIMESTAMP tsDateTimeVal;  
      DBDATE dDateVal;  
      struct _Time2Val {  
         DBTIME2 tTime2Val;  
         BYTE bScale;  
      } Time2Val;  
      struct _DateTimeVal {  
         DBTIMESTAMP tsDateTimeVal;  
         BYTE bScale;  
      } DateTimeVal;  
      struct _DateTimeOffsetVal {   
         DBTIMESTAMPOFFSET tsoDateTimeOffsetVal;  
         BYTE bScale;  
      } DateTimeOffsetVal;  
// ...  
   };  
};  
```  
  
 <span data-ttu-id="36ae5-203">Além disso, o enum associado à codificação do tipo SSVARIANT, que determina o tipo do enum, será estendido conforme indicado a seguir:</span><span class="sxs-lookup"><span data-stu-id="36ae5-203">In addition, the enum associated with SSVARIANT type encoding, which determines the type of the enum, will be extended as follows:</span></span>  
  
```  
enum SQLVARENUM {  
// ...  
   // Datetime  
   VT_SS_DATETIME      = DBTYPE_DBTIMESTAMP,  
   VT_SS_SMALLDATETIME = 206,  
  
   VT_SS_DATE = DBTYPE_DBDATE,  
   VT_SS_TIME2 = DBTYPE_DBTIME2,  
   VT_SS_DATETIME2 = 212  
   VT_SS_DATETIMEOFFSET = DBTYPE_DBTIMESTAMPOFFSET  
};  
```  
  
 <span data-ttu-id="36ae5-204">Os aplicativos que migrarem para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client que usam `sql_variant` e contam com a precisão limitada do `datetime` deverão ser atualizados se o esquema subjacente for atualizado para usar o `datetime2` em vez do `datetime`.</span><span class="sxs-lookup"><span data-stu-id="36ae5-204">Applications migrating to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client that use `sql_variant` and rely on the limited precision of `datetime` will have to be updated if the underlying schema is updated to use `datetime2` rather than `datetime`.</span></span>  
  
 <span data-ttu-id="36ae5-205">Também foram estendidas as macros de acesso para SSVARIANT com a adição do seguinte:</span><span class="sxs-lookup"><span data-stu-id="36ae5-205">The access macros for SSVARIANT have also been extended with the addition of the following:</span></span>  
  
```  
#define V_SS_DATETIME2(X)       V_SS_UNION(X, DateTimeVal)  
#define V_SS_TIME2(X)           V_SS_UNION(X, Time2Val)  
#define V_SS_DATE(X)            V_SS_UNION(X, dDateVal)  
#define V_SS_DATETIMEOFFSET(X)  V_SS_UNION(X, DateTimeOffsetVal)  
```  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a><span data-ttu-id="36ae5-206">Mapeamento de tipo de dados em ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="36ae5-206">Data Type Mapping in ITableDefinition::CreateTable</span></span>  
 <span data-ttu-id="36ae5-207">O seguinte mapeamento de tipo é usado com estruturas DBCOLUMNDESC usadas por ITableDefinition::CreateTable:</span><span class="sxs-lookup"><span data-stu-id="36ae5-207">The following type mapping is used with DBCOLUMNDESC structures used by ITableDefinition::CreateTable:</span></span>  
  
|<span data-ttu-id="36ae5-208">Tipo de dados OLE DB (*wType*)</span><span class="sxs-lookup"><span data-stu-id="36ae5-208">OLE DB data type (*wType*)</span></span>|<span data-ttu-id="36ae5-209">Tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ae5-209">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="36ae5-210">Observações</span><span class="sxs-lookup"><span data-stu-id="36ae5-210">Notes</span></span>|  
|----------------------------------|-----------------------------------------|-----------|  
|<span data-ttu-id="36ae5-211">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="36ae5-211">DBTYPE_DBDATE</span></span>|<span data-ttu-id="36ae5-212">date</span><span class="sxs-lookup"><span data-stu-id="36ae5-212">date</span></span>||  
|<span data-ttu-id="36ae5-213">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="36ae5-213">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="36ae5-214">`datetime2`(p)</span><span class="sxs-lookup"><span data-stu-id="36ae5-214">`datetime2`(p)</span></span>|<span data-ttu-id="36ae5-215">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo inspeciona o membro DBCOLUMDESC *bScale* para determinar a precisão de segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="36ae5-215">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="36ae5-216">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="36ae5-216">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="36ae5-217">`time`(p)</span><span class="sxs-lookup"><span data-stu-id="36ae5-217">`time`(p)</span></span>|<span data-ttu-id="36ae5-218">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo inspeciona o membro DBCOLUMDESC *bScale* para determinar a precisão de segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="36ae5-218">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="36ae5-219">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="36ae5-219">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="36ae5-220">`datetimeoffset`(p)</span><span class="sxs-lookup"><span data-stu-id="36ae5-220">`datetimeoffset`(p)</span></span>|<span data-ttu-id="36ae5-221">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo inspeciona o membro DBCOLUMDESC *bScale* para determinar a precisão de segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="36ae5-221">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
  
 <span data-ttu-id="36ae5-222">Quando um aplicativo especifica DBTYPE_DBTIMESTAMP em *wType*, ele pode substituir o mapeamento `datetime2` pelo fornecendo um nome de tipo em *pwszTypeName*.</span><span class="sxs-lookup"><span data-stu-id="36ae5-222">When an application specifies DBTYPE_DBTIMESTAMP in *wType*, it can override the mapping to `datetime2` by supplying a type name in *pwszTypeName*.</span></span> <span data-ttu-id="36ae5-223">Se `datetime` for especificado, *bScale* deverá ser 3.</span><span class="sxs-lookup"><span data-stu-id="36ae5-223">If `datetime` is specified, *bScale* must be 3.</span></span> <span data-ttu-id="36ae5-224">Se `smalldatetime` for especificado, *bScale* deverá ser 0.</span><span class="sxs-lookup"><span data-stu-id="36ae5-224">If `smalldatetime` is specified, *bScale* must be 0.</span></span> <span data-ttu-id="36ae5-225">Se *bScale* não for consistente com *wType* e *pwszTypeName*, DB_E_BADSCALE será retornado.</span><span class="sxs-lookup"><span data-stu-id="36ae5-225">If *bScale* is not consistent with *wType* and *pwszTypeName*,DB_E_BADSCALE is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ae5-226">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36ae5-226">See Also</span></span>  
 [<span data-ttu-id="36ae5-227">Melhorias de data e hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="36ae5-227">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
