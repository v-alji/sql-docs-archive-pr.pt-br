---
title: Nomes de fontes de dados e sistemas operacionais de 64 bits | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: c2f86810-2775-4ddd-8df7-e8373785a7fc
author: rothja
ms.author: jroth
ms.openlocfilehash: ae31584ca3c076919f688d1ef9bdef80706c6940
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571362"
---
# <a name="data-source-names-and-64-bit-operating-systems"></a><span data-ttu-id="cf45a-102">Nomes de fonte de dados e sistemas operacionais de 64 bits</span><span class="sxs-lookup"><span data-stu-id="cf45a-102">Data Source Names and 64-Bit Operating Systems</span></span>
  <span data-ttu-id="cf45a-103">Para compilar e executar um aplicativo como sendo de 32 bits em um sistema operacional de 64 bits, você precisa criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="cf45a-103">To build and run an application as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf45a-104">Comentários</span><span class="sxs-lookup"><span data-stu-id="cf45a-104">Remarks</span></span>  
 <span data-ttu-id="cf45a-105">Um sistema operacional Windows de 64 bits tem dois arquivos odbcad32.exe:</span><span class="sxs-lookup"><span data-stu-id="cf45a-105">A 64-bit Windows operating system has two odbcad32.exe files:</span></span>  
  
-   <span data-ttu-id="cf45a-106">%SystemRoot%\system32\odbcad32.exe é usado criar e manter nomes da fonte de dados para aplicativos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="cf45a-106">%SystemRoot%\system32\odbcad32.exe is used to create and maintain data source names for 64-bit applications.</span></span>  
  
-   <span data-ttu-id="cf45a-107">%SystemRoot%\SysWOW64\odbcad32.exe é usado criar e manter nomes da fonte de dados para aplicativos de 32 bits, incluindo aplicativos de 32 bits que são executados em sistemas operacionais de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="cf45a-107">%SystemRoot%\SysWOW64\odbcad32.exe is used to create and maintain data source names for 32-bit applications, including 32-bit applications that run on 64-bit operating systems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf45a-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cf45a-108">See Also</span></span>  
 [<span data-ttu-id="cf45a-109">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cf45a-109">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
