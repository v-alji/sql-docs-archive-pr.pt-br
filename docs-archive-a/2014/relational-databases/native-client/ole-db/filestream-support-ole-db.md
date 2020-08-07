---
title: Suporte a FILESTREAM (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: rothja
ms.author: jroth
ms.openlocfilehash: cde3c2cd1b72773cfcf17eacedeb3276dd2f63da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575795"
---
# <a name="filestream-support-ole-db"></a><span data-ttu-id="86d12-102">Suporte a FILESTREAM (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="86d12-102">FILESTREAM Support (OLE DB)</span></span>
  <span data-ttu-id="86d12-103">A partir [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do e do cliente nativo 10,0, o OLE DB dá suporte ao recurso FileStream avançado.</span><span class="sxs-lookup"><span data-stu-id="86d12-103">Beginning with [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, OLE DB supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="86d12-104">Para obter mais informações sobre esse recurso, consulte [suporte a FileStream](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="86d12-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="86d12-105">Para ver exemplos, confira [Fluxo de arquivos e OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="86d12-105">For samples, see [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span></span>  
  
 <span data-ttu-id="86d12-106">Para enviar e receber valores `varbinary(max)` maiores do que 2 GB, um aplicativo usa `DBTYPE_IUNKNOWN` em associações de parâmetro e resultado.</span><span class="sxs-lookup"><span data-stu-id="86d12-106">To send and receive `varbinary(max)` values greater than 2 GB, an application uses `DBTYPE_IUNKNOWN` in parameter and result bindings.</span></span> <span data-ttu-id="86d12-107">Para os parâmetros, o provedor precisa chamar IUnknown::QueryInterface para ISequentialStream e os resultados que retornam ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="86d12-107">For parameters the provider must call IUnknown::QueryInterface for ISequentialStream and for results that return ISequentialStream.</span></span>  
  
 <span data-ttu-id="86d12-108">Para o OLE DB, a verificação relacionada aos valores ISequentialStream será aliviada.</span><span class="sxs-lookup"><span data-stu-id="86d12-108">For OLE DB, checking related to ISequentialStream values will be relaxed.</span></span> <span data-ttu-id="86d12-109">Quando *wType* está `DBTYPE_IUNKNOWN` na `DBBINDING` struct, a verificação de comprimento pode ser desabilitada omitindo `DBPART_LENGTH` de *dwPart* ou definindo o comprimento dos dados (no deslocamento *obLength* no buffer de dados) para ~ 0.</span><span class="sxs-lookup"><span data-stu-id="86d12-109">When *wType* is `DBTYPE_IUNKNOWN` in the `DBBINDING` struct, length checking can be disabled either by omitting `DBPART_LENGTH` from *dwPart* or by setting the length of the data (at offset *obLength* in the data buffer) to ~0.</span></span> <span data-ttu-id="86d12-110">Nesse caso, o provedor não verificará o comprimento do valor, e solicitará e retornará todos os dados disponíveis através do fluxo.</span><span class="sxs-lookup"><span data-stu-id="86d12-110">In this case, the provider will not check the length of the value and will request and return all of the data available through the stream.</span></span> <span data-ttu-id="86d12-111">Essa alteração será aplicada a todos os tipos LOB (objeto grande) e XML, mas somente quando conectados a servidores [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (ou posterior).</span><span class="sxs-lookup"><span data-stu-id="86d12-111">This change will be applied to all large object (LOB) types and XML, but only when connected to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (or later) servers.</span></span> <span data-ttu-id="86d12-112">Isso oferecerá maior flexibilidade para desenvolvedores, ao mesmo tempo mantendo a consistência e compatibilidade com aplicativos e servidores de versões anteriores existentes.</span><span class="sxs-lookup"><span data-stu-id="86d12-112">This will provide greater flexibility for developers, while maintaining consistency and backwards compatibility for existing applications and downlevel servers.</span></span>  
  
 <span data-ttu-id="86d12-113">Essa alteração afeta todas as interfaces que transferem dados, principalmente IRowset::GetData, ICommand::Execute e IRowsetFastLoad::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="86d12-113">This change affects all interfaces that transfer data, principally IRowset::GetData, ICommand::Execute, and IRowsetFastLoad::InsertRow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d12-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86d12-114">See Also</span></span>  
 [<span data-ttu-id="86d12-115">Programação do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="86d12-115">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
