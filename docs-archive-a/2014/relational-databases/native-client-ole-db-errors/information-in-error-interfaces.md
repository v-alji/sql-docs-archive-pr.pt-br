---
title: Informações em interfaces de erro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581790"
---
# <a name="information-in-error-interfaces"></a><span data-ttu-id="1795e-102">Informações em interfaces de erro</span><span class="sxs-lookup"><span data-stu-id="1795e-102">Information in Error Interfaces</span></span>
  <span data-ttu-id="1795e-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo relata algumas informações de erro e status nas interfaces de erro definidas pelo OLE DB **IErrorInfo**, **IErrorRecords**e **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="1795e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reports some error and status information in the OLE DB-defined error interfaces **IErrorInfo**, **IErrorRecords**, and **ISQLErrorInfo**.</span></span>  
  
 <span data-ttu-id="1795e-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte às funções membro **IErrorInfo** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="1795e-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IErrorInfo** member functions as follows.</span></span>  
  
|<span data-ttu-id="1795e-105">Função de membro</span><span class="sxs-lookup"><span data-stu-id="1795e-105">Member function</span></span>|<span data-ttu-id="1795e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="1795e-106">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="1795e-107">**GetDescription**</span><span class="sxs-lookup"><span data-stu-id="1795e-107">**GetDescription**</span></span>|<span data-ttu-id="1795e-108">Cadeia de caracteres de mensagem de erro descritiva.</span><span class="sxs-lookup"><span data-stu-id="1795e-108">Descriptive error message string.</span></span>|  
|<span data-ttu-id="1795e-109">**GetGUID**</span><span class="sxs-lookup"><span data-stu-id="1795e-109">**GetGUID**</span></span>|<span data-ttu-id="1795e-110">GUID da interface que definiu o erro.</span><span class="sxs-lookup"><span data-stu-id="1795e-110">GUID of the interface that defined the error.</span></span>|  
|<span data-ttu-id="1795e-111">**GetHelpContext**</span><span class="sxs-lookup"><span data-stu-id="1795e-111">**GetHelpContext**</span></span>|<span data-ttu-id="1795e-112">Sem suporte.</span><span class="sxs-lookup"><span data-stu-id="1795e-112">Not supported.</span></span> <span data-ttu-id="1795e-113">Sempre retorna zero.</span><span class="sxs-lookup"><span data-stu-id="1795e-113">Always returns zero.</span></span>|  
|<span data-ttu-id="1795e-114">**GetHelpFile**</span><span class="sxs-lookup"><span data-stu-id="1795e-114">**GetHelpFile**</span></span>|<span data-ttu-id="1795e-115">Sem suporte.</span><span class="sxs-lookup"><span data-stu-id="1795e-115">Not supported.</span></span> <span data-ttu-id="1795e-116">Sempre retorna NULL.</span><span class="sxs-lookup"><span data-stu-id="1795e-116">Always returns NULL.</span></span>|  
|<span data-ttu-id="1795e-117">**GetSource**</span><span class="sxs-lookup"><span data-stu-id="1795e-117">**GetSource**</span></span>|<span data-ttu-id="1795e-118">Cadeia de caracteres "Microsoft SQL Server Native Client".</span><span class="sxs-lookup"><span data-stu-id="1795e-118">String "Microsoft SQL Server Native Client".</span></span>|  
  
 <span data-ttu-id="1795e-119">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo oferece suporte a funções de membro **IErrorRecords** disponíveis para o consumidor da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="1795e-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports consumer-available **IErrorRecords** member functions as follows.</span></span>  
  
