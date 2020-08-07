---
title: Função LocalDBCreateInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBCreateInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 3eebb485-8a53-4a79-82a9-57b8de9f8e84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ff822c552176ad8c083a1c8ea6c0f2430f72972f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576413"
---
# <a name="localdbcreateinstance-function"></a><span data-ttu-id="f0aba-102">Função LocalDBCreateInstance</span><span class="sxs-lookup"><span data-stu-id="f0aba-102">LocalDBCreateInstance Function</span></span>
  <span data-ttu-id="f0aba-103">Cria uma nova instância de LocalDB do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f0aba-103">Creates a new SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="f0aba-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="f0aba-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0aba-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f0aba-105">Syntax</span></span>  
  
```  
HRESULT LocalDBCreateInstance(  
           PCWSTR wszVersion,  
           PCWSTR pInstanceName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0aba-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f0aba-106">Parameters</span></span>  
 <span data-ttu-id="f0aba-107">*wszVersion*</span><span class="sxs-lookup"><span data-stu-id="f0aba-107">*wszVersion*</span></span>  
 <span data-ttu-id="f0aba-108">[Entrada] A versão LocalDB, por exemplo 11.0 ou 11.0.1094.2.</span><span class="sxs-lookup"><span data-stu-id="f0aba-108">[Input] The LocalDB version, for example 11.0 or 11.0.1094.2.</span></span>  
  
 <span data-ttu-id="f0aba-109">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="f0aba-109">*pInstanceName*</span></span>  
 <span data-ttu-id="f0aba-110">[Entrada] O nome para a instância de LocalDB ser criada.</span><span class="sxs-lookup"><span data-stu-id="f0aba-110">[Input] The name for the LocalDB instance to create.</span></span>  
  
 <span data-ttu-id="f0aba-111">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="f0aba-111">*dwFlags*</span></span>  
 <span data-ttu-id="f0aba-112">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f0aba-112">[Input] Reserved for future use.</span></span> <span data-ttu-id="f0aba-113">Atualmente deve ser definido como 0.</span><span class="sxs-lookup"><span data-stu-id="f0aba-113">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f0aba-114">Retornos</span><span class="sxs-lookup"><span data-stu-id="f0aba-114">Returns</span></span>  
 <span data-ttu-id="f0aba-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0aba-115">S_OK</span></span>  
 <span data-ttu-id="f0aba-116">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f0aba-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="f0aba-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f0aba-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="f0aba-118">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="f0aba-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="f0aba-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="f0aba-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="f0aba-120">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="f0aba-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="f0aba-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="f0aba-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="f0aba-122">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="f0aba-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="f0aba-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="f0aba-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="f0aba-124">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="f0aba-124">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="f0aba-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="f0aba-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>](../express-localdb-error-messages/localdb-error-instance-exists-with-lower-version.md)  
 <span data-ttu-id="f0aba-126">A instância especificada já existe, mas sua versão é inferior à solicitada.</span><span class="sxs-lookup"><span data-stu-id="f0aba-126">The specified instance already exists but its version is lower than requested.</span></span>  
  
 [<span data-ttu-id="f0aba-127">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="f0aba-127">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="f0aba-128">A versão especificada não está disponível.</span><span class="sxs-lookup"><span data-stu-id="f0aba-128">The specified version is not available.</span></span>  
  
 [<span data-ttu-id="f0aba-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f0aba-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-version-requested-not-installed.md)  
 <span data-ttu-id="f0aba-130">O nível de patch especificado não está instalado.</span><span class="sxs-lookup"><span data-stu-id="f0aba-130">The specified patch level is not installed.</span></span>  
  
 [<span data-ttu-id="f0aba-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f0aba-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-instance-folder.md)  
 <span data-ttu-id="f0aba-132">Uma pasta não pode ser criada abaixo de %userprofile%.</span><span class="sxs-lookup"><span data-stu-id="f0aba-132">A folder cannot be created under %userprofile%.</span></span>  
  
 [<span data-ttu-id="f0aba-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f0aba-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="f0aba-134">Não é possível recuperar uma pasta de perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="f0aba-134">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="f0aba-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f0aba-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="f0aba-136">Não é possível acessar uma pasta de instância.</span><span class="sxs-lookup"><span data-stu-id="f0aba-136">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="f0aba-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="f0aba-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="f0aba-138">Não é possível acessar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="f0aba-138">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="f0aba-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="f0aba-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="f0aba-140">Não é possível modificar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="f0aba-140">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="f0aba-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="f0aba-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="f0aba-142">Um processo do SQL Server foi iniciado, mas houve falha na inicialização do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f0aba-142">A SQL Server process is started but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="f0aba-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="f0aba-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="f0aba-144">Uma configuração de instância está corrompida.</span><span class="sxs-lookup"><span data-stu-id="f0aba-144">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="f0aba-145">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="f0aba-145">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="f0aba-146">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="f0aba-146">An unexpected error occurred.</span></span> <span data-ttu-id="f0aba-147">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="f0aba-147">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0aba-148">Comentários</span><span class="sxs-lookup"><span data-stu-id="f0aba-148">Remarks</span></span>  
 <span data-ttu-id="f0aba-149">Se uma instância de LocalDB completamente funcional com o nome especificado já existir e sua versão for igual a ou mais alta que a solicitada, o resultado será S_OK.</span><span class="sxs-lookup"><span data-stu-id="f0aba-149">If a fully functional LocalDB instance with the specified name already exists and its version is equal to or higher than requested, the result is S_OK.</span></span>  
  
 <span data-ttu-id="f0aba-150">Em casos em que uma instância existente torna-se corrompida, chamadas subsequentes para a API do método `LocalDBCreateInstance` falharão.</span><span class="sxs-lookup"><span data-stu-id="f0aba-150">In cases when an existing instance becomes corrupted, subsequent calls to the `LocalDBCreateInstance` API method will fail.</span></span> <span data-ttu-id="f0aba-151">As instâncias corrompidas devem ser corrigidas manualmente ou explicitamente excluídas antes de poderem ser usadas novamente.</span><span class="sxs-lookup"><span data-stu-id="f0aba-151">Corrupted instances must be fixed manually or explicitly deleted before they can be used again.</span></span>  
  
 <span data-ttu-id="f0aba-152">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f0aba-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0aba-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0aba-153">See Also</span></span>  
 [<span data-ttu-id="f0aba-154">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f0aba-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
