---
title: Suporte a FOR XML para os UDTs (tipos de dados definidos pelo usuário) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- UDTs [SQL Server], XML
- user-defined types [SQL Server], XML
ms.assetid: 354e2150-fa2a-4583-b1aa-6b78ae4378b6
author: rothja
ms.author: jroth
ms.openlocfilehash: b668ad2da13fdfc880ab26cb2b2759ff3693f7d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686189"
---
# <a name="for-xml-support-for-the-user-defined-data-types-udt"></a><span data-ttu-id="57bb8-102">Suporte a FOR XML para os UDTs (tipos de dados definidos pelo usuário)</span><span class="sxs-lookup"><span data-stu-id="57bb8-102">FOR XML Support for the User-Defined Data Types (UDT)</span></span>
  <span data-ttu-id="57bb8-103">FOR XML não oferece suporte a UDTs (tipos de dados definidos pelo usuário) do CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="57bb8-103">FOR XML does not support common language runtime (CLR) user-defined data types (UDTs).</span></span>  
  
 <span data-ttu-id="57bb8-104">Para usar FOR XML com tipos definidos pelo usuário do CLR, verifique se o tipo de dados tem uma serialização XML e usa uma conversão explícita para XML na cláusula select de FOR XML.</span><span class="sxs-lookup"><span data-stu-id="57bb8-104">To use FOR XML with CLR user-defined data types, make sure that the data type has an XML serialization, and use an explicit cast to XML in the FOR XML select clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bb8-105">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57bb8-105">See Also</span></span>  
 [<span data-ttu-id="57bb8-106">Suporte a FOR XML para vários tipos de dados de SQL Server</span><span class="sxs-lookup"><span data-stu-id="57bb8-106">FOR XML Support for Various SQL Server Data Types</span></span>](for-xml-support-for-various-sql-server-data-types.md)  
  
  
