---
title: Função LocalDBGetInstanceInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstanceInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 231706f5-26c6-42eb-ab47-315df6b8f824
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dc7cbe2c59a7502a1fd0c8b4f92fb14e5defd50b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571402"
---
# <a name="localdbgetinstanceinfo-function"></a><span data-ttu-id="25d36-102">Função LocalDBGetInstanceInfo</span><span class="sxs-lookup"><span data-stu-id="25d36-102">LocalDBGetInstanceInfo Function</span></span>
  <span data-ttu-id="25d36-103">Retorna informações sobre a instância de LocalDB do SQL Server Express especificada, como se existe ou não, a versão do LocalDB usada, se está sendo executada ou não, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="25d36-103">Returns information for the specified SQL Server Express LocalDB instance, such as whether it exists, the LocalDB version it uses, whether it is running, and so on.</span></span>  
  
 <span data-ttu-id="25d36-104">As informações são retornadas em `struct` um **LocalDBInstanceInfo**nomeado, que tem a definição a seguir.</span><span class="sxs-lookup"><span data-stu-id="25d36-104">The information is returned in a `struct` named **LocalDBInstanceInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBInstanceInfo  
{  
      // Contains the size of the LocalDBInstanceInfo struct  
      DWORD  cbLocalDBInstanceInfoSize;  
  
      // Holds the instance name  
      TLocalDBInstanceNamewszInstanceName;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // TRUE if the instance configuration registry is corrupted, FALSE otherwise  
      BOOLbConfigurationCorrupted;  
  
      // TRUE if the instance is running at the moment, FALSE otherwise  
      BOOL   bIsRunning;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
  
      // Holds the date and time when the instance was started for the last time  
      FILETIME ftLastStartUTC;  
  
      // Holds the name of the TDS named pipe to connect to the instance  
      WCHARwszConnection;  
  
      // TRUE if the instance is shared, FALSE otherwise  
      BOOLbIsShared;  
  
      // Holds the shared name for the instance (if the instance is shared)  
      TLocalDBInstanceNamewszSharedInstanceName;  
  
      // Holds the SID of the instance owner (if the instance is shared)  
      WCHARwszOwnerSID;   
  
      // TRUE if the instance is Automatic, FALSE otherwise  
      BOOLbIsAutomatic;  
} LocalDBInstanceInfo;  
  
```  
  
 <span data-ttu-id="25d36-105">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="25d36-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d36-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25d36-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetInstanceInfo(  
           PCWSTR wszInstanceName,  
           PLocalDBInstanceInfo pInstanceInfo,  
           DWORD dwInstanceInfoSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25d36-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="25d36-107">Parameters</span></span>  
 <span data-ttu-id="25d36-108">*wszInstanceName*</span><span class="sxs-lookup"><span data-stu-id="25d36-108">*wszInstanceName*</span></span>  
 <span data-ttu-id="25d36-109">[Entrada] O nome da instância.</span><span class="sxs-lookup"><span data-stu-id="25d36-109">[Input] The instance name.</span></span>  
  
 <span data-ttu-id="25d36-110">*pInstanceInfo*</span><span class="sxs-lookup"><span data-stu-id="25d36-110">*pInstanceInfo*</span></span>  
 <span data-ttu-id="25d36-111">[Saída] O buffer para armazenar as informações sobre a instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="25d36-111">[Output] The buffer to store the information about the LocalDB instance.</span></span>  
  
 <span data-ttu-id="25d36-112">*dwInstanceInfoSize*</span><span class="sxs-lookup"><span data-stu-id="25d36-112">*dwInstanceInfoSize*</span></span>  
 <span data-ttu-id="25d36-113">Entrada Mantém o tamanho do buffer *InstanceInfo* .</span><span class="sxs-lookup"><span data-stu-id="25d36-113">[Input] Holds the size of the *InstanceInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="25d36-114">Retornos</span><span class="sxs-lookup"><span data-stu-id="25d36-114">Returns</span></span>  
 <span data-ttu-id="25d36-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="25d36-115">S_OK</span></span>  
 <span data-ttu-id="25d36-116">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="25d36-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="25d36-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="25d36-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="25d36-118">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="25d36-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="25d36-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="25d36-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="25d36-120">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="25d36-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="25d36-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="25d36-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="25d36-122">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="25d36-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="25d36-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="25d36-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="25d36-124">A instância não existe.</span><span class="sxs-lookup"><span data-stu-id="25d36-124">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="25d36-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="25d36-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="25d36-126">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="25d36-126">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="25d36-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="25d36-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="25d36-128">Não é possível acessar uma pasta de instância.</span><span class="sxs-lookup"><span data-stu-id="25d36-128">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="25d36-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="25d36-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="25d36-130">Não é possível acessar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="25d36-130">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="25d36-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="25d36-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="25d36-132">Uma configuração de instância está corrompida.</span><span class="sxs-lookup"><span data-stu-id="25d36-132">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="25d36-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="25d36-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="25d36-134">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="25d36-134">An unexpected error occurred.</span></span> <span data-ttu-id="25d36-135">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="25d36-135">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="25d36-136">Detalhes</span><span class="sxs-lookup"><span data-stu-id="25d36-136">Details</span></span>  
 <span data-ttu-id="25d36-137">A lógica por trás da introdução do `struct` argumento de tamanho (*lpInstanceInfoSize*) é permitir que a API retorne versões diferentes do **LocalDBInstanceInfostruct**, habilitando efetivamente a compatibilidade com versões anteriores e posteriores.</span><span class="sxs-lookup"><span data-stu-id="25d36-137">The rationale behind the introduction of the `struct` size argument (*lpInstanceInfoSize*) is to enable the API to return different versions of the **LocalDBInstanceInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="25d36-138">Se o `struct` argumento Size (*lpInstanceInfoSize*) corresponder ao tamanho de uma versão conhecida do **LocalDBInstanceInfostruct**, essa versão do `struct` será retornada.</span><span class="sxs-lookup"><span data-stu-id="25d36-138">If the `struct` size argument (*lpInstanceInfoSize*) matches the size of a known version of the **LocalDBInstanceInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="25d36-139">Caso contrário, LOCALDB_ERROR_INVALID_PARAMETER será retornado.</span><span class="sxs-lookup"><span data-stu-id="25d36-139">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="25d36-140">Um exemplo típico de uso da API **LocalDBGetInstanceInfo** é semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="25d36-140">A typical example of **LocalDBGetInstanceInfo** API usage looks like this:</span></span>  
  
```  
LocalDBInstanceInfo ii;  
LocalDBInstanceInfo(L"Test", &ii, sizeof(LocalDBInstanceInfo));  
  
```  
  
 <span data-ttu-id="25d36-141">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="25d36-141">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d36-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25d36-142">See Also</span></span>  
 [<span data-ttu-id="25d36-143">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="25d36-143">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
