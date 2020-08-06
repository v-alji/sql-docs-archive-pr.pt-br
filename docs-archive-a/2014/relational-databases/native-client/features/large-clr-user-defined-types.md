---
title: Tipos definidos pelo usuário CLR grandes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
ms.assetid: b65eb61d-ccf6-49c0-98e7-9a4ef4b2f790
author: rothja
ms.author: jroth
ms.openlocfilehash: 27f0c13caea8c4aca63d78238509c6d05f1bf7bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679913"
---
# <a name="large-clr-user-defined-types"></a><span data-ttu-id="fdd40-102">Tipos de dados CLR grandes definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="fdd40-102">Large CLR User-Defined Types</span></span>
  <span data-ttu-id="fdd40-103">No SQL Server 2005, os UDTs (tipos definidos pelo usuário) no CLR (Common Language Runtime) eram restritos a 8.000 bytes de tamanho.</span><span class="sxs-lookup"><span data-stu-id="fdd40-103">In SQL Server 2005, user-defined types (UDTs) in the common language runtime (CLR) were restricted to 8,000 bytes in size.</span></span> <span data-ttu-id="fdd40-104">Essa restrição foi eliminada no [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] e em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="fdd40-104">This restriction has been lifted in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions.</span></span> <span data-ttu-id="fdd40-105">Os UDTs CLR agora são tratados de maneira semelhante aos tipos LOB (objeto grande).</span><span class="sxs-lookup"><span data-stu-id="fdd40-105">CLR UDTs are now treated in a similar way to large object (LOB) types.</span></span> <span data-ttu-id="fdd40-106">Ou seja, os UDTs inferiores ou iguais a 8.000 bytes têm o mesmo comportamento que no SQL Server 2005, mas são suportados UDTs maiores que informam seu tamanho como "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="fdd40-106">That is, UDTs less than or equal to 8,000 bytes behave the same way as in SQL Server 2005, but larger UDTs are supported and report their size as "unlimited".</span></span>  
  
 <span data-ttu-id="fdd40-107">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) e [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fdd40-107">For more information, see [Large CLR User-Defined Types &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) and [Large CLR User-Defined Types &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="use-cases"></a><span data-ttu-id="fdd40-108">Casos de uso</span><span class="sxs-lookup"><span data-stu-id="fdd40-108">Use Cases</span></span>  
 <span data-ttu-id="fdd40-109">Para o ODBC, o suporte a UDTs grandes inclui a capacidade de enviar valores UDT em partes como parâmetros de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="fdd40-109">For ODBC, support for large UDTs includes the ability to send UDT values in pieces as data-at-execution parameters.</span></span> <span data-ttu-id="fdd40-110">Isso é feito usando SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="fdd40-110">This is done by using SQLPutData.</span></span>  
  
 <span data-ttu-id="fdd40-111">Para o OLE DB, o suporte a UDTs grandes inclui a capacidade de transmitir valores UDT bidirecionalmente no servidor usando a associação ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="fdd40-111">For OLE DB, support for large UDTs includes the ability to stream UDT values to and from the server by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="fdd40-112">Os UDTs inferiores ou iguais a 8.000 bytes se comportarão como no SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="fdd40-112">UDTs less than or equal to 8,000 bytes will behave as they did in SQL Server 2005.</span></span> <span data-ttu-id="fdd40-113">Para o OLE DB, você ainda pode transmitir UDTs pequenos usando a associação ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="fdd40-113">For OLE DB, you can still stream small UDTs by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="fdd40-114">Às vezes, o código nativo terá de entender o conteúdo dos UDTs CLR, mas não terão de criar uma instância dos objetos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="fdd40-114">Sometimes native code will have to understand the contents of CLR UDTs, but will not have to instantiate managed objects.</span></span> <span data-ttu-id="fdd40-115">Se esse for o caso, você poderá usar serialização personalizada para converter valores UDT no servidor em um formato bem conhecido para os clientes.</span><span class="sxs-lookup"><span data-stu-id="fdd40-115">If this is the case, you can use custom serialization to convert UDT values on the server into a well known format for clients.</span></span>  
  
 <span data-ttu-id="fdd40-116">Para aplicativos com código de acesso a dados existente, você pode explorar o comportamento de UDTs CLR no cliente recuperando UDTs através de APIs nativas e criando instâncias deles com C++ CLI interop em aplicativos de modo misto.</span><span class="sxs-lookup"><span data-stu-id="fdd40-116">For applications that have existing data access code, you can exploit CLR UDT behavior on the client by retrieving UDTs through native APIs and instantiating them by using C++ CLI interop in mixed mode applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd40-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fdd40-117">See Also</span></span>  
 [<span data-ttu-id="fdd40-118">Recursos do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="fdd40-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
