---
title: Função LocalDBStartInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: cb325f5d-10ee-4a56-ba28-db0074ab3926
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 748bc373e8b0dbad0a91247e068d21b67f2dbc1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583071"
---
# <a name="localdbstartinstance-function"></a><span data-ttu-id="cfda1-102">Função LocalDBStartInstance</span><span class="sxs-lookup"><span data-stu-id="cfda1-102">LocalDBStartInstance Function</span></span>
  <span data-ttu-id="cfda1-103">Inicia a instância especificada de LocalDB do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="cfda1-103">Starts the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="cfda1-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="cfda1-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfda1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cfda1-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           LPWSTR wszSqlConnection,   
           LPDWORD lpcchSqlConnection   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfda1-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cfda1-106">Parameters</span></span>  
 <span data-ttu-id="cfda1-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="cfda1-107">*pInstanceName*</span></span>  
 <span data-ttu-id="cfda1-108">[Entrada] O nome da instância de LocalDB a ser iniciada.</span><span class="sxs-lookup"><span data-stu-id="cfda1-108">[Input] The name of the LocalDB instance to start.</span></span>  
  
 <span data-ttu-id="cfda1-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="cfda1-109">*dwFlags*</span></span>  
 <span data-ttu-id="cfda1-110">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="cfda1-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="cfda1-111">Atualmente deve ser definido como 0.</span><span class="sxs-lookup"><span data-stu-id="cfda1-111">Currently should be set to 0.</span></span>  
  
 <span data-ttu-id="cfda1-112">*wszSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="cfda1-112">*wszSqlConnection*</span></span>  
 <span data-ttu-id="cfda1-113">[Saída] O buffer para armazenar a cadeia de conexão na instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cfda1-113">[Output] The buffer to store the connection string to the LocalDB instance.</span></span>  
  
 <span data-ttu-id="cfda1-114">*lpcchSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="cfda1-114">*lpcchSqlConnection*</span></span>  
 <span data-ttu-id="cfda1-115">[Saída/entrada] On input contém o tamanho do buffer *wszSqlConnection* em caracteres, incluindo qualquer caractere nulo à esquerda.</span><span class="sxs-lookup"><span data-stu-id="cfda1-115">[Input/Output] On input contains the size of the *wszSqlConnection* buffer in characters, including any trailing nulls.</span></span> <span data-ttu-id="cfda1-116">Na saída, se o tamanho de buffer especificado for muito pequeno, conterá o tamanho de buffer necessário em caracteres, incluindo quaisquer caracteres nulos à esquerda.</span><span class="sxs-lookup"><span data-stu-id="cfda1-116">On output, if the given buffer size is too small, contains the required buffer size in characters, including any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cfda1-117">Retornos</span><span class="sxs-lookup"><span data-stu-id="cfda1-117">Returns</span></span>  
 <span data-ttu-id="cfda1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="cfda1-118">S_OK</span></span>  
 <span data-ttu-id="cfda1-119">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="cfda1-119">The function succeeded.</span></span>  
  
 [<span data-ttu-id="cfda1-120">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="cfda1-120">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="cfda1-121">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="cfda1-121">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="cfda1-122">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="cfda1-122">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="cfda1-123">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="cfda1-123">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="cfda1-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="cfda1-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="cfda1-125">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="cfda1-125">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="cfda1-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="cfda1-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="cfda1-127">A instância não existe.</span><span class="sxs-lookup"><span data-stu-id="cfda1-127">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="cfda1-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cfda1-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="cfda1-129">O buffer *wszSqlConnection* especificado é muito pequeno.</span><span class="sxs-lookup"><span data-stu-id="cfda1-129">The specified buffer *wszSqlConnection* is too small.</span></span>  
  
 [<span data-ttu-id="cfda1-130">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cfda1-130">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="cfda1-131">Tempo limite esgotado durante tentativa de obtenção de bloqueios de sincronização.</span><span class="sxs-lookup"><span data-stu-id="cfda1-131">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="cfda1-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="cfda1-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="cfda1-133">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="cfda1-133">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="cfda1-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="cfda1-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="cfda1-135">Não é possível recuperar uma pasta de perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="cfda1-135">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="cfda1-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="cfda1-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="cfda1-137">Não é possível acessar uma pasta de instância.</span><span class="sxs-lookup"><span data-stu-id="cfda1-137">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="cfda1-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="cfda1-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="cfda1-139">Não é possível acessar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="cfda1-139">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="cfda1-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="cfda1-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="cfda1-141">Não é possível modificar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="cfda1-141">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="cfda1-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="cfda1-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-sql-process.md)  
 <span data-ttu-id="cfda1-143">Não é possível criar um processo para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfda1-143">A process for SQL Server cannot be created.</span></span>  
  
 [<span data-ttu-id="cfda1-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="cfda1-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="cfda1-145">Um processo do SQL Server foi iniciado, mas houve falha na inicialização do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfda1-145">A SQL Server process was started, but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="cfda1-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="cfda1-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="cfda1-147">Uma configuração de instância foi corrompida.</span><span class="sxs-lookup"><span data-stu-id="cfda1-147">An instance configuration was corrupted.</span></span>  
  
 [<span data-ttu-id="cfda1-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="cfda1-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span></span>](../express-localdb-error-messages/localdb-error-auto-instance-create-failed.md)  
 <span data-ttu-id="cfda1-149">Não é possível criar uma instância automática.</span><span class="sxs-lookup"><span data-stu-id="cfda1-149">Cannot create an automatic instance.</span></span> <span data-ttu-id="cfda1-150">Consulte o log de eventos de Aplicativo do Windows para obter detalhes sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="cfda1-150">See the Windows Application event log for error details.</span></span>  
  
 [<span data-ttu-id="cfda1-151">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="cfda1-151">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="cfda1-152">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="cfda1-152">An unexpected error occurred.</span></span> <span data-ttu-id="cfda1-153">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="cfda1-153">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfda1-154">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cfda1-154">Details</span></span>  
 <span data-ttu-id="cfda1-155">O argumento do buffer de conexão (*wszSqlConnection*) e o argumento do tamanho do buffer de conexão (*lpcchSqlConnection*) são opcionais.</span><span class="sxs-lookup"><span data-stu-id="cfda1-155">Both the connection buffer argument (*wszSqlConnection*) and the connection buffer size argument (*lpcchSqlConnection*) are optional.</span></span> <span data-ttu-id="cfda1-156">A tabela a seguir mostra opções para o uso desses argumentos e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="cfda1-156">The following table shows options for using these arguments and their results.</span></span>  
  
|<span data-ttu-id="cfda1-157">Buffer</span><span class="sxs-lookup"><span data-stu-id="cfda1-157">Buffer</span></span>|<span data-ttu-id="cfda1-158">Tamanho do buffer</span><span class="sxs-lookup"><span data-stu-id="cfda1-158">Buffer size</span></span>|<span data-ttu-id="cfda1-159">Fundamento</span><span class="sxs-lookup"><span data-stu-id="cfda1-159">Rationale</span></span>|<span data-ttu-id="cfda1-160">Ação</span><span class="sxs-lookup"><span data-stu-id="cfda1-160">Action</span></span>|  
|------------|-----------------|---------------|------------|  
|<span data-ttu-id="cfda1-161">NULO</span><span class="sxs-lookup"><span data-stu-id="cfda1-161">NULL</span></span>|<span data-ttu-id="cfda1-162">NULO</span><span class="sxs-lookup"><span data-stu-id="cfda1-162">NULL</span></span>|<span data-ttu-id="cfda1-163">O usuário deseja iniciar a instância e não precisa de um nome de pipe.</span><span class="sxs-lookup"><span data-stu-id="cfda1-163">User wants to start the instance and doesn't need a pipe name.</span></span>|<span data-ttu-id="cfda1-164">Inicia uma instância (sem retorno de pipe e sem retorno do tamanho de buffer necessário).</span><span class="sxs-lookup"><span data-stu-id="cfda1-164">Starts an instance (no pipe return and no required buffer size return).</span></span>|  
|<span data-ttu-id="cfda1-165">NULO</span><span class="sxs-lookup"><span data-stu-id="cfda1-165">NULL</span></span>|<span data-ttu-id="cfda1-166">Presente</span><span class="sxs-lookup"><span data-stu-id="cfda1-166">Present</span></span>|<span data-ttu-id="cfda1-167">O usuário solicita o tamanho do buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="cfda1-167">User asks for the output buffer size.</span></span> <span data-ttu-id="cfda1-168">(Na próxima chamada, o usuário provavelmente solicitará uma inicialização real.)</span><span class="sxs-lookup"><span data-stu-id="cfda1-168">(In the next call the user will probably ask for an actual start.)</span></span>|<span data-ttu-id="cfda1-169">Retorna um tamanho de buffer necessário (sem inicialização e sem retorno de pipe).</span><span class="sxs-lookup"><span data-stu-id="cfda1-169">Returns a required buffer size (no start and no pipe return).</span></span> <span data-ttu-id="cfda1-170">O resultado é S_OK.</span><span class="sxs-lookup"><span data-stu-id="cfda1-170">Result is S_OK.</span></span>|  
|<span data-ttu-id="cfda1-171">Presente</span><span class="sxs-lookup"><span data-stu-id="cfda1-171">Present</span></span>|<span data-ttu-id="cfda1-172">NULO</span><span class="sxs-lookup"><span data-stu-id="cfda1-172">NULL</span></span>|<span data-ttu-id="cfda1-173">Não permitido; entrada incorreta.</span><span class="sxs-lookup"><span data-stu-id="cfda1-173">Not allowed; incorrect input.</span></span>|<span data-ttu-id="cfda1-174">O resultado retornado é LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="cfda1-174">Returned result is LOCALDB_ERROR_INVALID_PARAMETER.</span></span>|  
|<span data-ttu-id="cfda1-175">Presente</span><span class="sxs-lookup"><span data-stu-id="cfda1-175">Present</span></span>|<span data-ttu-id="cfda1-176">Presente</span><span class="sxs-lookup"><span data-stu-id="cfda1-176">Present</span></span>|<span data-ttu-id="cfda1-177">O usuário deseja iniciar a instância e precisa do nome do pipe para se conectar a ela após a inicialização.</span><span class="sxs-lookup"><span data-stu-id="cfda1-177">User wants to start the instance and needs the pipe name to connect to it after it is started.</span></span>|<span data-ttu-id="cfda1-178">Verifica o tamanho do buffer, inicia a instância e retorna o nome do pipe no buffer.</span><span class="sxs-lookup"><span data-stu-id="cfda1-178">Checks the buffer size, starts the instance, and returns the pipe name in the buffer.</span></span> <br /><span data-ttu-id="cfda1-179">O argumento tamanho do buffer retorna o comprimento da cadeia de caracteres "Server =", sem incluir nulos de terminação.</span><span class="sxs-lookup"><span data-stu-id="cfda1-179">The buffer size argument returns the length of the "server=" string, not including terminating nulls.</span></span>|  
  
 <span data-ttu-id="cfda1-180">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="cfda1-180">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfda1-181">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cfda1-181">See Also</span></span>  
 [<span data-ttu-id="cfda1-182">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="cfda1-182">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
