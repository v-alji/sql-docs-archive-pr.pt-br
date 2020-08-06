---
title: Função LocalDBGetVersionInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersionInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: d4aaea30-1d0d-4436-bcdc-5c101d27b1c1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e30bb4dcd4c258db899883f650dbfe7100171ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685720"
---
# <a name="localdbgetversioninfo-function"></a><span data-ttu-id="11d3b-102">Função LocalDBGetVersionInfo</span><span class="sxs-lookup"><span data-stu-id="11d3b-102">LocalDBGetVersionInfo Function</span></span>
  <span data-ttu-id="11d3b-103">Retorna informações sobre a versão de LocalDB do SQL Server Express especificada, como se existe ou não, e o número da versão total do LocalDB (incluindo números de versão e compilação).</span><span class="sxs-lookup"><span data-stu-id="11d3b-103">Returns information for the specified SQL Server Express LocalDB version, such as whether it exists and the full LocalDB version number (including build and release numbers).</span></span>  
  
 <span data-ttu-id="11d3b-104">As informações são retornadas na forma de um `struct` **LocalDBVersionInfo**nomeado, que tem a definição a seguir.</span><span class="sxs-lookup"><span data-stu-id="11d3b-104">The information is returned in the form of a `struct` named **LocalDBVersionInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBVersionInfo  
{  
      // Contains the size of the LocalDBVersionInfo struct  
      DWORD  cbLocalDBVersionInfoSize;  
  
      // Holds the version name  
      TLocalDBVersionwszVersion;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
} LocalDBVersionInfo;  
  
```  
  
 <span data-ttu-id="11d3b-105">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="11d3b-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d3b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11d3b-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetVersionInfo(  
           PCWSTR wszVersionName,           PLocalDBVersionInfo pVersionInfo,           DWORD dwVersionInfoSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11d3b-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="11d3b-107">Parameters</span></span>  
 <span data-ttu-id="11d3b-108">*wszVersionName*</span><span class="sxs-lookup"><span data-stu-id="11d3b-108">*wszVersionName*</span></span>  
 <span data-ttu-id="11d3b-109">[Entrada] O nome de versão de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="11d3b-109">[Input] The LocalDB version name.</span></span>  
  
 <span data-ttu-id="11d3b-110">*pVersionInfo*</span><span class="sxs-lookup"><span data-stu-id="11d3b-110">*pVersionInfo*</span></span>  
 <span data-ttu-id="11d3b-111">[Saída] O buffer para armazenar as informações sobre a versão de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="11d3b-111">[Output] The buffer to store the information about the LocalDB version.</span></span>  
  
 <span data-ttu-id="11d3b-112">*dwVersionInfoSize*</span><span class="sxs-lookup"><span data-stu-id="11d3b-112">*dwVersionInfoSize*</span></span>  
 <span data-ttu-id="11d3b-113">Entrada Mantém o tamanho do buffer *VERSIONINFO* .</span><span class="sxs-lookup"><span data-stu-id="11d3b-113">[Input] Holds the size of the *VersionInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="11d3b-114">Retornos</span><span class="sxs-lookup"><span data-stu-id="11d3b-114">Returns</span></span>  
 <span data-ttu-id="11d3b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="11d3b-115">S_OK</span></span>  
 <span data-ttu-id="11d3b-116">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="11d3b-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="11d3b-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="11d3b-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="11d3b-118">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="11d3b-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="11d3b-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="11d3b-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="11d3b-120">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="11d3b-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="11d3b-121">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="11d3b-121">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="11d3b-122">A versão de LocalDB especificada não existe.</span><span class="sxs-lookup"><span data-stu-id="11d3b-122">The specified LocalDB version does not exist.</span></span>  
  
 [<span data-ttu-id="11d3b-123">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="11d3b-123">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="11d3b-124">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="11d3b-124">An unexpected error occurred.</span></span> <span data-ttu-id="11d3b-125">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="11d3b-125">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11d3b-126">Detalhes</span><span class="sxs-lookup"><span data-stu-id="11d3b-126">Details</span></span>  
 <span data-ttu-id="11d3b-127">A lógica por trás da introdução do `struct` argumento de tamanho (*lpVersionInfoSize*) é permitir que a API retorne versões diferentes do **LocalDBVersionInfostruct**, habilitando efetivamente a compatibilidade com versões anteriores e posteriores.</span><span class="sxs-lookup"><span data-stu-id="11d3b-127">The rationale behind the introduction of the `struct` size argument (*lpVersionInfoSize*) is to enable the API to return different versions of the **LocalDBVersionInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="11d3b-128">Se o `struct` argumento Size (*lpVersionInfoSize*) corresponder ao tamanho de uma versão conhecida do **LocalDBVersionInfostruct**, essa versão do `struct` será retornada.</span><span class="sxs-lookup"><span data-stu-id="11d3b-128">If the `struct` size argument (*lpVersionInfoSize*) matches the size of a known version of the **LocalDBVersionInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="11d3b-129">Caso contrário, LOCALDB_ERROR_INVALID_PARAMETER será retornado.</span><span class="sxs-lookup"><span data-stu-id="11d3b-129">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="11d3b-130">Um exemplo típico de uso da API **LocalDBGetVersionInfo** é semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="11d3b-130">A typical example of **LocalDBGetVersionInfo** API usage looks like this:</span></span>  
  
```  
LocalDBVersionInfo vi;  
LocalDBVersionInfo(L"11.0", &vi, sizeof(LocalDBVersionInfo));  
  
```  
  
## <a name="remarks"></a><span data-ttu-id="11d3b-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="11d3b-131">Remarks</span></span>  
 <span data-ttu-id="11d3b-132">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="11d3b-132">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d3b-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11d3b-133">See Also</span></span>  
 [<span data-ttu-id="11d3b-134">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="11d3b-134">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