|<span data-ttu-id="1795e-120">Função de membro</span><span class="sxs-lookup"><span data-stu-id="1795e-120">Member function</span></span>|<span data-ttu-id="1795e-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="1795e-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="1795e-122">**GetBasicErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="1795e-122">**GetBasicErrorInfo**</span></span>|<span data-ttu-id="1795e-123">Preenche uma estrutura ERRORINFO com informações básica sobre um erro.</span><span class="sxs-lookup"><span data-stu-id="1795e-123">Fills an ERRORINFO structure with basic information about an error.</span></span> <span data-ttu-id="1795e-124">Uma estrutura ERRORINFO contém membros que identificam o valor de retorno HRESULT para o erro e o provedor e interface aos quais o erro se aplica.</span><span class="sxs-lookup"><span data-stu-id="1795e-124">An ERRORINFO structure contains members that identify the HRESULT return value for the error, and the provider and interface to which the error applies.</span></span>|  
|<span data-ttu-id="1795e-125">**GetCustomErrorObject**</span><span class="sxs-lookup"><span data-stu-id="1795e-125">**GetCustomErrorObject**</span></span>|<span data-ttu-id="1795e-126">Retorna uma referência em interfaces **ISQLErrorInfo** e [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="1795e-126">Returns a reference on interfaces **ISQLErrorInfo,** and [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span>|  
|<span data-ttu-id="1795e-127">**GetErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="1795e-127">**GetErrorInfo**</span></span>|<span data-ttu-id="1795e-128">Retorna uma referência em uma interface **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="1795e-128">Returns a reference on an **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="1795e-129">**GetErrorParameters**</span><span class="sxs-lookup"><span data-stu-id="1795e-129">**GetErrorParameters**</span></span>|<span data-ttu-id="1795e-130">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não retorna parâmetros para o consumidor por meio de **geterroparameters**.</span><span class="sxs-lookup"><span data-stu-id="1795e-130">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not return parameters to the consumer through **GetErrorParameters**.</span></span>|  
|<span data-ttu-id="1795e-131">**GetRecordCount**</span><span class="sxs-lookup"><span data-stu-id="1795e-131">**GetRecordCount**</span></span>|<span data-ttu-id="1795e-132">Contagem de registros de erro disponível.</span><span class="sxs-lookup"><span data-stu-id="1795e-132">Count of error records available.</span></span>|  
  
 <span data-ttu-id="1795e-133">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo oferece suporte aos parâmetros **ISQLErrorInfo:: GetSQLInfo** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="1795e-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ISQLErrorInfo::GetSQLInfo** parameters as follows.</span></span>  
  
|<span data-ttu-id="1795e-134">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="1795e-134">Parameter</span></span>|<span data-ttu-id="1795e-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="1795e-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1795e-136">*pbstrSQLState*</span><span class="sxs-lookup"><span data-stu-id="1795e-136">*pbstrSQLState*</span></span>|<span data-ttu-id="1795e-137">Retorna um valor SQLSTATE para o erro.</span><span class="sxs-lookup"><span data-stu-id="1795e-137">Returns a SQLSTATE value for the error.</span></span> <span data-ttu-id="1795e-138">São definidos valores SQLSTATE nas especificações SQL-92, ODBC ISO SQL e de API.</span><span class="sxs-lookup"><span data-stu-id="1795e-138">SQLSTATE values are defined in the SQL-92, ODBC and ISO SQL, and API specifications.</span></span> <span data-ttu-id="1795e-139">Nem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB nativo não definiu valores SQLSTATE específicos de implementação.</span><span class="sxs-lookup"><span data-stu-id="1795e-139">Neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defined implementation-specific SQLSTATE values.</span></span>|  
|<span data-ttu-id="1795e-140">*plNativeError*</span><span class="sxs-lookup"><span data-stu-id="1795e-140">*plNativeError*</span></span>|<span data-ttu-id="1795e-141">Retorna o número do erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de **master.dbo.sysmessages** quando disponível.</span><span class="sxs-lookup"><span data-stu-id="1795e-141">Returns the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number from **master.dbo.sysmessages** when available.</span></span> <span data-ttu-id="1795e-142">Os erros nativos estão disponíveis após uma tentativa bem-sucedida de inicializar uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonte de dados de provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="1795e-142">Native errors are available after a successful attempt to initialize a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source.</span></span> <span data-ttu-id="1795e-143">Antes da tentativa, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo sempre retorna zero.</span><span class="sxs-lookup"><span data-stu-id="1795e-143">Prior to the attempt, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider always returns zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1795e-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1795e-144">See Also</span></span>  
 [<span data-ttu-id="1795e-145">Erros</span><span class="sxs-lookup"><span data-stu-id="1795e-145">Errors</span></span>](errors.md)  
  
  
