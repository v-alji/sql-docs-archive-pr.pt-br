---
title: Função LocalDBStopInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 4bd73187-0aac-4f03-ac54-2b78e41917e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 48b014e65e0a02a5f866e5301b12dae3cd255b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678743"
---
# <a name="localdbstopinstance-function"></a><span data-ttu-id="610c3-102">Função LocalDBStopInstance</span><span class="sxs-lookup"><span data-stu-id="610c3-102">LocalDBStopInstance Function</span></span>
  <span data-ttu-id="610c3-103">Interrompe a execução da instância especificada de LocalDB do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="610c3-103">Stops the specified SQL Server Express LocalDB instance from running.</span></span>  
  
 <span data-ttu-id="610c3-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="610c3-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610c3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="610c3-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           ULONG ulTimeout   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="610c3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="610c3-106">Parameters</span></span>  
 <span data-ttu-id="610c3-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="610c3-107">*pInstanceName*</span></span>  
 <span data-ttu-id="610c3-108">[Entrada] O nome da instância de LocalDB a ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="610c3-108">[Input] The name of the LocalDB instance to stop.</span></span>  
  
 <span data-ttu-id="610c3-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="610c3-109">*dwFlags*</span></span>  
 <span data-ttu-id="610c3-110">[Entrada] Uma ou uma combinação dos valores de sinalizador que especificam o modo de parar a instância.</span><span class="sxs-lookup"><span data-stu-id="610c3-110">[Input] One or a combination of the flag values specifying the way to stop the instance.</span></span>  
  
 <span data-ttu-id="610c3-111">Sinalizadores disponíveis:</span><span class="sxs-lookup"><span data-stu-id="610c3-111">Available flags:</span></span>  
  
 <span data-ttu-id="610c3-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="610c3-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span></span>  
 <span data-ttu-id="610c3-113">Desligue imediatamente usando o comando do sistema operacional de eliminar processo.</span><span class="sxs-lookup"><span data-stu-id="610c3-113">Shut down immediately using the kill process operating system command.</span></span>  
  
 <span data-ttu-id="610c3-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span><span class="sxs-lookup"><span data-stu-id="610c3-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span></span>  
 <span data-ttu-id="610c3-115">Desligue usando a opção WITH NOWAIT do comando Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="610c3-115">Shut down using the WITH NOWAIT option Transact-SQL command.</span></span>  
  
 <span data-ttu-id="610c3-116">Se nenhum dos sinalizadores estiver definido, a instância de LocalDB será desligada usando o comando Transact-SQL SHUTDOWN.</span><span class="sxs-lookup"><span data-stu-id="610c3-116">If none of the flags is set, the LocalDB instance will be shut down using the SHUTDOWN Transact-SQL command.</span></span> <span data-ttu-id="610c3-117">Se ambos os sinalizadores estiverem definidos, o sinalizador LOCALDB_SHUTDOWN_KILL_PROCESS terá precedência.</span><span class="sxs-lookup"><span data-stu-id="610c3-117">If both flags are set, the LOCALDB_SHUTDOWN_KILL_PROCESS flag takes precedence.</span></span>  
  
 <span data-ttu-id="610c3-118">*ulTimeout*</span><span class="sxs-lookup"><span data-stu-id="610c3-118">*ulTimeout*</span></span>  
 <span data-ttu-id="610c3-119">[Entrada] O tempo em segundos que deve ser aguardado para essa operação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="610c3-119">[Input] The time in seconds to wait for this operation to complete.</span></span> <span data-ttu-id="610c3-120">Se este valor for 0, esta função retornará imediatamente sem aguardar que a instância LocalDB pare.</span><span class="sxs-lookup"><span data-stu-id="610c3-120">If this value is 0, this function will return immediately without waiting for the LocalDB instance to stop.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="610c3-121">Retornos</span><span class="sxs-lookup"><span data-stu-id="610c3-121">Returns</span></span>  
 <span data-ttu-id="610c3-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="610c3-122">S_OK</span></span>  
 <span data-ttu-id="610c3-123">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="610c3-123">The function succeeded.</span></span>  
  
 [<span data-ttu-id="610c3-124">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="610c3-124">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="610c3-125">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="610c3-125">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="610c3-126">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="610c3-126">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="610c3-127">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="610c3-127">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="610c3-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="610c3-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="610c3-129">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="610c3-129">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="610c3-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="610c3-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="610c3-131">A instância não existe.</span><span class="sxs-lookup"><span data-stu-id="610c3-131">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="610c3-132">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="610c3-132">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="610c3-133">Tempo limite esgotado durante tentativa de obtenção de bloqueios de sincronização.</span><span class="sxs-lookup"><span data-stu-id="610c3-133">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="610c3-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span><span class="sxs-lookup"><span data-stu-id="610c3-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-instance-stop-failed.md)  
 <span data-ttu-id="610c3-135">A operação de interrupção não foi concluída no tempo determinado.</span><span class="sxs-lookup"><span data-stu-id="610c3-135">The stop operation failed to complete within the given time.</span></span>  
  
 [<span data-ttu-id="610c3-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="610c3-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="610c3-137">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="610c3-137">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="610c3-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="610c3-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="610c3-139">Não é possível recuperar uma pasta de perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="610c3-139">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="610c3-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="610c3-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="610c3-141">Não é possível acessar uma pasta de instância.</span><span class="sxs-lookup"><span data-stu-id="610c3-141">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="610c3-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="610c3-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="610c3-143">Não é possível acessar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="610c3-143">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="610c3-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="610c3-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="610c3-145">Uma configuração de instância está corrompida.</span><span class="sxs-lookup"><span data-stu-id="610c3-145">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="610c3-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="610c3-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="610c3-147">O chamador de API não é proprietário da instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="610c3-147">API caller is not LocalDB instance owner.</span></span>  
  
 [<span data-ttu-id="610c3-148">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="610c3-148">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="610c3-149">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="610c3-149">An unexpected error occurred.</span></span> <span data-ttu-id="610c3-150">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="610c3-150">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="610c3-151">Comentários</span><span class="sxs-lookup"><span data-stu-id="610c3-151">Remarks</span></span>  
 <span data-ttu-id="610c3-152">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="610c3-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610c3-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="610c3-153">See Also</span></span>  
 [<span data-ttu-id="610c3-154">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="610c3-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
