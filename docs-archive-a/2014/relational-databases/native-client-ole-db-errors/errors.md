---
title: Erros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: rothja
ms.author: jroth
ms.openlocfilehash: 0560a31b60a10e278f621aa53f1c7fa038fe8039
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581794"
---
# <a name="errors"></a><span data-ttu-id="f3154-102">Errors</span><span class="sxs-lookup"><span data-stu-id="f3154-102">Errors</span></span>
  <span data-ttu-id="f3154-103">Os objetos OLE/COM informam erros através do código de retorno de HRESULT das funções de membro de objeto.</span><span class="sxs-lookup"><span data-stu-id="f3154-103">OLE/COM objects report errors through the HRESULT return code of object member functions.</span></span> <span data-ttu-id="f3154-104">Um HRESULT de OLE/COM é uma estrutura de bits compactados.</span><span class="sxs-lookup"><span data-stu-id="f3154-104">An OLE/COM HRESULT is a bit-packed structure.</span></span> <span data-ttu-id="f3154-105">A OLE fornece macros que eliminam a referência de membros de estrutura.</span><span class="sxs-lookup"><span data-stu-id="f3154-105">OLE provides macros that dereference structure members.</span></span>  
  
 <span data-ttu-id="f3154-106">O OLE/COM especifica a interface **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="f3154-106">OLE/COM specifies the **IErrorInfo** interface.</span></span> <span data-ttu-id="f3154-107">A interface expõe métodos como **GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="f3154-107">The interface exposes methods such as **GetDescription**.</span></span> <span data-ttu-id="f3154-108">Isso permite que clientes extraiam detalhes de erros dos servidores OLE/COM.</span><span class="sxs-lookup"><span data-stu-id="f3154-108">This allows clients to extract error details from OLE/COM servers.</span></span> <span data-ttu-id="f3154-109">O OLE DB estende **IErrorInfo** para dar suporte ao retorno de vários pacotes de informações de erros em uma execução de função de único membro.</span><span class="sxs-lookup"><span data-stu-id="f3154-109">OLE DB extends **IErrorInfo** to support the return of multiple error information packets on a single-member function execution.</span></span>  
  
 <span data-ttu-id="f3154-110">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode retornar vários erros.</span><span class="sxs-lookup"><span data-stu-id="f3154-110">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can return multiple errors.</span></span> <span data-ttu-id="f3154-111">Um aplicativo pode recuperar erros do servidor um de cada vez chamando [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combinado com ISQLErrorInfo e IErrorRecords.</span><span class="sxs-lookup"><span data-stu-id="f3154-111">An application can retrieve server errors one at a time by calling [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combined with ISQLErrorInfo and IErrorRecords.</span></span>  
  
 <span data-ttu-id="f3154-112">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe as interfaces OLE DB de objeto de erro ISQLServerErrorInfo de registro **IErrorInfo**, personalizadas `ISQLErrorInfo` e específicas do provedor. [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md)</span><span class="sxs-lookup"><span data-stu-id="f3154-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the OLE DB record-enhanced **IErrorInfo**, the custom `ISQLErrorInfo`, and the provider-specific [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) error object interfaces.</span></span>  
  
 <span data-ttu-id="f3154-113">Para obter informações sobre como rastrear erros, confira [Rastreamento do acesso a dados](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="f3154-113">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="f3154-114">Para obter informações sobre aprimoramentos no rastreamento de erros adicionados em [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], confira [Acessar informações de diagnóstico nos logs de eventos estendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="f3154-114">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3154-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f3154-115">In This Section</span></span>  
  
-   [<span data-ttu-id="f3154-116">Códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="f3154-116">Return Codes</span></span>](return-codes.md)  
  
-   [<span data-ttu-id="f3154-117">Informações em interfaces de erro</span><span class="sxs-lookup"><span data-stu-id="f3154-117">Information in Error Interfaces</span></span>](information-in-error-interfaces.md)  
  
-   [<span data-ttu-id="f3154-118">Detalhes de erros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3154-118">SQL Server Error Detail</span></span>](sql-server-error-detail.md)  
  
-   [<span data-ttu-id="f3154-119">Recuperando informações de erro</span><span class="sxs-lookup"><span data-stu-id="f3154-119">Retrieving Error Information</span></span>](retrieving-error-information.md)  
  
-   [<span data-ttu-id="f3154-120">Resultados da mensagem do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3154-120">SQL Server Message Results</span></span>](sql-server-message-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="f3154-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3154-121">See Also</span></span>  
 [<span data-ttu-id="f3154-122">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f3154-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
