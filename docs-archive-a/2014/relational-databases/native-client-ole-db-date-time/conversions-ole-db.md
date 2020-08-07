---
title: Associações e conversões (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- conversions [OLE DB]
- bindings [OLE DB]
- OLE DB, bindings and conversions
ms.assetid: c187df58-a8c8-4c74-a76f-663abbc5f0c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 95c73bdad80b5f948a45235ad208ab307fcceff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582452"
---
# <a name="bindings-and-conversions-ole-db"></a><span data-ttu-id="1eb99-102">Associações e conversões (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1eb99-102">Bindings and Conversions (OLE DB)</span></span>
  <span data-ttu-id="1eb99-103">Esta seção aborda como converter entre valores `datetime` e `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="1eb99-103">This section discusses how to convert between `datetime` and `datetimeoffset` values.</span></span> <span data-ttu-id="1eb99-104">As conversões descritas nesta seção já são fornecidas pelo OLE DB ou são uma extensão consistente do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1eb99-104">The conversions described in this section are either already provided by OLE DB or are a consistent extension of OLE DB.</span></span>  
  
 <span data-ttu-id="1eb99-105">O formato de literais e cadeias de caracteres para datas e horas no OLE DB geralmente segue a norma ISO e não depende da localidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="1eb99-105">The format of literals and strings for dates and times in OLE DB generally follows ISO, and is not dependent on the client locale.</span></span> <span data-ttu-id="1eb99-106">Uma exceção é DBTYPE_DATE, em que o padrão é Automação OLE.</span><span class="sxs-lookup"><span data-stu-id="1eb99-106">One exception is DBTYPE_DATE, where the standard is OLE Automation.</span></span> <span data-ttu-id="1eb99-107">Entretanto, como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client só converte entre tipos quando os dados são transmitidos para ou do cliente, não há como um aplicativo obrigar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client a converter entre DBTYPE_DATE e formatos de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1eb99-107">However, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client only converts between types when data is transmitted to or from the client, there is no way for an application to force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to convert between DBTYPE_DATE and string formats.</span></span> <span data-ttu-id="1eb99-108">Caso contrário, as cadeias de caracteres usam os formatos a seguir (texto entre colchetes indica um elemento opcional):</span><span class="sxs-lookup"><span data-stu-id="1eb99-108">Otherwise, strings use the following formats (text in brackets indicates an optional element):</span></span>  
  
-   <span data-ttu-id="1eb99-109">O formato das cadeias de caracteres `datetime` e `datetimeoffset` é:</span><span class="sxs-lookup"><span data-stu-id="1eb99-109">The format of `datetime` and `datetimeoffset` strings is:</span></span>  
  
     <span data-ttu-id="1eb99-110">*aaaa* - *mm* - *DD*[ *hh*:*mm*:*SS*[.\* 9999999\*] [??</span><span class="sxs-lookup"><span data-stu-id="1eb99-110">*yyyy*-*mm*-*dd*[ *hh*:*mm*:*ss*[.*9999999*][ ??</span></span> <span data-ttu-id="1eb99-111">*hh*:*mm*]]</span><span class="sxs-lookup"><span data-stu-id="1eb99-111">*hh*:*mm*]]</span></span>  
  
-   <span data-ttu-id="1eb99-112">O formato das cadeias de caracteres `time` é:</span><span class="sxs-lookup"><span data-stu-id="1eb99-112">The format of `time` strings is:</span></span>  
  
     <span data-ttu-id="1eb99-113">*hh*:*mm*:*ss*[.*9999999*]</span><span class="sxs-lookup"><span data-stu-id="1eb99-113">*hh*:*mm*:*ss*[.*9999999*]</span></span>  
  
-   <span data-ttu-id="1eb99-114">O formato das cadeias de caracteres `date` é:</span><span class="sxs-lookup"><span data-stu-id="1eb99-114">The format of `date` strings is:</span></span>  
  
     <span data-ttu-id="1eb99-115">*yyyy*-*mm*-*dd*</span><span class="sxs-lookup"><span data-stu-id="1eb99-115">*yyyy*-*mm*-*dd*</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1eb99-116">As versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client e SQLOLEDB implementavam conversões OLE, caso em que conversões padrão falhavam.</span><span class="sxs-lookup"><span data-stu-id="1eb99-116">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and SQLOLEDB implemented OLE conversions, in case standard conversions failed.</span></span> <span data-ttu-id="1eb99-117">Consequentemente, algumas conversões executadas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 e versões posteriores diferem da especificação OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1eb99-117">As a result, some conversions performed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 and later differ from the OLE DB specification.</span></span>  
  
 <span data-ttu-id="1eb99-118">As conversões de cadeias de caracteres permitem uma flexibilidade nos espaços em branco e na largura dos campos.</span><span class="sxs-lookup"><span data-stu-id="1eb99-118">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="1eb99-119">Para obter mais informações, consulte a seção "formatos de dados: cadeias de caracteres e literais" em [suporte de tipo de dados para OLE DB melhorias de data e hora](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="1eb99-119">For more information, see the "Data Formats: Strings and Literals" section in [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="1eb99-120">Seguem as regras de conversão gerais:</span><span class="sxs-lookup"><span data-stu-id="1eb99-120">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="1eb99-121">Quando uma cadeia de caracteres é convertida em um tipo de data/hora, a cadeia de caracteres é analisada primeiro como um literal ISO.</span><span class="sxs-lookup"><span data-stu-id="1eb99-121">When a string is converted to a date/time type, the string is first parsed as an ISO literal.</span></span> <span data-ttu-id="1eb99-122">Se esse procedimento falhar, a cadeia de caracteres será analisada como um literal de data OLE, que tem componentes de hora.</span><span class="sxs-lookup"><span data-stu-id="1eb99-122">If this fails, the string is parsed as an OLE date literal, which has time components.</span></span>  
  
-   <span data-ttu-id="1eb99-123">Se não houver uma hora mas o receptor puder armazenar horas, a hora será definida como zero.</span><span class="sxs-lookup"><span data-stu-id="1eb99-123">If no time is present but the receiver can store time, the time is set to zero.</span></span> <span data-ttu-id="1eb99-124">Se não houver uma data mas o receptor puder armazenar datas, a data será definida como a data atual quando conversões ISO forem usadas e como 1899-12-30 quando conversões OLE forem usadas.</span><span class="sxs-lookup"><span data-stu-id="1eb99-124">If no date is present but the receiver can store a date, the date is set to the current date when ISO conversions are used and to 1899-12-30 when OLE conversions are used.</span></span>  
  
-   <span data-ttu-id="1eb99-125">Se não houver um fuso horário no tipo de dados que o cliente está utilizando mas o servidor puder armazenar fusos horários, a data no cliente será assumida como o fuso horário do cliente.</span><span class="sxs-lookup"><span data-stu-id="1eb99-125">If no timezone is present in the data type that the client is using, but the server can store timezone, the data on the client is assumed to be in the client timezone.</span></span>  
  
-   <span data-ttu-id="1eb99-126">Se não houver nenhum fuso horário no servidor mas o cliente tiver informações de fusos horários, o fuso horário de UTC será assumido.</span><span class="sxs-lookup"><span data-stu-id="1eb99-126">If no timezone is present at the server but the client has timezone information, the UTC timezone is assumed.</span></span> <span data-ttu-id="1eb99-127">Esse é um comportamento diferente daquele do servidor.</span><span class="sxs-lookup"><span data-stu-id="1eb99-127">This differs from server behavior.</span></span>  
  
-   <span data-ttu-id="1eb99-128">Se houver uma hora mas o receptor não puder armazenar horas, o componente de hora será ignorado.</span><span class="sxs-lookup"><span data-stu-id="1eb99-128">If the time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="1eb99-129">Se houver uma data mas o receptor não puder armazenar datas, o componente de data será ignorado.</span><span class="sxs-lookup"><span data-stu-id="1eb99-129">If the date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="1eb99-130">Se ocorrer o truncamento de segundos ou segundos fracionários ao converter de cliente em servidor, DB_E_ERRORSOCCURRED será retornado e o status DBSTATUS_E_DATAOVERFLOW será definido.</span><span class="sxs-lookup"><span data-stu-id="1eb99-130">If truncation of seconds or fractional seconds occurs when converting from client to server, DB_E_ERRORSOCCURRED is returned and the status DBSTATUS_E_DATAOVERFLOW is set.</span></span>  
  
-   <span data-ttu-id="1eb99-131">Se ocorrer o truncamento de segundos ou segundos fracionários ao converter de servidor em cliente, DBSTATUS_S_TRUNCATED será definido.</span><span class="sxs-lookup"><span data-stu-id="1eb99-131">If truncation of seconds or fractional seconds occurs when converting from server to client, DBSTATUS_S_TRUNCATED is set</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1eb99-132">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1eb99-132">In This Section</span></span>  
 [<span data-ttu-id="1eb99-133">Conversões executadas do cliente para o servidor</span><span class="sxs-lookup"><span data-stu-id="1eb99-133">Conversions Performed from Client to Server</span></span>](conversions-performed-from-client-to-server.md)  
 <span data-ttu-id="1eb99-134">Descreve conversões de data/hora executadas entre um aplicativo cliente escrito com o OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client e o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (ou posterior).</span><span class="sxs-lookup"><span data-stu-id="1eb99-134">Describes date/time conversions performed between a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 [<span data-ttu-id="1eb99-135">Conversões executadas do servidor para o cliente</span><span class="sxs-lookup"><span data-stu-id="1eb99-135">Conversions Performed from Server to Client</span></span>](conversions-performed-from-server-to-client.md)  
 <span data-ttu-id="1eb99-136">Descreve conversões de data/hora executadas entre o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (ou posterior) e um aplicativo cliente escrito com o DB OLE do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1eb99-136">Describes date/time conversions performed between [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) and a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb99-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1eb99-137">See Also</span></span>  
 [<span data-ttu-id="1eb99-138">Melhorias de data e hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1eb99-138">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
