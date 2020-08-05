---
title: Função LocalDBShareInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBShareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 21eb3b9a-7d32-455b-89bb-f624198cd202
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 238bff0b3512ceb03ead186dc001165274bd4e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573004"
---
# <a name="localdbshareinstance-function"></a><span data-ttu-id="9006a-102">Função LocalDBShareInstance</span><span class="sxs-lookup"><span data-stu-id="9006a-102">LocalDBShareInstance Function</span></span>
  <span data-ttu-id="9006a-103">Compartilha a instância especificada do LocalDB do SQL Server Express com outros usuários do computador, usando o nome compartilhado especificado.</span><span class="sxs-lookup"><span data-stu-id="9006a-103">Shares the specified SQL Server Express LocalDB instance with other users of the computer, using the specified shared name.</span></span>  
  
 <span data-ttu-id="9006a-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="9006a-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9006a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9006a-105">Syntax</span></span>  
  
```  
HRESULT LocalDBShareInstance(  
           PSID pOwnerSID,  
           PCWSTR pInstancePrivateName,  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9006a-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9006a-106">Parameters</span></span>  
 <span data-ttu-id="9006a-107">*pOwnerSID*</span><span class="sxs-lookup"><span data-stu-id="9006a-107">*pOwnerSID*</span></span>  
 <span data-ttu-id="9006a-108">[Entrada] O SID do proprietário da instância.</span><span class="sxs-lookup"><span data-stu-id="9006a-108">[Input] The SID of the instance owner.</span></span>  
  
 <span data-ttu-id="9006a-109">*pInstancePrivateName*</span><span class="sxs-lookup"><span data-stu-id="9006a-109">*pInstancePrivateName*</span></span>  
 <span data-ttu-id="9006a-110">[Entrada] O nome privado da instância de LocalDB a ser compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9006a-110">[Input] The private name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="9006a-111">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="9006a-111">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="9006a-112">[Entrada] O nome compartilhado da instância de LocalDB a ser compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9006a-112">[Input] The shared name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="9006a-113">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="9006a-113">*dwFlags*</span></span>  
 <span data-ttu-id="9006a-114">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="9006a-114">[Input] Reserved for future use.</span></span> <span data-ttu-id="9006a-115">Atualmente deve ser definido como 0.</span><span class="sxs-lookup"><span data-stu-id="9006a-115">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9006a-116">Retornos</span><span class="sxs-lookup"><span data-stu-id="9006a-116">Returns</span></span>  
 <span data-ttu-id="9006a-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="9006a-117">S_OK</span></span>  
 <span data-ttu-id="9006a-118">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="9006a-118">The function succeeded.</span></span>  
  
 [<span data-ttu-id="9006a-119">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="9006a-119">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="9006a-120">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="9006a-120">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="9006a-121">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="9006a-121">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="9006a-122">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="9006a-122">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="9006a-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="9006a-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="9006a-124">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="9006a-124">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="9006a-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="9006a-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="9006a-126">A instância especificada não existe.</span><span class="sxs-lookup"><span data-stu-id="9006a-126">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="9006a-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="9006a-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="9006a-128">É preciso ter privilégios de administrador para executar esta operação.</span><span class="sxs-lookup"><span data-stu-id="9006a-128">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="9006a-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span><span class="sxs-lookup"><span data-stu-id="9006a-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span></span>](../express-localdb-error-messages/localdb-error-shared-name-taken.md)  
 <span data-ttu-id="9006a-130">O nome compartilhado especificado já está sendo utilizado.</span><span class="sxs-lookup"><span data-stu-id="9006a-130">The specified shared name is already taken.</span></span>  
  
 [<span data-ttu-id="9006a-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="9006a-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>](../express-localdb-error-messages/localdb-error-instance-already-shared.md)  
 <span data-ttu-id="9006a-132">A instância especificada já está compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9006a-132">The specified instance is already shared.</span></span>  
  
 [<span data-ttu-id="9006a-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="9006a-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="9006a-134">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="9006a-134">An unexpected error occurred.</span></span> <span data-ttu-id="9006a-135">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="9006a-135">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9006a-136">Comentários</span><span class="sxs-lookup"><span data-stu-id="9006a-136">Remarks</span></span>  
 <span data-ttu-id="9006a-137">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9006a-137">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9006a-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9006a-138">See Also</span></span>  
 [<span data-ttu-id="9006a-139">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="9006a-139">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
