---
title: Codificar e decodificar identificadores do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: bb9fe0d3-e432-42d3-b324-64dc908b544a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88e7ebbc81d9c3cb91b1bf678075c5b5d0884890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679390"
---
# <a name="encode-and-decode-sql-server-identifiers"></a><span data-ttu-id="ae244-102">Codificar e decodificar identificadores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae244-102">Encode and Decode SQL Server Identifiers</span></span>
  <span data-ttu-id="ae244-103">Os identificadores delimitados do SQL Server às vezes contêm caracteres sem suporte em caminhos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae244-103">SQL Server delimited identifiers sometimes contain characters not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="ae244-104">Esses caracteres podem ser especificados codificando seus valores hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="ae244-104">These characters can be specified by encoding their hexadecimal values.</span></span>  
  
1.  <span data-ttu-id="ae244-105">**Antes de começar:**  [Limitações e restrições](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="ae244-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="ae244-106">**Para processar caracteres especiais:**  [Codificando um Identificador](#EncodeIdent), [Decodificando um Identificador](#DecodeIdent)</span><span class="sxs-lookup"><span data-stu-id="ae244-106">**To process special characters:**  [Encoding an Identifier](#EncodeIdent), [Decoding an Identifier](#DecodeIdent)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="ae244-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ae244-107">Before You Begin</span></span>  
 <span data-ttu-id="ae244-108">Os caracteres que não têm suporte nos nomes de caminho do Windows PowerShell podem ser representados, ou codificados, como o caractere "%" seguido pelo valor hexadecimal para o padrão de bit que representa o caractere, como em " **%** XX".</span><span class="sxs-lookup"><span data-stu-id="ae244-108">Characters that are not supported in Windows PowerShell path names can be represented, or encoded, as the "%" character followed by the hexadecimal value for the bit pattern that represents the character, as in "**%** xx".</span></span> <span data-ttu-id="ae244-109">A codificação sempre pode ser usada para manipular caracteres não suportados em caminhos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae244-109">Encoding can always be used to handle characters that are not supported in Windows PowerShell paths.</span></span>  
  
 <span data-ttu-id="ae244-110">O cmdlet **Encode-SqlName** usa um identificador do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] como entrada.</span><span class="sxs-lookup"><span data-stu-id="ae244-110">The **Encode-SqlName** cmdlet takes as input a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier.</span></span> <span data-ttu-id="ae244-111">Ele produz uma cadeia de caracteres com todos os caracteres não suportados pela linguagem Windows PowerShell codificada com "%xx".</span><span class="sxs-lookup"><span data-stu-id="ae244-111">It outputs a string with all the characters that are not supported by the Windows PowerShell language encoded with "%xx".</span></span> <span data-ttu-id="ae244-112">O cmdlet **Decode-SqlName** usa um identificador codificado do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] como entrada e retorna o identificador original.</span><span class="sxs-lookup"><span data-stu-id="ae244-112">The **Decode-SqlName** cmdlet takes as input an encoded [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier and returns the original identifier.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="ae244-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ae244-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ae244-114">Os cmdlets `Encode-Sqlname` e `Decode-Sqlname` só codificam ou decodificam os caracteres que são permitidos nos identificadores delimitados SQL Server, mas não tem suporte em caminhos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae244-114">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets only encode or decode the characters that are allowed in SQL Server delimited identifiers, but are not supported in PowerShell paths.</span></span> <span data-ttu-id="ae244-115">Estes são os caracteres codificados pelo **Encode-SqlName** e decodificados pelo **Decode-SqlName**:</span><span class="sxs-lookup"><span data-stu-id="ae244-115">These are the characters encoded by **Encode-SqlName** and decoded by **Decode-SqlName**:</span></span>  
  
|||||||||||||  
|-|-|-|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="ae244-116">**Caractere**</span><span class="sxs-lookup"><span data-stu-id="ae244-116">**Character**</span></span>|\ |/|<span data-ttu-id="ae244-117">:</span><span class="sxs-lookup"><span data-stu-id="ae244-117">:</span></span>|%|\<|>|*|<span data-ttu-id="ae244-118">?</span><span class="sxs-lookup"><span data-stu-id="ae244-118">?</span></span>|<span data-ttu-id="ae244-119">[</span><span class="sxs-lookup"><span data-stu-id="ae244-119">[</span></span>|<span data-ttu-id="ae244-120">]</span><span class="sxs-lookup"><span data-stu-id="ae244-120">]</span></span>|<span data-ttu-id="ae244-121">&#124;</span><span class="sxs-lookup"><span data-stu-id="ae244-121">&#124;</span></span>|  
|<span data-ttu-id="ae244-122">**Codificação hexadecimal**</span><span class="sxs-lookup"><span data-stu-id="ae244-122">**Hexadecimal Encoding**</span></span>|<span data-ttu-id="ae244-123">%5C</span><span class="sxs-lookup"><span data-stu-id="ae244-123">%5C</span></span>|<span data-ttu-id="ae244-124">%2F</span><span class="sxs-lookup"><span data-stu-id="ae244-124">%2F</span></span>|<span data-ttu-id="ae244-125">%3A</span><span class="sxs-lookup"><span data-stu-id="ae244-125">%3A</span></span>|<span data-ttu-id="ae244-126">%25</span><span class="sxs-lookup"><span data-stu-id="ae244-126">%25</span></span>|<span data-ttu-id="ae244-127">%3C</span><span class="sxs-lookup"><span data-stu-id="ae244-127">%3C</span></span>|<span data-ttu-id="ae244-128">%3E</span><span class="sxs-lookup"><span data-stu-id="ae244-128">%3E</span></span>|<span data-ttu-id="ae244-129">%2A</span><span class="sxs-lookup"><span data-stu-id="ae244-129">%2A</span></span>|<span data-ttu-id="ae244-130">%3F</span><span class="sxs-lookup"><span data-stu-id="ae244-130">%3F</span></span>|<span data-ttu-id="ae244-131">%5B</span><span class="sxs-lookup"><span data-stu-id="ae244-131">%5B</span></span>|<span data-ttu-id="ae244-132">%5D</span><span class="sxs-lookup"><span data-stu-id="ae244-132">%5D</span></span>|<span data-ttu-id="ae244-133">%7C</span><span class="sxs-lookup"><span data-stu-id="ae244-133">%7C</span></span>|  
  
##  <a name="encoding-an-identifier"></a><a name="EncodeIdent"></a> <span data-ttu-id="ae244-134">Codificando um Identificador</span><span class="sxs-lookup"><span data-stu-id="ae244-134">Encoding an Identifier</span></span>  
 <span data-ttu-id="ae244-135">**Para codificar um identificadores do SQL Server em um caminho PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ae244-135">**To encode a SQL Server identifier in a PowerShell path**</span></span>  
  
-   <span data-ttu-id="ae244-136">Use um destes dois métodos para codificar um identificador do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ae244-136">Use one of two methods to encode a SQL Server identifier:</span></span>  
  
    -   <span data-ttu-id="ae244-137">Especifique o código hexadecimal para o caractere sem suporte que usa a sintaxe %XX, onde XX é o código hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ae244-137">Specify the hexadecimal code for the unsupported character using the syntax %XX, where XX is the hexadecimal code.</span></span>  
  
    -   <span data-ttu-id="ae244-138">Passe o identificador como uma cadeia de caracteres entre aspas para o cmdlet `Encode-Sqlname`</span><span class="sxs-lookup"><span data-stu-id="ae244-138">Pass the identifier as a quoted string to the `Encode-Sqlname` cmdlet</span></span>  
  
### <a name="examples-encoding"></a><span data-ttu-id="ae244-139">Exemplos (codificação)</span><span class="sxs-lookup"><span data-stu-id="ae244-139">Examples (Encoding)</span></span>  
 <span data-ttu-id="ae244-140">Este exemplo especifica a versão codificada do caractere ":" (%3A):</span><span class="sxs-lookup"><span data-stu-id="ae244-140">This example specifies the encoded version of the ":" character (%3A):</span></span>  
  
```  
Set-Location Table%3ATest  
```  
  
 <span data-ttu-id="ae244-141">Como alternativa, use **Encode-SqlName** para criar um nome com suporte no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae244-141">Alternatively, you can use **Encode-SqlName** to build a name supported by Windows PowerShell:</span></span>  
  
```powershell
Set-Location (Encode-SqlName "Table:Test")  
```  
  
##  <a name="decoding-an-identifier"></a><a name="DecodeIdent"></a> <span data-ttu-id="ae244-142">Decodificando um Identificador</span><span class="sxs-lookup"><span data-stu-id="ae244-142">Decoding an Identifier</span></span>  
 <span data-ttu-id="ae244-143">**Para decodificar um identificador do SQL Server de um caminho do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ae244-143">**To decode a SQL Server identifier from a PowerShell path**</span></span>  
  
 <span data-ttu-id="ae244-144">Use o cmdlet `Decode-Sqlname` para substituir as codificações hexadecimais pelos caracteres representados pela codificação.</span><span class="sxs-lookup"><span data-stu-id="ae244-144">Use the `Decode-Sqlname` cmdlet to replace the hexadecimal encodings with the characters represented by the encoding.</span></span>  
  
### <a name="examples-decoding"></a><span data-ttu-id="ae244-145">Exemplos (decodificação)</span><span class="sxs-lookup"><span data-stu-id="ae244-145">Examples (Decoding)</span></span>  
 <span data-ttu-id="ae244-146">Este exemplo retorna "Table:Test":</span><span class="sxs-lookup"><span data-stu-id="ae244-146">This example returns "Table:Test":</span></span>  
  
```powershell
Decode-SqlName "Table%3ATest"  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae244-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae244-147">See Also</span></span>  
 <span data-ttu-id="ae244-148">[Identificadores de SQL Server no PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="ae244-148">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="ae244-149">[Provedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="ae244-149">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="ae244-150">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae244-150">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
