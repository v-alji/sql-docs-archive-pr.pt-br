---
title: Função LocalDBDeleteInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBDeleteInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 37cb2a7e-672a-4223-b6f3-a94d7b8d58cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8d4c873e045c5effed476ca9d147270d159ec3b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576408"
---
# <a name="localdbdeleteinstance-function"></a><span data-ttu-id="25f01-102">Função LocalDBDeleteInstance</span><span class="sxs-lookup"><span data-stu-id="25f01-102">LocalDBDeleteInstance Function</span></span>
  <span data-ttu-id="25f01-103">Remove a instância especificada de LocalDB do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="25f01-103">Removes the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="25f01-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="25f01-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f01-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25f01-105">Syntax</span></span>  
  
```  
HRESULT LocalDBDeleteInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25f01-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="25f01-106">Parameters</span></span>  
 <span data-ttu-id="25f01-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="25f01-107">*pInstanceName*</span></span>  
 <span data-ttu-id="25f01-108">[Entrada] O nome da instância de LocalDB a ser removida.</span><span class="sxs-lookup"><span data-stu-id="25f01-108">[Input] The name of the LocalDB instance to remove.</span></span>  
  
 <span data-ttu-id="25f01-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="25f01-109">*dwFlags*</span></span>  
 <span data-ttu-id="25f01-110">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="25f01-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="25f01-111">Atualmente deve ser definido como 0.</span><span class="sxs-lookup"><span data-stu-id="25f01-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="25f01-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="25f01-112">Returns</span></span>  
 <span data-ttu-id="25f01-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="25f01-113">S_OK</span></span>  
 <span data-ttu-id="25f01-114">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="25f01-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="25f01-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="25f01-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="25f01-116">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="25f01-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="25f01-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="25f01-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="25f01-118">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="25f01-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="25f01-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="25f01-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="25f01-120">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="25f01-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="25f01-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="25f01-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="25f01-122">A instância especificada não existe.</span><span class="sxs-lookup"><span data-stu-id="25f01-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="25f01-123">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="25f01-123">LOCALDB_ERROR_INSTANCE_BUSY</span></span>](../express-localdb-error-messages/localdb-error-instance-busy.md)  
 <span data-ttu-id="25f01-124">A instância especificada está em execução.</span><span class="sxs-lookup"><span data-stu-id="25f01-124">The specified instance is running.</span></span>  
  
 [<span data-ttu-id="25f01-125">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="25f01-125">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="25f01-126">Tempo limite esgotado durante tentativa de obtenção de bloqueios de sincronização.</span><span class="sxs-lookup"><span data-stu-id="25f01-126">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
 [<span data-ttu-id="25f01-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="25f01-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="25f01-128">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="25f01-128">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="25f01-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="25f01-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="25f01-130">Não é possível recuperar uma pasta de perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="25f01-130">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="25f01-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="25f01-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="25f01-132">Não é possível acessar uma pasta de instância.</span><span class="sxs-lookup"><span data-stu-id="25f01-132">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="25f01-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="25f01-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="25f01-134">Não é possível acessar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="25f01-134">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="25f01-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="25f01-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="25f01-136">Não é possível modificar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="25f01-136">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="25f01-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="25f01-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="25f01-138">Uma configuração de instância está corrompida.</span><span class="sxs-lookup"><span data-stu-id="25f01-138">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="25f01-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="25f01-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="25f01-140">O chamador de API não é proprietário da instância de Banco de Dados Local.</span><span class="sxs-lookup"><span data-stu-id="25f01-140">API caller is not Local Database instance owner.</span></span>  
  
 [<span data-ttu-id="25f01-141">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="25f01-141">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="25f01-142">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="25f01-142">An unexpected error occurred.</span></span> <span data-ttu-id="25f01-143">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="25f01-143">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25f01-144">Comentários</span><span class="sxs-lookup"><span data-stu-id="25f01-144">Remarks</span></span>  
 <span data-ttu-id="25f01-145">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="25f01-145">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f01-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25f01-146">See Also</span></span>  
 [<span data-ttu-id="25f01-147">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="25f01-147">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
